---
description: Adobe Target has enabled processes and settings that allow you to use
  Target in compliance with applicable data privacy laws.
keywords: Overview and Reference
seo-description: Adobe Target has enabled processes and settings that allow you to
  use Target in compliance with applicable data privacy laws.
seo-title: Privacy
solution: Target
subtopic: Getting Started
title: Privacy
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Privacy{#privacy}

Adobe Target has enabled processes and settings that allow you to use Target in compliance with applicable data privacy laws.

## Collection of IP Address {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

The IP address of a visitor to your website is transmitted to an Adobe Data Processing Center (DPC). Depending on the network configuration for the visitor, the IP address does not necessarily represent the IP address of the visitor’s computer. For example, the IP address could be the external IP address of a Network Address Translation (NAT) firewall, HTTP proxy, or Internet gateway. Target doesn't store any IP addresses of the user or any Personally Identifiable Information (PII). IP addresses are used only by Target for the duration of the session (in-memory, never persisted).

## Replacement of Last Octet of the IP Address {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe has developed a new “privacy by design” setting that can be enabled by Adobe Client Care for Adobe Target. When this setting is enabled, the last octet (the last portion) of the IP address is immediately hidden when the IP address is collected by Adobe. This anonymization is performed prior to any processing of the IP address, including before an optional geo-lookup of the IP address.

When this feature is enabled, the IP address is made sufficiently anonymous so it is no longer identifiable as personal information. As a result, Adobe Target can be used in compliance with data privacy laws in countries that do not permit the collection of personal information. Obtaining city-level information will likely be significantly impacted by the obfuscation of the IP address. Obtaining region- and country-level information should only be slightly impacted.

There is also a setting available to obfuscate the entire IP address.

Contact Adobe Client Care to enable the IP obfuscation feature.

## GeoSegmentation {#section_BB69F96559BD44BDA4177537C4A5345A}

If you enable the replacement of the last octet of the IP address, the remaining values of the IP address can be analyzed using reports in Adobe Target. If the last octet of the IP address has not been obfuscated, then the full IP address can be analyzed in Adobe Target. You can use the GeoSegmentation feature to map out visitor location by geographic area. GeoSegmentation data is granular only to the city level or zip code level, and not to the individual level.

If IP addresses are completely obfuscated, GeoSegmentation and geo targeting is not available.

## Opt-Out Link {#section_E7A62B7B99C94B3A806CB262D16E27FC}

You can add an opt-out link to your sites to enable visitors to opt-out of all counting and content delivery.

1. Add the following link to your site:

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`
1. Replace the `clientcode` text with your client code, and add the text or image to be linked to the opt-out URL.

Any visitor who clicks this link is not included in any mbox requests called from their browsing sessions until they delete their cookies, or for two years, whichever comes first. This works by setting a cookie for the visitor called `disableClient` in the `clientcode.tt.omtrdc.net` domain.

Even if you use a first-party cookie implementation, the provided opt-out is set via a 3rd-party cookie. If the client is using a first-party cookie only, Target checks whether an opt-out cookie is set.
