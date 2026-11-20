# Description

Test that a CIP request whose path is an ANSI extended symbolic segment
(0x91, how Logix clients name a tag) is parsed instead of being flagged
as an invalid PDU, and that the additional status size of a CIP reply is
counted in 16-bit words.

# PCAP

Hand built, one TCP session to port 44818: Register Session, a Read Tag
request for "MyTag" with its reply, a Write Tag request for "Counter" with
a reply carrying general status 0xff and extended status 0x2107, and a
Read Tag request for "Tag1" with an unknown tag reply (status 0x04, extended
status 0x0000). The tag names cover an odd length (with the pad byte) and
an even length.

# Ticket

https://redmine.openinfosecfoundation.org/issues/TICKET
