# AWS S3 Secure Document Storage & Auditing

A hands-on AWS project demonstrating secure document storage, data protection, lifecycle management, version recovery, and CloudTrail auditing using Amazon S3.

## Project Overview

This project was built to practice implementing security and operational controls for an Amazon S3-based document storage environment.

The project includes:

- S3 Versioning
- Server-side encryption (SSE-S3)
- Block Public Access
- S3 Lifecycle Management
- CloudTrail management event logging
- CloudTrail S3 object-level data event logging
- Version recovery testing

## AWS Services Used

- Amazon S3
- AWS CloudTrail

## Architecture

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
