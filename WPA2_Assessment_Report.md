📡 Wireless Security Assessment Report

Author: ALCHEMISTDEV-007
Date: 13-02-2026
Environment: Authorized Home Lab
Assessment Type: WPA2-PSK Security Evaluation

1. Executive Summary

This report documents a controlled wireless security assessment conducted on a personally owned home network configured with WPA/WPA2-PSK encryption.

The objective was to evaluate password resilience against offline dictionary-based attacks and analyze the security implications of weak credentials.

The assessment demonstrated that passwords present in publicly available wordlists are vulnerable once a valid WPA handshake is captured. The findings reinforce the importance of password entropy and proper wireless configuration practices.

This test was conducted with full authorization on infrastructure owned by the author.

2. Objective

To assess the strength of a WPA/WPA2-PSK wireless network against dictionary-based password attacks and understand potential real-world risks associated with weak WiFi passwords.

3. Scope

Target: Personal home WiFi network

Encryption Mode: WPA/WPA2 (Mixed Mode)

Authorization: Full ownership and permission

Attack Type: Offline dictionary attack

Focus: Password strength evaluation

No unauthorized networks were accessed during this assessment.

4. Environment & Technical Setup
Operating System

Ubuntu Linux (Kernel 6.14.x)

Hardware

HP Pavilion Gaming Laptop (GTX 1650 system)

TP-Link external WiFi adapter (monitor-mode capable)

Tools Used

aircrack-ng – Wireless security auditing framework

rockyou.txt – Public password wordlist

Linux networking utilities for interface configuration

5. Methodology (High-Level Overview)

Wireless interface configured in monitor mode.

WPA 4-way handshake captured during legitimate authentication.

Handshake integrity verified.

Offline dictionary attack performed using a public wordlist.

Password strength evaluated based on time-to-recovery.

This assessment avoided active disruption or unauthorized intrusion.

6. Technical Background

WPA2-PSK security relies on:

4-Way Handshake protocol

PBKDF2 key derivation function

HMAC-SHA1 hashing

Pairwise Master Key (PMK) derivation

Once a handshake is captured, password validation can be performed offline. The security strength then depends entirely on password entropy.

If a password exists in a common wordlist, it becomes vulnerable to dictionary attacks.

Mixed WPA/WPA2 mode may increase exposure to legacy attack surfaces compared to WPA2-AES or WPA3-only configurations.

7. Results

The password was successfully recovered using a dictionary-based approach.

Time to recovery: ~9 minutes

Attack type: Offline dictionary attack

Wordlist used: rockyou.txt

Root Cause Analysis

The password was vulnerable due to:

Predictable structure

Insufficient entropy

Inclusion within a commonly leaked password dataset

8. Why Weak Passwords Fail

Passwords fail under dictionary attacks because:

Public wordlists contain millions of leaked credentials.

Humans tend to create predictable patterns.

WPA2 cracking becomes offline once handshake is captured.

GPU acceleration significantly reduces cracking time.

Short or pattern-based passwords reduce computational search space.

Entropy is reduced when passwords:

Contain dictionary words

Follow “word + numbers” format

Are shorter than 12–16 characters

Lack randomness

9. Risk Analysis – Impact of Exposed WiFi Password

If a WiFi password is compromised, attackers may:

Gain unauthorized network access

Intercept unencrypted traffic

Launch man-in-the-middle attacks

Perform reconnaissance on internal devices

Access shared systems or misconfigured services

Use victim’s IP address for malicious activity

Attempt lateral movement within the network

Wireless compromise can escalate into broader internal network exposure.

10. Security Observations

Network configured in WPA/WPA2 mixed mode

WPS was enabled at the time of testing

Both configurations can increase attack surface and should be reviewed.

11. Security Recommendations
Password Hardening

Use 16+ character randomly generated passwords

Avoid dictionary words or predictable patterns

Include upper/lowercase letters, numbers, and symbols

Configuration Improvements

Switch to WPA2-AES only or WPA3 if supported

Disable WPS

Keep router firmware updated

Change default router admin credentials

Network Hygiene

Monitor connected devices regularly

Use a separate guest network

Consider network segmentation for IoT devices

12. Future Work

Further research and experimentation areas:

Deep dive into WPA2 cryptographic internals (PBKDF2 implementation)

Comparative analysis of WPA3-SAE security model

Performance benchmarking of CPU vs GPU-based password cracking

Study of PMKID-based attack vectors

Review of aircrack-ng source code to understand packet processing and optimization techniques

13. Ethical Statement

This assessment was conducted on a personally owned network with full authorization. The objective was educational — to understand wireless security architecture and strengthen defensive awareness.

No unauthorized systems were targeted.

14. Reflection

This exercise reinforced:

The importance of password entropy

The risks of publicly available wordlists

The engineering complexity behind wireless auditing tools

The responsibility that comes with security knowledge

This assessment strengthened both offensive understanding and defensive awareness.
