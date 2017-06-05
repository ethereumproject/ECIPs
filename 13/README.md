---
domain: ecip.ethereumclassic.org
shortname: 13/OPCODE
name: Ethereum Virtual Machine
status: stable
editor: Wei Tang <hi@that.world>
---

The [EIP-150 revision](http://gavwood.com/paper.pdf) of the yellow
paper is used. This RFC refers to the Appendix H.

Until we are able to move the section of the yellow paper to
here. Those following things should be noted:

* If a call asks for more gas than the maximum allowed amount, do not
  return an OOG error; instead, call with the maximum allowed amount
  of gas.
