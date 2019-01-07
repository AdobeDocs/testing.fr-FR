---
description: null
seo-description: null
seo-title: Templates
solution: Target
title: Templates
topic: Appendices,Site search and merchandising
uuid: c537a538-d713-49e2-84ed-5c155cb05c52
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b33d6ee6c7ba7161294074b9210d1ad4e95559ae

---


# Templates{#templates}

## Templates {#concept_A5CFB6BD805D49459A96219AF1B17842}

## Presentation template tags {#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64}

A list of site search/merchandising tags and attributes for presentation templates.

<!-- 

r_presentation_template_tags.xml

 -->

A presentation template is an HTML file that includes presentation template tags that site search/merchandising defines. These tags indicate how the search results that customers see are formatted.

See [About Templates](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

You can select from the following presentation tag groups:

* [Declarations](../c-appendices/c-templates.md#section_82C5CA734D2941EB858FEFE3B695D2EC)
* [Results](../c-appendices/c-templates.md#section_06F249C9F6AE4B0F8C32117E19DCC905)
* [Facets](../c-appendices/c-templates.md#section_EA4C5678D5864B89BAB4D0DFE62A4624)
* [Breadcrumb](../c-appendices/c-templates.md#section_9B39B71FA6EC49FA8D88AD8A3BA987F7)
* [Menus](../c-appendices/c-templates.md#section_1D489ADF041F4351A66E5D5742125CA8)
* [Pagenav](../c-appendices/c-templates.md#section_2EE397635C514BBC8D668278EA314F35)
* [Recent Searches](../c-appendices/c-templates.md#section_8CD907521F584257B475595B01A5964B)
* [Did You Mean](../c-appendices/c-templates.md#section_C1EB3B9D8E1242798A6E04609D1E3543)
* [Autocomplete](../c-appendices/c-templates.md#section_897316BEE1454E839A56B565CA4AF018)
* [Store](../c-appendices/c-templates.md#section_A33E25DB5E67404A823BD9618665B773)
* [Zones](../c-appendices/c-templates.md#section_B9B3179E000C42D492E1541F2FE44CB5)
* [Loop Indicators](../c-appendices/c-templates.md#section_387322CA0AA843A2ACF2795C328673E9)
* [Miscellaneous Language](../c-appendices/c-templates.md#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C)

## Declarations {#section_82C5CA734D2941EB858FEFE3B695D2EC}

Declarations are special guided-declare tags that you can set at the top of a top-level presentation template. Any subsequent declarations are ignored, including declarations in included templates.

<table id="table_892D11DDDFBE4DDE85374961A9F8973D"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-content-type-header content="content-type"> </span> </p> </td> 
   <td colname="col2"> <p>By default the presentation template is sent back with a mime-type of text/html. You can change what content-type is used with this tag. </p> <p>Declare this tag as high as possible in your presentation template. Do not add other text on the same line with this tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml-declare [charset="charset"]> </span> </p> </td> 
   <td colname="col2"> <p> If you are returning XML, you can use this tag to create the XML declaration. Make this tag the first line in your presentation template. When you use this tag, the content-type is automatically set to text/xml, unless you overrule it with <span class="codeph"> &lt;guided-content-type-header> </span> in the first line. If you do not specify a charset, it defaults to UTF-8. This tag results in the following output in your XML document: </p> <p> <span class="codeph"> &lt;?xml version="1.0" encoding="charset-name" standalone="yes" ?> </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Results {#section_06F249C9F6AE4B0F8C32117E19DCC905}

<table id="table_BBC8FA6BDA5040838C9F0BD4F293C6E3"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-results [gsname="searchname"]>&lt;/guided-results> </span> </p> </td> 
   <td colname="col2"> <p>The guided-results tag defines the boundaries of a results loop. Any set of results can be accessed by specifying a <span class="codeph"> gsname </span> attribute. If no <span class="codeph"> gsname </span> is given, then the default search results are displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-link [gsname="fieldname"] [attr="value"]+>&lt;/guided-result-link> </span> </p> </td> 
   <td colname="col2"> <p>To create a link to a given result, use the <span class="codeph"> guided-result-link </span> tag. By defining a <span class="codeph"> gsname </span> attribute, you can use a field from the index instead of the standard "loc" tag that references the "search-url". Any other attributes, such as class and target, can be passed as well, which are output in the resulting anchor tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-img gsname="fieldname" [attr="value"]+> </span> </p> </td> 
   <td colname="col2"> <p>The <span class="codeph"> &lt;guided-result-img> </span> tag helps create image tags rather than embedding variables inside a raw <span class="codeph"> img </span> tag. </p> <p>Specify the field to use for the image path in the <span class="codeph"> gsname </span> attribute. The result is an <span class="codeph"> img </span> tag with any standard HTML attributes that you defined, passed through. So, the following example: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-result-img gsname="thumbnail" 
       class="thumb" border="0"/> 
     </codeblock> </p> <p>becomes: </p> <p> 
     <codeblock class="syntax html">
       &lt;img src="prod8172.jpg" class="thumb" 
       border="0"/> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 1/31/13; search-eng version does not have [escape...] Added ijson on 8/28/2015--> <span class="codeph"> &lt;guided-result-field gsname="fieldname" [escape="html|url|js|json|ijson|0"]/> </span> </p> </td> 
   <td colname="col2"> <p> Any piece of information to present in the results is displayed as a <span class="codeph"> &lt;guided-result-field> </span> tag (except when using auto-generating tags such as the <span class="codeph"> &lt;guided-result-img> </span> tag). </p> <p>Specify the name of the Search index field in <span class="codeph"> gsname </span>. The exact string passed is output in the template. </p> <p>You can specify an escape option if you want this field escaped differently from what was specified in the transport template. </p> <p>This encoding is applied on top of whatever encoding was specified in the transport template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--added 1/31/13 from search-eng version--> <span class="codeph"> &lt;guided-if[-not]-result-field gsname="fieldname>&lt;/guided-if-result-field> </span> </p> </td> 
   <td colname="col2"> <p>This set of conditional tags is true if there is content in the specific field to display. If no content exists, the condition is false. You can use the tags to decide whether surrounding HTML is displayed or not displayed if a value does not exist, or if a different image is displayed, and so on. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-result-field gsname="thumbnail"> 
          &lt;guided-result-img gsname="thumbnail" class="thumb" /> 
      &lt;guided-else-result-field> 
          &lt;img src="nothumb.jpg" class="nothumb" /> 
      &lt;/guided-if-result-field> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--updated to match search-eng version, 1/31/13--> 
     <codeblock>
       &lt;guided-if[-not]-result-wrap> 
      &lt;guided-else-result-wrap>

    &lt;/guided-if[-not]-result-wrap&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>When displaying results in columns, this tag is used to identify whether the current result marks the end of a column. </p> <p>When the Boolean condition is true, HTML is added to the end of the result to finish off the row and start a new one. When it is the last one, a new row is not started. </p> <p>See <span class="codeph"> &lt;guided-if-not-last> </span> to learn more about that tag. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-result-wrap> 
           &lt;/div> 
           &lt;guided-if-not-last> 
               &lt;div> 
           &lt;/guided-if-not-last> 
       &lt;/guided-if-result-wrap> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-results-found [gsname="searchname"]/> </span> </p> </td> 
   <td colname="col2"> <p>Returns a 1 if the back-end search request returned results and 0 if it did not. If no <span class="codeph"> gsname </span> is specified, the tag assumes the primary search. This tag is useful to pass logic to JavaScript routines. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-total [gsname="searchname"]/> </span> </p> </td> 
   <td colname="col2"> <p>Returns the total number of results in the specified results set. Assumes the default search when no <span class="codeph"> gsname </span> is given. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-lower [gsname="searchname"]/> </span> </p> </td> 
   <td colname="col2"> <p>Returns the result number of the lower result on the page for the specified results set. Assumes the default search when no <span class="codeph"> gsname </span> is given. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-upper [gsname="searchname"]/> </span> </p> </td> 
   <td colname="col2"> <p>Returns the result number of the upper result on the page for the specified results set. Assumes the default search when no <span class="codeph"> gsname </span> is given. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 
     <codeblock>
       &lt;guided-if[-not]-results-found 
      [gsname="searchname"]&gt; 
      &lt;guided-else[-not]-results-found>

    &lt;/guided-if[-not]-results-found&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>Shows content when results are found. Or, shows no results HTML when results are not found. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-results-found gsname="products"> 
          &lt;guided-results gsname="products"> 
              ... 
          &lt;/guided-results> 
      &lt;guided-else-results-found> 
           No results were found. 
      &lt;/guided-if-results-found> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-title/> </span> </p> </td> 
   <td colname="col2"> <p>The <span class="codeph"> &lt;guided-result-title> </span> tag gives value of title transport template field specified with <span class="codeph"> &lt;title> </span> transport tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-description/> </span> </p> </td> 
   <td colname="col2"> <p>The <span class="codeph"> &lt;guided-result-description> </span> tag gives value of description transport template field specified with <span class="codeph"> &lt;description> </span> transport tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-loc/> </span> </p> </td> 
   <td colname="col2"> <p>The &lt; <span class="codeph"> guided-result-loc> </span> tag gives value of loc transport template field specified with <span class="codeph"> &lt;loc> </span> transport tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-result-field gsname="fieldname"> 
      &lt;guided-else-result-field>

    &lt;/guided-if-result-field&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>True if there is content in the specific field to display. If no content exists, the condition is false. Use the tags to decide whether surrounding HTML is displayed or not if a value does not exist, or if a different image is displayed, and so on. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-result-field gsname="thumbnail"> 
           &lt;guided-result-img gsname="thumbnail" class="thumb"/> 
      &lt;guided-else-result-field> 
           &lt;img src="nothumb.jpg" class="nothumb"/> 
      &lt;/guided-if-result-field> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table gsname="tablename"> </span> </p> </td> 
   <td colname="col2"> <p>This tag provides a loop through attribute table defined in the transport template with <span class="codeph"> &lt;attribute_table> </span> transport tag. There is <span class="codeph"> &lt;guided-result-attribute-table-field> </span> tag for displaying attribute table field values. Also it is possible to use plain <span class="codeph"> guided-result-field </span> tag inside loop for displaying other result fields. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table-field gsname="fieldname" [escape="html|url|js|json|0"]/> </span> </p> </td> 
   <td colname="col2"> <p>Displays attribute table field as defined in transport template. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-results>

    ...
    
    &lt;ul&gt;
    
    &lt;guided-result-attribute-table&nbsp;gsname="downloads"&gt;
    &nbsp;&nbsp;&lt;li&gt;
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="&lt;guided-result-attribute-table-field&nbsp;gsname="download_link"&nbsp;/&gt;"&gt;
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-attribute-table-field&nbsp;gsname="download_title"&nbsp;/&gt;
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/a&gt;&nbsp;(&lt;guided-result-field&nbsp;gsname="title"/&gt;)
    &nbsp;&nbsp;&lt;/li&gt;
    &lt;/guided-result-attribute-table&gt;
    
    &lt;/ul&gt;
    
    ...
    
    &lt;/guided-results&gt;
    </codeblock> </p> </td>
</tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release in October 2014--> <span class="codeph"> &lt;guided-trace [gsname="searchname"]/> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the trace information found within the trace data within the general section of the JSON data output by the transport template for the given search. </p> <p>If no search name is given, <span class="codeph"> default </span> is assumed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30, 2014)--> <span class="codeph"> &lt;guided-result-trace/> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the JSON content found within the results > trace information of the JSON data output by the transport template for the current search result. </p> <p>This tag is only valid within the <span class="codeph"> &lt;guided-results>&lt;/guided-results> </span> loop. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facets {#section_EA4C5678D5864B89BAB4D0DFE62A4624}

Facets are navigational components that let you drill into search results. You can use the facet tags to display various facets on your presentation template. You reference facets by name.

See [About Facets](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

See [About Facet Rail](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB).

See [About Dynamic Facets](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899).

<table id="table_9C1183C074444179A0C296248A3C0BA1"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 02/27/2014--> <span class="codeph"> &lt;guided-dynamic-facets>&lt;/guided-dynamic-facets> </span> </p> </td> 
   <td colname="col2"> 
    <!--NEW 2/2/2014--> <p>A looping context for any dynamic facets for a given search. </p> <p>The <span class="codeph"> &lt;guided-facet> </span> presentation template tag is edited so that the gsname attribute is automatically provided by the <span class="codeph"> &lt;guided-dynamic-facets> </span> looping context. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-display-name gsname=" <span class="varname"> facetname </span>"/> </span> </p> </td> 
   <td colname="col2"> <p>Returns the display label of the facet. </p> <p>If the facet uses the <span class="codeph"> &lt;display-name> </span> tag on the transport template, the content of that tag becomes the label. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-rail>&lt;/guided-facet-rail> </span> </p> </td> 
   <td colname="col2"> <p> Defines a section on the presentation template that is used as a repeating pattern for each facet in the facet rail. </p> <p> Each facet that belongs to the facet rail uses this section to evaluate its output. </p> <p>The following is an example of a facet rail: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-rail> 
        &lt;guided-facet> 
          &lt;guided-facet-display-name/> 
          ... 
          &lt;/guided-facet> 
        &lt;/guided-facet-rail> 
     </codeblock> </p> <p>Note that following tags do not need <span class="codeph"> gsname </span> attribute when inside <span class="codeph"> &lt;guided-facet-rail> </span> tag as value is dynamically determined at search time and is properly substituted: </p> 
    <ul id="ul_5B5ACAFD2B8848DDB27471AB9DA7BE6E"> 
     <li id="li_5A07E78D51FE4708879DD742C877FFFF">guided-facet </li> 
     <li id="li_B875DCACD7AB4FC890A456A6939AB657">guided-facet-display-name </li> 
     <li id="li_B70450749E864DE7BA401E3CD6EF5EB3">guided-facet-total-count </li> 
     <li id="li_DECDF5EF6FF7454F86C236D322F2BFEA">guided-facet-undo-link </li> 
     <li id="li_176949227AC14E8CA643A419E10F7B5A">guided-facet-undo-path </li> 
     <li id="li_B32D981281744462BC680F6EFEAC0069">guided-facet-behavior </li> 
    </ul> <p>The sort criteria on the <span class="wintitle"> Facet Rail </span> page determines the position of the facets. You can choose the sort order from the Sort Facets Method drop-down list. </p> <p> 
     <!--NEW 02/27/2014-->This tag can optionally accept a gsname attribute value of <span class="codeph"> _dynamic_facets </span>, which provides a looping context for any dynamic facets for this search. This pre-defined facet rail is also exposed in the Business Rules user interface for action <span class="codeph"> push facet X in facet rail '_dynamic_facets' to position Y </span>". </p> <p>See <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> About Facet Rail </a>. </p> <p>See also <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> About Dynamic Facets </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match current search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet gsname=" <span class="varname"> facetname </span>" height=" <span class="varname"> 60px </span>" width=" <span class="varname"> 120px </span>">&lt;/guided-facet> </span> </p> </td> 
   <td colname="col2"> <p>Use the <span class="codeph"> guided-facet </span> tag to define an area within which all facet tags relate to a specific facet. This tag is also a Boolean tag that hides all of the content if no values in the facet exist. In such case, there is no point outputting the facet values). </p> <p>The height and width attributes are optional and the dimensions are specified in pixels (px). The Visual Rule Builder (VRB) uses these two attributes, and displays a dotted box as an interactive placeholder when the facet is hidden. </p> <p> When the display name is in the facet and the facet is hidden, the name is also hidden. However, if the name is outside the facet, you can hide the name only if a <span class="codeph"> zone </span> tag or a <span class="codeph"> guided-if-facet-visible </span> tag is wrapped around it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if[-not]-facet-long [gsname="facetname"]>&lt;/guided-if[-not]-facet-long> </span> </p> </td> 
   <td colname="col2"> <p>This conditional tag is true when the number of facet values is over the length-threshold defined in the configuration. Use it to display a facet as a different UI element (such as a truncated list or a scroll box) when the list is too long. </p> <p> 
     <codeblock class="syntax xml">
       &lt;guided-facet name="category"> 
          &lt;guided-if-facet-long> 
              &lt;select> 
                  &lt;guided-facet-values> 
                      &lt;guided-facet-option /> 
                  &lt;/guided-facet-values> 
              &lt;/select> 
          &lt;guided-else-facet-long> 
              &lt;guided-facet-values> 
                  &lt;guided-facet-value-link>&lt;guided-facet-value />&lt;/guided-facet-link> 
              &lt;/guided-facet-values> 
          &lt;/guided-if-facet-long> 
      &lt;/guided-facet> 
     </codeblock> </p> <p>You can also use this condition outside the context of a named <span class="codeph"> guided-facet </span> block by referencing a specific facet directly through use of the <span class="codeph"> gsname </span> attribute. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-long gsname="category"> 
          The category facet is very long! 
      &lt;/guided-if-facet-long> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if[-not]-facet-selected [gsname="facetname"]>&lt;/guided-if[-not]-facet-selected> </span> </p> </td> 
   <td colname="col2"> <p>This conditional tag is true when the facet is clicked at least once and a facet value is currently selected. It is used to show or hide HTML or gs tags depending on whether a facet was clicked. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet name="category"> 
          &lt;guided-if-facet-selected> 
              This facet has been selected.  You can no longer refine it. 
          &lt;guided-else-facet-selected> 
          &lt;guided-facet-values> 
              &lt;guided-facet-value-link>&lt;guided-facet-value />&lt;/guided-facet-link> 
          &lt;/guided-facet-values> 
          &lt;/guided-if-facet-selected> 
      &lt;/guided-facet> 
     </codeblock> </p> <p>You can also use this condition outside the context of a named <span class="codeph"> guided-facet </span> block by referencing a specific facet directly through use of the <span class="codeph"> gsname </span> attribute. </p> <p> 
     <codeblock>
       &lt;guided-if-facet-selected gsname="category"> 
          The category facet is selected! 
      &lt;/guided-if-facet-selected> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if[-not]-facet-single [gsname="facetname"]>&lt;/guided-if[-not]-facet-single> </span> </p> </td> 
   <td colname="col2"> <p>This conditional tag is true when there is only one facet value. Use the tag to change the display of the facet when it has no ability to refine the results. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet name="category"> 
          &lt;guided-if-facet-single> 
              Facet is not refinable. 
          &lt;guided-else-facet-single> 
              &lt;guided-facet-values> 
                  &lt;guided-facet-value-link>&lt;guided-facet-value />&lt;/guided-facet-link> 
              &lt;/guided-facet-values> 
          &lt;/guided-if-facet-single> 
      &lt;/guided-facet> 
     </codeblock> </p> <p>You can also use this condition outside the context of a named <span class="codeph"> guided-facet </span> block by referencing a specific facet directly through use of the <span class="codeph"> gsname </span> attribute. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-single gsname="category"> 
          There is only one value in the category facet! 
      &lt;/guided-if-facet-single> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Added 7/15/2014--> <span class="codeph"> &lt;guided-if[-not]-facet-multiselect [gsname="facetname"]>&lt;/guided-if[-not]-facet-multiselect> </span> </p> </td> 
   <td colname="col2"> <p>This conditional tag is true when the facet is multi-select. Use the tag to change the display of the facet inside <span class="codeph"> &lt;guided-facet-rail> </span> or <span class="codeph"> &lt;guided-dynamic-facets> </span> tags. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-rail> 
        &lt;guided-facet> 
          &lt;guided-facet-display-name/>

    &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-multiselect&gt;
    &nbsp;...
    &nbsp;&lt;guided-else-facet-multiselect&gt;
    &nbsp;...
    &nbsp;&lt;/guided-if-facet-multiselect&gt;
    &nbsp;&nbsp;&nbsp;&nbsp;...
    &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet&gt;
    &nbsp;&nbsp;&lt;/guided-facet-rail&gt;
    </codeblock> </p> </td>
</tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-values [gsname=" <span class="varname"> facetname </span>"]>&lt;/guided-facet-values> </span> </p> </td> 
   <td colname="col2"> <p>This is the facet value loop iterator tag. You can define it within the context of a named <span class="codeph"> guided-facet </span> block, in which case you can omit the <span class="codeph"> <span class="varname"> gsname </span> </span>. Or, you can define it outside any <span class="codeph"> guided-facet </span> block, but it would require the <span class="codeph"> <span class="varname"> gsname </span> </span> attribute to identify which set of facet values are displayed. </p> <p>You can also use this tag to display the facet values outside the context of a named <span class="codeph"> guided-facet </span> block. You reference a specific facet directly by using the <span class="codeph"> <span class="varname"> gsname </span> </span> attribute. </p> <p> 
     <codeblock class="syntax html">
       &lt;script> 
           registerFacetValues('category', '&lt;guided-facet-values gsname="category">&lt;guided-facet-value/>,&lt;/guided-facet-values>'); 
      &lt;/script> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-value [escape="html|url|js|json|0"]/> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the string of the current facet value. </p> <p>By default the value is HTML escaped. You can use the escape option to change how the value is escaped. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-count/> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the number of results that match the current facet value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-facet-value-link [attr="value"]+>&lt;/guided-facet-value-link> </span> </p> </td> 
   <td colname="col2"> <p>Creates a link around the facet value string for the site visitor to click. The path is automatically generated to narrow the results by the current facet value. It supports passing any attribute directly to the anchor tag. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values> 
          &lt;guided-facet-value-link class="facetlink">&lt;guided-facet-value />&lt;/guided-facet-value-link> 
      &lt;/guided-facet-values> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 
     <codeblock>
       &lt;guided-if-facet-value-selected> 
      &lt;guided-else-facet- 
      value-selected> 
      &lt;/guided-if-facet-value-selected> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Changes the display of the facet value when it is currently selected. If it has already been chosen, in most cases, it is no longer linkable. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values> 
           &lt;guided-if-facet-value-selected> 
               &lt;b>&lt;guided-facet-value/>&lt;/b> 
           &lt;guided-else-facet-value-selected> 
               &lt;guided-facet-link>&lt;guided-facet-value/>&lt;/guided-facet-link>    
           &lt;/guided-if-facet-value-selected> 
      &lt;/guided-facet-values> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 
     <codeblock>
       &lt;guided-if[-not]-facet-value-ghost> 
      &lt;guided-else[-not]-facet-value-ghost>

    &lt;/guided-if[-not]-facet-value-ghost&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>Changes the display of the facet value when it is a ghost value. When a facet value is a ghost value, it is typically displayed in italic text to indicate that the value is missing or "ghosted". </p> <p>The following code excerpt is an example of a facet block: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values> 
          &lt;guided-if-facet-value-selected> 
              &lt;b>&lt;guided-facet-value /> (&lt;guided-facet-count />)&lt;/b> 
                  &lt;guided-else-facet-value-selected> 
                      &lt;guided-if-facet-value-ghost> 
                          &lt;i>&lt;guided-facet-value /> (0)&lt;/i> 
                      &lt;guided-else-facet-value-ghost> 
                  &lt;guided-facet-link class="link">&lt;guided-facet-value />&lt;/guided-facet-link> (&lt;guided-facet-count />) 
              &lt;/guided-if-facet-value-ghost> 
          &lt;/guided-if-facet-value-selected> 
      &lt;/guided-facet-values> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-undo-link gsname=" <span class="varname"> facetname </span>">&lt;/guided-facet-undo-link> </span> </p> </td> 
   <td colname="col2"> <p>Displays an undo link for a given facet. If there are multi-select facets, this link deselects all of the given facet's values. Give the facet a name. If the facet is not currently selected then the link is the current path. </p> <p>The following is an example of this tag's usage: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-selected gsname="category"> 
          &lt;guided-facet-undo-link gsname="category">Undo Category&lt;/guided-facet-undo-link> 
      &lt;/guided-if-facet-selected> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-long [gsname=" 
      <varname>
        facetname 
      </varname>"]&gt; 
      &lt;guided-else-facet-long>&lt;/guided-if-facet-long> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This conditional tag is true when the number of facet values is over the length-threshold defined in the configuration. Use it to display a facet as a different user interface element (such as a truncated list or a scroll box) when the list is too long. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet gsname="category"> 
           &lt;guided-if-facet-long> 
               &lt;div class="long_facet"> 
                   &lt;guided-facet-values> 
                       &lt;guided-facet-link>&lt;guided-facet-value/>&lt;/guided-facet-link> 
                   &lt;/guided-facet-values> 
               &lt;/div> 
           &lt;guided-else-facet-long> 
               &lt;div class="facet"> 
                   &lt;guided-facet-values> 
                       &lt;guided-facet-link>&lt;guided-facet-value/>&lt;/guided-facet-link> 
                   &lt;/guided-facet-values> 
               &lt;/div> 
           &lt;/guided-if-facet-long> 
       &lt;/guided-facet> 
     </codeblock> </p> <p>You can also use this condition outside the context of a named <span class="codeph"> guided-facet </span> block by referencing a specific facet directly through use of the <span class="codeph"> <span class="varname"> gsname </span> </span> attribute. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-long gsname="category"> 
           The category facet is very long! 
      &lt;/guided-if-facet-long> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-selected [gsname="facetname"]&gt; 
      &lt;guided-else-facet-selected>&lt;/guided-if-facet-selected> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This conditional tag is true when the facet is clicked at least once and a facet value is currently selected. It can be used to show or hide HTML or gs tags depending on whether a facet is clicked. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet gsname="category"> 
           &lt;guided-if-facet-selected> 
               This facet has been selected.  You can no longer refine it. 
           &lt;guided-else-facet-selected> 
               &lt;guided-facet-values> 
                   &lt;guided-facet-link>&lt;guided-facet-value/>&lt;/guided-facet-link> 
               &lt;/guided-facet-values> 
           &lt;/guided-if-facet-selected> 
      &lt;/guided-facet> 
     </codeblock> </p> <p>You can also use this condition outside the context of a named <span class="codeph"> guided-facet </span> block by referencing a specific facet directly through use of the <span class="codeph"> gsname </span> attribute. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-selected gsname="category"> 
           The category facet is selected! 
      &lt;/guided-if-facet-selected> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-single [gsname=" 
      <varname>
        facetname 
      </varname>"]&gt; 
      &lt;guided-else-facet-single>&lt;/guided-if-facet-single> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This conditional tag is true when there is only one facet value. It can be used to change the display of the facet when it has no ability to refine the results. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet gsname="category"> 
           &lt;guided-if-facet-single> 
               Facet is not refinable. 
           &lt;guided-else-facet-single> 
               &lt;guided-facet-values> 
                   &lt;guided-facet-link>&lt;guided-facet-value/>&lt;/guided-facet-link> 
               &lt;/guided-facet-values> 
           &lt;/guided-if-facet-single> 
      &lt;/guided-facet> 
     </codeblock> </p> <p>You can also use this condition outside the context of a named <span class="codeph"> guided-facet </span> block by referencing a specific facet directly through use of the <span class="codeph"> <span class="varname"> gsname </span> </span> attribute. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-single gsname="category"> 
           There is only one value in the category facet! 
      &lt;/guided-if-facet-single> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-has-values [gsname=" 
      <varname>
        facetname 
      </varname>"]&gt; 
      &lt;guided-else-facet-has-values>&lt;/guided-if-facet-has-values> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This condition lets you check if the specified facet has any values at all. You can use it for showing another facet instead of an empty one. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-total-count gsname=" <span class="varname"> facetname </span>"/> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the total number of results that are within the given facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value gsname=" <span class="varname"> associated custom facet value </span>" [escape="html|url|js|json|0"]/> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the string of a value that is associated with the facet. You can have 0 or more fields associated with a facet. Having associated fields is rare and to support such you configure the transport template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-facet-value gsname=" <span class="varname"> associated custom facet value </span>"/>&lt;guided-else-facet-value>&lt;/guided-if-facet-value> </span> </p> </td> 
   <td colname="col2"> <p>Tests if the facet value has an associated field value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-link [attr=" <span class="varname"> value </span>"]+>&lt;/guided-facet-link> </span> </p> </td> 
   <td colname="col2"> <p>Creates a link around the facet value string for the customer to click. The path is automatically generated to narrow the results by the current facet value. It supports passing any attribute directly to the anchor tag. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values> 
           &lt;guided-facet-link class="facetlink">&lt;guided-facet-value/>&lt;/guided-facet-link> 
      &lt;/guided-facet-values> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-path [escape="html|url|js|json|0"]/> </span> </p> </td> 
   <td colname="col2"> <p>Creates your own link to a facet value. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values> 
           &lt;guided-lt/>a href="&lt;guided-facet-value-path/>"&lt;guided-gt/>&lt;guided-facet-value/>&lt;/a> 
      &lt;/guided-facet-values> 
     </codeblock> </p> <p>By default, the value is URL escaped. You can, however, add another layer of encoding by specifying which mode of escaping you want to use by way of the escape parameter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-children>&lt;/guided-facet-value-children> </span> </p> </td> 
   <td colname="col2"> <p>As <span class="codeph"> &lt;guided-facet-values> </span> iterate through each facet value, this tag iterates through all the child values of a nested facet. Inside this tag, use the typical facet tags for creating links, creating undo links, and displaying facet values. This tag must be inside <span class="codeph"> &lt;guided-facet-values> </span> because it does nested looping. </p> <p>An example of using this tag is the following: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values> 
        &lt;guided-facet-link title='&lt;guided-facet-value />'>&lt;guided-facet-value /> (&lt;guided-facet-count />)&lt;/guided-facet-link> 
        &lt;guided-if-facet-value-has-children> 
         &lt;guided-facet-value-children> 
          &lt;guided-facet-link title='&lt;guided-facet-value />'>&lt;guided-facet-value /> (&lt;guided-facet-count />)&lt;/guided-facet-link> 
         &lt;/guided-facet-value-children> 
        &lt;/guided-if-facet-value-has-children> 
      &lt;/guided-facet-values> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-value-has-children> 
      &lt;guided-else-facet- 
      value-has-children> 
      &lt;/guided-if-facet-value-has-children> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Tests if the current facet value has child values. Recommended to use before using the <span class="codeph"> &lt;guided-facet-value-children> </span> tags. The "else" clause is optional. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-facet-value-above-length-threshold>

    &lt;guided-else[-not]-facet-value-above-length-threshold&gt;
    
    &lt;/guided-if[-not]-facet-value-above-length-threshold&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>Determines if the current facet value within the facet-values loop, is above the length threshold. It is typically used to only display values below the threshold on a long facet (unless the user previously selected a "See more" link displayed beneath the facet). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-facet-value-equals-length-threshold>

    &lt;guided-else[-not]-facet-value-equals-length-threshold&gt;
    
    &lt;/guided-if[-not]-facet-value-equals-length-threshold&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>Determines if the current facet value within the facet-values loop, is equal to the length threshold. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-link>&lt;/guided-facet-value-undo-link> </span> </p> </td> 
   <td colname="col2"> <p>Displays an undo link for a given selected facet value. Use it to display an undo link next to a selected facet value. Because this undo link only undoes that particular selected value, it differs from <span class="codeph"> &lt;guided-facet-undo-link> </span> which deselects all selected values. </p> <p> <p>Note:  If the facet does not have multi-select behavior then the two undo links have the same behavior. That is, the facet can only have one selected value. </p> </p> <p>If the facet is not currently selected then the link is the current path. Use this tag only within a <span class="codeph"> guided-facet-values </span> loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>30 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-path/> </span> </p> </td> 
   <td colname="col2"> <p>Create your own facet value undo link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>31 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-undo-path gsname=" <span class="varname"> facetname </span>"/> </span> </p> </td> 
   <td colname="col2"> <p>Create your own facet undo link. </p> <p> Similar to the <span class="codeph"> &lt;guided-facet-undo-link> </span> tag except that it gives you the raw path to build your own undo link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>32 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-value-matches facetname=" 
      <varname>
        facetname 
      </varname>" value="value">&lt;guided-else-facet-value-matches> 
      &lt;/guided-if-facet-value-matches> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Conditionally display HTML when the given facet has the selected or single value "value". This set of tags is often used to display a facet based on the value selected in another facet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>33 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-behavior gsname=" <span class="varname"> facetname </span>"/> </span> </p> </td> 
   <td colname="col2"> <p>Determine a facet's behavior, such as normal, sticky, or multi-select. It is useful for customers that receive XML results and want to dynamically change how the facet is displayed based on its behavior. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>34 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet[-not]-visible gsname=" 
      <varname>
        real_facet 
      </varname>"> 
      &lt;guided-else-facet[-not]-visible>

    &lt;/guided-if-facet[-not]-visible&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>The content that this tag wraps is either hidden or revealed based on the visibility state of the facet. If a business rule hides or reveals the facet directly, any content inside the facet is hidden or revealed. It is not necessary for these tags to wrap around the facet. </p> <p> A common use for this tag is to hide the display name when the name is outside the facet. Wrapping this tag around the display name makes the name disappear when the facet is hidden. </p> <p>This tag replaces the zone and has many of the same performance benefits as using zones. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_9B39B71FA6EC49FA8D88AD8A3BA987F7}

See [About Breadcrumbs](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03).

<table id="table_752EFE34541E41C6AA521970E40D74E2"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb [gsname=" <span class="varname"> breadcrumbname </span>"]>&lt;/guided-breadcrumb> </span> </p> </td> 
   <td colname="col2"> <p>The loop tag for the breadcrumb. Any content in between the opening and closing tags is iterated for each query-number of the current state. </p> <p>If <span class="codeph"> <span class="varname"> gsname </span> </span> is omitted, then the breadcrumb named "default" is used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-link [gsname="goto|remove|drop"] [attr="value"]+>&lt;/guided-breadcrumb-link> </span> </p> </td> 
   <td colname="col2"> <p>Creates a link in the breadcrumb. The default behavior is the "goto" behavior. If the link behaves differently, use the <span class="codeph"> <span class="varname"> gsname </span> </span> optional attribute to specify "remove" or "drop". Any attribute included in the tag is passed through to the resulting anchor tag. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-breadcrumb> 
           &lt;guided-breadcrumb-link gsname="remove" class="bc_link"> 
               &lt;guided-breadcrumb-value/> 
           &lt;/guided-breadcrumb-link> 
      &lt;/guided-breadcrumb> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-value /> </span> </p> </td> 
   <td colname="col2"> <p>The value tag prints out the transformed value of the current breadcrumb iteration. It is used only in the context of a <span class="codeph"> guided-breadcrumb </span> block. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-breadcrumb> 
           &lt;guided-breadcrumb-link> 
               &lt;guided-breadcrumb-value/> 
           &lt;/guided-breadcrumb-link> 
      &lt;/guided-breadcrumb> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-label /> </span> </p> </td> 
   <td colname="col2"> <p>The label tag outputs a label for a breadcrumb value detailing which facet was selected to generate that breadcrumb item. It is only used in the context of a <span class="codeph"> guided-breadcrumb </span> block. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-breadcrumb> 
           &lt;guided-breadcrumb-link> 
               &lt;guided-breadcrumb-label/>: &lt;guided-breadcrumb-value/> 
           &lt;/guided-breadcrumb-link> 
      &lt;/guided-breadcrumb> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if-breadcrumb-label> 
      &lt;guided-else- 
      breadcrumb-label> 
      &lt;guided-if-breadcrumb-label /> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This conditional tag is used to conditionally display content if the current breadcrumb value has a label. It is used to only display labels and relating content when a label actually exists. It is only used in the context of a <span class="codeph"> guided-breadcrumb </span> block. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-breadcrumb> 
           &lt;guided-breadcrumb-link> 
               &lt;guided-if-breadcrumb-label> 
                   &lt;guided-breadcrumb-label/>: 
               &lt;/guided-if-breadcrumb-label> 
           &lt;guided-breadcrumb-value/>&lt;/guided-breadcrumb-link> 
      &lt;/guided-breadcrumb> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb-path [gsname="goto|remove|drop"]/> </span> </p> </td> 
   <td colname="col2"> <p>Used to build your own breadcrumb link. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Menus {#section_1D489ADF041F4351A66E5D5742125CA8}

See [About Menus](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32).

<table id="table_323B2C09835442DBA51DC39F5848665F"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu gsname="menuname">&lt;/guided-menu> </span> </p> </td> 
   <td colname="col2"> <p>This is the menu value loop iterator tag. Use the <span class="codeph"> gsname </span> attribute to identify which set of menu items is displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-link [attr="value"]+>&lt;/guided-menu-item-link> </span> </p> </td> 
   <td colname="col2"> <p>Gives you the URL for refining the current search for the menu item. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-option [attr="value"]+ /> </span> </p> </td> 
   <td colname="col2"> <p>Typically a menu is displayed in a select control on a template. This tag makes constructing the select control easier because it generates the HTML for generating the option for the select control. </p> <p>For example, the following code block: </p> <p> 
     <codeblock class="syntax html">
       &lt;select name="sort" onchange="gcGo(this);"> 
      &lt;guided-menu gsname="sort"> 
      &lt;guided-menu-item-option/> 
      &lt;/guided-menu> 
      &lt;/select> 
     </codeblock> </p> <p>Can generate HTML like the following: </p> <p> 
     <codeblock class="syntax html">
       &lt;select name="sort" onchange="gcGo(this);"> 
        &lt;option value="?sort=relevance;sp_sfvl_field=product-type|category|size;" selected="selected">Sort by Relevance&lt;/option> 
        &lt;option value="?sort=avail-code;sp_sfvl_field=product-type|category|size;">Sort by Availability&lt;/option> 
        &lt;option value="?sort=price;sp_sfvl_field=product-type|category|size;">Sort by Price&lt;/option> 
      &lt;/select> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-value /> </span> </p> </td> 
   <td colname="col2"> <p>Returns the string of the value that is associated with the menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-label /> </span> </p> </td> 
   <td colname="col2"> <p>Returns the string of the label that is associated with the menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-path /> </span> </p> </td> 
   <td colname="col2"> <p>Returns the path string. Use the tag if you want to add a parameter to the path and create a custom link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if-menu-item-selected> 
      &lt;guided-else-menu- 
      item-selected> 
      &lt;/guided-if-menu-item-selected> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Returns a 1 or 0 indicating if the current menu item is selected. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pagenav {#section_2EE397635C514BBC8D668278EA314F35}

The page navigation tags can be used to build a set of links allowing a user to page through the search results.

<table id="table_2B8DFA07CAEE4B8BA156FD55DC9E7068"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-pages>&lt;/guided-pages> </span> </p> </td> 
   <td colname="col2"> <p>The loop tag for the page navigation. Any content between the opening and closing tags is iterated for each page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link [attr="value"]+>&lt;/guided-page-link> </span> </p> </td> 
   <td colname="col2"> <p>Creates a link in the page navigation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link gsname="first|prev|next|last|viewall|viewpages" [attr="value"]+>&lt;/guided-page-link> </span> </p> </td> 
   <td colname="col2"> <p>Creates a link to the first, previous, next, or last page. It can also create a link to view all of the pages on one page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-number /> </span> </p> </td> 
   <td colname="col2"> <p> Returns a string with the current page number. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if-page-selected> 
      &lt;guided-else-page- 
      selected> 
      &lt;/guided-if-page-selected> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This set of conditional tags is true if the page that is currently iterated over is selected. It is typically used to display differently the page number in the page-navigation control. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-page-prev> 
      &lt;guided-else-page- 
      prev> 
      &lt;/guided-if[-not]-page-prev> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p> This set of conditional tags is true if the current page has a previous page. It is typically used to display a previous link in the page navigation, when it makes sense. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-page-next> 
      &lt;guided-else-page- 
      next> 
      &lt;/guided-if[-not]-page-next> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p> This set of conditional tags is true if the current page has a next page. It is typically used to display a previous link in the page navigation, when it makes sense. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-page-viewall> 
      &lt;guided-else-page- 
      viewall> 
      &lt;/guided-if[-not]-page-viewall> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p> When a search returns a large result set you might not want to offer the ability to view all of the results. Therefore, you can use this set of conditional tags to determine when to display the View All link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-page-viewpages> 
      &lt;guided-else-page- 
      viewpages> 
      &lt;/guided-if[-not]-page-viewpages> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>You can use this set of conditional tags to determine when to display the View Pages link. It is typically used to allow a customer to view certain pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if 
      <!--[-not]-->-page-link gsname="first|prev| 
      next|last|viewall|viewpages">

    &lt;guided-else-page-link&gt;
    &lt;/guided-if[-not]-page-link&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>Tests if the page navigation has a first page, previous page, next page, and so on. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-total /> </span> </p> </td> 
   <td colname="col2"> <p> Returns a string with the total number of pages of search results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-pagination gsname= 
      "pagination_name">&lt;/guided-pagination> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Use the <span class="codeph"> guided-pagination </span> tag to define an area in which all pagination tags relate to a specific pagination setting in case you have few Page Navigation Settings defined. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-page-path[gsname="first|prev|

    next|last|viewall|viewpages]/&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>Creates your own link in the page navigation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-page-high-eq-last> 
      &lt;guided-else-page- 
      high-eq-last> 
      &lt;/guided-if-page-high-eq-last> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Tests if the highest page in the page navigation is equal to the total number of pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-page-low-eq-first> 
      &lt;guided-else-page-low-eq-first> &lt;/guided-if-page-low-eq-first> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Tests if the lowest page in the page navigation is equal to the one. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-page-is-multipage> &lt;guided-else-page-is-multipage> &lt;/guided-if-page-is-multipage> </span> </p> </td> 
   <td colname="col2"> <p>Tests if there is a single page of results or multiple pages of results. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recent Searches {#section_8CD907521F584257B475595B01A5964B}

You can use recent searches tags to build a set of links that let a user quickly run a previous search, as in the following example:

```
<guided-if-recent-searches> 
    <span>Recent Searches</span><br/> 
    <guided-recent-searches> 
        <guided-recent-searches-link><guided-recent-searches-value></guided-recent-searches-link><br/> 
    </guided-recent-searches> 
    <guided-recent-searches-clear-link>Clear Recent Searches</guided-recent-searches-clear-link> 
</guided-if-recent-searches>
```

See [Configuring recent searches](../c-about-design-menu/t-configuring-recent-searches.md#task_E9E8ACA04C90484F8AFD5262167B2562).

<table id="table_FBDC9DB8ED2A4974B16ED43508C74B7F"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches>&lt;/guided-recent-searches> </span> </p> </td> 
   <td colname="col2"> <p>The loop tag for recent searches. Any content between the opening and closing tags is iterated for each page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-recent-searches-link [attr="value"]+> 
      &lt;/guided-recent-searches-link> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Lets you build a link to a recent search. It supports the passing of any HTML attributes directly to the anchor tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-path/> </span> </p> </td> 
   <td colname="col2"> <p>Lets you grab the relative URL path for a recent search, within a <span class="codeph"> guided-recent-searches </span> loop. Typically you would use <span class="codeph"> guided-recent-search-link </span>. However, if you wanted to build your own link you could use this tag. The following is an example: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-lt/>a&amp;nbsp;href="&lt;guided_recent_searches_path>">&lt;guided-recent-searches-value>&lt;/a> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-value> </span> </p> </td> 
   <td colname="col2"> <p>Lets you grab the query term that is associated with a recent search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-link [attr="value"]+>&lt;/guided-recent-searches-clear-link> </span> </p> </td> 
   <td colname="col2"> <p>Lets you offer your customers the ability to clear recently saved searches. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-path/> </span> </p> </td> 
   <td colname="col2"> <p>Returns the path that <span class="codeph"> &lt;guided-recent-searches-clear-link> </span> uses so that you can build your own link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-recent-searches> 
      &lt;guided-else-recent-searches>

    &lt;/guided-if-recent-searches&gt;
    </codeblock> </p> </td>
<td colname="col2"> <p>Lets you display the recent searches when a customer has performed a recent search. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Did You Mean {#section_C1EB3B9D8E1242798A6E04609D1E3543}

You can use Did You Mean tags to build a set of links to suggestions when a search returns no results and the Search term is not in the account's dictionary. The following is an example of using Did You Mean tags:

```
<guided-if-suggestions> 
    <span>Did You Mean?</span><br/> 
    <guided-suggestions> 
        <guided-suggestion-link><guided-suggestion/></guided-suggestion-link><br/> 
    </guided-suggestions> 
</guided-if-suggestions>
```

See [About Did You Mean](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E).

<table id="table_A139FC0A7DF7460DBC52D0C05771789C"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestions>&lt;/guided-suggestions> </span> </p> </td> 
   <td colname="col2"> <p>This is the loop tag for looping over the suggestions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestion-link [attr="value"]+>&lt;/guided-suggestion-link> </span> </p> </td> 
   <td colname="col2"> <p>Creates a link to the given suggestion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Newly added from search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestion-value /> </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-suggestions>&lt;guided-else[-not]- 
      suggestions>&lt;/guided-if[-not]-suggestions> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Lets you test if there are any suggestions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-path/> </span> </p> </td> 
   <td colname="col2"> <p>Returns the path string to the suggestion. You can use it to build your own anchor tag. Typically, <span class="codeph"> guided-suggestion-link </span> is used instead. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion/> </span> </p> </td> 
   <td colname="col2"> <p>A suggestion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-result-count/> </span> </p> </td> 
   <td colname="col2"> <p>Result count for the suggestion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-suggestion-autosearch> 
      &lt;guided-else[-not]-suggestion-autosearch> 
      &lt;/guided-if[-not]-suggestion-autosearch> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Lets you test if autosearch by suggestion on zero results was performed, in case this feature is on. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-original-query/> </span> </p> </td> 
   <td colname="col2"> <p>Returns the original query if autosearch was performed. </p> <p>Example of use: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-suggestion-autosearch> 
          Search for &lt;guided-query-param gsname="q" /> instead of &lt;guided-suggestion-original-query /> 
      &lt;/guided-if-suggestion-autosearch> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-suggestion-low-results> 
      &lt;guided-else[-not]-suggestion-low-results> 
      &lt;/guided-if[-not]-suggestion-low-results> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This condition is true if there are suggestions due to a low result count, in case this feature is on. </p> <p>The following is an example of using this tag: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-suggestion-low-results> 
         You have a low result count for &lt;guided-query-param gsname="q" />. 
         Did you mean: &lt;guided-suggestions> 
             &lt;guided-suggestion-link> 
                &lt;guided-suggestion /> 
             &lt;/guided-suggestion-link>&lt;guided-if-not-last>, &lt;/guided-if-not-last> 
         &lt;/guided-suggestions> 
      &lt;/guided-if-suggestion-low-results> 
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Autocomplete {#section_897316BEE1454E839A56B565CA4AF018}

The following tags can be used to add autocomplete to your search form. The head-content and form-content tags are required to make autocomplete function correctly. It is recommended you use the tags as opposed to hard coding the autocomplete Javascript and CSS into your presentation template. The reason is because tags enable your templates to pick up any new defeat cache IDs whenever you change your autocomplete settings without the need to manually update your template.

See [About Auto-Complete](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578).

<table id="table_797858E5872545BE98CD59054F459C1D"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-autocomplete> &lt;guided-else-autocomplete> &lt;/guided-if-autocomplete> </span> </p> </td> 
   <td colname="col2"> <p>Detects if the autocomplete feature is enabled. You could use the tags to optionally pick up the head and form content that are required for autocomplete. In turn, this lets you toggle the feature on and off and not have to alter your presentation templates. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-css/> </span> </p> </td> 
   <td colname="col2"> <p>Used in the head of the presentation template and replaced by the appropriate CSS script includes for autocomplete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-form-content/> </span> </p> </td> 
   <td colname="col2"> <p>Used in the search form (between the <span class="codeph"> &lt;form> </span> and <span class="codeph"> &lt;/form> </span> tags) of the presentation template instead of hard coding the autocomplete tags within the form. The tags are replaced with the appropriate HTML that is required to make autocomplete work. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-javascript/> </span> </p> </td> 
   <td colname="col2"> <p>Generates the links to the Autocomplete JavaScript. For best performance it is recommended that you place this tag near the bottom of the page before the closing "body" tag. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Store {#section_A33E25DB5E67404A823BD9618665B773}

Use the following tags to test and display the store that a user is currently in.

<table id="table_6B6538E0D678491DB5BDF22A7CB70932"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-store/> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the current store. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store-defined> &lt;guided-else-store-defined> &lt;/guided-if-store-defined> </span> </p> </td> 
   <td colname="col2"> <p>Detects if the user is in a store. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store gsname="store"> &lt;guided-else-store> &lt;/guided-if-store> </span> </p> </td> 
   <td colname="col2"> <p>Detects if the user is in the store that the <span class="codeph"> gsname </span> parameter specifies. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zones {#section_B9B3179E000C42D492E1541F2FE44CB5}

<table id="table_514E2E1BBCBC45C8999893B4CF28548C"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-zone gsname="zone area" [search="associated search"] [facet="associated facet"] [width="xx" height="yy"]> </span> </p> </td> 
   <td colname="col2"> <p>You can wrap any content in zone tags to create a zone out of that area. This lets you use business rules to display the zone as needed. By default, zones are always displayed. You can use the optional search and facet parameters to indicate what search or facet is associated with the zone. Such functionality lets the software skip searches or facets when a zone is hidden, improving search-time performance. The height and width attributes are optional and are used to configure how the placeholder is displayed in the Visual Rule Builder when a zone is removed. </p> <p> Use the <span class="codeph"> guided-if-facet[-not]-visible </span> tag instead of the zone where possible. It simplifies the presentation template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-zone gsname="zone area"> &lt;guided-else-zone> &lt;/guided-if-zone> </span> </p> </td> 
   <td colname="col2"> <p>This set of tags enables testing if a zone is currently being displayed. It is useful when you have content elsewhere on the page that you only want to display when the zone is displayed. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Loop Indicators {#section_387322CA0AA843A2ACF2795C328673E9}

You can use each of the following loop indicators in any of these loop blocks:

* guided-results
* guided-facet-values
* guided-breadcrumb
* guided-menu-items
* guided-pages

<table id="table_1CA600313C7744BEA98532BFC8B39926"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-first>&lt;guided-else[-not]-first> 
      &lt;/guided-if[-not]-first> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This condition is true when the current iteration is the first iteration of the loop. That does not necessarily mean the first result or the first page, but the first one shown. If the site visitor is on page 2 of a results set that is 10 per page, the first iteration is result 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-last>&lt;guided-else[-not]-last> 
      &lt;/guided-if[-not]-last> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This condition is true when the current iteration is the last iteration of the loop. That does not necessarily mean the last result or the last page, but the last one shown in the current context (page). If the site visitor is on page 1 of a results set that contains 200 results but only has 10 results per page, the last iteration is result 10 instead of result 200. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-odd>&lt;guided-else[-not]-odd> 
      &lt;/guided-if[-not]-odd> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This condition is true when the current iteration is an odd iteration of the loop (versus an even iteration). This is helpful for displaying varying row colors. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-even>&lt;guided-else[-not]-even> 
      &lt;/guided-if[-not]-even> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This condition is true when the current iteration is an even iteration of the loop (versus an odd iteration). This is helpful for displaying varying row colors. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-alt>&lt;guided-else[-not]-alt> 
      &lt;/guided-if[-not]-alt> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This condition is true when the current iteration is an even iteration of the loop. This is helpful for displaying varying row colors. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-inner>&lt;guided-else[-not]-inner> 
      &lt;/guided-if[-not]-inner> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Includes the text between them if the current iteration is neither the first or the last. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-outer>&lt;guided-else[-not]-outer> 
      &lt;/guided-if[-not]-outer> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Includes the text between them if the current iteration is the first or the last. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-index> </span> </p> </td> 
   <td colname="col2"> <p>An integer (starting from 0) whose value increments for each iteration of the loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-counter> </span> </p> </td> 
   <td colname="col2"> <p>An integer (starting from 1) whose value increments for each iteration of the loop. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Miscellaneous Language {#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C}

The following tags are available to let you do more advanced things with your template, such as building your own mini-facet.

<table id="table_7665FC6120A842919EFF325ACB1E1A86"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-current-path [escape="html|url|js|json|0"] /> </span> </p> </td> 
   <td colname="col2"> <p>Gives you the current path that is used. Typically it is used to create a link that adds on a new parameter to the existing search. By default the path is URL escaped. You can specify which mode of escaping you want to use by way of the escape parameter. </p> <p>Example: </p> <p> 
     <codeblock class="syntax html">
       &lt;a href="&lt;guided-current-path />&amp;lang=fr"> 
      French Version 
     </codeblock> </p> <p>In this example, a search processing rule uses lang to select the French version. </p> <p>Current path always has at least one query parameter. If no other query parameters exist it is set to <span class="codeph"> q=* </span> making it easier to add more parameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> Base Path </span> </p> </td> 
   <td colname="col2"> <p> If you want to create a link using the basepath, use <span class="codeph"> / </span> at the start of your <span class="codeph"> href </span> and add on parameters. </p> <p> 
     <codeblock class="syntax html">
       &lt;a href="/">All Products&lt;/a> 
      Would create a link "All Products" to your 
      basepath, for example http://search.mycompany.com/

    </codeblock> </p> </td>
</tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-query-param gsname="query_parameter" [escape="html|url"] /> </span> </p> </td> 
   <td colname="col2"> <p>Lets you grab the existing value of a query parameter that is on the URL. If your parameter does not exist, this tag returns an empty string. If you do not specify an escape option the string returned is automatically HTML escaped, you can specify either HTML or URL escaping. </p> <p>Example: </p> <p> 
     <codeblock>
       If 
      my URL is http://stage.leejeansken.com:2928/?q=pants&amp;lang=en

    &lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;
    gives&nbsp;you&nbsp;the&nbsp;value&nbsp;pants
    
    &lt;guided-query-param&nbsp;gsname="lang"&nbsp;/&gt;
    gives&nbsp;you&nbsp;the&nbsp;value&nbsp;en
    
    &lt;guided-query-param&nbsp;gsname="test"&nbsp;/&gt;
    gives&nbsp;you&nbsp;an&nbsp;empty&nbsp;string
    &nbsp;
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    </codeblock> </p> </td>
</tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-query-param-name gsname="param#" offset="offset_number"/> </span> </p> </td> 
   <td colname="col2"> <p>Guided Search has the notion of a query number, which is used in the breadcrumb control. <span class="codeph"> guided-query-param-name </span> lets you define parameters as part of a link in the presentation template where Guided Search figures out the correct query number for you. The <span class="codeph"> gsname </span> has an "x" in it, which Guided Search replaces with the correct number. The offset value can be 0 - 15, where 0 indicates that the next available query number is used. A 1 indicates that you want to add 1 to it, and so on. </p> <p>Combined with <span class="codeph"> guided-current-path </span>, you can build your own mini facet link or allow an additional drill-down level. </p> <p>Example: </p> <p> 
     <codeblock class="syntax html">
       &lt;a href="&lt;guided-current-path 
              />&amp;&lt;guided-query-param-name gsname="q#" offset="0" 
              />=mens&amp;&lt;guided-query-param-name gsname="x#" offset="0" 
              />=category" >Category:Men&lt;/a>  
             
     </codeblock> </p> <p> 
     <codeblock class="syntax html">
       &lt;a href="&lt;guided-current-path 
              />&amp;&lt;guided-query-param-name gsname="sp_q_exact_#" offset="0" 
              />=mens&amp;&lt;guided-query-param-name gsname="sp_x_#" offset="0" 
              />=category&amp;&lt;guided-query-param-name gsname="sp_q_exact_#" offset="1" 
              />=Jeans&amp;&lt;guided-query-param-name gsname="sp_x_#" offset="1" 
              />=product-type" >Cat:Men - Product:Jeans&lt;/a> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-include gsfile="filename" /> </span> </p> </td> 
   <td colname="col2"> <p> Lets you include other template files. This functionality means that you can create multiple templates using sub templates as modules. </p> <p>In the following example, the <span class="filepath"> breadcrumbs </span> and <span class="filepath"> facets </span> files are included: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-include gsfile='breadcrumbs.tmpl' /> 
      &lt;guided-include gsfile='facets.tmpl' /> 
     </codeblock> </p> <p>Dynamic includes are not supported. In other words, <span class="codeph"> gsfile </span> cannot be a variable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-search-time> </span> </p> </td> 
   <td colname="col2"> <p> Identifies how long the search took. The returned search time value is specified in ms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-fall-through-searches> </span> </p> </td> 
   <td colname="col2"> <p> Returns the count of cores searches that are used to build the page of search results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-if-fall-through-search>&lt;/guided-if-fall-through-search> </span> </p> </td> 
   <td colname="col2"> <p>Tests if the count of core searches is greater than one. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-even>&lt;guided-else[-not]-even> 
      &lt;/guided-if[-not]-even> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This condition is true when the current iteration is an even iteration of the loop (versus an odd iteration). This is helpful for displaying varying row colors. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-alt>&lt;guided-else[-not]-alt> 
      &lt;/guided-if[-not]-alt> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>This condition is true when the current iteration is an even iteration of the loop. This is helpful for displaying varying row colors. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-inner>&lt;guided-else[-not]-inner> 
      &lt;/guided-if[-not]-inner> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Includes the text between them if the current iteration is neither the first or the last. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-outer>&lt;guided-else[-not]-outer> 
      &lt;/guided-if[-not]-outer> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Includes the text between them if the current iteration is the first or the last. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-first-search>&lt;guided-else-first-search> 
      &lt;/guided-if-first-search> 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Lets you check whether you are on the initial search or not (query was the result of a search from the search box). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-search-url/> </span> </p> </td> 
   <td colname="col2"> <p>You can use this tag in your template to save you from hardcoding the search form's action. It detects when you are in the Staged or Live environment and changes correspondingly. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-query-param-defined gsname="query_parameter"> &lt;guided-else-query-param-defined> &lt;/guided-if-query-param-defined> </span> </p> </td> 
   <td colname="col2"> <p>This set of tags lets you test what CGI parameters are defined in the search path. You can test the values of the parameters only if they are defined. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-next-query-number [gsname="offset"] /> </span> </p> </td> 
   <td colname="col2"> <p>The Guided Search engine that drives the template has the notion of floating query numbers where each new link that the engine generates, uses the next available query number. This tag lets you grab the next query number or offsets so that you can build custom links that drill into the result set. Offset lets you offset into the next query number. For example, if you have selected one facet, the next query number is 2, with an offset of 1 the query number returned is 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-custom-var gsname="custom_variable" [escape="html|url|js|json|0"]/> </span> </p> </td> 
   <td colname="col2"> <p>Lets you grab the existing value of a custom variable that your processing rules define. If you do not specify an escape option the string returned is automatically HTML escaped, you can specify either <span class="codeph"> html </span>, <span class="codeph"> url </span>, <span class="codeph"> js </span>, or <span class="codeph"> 0 </span>. If you use a processing rule to copy an incoming CGI parameter to a custom variable and then display or use that variable in your template with escaping set to none or js, then you can create an XSS vulnerability in your search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-custom-var-defined gsname="custom_variable"> &lt;guided-else-custom-var-defined> &lt;/guided-if-custom-var-defined> </span> </p> </td> 
   <td colname="col2"> <p>Enables testing if a custom variable is defined in the processing rules (query cleaning, pre-search processing and post-search processing). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-general-field gsname="searchname" field="fieldname" [escape="html|url|js|json|0"]/> </span> </p> </td> 
   <td colname="col2"> <p>Lets you display the contents of a general field that is defined in the transport template. If you do not specify an escape option the string returned is encoded in the format you have specified in the transport template for that field. Specifying an escape option applies on top of whatever format you are encoding the field as in your transport template. You can specify either <span class="codeph"> html </span>, <span class="codeph"> url </span>, <span class="codeph"> js </span>, <span class="codeph"> json </span>, or <span class="codeph"> 0 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-general-field gsname="searchname" field="fieldname"> &lt;guided-else-general-field> &lt;/guided-if-general-field> </span> </p> </td> 
   <td colname="col2"> <p>Enables testing if the contents of a general field, as defined in the transport template, exists. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-cookie-value gsname="cookie_name" [escape="html|url|js|json|0"]/> </span> </p> </td> 
   <td colname="col2"> <p>Lets you grab the value of a cookie, assuming that the cookie is available. If you do not specify an escape option the string returned is automatically HTML escaped, you can specify either <span class="codeph"> html </span>, <span class="codeph"> url </span>, <span class="codeph"> js </span>, <span class="codeph"> json </span>, or <span class="codeph"> 0 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-cookie gsname="cookie_name"> &lt;guided-else-cookie> &lt;/guided-if-cookie> </span> </p> </td> 
   <td colname="col2"> <p>Enables testing if a cookie exists. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-banner gsname="banner area" [escape="html|url|js|json|0"] [width="xx" height="yy"]/> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the banner for a given area. The optional width and height attributes are used in the Visual Rule Builder to enable the display of a meaningful place-holder to let users select a banner. By default banners are not escaped. Instead, you want to inject HTML into the presentation template. However, if you are building a JSON template consider using the js escaping option. </p> <p>Example: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-banner gsname="top" width="400px" 
       height="50px"/> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-banner-set gsname="banner area"> &lt;guided-else-banner-set> &lt;/guided-if-banner-set> </span> </p> </td> 
   <td colname="col2"> <p>Enables testing if a banner area is set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-simulator-mode> &lt;guided-else-simulator-mode> &lt;/guided-if-simulator-mode> </span> </p> </td> 
   <td colname="col2"> <p>Lets you detect when you are viewing your search in Simulator or the Visual Rule Builder. It is normally used to display extra debug information for you. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-tnt-business-rules> &lt;guided-else-tnt-business-rules> &lt;/guided-if-tnt-business-rules> </span> </p> </td> 
   <td colname="col2"> <p>Lets you detect if you have any business rules referencing an <span class="keyword"> Adobe Target </span> campaign. It is normally used as part of the integration with <span class="keyword"> Adobe Target </span> to prevent hitting the <span class="keyword"> Target </span> servers when it is not necessary. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-redirect/> </span> </p> </td> 
   <td colname="col2"> <p>By default redirects are performed automatically. However, if you have configured site search/merchandising to return an XML or JSON response to your web-application, you can choose to either parse the 302/301 response in your web-application or have the redirect passed to you as part of the result set. If you are passing the redirect as part of the result set, then this tag can be used in the template to output the redirect location. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-redirect> &lt;guided-else-redirect> &lt;/guided-if-redirect> </span> </p> </td> 
   <td colname="col2"> <p>When you have configured site search/merchandising to return redirects in the result set, this set of tags can be used to determine if there is a redirect to output. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-lt/> &lt;guided-gt/> </span> </p> </td> 
   <td colname="col2"> <p>This set of tags lets you embed guided template tags within HTML attributes. </p> <p>Example: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-lt/>div &lt;guided-if-facet-long> 
              style="height: 125px; overflow: 
              auto;"&lt;/guided-if-facet-long>&lt;guided-gt/> 
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Transport template tags {#reference_227D199F5A7248049BE1D405C0584751}

Transport templates are XML templates that pass data from the backend search to the Guided Search presentation layer.

<!-- 

r_transport_template_tags.xml

 -->

In your presentation layer, you can have a single presentation template that presents the results of multiple searches. Each search could use the same transport template or a custom transport template to pass the data to the presentation layer.

Because the transport template is only used to pass data to the presentation layer, it does not have any HTML that is concerned with displaying the search results. The transport template uses transport template XML tags to pass the search results for populating the Guided Search components, such as facets, breadcrumbs, and menus. Within these tags standard search template tags are used to display the actual values.

See [Editing a presentation or a transport template](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).

See [Search template tags](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

<table id="table_C94AA64B3C694C528E25CF0C45833872"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Transport template tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml>&lt;/guided-xml> </span> </p> </td> 
   <td colname="col2"> <p>The root XML tags that the presentation layer uses to detect what gets parsed out of the transport template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general>&lt;/general> </span> </p> </td> 
   <td colname="col2"> <p>Tags surround search template tags that provide summary data based on the result set. Typically, these tags contain search tags for total number of results, lower result, and highest result. You can define any number of additional global fields that you want with the <span class="codeph"> general-field </span> tag, as in the following example: </p> <p> 
     <codeblock class="syntax html">
       &lt;general> 
        &lt;total>&lt;search-total />&lt;/total> 
        &lt;lower>&lt;search-lower />&lt;/lower> 
        &lt;upper>&lt;search-upper />&lt;/upper> 
        &lt;general-field name="my_custom_field">Some global content&lt;/general-field> 
      &lt;/general> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results>&lt;/results> </span> </p> </td> 
   <td colname="col2"> <p>Tags are wrapped around the search results, so that Guided Search knows where to look for them. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result>&lt;/result> </span> </p> </td> 
   <td colname="col2"> <p>Tags are wrapped around each search result, so that Guided Search recognizes where the content for a single search result starts and ends, as in the following example: </p> 
    <codeblock class="syntax html">
      &lt;results> 
       &lt;search-results> 
         &lt;result> 
           &lt;index>&lt;search-index />&lt;/index> 
           &lt;loc>&lt;search-cdata>&lt;search-url length="500" />&lt;/search-cdata>&lt;/loc> 
         &lt;/result> 
       &lt;/search-results> 
     &lt;/results> 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"> </span> </p> </td> 
   <td colname="col2"> <p>Lets you loop through each item in a multi-value list for a single result. Only use this tag within a result. Its purpose is to let you iterate over attributes that belong to a result field, as in the following example: </p> 
    <codeblock class="syntax html">
      &lt;results> 
       &lt;search-results> 
         &lt;result> 
           &lt;index>&lt;search-index />&lt;/index> 
           &lt;loc>&lt;search-url />&lt;/loc> 
           &lt;title>&lt;search-title />&lt;/title> 
           &lt;attribute-table name="downloads"> 
             &lt;field name="download_title">&lt;search-display-field name="download_title" />&lt;/field> 
             &lt;field name="download_link" delimiter="|">&lt;search-display-field name="download_link" />&lt;/field> 
           &lt;/attribute-table> 
         &lt;/result> 
       &lt;/search-results> 
     &lt;/results> 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets>&lt;/facets> </span> </p> </td> 
   <td colname="col2"> <p>Passes on the results that populate the facets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <!--NEW 2/27/2014--> <span class="codeph"> &lt;dynamic-facet>&lt;/dynamic-facet> </span> </p> </td> 
   <td colname="col2"> <p> You can designate a facet as both a dynamic facet and as a member of a facet rail. However, their treatment is independent with respect to the related presentation template tags. </p> <p>In other words, the nesting of a facet rail looping context within a dynamic facet looping context, or vice versa, is not allowed. </p> <p>For facets that are both dynamic and railed, only those dynamic facets that were returned for a given search are visible within the facet rail looping context. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name">&lt;/facet> </span> </p> </td> 
   <td colname="col2"> <p> Each facet has its own facet tags where the name parameter matches the facet name. Search tags are used within the facet tags for the facet values, as in the following example: </p> 
    <codeblock class="syntax html">
      &lt;facets> 
       &lt;facet name="brand"> 
         &lt;values>&lt;search-field-value-list name="brand" quotes="no" commas="yes" data="values" sortby="values" />&lt;/values> 
         &lt;counts>&lt;search-field-value-list name="brand" quotes="no" commas="yes" data="counts" sortby="values" />&lt;/counts> 
       &lt;/facet> 
       &lt;facet name="category"> 
         &lt;values>&lt;search-field-value-list name="category" quotes="no" commas="yes" data="values" sortby="values" />&lt;/values> 
         &lt;counts>&lt;search-field-value-list name="category" quotes="no" commas="yes" data="counts" sortby="values" />&lt;/counts> 
       &lt;/facet> 
     &lt;/facets> 
    </codeblock> <p> Accounts using slotted facets can use the dynamic tag and the display-names tag. Both of these tags help facilitate the mapping between slotted facets and real facets while creating business rules. </p> 
    <codeblock class="syntax html">
      &lt;facets> 
       &lt;facet name="facet_values01"> 
      &lt;dynamic>1&lt;/dynamic> 
      &lt;display-names>&lt;search-field-value-list name="facet_names01" quotes="no" commas="yes" data="values" sortby="values" />&lt;/display-names> 
         &lt;values>&lt;search-field-value-list name="facet_values01" quotes="no" commas="yes" data="values" sortby="values" />&lt;/values> 
         &lt;counts>&lt;search-field-value-list name="facet_values01" quotes="no" commas="yes" data="counts" sortby="values" />&lt;/counts> 
       &lt;/facet> 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field separator=","> </span> </p> </td> 
   <td colname="col2"> <p>The <span class="codeph"> separator </span> attribute lets change the delimiter that is used when you output search-display-field data for lists. The default is a comma. </p> <p>Generally, the delimiter you use should be something that does not readily appear in your field content. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestions>&lt;/suggestions> </span> </p> </td> 
   <td colname="col2"> <p> Wrap your Did You Mean suggestions with tags so that Guided Search recognizes which XML nodes contain suggestions. </p> <p>See <a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local"> About Did You Mean </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestion>&lt;/suggestion> </span> </p> </td> 
   <td colname="col2"> <p>Wrap each Did You Mean suggestion with tags, as in the following example: </p> 
    <codeblock class="syntax html">
      &lt;search-if-suggestions> 
       &lt;suggestions> 
         &lt;search-suggestions> 
           &lt;suggestion>&lt;search-suggestion-text />&lt;/suggestion> 
         &lt;/search-suggestions> 
       &lt;/suggestions> 
     &lt;/search-if-suggestions> 
    </codeblock> <p>See <a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local"> About Did You Mean </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Search template tags {#reference_F7AA3FF602314E42842BBC740D2CA1A4}

A search template is an HTML file that includes template tags that site search/merchandising defines. These tags indicate how your search results are formatted. The following reference contains a brief description of each search template tag and its attributes.

<!-- 

r_search_template_tags.xml

 -->

>[!NOTE]
>
>Only use search template tags in transport template files (.tpl).

You can select from the following search template tag groups and reference material.

Tags that are valid only within the results loop include the following:

* [About Results loop tags](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)
* [Results loop string tags](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [Results loop conditional tags](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [Results loop anchor link tags](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [Loop position conditional tags](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

Tags that are valid throughout the template include the following:

* [Field value list tags](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1)
* [Field value list loop tags](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E)
* [Suggest tags](../c-appendices/c-templates.md#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC)
* [Template string tags](../c-appendices/c-templates.md#section_67E3D529661F4F03A1FF469D9D658CAF)
* [Template anchor link tags](../c-appendices/c-templates.md#section_3A51D27616C541E2B818CC52B2B856BA)
* [Template conditional tags](../c-appendices/c-templates.md#section_18D9BC66DE484881932FD2F7EA9D170D)
* [Template form control tags](../c-appendices/c-templates.md#section_45AFC414ACA74825B72FEAA8456F8DD2)

Search template reference topics

* [Date format strings](../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4)
* [Language identifiers](../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911)
* [Specifying the content-type HTTP header](../c-appendices/c-templates.md#section_AEED823E9938448A9EDB2F286D9CFD90)
* [Specifying a character set in an HTML template](../c-appendices/c-templates.md#section_E0D1816ABB5846BEBE9C26D5980CCBE6)
* [Specifying a character set in an XML template](../c-appendices/c-templates.md#section_17DC31CDCC104F5F8081466B41A96E9D)
* [Including a search template within another](../c-appendices/c-templates.md#section_7D1FCD3D9E2340C291E354C9720E8BC0)

## About Results loop tags {#section_D4DC7B4560144663972E8DBC3369C629}

The results loop tag is the workhorse of the template system. When the tag is encountered during a search, the HTML is repeated and other tags between the beginning and ending results loop tags, replacing any other tags with your search results.

`<search-results> ... </search-results>`

The results loop tags surround the HTML that shows the search results. The HTML between the tags is repeated for every result and is displayed on the page.

The following tags are valid only within the results loop:

* [Results loop string tags](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [Results loop conditional tags](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [Results loop anchor link tags](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [Loop position conditional tags](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

## Results loop string tags {#section_80D68334E8D04A33937A6E58ABAAA320}

The following tags return a string.

See [About Results loop tags](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table id="table_2B841B64E9744F6881FFE6E16FA98D58"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-index> </span> </p> </td> 
   <td colname="col2"> <p>Returns the numerical index of the current result. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-title length="XX"> </span> </p> </td> 
   <td colname="col2"> <p>Returns the page title of the current result. The optional length attribute is used to limit the length of strings displayed, with a default of 80 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-bodytext length="XX" encoding="html/javascript/json/perl/url/none" > </span> </p> </td> 
   <td colname="col2"> <p>Returns the body text starting from the top of the page. Relevant terms are shown in bold. The optional length attribute is used to limit the length of strings displayed, with a default of 80 characters. The encoding attribute is optional and it can encode output characters with HTML encoding (default), Javascript encoding, Perl encoding, or none. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-description length="XX" encoding="html/javascript/json/perl/url/none"> </span> </p> </td> 
   <td colname="col2"> <p> Returns the description of the current result. If the meta description tag exists and the content attribute is not empty, that text is shown. Otherwise, the beginning of the body text of the page is shown. The optional length attribute is used to limit the length of strings displayed, with a default of 80 characters. </p> <p>The optional <span class="codeph"> encoding </span> attribute controls whether the output is HTML encoded, JavaScript encoded, Perl encoded, URL encoded or not encoded, for output on the results page. The default value of <span class="codeph"> encoding </span> is <span class="codeph"> html </span>. Normally, you do not need to specify the encoding attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-score rank="dynamic/static/dynamic-raw/static-raw/final-raw" precision="XX"> </span> </p> </td> 
   <td colname="col2"> <p>Returns the score of the current result, which is a number 0 - 100. If you have defined a rank field under <span class="uicontrol"> Options </span> > <span class="uicontrol"> Metadata </span> > <span class="uicontrol"> Definitions </span>, you can display the dynamic page rank by setting the rank attribute to dynamic ( <span class="codeph"> &lt;search-score rank="dynamic"> </span>). You can display the static page rank by setting the rank attribute to static ( <span class="codeph"> &lt;search-score rank="static"> </span>). You can use the optional precision attribute to specify the number of decimal places to display. The default is 0 which displays the integer score). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-date length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id"> </span> </p> </td> 
   <td colname="col2"> <p>Returns the date of the current result. The optional "none" text value is displayed if there is no date associated with the current result. If the optional "none" value is not given, the text "No Date" is displayed if there is no date associated with the current result. </p> <p>The "date-format" attribute takes a UNIX style date format string such as "%A, %B %d, %Y" (for "Monday, July 25, 2016"). "gmt" defaults to "yes" and controls whether the time portion of the date string should be output in GMT ("yes") or the account's time zone ("no"). </p> <p>The "language" attribute controls the language and locale conventions of the output date string. "0" (the default) means "Use Account Language". "2" means "Use Document Language". The "language" value "1" is reserved for future use. Any other "language" value is interpreted as a specific language identifier, for example, "en_US" means "English (United States)". </p> <p>The optional length attribute is used to limit the length of strings displayed, with a default of 80 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-size> </span> </p> </td> 
   <td colname="col2"> <p>Returns the size of the current result in bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url length="XX" encoding="html/javascript/json/perl/url/none" > </span> </p> </td> 
   <td colname="col2"> <p>Returns the URL of the current result. </p> <p>Use the optional <span class="codeph"> length </span> attribute to limit the length of strings displayed, with a default of unlimited characters. </p> <p>The <span class="codeph"> encoding </span> attribute is optional and it can encode output characters with HTML encoding, Javascript encoding, Perl encoding, or none. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url-path-query length="XX"> </span> </p> </td> 
   <td colname="col2"> <p>Returns the path and query portions including the question mark of the URL of the current result. </p> <p>Use the optional <span class="codeph"> length </span> attribute to limit the length of strings displayed, with a default of unlimited characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-context length="XX" encoding="html/javascript/json/perl/url/none" > </span> </p> </td> 
   <td colname="col2"> <p>Returns the next line of context for the search term. Relevant terms are shown in bold. Call this tag repeatedly to display more than one context line for the current result. </p> <p>Use the optional <span class="codeph"> length </span> attribute to limit the length of strings displayed, with a default of 80 characters. The <span class="codeph"> length </span> attribute is ignored if this tag is enclosed by either <span class="codeph"> &lt;search-if-context> </span> or <span class="codeph"> &lt;search-if-any-context> </span> tag sets which contain a length attribute. </p> <p>The <span class="codeph"> encoding </span> attribute is optional and it can encode output characters with HTML encoding (default), Javascript encoding, Perl encoding, or none. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field name="field-name" length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id" encoding="html/javascript/json/perl/url/none" quotes="yes/no" commas="yes/no" units="miles/kilometers" separator="|"> </span> </p> </td> 
   <td colname="col2"> <p>This advanced tag displays the content of the metadata field (url, title, desc, keys, target, body, alt, date, charset, and language or fields defined under <span class="uicontrol"> Options </span> > <span class="uicontrol"> Metadata </span> > Definitions) specified in the <span class="codeph"> name </span> attribute, for the current result. For example: </p> <p> <span class="codeph"> &lt;search-display-field name="title" length="70" none="no title"> </span> </p> <p>Outputs the title of the page for a search result. If the optional <span class="codeph"> none </span> attribute is specified, its value is displayed on the results page only if there is no content associated with the field. </p> <p>The <span class="codeph"> date-format </span>, <span class="codeph"> gmt </span> and <span class="codeph"> language </span> attributes are only relevant if the content type of the specified field is <span class="codeph"> date </span>. </p> <p>The <span class="codeph"> date-format </span> attribute takes a UNIX style date format string such as <span class="codeph"> %A, %B %d, %Y </span> (for Monday, July 25, 2016). <span class="codeph"> gmt </span> defaults to <span class="codeph"> yes </span> and controls whether the time portion of the date string is output in GMT ( <span class="codeph"> yes </span>) or the account's time zone ( <span class="codeph"> no </span>). </p> <p>See <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> Date format strings </a>. </p> <p>The <span class="codeph"> language </span> attribute controls the language and locale conventions of the output date string. <span class="codeph"> 0 </span> (the default) means "Use Account Language". <span class="codeph"> 2 </span> means "Use Document Language". The <span class="codeph"> language </span> value <span class="codeph"> 1 </span> is reserved for future use). Any other <span class="codeph"> language </span> value is interpreted as a specific language identifier, for example, <span class="codeph"> en_US </span> means "English (United States)". </p> <p>See <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> Language identifiers </a>. </p> <p>The optional <span class="codeph"> length </span> attribute is used to limit the length of strings displayed, with a default of 80 characters. </p> <p>The optional <span class="codeph"> encoding </span> attribute controls whether the output is HTML encoded, JavaScript encoded, Perl encoded, URL encoded or not encoded, for output on the results page. The default value of <span class="codeph"> encoding </span> is <span class="codeph"> html </span>. Normally, you do not need to specify the encoding attribute. </p> <p>The optional <span class="codeph"> quotes </span> attribute controls whether the individual items output are surrounded by double-quotes (or single-quotes, if <span class="codeph"> encoding=perl </span>). The default value of <span class="codeph"> quotes </span> is <span class="codeph"> no </span>. </p> <p>The optional <span class="codeph"> commas </span> attribute controls whether the individual items output are separated by commas. The default value of <span class="codeph"> commas </span> is <span class="codeph"> yes </span>. The <span class="codeph"> commas </span> attribute is ignored for non-list-type fields. </p> <p>The optional <span class="codeph"> units </span> attribute controls the distance units applied to a proximity search output field. The default value of <span class="codeph"> units </span> is determined from the "Default Units" setting of the location-type field associated with the given proximity search output field. </p> <p>See <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> About proximity search </a>. </p> <p>The optional <span class="codeph"> separator </span> attribute defines the single character, or delimiter, that is inserted between the values of the output for list-type fields. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-values name="field-name"> ...&lt;search-display-field-values> </span> </p> </td> 
   <td colname="col2"> <p>This tag creates a loop for enumerating metadata field values (url, title, desc, keys, target, body, alt, date, charset, and language or fields defined under <span class="uicontrol"> Options </span> > <span class="uicontrol"> Metadata </span> > <span class="uicontrol"> Definitions </span>) for the current result. Do not nest this tag inside another <span class="codeph"> &lt;search-display-field-values> </span> tag. The <span class="codeph"> name </span> attribute specifies the name of the field containing the values to enumerate. This tag is most useful with fields that have the <span class="uicontrol"> Allow Lists </span> attribute checked (under <span class="uicontrol"> Options </span> > <span class="uicontrol"> Metadata </span> > <span class="uicontrol"> Definitions </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"> </span> </p> </td> 
   <td colname="col2"> <p>This tag outputs the metadata field value (url, title, desc, keys, target, body, alt, date, charset, and language or fields defined under <span class="uicontrol"> Options </span> > <span class="uicontrol"> Metadata </span> > <span class="uicontrol"> Definitions </span>) for the current <span class="codeph"> &lt;search-display-field-values> </span> loop iteration. This tag is only valid inside a <span class="codeph"> &lt;search-display-field-values> </span> loop. The <span class="codeph"> date-format </span>, <span class="codeph"> gmt </span> and <span class="codeph"> language </span> attributes are only relevant if the content type of the field name specified in the enclosing <span class="codeph"> &lt;search-display-field-values> </span> tag is <span class="codeph"> date </span>. The <span class="codeph"> date-format </span> attribute takes a UNIX style date format string such as <span class="codeph"> "%A </span>, <span class="codeph"> %B </span> <span class="codeph"> %d </span>, <span class="codeph"> %Y </span>" (for "Monday, July 25, 2016"). The <span class="codeph"> gmt </span> attribute defaults to <span class="codeph"> yes </span> and controls whether the time portion of the date string is output in GMT ( <span class="codeph"> yes </span>) or the account's time zone ( <span class="codeph"> no </span>). </p> <p>The <span class="codeph"> language </span> attribute controls the language and locale conventions of the output date string. <span class="codeph"> 0 </span> (the default) means "Use Account Language". Any other <span class="codeph"> language </span> value is interpreted as a specific language identifier, for example, <span class="codeph"> en_US </span> means "English (United States)". </p> <p>The optional <span class="codeph"> encoding </span> attribute controls whether the output is HTML encoded, JavaScript encoded, Perl encoded, URL encoded or not encoded, for output on the results page. The default value of <span class="codeph"> encoding </span> is <span class="codeph"> html </span>. Normally, you do not need to specify the encoding attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-count name="field-name"> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the total number of values in the current result for the metadata field (url, title, desc, keys, target, body, alt, date, charset, and language or fields defined under <span class="uicontrol"> Options </span> > <span class="uicontrol"> Metadata </span> > <span class="uicontrol"> Definitions </span>) specified with the name attribute. This tag can appear anywhere in the results loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-counter> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the ordinal counter (1, 2, 3, and so on) for the current <span class="codeph"> &lt;search-display-field-values> </span> loop iteration. This tag is only valid inside a <span class="codeph"> &lt;search-display-field-values> </span> loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-fields> </span> </p> </td> 
   <td colname="col2"> <p>Begins a looping context for any dynamic-facet-fields returned for this search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-field-name> </span> </p> </td> 
   <td colname="col2"> <p>Outputs the name of the current dynamic-facet-field, for this loop iteration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-result-trace encoding="html/javascript/ json/perl/url/none"> </span> </p> </td> 
   <td colname="col2"> <p>Outputs information related to the placement of the current result, for example, any results-based actions that affected the position of the result. </p> <p>The output format of this tag is JSON as in the following example: </p> <p> 
     <codeblock>
       { 
        "sliceID": 5, 
        "indexID": 5894, 
        "finalScore": 98.5, 
        "dynamicScore": 15.3, 
        "staticScore": 55.456, 
        "position": 1, 
        "rbtaActionListID": 117, 
        "rbtaActionID": 57 
      } 
     </codeblock> </p> 
    <!--<p> Results added to the results set by way of <codeph>rbta</codeph> have a "naturalPosition" value of -1. </p>--> <p>The <span class="codeph"> encoding </span> attribute is optional; the default value is <span class="codeph"> html </span>. </p> <p> <p>Note:  This tag only has output if <span class="codeph"> sp_trace=1 </span> is specified with the core search query parameters. </p> </p> <p>See row 48 in the table found in <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Results loop conditional tags {#section_35C367969E384A06A9865E388F1F9360}

The following tags conditionally include the HTML between them.

See [About Results loop tags](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table id="table_C49347072D074E888DC5A8F3CE7C3113"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-title> ... &lt;/search-if-title> </span> </p> <p> <span class="codeph"> &lt;search-if-not-title> ... &lt;/search-if-not-title> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the HTML between them if the next call to <span class="codeph"> &lt;search-title> </span> returns (or does not return) text from the document title. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-description length="XX"> ... /search-if-description> </span> </p> <p> <span class="codeph"> &lt;search-if-not-description> ... &lt;/search-if-not-description> </span> </p> </td> 
   <td colname="col2"> <p> These tags include the HTML between them if the next call to <span class="codeph"> &lt;search-description> </span> returns (or does not return) text from the document description. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bodytext> ... &lt;/search-if-bodytext> </span> </p> <p> <span class="codeph"> &lt;search-if-not-bodytext> ... &lt;/search-if-not-bodytext> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the HTML between them if the next call to <span class="codeph"> &lt;search-bodytext> </span> returns (or does not return) text from the document body. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-context length="XX"> ... &lt;/search-if-context> </span> </p> <p> <span class="codeph"> &lt;search-if-not-context> ... &lt;/search-if-not-context> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the HTML between them if the next call to <span class="codeph"> &lt;search-context> </span> returns (or does not return) a non-empty context string. The length attribute overrides the length attribute on any enclosed <span class="codeph"> &lt;search-context> </span> tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-any-context length="XX"> ... /search-if-any-context> </span> </p> <p> <span class="codeph"> &lt;search-if-not-any-context> ... &lt;/search-if-not-any-context> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the HTML between them if there is (or is not) a context string associated with the result. The length attribute overrides the length attribute on any enclosed <span class="codeph"> &lt;search-context> </span> tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-score lower="XX" upper="yy" rank="dynamic/static/dynamic-raw/static-raw/final-raw"> ... &lt;/search-if-score> </span> </p> <p> <span class="codeph"> &lt;search-if-not-score lower=XX upper=yy rank="dynamic/static"> ... &lt;/search-if-not-score> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the HTML between them if the score of the current result is (or is not) between XX and YY. Useful for adding bullets or graphics to show how relevant the result is. If you have defined a rank-type field under <span class="uicontrol"> Options </span> > <span class="uicontrol"> Metadata </span> > <span class="uicontrol"> Definitions </span>, you can check the dynamic page rank by setting the rank attribute to dynamic ( <span class="codeph"> &lt;search-if-score rank="dynamic" lower=XX upper=YY> </span>). You can check the static page rank by setting the rank attribute to static ( <span class="codeph"> &lt;search-if-score rank="static" lower=XX upper=YY> </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field name="field-name" value="value"> ... &lt;/search-if-field> </span> </p> <p> <span class="codeph"> &lt;search-if-not-field name="field-name" value="value"> ... &lt;/search-if-not-field> </span> </p> </td> 
   <td colname="col2"> <p>These advanced tags include the HTML between them based on whether the field specified in the "name" attribute has content or not. If the optional "value" attribute is specified, the tags include the HTML between them based on whether the given value matches (or does not match) the value for the field in the current result. These tags only function within the results loop (between <span class="codeph"> &lt;search-results> </span> and <span class="codeph"> &lt;/search-results> </span> tags). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Results loop anchor link tags {#section_C5FAEF520E9E42ADAD1F90651922AA02}

See [About Results loop tags](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table id="table_90B49709BD5A459EAE152066529B848B"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX" > ... &lt;/search-link> </span> </p> </td> 
   <td colname="col2"> <p>This pair of tags creates an anchor link around the HTML between them. When the link is clicked, the results page displays. An optional target attribute specifies the named window in which frame-capable browsers should display the results page. </p> <p>Set the hbx-enable attribute to "yes" to take advantage of the analytics available through HBX. Set hbx-linkid-name to the name of a Meta-data field you would like to track. For example, to track search results by SKU number, set hbx-linkid-name to the name of the Meta-data field that contains SKU information. </p> <p>Date-type fields are currently not supported. The value of hbx-linkid-name is appended to the link ID in the generated anchor. The value of the hbx-linkid-none attribute is appended to the link ID whenever the named Meta-data field is empty. The value of hbx-linkid-length limits the number of characters fetched and displayed from the Meta tag. The default number of characters is 12. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-smart-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"> ... &lt;/search-smart-link> </span> </p> </td> 
   <td colname="col2"> <p>This pair of tags is similar to the <span class="codeph"> &lt;search-link> ... &lt;/search-link> </span> tags. When the generated anchor links are clicked, the results page displays, but with the page scrolled to the nearest anchor tag preceding the result. For PDF links, the Acrobat viewer displays the page that contains the result. An optional target attribute specifies the named window in which frame-capable browsers should display the results page. </p> <p>Set the hbx-enable attribute to "yes" to take advantage of the analytics available through HBX. Set hbx-linkid-name to the name of a Meta-data field you would like to track. For example, to track search results by SKU number, set hbx-linkid-name to the name of the Meta-data field that contains SKU information. </p> <p>Date-type fields are currently not supported. The value of hbx-linkid-name is appended to the link ID in the generated anchor. The value of the hbx-linkid-none attribute is appended to the link ID whenever the named Meta-data field is empty. The value of hbx-linkid-length limits the number of characters fetched and displayed from the Meta tag. The default number of characters is 12. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-link-extension> ... &lt;/search-if-link-extension> </span> </p> <p> <span class="codeph"> &lt;search-if-not-link-extension> ... &lt;/search-if-not-link-extension> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the HTML between them if a value attribute specifies an extension that matches the end of the URL for the result. This tag is useful for including a graphic in the search results based on the link extension. The value attribute is a list of one or more extensions (space separated) as follows: VALUE=".pdf" or VALUE=".html .htm". </p> </td> 
  </tr> 
 </tbody> 
</table>

## Loop position conditional tags {#section_E0C29DDA09E043C9A396F36334F05EBB}

The following tags conditionally include the text between them. They can only appear inside the "looping" tags: < `search-results>` and `<search-field-values>`. They are used to test the position of the current result within the result set.

See [About Results loop tags](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table id="table_9CA9445FC1D4439EB65ADFD17B2D890D"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-first> ... &lt;/search-if-first> </span> </p> <p> <span class="codeph"> &lt;search-if-not-first> ... &lt;/search-if-not-first> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the text between them if the current result is (or is not) the first result on the page (when used inside <span class="codeph"> &lt;search-results> </span>) or the first field value (when used inside <span class="codeph"> &lt;search-field-values> </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-last> ... &lt;/search-if-last> </span> </p> <p> <span class="codeph"> &lt;search-if-not-last> ... &lt;/search-if-not-last> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the text between them if the current result is (or is not) the last result on the page (when used inside <span class="codeph"> &lt;search-results> </span>) or the last field value (when used inside <span class="codeph"> &lt;search-field-values> </span>). This tag can be used to insert a separator between results. For example, this inserts an <span class="codeph"> &lt;hr> </span> tag between results: </p> <p> 
     <codeblock class="syntax html">
       &lt;search-results> 
         &lt;search-lt>tr&lt;search-if-alt> class="alt"&lt;/search-if-alt>&lt;search-gt> 
            &lt;td>&lt;search-url>&lt;/td> 
         &lt;/tr> 
      &lt;/search-results> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-inner> ... &lt;/search-if-inner> </span> </p> <p> <span class="codeph"> &lt;search-if-not-inner> ... &lt;/search-if-not-inner> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the text between them if the current result is not the first nor the last result on the page (when used inside <span class="codeph"> &lt;search-results> </span>) or is not the first nor the last field value (when used inside <span class="codeph"> &lt;search-field-values> </span>). The not version of the tag tests whether the result is either the first or the last. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-alt> ... &lt;/search-if-alt> </span> </p> <p> <span class="codeph"> &lt;search-if-not-alt> ... &lt;/search-if-not-alt> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the text between them if the current result is (or is not) an alternate result on the page (when used inside <span class="codeph"> &lt;search-results> </span>) or an alternate field value (when used inside <span class="codeph"> &lt;search-field-values> </span>). The "alternate" results are the second, fourth, sixth, and so on, on the page. This example applies a different class to alternate table rows. Note the use of <span class="codeph"> &lt;search-lt> </span> and <span class="codeph"> &lt;search-gt> </span> to allow the <span class="codeph"> &lt;search-if-alt> </span> tag to be placed "inside" the <span class="codeph"> &lt;tr> </span> tag. </p> <p> 
     <codeblock class="syntax html">
           &lt;search-results> 
             &lt;search-lt>tr&lt;search-if-alt> class="alt"&lt;/search-if-alt>&lt;search-gt> 
                &lt;td>&lt;search-url>&lt;/td> 
             &lt;/tr> 
          &lt;/search-results> 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-even> ... &lt;/search-if-even> </span> </p> <p> <span class="codeph"> &lt;search-if-not-even> ... &lt;/search-if-not-even> </span> </p> </td> 
   <td colname="col2"> <p>These tags include the text between them if the current result is (or is not) an even-numbered result (when used inside <span class="codeph"> &lt;search-results> </span>) or an even-numbered field value (when used inside <span class="codeph"> &lt;search-field-values> </span>). A search result is even-numbered if its <span class="codeph"> &lt;search-index> </span> value is even. In other words, if its position within the entire result set is even. This may be different from <span class="codeph"> &lt;search-if-alt> </span> which tests the position of a result on the page, not within the entire result set. The following two tables illustrate the difference: </p> </td> 
  </tr> 
 </tbody> 
</table>

#### First page, sp_n=1
<table id="table_0334F560A1F840A9A1447F357A888B6E">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Index </p> </th> 
   <th colname="col2" class="entry"> <p>Result </p> </th> 
   <th colname="col3" class="entry"> <p>Even? </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>First result </p> </td> 
   <td colname="col3"> <p>No </p> </td> 
   <td colname="col4"> <p>No </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Second result </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>Yes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Third result </p> </td> 
   <td colname="col3"> <p>No </p> </td> 
   <td colname="col4"> <p>No </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Fourth result </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>Yes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Fifth result </p> </td> 
   <td colname="col3"> <p>No </p> </td> 
   <td colname="col4"> <p>No </p> </td> 
  </tr> 
 </tbody> 
</table>

#### Later page, sp_n=10
<table id="table_00DAAFA92C994387B38737C8435AB3D4">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Index </p> </th> 
   <th colname="col2" class="entry"> <p>Result </p> </th> 
   <th colname="col3" class="entry"> <p>Even? </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>Tenth result </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>No </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p>Eleventh result </p> </td> 
   <td colname="col3"> <p>No </p> </td> 
   <td colname="col4"> <p>Yes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>Twelfth result </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>No </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>Thirteenth result </p> </td> 
   <td colname="col3"> <p>No </p> </td> 
   <td colname="col4"> <p>Yes </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>Fourteenth result </p> </td> 
   <td colname="col3"> <p>Yes </p> </td> 
   <td colname="col4"> <p>No </p> </td> 
  </tr> 
 </tbody> 
</table>

Finally, note that `<search-if-even>` is always the same as `<search-if-alt>` for search field values since field values are not paged.

## Field value list tags {#section_D3298B5F976447DBA0032B883DCC91B1}

The following advanced tags output field values and related data from the entire set of search results. These tags only yield output for fields specified by the `sp-sfvl-field` CGI parameters in the search query.

<table id="table_7854EEFBE7BB40338A84F7AE0381C0BA"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list name="field-name" quotes="yes/no" commas="yes/no" data="values/counts/results" separator="X" sortby="none/values/counts/results" max-items="XX" date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"> </span> </p> </td> 
   <td colname="col2"> <p>This tag displays a list of unique field values, value counts, or result counts within the entire result set. </p> <p>This tag only yields output for fields specified by the <span class="codeph"> sp_sfvl_field </span> CGI parameters in the search query. The optional "quotes" attribute controls whether the individual items output are surrounded by double-quotes (or single-quotes, if encoding=perl). The default value of "quotes" is "yes". The optional "commas" attribute controls whether the individual items output are separated by commas. The default value of "commas" is "yes". The optional "data" attribute controls whether each unique field value is output (data="values"), the total count of each unique field value is output (data="counts"), or the number of results containing each unique value (data="results") is output. The default value of "data" is "values". For non-list-type fields, data="counts" and data="results" are equivalent. The separator attribute defines the single character, or delimiter, to be inserted between the values of the output. The optional "sortby" attribute controls the ordering of the output; sortby="none" means no particular order, sortby="values" means sort by field values (in ascending or descending order according to the field's Sorting property), sortby="counts" means sort in descending order of field value counts, and sortby="results" means sort in descending order of the number of results containing each value. </p> <p>Note that sortby="counts" and sortby="results" are equivalent for non-list-type fields. The optional "max-items" attribute limits the number of items to output. The default value of "max-items" is -1, which means "output all items". </p> <p>There is an absolute limit of 100 for max-items. The "date-format", "gmt" and "language" attributes are only relevant if the content type of the specified field is "date". The "date-format" attribute takes a UNIX style date format string such as "%A, %B %d, %Y" (for "Monday, July 25, 2016"). "gmt" defaults to "yes" and controls whether the time portion of the date string should be output in GMT ("yes") or the account's time zone ("no"). </p> <p>See <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> Date format strings </a>. </p> <p>The "language" attribute controls the language and locale conventions of the output date string. "0" (the default) means "Use Account Language". Any other "language" value is interpreted as a specific language identifier, for example, "en_US" means "English (United States)". The optional "encoding" attribute controls whether the output string characters are HTML encoded, JavaScript encoded, Perl encoded, URL encoded or not encoded, for output on the results page. The default value of "encoding" is "html". </p> <p>See <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> Language identifiers </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value" results="yes/no"> </span> </p> </td> 
   <td colname="col2"> <p>This tag displays count information for a given search-field-value-list. There are three distinct uses for this tag. If only the "name" attribute is supplied, this tag outputs the number of unique values for the named field within the entire results set. If the "name" and "value" attributes are both supplied, this tag outputs either the total count of the given value within the entire results set (for results="no"), or the total count of results containing the given value in the entire results set (for results="yes"). The default value of "results" is "no". Note: For non-list-type fields, results="yes" and results="no" are equivalent. The value of "results" is ignored if the "value" attribute is not supplied. This tag only yields output for fields specified by the <span class="codeph"> sp-sfvl-field </span> CGI parameters in the search query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field-value-list-count name="field-name" value="field-value"> ... &lt;/search-if-field-value-list-count> </span> </p> <p> <span class="codeph"> &lt;search-if-not-field-value-list-count name="field-name" value="field-value"> ... &lt;/search-if-not-field-value-list-count> </span> </p> </td> 
   <td colname="col2"> <p>These tags display the HTML between them if the equivalent call to <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value"> </span> with the given attributes would (or would not) return a value greater than zero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-single-field-value-list-count name="field-name"> ... &lt;/search-if-single-field-value-list-count> </span> </p> </td> 
   <td colname="col2"> <p>These tags display the content between them if the equivalent call to <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value"> </span> with the given attributes would (or would not) return a single value. This is typically used when an account is using facets slots. With facet slots, you typically only want to display the value-slot when the associated name-slot has a single item. Doing this check in the transport template is more efficient than doing it in the presentation layer. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Field value list loop tags {#section_0717FA09F0FC449CB916883B0500A60E}

The following advanced tags enumerate and output field values and related data from the entire set of search results using a looping construct. These tags only yield output for fields specified by the `sp-sfvl-field` CGI parameters in the search query.

<table id="table_BB19BF975DE4470190DB02015E5FABB2"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-values name="field-name" sortby="none/values/counts/results" max-items="XX"> ... &lt;/search-field-values> </span> </p> </td> 
   <td colname="col2"> <p>This tag creates a loop for enumerating field values and related data for a particular field within the entire results set. Do not nest this tag inside another <span class="codeph"> &lt;search-field-values> </span> tag. The "name" attribute specifies the name of the field containing the values to enumerate. The optional "sortby" attribute controls the enumeration order: "none" means no particular order, "values" means sort by field values (in ascending or descending order according to the field's Sorting property), sortby="counts" means sort in descending order of field value counts, and sortby="results" means sort in descending order of the number of results containing each value. </p> <p>Note that sortby="counts" and sortby="results" are equivalent for non-list-type fields. . The optional "max-items" attribute limits the number of iterations to the given value. The default value for "max-items" is -1, which means "enumerate all values". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value date-format="date-format-string" encoding="html/javascript/json/perl/url/none" gmt="yes/no" language="0/language-id"> </span> </p> </td> 
   <td colname="col2"> <p>This tag outputs the field value for the current &lt;search-field-values> loop iteration. This tag is only valid inside a <span class="codeph"> &lt;search-field-values> </span> loop. The "date-format", "gmt" and "language" attributes are only relevant if the content type of the field name specified in the enclosing &lt;search-field-values> tag is "date". The "date-format" attribute takes a UNIX style date format string such as "%A, %B %d, %Y" (for "Monday, July 25, 2016"). </p> <p>See <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> Date format strings </a>. </p> <p>The optional "encoding" attribute controls whether the output string characters are HTML encoded, JavaScript encoded, Perl encoded, URL encoded or not encoded, for output on the results page. The default value of "encoding" is "none". Normally, you do not need to specify the encoding attribute. "gmt" defaults to "yes" and controls whether the time portion of the date string should be output in GMT ("yes") or the account's time zone ("no"). The "language" attribute controls the language and locale conventions of the output date string. "0" (the default) means "Use Account Language". Any other "language" value is interpreted as a specific language identifier, for example, "en_US" means "English (United States)". </p> <p>See <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> Language identifiers </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-count results="yes/no"> </span> </p> </td> 
   <td colname="col2"> <p>This tag outputs the count associated with the current <span class="codeph"> &lt;search-field-values> </span> loop iteration. The output count is either the number of results in the entire results set containing the field value (results="yes"), or the total count for the field value in the entire results set. The default value of "results" is "no". </p> <p>For non-list-type fields, results="yes" and results="no" are equivalent. This tag is only valid inside a <span class="codeph"> &lt;search-field-values> </span> loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-counter> </span> </p> </td> 
   <td colname="col2"> <p>This tag outputs the ordinal counter for the current <span class="codeph"> &lt;search-field-values> </span> loop iteration. This tag is only valid inside a <span class="codeph"> &lt;search-field-values> </span> loop. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suggest tags {#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC}

Suggest provides a user-friendly "Did you mean?" service for suggesting alternative search terms. If a user has misspelled a search term, for example, Suggest can help the user find results by suggesting a correct spelling. The system can also suggest related keywords that can help a user discover results. When generating suggestions, the Suggest service uses two dictionaries: one based on the account language (set under **[!UICONTROL Indexing]** > **[!UICONTROL Words and Languages]** > **[!UICONTROL Language]**), and the other that is uniquely built from the keywords in the account index.

>[!NOTE]
>
>The Suggest service does not work for Chinese, Japanese, or Korean.

<table id="table_8E014DED2453470596AD5FBCE371CF29"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-suggestions> ... &lt;/search-if-suggestions> </span> </p> </td> 
   <td colname="col2"> <p>Surround these tags with any "Suggest" template tags, such as <span class="codeph"> &lt;search-suggestion> </span>, <span class="codeph"> &lt;search-suggestion-link> </span>, and so on. If the search generates suggestions, the search engine outputs and processes everything between the open and close tag. If the search does not generate suggestions, none of the nested content is output. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestions> ... &lt;/search-suggestions> </span> </p> </td> 
   <td colname="col2"> <p>This tag generates the "Suggest" loop, which contains a list of suggested search terms (for example, "intend", "intended" and "intends", for a query originally entered as "intendds"). When generating the list of terms, the search engine repeats any nested HTML and/or template tags up to five times, which is the maximum number of suggestions. Use the count attribute to specify the number of generated suggestions (between 0-5). </p> <p>The <span class="codeph"> &lt;search-suggestions> </span> tag can appear multiple times on the page to repeat the list of suggestions. Multiple suggestions are sorted according to the number of results each yields. </p> <p>Nest the <span class="codeph"> &lt;search-suggestions> </span> tag between open and close <span class="codeph"> &lt;search-if-suggestions> </span> tags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-link> ... &lt;/search-suggestion-link> </span> </p> </td> 
   <td colname="col2"> <p>This tag generates a link to the original search query using the selected suggested search term instead of the original term. The tag accepts and simply prints out any HTML attribute such as class, target, and style. The tag can also accept a URL attribute, the value of which is used as the base URL for the generated link. The tags can only appear inside the <span class="codeph"> &lt;search-suggestions> </span> loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-text/> </span> </p> </td> 
   <td colname="col2"> <p>This tag prints out the currently suggested query term (for example, "intend" for a query originally entered as "intendds"). The tag has no attributes and can only appear inside the <span class="codeph"> &lt;search-suggestions> </span> loop. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-not-suggestions> ... &lt;/search-if-not-suggestions> </span> </p> </td> 
   <td colname="col2"> <p>If the search generates no suggestions, the search engine outputs and processes everything between the open and close tag. If the search generates suggestions, none of the nested content is output. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if[-not]-first-suggestion> ... &lt;/search-if[-not]-first-suggestion> </span> </p> </td> 
   <td colname="col2"> <p>These conditional tags include the HTML between them based on whether the suggested term is the first term in the Suggest loop. The tags must appear between open and close <span class="codeph"> &lt;search-suggestion> </span> tags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if[-not]-last-suggestion> ... &lt;/search-if[-not]-last-suggestion> </span> </p> </td> 
   <td colname="col2"> <p>These conditional tags include the HTML between them based on whether the suggested term is the last term in the Suggest loop. The tags must appear between open and close <span class="codeph"> &lt;search-suggestion> </span> tags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-index> </span> </p> </td> 
   <td colname="col2"> <p>This tag returns the numerical index of the current suggested search term. The tag must appear between open and close <span class="codeph"> &lt;search-suggestion> </span> tags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-total> </span> </p> </td> 
   <td colname="col2"> <p>This tag returns the total number of generated suggested search terms. The tag must appear between open and close <span class="codeph"> &lt;search-suggestion> </span> tags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-result-count> </span> </p> </td> 
   <td colname="col2"> <p>This tag returns the total number of results for suggested search term. The tag must appear between open and close <span class="codeph"> &lt;search-suggestion> </span> tags. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Template string tags {#section_67E3D529661F4F03A1FF469D9D658CAF}

The following tags output a string into the HTML at that point in the template.

<table id="table_141DA461BC7442C4A343159F151277B3"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-body> </span> </p> </td> 
   <td colname="col2"> <p>The HTML body tag with any Search Link Color settings that the Basic Look Section sets under the Template link. Add a background attribute to this tag to display background images on the results page. Any color attributes added to this tag override the Search Link Color settings that the Basic Look section sets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-header> </span> </p> </td> 
   <td colname="col2"> <p>The HTML for the Search Results Header as set in the Basic Look section under the Template link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-cdata> ... &lt;/search-cdata> </span> </p> </td> 
   <td colname="col2"> <p>The search-cdata tags are replaced with their XML equivalents: <span class="codeph"> &lt;search-cdata> </span> is replaced with <span class="codeph"> &lt;![CDATA[" and the &lt;/search-cdata> </span> tag is replaced with " <span class="codeph"> ]]> </span>". An XML parser does not parse any information between the open and close tag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-query query-number="XX" encoding="html/javascript/json/perl/url/none"> </span> </p> </td> 
   <td colname="col2"> <p>The query that the visitor entered. The advanced, optional "query-number" attribute controls which numbered query string is output by this tag. For example, <span class="codeph"> &lt;search-query query-number=1> </span> outputs the contents of the <span class="codeph"> sp_q_1 </span> cgi parameter. If "query-number" is not specified, or if query-number is "0", the main query ( <span class="codeph"> sp_q </span>) is output. The optional "encoding" attribute controls whether the output is HTML encoded, JavaScript encoded, Perl encoded, URL encoded or not encoded, for output on the results page. The default value of "encoding" is "html". Normally, you do not need to specify the encoding attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-total> </span> </p> </td> 
   <td colname="col2"> <p>The total count of results for this search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-count> </span> </p> </td> 
   <td colname="col2"> <p>The count of results reported for this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lower> </span> </p> </td> 
   <td colname="col2"> <p>The number of the first result reported for this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-upper> </span> </p> </td> 
   <td colname="col2"> <p>The number of the last result reported for this page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-prev-count> </span> </p> </td> 
   <td colname="col2"> <p>The number of results reported for the previous page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next-count> </span> </p> </td> 
   <td colname="col2"> <p>The number of results reported for the next page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-time> </span> </p> </td> 
   <td colname="col2"> <p>The time in seconds for this search. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-logo> </span> </p> </td> 
   <td colname="col2"> <p>The HTML for the Search logo that is configured for your account, if any. This logo is the image that gives credit to site search/merchandising </p> <p>Most accounts do not have an associated Search logo at this time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-collection all="name"> </span> </p> </td> 
   <td colname="col2"> <p>The collection of the results for this search. The optional "all" attribute is used to give the name of the collection that represents the entire website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-form> ...&lt;/search-form> </span> </p> </td> 
   <td colname="col2"> <p>Inserts begin and end form tags. Inserts the method and action attributes into the begin form tag. Accepts additional attributes including the dir="RTL" attribute for language as well as JavaScript-related "name" and "onSubmit" attributes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-account> </span> </p> </td> 
   <td colname="col2"> <p>Inserts a form input tag which specifies your account number. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-gallery> </span> </p> </td> 
   <td colname="col2"> <p>Inserts a form input tag which specifies the gallery number. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-query query-number="XX"> </span> </p> </td> 
   <td colname="col2"> <p>Inserts a form input tag which specifies the query string. The advanced, optional "query-number" attribute controls which numbered query is used for the form input tag. For example, <span class="codeph"> &lt;search-input-query query-number=1> </span> outputs a form input tag for the <span class="codeph"> sp_q_1 </span> query. If "query-number" is not specified, or if "query-number" is "0", an input tag for the main <span class="codeph"> sp_q </span> query is inserted. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-collections all="name"> </span> </p> </td> 
   <td colname="col2"> <p>Inserts a form select tag and associated HTML which display the collections selection menu. The optional "all" attribute is used to give the name of the collection that represents the entire website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lt> </span> </p> </td> 
   <td colname="col2"> <p>Inserts the output from one of the Search template tags within other HTML or template tags on the results page. <span class="codeph"> &lt;search-lt> </span> inserts a less than character. Use of <span class="codeph"> &lt;search-lt> </span> and <span class="codeph"> &lt;search-gt> </span> provides a way to escape the definition of a tag so that you can use Search template tags as attribute values. When the template is rendered in response to a search, a less-than sign (&lt;) replaces the <span class="codeph"> &lt;search-lt> </span> tag. For example, <span class="codeph"> &lt;search-link> </span> is equivalent to <span class="codeph"> &lt;search-lt>a href="&lt;search-url>"&lt;search-gt> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-gt> </span> </p> </td> 
   <td colname="col2"> <p>Inserts the output from one of the Search template tags within other HTML or template tags on the results page. <span class="codeph"> &lt;search-gt> </span> inserts a greater than character. Use of <span class="codeph"> &lt;search-lt> </span> and <span class="codeph"> &lt;search-gt> </span> provides a way to escape the definition of a tag so that you can use other template tags as attribute values. When the template is rendered in response to a search, a greater-than sign (>) replaces the <span class="codeph"> &lt;search-gt> </span> tag. For example, <span class="codeph"> &lt;search-link> </span> is equivalent to <span class="codeph"> &lt;search-lt>a href="&lt;search-url>"&lt;search-gt> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-param name="param-name" length="XX" encoding="html/javascript/json/perl/url/none"> </span> </p> </td> 
   <td colname="col2"> <p>Returns the value of the cgi parameter named "param-name" from the current search request. The optional "encoding" attribute controls whether the output is HTML encoded, JavaScript encoded, Perl encoded, URL encoded or not encoded, for output on the results page. The default value of "encoding" is "html". Normally, you do not need to specify the encoding attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-trace encoding="html/javascript/ json/perl/url/none"> </span> </p> </td> 
   <td colname="col2"> 
    <!--<p>This global core search template tag outputs a representation of the submitted core search query, including any "fuzzy-search" query term expansions that happen by way of synonyms, sound-alikes, and so forth. </p>--> <p>The <span class="codeph"> encoding </span> attribute is optional; the default value is <span class="codeph"> json </span>. </p> <p> <p>Note:  This tag only has output if <span class="codeph"> sp_trace=1 </span> is specified with the core search query parameters. </p> </p> <p>See row 48 in the table found in <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> Backend search CGI parameters </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Template anchor link tags {#section_3A51D27616C541E2B818CC52B2B856BA}

The following are tags that cause an anchor link to surround the HTML between them. When clicked, the anchor link requests another page of results to display. The optional attribute "count" requests that many results on the page to display. If not specified, the count requested on the current page is used. The advanced, optional "URL" attribute controls the domain to which the associated link is directed. By default the domain is http://search.atomz.com/search/, but you can change this using the URL attribute.

<table id="table_F940A41509A2488DAB04ACC144A3FB8A"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next URL="http://search.yourdomain.com/search/"> ... &lt;/search-next> </span> </p> <p> <span class="codeph"> &lt;search-prev URL="http://search.yourdomain.com/search/"> ... &lt;/search-prev> </span> </p> </td> 
   <td colname="col2"> <p>Displays the next or previous page of the results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-date URL="http://search.yourdomain.com/search/"> ... &lt;/search-sort-by-date> </span> </p> <p> <span class="codeph"> &lt;search-sort-by-score URL="http://search.yourdomain.com/search/"> ... &lt;/search-sort-by-score> </span> </p> </td> 
   <td colname="col2"> <p>Sorts the results by date or by relevance. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-show-summaries URL="http://search.yourdomain.com/search/"> ... &lt;/search-show-summaries> </span> </p> <p> <span class="codeph"> &lt;search-hide-summaries URL="http://search.yourdomain.com/search/"> ... &lt;/search-hide-summaries> </span> </p> </td> 
   <td colname="col2"> <p>Shows or hides the summaries. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Template conditional tags {#section_18D9BC66DE484881932FD2F7EA9D170D}

Tags that let you conditionally include HTML between them.

<table id="table_A1842D42AB8F4F5688AC57C44F817042"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-results> ... &lt;/search-if-results> </span> </p> <p> <span class="codeph"> &lt;search-if-not-results> ...&lt;/search-if-not-results> </span> </p> </td> 
   <td colname="col2"> <p>These tags include HTML if the current page contains any (or no) search results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-prev-count> ... &lt;/search-if-prev-count> </span> </p> <p> <span class="codeph"> &lt;search-if-not-prev-count> ... &lt;/search-if-not-prev-count> </span> </p> <p> <span class="codeph"> &lt;search-if-next-count> ... &lt;/search-if-next-count> </span> </p> <p> <span class="codeph"> &lt;search-if-not-next-count> ... &lt;/search-if-not-next-count> </span> </p> </td> 
   <td colname="col2"> <p>These tags include HTML if the previous page or the next page has any (or none) results associated with it. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-score> ... &lt;/search-if-sort-by-score> </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-score> ... &lt;/search-if-not-sort-by-score> </span> </p> <p> <span class="codeph"> &lt;search-if-sort-by-date> ... &lt;/search-if-sort-by-date> </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-date> ... &lt;/search-if-not-sort-by-date> </span> </p> </td> 
   <td colname="col2"> <p>These tags include HTML if the current page is, or is not, sorted by relevance or by date. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-show-summaries> ... &lt;/search-if-show-summaries> </span> </p> <p> <span class="codeph"> &lt;search-if-hide-summaries> ... &lt;/search-if-hide-summaries> </span> </p> </td> 
   <td colname="col2"> <p>These tags include HTML if the current page is showing or hiding summaries. You can use these tags to include or exclude any portion of the search result. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-input-collections> ... &lt;/search-if-input-collections> </span> </p> <p> <span class="codeph"> &lt;search-if-not-input-collections> ... &lt;/search-if-not-input-collections> </span> </p> </td> 
   <td colname="col2"> <p>These tags include HTML if a collection was specified in the generation of search results for the current page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-advanced> ... &lt;/search-if-advanced> </span> </p> <p> <span class="codeph"> &lt;search-if-not-advanced> ... &lt;/search-if-not-advanced> </span> </p> </td> 
   <td colname="col2"> <p>These tags include HTML if the <span class="codeph"> sp_advanced=1 </span> CGI parameter was specified for the search query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bad-param name="parameter-name"> ... &lt;/search-if-bad-param> </span> </p> <p> <span class="codeph"> &lt;search-if-not-bad-param name="parameter-name"> ... &lt;/search-if-not-bad-param> </span> </p> </td> 
   <td colname="col2"> <p>These tags include or exclude the HTML between them if the given parameter is, or is not, invalid. </p> <p>Currently only the <span class="codeph"> sp_q_location[_#] </span> parameter is supported. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-param name="param-name" value="param-value"> ... &lt;/search-if-param> </span> </p> <p> <span class="codeph"> &lt;search-if-not-param name="param-name" value="param-value"> ... &lt;/search-if-not-param> </span> </p> </td> 
   <td colname="col2"> <p>These advanced tags include the HTML between them based on whether the CGI parameter specified in the "name" attribute has the value specified in the "value" attribute. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-field name="field-name"> ... &lt;/search-if-sort-by-field> </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-field name="field-name"> ... &lt;/search-if-not-sort-by-field> </span> </p> </td> 
   <td colname="col2"> <p>These advanced tags include the HTML between them if the current page is, or is not, sorted by the given field-name. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Template form control tags {#section_45AFC414ACA74825B72FEAA8456F8DD2}

Tags that let you control the default selection state for check boxes, radio buttons, and list boxes within a `<form>` on the search template.

<table id="table_F77D41DADC064DC48AB06A24A00DB472"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tag </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input> </span> </p> </td> 
   <td colname="col2"> <p>Used in a template in place of an <span class="codeph"> &lt;input> </span> tag. When the tag is written to the browser, the word <span class="codeph"> input </span> replaces <span class="codeph"> search-input </span> and all other information in the tag is output as-is. In addition, if the <span class="codeph"> name </span> specified in the tag is listed as a CGI parameter and if the <span class="codeph"> value </span> specified in the tag is the value for that CGI parameter, then the word <span class="codeph"> checked </span> is added at the end of the tag. In this way, you can automatically make the default radio button or checkbox state in your search result the same as the current query. </p> <p>For example, the HTML code for a check box might look like the following: </p> <p> <span class="codeph"> &lt;input type=checkbox name="sp_w" value="exact">No sound-alike matching </span> </p> <p>The corresponding template code for that checkbox is the following: </p> <p> <span class="codeph"> &lt;search-input type=checkbox name="sp_w" value="exact">No sound-alike matching </span> </p> <p>If the CGI parameter string for the query contains <span class="codeph"> sp_w=exact </span>, then the tag written to the browser with the search results looks like the following (the word <span class="codeph"> checked </span> is inserted at the end of the tag): </p> <p> <span class="codeph"> &lt;input type=checkbox name="sp_w" value="exact" checked>No sound-alike matching </span> </p> <p>If the CGI parameter string for the query does not contain <span class="codeph"> sp_w=exact </span>, then the tag written to the browser with the search results looks like the following (the word <span class="codeph"> checked </span> is not listed in the tag): </p> <p> <span class="codeph"> &lt;input type=checkbox name="sp_w" value="exact">No sound-alike matching </span> </p> <p>The <span class="codeph"> &lt;search-input> </span> tag is useful for putting check boxes and radio buttons into your search template. If you have check boxes or radio buttons that you want to add to the <span class="codeph"> &lt;form> </span> in your search template, use <span class="codeph"> &lt;search-input...> </span> in place of <span class="codeph"> &lt;input...> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-select> ... &lt;/search-select> </span> </p> <p> <span class="codeph"> &lt;search-option> ... &lt;/search-option> </span> </p> </td> 
   <td colname="col2"> <p>Drop-down list boxes in a <span class="codeph"> &lt;form> </span> tag are started with a <span class="codeph"> &lt;select> </span> tag and ended with a <span class="codeph"> &lt;/select> </span> tag. The <span class="codeph"> name </span> for the associated CGI parameter is listed inside the <span class="codeph"> &lt;select> </span> tag. Following the <span class="codeph"> &lt;select> </span> tag is a list of <span class="codeph"> &lt;option> </span> tags that specify the values to show inside the list box. </p> <p>The <span class="codeph"> &lt;search-select> </span>, <span class="codeph"> &lt;/search-select> </span>, <span class="codeph"> &lt;search-option> </span>, and <span class="codeph"> &lt;/search-option> </span> tags provide similar functionality to the <span class="codeph"> &lt;search-input> </span> tag. That is, the word <span class="codeph"> selected </span> is automatically added at the end of the <span class="codeph"> &lt;option> </span> tag sent to the browser if the <span class="codeph"> name </span> in the <span class="codeph"> &lt;search-select> </span> tag is listed as a CGI parameter and if the <span class="codeph"> value </span> of that CGI parameter is listed as the <span class="codeph"> value </span> in a particular <span class="codeph"> &lt;search-option> </span> tag. In this way, you can automatically make the default list box choice in your search result the same as the current query. </p> <p>For example, a typical list box looks like the following: </p> <p> 
     <codeblock class="syntax html">
       &lt;select name="sp_x" size=1> 
      &lt;option value="any" selected>Anywhere&lt;/option> 
      &lt;option value="title">Title&lt;/option> 
      &lt;option value="desc">Description&lt;/option> 
      &lt;option value="keys">Keywords&lt;/option> 
      &lt;option value="body">Body&lt;/option> 
      &lt;option value="alt">Alternate text&lt;/option> 
      &lt;option value="url">URL&lt;/option> 
      &lt;option value="target">Target&lt;/option> 
      &lt;/select> 
     </codeblock> </p> <p>The corresponding template code for that list box is the following: </p> <p> 
     <codeblock class="syntax html">
       &lt;search-select name="sp_x" size=1> 
      &lt;search-option value="any">Anywhere&lt;/search-option> 
      &lt;search-option value="title">Title&lt;/search-option> 
      &lt;search-option value="desc">Description&lt;/search-option> 
      &lt;search-option value="keys">Keywords&lt;/search-option> 
      &lt;search-option value="body">Body&lt;/search-option> 
      &lt;search-option value="alt">Alternate text&lt;/search-option> 
      &lt;search-option value="url">URL&lt;/search-option> 
      &lt;search-option value="target">Target&lt;/search-option> 
      &lt;/search-select> 
     </codeblock> </p> <p>If you have list boxes that you want to add to the <span class="codeph"> &lt;form> </span> in your search template, use <span class="codeph"> &lt;search-select...> </span> in place of <span class="codeph"> &lt;select...> </span>, <span class="codeph"> &lt;/search-select> </span> in place of <span class="codeph"> &lt;/select> </span>, <span class="codeph"> &lt;search-option...> </span> in place of <span class="codeph"> &lt;option...> </span>, and <span class="codeph"> &lt;/search-option> </span> in place of <span class="codeph"> &lt;/option> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-field name="field-name" count="XX"> ... &lt;/search-sort-by-field> </span> </p> </td> 
   <td colname="col2"> <p>These advanced tags create an anchor link around the HTML between them. When this anchor is clicked, a page of results sorted on the given field is displayed. The optional <span class="codeph"> count </span> attribute specifies the number of results to display on the result page. If <span class="codeph"> count </span> is omitted, the count used on the current page is used. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Date format strings {#section_4BBDBBEF2B96414497617CD4B52D96E4}

You can use the following conversion specifications in date format strings:

<table id="table_00090E2D245D490FAB5DF7E35600D851"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Date format string </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p> Matches the national representation of the full weekday name, for example, "Monday." The setting in <span class="uicontrol"> Linguistics </span> > <span class="uicontrol"> Words &amp; Languages </span> > <span class="uicontrol"> Language </span> determines the national representation. </p> <p>See <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> About Words &amp; Language </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> Matches the national representation of the abbreviated weekday name, where the abbreviation is the first three characters, for example "Mon." The setting in <span class="uicontrol"> Linguistics </span> > <span class="uicontrol"> Words &amp; Languages </span> > <span class="uicontrol"> Language </span> determines the national representation. </p> <p>See <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> About Words &amp; Language </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> Matches the national representation of the full month name, for example "June." The setting in <span class="uicontrol"> Linguistics </span> > <span class="uicontrol"> Words &amp; Languages </span> > <span class="uicontrol"> Language </span> determines the national representation. </p> <p>See <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> About Words &amp; Language </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> Matches the national representation of the abbreviated month name, where the abbreviation is the first three characters, for example "Jun." The setting in <span class="uicontrol"> Linguistics </span> > <span class="uicontrol"> Words &amp; Languages </span> > <span class="uicontrol"> Language </span> determines the national representation. </p> <p>See <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> About Words &amp; Language </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p>Equivalent to "%m/%d/%y", for example "07/25/13". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> Matches the day of the month as a decimal number (01-31). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> Matches the day of month as a decimal number (1-31). A blank precedes single digits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> Matches the 24-hour clock as a decimal number (00-23). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> Matches the national representation of the abbreviated month name, where the abbreviation is the first three characters, for example "Jun" (the same as %b). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> Matches the 12-hour clock as a decimal number (01-12). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> Matches the day of the year as a decimal number (001-366). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> Matches the (24-hour clock as a decimal number (0-23). A blank precedes single digits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> Matches the hour 12-hour clock as a decimal number (1-12). A blank precedes single digits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> Matches the minute as a decimal number (00-59). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> Matches the month as a decimal number (01-12). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> Matches the national representation of either "ante meridiem" or "post meridiem" as appropriate, for example "PM." The setting in <span class="uicontrol"> Linguistics </span> > <span class="uicontrol"> Words &amp; Languages </span> > <span class="uicontrol"> Language </span> determines the national representation. </p> <p>See <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> About Words &amp; Language </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p>Equivalent to "%H:%M", for example, "13:23". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p>Equivalent to "%I:%M:%S %p", for example, "01:23:45 PM". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S </p> </td> 
   <td colname="col2"> <p> Matches the second as a decimal number (00-60). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p>Equivalent to "%H:%M:%S", for example, "13:26:47". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> Matches the week number of the year (Sunday as the first day of the week) as a decimal number (00-53). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p>Equivalent to "%e-%b-%Y", for example, "25-Jul-2013". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> Matches the year with century as a decimal number, for example, "2013". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> Matches the year without century as a decimal number (00-99). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> Matches the time zone name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> Matches "%". </p> </td> 
  </tr> 
 </tbody> 
</table>

## Language identifiers {#section_0490DECC00E34691ADE5A9ED90A6D911}

The following table contains the language identifiers for each supported language. You can use these identifiers as values for the optional "language" attribute in the following template tags:

* `search-date` and `search-display-field`.

   See [Results loop string tags](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320).

* `search-field-value-list` See [Field value list tags](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1).

* `search-field-value` See [Field value list loop tags](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E).

<table id="table_5960FA4A816C47ECA8D8F1F937558FB5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Language </p> </th> 
   <th colname="col2" class="entry"> <p>Language identifier </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Bulgarian (Bulgaria) </p> </td> 
   <td colname="col2"> <p> bg_BG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (China) </p> </td> 
   <td colname="col2"> <p> zh_CN </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (Hong Kong) </p> </td> 
   <td colname="col2"> <p> zh_HK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (Singapore) </p> </td> 
   <td colname="col2"> <p>zh_SG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinese (Taiwan) </p> </td> 
   <td colname="col2"> <p> zh_TW </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Czech (Czech Republic) </p> </td> 
   <td colname="col2"> <p> cs_CZ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Danish (Denmark) </p> </td> 
   <td colname="col2"> <p> da_DK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dutch (Belgium) </p> </td> 
   <td colname="col2"> <p> nl_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dutch (Netherlands) </p> </td> 
   <td colname="col2"> <p> nl_NL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>English (Australia) </p> </td> 
   <td colname="col2"> <p> en_AU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>English (Canada) </p> </td> 
   <td colname="col2"> <p> en_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>English (Great Britain) </p> </td> 
   <td colname="col2"> <p> en_GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>English (United States) </p> </td> 
   <td colname="col2"> <p> en_US </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>French (Belgium) </p> </td> 
   <td colname="col2"> <p> fr_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>French (Canada) </p> </td> 
   <td colname="col2"> <p>fr_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Finnish (Finland) </p> </td> 
   <td colname="col2"> <p> fi_FI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>French (France) </p> </td> 
   <td colname="col2"> <p> fr_FR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>French (Switzerland) </p> </td> 
   <td colname="col2"> <p> fr_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>German (Austria) </p> </td> 
   <td colname="col2"> <p> de_AT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>German (Germany) </p> </td> 
   <td colname="col2"> <p> de_DE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>German (Switzerland) </p> </td> 
   <td colname="col2"> <p> de_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Greek (Greece) </p> </td> 
   <td colname="col2"> <p> el_GR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Irish Gaelic (Ireland) </p> </td> 
   <td colname="col2"> <p> ga_IE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Italian (Italy) </p> </td> 
   <td colname="col2"> <p> it_IT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Japanese (Japan) </p> </td> 
   <td colname="col2"> <p> ja_JP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Korean (Korea) </p> </td> 
   <td colname="col2"> <p> ko_KR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Norwegian (Norway) </p> </td> 
   <td colname="col2"> <p> no_NO </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Polish (Poland) </p> </td> 
   <td colname="col2"> <p> pl_PL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Portuguese (Brazil) </p> </td> 
   <td colname="col2"> <p> pt_BR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Portuguese (Portugal) </p> </td> 
   <td colname="col2"> <p> pt_PT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Russian (Former Soviet Union) </p> </td> 
   <td colname="col2"> <p> ru_SU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slovak (Slovakia) </p> </td> 
   <td colname="col2"> <p> sk_SK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slovak (Slovenia) </p> </td> 
   <td colname="col2"> <p>sl_SI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spanish (Mexico) </p> </td> 
   <td colname="col2"> <p> es_MX </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spanish (Spain) </p> </td> 
   <td colname="col2"> <p> es_ES </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Swedish (Sweden) </p> </td> 
   <td colname="col2"> <p> sv_SE </p> </td> 
  </tr> 
 </tbody> 
</table>

## Specifying the content-type HTTP header {#section_AEED823E9938448A9EDB2F286D9CFD90}

You can specify the Content-Type HTTP response header by using the following tag:

`<search-content-type-header [content="MIME-type"] [charset="charset-name"]>`

The `content` and `charset` attributes are optional. This tag should appear as early as possible in the template. It is also recommended that it appear before either `<search-html-meta-charset>` or `<search-xml-decl>`, because it affects the behavior of those tags.

If you do not specify the `content` attribute, then the value of `MIME-type` defaults to the value that is set in **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**. If you specify a `content` attribute, it is used as the default `content` attribute for the `<search-html-meta-charset>` tag.

If you do not specify the `charset` attribute, then no `charset` value is written to the `content-type` header.

If you specify `charset="1"` then the actual value for `charset-name` is the value of the `sp_f` CGI parameter. If no `sp_f` CGI parameter is submitted with the search, then the actual value for `charset-name` is read from your account settings. You can view or change the character set that is associated with your account under **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]**.

See [Configuring your personal user information](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

You can choose a specific character set name by listing it as the `charset` value, like `charset="iso-8859-1"` or `charset="Shift-JIS"`.

If you specify a `charset` attribute, then it is used as the default `charset` attribute for the `<search-html-meta-charset>` and `<search-xml-decl>` tags, as well as being output to the `content-type` header.

## Specifying a character set in an HTML template {#section_E0D1816ABB5846BEBE9C26D5980CCBE6}

The default HTML search result templates specify the character set associated with the current account via the following tag:

`<search-html-meta-charset [content="MIME-type"] [charset="charset-name"]>`

The content and charset attributes are optional. This tag must appear in the HTML `<head>` section of the template. This tag results in the following tag on the HTML page generated from the template:

`<meta http-equiv="content-type" content="MIME-type; charset=charset-name">`

If you do not specify the content attribute, then the actual value of `MIME-type` defaults to one of two values. If the `<search-content-type-header>` tag specified a `content` attribute, then that value is used. Otherwise, the value used is the one set in the **[!UICONTROL Templates]** > **[!UICONTROL Settings]** > **[!UICONTROL Content Type]** tab.

If you do not specify the `charset` attribute, then the actual value of `charset-name` defaults to one of two values. If the `<search-content-type-header>` tag specified a `charset` attribute, then that value is used. Otherwise, the actual value for `charset-name` is read from your account settings. You can view or change the character set that is associated with your account under **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]**.

See [Configuring your personal user information](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

If you specify `charset="1"` then the actual value for `charset-name` is the value of the `sp_f` CGI parameter. If no `sp_f` CGI parameter is submitted with the search, then the actual value for `charset-name` is either the value set in the `<search-content-type-header>` tag if it was specified, or the value that is set in your account settings.

You can specify a specific character set name, as in `charset="charset-name"`. For example, `charset="iso-8859-1"` or `charset="Shift-JIS"`.

The `<search-html-meta-charset>` tag is optional. If you remove it, the browser assumes the default values for `content-type`, which is the following: `content="text/html; charset=ISO-8859-1"`. You can also choose to replace the `<search-html-meta-charset>` tag with your own `http-equiv` tag.

## Specifying a character set in an XML template {#section_17DC31CDCC104F5F8081466B41A96E9D}

The default XML search result template specifies the character set associated with the current account by way of the following tag:

`<search-xml-decl [charset="charset-name"]>`

The `charset` attribute is optional. This tag must appear at the top of the template, but after any `<search-content-type-header>` tag. This tag results in the following tag on the XML document that is generated from the template:

`<?xml version="1.0" encoding="charset-name" standalone="yes" ?>`

If you do not specify the `charset`, then the actual value of `charset-name` defaults to one of two values. If `<search-content-type-header>` specified a `charset` attribute, then that value is used. Otherwise, the actual value for `charset-name` is read from your account settings. You can view or change the character set that is associated with your account under **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]**.

See [Configuring your personal user information](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

If you specify `charset="1"` then the actual value for `charset-name` is the value of the `sp_f` CGI parameter. If no `sp_f` CGI parameter is submitted with the search, then the actual value for `charset-name` is either the value that is set in the `<search-content-type-header>` tag if it was specified, or the value that is set in your account settings.

You can specify a specific character set name, as in `charset="charset-name"`, if you so desire. For example, `charset="iso-8859-1" or charset="Shift-JIS"`.

You can choose to replace the `<search-xml-decl>` tag with your own `?xml` tag.

## Including a search template within another {#section_7D1FCD3D9E2340C291E354C9720E8BC0}

To include one search template in another, use the `<search-include>` tag, setting the file attribute to the name of the template file that you want to include as in the following example:

`<search-include file="seo/seo_search_title.tpl" />`

SEO search template segments are in the `seo/` subfolder and normal search templates are in the `templates/` subfolder. Only .tpl files are meaningful to include in this context.

## Managing multiple transport templates for your website {#reference_12AAB3B9F4C74C11956F1DBA95714C2F}

You can control the appearance of search results across your website by using different search transport templates for each area.

<!-- 

r_managing_multiple_templates.xml

 -->

To accomplish this kind of search functionality, you can manage your transport templates in site search/merchandising. Or, you can manage your transport templates in Publish. Like site search/merchandising, Publish lets you edit, preview, and publish multiple search transport templates.

To set up your search forms to use a specific transport template (other than the default), use the `sp_t` query parameter. For example, suppose you have a search template called "clearance" for the marked-down sales area of your website. You use the standard HTML search form with the following additional form code:

`<input type=hidden name="sp_t" value="clearance">`

When a customer clicks a standard form that contains this line of code, the "clearance" search transport template is displayed along with their search results.

See [Using collections in search forms](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

See [Using frames with forms](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

See [Sample advanced search form](../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).
