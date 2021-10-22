---
coding: utf-8

title: "Gap Analysis in Internet Addressing"
abbrev: "Gap Analysis in Internet Addressing"
docname: draft-jia-intarea-internet-addressing-gap-analysis-01
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
  ins: Y. Jia
  name: Yihao Jia
  org: Huawei Technologies Co., Ltd
  abbrev: Huawei
  # role: editor
  street: 156 Beiqing Rd.
  city: Beijing
  country: P.R. China
  code: '100095'
  email: jiayihao@huawei.com
-
  ins: D. Trossen
  name: Dirk Trossen
  org: Huawei Technologies Duesseldorf GmbH
  abbrev: Huawei
  # role: editor
  street: Riesstr. 25C
  city: Munich
  country: Germany
  code: '80992'
  email: dirk.trossen@huawei.com
-
  ins: L. Iannone
  name: Luigi Iannone
  org: Huawei Technologies France S.A.S.U.
  abbrev: Huawei
  # role: editor
  street: 18, Quai du Point du Jour
  city: Boulogne-Billancourt
  country: France
  code: '92100'
  email: luigi.iannone@huawei.com
-
  ins: N. Shenoy
  name: Nirmala Shenoy
  org: Rochester Institute of Technology
  abbrev: R.I.T.
  # role: editor
  street: ''
  city: New-York
  country: USA
  code: '14623'
  email: nxsvks@rit.edu
-
  ins: P. Mendes
  name: Paulo Mendes
  org: Airbus
  abbrev: Airbus
  # role: editor
  street: Willy-Messerschmitt Strasse 1
  city: Munich
  country: Germany
  code: '81663'
  email: paulo.mendes@airbus.com



normative:


informative:

  # Here are drafts

  I-D.ietf-lisp-introduction:
  I-D.ietf-lisp-mn:
  I-D.ietf-intarea-gue:

  EPHEMERALv6: I-D.gont-v6ops-ipv6-addressing-considerations
  ODoH: I-D.pauly-dprive-oblivious-doh
  OHTTP: I-D.thomson-http-oblivious
  ICNIP: I-D.trossen-icnrg-internet-icn-5glan

  #BIER-MC: I-D.ietf-bier-multicast-http-response
  #I-D.ietf-lisp-nexagon:
  #ICN5G: I-D.irtf-icnrg-5gc-icn


  # Here are publications
  GDPR: DOI.10.1007/978-3-319-57959-7
  ONION: DOI.10.1145/293411.293443
  VPN: DOI.10.1109/MCOM.2004.1341273
  WireGuard: DOI.10.14722/NDSS.2017.23160
  ROHC: DOI.10.1007/s11277-005-7733-2
  ITU9959: DOI.10.1007/978-3-319-26567-4_13
  UA-DHCP:  DOI.10.1109/LCN.2002.1181774


  # below references were copied from PS

  ADDRLESS: DOI.10.1371/journal.pone.0246293
  SFCANYCAST: DOI.10.1145/3314148.3314355
  REED: DOI.10.1109/ICC.2016.7511036
  SPHINX: DOI.10.1109/SP.2009.15
  OPENFLOW: DOI.10.1145/1355734.1355746
  POSTEL: DOI.10.1109/TCOM.1980.1094705
  HEADER_COMP_ISSUES1: DOI.10.1109/APCC.2011.6152926
  ROBUSTSDN: DOI.10.1109/INFOCOM.2015.7218382
  TRANSACTIONSDN: DOI.10.1109/EuCNC.2018.8442793
  P4: DOI.10.1145/2656877.2656890
  FAYED21: DOI.10.1145/3452296.3472922
  CLOUDFLARE_SIGCOMM: DOI.10.1145/3452296.3472922

  #MANET1: DOI.10.1177/1550147716671255
  #CCN: DOI.10.1145/1658939.1658941
  #HANDLEY: DOI.10.1145/3286062.3286075
  #TROSSEN: DOI.10.1145/1764873.1764878
  #ALOHA: DOI.10.1145/205447.205451
  #CARTISEAN: DOI.10.1007/978-3-540-39611-6_27
  #ANYCAST: DOI.10.1145/3230543.3230547
  #TORMEASURE: DOI.10.1145/3278532.3278549


  # Here are self-defined references

  TOR:
      title: The Tor Project
      target: https://www.torproject.org/
  HICN:
    title: "Hybrid Information-Centric Networking: ICN inside the Internet Protocol"
    author:
      ins: L. Muscariello
    target: https://datatracker.ietf.org/meeting/interim-2018-icnrg-01/materials/slides-interim-2018-icnrg-01-sessa-hybrid-icn-hicn-luca-muscariello
    date: 2018-03
  EXPRESSIVE-POWER:
    title: "The expressive power of the Internet design"
    author:
      ins: D. Clark
    target: http://groups.csail.mit.edu/ana/People/DDC/Expressive%20power%205.pdf
    date: 2009-04
  CONTIKI:
    title: "Contiki-NG: The OS for Next Generation IoT Devices"
    target: https://github.com/contiki-ng/contiki-ng
  GNATCATCHER:
    title: Global Network Address Translation Combined with Audited and Trusted CDN or HTTP-Proxy Eliminating Reidentification
    target: https://github.com/bslassey/ip-blindness
  EIBP:
    title: "A Structured Approach to Routing in the Internet"
    author:
        ins: N. Shenoy, S. Chandraiah, P. Willis
    target: First Intl Workshop on Semantic Addressing and Routing for Future Networks
    date: 2021-06
  HISTORY127:
    title: History of 127/8 as localhost/loopback addresses
    target: https://elists.isoc.org/pipermail/internet-history/2021-January/006920.html






--- abstract

There exist many extensions to Internet addressing, as it is defined in {{?RFC0791}} for IPv4 and {{?RFC8200}} for IPv6, respectively. Those extensions have been developed to fill gaps in capabilities beyond the basic properties of Internet addressing. This document outlines those properties as a baseline against which the extensions are categorized in terms of methodology used to fill the gap together with examples of solutions doing so.

While introducing such extensions, we outline the issues we see with those extensions. This ultimately leads to consider whether or not a more consistent approach to tackling the identified gaps, beyond point-wise extensions as done so far, would be beneficial. The benefits are the ones detailed in the companion document {{?I-D.jia-intarea-scenarios-problems-addressing}}, where, leveraging on the gaps identified in this memo and scenarios provided in {{I-D.jia-intarea-scenarios-problems-addressing}}, a clear problem statement is provided.

--- middle





# Introduction {#SEC:intro}

{{?I-D.jia-intarea-scenarios-problems-addressing}} outlines scenarios and problems in Internet addressing through presenting a number of cases of communication that have emerged over the many years of utilizing the Internet and for which various extensions to the network interface-centric addressing of IPv6 have been developed. In order to continue the discussion on the emerging needs for addressing, initiated with {{?I-D.jia-intarea-scenarios-problems-addressing}}, this memo aims at identifying gaps between the Internet addressing model and desirable features that have been added by various extensions, in various contexts.

