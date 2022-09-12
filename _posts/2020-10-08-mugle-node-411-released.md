---
layout: post
title:  "Mugle node v4.1.1 released"
author: "@quentinlesceller"
categories: blog
---

Mugle node v4.1.1 has been released. Binaries are as usual available from the [download section]({{'download' | relative_url}}).

This patch fixes a small issue involving older nodes (v4.0.0) syncing against more recent v4.1.0 nodes. This bug is related to the conversion logic between v2 and v3 blocks to support `CommitOnly` transaction inputs. For more details, see [the announcement on the Mugle forum](https://forum.mugle.org/t/mugle-node-v4-1-0-released/7840/3).

The version 4.x family of releases include many improvements and fixes, and is required in order to interact with the network after the scheduled hard fork. All users are encouraged to upgrade.

For more details, see the [post announcing version 4.0.0]({% post_url 2020-07-02-mugle-4-released %}).
