# PayBridge Encryption Inventory

**Last Updated:** [Today's date]
**Owner:** Security Team
**SOC 2 Controls:** CC6.7, CC9.1, C1.1

---

## Data at Rest Encryption

| System | Encryption | Key | Rotation | Status |
|--------|-----------|-----|---------|--------|
| RDS PostgreSQL | AES-256 | paybridge-rds-key | 365 days | ✅ Enabled |
| S3 App Bucket | AES-256 | paybridge-s3-key | 365 days | ✅ Enabled |
| S3 Logs Bucket | AES-256 | paybridge-s3-key | 365 days | ✅ Enabled |
| EBS Volumes | AES-256 | paybridge-rds-key | 365 days | ✅ Enabled |
| Secrets Manager | AES-256 | paybridge-secrets-key | 365 days | ✅ Enabled |
| RDS Backups | AES-256 | paybridge-rds-key | 365 days | ✅ Enabled |

---

## Data in Transit Encryption

| Connection | Protocol | Certificate | Status |
|-----------|---------|------------|--------|
| User → Load Balancer | TLS 1.3 | ACM Certificate | ✅ Enabled |
| Load Balancer → App | TLS 1.2+ | Internal cert | ✅ Enabled |
| App → RDS | TLS 1.2+ | RDS SSL cert | ✅ Enabled |
| App → S3 | TLS 1.2+ | AWS managed | ✅ Enabled |
| App → External APIs | TLS 1.2+ | Vendor managed | ✅ Verified |

---

## KMS Key Inventory

| Key Alias | Purpose | Created | Rotation | Administrator |
|-----------|---------|---------|---------|--------------|
| paybridge-rds-key | Database encryption | [date] | Annual | Security Team |
| paybridge-s3-key | Storage encryption | [date] | Annual | Security Team |
| paybridge-secrets-key | Secrets encryption | [date] | Annual | Security Team |

---

## Secrets Inventory

| Secret Name | Type | Rotation | Last Rotated |
|------------|------|---------|-------------|
| paybridge/production/db-credentials | Database | 30 days | [date] |
| paybridge/production/api-keys | API Keys | 90 days | [date] |
| paybridge/production/service-tokens | Service tokens | 90 days | [date] |

---

## Annual Review Checklist

- [ ] All KMS keys showing enabled status
- [ ] Key rotation active on all keys
- [ ] No expired TLS certificates
- [ ] All S3 buckets showing encryption enabled
- [ ] RDS encryption verified
- [ ] EBS default encryption enabled
- [ ] Secrets Manager rotation active
- [ ] No unencrypted sensitive data found

**Reviewed by:** _______________
**Date:** _______________
