---
title: Protocol Audit Report
author: Tim Sigl
date: TODO: DATE
header-includes:
    - \usepackage{titling}
    - \usepackage{graphicx}
---

\begin{titlepage}
\centering
\begin{figure}[h]
\centering
\includegraphics[width=0.5\textwidth]{logo.pdf}
\end{figure}
\vspace{2cm}
{\Huge\bfseries Protocol Audit Report\par}
\vspace{1cm}
{\Large Version 1.0\par}
\vspace{2cm}
{\Large\itshape Tim Sigl\par}
\vfill
{\large \today\par}
\end{titlepage}

\maketitle

<!-- Your report starts here! -->

Prepared by: [Tim Sigl](https://timsigl.de)
Lead Security Researcher:

-   Tim Sigl

# Table of Contents

- [Table of Contents](#table-of-contents)
- [Protocol Summary](#protocol-summary)
- [Disclaimer](#disclaimer)
- [Risk Classification](#risk-classification)
- [Audit Details](#audit-details)
  - [Scope](#scope)
  - [Roles](#roles)
- [Executive Summary](#executive-summary)
  - [Issues found](#issues-found)
- [Findings](#findings)
  - [High](#high)
  - [Medium](#medium)
  - [Low](#low)
  - [Informational](#informational)
    - [\[S-#\] Title (ROOT CAUSE + IMPACT)](#s--title-root-cause--impact)

# Protocol Summary

TODO: SUMMARY

# Disclaimer

The Tim-team makes all effort to find as many vulnerabilities in the code in the given time period, but holds no responsibilities for the findings provided in this document. A security audit by the team is not an endorsement of the underlying business or product. The audit was time-boxed and the review of the code was solely on the security aspects of the Solidity implementation of the contracts.

# Risk Classification

|            |        | Impact |        |     |
| ---------- | ------ | ------ | ------ | --- |
|            |        | High   | Medium | Low |
|            | High   | H      | H/M    | M   |
| Likelihood | Medium | H/M    | M      | M/L |
|            | Low    | M      | M/L    | L   |

We use the [CodeHawks](https://docs.codehawks.com/hawks-auditors/how-to-evaluate-a-finding-severity) severity matrix to determine severity. See the documentation for more details.

# Audit Details

**The findings described in this document correspond with the following commit hash:**

```
TODO: COMMIT-HASH
```

## Scope

```
TODO: SCOPE
```

## Roles

- TODO: ROLES

# Executive Summary

TODO: SUMMARY

## Issues found

| Severity | Number of Findings |
| -------- | ------------------ |
| High     | x                  |
| Medium   | x                  |
| Low      | x                  |
| Info     | x                  |
| Total    | x                  |

# Findings

## High

## Medium

## Low

## Informational


### [S-#] Title (ROOT CAUSE + IMPACT)

**Description:** 

**Impact:** 

**Proof of Concept:**

<details>
<Summary>Code Snippet</Summary>

```javascript

```

</details>

**Recommended Mitigation:** 

<details>
<Summary>Mitigation Example</Summary>

```diff
-
+
```

</details>