The approach to identifying the gaps is guided by key properties of Internet addressing, outlined in {{SEC:properties}}, namely (i) the fixed length of the IP addresses, (ii) the ambiguity of IP addresses semantic, while still (iii) providing limited IP address semantic support. Those properties are derived directly as a consequence of the respective standards that provide the basis for Internet addressing, most notably {{?RFC0791}} for IPv4 and {{?RFC8200}} for IPv6, respectively.

Those basic properties, and the potential issues that arise from those properties, give way to extensions that have been proposed over the course of deploying new Internet technologies. {{SEC:extensions}} discusses those extensions, summarized as gaps against the basic properties in {{SEC:overview}}.

Finally, this memo outlines issues that arise with the extension-driven approach to the basic Internet addressing, discussed in {{SEC:issues}}, arguing that any requirements for solutions that would revise the basic Internet addressing would require to address those issues.


# Properties of Internet Addressing {#SEC:properties}

As the Internet Protocol adoption has grown towards the global communication system we know today, its characteristics have evolved subtly, with {{?RFC6250}} documenting various aspects of the IP service model and its frequent misconceptions, including Internet addressing. In this section, the three most acknowledged properties related to *Internet addressing* are detailed. Those are (i) fixed IP address length, (ii) ambiguous IP address semantic, and (iii) limited IP address semantic support.

{{SEC:extensions}} elaborates on various extensions that aim to expand Internet addressing beyond those properties; those extensions are positioned as intentions to close perceived gaps against those key properties.

<!-- [LI]: We did the hell of a job in defining the properties ;-) -->

## Property 1: Fixed Address Length {#SEC:properties:1}

The fixed IP address length is specified as a key property of the design of Internet addressing, with 32 bits for IPv4 ({{?RFC0791}}), and 128 bits for IPv6 ({{?RFC8200}}), respectively. Given the capability of the hardware at the time of IPv4 design, a fixed length address was considered as a more appropriate choice for efficient packet forwarding. Although the address length was once considered to be variable during the design of Internet Protocol Next Generation ("IPng", cf., {{?RFC1752}}) in the 1990s, it finally inherited the design of IPv4 and adopted a fixed length address towards the current IPv6. As a consequence, the 128-bit fixed address length of IPv6 is regarded as a balance between fast forwarding (i.e., fixed length) and practically boundless cyberspace (i.e., enabled by using 128-bit addresses).


## Property 2: Ambiguous Address Semantic {#SEC:properties:2}

Initially, the meaning of an IP address has been to identify an interface on a network device, although, when {{?RFC0791}} was written, there were no explicit definitions of the IP address semantic.

With the global expansion of the Internet protocol, the semantic of the IP address is commonly believed to contain at least two notions, i.e., the explicit 'locator', and the implicit 'identifier'. Because of the increasing use of IP addresses to both identify a node and to indicate the physical or virtual location of the node, the intertwined address semantics of identifier and locator was then gradually observed and first documented in {{?RFC2101}} as 'locator/identifier overload' property. With this, the IP address is used as an identification for host and server, very often directly used, e.g., for remote access or maintenance.


## Property 3: Limited Address Semantic Support {#SEC:properties:3}

Although IPv4 {{?RFC0791}} did not add any semantic to IP addresses beyond interface identification (and location), time has proven that additional semantics are desirable (c.f., the history of 127/8 {{HISTORY127}} or the introduction of private addresses {{?RFC1918}}), hence, IPv6 {{?RFC4291}} introduced some form of additional semantics based on specific prefix values, for instance link-local addresses or a more structured multicast addressing. Nevertheless, systematic support for rich address semantics remains limited and basically prefix-based.

# Filling Gaps through Extensions to Internet Addressing Properties {#SEC:extensions}

Over the years, a plethora of extensions has been proposed in order to move beyond the native properties of IP addresses, outlined in the previous section. The development of those extensions can be interpreted as filling gaps between the original properties of Internet addressing and desired new capabilities that those developing the extensions identified as being missing and yet needed and desirable.


## Length Extensions

Extensions in this subsection aim at extending the property described in {{SEC:properties:1}}, i.e., the fixed IP address length.

When IPv6 was designed, the main objective was to create an address space that would not lead to the same situation as IPv4, namely to address exhaustion. To this end, while keeping the same addressing model like IPv4, IPv6 adopted a 128-bit address length with the aim of providing a sufficient and future-proof address space. The choice was also founded on the assumption that advances in hardware and Moore's law would still allow to make routing and forwarding faster, and the IPv6 routing table manageable.

We observe, however, that the rise of new use cases but also the number of new, e.g., industrial/home or small footprint devices, was possibly unforeseen. Sensor networks and more generally the Internet of Things (IoT) emerged after the core body of work on IPv6. Nevertheless, it was clear from the beginning that, different from IPv6 assumptions, 128-bit addresses were costly in certain scenarios.

At the same time, new use cases emerged, where addresses even bigger than 128-bit are useful, like in the context of content centric networks, structured addresses, or cryptographically generated addresses.


### Shorter Address Length

#### Description:

In the context of IoT {{?RFC7228}}, where bandwidth and energy are very scarce resources, the static length of 128-bit for an IP address is more a hindrance than a benefit since 128-bit for an IP address may occupy a lot of space, even to the point of being the dominant part of a packet. In order to use bandwidth more efficiently and use less energy in end-to-end communication, solutions have been proposed that allow for very small network layer headers instead.

#### Methodology:

**Header Compression/Translation**:
One of the main approaches to reduce header size in the IoT context is by compressing it. Such technique is based on a stateful approach, utilizing what is usually called a 'context' on the IoT sensor and the gateway for communications between an IoT device and a server placed somewhere in the Internet - from the edge to the cloud.

The role of the 'context' is to provide a way to 'compress' the original IP header into a smaller one, using shorter address information and/or dropping some field(s); the context here serves as a kind of dictionary.

**Separate device from locator identifier**:
Approaches that can offer customized address length that is adequate for use in such constrained domains are preferred. Using different namespaces for the 'device identifier' and the 'routing' or 'locator identifier' is one such approach.

#### Examples

**Header Compression/Translation**:
Considering one base station is supposed to serve hundreds of user devices, maximizing the effectiveness for specific spectrum directly improves user quality of experience. To achieve the optimal utilization of the spectrum resource in the wireless area, the RObust Header Compression (ROHC) {{?RFC5795}} mechanism, which has been widely adopted in cellar network like WCDMA, LTE, and 5G, utilizes header compression to shrink existing IPv6 headers onto shorter ones.

Similarly, header compression techniques for IPv6 over Low-Power Wireless Personal Area Networks (6LoWPAN) have been around for several years now, constituting a main example of using the notion of a 'shared context' in order to reduce the size of the network layer header ({{?RFC6282}}, {{?RFC7400}}, {{ITU9959}}). More recently, other compression solution have been proposed for Low Power Wide Area Networks (LPWAN - {{?RFC8376}}), but they basically rely on the same 'context' approach ({{?RFC8724}}).

