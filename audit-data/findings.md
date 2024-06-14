### [M-1] Denial-of-Service in `PuppyRaffle:enterRaffle`, unbound variable `player.length` will exceed block gas limit eventually denying execution of the function

**Description:**
The `PuppyRaffle:enterRaffle` iterates twice over every player which is a gas intensive operation.
The gas costs can potentially grow infinitely, reaching to block gas limit and even before discouraging players from joining the raffle. The costs increase linearly as shown in the PoC.

DoS possibility

```javascript
 for (uint256 i = 0; i < players.length - 1; i++) {
        for (uint256 j = i + 1; j < players.length; j++) {
            // @audit: When to player refunded, their address is set to address(0). When at least two players are refunded, the check will fail
            require(players[i] != players[j], "PuppyRaffle: Duplicate player");
        }
    }
```

**Impact:**
Prevents players from entering the raffle.

**Proof of Concept:**
The following tests shows that the gas costs grow linearly with the number of players:

<details>
<Summary> Test code snippet</Summary>

```javascript
function testDosEnterRaffle() public {
        uint256 newPlayersToJoin = 100;
        for (uint256 i = 0; i < newPlayersToJoin; i++) {
            address[] memory players = new address[](1);
            players[0] = address(uint160(i));
            uint256 gasBefore = gasleft();
            puppyRaffle.enterRaffle{value: entranceFee}(players);
            uint256 gasAfter = gasleft();
            console.log("Gas used:", gasBefore - gasAfter);
        }
    }
```

</details>


**Recommended Mitigation:**
There are two potential options:

1. Remove the check for duplicate address since players could enter with other wallets multiple times either way
2. Store the players that have entered in a mapping which can directly accessed by player address for checking if the player has already entered
   1. OpenZeppelins enumerables might help here: [Enumerables](https://docs.openzeppelin.com/contracts/3.x/api/utils#EnumerableMap)
