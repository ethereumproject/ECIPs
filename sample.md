---
domain: ecip.ethereumclassic.org
shortname: 22/SAMPECIP
name: Sample Ethereum Classic Improvement Process
status: raw
editor: Stewart Mackenzie <setori88@gmail.com>
contributors:
  - Christopher Hitchens <chris@hitchslap.com>
---

## License

Copyright (C) 2009-2017  Ethereum Classic Contributors

Ethereum Classic Contributors have dedicated the work to the public domain by waiving all of its rights to the work worldwide under copyright law, including all related and neighboring rights, to the extent allowed by law.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
You can copy, modify, distribute and perform the work, even for commercial
purposes, all without asking permission. You should have received a copy of
the creative commons license (CC0 1.0 universal) along with this program.
See the license file for more information.

## Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119).

### Abstract
An Ethereum Classic Improvement Proposal (ECIP) is a contract between multiple parties, it specifies and provides information on Public APIs, file formats, protocols and workflows to the community. It communicates enough technical information to achieve an initial implementation for the community to discuss and refine the implementation and specification further. It has a lifecycle and supports forking and merging of specifications, thus reducing petty bickering in the community. Entire supply chains should be described with these composible ECIPs allowing market entry of competing vendors who selectively implement a few ECIP contracts and provide cheaper more efficient services and products.

### Motivation

An ECIP is the primary mechanism for isolating, discussing and solving problems within the community. It does this by collecting input on an issue, validating there is indeed a problem faced by many in the community and proposes a solution which provides enough technical information to make an implementation. The community achieves *rough consensus through executing code*.

### Specification
#### ECIP Lifecycle

* All ECIPs MUST follow a lifecycle as defined in [2/COSS](2/COSS), with the exception of [1/C4](1/C4) and [2/COSS](2/COSS) (see `C4 and COSS Evolution`)

#### ECIP Change Management

* All ECIPs MUST follow the [1/C4](1/C4) change management, with the exception of [1/C4](1/C4) and [2/COSS](2/COSS) (see `C4 and COSS Evolution`)

#### C4 and COSS Evolution

