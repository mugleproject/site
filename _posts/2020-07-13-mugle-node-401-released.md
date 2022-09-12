---
layout: post
title:  "Mugle node patched to v4.0.1"
author: "@lehnberg"
categories: blog
---

Mugle node v4.0.1 has been released and is ready for use in advance of this week's scheduled hard fork, occurring at block height #786,240. Binaries are as usual available from the [download section]({{'download' | relative_url}}).

This release includes a patch for a bug that was causing a thread panic. Details in the issue [mimblewimble/mugle/#3386](https://github.com/mugleproject/mugle/issues/3386) and the accompanying pull request [mimblewimble/mugle/#3387](https://github.com/mugleproject/mugle/pull/3387).

The version 4.x family of releases include many improvements and fixes, and is required in order to interact with the network after the scheduled hard fork, currently estimated to occur on Jul 16 around 11 PM UTC. All users are encouraged to upgrade.

For more details, see the [previous post announcing version 4.0.0]({% post_url 2020-07-02-mugle-4-released %}).
