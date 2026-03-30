## Objective

Detect repeated SSH authentication failures from the same source IP to potentially identify brute force attempt. 

## Context

A brute force attempt is when an adversary repeatedly tries to guess valid credentials by trying different user or passwords.

## Detection Strategy

1. Identify individual failed authentication attempts
2. Correlate multiple failed attempts from the same IP
3. Detect successful login attempt after multiple failures

## Rule Design

Rule 1 - Base Detection:

Base event to detect individual failed SSH login attempts using default Wazuh SID. It serves as a base rule for subsequent brute force detection logic. Each authentication failure is logged to enable correlation rules to track over time.

 <rule id="100100" level="3">
   <if_sid>5710</if_sid>
   <description>Invalid SSH user authentication attempts</description>
 </rule>

Rule 2 - Multiple SSH Failure Dection:



  <rule id="100101" level="7" frequency="6" timeframe="120" ignore="300">
   <if_matched_sid>100100</if_matched_sid>
   <same_srcip />
   <description>Multiple SSH authentication failures (possible brute force attack)</description>
   <mitre>
     <id>T1110</id>
   </mitre>
 </rule>
