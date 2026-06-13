# Mover review case study

## Purpose

This fictional case study shows how an IAM analyst might review access after a department change in SailPoint Identity Security Cloud.

The scenario is public-safe and does not include screenshots, tenant data, real user records, object IDs, URLs, secrets, tokens, API keys, or internal training material.

## Scenario

A fictional employee at Northstar Identity Lab moved from Operations to Finance.

The analyst review question was:

> Does the identity still have access from the prior department that should be reviewed, removed, or reapproved?

## Fictional identity context

| Field | Value |
| --- | --- |
| Identity | Jordan Lee |
| Previous department | Operations |
| New department | Finance |
| Previous role context | Operations specialist |
| New role context | Finance analyst |
| Lifecycle event | Mover |
| Review focus | Validate whether prior access still matches business need |

## Access reviewed

| Access item | Business context | Review question | Result |
| --- | --- | --- | --- |
| Operations team access | Prior department access | Is this still required after the move to Finance? | Review needed |
| Finance reports access | New department access | Does this align with the new role? | Expected access |
| Baseline employee access | Standard employee access | Should this remain assigned? | Keep |
| Elevated or sensitive access | Higher-risk access | Is there a clear owner, purpose, and approval path? | Validate before approval |

## Analyst review steps

| Step | Review action | Why it matters |
| --- | --- | --- |
| 1 | Confirm the identity profile has current department, title, manager, and lifecycle context | Reviewers need accurate identity context before making access decisions |
| 2 | Compare previous department access against the new department | Movers can retain access that no longer matches their role |
| 3 | Check whether access is assigned directly, through an access profile, or through a role | The removal path may depend on how the access was granted |
| 4 | Review request and approval context where available | Helps explain why access was assigned |
| 5 | Document whether access should be kept, removed, or investigated | Creates an audit-friendly analyst trail |
| 6 | Record only sanitized findings in the public version | Protects tenant, user, and training details |

## Finding

The fictional mover retained access associated with the previous Operations role after moving to Finance.

This does not automatically mean the access is inappropriate. It means the access should be reviewed against the new job function, department, manager context, and business need.

## Risk

Mover events can create stale access when prior access is not reviewed after a department or job change.

The risk is higher when access is sensitive, broadly scoped, poorly described, or not clearly tied to an access owner.

## Suggested action

Review previous department access during mover events and compare assigned access against the identity's updated department, job title, manager, lifecycle state, and expected role access.

Where access is still needed, document the business reason and approval context. Where access is no longer needed, remove or route it for revocation according to the organization’s governance process.

## Public-safe takeaway

This case study demonstrates IAM analyst review thinking:

- Identify a lifecycle change
- Compare old access against new business context
- Validate whether access still matches least privilege
- Document the finding safely
- Avoid exposing real tenant details
