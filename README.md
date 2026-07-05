SAPS — Secondary Authentication Password System
Patent Pending — CA 3301766  
Website: https://sapstech.ca

Purpose
SAPS is a dual‑channel post‑password authentication protocol engineered to eliminate MFA fatigue, credential replay, and push‑bombing attacks. It hardens identity systems without relying on biometrics, hardware tokens, or push notifications.

Protocol Overview
SAPS introduces a second, isolated authentication password generated after primary credential validation. This secondary password is single‑use, channel‑isolated, and validated independently before any session is established.

Authentication Stages
C1 — Primary Credential Stage  
User submits their primary credential (password, passphrase, or existing IAM login).

C2 — Secondary Authentication Password Stage  
SAPS generates a unique, single‑use secondary password delivered through a separate channel.

Dual‑Channel Validation  
Both C1 and C2 must be validated independently before session creation.

Session Establishment  
Only after dual validation does SAPS authorize the session.

Why SAPS Exists
Modern MFA is collapsing under:

Push bombing

MFA fatigue

Credential replay

Session hijacking

Passwordless gaps

IAM systems relying on reactive user approvals

SAPS replaces reactive MFA with deterministic dual‑channel authentication.

What SAPS Solves
Replay attacks — secondary password is single‑use and channel‑isolated

MFA fatigue — no push approvals, no reactive user prompts

Push bombing — SAPS does not use push notifications

Credential stuffing — attackers cannot complete C2

Session hijacking — dual validation blocks token theft

Passwordless gaps — SAPS strengthens password‑based systems without replacing them

Security Guarantees
SAPS provides:

Replay resistance

Push‑bombing immunity

Fatigue‑proof authentication

Dual‑channel isolation

Single‑use secondary credentialing

Session‑establishment hardening

Compatibility with existing IAM stacks

Compatibility
SAPS integrates with:

OAuth2

OIDC

SAML

Custom identity providers

Existing password‑based systems

No hardware tokens. No biometrics. No push infrastructure.

Threat Model
SAPS blocks:

Replay attacks

MFA bombing

Credential stuffing

Session hijacking

Push fatigue exploitation

Unauthorized session escalation

Protocol Sequence Diagram
ASCII Version
text
User                SAPS Server              Secondary Channel
 |                       |                           |
 |--- Primary Login ---->|                           |
 |                       |                           |
 |        Validate Primary Credential                |
 |                       |                           |
 |<-- Request SAPS Code -|                           |
 |                       |--- Generate SAPS Code ----|
 |                       |                           |
 |--- Enter SAPS Code ---|                           |
 |                       |                           |
 |        Validate SAPS Code (Dual Channel)          |
 |                       |                           |
 |<------ Authentication Success --------------------|
 
 sequenceDiagram
    participant User
    participant SAPS
    participant SecondaryChannel

    User->>SAPS: Primary Credential
    SAPS->>SAPS: Validate Primary
    SAPS->>SecondaryChannel: Generate SAPS Code
    SAPS->>User: Request SAPS Code
    User->>SAPS: Enter SAPS Code
    SAPS->>SAPS: Validate Dual Channel
    SAPS->>User: Authentication Success
    
Roadmap
v1 — Protocol definition

v2 — Reference implementation

v3 — SDKs (Node, Python, Go)

v4 — IAM integrations (Auth0, Okta, Azure AD)

v5 — Enterprise deployment patterns


License
Copyright (c) 2026 SAPS Technologies.
All rights reserved.
Unauthorized use, reproduction, or distribution of this protocol or its implementations
is strictly prohibited.
Use of this protocol or any derivative works requires explicit written permission from SAPS Technologies.
Patent Pending — CA 3301766.



