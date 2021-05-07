---
coding: utf-8

title: "Gap Analysis in Internet Addressing"
abbrev: "Gap Analysis in Internet Addressing"
docname: draft-intarea-gap-analysis-internet-addressing-00
category: info
area: Internet
workgroup: Internet Area Working Group
keyword: Internet-Draft

ipr: trust200902
date: {DATE}
stand_alone: yes
pi: [toc, sortrefs, symrefs, docmapping]


author:
-
  ins: Anonymity
  name: Anonymity
  org: Anonymity
  abbrev: TBD
  street: TBD
  city: TBD
  country: Anonymity
  code: 'TBD'
  email: TBD


normative:


informative:


--- abstract

The body of the document contain the skeleton of the content.

--- middle


# Introduction {#SEC:intro}

Describe approach of draft:

* Outline properties of Internet addressing ({{SEC:properties}})
* Identify extensions to those properties -> gaps ({{SEC:extensions}}), summarized in {{SEC:overview}}
* Analyze those extensions wrt issues ({{SEC:issues}}) -> may identify further gaps in those extensions


# Properties of Internet Addressing {#SEC:properties}

This outlines what properties are currently foreseen for internet addressing with RFCs as basis

## Property 1: Fixed Address Length

32-bit for IPv4, 128-bit for IPv6

## Property 2: Limited Address Semantic

no structure for IPv4, limited structure for IPv6 but with the 'twist' that semantics of identifier & locator are intertwined.

## Property 3: Ambiguous Address Semantic

discuss ambiguity of address in various contexts, e.g., IPv6 as PII or network interface






# Extensions to Addressing Properties {#SEC:extensions}

NOTE: Reasoning here is that this is the ‘gap’ compared to Section 1 in terms of desired properties since we can observe solutions for it. If we had an extension without any example, we’d had a desired property (although we are likely to find an example at least in research).

## Length Extensions

Extensions here cover those to property 1, i.e., the fixed length. We distinguish here extensions for shorter or longer addresses. Other extensions could be those for structured addresses which could be either shorter or longer.

### Shorter Address Length

**Description**: Sensor networks etc.

**Approaches**: Header compression, header translation

**Examples**: 6Lo: IEEE 802.15.4 16-bit address, ITU-t G.9959 32-bit HomeID, 16-bit NodeID, etc.


### Longer Address Length

**Description**: Anything going beyond 128bit, possibly structured or not

**Approaches**: Overlay? Radical new format

**Examples**: ICN names


## Semantic Extensions

These extensions address property 2 but include any approaches that utilize semantics beyond those defined by the Internet address for making a decision for forwarding the packet towards a local network interface. With this in mind, we distinguish here those which extend the address semantic, i.e., work within the given address size and semantic of an Internet address, from those which extend the semantic through existing or additional header fields outside the Internet address.

### Utilizing Extended Address Semantics

**Description**: New IPv6 address semantics, which may include structured approaches to addresses albeit in the limits of IPv6 address size and semantic.

**Approaches**: 
1) Semantic prefixes
2) refactor IPv6 semantics but also locator/ID split
3) on-demand overlay loaded for new semantic

**Examples**: e.g., (1) Dyncast, (2) ILNP, (3) CGA


### Utilizing Existing or Extended Header Semantics

**Description**: Here comes the bulk of new semantics that use existing or new header fields as well as extension headers.

**Approaches**: e.g., Extension headers, additional layers

**Examples**: e.g., SHIM6, SRv6, detnet, flow label, HIP, LISP, ICN




## Identity Assignment Extensions

These extensions target property 3, i.e., the assignment of identifiers.

### Anonymous Address Identity

**Description**: 

**Approaches**: Proxies/ ephemeral addresses

**Examples**: e.g., Tor, ODoH

### Authenticated Address Identity

**Description**: 

**Approaches**: e.g., Proxy/Third party trust anchor

**Examples**: e.g., CGA



# Overview of Approaches to Extend Internet Addressing {#SEC:overview}

Table, derived from {{SEC:extensions}}


# Issues in Extensions to Internet Addressing {#SEC:issues}

Suggest to list the problems here, then associate those to approaches first and the extension properties in {{SEC:extensions}}


## Limiting Address Semantics

If adhering to size of address field, might negatively impact semantic expressiveness

## Edge Complexity and Efficiency

Impacted by, e.g., header compression

## Core Complexity and Efficiency

* Impact by, e.g., semantic complexity of address
* Impacted by, e.g., need for parsing more than header field

## Fragility

## Security

## Extensibility

## ...



# Security Considerations {#SEC:sec}

TBD.


# IANA Considerations {#SEC:iana}

This document does not include an IANA request.


--- back


<!-- 

# Change Log

**NOTES**: Please remove this section prior to publication of a final version of this document.

TBD.

# Acknowledgments
{:numbered="false"}

Here is Acknowledgements.

-->
