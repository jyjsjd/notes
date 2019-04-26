---
title: Refresh vs. flush
created: '2019-03-01T09:00:58.232Z'
modified: '2019-04-26T06:34:21.152Z'
tags: [es, Middleware]
---

# Refresh vs. flush
- An elasticsearch `refresh` makes your documents available for search, but it doesn't make sure that they are written to disk to a persistent storage, as it doesn't call `fsync`, thus doesn't guarantee durability. 
- An elasticsearch `flush` effectively triggers a lucene `commit`, and empties also the transaction log, since once data is committed on the lucene level, durability can be guaranteed by lucene itself.
