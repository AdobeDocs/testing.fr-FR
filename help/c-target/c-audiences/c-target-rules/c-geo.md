---
description: Target users based on their geographical location, including their country,
  state/province, city, zip/postal code, DMA, or mobile carrier.
keywords: targeting;a4t;geo;geotargeting;geotargeting accuracy;country;state;city;zip
  code;dma;mobile carrier;city codes;region codes;country codes;metro codes;profile
  scripts;geotargeting profile scripts;geotargeting mobile
seo-description: Target users based on their geographical location, including their
  country, state/province, city, zip/postal code, DMA, or mobile carrier.
seo-title: Geo
solution: Target,Analytics
title: Geo
topic: Reports and analytics
uuid: d30cda0e-016e-4391-95b7-ff3b55e06bf0
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Geo{#geo}

Target users based on their geographical location, including their country, state/province, city, zip/postal code, DMA, or mobile carrier.

**Creating Audiences (9:58)**

This video includes information about using audience categories.

* Create audiences
* Define audience categories

>[!VIDEO](https://www.youtube.com/watch?v=wV9lVTSOxMk)

Geo location parameters allow you to target activities and experiences based on your visitors' geography. You can include or exclude visitors based on their country, state/province, city, zip/postal code, DMA, or mobile carrier. This data is sent with each mbox request and is based on the visitor's IP address. Select these parameters just like any targeting values.

## Create an Audience with Geo Targeting {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. In the [!DNL Target] interface, click **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Name the audience.
1. Click **[!UICONTROL Add Rule]** > **[!UICONTROL Geo]**.

   ![](assets/target_geo.png)

1. Click **[!UICONTROL Select]**, then select one of the following options:

   * Country
   * State
   * City
   * Zip Code
   * Latitude
   * Longitude
   * DMA
   * Mobile Carrier
   A visitor's IP address is passed with an mbox request, once per visit (session), to resolve geo targeting parameters for that visitor.

   For Mobile Carrier, [!DNL Target] uses the IP address registration data (who owns the block of IP addresses) to determine the appropriate mobile carrier using [Mobile Country Codes (MCC) and Mobile Network Codes MNC)](https://www.mcc-mnc.com).

1. (Optional) Click **[!UICONTROL Add Rule]** and set up additional rules for the audience.
1. Click **[!UICONTROL Save]**.

## Accuracy {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

The accuracy of geo targeting depends on several factors. WiFi connections are more accurate than cellular networks. When the visitor is using a cellular data connection, the accuracy of the geo-lookup can be affected by location, the provider's data relationship with deviceatlas, and other factors. Cell tower-based network connections might be less accurate than wired or WiFi connections. Also, a visitor's IP address might be mapped to his or her ISP location, which might not be the same as the visitor's actual location. Some mobile geo-location issues can be solved using the [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

The following table shows the accuracy of IP-based geographical information from [DigitalEnvoy](https://www.digitalelement.com/solutions/) for wired or WiFi Internet connections. DigitalEnvoy provides the most accurate data in the industry. Global accuracy is more than 99.9 percent at the country level and is up to 97 percent accurate at a city level. Accuracy information does not apply to cell tower-based networks.

<table id="table_9F4BD43BF51A400E81D43876D4310820"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Country </th> 
   <th colname="col2" class="entry"> State </th> 
   <th colname="col3" class="entry"> City </th> 
   <th colname="col4" class="entry"> Region </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>US </p> </td> 
   <td colname="col2"> <p>99.99% </p> </td> 
   <td colname="col3"> <p>96% </p> </td> 
   <td colname="col4"> <p>94% </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Canada </p> </td> 
   <td colname="col2"> <p>99.99% </p> </td> 
   <td colname="col3"> <p>96% </p> </td> 
   <td colname="col4"> <p>94% </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Europe </p> </td> 
   <td colname="col2"> <p>99.99% </p> </td> 
   <td colname="col3"> <p> </p> </td> 
   <td colname="col4"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>UK </p> </td> 
   <td colname="col2"> <p>99.99% </p> </td> 
   <td colname="col3"> <p> </p> </td> 
   <td colname="col4"> <p>87% </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Germany </p> </td> 
   <td colname="col2"> <p>99.99% </p> </td> 
   <td colname="col3"> <p>95% </p> </td> 
   <td colname="col4"> <p>93% </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scandinavia </p> </td> 
   <td colname="col2"> <p>99% </p> </td> 
   <td colname="col3"> <p>Low 90s </p> </td> 
   <td colname="col4"> <p>Mid 80s </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spain </p> </td> 
   <td colname="col2"> <p>99.99% </p> </td> 
   <td colname="col3"> <p>Around 90% </p> </td> 
   <td colname="col4"> <p>Mid to high 90s </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Asia </p> </td> 
   <td colname="col2"> <p>99% </p> </td> 
   <td colname="col3"> <p>Mid 90s </p> </td> 
   <td colname="col4"> <p>Low 90s </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Japan </p> </td> 
   <td colname="col2"> <p>99.99% </p> </td> 
   <td colname="col3"> <p>Mid 90s </p> </td> 
   <td colname="col4"> <p>Low 90s </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Australia </p> </td> 
   <td colname="col2"> <p>99.99% </p> </td> 
   <td colname="col3"> <p>94% </p> </td> 
   <td colname="col4"> <p>91% </p> </td> 
  </tr> 
 </tbody> 
</table>

## Using Geo-Targeting in Profile Scripts {#section_92C93138542C4A94997E3F4BE3F5DA28}

You can use geo information for profile scripts.

For example, use:

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`

So, you can write a target expression called "From North America" with the following code:

`return profile.geolocation.country == 'united states' || profile.geolocation.country == 'canada' || profile.geolocation.country == 'mexico';`

## Using Geo-Targeting Values as Tokens {#section_E7F7FDF62C3B4934A6565D04B24655F6}

You can now use `profile.geolocation` values directly as tokens in offers, plugins, and so forth.

For example, use:

* `${profile.geolocation.country}`
* `${profile.geolocation.state}`
* `${profile.geolocation.city}`
* `${profile.geolocation.zip}`
* `${profile.geolocation.dma}`
* `${profile.geolocation.domainName}`
* `${profile.geolocation.ispName}`
* `${profile.geolocation.connectionSpeed}`
* `${profile.geolocation.mobileCarrier}`
* `${profile.geolocation.latitude}`
* `${profile.geolocation.longitude}`

## Geotargeting FAQ {#section_DD308A53AF0F48FA8C81423580561FE7}

**How do I specify latitude and longitude?**

* The value for latitude/longitude should be a numeric value in degrees.
* The value for latitude/longitude can have a maximum precision of five decimal places.
* The value for latitude should be between -90 and 90.
* The value for longitude should be between -180 and 180.

**How does geo targeting work for mobile devices?**

The vast majority of mobile device users access content via WiFi, which means Target's IP-based geo targeting is as accurate as on a desktop. Cell tower-based connections might be less accurate because the visitor's IP address is based on the tower where the signal is being picked up. Some mobile geo-location issues can be solved using the [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

**How does geo feature handle visitors from AOL?**

Due to the way AOL proxies its traffic, we can only target them at a country level. For example, a campaign targeted to France will successfully target AOL users in France. But a campaign targeted to Paris will not successfully target AOL users in Paris. If your intent is to specifically target AOL users, you can set the region field to "aol." In fact, you can target US AOL users by specifying two targeting conditions: country exactly matches "united states" and region exactly matches "aol."

**What location granularity does geo targeting provide?**

* Country - global
* State/province/region - global
* City - global
* Zip/postal code - US, Germany, Canada
* DMA/ITV (UK) - US, UK
* Mobile carrier - global

**How can I test my campaigns as if I'm a user coming from a different location?**

You can override your IP address with an IP address from a different location and use the `mboxOverride.browserIp url` parameter. So if your company is in the UK, but your global campaign targets visitors in Aukland, New Zealand, use this style of URL assuming that `60.234.0.39` is an IP address in Auckland:

`https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

You'll need to clear your cookies before doing this.

**How are territories, such as Puerto Rico and Hong Kong, mapped into the geo-targeting structure?**

Puerto Rico, Hong Kong, and other territories are treated as separate "Country" values.
