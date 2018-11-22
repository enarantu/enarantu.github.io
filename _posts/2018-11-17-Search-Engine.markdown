---
layout: post
categories: project
thumbnail: "/public/images/insta485.png"
pid: "post-03"
description: "How google used to work around 2006"
techs: "Flask, React.js, SQLite, Hadoop, Socket, Multithreading"
resp: Everything except design(design was done by course staff).
---
Reasons why this project is awesome:<br/>
1) It is a search engine implemented almost from scratch.
We first implemented a single machine, multi-process, multi-threaded, fault tolerant server with master and workers that execute user-submitted MapReduce jobs. We then indexed wikipedia page dumps with hadoop, and created<br/>
2) Painless to set it up. Making heavy use of bash scripts and python virtual enviroment allowed setting uniform environtment among developers quite simple.<br/>
3) Readable code. Usage of pydocstyle, pycodestyle, and eslinter forced beautiful code.
<img src="/public/images/search-engine.jpg" width="100%"/>