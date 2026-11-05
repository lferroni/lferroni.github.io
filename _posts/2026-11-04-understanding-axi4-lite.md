---
layout: post
title: "Understanding and implementing AXI4-Lite"
description: "Explaination of the basics of AXI4-Lite and implementing it on a UART peripheral."
comments: true
keywords: "AXI4-Lite,AXI4,AMBA,AXI4-Stream,AMBA,AXI,UART"
---

The AXI bus is a widely used bus standard for on-chip communication. Its official documentation called the AMBA AXI protocol, maintained by ARM, is around 300 pages long (pretty intimidating if you ask me) but in this post we will only focus on the part A and B since they cover the features necessary to build a AXI4-Lite slave first and then a AXI4-Lite master.

### Why use a bus standard?
When learning a new technology I always tend to ask myself "why is it designed this way?", "what problems was it designed to solve?". In this case the answer is pretty straightforward. Consider the following situation:


In the diagram we can see 3 modules 

### Understanding AXI4 Transactions
The AXI4 specification defines 5 different channels of communication between a master and a slave:

1. Write Address Channel (AW)
2. Write Data Channel (W)
3. Write Response Channel (B)
4. Read Address Channel (AR)
5. Read Data Channel (R)

Giving an easy example of the channel flow, the read address channel (AR) will carry control information (like a register address from where to read the data from and its size) from master to slave, then the read data channel (R) will carry the data read from the slave to the master. 

Each channel will contain many different signals carrying information, two of them present on every channel are the VALID and READY
signals used in the handshake process.

### Where does it come from?

Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.

The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. Sections 1.10.32 and 1.10.33 from "de Finibus Bonorum et Malorum" by Cicero are also reproduced in their exact original form, accompanied by English versions from the 1914 translation by H. Rackham.

### Why do we use it?

It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).

### Where can I get some?

There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary, making this the first true generator on the Internet. It uses a dictionary of over 200 Latin words, combined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The generated Lorem Ipsum is therefore always free from repetition, injected humour, or non-characteristic words etc.

> This content was copied from http://www.lipsum.com/ as an example of post article.
