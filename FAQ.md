## Frequently Asked Questions
***

### Can I use this in my commercial or closed-source application or service?

Yes! - Just let us know, and we will work out a licensing scheme. You will need to build the library with the `lwIP` network stack. In the case that you're a non-profit, or are developing open source software, you can use this entirely for free and may choose either `picoTCP` or `lwIP` as your network stack.

### Application or service won't fully come online

In rare circumstances it can take a substantial amount of time for a libzt instance to come online and become reachable. In cases where it never seems to progress beyond this stage you should check to make sure there are no rogue processes on the machines using the same ZeroTier identity files, or no other instances on your ZeroTier network using said identity files. If this doesn't help. Contact us.

### How do I get debug output?

In order of relevance, enable the following: For `libzt`-specific debug output which basically includes the POSIX socket emulation layer and network stack *drivers*, enable `LIBZT_DEBUG=1`. For situations where you suspect that the problem might lie within the network stack itself, enable `NS_DEBUG=1`. You should also check out `include/libzt.h` for additional fine-grained debug options for each network stack. If you think that your problem is with the ZeroTier protocol itself, enable `ZT_DEBUG=1`. This will output what's happening in the ZeroTier core. Note, you can enable all of these at once if you're brave.