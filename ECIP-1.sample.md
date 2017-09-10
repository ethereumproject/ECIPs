### What is an EIP?

    EIP: 1
    Title: EIP Purpose and Guidelines
    Status: Draft
    Type: Meta
    Author: Martin Becze <mb@ethdev.com>
    Created: 2015-10-27

### Abstract
EIP stands for Ethereum Improvement Proposal. A EIP is a design document providing information to the Ethereum classic community, or describing a new feature for Ethereum or its processes or environment. The EIP should provide a concise technical specification of the feature and a rationale for the feature.  The EIP author is responsible for building consensus within the community and documenting dissenting opinions.

### Motivation
We intend EIPs to be the primary mechanisms for proposing new features, for collecting community input on an issue and for documenting the design decisions that have gone into Ethereum. Because the EIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

### Specification
#### EIP Types
There are three kinds of EIP:

* A Standard Track EIP describes any change that affects most or all Ethereum implementations, such as a change to the [https://github.com/ethereum/yellowpaper Yellow Paper], the network protocol, a change in block or transaction validity rules, or any change or addition that affects the interoperability of applications using Ethereum. Furthermore Standard EIPs can be broken down into the following categories.
** Consensus - Once PoS has been established it is expected that PoS protocol will have a separate specification.
** Networking - Currently Networking discussion tracks in the [https://github.com/ethereum/devp2p devp2p repository].

* An Informational EIP describes a Ethereum design issue, or provides general guidelines or information to the Ethereum community, but does not propose a new feature. Informational EIPs do not necessarily represent Ethereum community consensus or a recommendation, so users and implementors are free to ignore Informational EIPs or follow their advice.
* A Meta EIP describes a process surrounding Ethereum or proposes a change to (or an event in) a process. Process EIPs are like Standards Track EIPs but apply to areas other than the Ethereum protocol itself. They may propose an implementation, but not to Ethereum's codebase; they often require community consensus; unlike Informational EIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in Ethereum development. Any meta-EIP is also considered a Process EIP.

#### EIP Work Flow
The EIP repository Collaborators change the EIPs status. Please send all EIP-related email to the EIP Collaborators, which is listed under EIP Editors below. Also see EIP Editor Responsibilities & Workflow.

The EIP process begins with a new idea for Ethereum. It is highly recommended that a single EIP contain a single key proposal or new idea. Small enhancements or patches that don't affect consensus often don't need a EIP and can be injected into the Ethereum development workflow with a patch submission to the corresponding Ethereum issue tracker. The more focused the EIP, the more successful it tends to be. The EIP editor reserves the right to reject EIP proposals if they appear too unfocused or too broad. If in doubt, split your EIP into several well-focused ones.

Each EIP must have a champion -- someone who writes the EIP using the style and format described below, shepherds the discussions in the appropriate forums, and attempts to build community consensus around the idea. The EIP champion (a.k.a. Author) should first attempt to ascertain whether the idea is EIP-able. Posting to the  the [https://forum.ethereum.org/categories/protocol-and-client-discussion Protocol Discussion] forum or opening an [https://github.com/ethereum/EIP/issues Issue] is the best way to go about this.

Vetting an idea publicly before going as far as writing a EIP is meant to save the potential author time. Asking the Ethereum community first if an idea is original helps prevent too much time being spent on something that is guaranteed to be rejected based on prior discussions (searching the Internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where Ethereum is used.

Once the champion has asked the Ethereum community as to whether an idea has any chance of acceptance, a draft EIP should be presented as a Pull Request. This gives the author a chance to flesh out the draft EIP to make properly formatted, of high quality, and to address initial concerns about the proposal.

If the EIP collaborators approves, the EIP editor will assign the EIP a number, label it as Standards Track, Informational, or Process, give it status "Draft", and add it to the git repository. The EIP editor will not unreasonably deny an EIP. Reasons for denying EIP status include duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the Ethereum philosophy.

The EIP author may update the Draft as necessary in the git repository. Updates to drafts may also be submitted by the author as pull requests.

Standards Track EIPs consist of three parts, a design document, implementation and finally if warranted an update to the [https://github.com/ethereum/yellowpaper formal specification]. The EIP should be reviewed and accepted before an implementation is begun, unless an implementation will aid people in studying the EIP. Standards Track EIPs must be implemented in at least two viable Ethereum clients before it can be considered Final.

EIP authors are responsible for collecting community feedback on a EIP before submitting it for review. However, wherever possible, long open-ended discussions should be avoided. Strategies to keep the discussions efficient include: having the EIP author accept private comments in the early design phases, setting up a wiki page or git repository, etc. EIP authors should use their discretion here.

For a EIP to be accepted it must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

Once a EIP has been accepted, the implementations must be completed. When the implementation is complete in at least two viable clients and accepted by the community, the status will be changed to "Final". An update to the [https://github.com/ethereum/yellowpaper formal specification] should accompany the "Final" status change.

A EIP can also be assigned status "Deferred". The EIP author or editor can assign the EIP this status when no progress is being made on the EIP. Once a EIP is deferred, the EIP editor can re-assign it to draft status.

A EIP can also be "Rejected". Perhaps after all is said and done it was not a good idea. It is still important to have a record of this fact.

EIPs can also be superseded by a different EIP, rendering the original obsolete. This is intended for Informational EIPs, where version 2 of an API can replace version 1.

The possible paths of the status of EIPs are as follows:

<img src=./process.png>

Some Informational and Process EIPs may also have a status of "Active" if they are never meant to be completed. E.g. EIP 1 (this EIP).

#### What belongs in a successful EIP?
Each EIP should have the following parts:

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
Each EIP must begin with an RFC 822 style header preamble. The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

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
Fork the [EIP repo](https://github.com/ethereumproject/EIPs). Write an EIP using the [EIP markdown template](./EIP-0000.md.template) and initiate a pull request.

### History
This document was derived heavily from [https://github.com/bitcoin/bips Bitcoin's BIP-0001] written by Amir Taaki which in turn was derived from [https://www.python.org/dev/peps/ Python's PEP-0001]. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Ethereum Improvement Process, and should not be bothered with technical questions specific to Ethereum or the EIP. Please direct all comments to the EIP editors.
