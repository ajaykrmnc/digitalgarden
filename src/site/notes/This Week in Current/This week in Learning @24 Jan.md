---
{
  "dg-publish": true,
  "permalink": "/this-week-in-current/this-week-in-learning-24-jan/",
}
---

-- 2026-01-24 21:47

This week I mostly worked upon learning the kernel driver modules, I also went through lsp setup, backing up
the export, understanding the docker container, also inspecting the images, learnt how cross compilation done
and mostly read the generated content of the augment, I also went through different level's of the how the
barney docker is happening,
Honestly I messed up a little bit in the mid of the week. I worked a little less this week. Mostly I've learnt
the networking stack, how the data packet is getting transferred over the network, read some tutorial about
the sk_buff which is a primary data structure used across different network layer starting from the
application layer to the link layer, I skbuff have control buffer which is internally managed by the tcp/udp
buffer It's very interesting to know that every data packet follow the same struct and through the pull and
put method they can be added with the ethernet/ip header's. They follow the headroom data and tailroom and a
shared info, then I questionned their is abstraction layer over this since the networking stack differ from os
to os. there's a OS interface over this buffer. I also go to know about the SRing buffer algorithm in which
the data got replished to the main memory of the host machine ie cpu with zero memory copy mechanism through
the dma engine, since we don't copy it to the device driver we directly copy it to the host machine.

I'm also done the remote lsp setup like the remote process, running over the docker container and connected
ssh through to my computer and I'm using the lsp over tcp protocol by maintaining a persistence connnection
through my laptop to docker ssh. Since the problem I was facing is cross architecture of Mac OS, vs Linux
since the macOS doesn't understand the ELF(Executable and Linking format) all the element or the path
generated in the the compile_commands.json file, have their corresponding elf output which the macOS doesn't
understand since it's arm based architecture and Linux is x86 architecture since they follow different rule
the arm architecture follow risc-v vs the x86 follow's the cisc which takes more energy so for embedded
development it's preferrable to use arm which aarch64 which means arm architecture with 64 bit. Along the way
I also learnt the 8 level's of print the kernel error. like printk, pr_debug. and error, for the first time
I've booted the device manually, off course I've rebooted my mac Once through but this hit's different.

Now my plan's is to learn about the memory hierarchy which program is cache friendly and which are not.
yesterday I planned to read about the how to read the man file's because these day's I'm using CLI very much
so I thought that every time instead of googling the command for the cli, I get to know what's the correct way
to learn this things. So I get introduced to Man Pages. I learnt the synposis, description, bug's and all the
different part's of the man pages, Now I'm able to digest the man pages very well. Okay I forgot to mentioned
that during the tranferring a chunk's of files I got noticed how it's efficient to send data through bundling
them and then send over the network. Then I learnt about the tar command how it's pack/unpack the data to send
over the network. It's compression algorithm, differeces between ssh scp rsync, which one is efficient and
how's it's efficient. Noted abou the rtt and failure mode how to trace back the failure mode. I noticed the
blob (Binary large object) which is also used in git file's so It's also interesting to learn about how the
git handle everything which I'm gonna to read about that also. I got also exposed through the gnu core util's
how to securely zip/unzip the file's using sha1/sha2 and sha256. It's also interesting to know about the lsof
program, which on which port which program is running over. What is vcs mostly hg, and git.

Also forgot to mention that the transition from the obsidian to nvim happen very well. I also installed the
image previwer, which enable me to the preview the image inside the terminal itself.

I'm also have the discussion over the future of AI, I cannot forgot to mention that the Andrej Karapathy video
over the YC Combinator goes viral and got 23 million of view. It's must watch i got understanding about how
the ai closely resemble to the Operating system. the Chrome will the next the Ethernet device. The context
window will the ram and the modern day computer will the terminal for the AI. And the embedding will the
physical memory of the device. It's very crazy thing that how they think about the AI no one is thinking like
that.. here in India. I know sarvam like startup is doing something in India but not much. For the
entertainmain I watched the movie Up from the Pixar and the cricket match in this week. I believe I'm learning
a lot these day. On Saturday I cleaned the room and common area. Also I'm willing to learn about the dynamic
dispatch and vtable. I've already ordered the book by the Bjarne Stroutoup. Now I need to learn about the
databases and How I can utilise the knowledge I've already acquired to the databases and transaction
processing this things' I've learnt along the way I'm sure will help me to grow faster. All this thing. I'm
planning to go to home in Holi so I need to book the ticket also.
Thanks, Ba Bye.
