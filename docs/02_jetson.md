# Using Jetson GUI Headlessly

A seperate Monitor for Jetson Nano and variants Is a Lie

**Zero Monitors. Zero Cables. Full Jetson GUI.**

You would still need a laptop though.

Alright, here’s the thing, linux systems are super customizable. You typically have access to every little thing unlike Apple or Windows. 

With that said, edge devices like Jetson, have mostly linux (ubuntu versions) running. 

They do not activate display drivers, which are mostly Xorg (nvidia), untill you physically connect a monitor via HDMI port.

I have a small robot lab setup at home and I don’t want to put a monitor, keyboard, blah blah blah… just for a jetson, takes too much space on desk. 

So I considered “nomachine” server to connect via the network to my jetson. 

“NoMachine” is pretty straightforward, you don’t need big brains to use it. “Browser” → “Download” → “Install” → “Use it”. So I did that on jetson ONCE, using some random monitor I found in some place. Then, I installed “NoMachine” on my Mac and I could totally see Jetson on my network devices list.

However, it just shows black screen after login.

That’s when I found out that, the problem is, the physical HDMI cable triggers the display driver. 

Tried stuff like “getting a dummy hdmi, which is like a dongle, that tricks like if monitor is connected” — and it never got delivered.

But come on, its linux,

Apparently there exists a software package for simulating a monitor, and you edit some files, and write some lines, to trick the jetson, that a display is connected (so, you can see through NoMachine)

Here’s the Setup that you can try

1. Install this

```bash

```

1. Edit the xorg.conf

```bash

```

1. Reboot

Try with NoMachine and you would see the display this time