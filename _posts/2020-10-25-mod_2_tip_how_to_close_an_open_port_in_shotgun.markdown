---
layout: post
title:      "Mod 2 Tip: How to Close An Open Port in Shotgun"
date:       2020-10-25 17:18:29 -0400
permalink:  mod_2_tip_how_to_close_an_open_port_in_shotgun
---


"Shotgun is a small Ruby gem that makes it easier to develop and test Rack-based Ruby web applications locally by starting Rack with automatic code reloading"(Learn.Co, 2020). Understanding how to use the shotgun development server is an imperative part of completing the mod 2 Sinatra project. One night when I was coding through my Sinatra lessons in mod 2, I tried to run shotgun and ran into an error message that took me about 45 minutes to solve.  The terminal error stated that I had a runtime error due to a port in use. In layman's terms this meant that I was unable to run the shotgun developement server in my new terminal because I had a port (server connection) in use somewhere else that I was not aware of.

**My error:**

```
/Users/christinemyerskeitt/.rvm/gems/ruby-2.6.1/gems/eventmachine-1.2.7/lib/eventmachine.rb:531:in `start_tcp_server': no acceptor (port is in use or requires root privileges) (RuntimeError)
```

**What can cause this to happen?**

This error is caused when I closed the terminal session in my previous lab with the shotgun server still running on localhost:9393.  Although I closed the terminal  window, the server was still active and serving pages from my previous lab on localhost:9393. Therefore when I ran shotgun in the new lab, I received an error message to prevent me from trying to start a new server on the same port.

**How do you fix this problem?**

The basic process is:

* Use the lsof command to list open files (In this case in reference to tcp port 9393/ localhost: 9393) 

**lsof -i TCP: 9393**

* Review the running shotgun servers to find the PID of the open port 

```
COMMAND  PID                USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
ruby   7836 christinemyerskeitt   20u  IPv4 0x9f8610427f099193      0t0  TCP localhost:9393 (LISTEN)
```


* Send a signal to kill that open file using the PID 

**kill 7836**

* Rerun Shotgun 

Run shotgun and it should work this time.

**Happy coding and good luck on your Sinatra project!**










