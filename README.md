# tcptrace

## What is tcptrace?

The following is a definition of ***tcptrace*** from [Wikipedia](https://en.wikipedia.org/wiki/Tcptrace):

> tcptrace is a free and open-source tool for analyzing TCP dump files. It accepts as input files produced by packet-capture programs, including tcpdump, Wireshark, and snoop. tcptrace can produce several different types of output containing information on each connection seen, such as elapsed time, bytes and segments sent and received, retransmissions, round trip times, window advertisements, and throughput. It can also produce graphs for further analysis. As of version 5, minimal UDP processing has been implemented in addition to the TCP capabilities.

## Compilation instructions

This repository contains all the files necessary to compile ***tcptrace*** on a Linux system (tested on Ubuntu 20.04) and a Mac (tested on macOS 12.1 Monterey).

Please execute the following steps to compile, in order:

```
cd tcptrace-6.6.7
./configure
make
```

In order to execute the locally compiled binary of ***tcptrace*** (generated using the above steps), execute:
```
./tcptrace [options] [network trace file]
```

For example, in order to print the *help* options, execute:
```
./tcptrace -h
```

In order to print a long-form summary of the network trace file (called *trace_file.pcap* in this example), including a summary of the round-trip times (RTTs), execute:
```
./tcptrace -rl trace_file.pcap
```

All advanced options are available at the [manual page](https://linux.die.net/man/1/tcptrace) and at the [official website](www.tcptrace.org).


## Note from maintainer

**Date:** Fri Aug 21, 2020

**Satadal Sengupta**\
*satadal.sengupta@princeton.edu*\
[Academic webpage](https://satadalsengupta.github.io/)

> I'm a Ph.D. candidate at Princeton University. I'm maintaining 
and enhancing this tool in personal interest as part of my research 
work. The original creator of this tool is Shawn Ostermann and his 
notes are available below. All citations should go to him.\
\
Detailed information about changes introduced by me is available in 
the commit messages - please follow those chronologically.\
\
Please contact me for more information.

## Note from creator

**Date:** Fri May 25, 2001

**Shawn Ostermann**\
*ostermann@cs.ohiou.edu*

> tcptrace is a TCP connection analysis tool.  It can tell you detailed
information about TCP connections by sifting through dump files.  The
dump file formats supported are:
>   - Standard tcpdump format (you need the pcap library)
>   - Sun's snoop format
>   - Macintosh Etherpeek format
>   - HP/NetMetrix protocol analysis format
>   - NS simulator output format
>   - NetScout
>   - NLANR Tsh Format\

> To see the graphs, you'll also need Tim Shepard's xplot program,
available at http://www.xplot.org\
\
I've switched to using "./configure" to set up the Makefile.  That
seems to have eased portability problems a great deal.  Just say
"./configure" and then "make" to build the program.\
\
Most of the rest of the Docs are on the web.\
Check out: http://www.tcptrace.org/


> **Supported Platforms:**
>
> The program is developed here at OU on Sparc machines running Solaris 8. Our intention is that it also run under common Unix variants.  In
particular, we try to test each release on the following platforms:
>  - NetBSD	
>  - FreeBSD	
>  - Linux		
>  - Darwin/OSX (Mac)
>  - Tru64 (Alpha)

> We appreciate feedback and fixes on these or other platforms and will
attempt to modify the program to work on other platforms if we can get
enough help from people with access to those platforms and the changes
are not too "esthetically disagreeable".\


> **Running the program:**
> 
> Some simple examples:
>
> 0) What are the args and what do they mean?\
     ``` tcptrace ``` 
> 1) Run the program quickly over a dump file\
     ``` tcptrace dumpfile ```
> 2) Get longer output\
     ``` tcptrace -l dumpfile ```
> 3) Generate lots of pretty plot files (you need xplot to see them)\
     ``` tcptrace -G dumpfile ```
> 4) Print the segment contents as you go\
     ``` tcptrace -p dumpfile ```
> 5) Print progress info (useful for large files)\
     ``` tcptrace -t dumpfile ```

> Of course, you can chain arguments together until you get just what
you want.\
\
Let me know what you think....\
\
**Shawn**
