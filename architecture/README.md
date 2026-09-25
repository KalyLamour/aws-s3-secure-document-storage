# Architecture

This project uses Amazon S3 for secure document storage and AWS CloudTrail for auditing.

```text
                    AWS Cloud
                       │
                       ▼
              ┌─────────────────┐
              │   Amazon S3     │
              │ Secure Storage  │
              └────────┬────────┘
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
   Versioning      SSE-S3       Block Public
                                  Access
                       │
                       ▼
               Lifecycle Rules
                       │
                       ▼
                AWS CloudTrail
                       │
                       ▼
              Audit Log S3 Bucket
