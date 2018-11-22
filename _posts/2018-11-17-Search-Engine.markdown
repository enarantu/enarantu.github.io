---
layout: post
categories: project
thumbnail: "/public/images/insta485.png"
pid: "post-03"
description: "How google used to work around 2006"
techs: "Flask, React.js, SQLite, Hadoop, Socket, Multithreading"
resp: Everything except design(design was done by course staff).
---
It is a search engine implemented almost from scratch.
We first implemented a single machine, multi-process, multi-threaded, fault tolerant server with master and workers that execute user-submitted MapReduce jobs.
<hr/>
Built index server that uses hadoop mapreduce to process Wikipedia page dumps to calculate page scores then built web server and interface.
<hr/>
<img src="/public/images/search-engine.jpg" width="100%"/>