## Objective

Detect repeated SSH authentication failures from the same source IP to potentially identify brute force attempt. 

## Context

A brute force attempt is when an adversary repeatedly tries to guess valid credentials by trying different user or passwords.

## Detection Strategy

1. Identify individual failed authentication attempts
2. Correlate multiple failed attempts from the same IP
3. Detect successful login attempt after multiple failures

## Rule Design