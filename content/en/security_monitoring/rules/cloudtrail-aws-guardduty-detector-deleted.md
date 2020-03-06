---
title: AWS GuardDuty Detector Deleted
kind: documentation
parent: cloudtrail
tags:
- security:attack
- tactic:TA0005-defense-evasion
- technique:T1089-disabling-security-tools
- service:guardduty.amazonaws.com
- source:cloudtrail
meta_image: /images/integrations_logos/amazon_cloudtrail.png
---
## **Goal:**
Detect when an attacker is trying to evade defenses by deleting a GuardDuty detector.

## **Strategy:**
Monitor CloudTrail and detect when a GuardDuty Dector is deleted via the following API call:
* [DeleteDetector][1]

## **Triage & Response:**
1. Determine who the user was who made this API call.
2. Contact the user and see if this was an API call which was made by the user.
3. If the API call was not made by the user:
   * Rotate the user credentials and investigate what other API calls.
   * Determine what other API calls the user made which were not made by the user.
[1]: https://docs.aws.amazon.com/guardduty/latest/ug/delete-detector.html