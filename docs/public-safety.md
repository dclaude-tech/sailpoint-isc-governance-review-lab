# Public safety

## Purpose

This document explains how this repo keeps the SailPoint ISC governance review public-safe.

The goal is to show IAM analyst thinking without exposing tenant details, screenshots, internal training content, or private implementation information.

## What is not included

This repo does not include:

| Excluded item                | Reason                                                                                     |
| ---------------------------- | ------------------------------------------------------------------------------------------ |
| Screenshots                  | Avoids publishing tenant UI, branding, designs, graphics, and training environment content |
| Real employee data           | Protects personal and organizational information                                           |
| Tenant names or URLs         | Avoids exposing environment details                                                        |
| Object IDs or source IDs     | Avoids exposing implementation-specific values                                             |
| Connector details            | Avoids exposing private configuration patterns                                             |
| Secrets, tokens, or API keys | Prevents credential exposure                                                               |
| Internal course instructions | Avoids reproducing private training material                                               |
| Proprietary UI content       | Keeps the project public-safe                                                              |

## What is included instead

| Public-safe item           | How it is used                                                         |
| -------------------------- | ---------------------------------------------------------------------- |
| Fictional organization     | Northstar Identity Lab is used as the scenario                         |
| Written summaries          | Analyst observations are described in plain language                   |
| Recreated Mermaid diagrams | Diagrams explain concepts without copying product screens              |
| Sanitized findings         | Findings use fictional examples and no tenant evidence                 |
| Generic attributes         | Examples use safe fields like department, manager, and lifecycle state |
| Short tables               | Tables make the review easy to scan                                    |

## Fictional examples

The examples in this repo are fictional and intentionally simple.

Example fictional values may include:

| Example              | Type                   |
| -------------------- | ---------------------- |
| Finance Analyst      | Job context            |
| HR Coordinator       | Job context            |
| Active               | Lifecycle state        |
| Terminated           | Lifecycle state        |
| Finance Reports Read | Access profile example |
| Payroll Viewer       | Entitlement example    |

These examples are used only to explain governance review thinking.

## Sanitization rules used

Before anything is included in the public repo, it should pass this check:

| Check                                      | Public-safe version                                 |
| ------------------------------------------ | --------------------------------------------------- |
| Does it include a real person?             | Replace with a fictional user or role               |
| Does it include a tenant value?            | Remove it                                           |
| Does it include a screenshot?              | Replace with a written summary or recreated diagram |
| Does it include an ID?                     | Remove it or describe the concept generically       |
| Does it copy training instructions?        | Rewrite as original analyst notes                   |
| Does it sound like official documentation? | Rewrite in a personal portfolio voice               |

## Boundary statement

This is a personal portfolio lab based on SailPoint Identity Security Cloud governance concepts reviewed in a temporary training tenant.

The project demonstrates IAM governance review thinking and safe technical documentation.

It does not claim production SailPoint administration experience and is not official SailPoint documentation, training material, implementation guidance, or product advice.
