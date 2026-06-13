# Analyst review

## Purpose

This document summarizes the IAM governance areas reviewed for the fictional **Northstar Identity Lab** scenario.

The goal is to show analyst thinking around SailPoint ISC governance concepts without using screenshots, tenant details, real user records, or internal training material.

## Review approach

| Review area        | Analyst question                                                            |
| ------------------ | --------------------------------------------------------------------------- |
| Identity profiles  | Is identity data shaped into useful governance context?                     |
| Attribute mappings | Are key attributes available for lifecycle, access, and review decisions?   |
| Human identities   | Can a reviewer understand who the identity is and why access may be needed? |
| Lifecycle states   | Does identity status support joiner, mover, and leaver decisions?           |
| Entitlements       | Are low-level permissions understandable and tied to business access?       |
| Access profiles    | Is access grouped in a way that supports requests and reviews?              |
| Roles              | Do roles reflect expected access for a job, team, or department?            |
| Access requests    | Are request settings clear enough for approval and least privilege review?  |
| Certifications     | Can reviewers make informed approve, revoke, or investigate decisions?      |
| Search             | Can analysts validate identity and access questions quickly?                |
| Identity Graph     | Does relationship context help explain access ownership and risk?           |

## Identity profile and attribute mapping review

A useful identity profile should help turn source data into reviewable identity context.

For this fictional scenario, the review focuses on attributes such as:

| Attribute         | Why it matters                                      |
| ----------------- | --------------------------------------------------- |
| Display name      | Helps reviewers identify the person                 |
| Department        | Supports role and access expectations               |
| Manager           | Supports approval and certification routing context |
| Job title         | Helps compare assigned access against business need |
| Employment status | Supports joiner, mover, and leaver review           |
| Start date        | Helps validate joiner timing                        |
| End date          | Helps validate leaver cleanup timing                |
| Location          | May affect regional access or policy context        |

The main analyst question is simple: **does the identity record give enough context to explain access?**

## Human identity review

Human identity review is not just about whether an account exists. It is about whether the identity has the right context for governance.

| Context         | Analyst use                                                |
| --------------- | ---------------------------------------------------------- |
| Manager         | Confirms who may review or approve access                  |
| Department      | Helps evaluate expected access                             |
| Lifecycle state | Shows whether access should be active, limited, or removed |
| Assigned access | Shows what the identity currently has                      |
| Role membership | Helps compare access against business function             |

## Lifecycle state review

Lifecycle states help connect identity status to access decisions.

| Lifecycle event | Review focus                                                    |
| --------------- | --------------------------------------------------------------- |
| Joiner          | Is baseline access assigned only after the identity is ready?   |
| Mover           | Does old access get reviewed when department or job changes?    |
| Leaver          | Is access removed when the identity should no longer be active? |

The main risk is stale access. A mover or leaver process can leave access behind if lifecycle context is unclear or not reviewed.

## Example mover review

A mover review checks whether access still matches the identity's updated business context after a department or job change.

For the fictional Northstar Identity Lab scenario, the analyst question was:

> Does the identity still have access from the prior department that should be reviewed, removed, or reapproved?

| Review point           | Analyst check                                                |
| ---------------------- | ------------------------------------------------------------ |
| Department change      | Compare previous department to current department            |
| Job title change       | Confirm whether assigned access still supports the new role  |
| Manager context        | Confirm who can validate current business need               |
| Assigned access        | Identify access that may belong to the previous role         |
| Role membership        | Check whether role-based access still matches the identity   |
| Access profile context | Confirm the business purpose and owner of requestable access |
| Review outcome         | Keep, remove, or investigate access based on business need   |

The goal is not to assume all old access is wrong. The goal is to identify access that needs review because the identity's business context changed.

Related artifact: [Mover review case study](../artifacts/mover-review-case-study.md)

## Access model review

The access model is reviewed from low-level permissions up to business-level access.

| Layer           | Review question                                                 |
| --------------- | --------------------------------------------------------------- |
| Entitlement     | What permission is being granted?                               |
| Access profile  | What business access does this group of entitlements represent? |
| Role            | Is the access expected for this job or department?              |
| Request setting | Who can request it, and what approval is needed?                |
| Certification   | Should the access remain assigned?                              |

A strong access model should make access easier to request, approve, review, and remove.

## Access request settings review

Access request settings are important because they affect how access enters the environment.

Areas reviewed:

| Area                 | Why it matters                                            |
| -------------------- | --------------------------------------------------------- |
| Request visibility   | Prevents users from requesting access they should not see |
| Approval path        | Helps ensure the right person reviews the request         |
| Access profile owner | Gives accountability for the access                       |
| Description          | Helps requesters and approvers understand the access      |
| Risk context         | Helps reviewers identify sensitive or broad access        |

## Certification review context

Certification decisions should not be made from access names alone.

A reviewer needs enough context to answer:

| Question                       | Why it matters                                    |
| ------------------------------ | ------------------------------------------------- |
| Who has the access?            | Confirms the identity being reviewed              |
| What is their lifecycle state? | Flags joiner, mover, or leaver concerns           |
| What department are they in?   | Supports business-need review                     |
| Who is their manager?          | Supports reviewer accountability                  |
| What access is assigned?       | Shows what may need approval or removal           |
| Is access tied to a role?      | Helps distinguish expected access from exceptions |
| Is the entitlement sensitive?  | Helps prioritize review attention                 |

## Search and Identity Graph review

Search and Identity Graph can help analysts validate identity and access questions.

| Tool concept   | Analyst use                                                                        |
| -------------- | ---------------------------------------------------------------------------------- |
| Search         | Validate identities, access assignments, lifecycle state, and review context       |
| Identity Graph | Understand relationships between identities, access, roles, and governance objects |

The review focus is not on capturing tenant output. The focus is on showing how an analyst would use identity and access context to investigate a governance question.

## Summary

This review shows how IAM governance concepts connect:

* Source identity data supports identity profiles.
* Identity profiles support lifecycle states and governed identities.
* Governed identities connect to access profiles, roles, requests, certifications, Search, and Identity Graph context.
* The analyst goal is to find where access is clear, where it is risky, and where documentation needs to be improved.
