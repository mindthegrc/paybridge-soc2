# PayBridge TLS Configuration

## SOC 2 Control: CC6.7

## Overview
All data transmitted to and from
PayBridge systems is encrypted using
TLS 1.2 or higher.

## Certificate Management
Provider: AWS Certificate Manager (ACM)
Certificate type: Public SSL/TLS
Domain: paybridge.example.com
Wildcard: *.paybridge.example.com
Renewal: Automatic via ACM

## TLS Policy
Minimum version: TLS 1.2
Recommended: TLS 1.3
Deprecated: TLS 1.0 and 1.1 disabled
Cipher suites: AWS recommended policy

## HTTPS Enforcement
All HTTP requests → Redirected to HTTPS
HSTS header: Enabled
   max-age: 31536000
   includeSubDomains: true

## Load Balancer Configuration
→ Listener port 443: HTTPS with ACM certificate
→ Listener port 80: Redirect to 443
→ Security policy: ELBSecurityPolicy-TLS13-1-2-2021-06

## Certificate Monitoring
→ ACM sends alerts 45 days before expiry
→ Auto-renewal enabled for ACM certificates
→ Certificate inventory reviewed quarterly

## Evidence of Compliance
→ ACM certificate screenshot showing valid
→ Load balancer HTTPS listener configuration
→ SSL Labs scan result (A or A+ rating)
