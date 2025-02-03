# Atari MSX

I'm beginning a project for Atari 8-bit computers that is based on my TRS80MSX project.  The TRS80MSX is a device that 
emulated several other devices and plugs into the expansion port on the TRS-80 Model 1.

## Why?

Although there are alternative devices already out there, one of the most popular ones, Fujinet, is built on the SIO 
port, which is slow.  Other alternatives include Ultimate 1MB, but that requires modifying hardware.  Other solutions 
have various pros and cons (AVGCart, UnoCart, SIDE2, MyIDE II).  I want to try this out to see if what I learned with 
TRS80MSX is transferable, and I want to do everything in open source (hardware and software).  I'll also be learning
Kicad, as I had used Eaglecad for all my previous projects, and now Eaglecad is too expensive.

## What?

I'll likely start with cartridge emulation via Teensy, a latch on the data port, address decover on the address bus. 
On the MSX I used a flip-flop triggered by the address decoder against the WAIT pin in order to synchronize 
communication between the Teensy and the 8-bit bus.  The equivalent (RDY) pin on the 6502 isn't exposed on the cartridge 
port.  It *is* exposed on the expansion port, but I'd really rather use the cartridge port, because the expansion port 
isn't available on Atari 8-bits.  This probably means I'll have to stay within a narrow bus bandwidth window, which may 
or may not be possible with a processor-based approach like Teensy (so an FPGA may come into play, we'll see).  So, 
although this effort is inspired by TRS80MSX, we'll be learning some new stuff for sure.

## When?

No big pressure on this one.  It's a hobby after all.  We'll see how it goes.  That said, I'd like to set a 
target time to keep myself motivated, so let's say that by July 2025 I'll have it emulating cartridges at least.  We'll
branch from there to see what's possible.  Maybe over time something could be built that just emulates everything (meaning 
it brings together SIO, expansion port if you have one, and cartridge port).  That would be kind of cool, huh?

Let's go!
