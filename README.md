# SAPS — Secondary Authentication Password System
Patent Pending — CA 3301766

## Overview
SAPS is a post-password authentication protocol designed to eliminate MFA fatigue, credential replay, and push bombing attacks.

## Problem SAPS Solves
- MFA fatigue
- Credential replay
- Push bombing
- Passwordless gaps
- Identity verification failures

## High-Level Flow
1. User enters primary credential.
2. SAPS generates a secondary authentication password.
3. Secondary password is validated through a separate channel.
4. Session is established only after dual validation.

## Why SAPS Is Different
- Not passwordless — post-password.
- Eliminates MFA fatigue.
- Stops replay attacks.
- Works with existing IAM systems.
- Zero reliance on push notifications.

## Threat Model
SAPS blocks:
- Replay attacks
- MFA bombing
- Credential stuffing
- Session hijacking
- Push fatigue exploitation

## Patent Status
Patent Pending — CA 3301766
