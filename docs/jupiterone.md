# JupiterOne Managed Integration for BugCrowd

## Overview

JupiterOne provides a managed integration for BugCrowd. The integration connects
directly to [BugCrowd REST API][1] to obtain application scan assets, reports,
and findings.

Configure the integration by providing an API Token from your BugCrowd account.

## Entities

The following entity resources are ingested when the integration runs.

| BugCrowd Resources | \_type of the Entity  | \_class of the Entity |
| ------------------ | --------------------- | --------------------- |
| Account            | `bugcrowd_account`    | `Account`             |
| Bounty Program     | `bugcrowd_bounty`     | `Program`             |
| Submission         | `bugcrowd_submission` | `Finding`             |

## Relationships

The following relationships are created:

| From               | Relationship | To                    |
| ------------------ | ------------ | --------------------- |
| `bugcrowd_account` | **HAS**      | `bugcrowd_bounty`     |
| `bugcrowd_bounty`  | **HAS**      | `bugcrowd_submission` |

The following relationships are mapped:

| From                  | Relationship | To                 |
| --------------------- | ------------ | ------------------ |
| `<ROOT>`              | **Owns**     | `bugcrowd_account` |
| `bugcrowd` (`Vendor`) | **Hosts**    | `bugcrowd_account` |

[1]: https://docs.bugcrowd.com/reference
