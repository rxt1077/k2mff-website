+++
author = "Ryan Tolboom N2BP"
title = "Bring Your Own Device Packet Station"
date = "2025-02-05"
description = "A new packet workstation has been set up in the shack."
tags = [
    "packet",
    "VHF",
    "UHF",
    "2M",
    "70cm",
    "BYOD",
]
+++

<img alt="BYOD packet station" src="/byod-packet/station.jpg" width=75% class="center">

## What is it?

Packet radio is a digital mode common on VHF/UHF (although there's HF packet as well).
It typically uses a 2M/70cm transceiver (the black box mounted under the shelf in the above photo) and a terminal node controller (TNC, the white box on the shelf in the above picture) to send audio signals that represent data.
The most common mode for packet is 1200 baud audio frequency shift keying (1200 AFSK) although other modes exist that can go much faster.

This particular setup is an [IC-208H](/byod-packet/IC-208H.pdf) hooked up to a [NinoTNC A3](https://tarpn.net/t/nino-tnc/n9600a/n9600a_operation.html).

## What can we do with it?

Using these tools you can have a keyboard-to-keyboard QSO (contact, conversation) with another operator, connect to a bulletin board system (BBS), or route traffic through other nodes to reach out even further.
I was able to connect to two different BBSs in about an hour of operating:

| Callsign | Frequency | Mode      | Notes                                       |
| -------- | --------- | --------- | ------------------------------------------- |
| KD2YCK-1 | 145.070   | 1200 AFSK | Great connection. Node is in Montclair, NJ. |
| N2MH-7   | 145.510   | 1200 AFSK | Connected, but would drop intermittently.   |

## Who can use it?

One of the great things about VHF/UHF packet is that anyone with a technician or above license can use it!
This means that all licensed K2MFF club members can use the BYOD packet station.
A general or extra licensed member _does not_ need to be present.

## How do I use it?

Turn on the transceiver (power button is labelled in yellow on the right of the rig) and rotate the knob to get to the frequency you want to work.
If you start hearing buzzing like the emergency alert system (which is also AFSK 1200) then you know there's packets on the channel.
Plug the black USB cable from the back of the TNC into your computer.

Now you'll need a terminal program to talk to the TNC.
[QtTermTCP](https://www.cantab.net/users/john.wiseman/Documents/QtTermTCP.html) is what I recommend.
Download from the above link and extract it.
Run `QtTermTCP.exe` and navigate to `Setup->KISS Setup`:

<img alt="QtTermTCP KISS Selection" src="/byod-packet/qttermtcp-kiss.png" width=75% class="center">

Inside the KISS Configuration window set click `Enable KISS Interface`, set your call sign, select the serial device for the TNC (it will probably be COM3, but you may need to check Device Manager), set the speed to `57600`, clear the TCP Setup options, and click `OK`:

<img alt="QtTermTCP KISS Configuration" src="/byod-packet/qttermtcp-kiss-config.png" width="60%" class="center">

QtTermTCP shows you the raw packets received at the top, the text from those packets in the middle panel, and gives you a text box to type in commands at the bottom.
You can connect to a BBS (see the ones I managed to reach out to above) by clicking `Connect` in the upper left-hand corner and putting in the BBS call sign.
Make sure you're on the right frequency for what you're trying to connect to!
Once connected to the BBS, type `?` in the bottom text box to see what it can do!

## Why BYOD?

Installing software (especially ham radio software!) can be a taxing exercise for a newcomer.
BYOD allows someone to set it up how they would like to use it and not have to worry about where the software is, what version they're running, or messing something up for the next person.
If an advanced user wants to use different software on their device, they're welcome to.
Likewise, once a beginner gets things working on their laptop they can be sure that the next time they come in things will be where they put them!

## Why a Physical TNC?

<img alt="NinoTNC" src="https://tarpn.net/t/nino-tnc/n9600a/n9600a4/a4rc10-fully-assembled-top-down-img-1998x800.jpg" width="60%" class="center">

A physical TNC makes a BYOD setup easy.
When a new club member comes in, all they have to do is plug a USB cable into their laptop.
We don't have to worry about teaching them how to configure [Direwolf](https://github.com/wb2osz/direwolf/), [UZ7HO](http://uz7.ho.ua/packetradio.htm), or [AGWPE](https://www.sv2agw.com/downloads/).

## Packet is dead, get over it.

Is this one a question?
All the other headings were questions.
If we're being pedantic, any student of networking will tell you that packet networks soundly beat circuit switched networks over half a century ago. 😄

Packet radio, especially "old-school" AFSK 1200, provides an excellent opportunity for new hams to practice radio skills and gain a tacit understanding of how networks operate.
When you watch a packet station operate you can see how the protocols have developed.
You can observe your TNC doing [CSMA](https://en.wikipedia.org/wiki/Carrier-sense_multiple_access) by queuing packets while the DCD is active.
You can see how larger messages are broken into smaller chunks.
You can witness acknowledgements and sequencing in action.
Finally, and perhaps most importantly, you can watch networks fail and try to figure out how to improve them.

Students I encounter are interested in data modes but don't have a general or extra license (yet!).
Many of them are very comfortable with software but are just getting starting with radios and antennas.
Packet lets them get a computer hooked to a radio, sending and receiving data in an obvious way, right away.

## What can we do with it in the future?

The NinoTNC supports some much more interesting packet modes and our interface cable is already attached to a 9600 baud port.
If we can find someone to connect to, or perhaps build a mobile packet station for on-campus testing, we could try some faster modes.

We could also set up our own packet BBS with [BPQ32](https://www.cantab.net/users/john.wiseman/Documents/BPQ32.html) if there's interest.

The sky is the limit! Let me know what you think.
