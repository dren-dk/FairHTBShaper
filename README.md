This is a traffic shaper generator that allows a number of different subnets to equally
share the bandwidth (both up and down stream) though a Linux router.

Ideally the traffic shaper would place a shaping tree on both input and output of the
WAN interface, but Linux does not allow one to place a traffic shaper on the incoming
traffic, only the outgoing.

This traffic shaper funnels all the downstream traffic via an ifb0 device which
allows several internal interfaces to share the same queue structure, thus allowing
near-perfect ingress shaping.

The gen-shaper script outputs a plain shell script that can be run on even quite
feeble routers.

See the start of the gen-shaper script for a desciption of the config options.

