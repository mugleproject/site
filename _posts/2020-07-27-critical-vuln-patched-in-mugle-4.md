---
layout: post
title:  "Critical PoW vulnerability successfully patched in v4.0.0"
author: "@lehnberg"
categories: blog
---

Prior to the third hard fork, a critical vulnerability was detected in the proof of work verification code of Cuckaroom by @tromp. Had it been exploited, this bug would have led to solution speedups of 1000x and more.

Working with the security team, a fix was introduced without detection in Mugle v4.0.0-rc.1, and the entire network successfully upgraded to running fixed software as part of Hard Fork 3 (HF3) on July 16.

**It has been verified that this vulnerability was never exploited. No action is required by Mugle users or services.**

Details of this vulnerability and the events surrounding it can be found in [this disclosure document](https://github.com/mugleproject/mugle-security/blob/master/CVEs/CVE-2020-15899.md) that was published today in the mugle-security repo. John's personal account of the events has also been published in [this forum post](https://forum.mugle.org/t/critical-pow-vulnerability-closed-the-accidental-birth-of-a-new-pow/7590).