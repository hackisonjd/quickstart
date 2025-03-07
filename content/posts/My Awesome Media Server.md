---
title: My Awesome Media Server
date: 2025-03-05
draft: true
tags:
  - self-hosting
---

## Rationale

In the last few years, streaming services have become a very convenient way to enjoy media, but have led to very significant problems regarding accessibility and media ownership. There is one prevalent truth, the streaming service you paid for can pull media without your knowledge, or even lock it behind their own services to get you to pay more.

You are essentially renting your entertainment. It's exploitative, and bad for your wallet. 

Not all is lost, though. Many people have a library of physical media that they've collected over the years, and thankfully, media servers have become way easier to host yourself. I made the journey to completely self-host my media last year, and I haven't looked back. I want to give you the tools to do that too.

## But first, a word on piracy

Piracy has become a murky subject, especially as the economy tightens and [corporations make it more difficult to back up your physical media](https://hackaday.com/2014/09/08/unbricking-a-bluray-drive/). It is not the business, nor goal of this article to give you moral guidance on where you should stand on this issue. Rather, this article aims to be an informational piece to let you know that these tools exist and how you can use them. Use your best judgment, and use these tools responsibly.

## Assumptions

This guide assumes that you have a spare computer that you can use to run as a media server. You don't need the most intense system to run something like this, and even something like a ten year old Thinkpad will be more than sufficient. Be creative!

In addition, it is highly, highly, highly recommended to use a VPN in order to use torrenting software. While you technically *can* get away with not using it, I don't recommend it for a [variety of different reasons](https://www.tomsguide.com/features/this-is-why-everybody-else-uses-a-vpn-when-torrenting). I've used [ProtonVPN](https://account.protonvpn.com/signup?plan=vpn2024&billing=24&currency=USD&coupon=VPN24DEAL) for a long time, and it's been fantastic. Their VPN plans typically go on sale quite often, but realistically any paid VPN will work as long as it supports port-forwarding.

Finally, if installing this on a physical machine, make sure that you have a spare USB stick ready.

## Preparation

- Navigate to the [Ubuntu Server](https://ubuntu.com/download/server) website and install the latest LTS version (at the time of writing, it's 24.04.2 LTS).

![[Pasted image 20250305182540.png]]