Also, constraints coming from either devices or carrier links would lead to mixed scenarios and compound requirements for extraordinary header compression. For native IPv6 communications on DECT ULE and MS/TP Networks {{?RFC6282}}, dedicated compression mechanisms are specified in {{?RFC8105}} and {{?RFC8163}}, while the transmission of IPv6 packets over NFC and PLC, specifications are being developed in {{?I-D.ietf-6lo-nfc}} and {{?I-D.ietf-6lo-plc}}.

**Separate device from locator identifier**:
Solutions such as proposed in {{EIBP}} and {{I-D.ietf-lisp-rfc6830bis}} can utilize a separation of device from locator, where only the latter is used for routing between the different domains using the same technology, therefore enabling the use of shorter addresses in the (possibly constrained) local environment. Device IDs used within such domains are carried as part of the payload by EIBP and hence can be of shorter size suited to the domain, while, for instance, in LISP a flexible address encoding {{?RFC8060}} allows shorter addresses to be supported in the LISP control plane {{?I-D.ietf-lisp-rfc6833bis}}.

### Longer Address Length {#SEC:longer-addr}

#### Description

To address current networking demands, it may be preferred to use variable and longer address lengths. For example in content delivery networks, longer addresses such as URLs are required to fetch content, an approach that Information-Centric Networking (ICN) applied for any data packet sent in the network, using information-based addressing at the network layer. Further, as an approach to address the routing challenges faced in the Internet, structured addresses may be used, avoiding the need for routing protocols.

Further, as an approach to address the routing challenges such as scalability, stability, and the complex interworking between OSPF, eBGP and iBGP faced in the Internet, structured addresses may be used, limiting (or avoiding) the need for routing protocols overall.

#### Methodology

The crucial need for longer address lengths comes from *semantic extensions* to IP addresses, where the extensions themselves do not fit within the length limitation of the IP address. {{SEC:semantic_extensions}} discusses those extensions, divided into those where limitations stemming from the IP address lengths are considered and those where information is either represented through a longer address and/or additional header information.

#### Examples

See {{SEC:semantic_extensions}} for examples of solutions that consider extended address and header information to represent extended semantics that are not limited by the IP address length.

### Summary

{{table:length}} summarizes methodologies and examples towards filling gaps on IP address length extensions.


