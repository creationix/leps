| Title  | Create sockets early |
|--------|----------------------|
| Author | @creationix          |
| Status | DRAFT                |
| Date   | 2015-09-22 015:17:00 |


## Overview

Currently libuv does not help in creating raw sockets of any kind.  I have run across a couple use cases
requireing raw sockets to implement internet protocols other than TCP and UDP.

 - ICMP Ping (needed by the rackspace monitoring agent, written in luvit)
 - DTLS messages over SCTP (needed by openpeer.org's node.js browser<->ORTC bridge)


## API

I'm still learning what a good API for this would be.  This seems almost as hard as requesting ioctl support
in such a cross-platform library.

Ideally, I could create a "raw" socket and implement the IP and higher level protocol headers using my own custom code.

What exactly "raw" means and what kernel flags are common or assumed, I'm still researching.
