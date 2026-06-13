# Sanitized review findings

## Purpose

This artifact shows sample governance findings for the fictional **Northstar Identity Lab** scenario.

The findings are written in a public-safe format. They do not include screenshots, real user data, tenant details, object IDs, source IDs, URLs, secrets, tokens, API keys, or internal training material.

## Findings summary

| ID      | Area             | Finding                                                      | Risk   | Suggested action                                              |
| ------- | ---------------- | ------------------------------------------------------------ | ------ | ------------------------------------------------------------- |
| GOV-001 | Identity profile | Manager value should be present for review context           | Medium | Validate manager mapping and fallback process                 |
| GOV-002 | Lifecycle state  | Mover changes should trigger access review                   | Medium | Review department changes against assigned access             |
| GOV-003 | Access profile   | Requestable access needs clear business descriptions         | Low    | Add short descriptions for requester and approver clarity     |
| GOV-004 | Role review      | Role membership should be checked against department context | Medium | Compare role assignment to job and department                 |
| GOV-005 | Certification    | Reviewers need entitlement and access profile context        | Medium | Include access purpose and owner context in review notes      |
| GOV-006 | Search           | Search queries can support access validation                 | Low    | Use search to confirm identity, lifecycle, and access context |

## GOV-001: Manager value should be present for review context

| Field                | Details                                                                                                                 |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Review area          | Identity profile and human identity context                                                                             |
| Observation          | A governed identity should have manager context available for review and approval decisions.                            |
| Why it matters       | Missing manager context can make certification and access request review harder.                                        |
| Public-safe evidence | Fictional identity record had department and title context, but manager context was treated as a required review field. |
| Suggested action     | Validate that manager mapping is populated and define a fallback review path when manager data is missing.              |

## GOV-002: Mover changes should trigger access review

| Field                | Details                                                                                                                                                                                                   |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Review area          | Lifecycle governance                                                                                                                                                                                      |
| Observation          | A department or job change should trigger a review of previously assigned access.                                                                                                                         |
| Why it matters       | Movers may keep access from a prior role if access is not reviewed after their business context changes.                                                                                                  |
| Public-safe evidence | Fictional mover scenario changed from Operations to Finance while retaining prior team access.                                                                                                            |
| Review question      | Does the retained access still match the identity's new department, job title, manager context, and business need?                                                                                        |
| Suggested action     | Compare old access against the new department, job title, lifecycle state, and expected role access. Keep access only when there is a clear business reason. Remove or review access that no longer fits. |
| Related artifact     | [`artifacts/mover-review-case-study.md`](mover-review-case-study.md)                                                                                                                                      |

## GOV-003: Requestable access needs clear business descriptions

| Field                | Details                                                                                           |
| -------------------- | ------------------------------------------------------------------------------------------------- |
| Review area          | Access profiles and access request settings                                                       |
| Observation          | Access profiles should have short descriptions that explain the business purpose.                 |
| Why it matters       | Requesters and approvers need to understand what access grants before approval.                   |
| Public-safe evidence | Fictional access profile name was understandable, but the request purpose needed clearer wording. |
| Suggested action     | Add plain-language descriptions for requestable access profiles.                                  |

## GOV-004: Role membership should be checked against department context

| Field                | Details                                                                            |
| -------------------- | ---------------------------------------------------------------------------------- |
| Review area          | Roles                                                                              |
| Observation          | Role assignment should be reviewed against department, title, and lifecycle state. |
| Why it matters       | Role-based access can become risky if users remain in roles after job changes.     |
| Public-safe evidence | Fictional identity had role access that required department validation.            |
| Suggested action     | Review role membership during mover and certification reviews.                     |

## GOV-005: Reviewers need entitlement and access profile context

| Field                | Details                                                                                                                         |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| Review area          | Certifications                                                                                                                  |
| Observation          | Certification reviewers need more than entitlement names to make good decisions.                                                |
| Why it matters       | Approving or revoking access without business context increases the chance of mistakes.                                         |
| Public-safe evidence | Fictional certification scenario included identity, lifecycle state, department, access profile, role, and entitlement context. |
| Suggested action     | Provide enough context for reviewers to approve, revoke, or investigate access.                                                 |

## GOV-006: Search can support access validation

| Field                | Details                                                                                      |
| -------------------- | -------------------------------------------------------------------------------------------- |
| Review area          | Search and Identity Graph                                                                    |
| Observation          | Search can help validate identity status, access assignments, and review context.            |
| Why it matters       | Analysts need a fast way to answer access questions without relying only on request history. |
| Public-safe evidence | Fictional review used Search and Identity Graph concepts to trace access context.            |
| Suggested action     | Use search-based validation as part of access review and troubleshooting workflows.          |

## Overall takeaway

The main governance theme is context.

An IAM analyst should be able to explain who has access, why they may need it, how they received it, whether it still matches their lifecycle state, and what evidence supports a review decision.
