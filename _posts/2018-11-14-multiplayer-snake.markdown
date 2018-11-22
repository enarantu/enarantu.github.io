---
layout: post
categories: project
thumbnail: "/public/images/snake.png"
pid: "post-00"
techs: Socket.io, Node.js, React.js, Jest, Bootstrap
description: "Real-time online multiplayer snake"
resp: Everything.
---
Try game at: <a href="https://www.multiplayersnakeproject.site" target="blank">https://www.multiplayersnakeproject.site</a> <br/>
Browse code at: <a href="https://github.com/enarantu/multiplayer-snake" target="black">https://github.com/enarantu/multiplayer-snake</a>
<hr/>
Challenge 1: Synchronization.<br/>
State: Locations of snakes, foods, etc.<br/>
Timestep: All clients must have same timestep length. State changes at each timestep.<br/>
<hr/>
Solution 1: Next state for client is only computed by the server. Client sends inputs to server and recieves new state for everybody. Ultimate power on the server prevents cheating.
Problem: On user input, UI updates after server replies with state. Due to reply latency, game feels laggy.
<hr/>
Solution 2: Client computes next state and sends to server. Server sends next state for other clients. This approach allows clients to see themselves without delay and see others some time in the past. This is my choice of approach.
Problem: Since ultimate state control is on players, they can cheat.
<hr/>
Solution 3: Client and server both computes the next state, but client renders UI with thier version of state without delay. When server version of state and client version of state conflicts, server has the ultimate control. This solution is both realtime and cheat proof.
Problem: This solution is less efficient than previous solution, and added complication would've made development time much longer. It isn't worth cheating on my toy project. :)
<hr/>
Challenge 2: Add power up that makes snake twice as fast.
Problem: Different timestep length can cause synchronization issues.
<hr/>
Solution: Make timesteps twice as short but if player doesn't have a power up only transition to next step on even timesteps.