* [1/C4](1/C4) and [2/COSS](2/COSS) are an implementation of the [Scientific Method](https://en.wikipedia.org/wiki/Scientific_method) that was empirically derived by many communities, hence changes to these specifications MUST first be listed as an issue on the upstream git [repository](https://github.com/unprotocols/rfc).
* Discussion MUST take place there, not here.
* Members in this community MUST be alerted to a discussion on upstream.
* We SHALL adopt the stable version of `C4` and `COSS` specifications on upstream [repository](https://github.com/unprotocols/rfc) under the next available directory number in this repository and deprecate the previous `C4/COSS`.
* For this reason Pull Requests that modify or locally fork `C4` and `COSS` will be reverted immediately, unless they are made to reflect upstream stable `C4` and `COSS`.
* The [1/C4](1/C4) and [2/COSS](2/COSS) processes are falsifiable.

#### What belongs in a successful ECIP?
Each ECIP should have the following parts:

* Preamble -- RFC 822 style headers containing the `domain`, `shortname`, `name`, `status`, `editor` and `contributors` of the ECIP.

* Abstract -- a short (~200 word) description of the technical issue being addressed.

* Motivation -- The motivation is critical for ECIPs that want to change the Ethereum protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem the ECIP solves. ECIP submissions without sufficient motivation may be moved to the deleted section outright.

* Specification -- The technical specification should describe the syntax and semantics of the solution to the problem. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum Classic platforms.

* Rationale -- The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. These motivations should be based on hard fact and where possible proven by implementation. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages.

  * The rationale should provide evidence of rough consensus within the community and discuss important objections or concerns raised during discussion.

* Backwards Compatibility -- Only ECIPs that are in `raw` or `draft` status may make backward incompatible changes. Once an ECIP reaches a `stable` status then backward incompatible changes are not acceptable unless there is strong overriding consensus on the matter. Hence it is encouraged to experiment and really understand the problem while the ECIP is in `raw` or `draft` stages. Please read [2/COSS](2/COSS) for more details.

* Implementations -- An ECIP that has no implementation is a `raw` ECIP. As soon as there is a minimal implementation proving the concept then the ECIP is upgraded to `draft` status. Once enough experimentation has taken place and the specification feels sturdy enough that 3rd parties start to implement the specification then the ECIP becomes `stable`. At this point only cosmetic changes to the ECIP are accepted and public APIs are not changed. Please read [2/COSS](2/COSS) for more details.

#### ECIP Formats and Templates
ECIPs should be written in markdown format in a file name `README.md`. Image files should be included in the same directory as the ECIP.

#### ECIP Header Preamble
Each ECIP must begin with an RFC 822 style header preamble. The headers must appear in the following order. All headers are required except the `contributors`. The three dashes demarkate YAML.

```
---
domain: ecip.ethereumclassic.org
shortname: 22/SAMPLECIP
name: Sample Ethereum Classic Improvement Process
status: raw
editor: Stewart Mackenzie <setori88@gmail.com>
contributors:
  - Christopher Hitchens <chris@hitchslap.com>
  - Richard Dawkins <dick@4horsemen.com>
---
```

The `domain` header details the domain this rfc applies to.

The `shortname` is defined by [2/COSS](2/COSS) and should be constructed in such a way the brain can easily pattern match. The integer is the next available directory number and the shortname is a simplified version of the `name`. It should be easy to type as it'll be used regularly in discussion forums. Indeed competing specifications such as `4/FEE` and `5/FEE` might be discussed at length, each containing different meanings.

The `name` is the full name of the ECIP.

The `status` header does a few things, it automatically displays a status badge on the rendered page. Though you'll need to update your `SUMMARY.md` and place the ECIP in the correct location.

The `editor` header lists the person championing the ECIP. The format of the `editor` header value must be

  Random J. User <address@dom.ain>

if the email address is included, and just

  Random J. User

if the address is not given.

The `contributors` header are people who have collaborated on the ECIP.

If there are multiple contributors, each should be on a separate line using markdown dash lists.

#### Auxiliary Files
ECIPs may include auxiliary files such as diagrams. Such files must be named <number>-<shortname>-Y.ext, where <number> is the numbered of the directory the ECIP occupies, the <shortname> is the shortname without the "2/" and the "Y" is a serial number (starting at 1), and "ext" is replaced by the actual file extension (e.g. "png").

For example 2-COSS-4.png refers to a png image located in the `2` directory which is ECIP `2/COSS`.

#### Transferring ECIP Ownership
It occasionally becomes necessary to transfer ownership of ECIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred ECIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the ECIP process, or has fallen off the face of the 'net (i.e. is unreachable or not responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the ECIP. We try to build consensus around a ECIP, but if that's not possible, you can always submit a competing ECIP.

If you are interested in assuming ownership of an ECIP, send a message asking to take over, addressed to both the original author and the ECIP editor. If the original author doesn't respond to email in a timely manner, the ECIP editor will make a unilateral decision (it's not like such decisions can't be reversed :).

#### ECIP Editors
The current ECIP editors are
  * All volunteers in the Ethereum Classic Project github organization

#### ECIP Editor Responsibilities & Workflow
For each new ECIP that comes in, an editor does the following:

* Read the ECIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to be accepted.
* The title should accurately describe the content.
* Edit the ECIP for language (spelling, grammar, sentence structure, etc.), markup (for reST EWIPs), code style

If the ECIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the EIP is ready for the repository, the EIP editor will:

* Assign a EIP number (almost always just the next available number)

* Accept the corresponding pull request

* List the EIP in [[README.md]]

* Send email back to the EIP author with next step.

Many EIPs are written and maintained by developers with write access to the Ethereum codebase. The EIP editors monitor EIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on EIPs. We merely do the administrative & editorial part. Except for times like this, there's relatively low volume.

### Rationale
For Ethereum implementers, EIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the EIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

EIPs are intend to replace the venerable etherpads which described the initial PoC (Proof of Concept) and strike a balance between ease of accessibility and trackablity.

### Implementation
* Read and understand [1/C4](1/C4).
* Read and understand [2/COSS](2/COSS).
* Fork github.com/ethereumproject/ECIPs
* `git clone github.com/<your-fork>/ECIPs` repo.
* `cd ECIPs`
* `mkdir <next_available_directory_number>`
* `cp template.md <next_available_directory_number>/README.md`
* Edit the `shortname`, `name`, `status`.
* Edit the document's contents using the Markdown syntax.
* Don't forget to add your new ECIP in the `SUMMARY.md` document under the `raw` section.
* Make a Pull Request.

### History
This document was derived heavily from [https://github.com/bitcoin/bips Bitcoin's BIP-0001] written by Amir Taaki which in turn was derived from [https://www.python.org/dev/peps/ Python's PEP-0001]. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Ethereum Improvement Process, and should not be bothered with technical questions specific to Ethereum or the EIP. Please direct all comments to the EIP editors.