|                        | Methodology                                   | Examples              |
| ---------------------- | --------------------------------------------- | --------------------- |
| Shorter Address Length | Header compression/translation                | 6LoWPAN, ROHC         |
|                        | Separate device from locator identifier       | EIBP, LISP, ILNP, HIP |
| Longer Address Length  | Same as Semantic Extension {{table:semantic}} |                      |
{: #table:length title="Summary Length Extensions"}



## Identity Extensions

Extensions in this subsection attempt extending the property described in {{SEC:properties:2}}, i.e., 'locator/identifier overload' of the ambiguous address semantic.

From the perspective of Internet users, on the one hand, the implicit identifier semantic results in a privacy issue due to network behavior tracking and association. Despite that IP address assignments may be dynamic, they are nowadays considered as 'personal data' and as such undergoes privacy protection regulations like General Data Protection Regulation ("GDPR" {{GDPR}}). Hence, additional mechanisms are necessary in order to protect end user privacy.

For network regulation of sensitive information, on the other hand, dynamically allocated IP addresses are not sufficient to guarantee device or user identification. As such, different address allocation systems, with stronger identification properties are necessary where security and authentication are at highest priority. Hence, in order to protect information security within a network, additional mechanism are necessary to identify the users or the devices attached to the network.


### Anonymous Address Identity

#### Description

As discussed in {{SEC:properties:2}}, IP addresses reveal both 'network locations' as well as implicit 'identifier' information to both traversed network elements and destination nodes alike. This enables recording, correlation, and profiling of user behaviors and historical network traces, possibly down to individual real user identity. The IETF, e.g., in {{?RFC7258}}, has taken a clear stand on preventing any such pervasive monitoring means by classifying them as an attack on end users' right to be left alone (i.e., privacy). Regulations such as the EU's General Data Protection Regulation (GDPR) classifies, for instance, the 'online identifier' as personal data which must be carefully protected; this includes end users' IP addresses {{GDPR}}.

Even before pervasive monitoring {{?RFC7258}}, IP addresses have been seen as something that some organizational owners of networked system may not want to reveal at the individual level towards any non-member of the same organization. Beyond that, if forwarding is based on semantic extensions, like other fields of the header, extension headers, or any other possible extension, if not adequately protected it may introduce privacy leakage and/or new attack vectors.

#### Methodology:

**Traffic Proxy**:
Detouring the traffic to a trusted proxy is a heuristic solution. Since nodes between trusted proxy and destination (including the destination per se) can only observe the source address of the proxy, the 'identification' of the origin source can thereby be hidden. To obfuscate the nodes between origin and the proxy, the traffic on such route would be encrypted via a key negotiated either in-band or off-band. Considering that all applications' traffic in such route can be seen as a unique flow directed to the same 'unknown' node, i.e., the trusted proxy, eavesdroppers in such route have to make more efforts to correlate user behavior through statistical analysis even if they are capable of identifying the users via their source addresses. The protection lays in the inability to isolate single application specific flows. According to the methodology, such approach is IP version independent and works for both IPv4 and IPv6.

**Source Address Rollover**:
Privacy issues related to address 'identifier' semantic can be mitigated through regular change (beyond the typical 24 hours lease of DHCP).
Due to the semantics of 'identifier' that an IP address carries, such approach promotes to change the source IP address at a certain frequency. Under such methodology, the refresh cycling window may reach to a balance between privacy protection and address update cost. Due to the limited space that IPv4 contains, such approach usually works for IPv6 only.

**Private Address Spaces**:
Their introduction in {{?RFC1918}} foresaw private addresses (assigned to specific address spaces by the IANA) as a means to communicate purely locally, e.g., within an enterprise, by separating private from public IP addresses. Considering that private addresses are never directly reachable from the Internet, hosts adopting private addresses are invisible and thus 'anonymous' for the Internet. Besides, hosts for purely local communication used the latter while hosts requiring public Internet service access would still use public IP addresses.

**Address Translation**:
The aforementioned original intention for using private IP addresses, namely for purely local communication, resulted in a lack of flexibility in changing from local to public Internet access on the basis of what application would require which type of service.

If eventually every end-system in an organization would require some form of public Internet access in addition to local one, an adequate number of public Internet addresses would be required for providing to all end systems. Instead, address translation enables to utilize many private IP addresses within an organization, while only relying on one (or few) public IP addresses for the overall organization.

In principle, address translation can be applied recursively. This can be seen in modern broadband access where Internet providers may rely on carrier-grade address translation for all their broadband customers, who in turn employ address translation of their internal home or office addresses to those (private again) IP addresses assigned to them by their network provider.

Two benefits arise from the use of (private to public IP) address translation, namely (i) the hiding of local end systems at the level of the (address) assigned organization, and (ii) the reduction of public IP addresses necessary for communication across the Internet. While the latter has been seen for long as a driver for address translation, we focus on the first issue in this section, also since we see such privacy benefit as well as objective as still being valid in addressing systems like IPv6 where address scarcity is all but gone {{GNATCATCHER}}.

**Separate device from locator identifier**:
Solutions that make a clear separation between the routing locator and the identifier, can allow for a device ID of any size, which in turn can be encrypted by a network element deployed at the border of routing domain (e.g.,  access/edge router). Both source and end-domain addresses can be encrypted and transported, as in the routing domain, only the routing locator is used.

#### Examples:

**Traffic Proxy**:
Although not initially designed as a traffic proxy approach, a Virtual Private Network (VPN {{VPN}}) is widely utilized for packets origin hiding as a traffic detouring methodology. As it evolved, VPN derivatives like WireGuard {{WireGuard}} have become a mainstream instance for user privacy and security enhancement.

With such methodology in mind, onion routing {{ONION}}, instantiated in the  TOR Project {{TOR}}, achieves high anonymity through traffic hand over via intermediates, before reaching the destination. Since the architecture of TOR requires at least three proxies, none of them is aware of the entire route. Given that the proxies themselves can be deployed all over cyberspace, trust is not the prerequisite if proxies are randomly selected.

In addition, dedicated protocols are also expected to be customized for privacy improvement via traffic proxy. For example, Oblivious DNS over HTTPS (ODoH {{ODoH}}) use a third-party proxy to obscure identifications of user source addresses during DNS over HTTPS (DoH {{?RFC8484}}) resolution. Similarly, Oblivious HTTP {{OHTTP}} involve proxy alike in the HTTP environment.

**Source Address Rollover**:
As for source address rollover, it has been standardized that IP addresses for Internet users should be dynamic and temporary every time they are being generated {{?RFC8981}}. This benefits from the available address space in the case of IPv6, through which address generation or assignment should be unpredictable and stochastic for outside observers.

More radically, {{EPHEMERALv6}} advocates an 'ephemeral address', changing over time,  for each process. Through this, correlating user behaviors conducted by different identifiers (i.e., source address) becomes much harder, if not impossible, if based on the IP packet header alone.

**Private Addresses**:
The use and assignment of private addresses for IPv4 is laid out in {{?RFC1918}}, while unique local addresses (ULAs) in IPv6 {{?RFC4193}} take over the role of private address spaces in IPv4.

**Network Address Translation**:
The translation from one IP address realm into another is laid out in {{?RFC2663}}, using a stateful address binding to translate between the realms, e.g., from a private into a public address space. As outlined in {{?RFC2663}}, basic address translation is usually extended to include port information in the translation process, support bidirectional or simple outbound traffic only. Given address translation can be performed several times in cascade, NATs may exist as part of existing customer premise equipment (CPE), such as a cable or an Ethernet router, with private wired/wireless connectivity, or may be provided in a carrier environment to further translate ISP-internal private addresses to a pool of (assigned) public IP addresses. The latter is often dynamically assigned to CPEs during its bootstrapping.

**Separate device from locator identifier**:
EIBP {{EIBP}} utilizes a structured approach to addressing. It separates the routing ID from the device ID, where only the former is used for routing. As such, the device IDs can be encrypted, protecting the end device identity. Similarly, LISP uses separate namespaces for routing and identification allowing to 'hide' identifiers in encrypted LISP packets that expose only known routing information {{?RFC8061}}.


### Authenticated Address Identity

#### Description

In some scenarios (e.g., corporate networks) it is desirable to being able authenticate IP addresses in order to prevent malicious attackers spoofing IP addresses. This is usually achieved by using a mechanism that allows to prove ownership of the IP address.

#### Methodology

**Self-certified addresses**: This method is usually based on the use of nodes' public/private keys. A node creates its own interface ID (IID) by using a cryptographic hash of its public key (with some additional parameters). Messages are then signed using the nodes' private key. The destination of the message will verify the signature through the information in the IP address. Self-certification has the advantage that no third party or additional security infrastructure is needed. Any node can generate its own address locally and then only the address and the public key are needed to verify the binding between the public key and the address.

**Third party granted addresses**: DHCP (Dynamic Host Configuration Protocol) is widely used to provide IP addresses, however, in its basic form, it does not perform any check and even an unauthorized user without the right to use the network can obtain an IP address. To solve this problem, a trusted third party has to grant access to the network before generating an address (via DHCP or other) that identifies the user. User authentication done securely either based on physical parameters like MAC addresses or based on an explicit login/password mechanism.

#### Examples

<!-- [LI]: May adding some details to the following two paragraphs? -->

**Self-certified Addresses**:
As an example of this methodology serves {{?RFC3972}}, defining IPv6 cryptographically Generated Addresses (CGA). The original specs have been already amended (cf., {{?RFC4581}} and {{?RFC4982}}) in order to support multiple (stronger) cryptographic algorithms.

**Third party granted addresses**:
{{?RFC3118}} defines a DHCP option through which authorization tickets can be generated and newly attached hosts with proper authorization can be automatically configured from an authenticated DHCP server. Solutions exist where separate servers are used for user authentication ({{UA-DHCP}}, {{?RFC4014}}).

### Summary

{{table:identity}}, summarize the methodologies and the examples towards filling the gaps on identity extensions.


|                                | Methodology                             | Examples       |
| ------------------------------ | --------------------------------------- | -------------- |
| Anonymous Address Identity     | Traffic Proxy                           | VPN, TOR, ODoH |
|                                | Source Address Rollover                 | SLAAC          |
|                                | Private Address Spaces                  | ULA            |
|                                | Address Translation                     | NAT            |
|                                | Separate device from locator identifier | EIBP, LISP     |
| Authenticated Address Identity | Self-certified Addresses                | CGA            |
|                                | Third party granted addresses           | DHCP-Option    |
{: #table:identity title="Summary Identity Extensions"}



## Semantic Extensions {#SEC:semantic_extensions}

Extensions in this subsection try extending the property described in {{SEC:properties:3}}, i.e., limited address semantic support.

As explained in {{SEC:properties:2}}, IP addresses carry both locator and interface identification semantic. Some efforts exist that try to separate these semantics either in different address spaces or through different address formats. Beyond just identification, location, and the fixed address size, other efforts extended the semantic through existing or additional header fields (or header options) outside the Internet address.

### Utilizing Extended Address Semantics

#### Description

Several extensions have been developed to extend beyond the limited IPv6 semantics. Those approaches may include to apply structure to the address, utilize specific prefixes, or entirely utilize the IPv6 address for different semantics, while re-encapsulating the original packet to restore the semantics in another part of the network. For instance, structured addresses have the capability to introduce delimiters to identify semantic information in the header, therefore not constraining any semantic by size limitations of the address fields.

We note here that extensions often start out as being proposed as an extended header semantic, while standardization may drive the solution to adopt an approach to accommodate their semantic within the limitations of an IP address. This section does include examples of this kind.

#### Methodology

**Semantic prefixes**:
Semantic prefixes are used to separate the IPv6 address space. Through this, new address families, such as for information-centric networking {{HICN}}, service routing or other semantically rich addressing, can be defined, albeit limited by the prefix length and structure as well as the overall length limitation of the IPv6 address.

**Separate device/resource from locator identifier**:
The option to use separate namespaces for the device address would  offer more freedom for the use of different semantics. For instance, the static binding of IP addresses to servers creates a strong binding between IP addresses and service/resources, which may be a limitation for large Content Distribution networks (CDNs) {{FAYED21}}.

As an extreme form of separating resource from locator identifier, recent engineering approaches, described in {{CLOUDFLARE_SIGCOMM}}, decouple web service (semantics) from the routing address assignments by using virtual hosting capabilities, thereby effectively mapping possibly millions of services onto a single IP address.

**Structured addressing**:
One approach to address the routing challenges faced in the Internet is the use of structured addresses, e.g., to void the need for routing protocols. Benefits of this approach can be significant, with the structured addresses capturing the relative physical or virtual position of routers in the network as well as being variable in length. Key to the approach, however, is that the structured addresses capturing the relative physical or virtual position of routers in the network, or networks in an internetwork may not fit within the fixed and limited IP address length (cf., {{SEC:longer-addr}}). Other structured approaches may be the use of application-specific structured binary components for identification, generalizing URL schema used for HTTP-level communication but utilized at the network level for traffic steering decisions.

**Localized forwarding semantics**:
Layer 2 hardware, such as SDN switches, are limited to the use of specific header fields for forwarding decisions. Hence, devising new localized forwarding mechanisms may be based on re-using differently existing header fields, such as the IPv6 source/destination fields, to achieve the desired forwarding behavior, while encapsulating the original packets in order to be restored at the local forwarding network boundary. Networks in those solutions are limited by the size of the utilized address field, e.g., 256 bits for IPv6, thereby limiting the way such techniques could be used.

#### Examples

**Semantic prefixes**:
Newer approaches to IP anycast suggest the use of service identification in combination with a binding IP address model {{SFCANYCAST}} as a way to allow for metric-based traffic steering decisions; approaches for Service Function Chaining (SFC) {{?RFC7665}} utilize the Network Service Header (NSH) information and packet classification to determine the destination of the next service.

Another example of the usage of different packet header extensions based on IP addressing is Segment Routing. In this case, the source chooses a path and encodes it in the packet header as an ordered list of segments. Segments are encoded using new Routing Extensions Header type, the Segment Routing Header (SRH), which contains the Segment List, similar to what is already specified in {{?RFC2460}}, i.e., a list of segment ID (SID) that dictate the path to follow in the network. Such segment IDs are coded as 128 bit IPv6 addresses {{?RFC8986}}.

Approaches such as {{HICN}} utilize semantic prefixing to allow for ICN forwarding behavior within an IPv6 network. In this case, an HICN name is the hierarchical concatenation of a name prefix and a name suffix, in which the name prefix is encoded as an IPv6 128 bits word and carried in IPv6 header fields, while the name suffix is encoded in transport headers fields such as TCP. However, it is a challenge to determine which IPv6 prefixes should be used as name prefixes. In order to know which IPv6 packets should be interpreted based on an ICN semantic, it is desirable to be able to recognize that an IPv6 prefix is a name prefix, e.g. to define a specific address family (AF_HICN, b0001::/16). This establishment of a specific address family allows the management and control plane to locally configure HICN prefixes and announce them to neighbors for interconnection.

**Separate device from locator identifier**:
EIBP {{EIBP}} separates the routing locator from the device identifier, relaxing therefore any semantic constraints on the device identifier. Similarly, LISP uses a flexible encoding named LISP Canonical Address Format (LCAF {{?RFC8061}}), which allows to associate to routing locators any possible form (and length) of identifier. ILNP {{?RFC6740}} introduces as well a different semantic of IP addresses, while aligning to the IPv6 address format (128 bits). Basically, ILNP introduces a sharper logical separation between the 64 most significant bits and the 64 least significant bits of an IPv6 address. The former being a global locator, while the latter being an identifier that can have different semantics (rather than just being an interface identifier).

**Structured addressing**:
Network topology captures the physical connectivity among devices in the network. There is a structure associated with the topology. Examples are the core-distribution-access router structure commonly used in enterprise networks and clos topologies that are used to provide multiple connections between Top of Rack (ToR) devices and multiple layers of spine devices. Internet service providers use a tier structure that defines their business relationships. A clear structure of connected networks can be noticed in the Internet. EIBP {{EIBP}} proposes to leverage the physical structure (or a virtual structure overlaid on the physical structure) to auto assign addresses to  routers in a network or networks in an internetwork to capture their relative position in the physical/virtual topology. EIBP proposes to administratively identify routers/networks  with a tier value based on the structure.

**Localized forwarding semantics**:
Approaches such as those outlined in {{REED}} suggest using a novel forwarding semantic based on path information carried in the packet itself, said path information consists in a fixed size bitfield (see {{REED}} for more information on how to represent the path information in said bitfield). In order to utilize existing, e.g., SDN-based, forwarding switches, the direct use of the IPv6 source/destination address is suggested for building appropriate match-action rules (over the suitable binary information representing the local output ports), while preserving the original IPv6 information in the encapsulated packet. As mentioned above, such use of the existing IPv6 address fields limits the size of the network to a maximum of 256 bits (therefore paths in the network over which such packets can be forwarded). {{ICNIP}}, however, goes a step further by suggesting to use the local forwarding as direct network layer mechanism, removing the IP packet and only leaving the transport/application layer, with the path identifier constituting the network-level identifier albeit limited by using the existing IP header for backward compatibility reasons (the next section outlines the removal of this limitation).

### Utilizing Existing or Extended Header Semantics

#### Description:

While the former sub-section explored extended address semantic, thereby limiting any such extended semantic with that of the existing IPv6 semantic and length, additional semantics may also be placed into the header of the packet or the packet itself, utilized for the forwarding decision to the appropriate endpoint according to the extended semantic.

Reasons for embedding such new semantics may be related to traffic engineering since it has long been shown that the IP address itself is not enough to steer traffic properly since the IP address itself is not semantically rich enough to adequately describe the forwarding decision to be taken in the network, not only impacting WHERE the packet will need to go but also HOW it will need to be sent.

#### Methodology:

**In-Header extensions**:
One way to add additional semantics besides the address fields is to use other fields already present in the header.

**Headers option extensions**:
Another mechanism to add additional semantics is to actually add additional fields, e.g., through Header Options in IPv4 or through Extension Headers in IPv6.

**Re-encapsulation extension**:
A more radical approach for additional semantics is the use of a completely new header that is designed so to carry the desired semantics in an efficient manner (often as a shim header).

**Structured addressing**:
Similar to the methodology that structures addresses within the limitations of the IPv6 address length, outlined in the previous sub-sections, structured addressing can also be applied within existing or extended header semantics, e.g., utilizing a dedicated (extension) header to carry the structured address information.

**Localized forwarding semantics**:
This set of solutions applies capabilities of newer (programmable) forwarding technology, such as {{P4}}, to utilize any header information for a localized forwarding decision. This removes any limitation to use existing header or address information for embedding a new address semantic into the transferred packet.

#### Examples:

**In-Header extensions:**
In order to allow additional semantic with respect to the pure Internet addressing, the original design of IPv4 included the field 'Type of Service' {{?RFC2474}}, while IPv6 introduced the 'Flow label' and the 'Traffic Class' {{?RFC8200}}. In a certain way, those fields can be considered 'semantic extensions' of IP addresses, and they are 'in-header' because natively present in the IP header (differently from options and extension headers). However, they proved not to be sufficient. Very often a variety of network operation are performed on the well-known 5-tuple (source and destination addresses; source and destination port number; and protocol number). In some contexts all of the above mentioned fields are used in order to have a very fine grained solution ({{?RFC8939}}).

**Headers option extensions:**
Header options have been largely under-exploited in IPv4. However, the introduction of the more efficient extension header model in IPv6 along with technology progress made the use of header extensions more widespread in IPv6. Segment Routing re-introduced the possibility to add path semantic to the packet by encoding a loosely defined source routing ({{?RFC8402}}). Similarly, in the aim to overcome the inherent shortcoming of the multi-homing in the IP context, SHIM6 ({{?RFC5533}}) also proposed the use of an extension header able to carry multi-homing information which cannot be accommodated natively in the IPv6 header.

To serve a moving endpoint, mechanisms like Mobile IPv6 {{?RFC6275}} are used for maintaining connection continuity by a dedicated IPv6 extension header. In such case, the IP address of the home agent in Mobile IPv6 is basically an identification of the on-going communication. In order to go beyond the interface identification model of IP, the Host Identity Protocol (HIP) tries to introduce an identification layer to provide (as the name says) host identification. The architecture here relies on the use of another type of extension header {{?RFC7401}}.

**Re-encapsulation extension:**
Differently from the previous approach, re-encapsulation prepends complete new IP headers to the original packet introducing a completely custom shim header between the outer and inner header. This is the case for LISP, adding a LISP specific header right after an IP+UDP header ({{?I-D.ietf-lisp-rfc6830bis}}). A similar design is used by VxLAN ({{?RFC7348}}) and GENEVE ({{?RFC8926}}), even if they are designed for a data center context. IP packets can also be wrapped with headers using more generic and semantically rich names, for instance with ICN {{ICNIP}}.

**Structured addressing:**
Solutions such as those described in the previous sub-section, e.g., EIBP {{EIBP}}, can provide structured addresses that are not limited to the IPv6 address length but instead carry the information in an extension header to remove such limitation.

Also Information-Centric Networking (ICN) naming approaches usually introduce structures in the (information) names without limiting themselves to the IP address length; more so, ICN proposes its own header format and therefore radically breaks with not only IP addressing semantic but the format of the packet header overall. For this, approaches such as those described in {{?RFC8609}} define a TLV-based binary application component structure that is carried as a 'name' part of the CCN messages. Such a name is a hierarchical structure for identifying and locating a data object, which contains a sequence of name components. Names are coded based on 2-level nested Type-Length-Value (TLV) encodings, where the name-type field in the outer TLV indicates this is a name, while the inner TLVs are name components including a generic name component, an implicit SHA-256 digest component and a SHA-256 digest of Interest parameters. For textual representation, URIs are normally used to represent names, as defined in {{?RFC3986}}.

In geographic addressing, position based routing protocols use the geographic location of nodes as their addresses, and packets are forwarded when possible in a greedy manner towards the destination. For this purpose, the packet header includes a field coding the geographic coordinates (x, y, z) of the destination node, as defined in {{?RFC2009}}. Some proposals also rely on extra fields in the packet header to code the distance towards the destination, in which case only the geographic coordinates of neighbors are exchanged. This way the location of the destination is protected even if routing packets are eavesdropped.

**Localized forwarding semantics:**
Unlike the original suggestion in {{REED}} to use existing SDN switches, the proliferation of P4 {{P4}} opens up the possibility to utilize a locally limited address semantic, e.g., expressed through the path identifier, as an entirely new header (including its new address) with an encapsulation of the IP packet for E2E delivery (including further delivery outside the localized forwarding network or positioning the limited address semantic directly as the network address semantic for the packet, i.e., removing any IP packet encapsulation from the forwarded packet, as done in {{ICNIP}}. Removing the IPv6 address size limitation by not utilizing the existing IP header for the forwarding decision also allows for extensible length approaches for building the path identifier with the potential for increasing the supported network size. On the downside, this approach requires to encapsulate the original IP packet header for communication beyond the local domain in which the new header is being used, such as discussed in the previous point above on 're-encapsulation extension'.

### Summary

{{table:semantic}}, summarize the methodologies and the examples towards filling the gaps on semantic extensions.

|                                                 | Methodology                             | Examples              |
| ----------------------------------------------- | --------------------------------------- | --------------------- |
| Utilizing Extended Address Semantics            | Semantic prefixes                       | HICN                  |
|                                                 | Separate device from locator identifier | EIBP, ILNP, LISP, HIP |
|                                                 | Structured addressing                   | EIBP, ILNP            |
|                                                 | Localized forwarding semantics          | REED                  |
| Utilizing Existing or Extended Header Semantics | In-Header extensions                    | DetNet                |
|                                                 | Headers option extensions               | SHIM6, SRv6, HIP      |
|                                                 | Re-encapsulation extension              | VxLAN, ICNIP          |
|                                                 | Structured addressing                   | EIBP                  |
|                                                 | Localized forwarding semantics          | REED                  |
{: #table:semantic title="Summary Semantic Extensions"}


# Overview of Approaches to Extend Internet Addressing {#SEC:overview}
<!-- NOTE: check that all proper checkmarks are placed! -->

The following {{table:extension}} describes the objectives of the extensions discussed in this memo with respect to the properties of Internet addressing ({{SEC:properties}}}. As summarized, extensions may aim to extend one property of the Internet addressing, or extend other properties at the same time.

|                | Length Extension | Identity Extension | Semantic Extension |
| -------------- | ---------------- | ------------------ | ------------------ |
| 6LoWPAN        | x                |                    |                    |
| ROHC           | x                |                    |                    |
| TOR            |                  | x                  |                    |
| ODoH           |                  | x                  |                    |
| SLAAC          |                  | x                  |                    |
| CGA            |                  | x                  | x                  |
| NAT            | x                | x                  |                    |
| HICN           |                  | x                  | x                  |
| ICNIP          | x                | x                  | x                  |
| CCNx names     | x                | x                  | x                  |
| EIBP           | x                | x                  | x                  |
| Geo addressing | x                |                    | x                  |
| REED           | x (with P4)      |                    | x                  |
| DetNet         |                  | x                  |                    |
| Mobile IP      |                  |                    | x                  |
| SHIM6          |                  |                    | x                  |
| SRv6           |                  |                    | x                  |
| HIP            |                  | x                  | x                  |
| VxLAN          |                  | x                  | x                  |
| LISP           |                  | x                  | x                  |
| SFC            |                  | x                  | x                  |
{: #table:extension title="Relationship between Extensions and Internet Addressing"}




# Issues in Extensions to Internet Addressing {#SEC:issues}

While the extensions to the original Internet properties, discussed in {{SEC:extensions}}, demonstrate the benefits of more flexibility in addressing, they also bring with them a number of issues, which are discussed in the following section. To this end, the problems hereafter outlined link to the approaches to extensions summarized in {{SEC:overview}}.

## Limiting Address Semantics {#SEC:issues:limiting}

Many approaches changing the semantics of communication, e.g., through separating host identification from network node identification {{?RFC7401}}, separating the device identifier from the routing locator ({{EIBP}}, {{I-D.ietf-lisp-introduction}}), or through identifying content and services directly {{HICN}}, are limited by the existing packet size and semantic constraints of IPv6, e.g., in the form of its source and destination network addresses.

While approaches such as {{ICNIP}} may override the addressing semantics, e.g., by replacing IPv6 source and destination information with path identification, a possible unawareness of endpoints still requires the carrying of other address information as part of the payload.

Also, the expressible service or content semantic may be limited, as in {{HICN}} or the size of supported networks {{REED}} due to relying on the limited bit positions usable in IPv6 addresses.


## Complexity and Efficiency {#SEC:issues:efficiency}

A crucial issue is the additional complexity introduced for realizing the additional addressing semantics. This is particularly an issue since we see those additional semantics particularly at the edge of the Internet, utilizing the existing addressing semantic of the Internet to interconnect the domains that require those additional semantics.

Furthermore, any additional complexity often comes with an efficiency and cost penalty, particularly at the edge of the network, where resource constraints may play a significant role. Compression processes, taking {{ROHC}} as an example, require additional resources both for the sender generating the compressed header but also the gateway linking to the general Internet by re-establishing the full IP header.

Conversely, the performance requirements of core networks, in terms of packet processing speed, makes the accommodation of extensions to addressing often prohibitive. This is not only due to the necessary extra processing that is specific to the extension, but also due to the complexity that will need to be managed in doing so at significantly higher speeds than at the edge of the network. The observations on the dropping of packets with IPv6 extension headers in the real world is (partially) due to such a implementation complexity {{?RFC7872}}.

Another example for lowering the efficiency of packet forwarding is the routing in systems like TOR {{TOR}}. As detailed before, traffic in TOR, for anonymity purposes, should be handed over by at least three intermediates before reaching the destination. Frequent relaying enhances the privacy, however, because such kind of solutions are implemented at application level, they come at the cost of lower communication efficiency. May be a different privacy enhanced address semantic would enable efficient implementation of TOR-like solutions at network layer.

### Repetitive encapsulation

Repetitive encapsulation is an issue since it bloats the packets size due to additional encapsulation headers. Addressing proposals such as those in {{ICNIP}} utilize path identification within an alternative forwarding architecture that acts upon the provided path identification. However, due to the limitation of existing flow-based architectures with respect to the supported header structures (in the form of IPv4 or IPv6 headers), the new routing semantics are being inserted into the existing header structure, while repeating the original, sender-generated header structure, in the payload of the packet as it traverses the local domain, effectively doubling the per-packet header overhead.

The problem is also present in a number of solutions tackling different issues, e.g., mobility {{I-D.ietf-lisp-mn}}, DC networking ({{?RFC8926}}, {{?RFC7348}}, {{I-D.ietf-intarea-gue}}), traffic engineering {{?RFC8986}}, and privacy ({{TOR}}, {{SPHINX}}). Certainly these solutions are able to avoid other issues, like path lengthening or privacy issues, as described before, but they come at the price of multiple encapsulations that reduce the effective payload. This, not only hampers efficiency in terms of header-to-payload ratio, but also introduces 'encapsulation points', which in turn add complexity to the (often edge) network as well as fragility due to the addition of possible failure points; this aspect is discussed in further details in {{SEC:issues:fragility}}.

### Compounding issues with header compression

IP header overhead requires header compression in constrained environments, such as wireless sensor networks and IoT in general. Together with fragmentation, both tasks constitute significant energy consumption, as shown in {{HEADER_COMP_ISSUES1}}, negatively impacting resource limited devices that often rely on battery for operation. Further, the reliance on the compression/decompression points creates a dependence on such gateways, which may be a problem for intermittent scenarios.

According to the implementation of *contiki-ng* {{CONTIKI}}, an example of operating system for IoT devices, the source codes for 6LowPan requires at least 600Kb to include a header compression process. In certain use cases, such requirement can be an obstacle for extremely constrained devices, especially for the RAM and energy consumption.


### Introducing Path Stretch

Mobile IP {{?RFC6275}}, which was designed for connection continuity in the face of moving endpoints, is a typical case for path stretch. Since traffic must follow a triangular route before arriving at the destination, such detour routing inevitably impacts transmission efficiency as well as latency.

### Complicating Traffic Engineering {#SEC:issues:traffic}

While many extensions to the original IP address semantic target to enrich the decisions that can be taken to steer traffic, according to requirements like QoS, mobility, chaining, compute/network metrics, flow treatment, path usage, etc., the realization of the mechanisms as individual solutions likely complicates the original goal of traffic engineering when individual solutions are being used in combination. Ultimately, this may even prevent the combined use of more than one mechanism and/or policy with a need to identify and prevent incompatibilities of mechanisms. Key here is not the issue arising from using conflicting traffic engineering policies, rather conflicting realizations of policies that may well generally work well alongside ({{ROBUSTSDN}}, {{TRANSACTIONSDN}}).

This not only increases fragility, as discussed separately in {{SEC:issues:fragility}}, but also requires careful planning of which mechanisms to use and in which combination, likely needing human-in-the-loop approaches alongside possible automation approaches for the individual solutions.

## Security {#SEC:issues:security}

The properties described in {{SEC:properties}} have, obviously, also consequences in terms of security and privacy related issues, as already mentioned in other parts of this document.

For instance, in the effort of being somehow backward compatible, HIP {{?RFC7401}} uses a 128-bit Host Identity, which may be not sufficiently  cryptographically strong in the future because of the limited size (future computational power may erode 128-bit security). Similarly, CGA {{?RFC3972}} also aligns to the 128-bit limit, but may use only 59 bits of them, hence, the packet signature may not be sufficiently robust to attacks {{?I-D.rafiee-6man-cga-attack}}.

IP addresses, even temporary ones meant to protect privacy, have been long recognized as a 'Personal Identification Information' that allows even to geolocate the communicating endpoints {{?RFC8280}}. The use of temporary addresses provides sufficient privacy protection only if the renewal rate is high {{EPHEMERALv6}}. However, this causes additional issues, like the large overhead due to the Duplicate Address Detection, the impact on the Neighbor Discovery mechanism, in particular the cache, which can even lead to communication disruption. With such drawbacks, the extensions may even lead to defeat the target, actually lowering security rather than increasing it.

The introduction of alternative addressing semantics has also been used to help in (D)DoS attacks mitigation. This leverages on changing the service identification model so to avoid topological information exposure, making the potential disruptions likely remain limited {{ADDRLESS}}. However, this increased robustness to DDoS comes at the price of important communication setup latency and fragility, as discussed next.

## Fragility {#SEC:issues:fragility}

From the extensions discussed in {{SEC:extensions}}, it is evident that having alternative or additional address semantic and formats available for making routing as well as forwarding decisions dependent on these, is common place in the Internet. This, however, adds many extension-specific translation/adaptation points, mapping the semantic and format in one context into what is meaningful in another context, but also, more importantly, creating a dependency towards an additional component, often without explicit exposure to the endpoints that originally intended to communicate.

For instance, the re-writing of IP addresses to facilitate the use of private address spaces throughout the public Internet, realized through network address translators (NATs), conflicts with the end-to-end nature of communication between two endpoints. Additional (flow) state is required at the NAT middlebox to smoothly allow communication, which in turn creates a dependency between the NAT and the end-to-end communication between those endpoints, thus increasing the fragility of the communication relation.

A similar situation arises when supporting constrained environments through a header compression mechanism, adding the need for, e.g., a ROHC {{?RFC5795}} element in the communication path, with communication-related compression state being held outside the communicating endpoints. Failure will introduce some inefficiencies due to context regeneration, which  may affects the communicating endpoints, increasing fragility of the system overall.

Such translation/adaptation between semantic extensions to the original 'semantic' of an IP address is generally not avoidable when accommodating more than a single universal semantic. However, the solution-specific nature of every single extension is likely to noticeably increase the fragility of the overall system, since individual extensions will need to interact with other extensions that may be deployed in parallel, but were not designed taking into account such deployment scenario (cf., {{?I-D.ietf-intarea-tunnels}}). Considering that extensions to traditional per-hop-behavior (based on IP addresses) can essentially be realized over almost 'any' packet field, the possible number of conflicting behaviors or diverging interpretation of the semantic and/or content of such fields, among different extensions, may soon become an issue, requiring careful testing and delineation at the boundaries of the network within which the specific extension has been realized.

# Summary of issues {#SEC:overview-issue}

{{table:issue}}, derived from {{SEC:issues}}, summarizes the issues related to each extension. While each extension involves at least one issue, some others, like ICNIP, may create several issues at the same time.

<!-- Below are for table drawing

1. Limiting Address Semantics
2. Complexity and Efficiency
   1. Repetitive encapsulation
   2. Compounding issues with header compression
   3. Introducing Path Stretch
   4. Complicating Traffic Engineering
3. Security
4. Fragility

 -->


|                | Limiting Address Semantics | Complexity and Efficiency | Security | Fragility |
| -------------- | -------------------------- | ------------------------- | -------- | --------- |
| 6LoWPAN        |                            | x                         |          | x         |
| ROHC           |                            | x                         |          | x         |
| TOR            |                            | x                         |          | x         |
| ODoH           |                            | x                         |          |           |
| SLAAC          |                            | x                         |          |           |
| CGA            | x                          |                           | x        |           |
| NAT            |                            | x                         |          | x         |
| HICN           | x                          |                           |          |           |
| ICNIP          | x                          | x                         |          |           |
| CCNx name      | x                          |                           |          |           |
| EIBP           | x                          | x                         |          |           |
| Geo addressing | x                          |                           |          | x         |
| REED           | x                          |                           |          |           |
| DetNet         |                            | x                         |          |           |
| Mobile IP      |                            | x                         |          | x         |
| SHIM6          |                            |                           |          | x         |
| SRv6           |                            |                           |          | x         |
| HIP            |                            |                           | x        | x         |
| VxLAN          |                            | x                         |          |           |
| LISP           | x                          | x                         |          |           |
| SFC            |                            | x                         |          | x         |
{: #table:issue title="Issues in Extensions to Internet Addressing"}


# Conclusions {#SEC:conclusion}

The examples of extensions discussed in {{SEC:extensions}} to the original Internet addressing scheme show that extensibility beyond the original model (and its underlying per-hop behavior) is a desired capability for networking technologies and has been so for a long time. Generally, we can observe that those extensions are driven by the requirements of stakeholders, expecting a desirable extended functionality from the introduction of the specific extension. If interoperability is required, those extensions require standardization of possibly new fields, new semantics as well as (network and/or end system) operations alike.

The issues we identified in this document with the extension-specific solution approach, point to the need for a discussion on Internet addressing, as formulated in the companion document {{?I-D.jia-intarea-scenarios-problems-addressing}} that formalizes the problem statement through scenarios that highlight the shortcomings of the Internet addressing model.

It is our conclusion that the existence of the many extensions to the original Internet addressing is clear evidence for gaps that have been identified over time by the wider Internet community, each of which come with a raft of issues that we need to deal with daily: We believe that it is time to develop an architectural but more importantly a sustainable approach to make Internet addressing extensible in order to capture the many new use cases that will still be identified for the Internet to come. Any inaction on our side in that regard will only compound the issues identified, eventually hampering the future Internet's readiness for those new uses.


# Security Considerations {#SEC:sec}

The present memo does not introduce any new technology and/or mechanism and as such does not introduce any security threat to the TCP/IP protocol suite.

As an additional note, and as discussed in this document, security and privacy aspects were not considered as part of the key properties for Internet addressing, which led to the introduction of a number of extensions intending to fix those gaps. The analysis presented in this memo (non-exhaustively) shows those issues are either solved in an ad-hoc manner at application level, or at transport layer, while at network level only few extensions tackling specific aspects exist, albeit often with limitations due to the adherence to the Internet addressing model and its properties.


# IANA Considerations {#SEC:iana}

This document does not include any IANA request.


--- back


<!--

# Change Log
**NOTES**: Please remove this section prior to publication of a final version of this document.

-->


# Acknowledgments
{:numbered="false"}

Thanks to Carsten Bormann for useful conversations.
<!-- [LI]: In revision 2 we ca add the panelists :-) -->

