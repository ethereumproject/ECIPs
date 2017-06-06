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
An Ethereum Classic Improvement Proposal (ECIP) is a contract between multiple parties, it specifies and provides information on Public APIs, file formats, protocols and workflows to the community. It communicates enough technical information to achieve an initial implementation for the community to discuss and refine the implementation and specification further. It has a lifecycle and supports forking and merging of specifications, thus reducing petty bickering in the community. Entire supply chains should be formed with these composible ECIPs allowing market entry of competing vendors who selectively implement a few ECIP contracts and provide cheaper more efficient services.

### Motivation

An ECIP is the primary mechanism for isolating, discussing and solving problems within the community. It does this by collecting input on an issue, validating there is indeed a problem faced by many in the community and proposes a solution which provids enough technical information to make an implementation. The community achieves *rough consensus through executing code*.

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

#### What belongs in a successful EIP?
Each ECIP should have the following parts:

* Preamble -- RFC 822 style headers containing metadata about the EIP, including the EIP number, a short descriptive title (limited to a maximum of 44 characters), the names, and optionally the contact info for each author, etc.

* Abstract -- a short (~200 word) description of the technical issue being addressed.

* Specification -- The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum platforms (cpp-ethereum, go-ethereum, ethereumj, ethereumjs).

* Motivation -- The motivation is critical for EIPs that want to change the Ethereum protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the EIP solves. EIP submissions without sufficient motivation may be rejected outright.

* Rationale -- The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages.

* The rationale should provide evidence of consensus within the community and discuss important objections or concerns raised during discussion.

* Backwards Compatibility -- All EIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The EIP must explain how the author proposes to deal with these incompatibilities. EIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

* Implementations -- The implementations must be completed before any EIP is given status "Final", but it need not be completed before the EIP is accepted. It is better to finish the specification and rationale first and reach consensus on it before writing code.

#### EIP Formats and Templates
EIPs should be written in markdown format. Image files should be included in a subdirectory for that EIP.

#### EIP Header Preamble
Each EIP must begin with an RFC 822 style header preamble. The headers must appear in the following order. Headers marked with "\*" are optional and are described below. All other headers are required.

      EIP: <EIP number>
      Title: <EIP title>
      Author: <list of authors' real names and optionally, email address>
    * Discussions-To: <email address>
      Status: <Draft | Active | Accepted | Deferred | Rejected |
               Withdrawn | Final | Superseded>
      Type: <Standards Track | Informational | Process>
      Created: <date created on, in ISO 8601 (yyyy-mm-dd) format>
    * Replaces: <EIP number>
    * Superseded-By: <EIP number>
    * Resolution: <url>

The Author header lists the names, and optionally the email addresses of all the authors/owners of the EIP. The format of the Author header value must be

  Random J. User <address@dom.ain>

if the email address is included, and just

  Random J. User

if the address is not given.

If there are multiple authors, each should be on a separate line following RFC 2822 continuation line conventions.

Note: The Resolution header is required for Standards Track EIPs only. It contains a URL that should point to an email message or other web resource where the pronouncement about the EIP is made.

While a EIP is in private discussions (usually during the initial Draft phase), a Discussions-To header will indicate the mailing list or URL where the EIP is being discussed. No Discussions-To header is necessary if the EIP is being discussed privately with the author.

The Type header specifies the type of EIP: Standards Track, Informational, or Process.

The Created header records the date that the EIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

EIPs may have a Requires header, indicating the EIP numbers that this EIP depends on.

EIPs may also have a Superseded-By header indicating that a EIP has been rendered obsolete by a later document; the value is the number of the EIP that replaces the current document. The newer EIP must have a Replaces header containing the number of the EIP that it rendered obsolete.

#### Auxiliary Files
EIPs may include auxiliary files such as diagrams. Such files must be named EIP-XXXX-Y.ext, where "XXXX" is the EIP number, "Y" is a serial number (starting at 1), and "ext" is replaced by the actual file extension (e.g. "png").

#### Transferring EIP Ownership
It occasionally becomes necessary to transfer ownership of EIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred EIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the EIP process, or has fallen off the face of the 'net (i.e. is unreachable or not responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the EIP. We try to build consensus around a EIP, but if that's not possible, you can always submit a competing EIP.

If you are interested in assuming ownership of a EIP, send a message asking to take over, addressed to both the original author and the EIP editor. If the original author doesn't respond to email in a timely manner, the EIP editor will make a unilateral decision (it's not like such decisions can't be reversed :).

#### EIP Editors
The current EIP editors are
  * All volunteers in the Ethereum Classic Project github organization

#### EIP Editor Responsibilities & Workflow
For each new EIP that comes in, an editor does the following:

* Read the EIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to be accepted.
* The title should accurately describe the content.
* Edit the EIP for language (spelling, grammar, sentence structure, etc.), markup (for reST EWIPs), code style

If the EIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

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
* `git clone github.com/<your-fork>/ECIPs` repo
* `mkdir <next_available_directory_number>`
* `cp template.md <next_available_directory_number>/README.md`
* Edit the `shortname`, `name`, `status`.
* Edit the document's contents using the Markdown syntax.
* Don't forget to add your new ECIP in the `SUMMARY.md` document under the `raw` section.
* Make a Pull Request.

### History
This document was derived heavily from [https://github.com/bitcoin/bips Bitcoin's BIP-0001] written by Amir Taaki which in turn was derived from [https://www.python.org/dev/peps/ Python's PEP-0001]. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Ethereum Improvement Process, and should not be bothered with technical questions specific to Ethereum or the EIP. Please direct all comments to the EIP editors.
