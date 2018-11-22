---
layout: post
categories: project
thumbnail: "/public/images/snake.png"
pid: "post-00"
techs: Socket.io, Node.js, React.js, Jest, Bootstrap
description: "Real-time online multiplayer snake"
---
<p>
    Try game at: <a href="https://www.multiplayersnakeproject.site" target="blank">https://www.multiplayersnakeproject.site</a> <br/>
    Browse code at: <a href="https://github.com/enarantu/multiplayer-snake" target="black">https://github.com/enarantu/multiplayer-snake</a>
</p>
<p>
    Technical challenge: When one snake makes a turn letting other players to know as fast as possible is the key challenge.
</p>
<p>
    State: Locations of snakes, foods, etc.<br/>
    Timestep: All clients must have same timestep.<br/>
</p>
<p>
    Solution 1: Client sends request at direction change. Next state for client is computed by server at timesteps. Client sends request at timesteps requesting state. Ultimate power on the server prevents cheating.<br/>
    Problem: On direction change, UI updates after server replies with state. Due to reply latency, game feels choppy.
</p>
<p>
    Solution 2: At timesteps, client computes next state and sends to server. Server sends next state for other clients at timesteps. This approach allows clients to see themselves without delay and see others some time in the past<br/>
    This is my choice of approach. <br/>
    Problem: Since ultimate state control is on players, they can cheat.
</p>
<p>
    Solution 3: At timesteps, client and server both computes the next state, but client renders UI with thier version of state without delay. When server version of state and client version of state conflicts, server has the ultimate control. This solution is both realtime and cheat proof.<br/>
    Problem: This solution is less efficient than previous solution, and added complication will make development time much longer.
</p>

