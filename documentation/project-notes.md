# Project Notes

## Project

AWS S3 Secure Document Storage & Auditing

## S3 Configuration

The project S3 bucket was configured with multiple security and data-protection controls.

### Versioning

S3 Versioning was enabled to protect documents from accidental deletion or modification.

A recovery test was performed by deleting a document, displaying the object versions, removing the delete marker, and confirming that the previous version was restored.

### Encryption

Default S3 server-side encryption was configured using SSE-S3.

This provides encryption for objects stored in the S3 bucket.

### Block Public Access

S3 Block Public Access was enabled to help prevent unintended public access to objects in the bucket.

### Lifecycle Management

A lifecycle rule named `archive-old-resume-versions` was configured.

The rule:

- Permanently deletes noncurrent object versions after 90 days.
- Deletes expired object delete markers after 7 days.
- Aborts incomplete multipart uploads after 7 days.
- Does not automatically expire current object versions.

## CloudTrail Auditing

AWS CloudTrail was configured to monitor activity related to the project.

The CloudTrail trail:

- Uses a dedicated S3 bucket for audit logs.
- Records management events.
- Records S3 object-level data events for the project bucket.
- Uses multi-region logging.
- Has log file validation enabled.

## CloudTrail Validation

CloudTrail logs were inspected in the CloudTrail S3 log bucket.

An S3 `HeadObject` event was identified for an object stored in the project bucket:

`documents/Kaly Lamour Data Analyst Resume 2026.docx`

The event was classified as an S3 data event rather than a management event, confirming that object-level data-event logging was functioning.

## Security Considerations

The actual documents stored in the project bucket are not included in this public GitHub repository.

Raw CloudTrail log files are also not included because they may contain account, identity, network, or other environment-specific information.

Only selected configuration screenshots and documentation are included in the portfolio.

## Skills Demonstrated

- Amazon S3
- AWS CloudTrail
- S3 Versioning
- Server-side encryption
- Block Public Access
- Lifecycle management
- Object recovery
- Cloud auditing
- AWS security fundamentals
