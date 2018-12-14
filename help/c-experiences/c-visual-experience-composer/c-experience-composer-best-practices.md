---
description: Following best practices can help make your experiences work as expected.
  There are also other tips and limitations that you should be aware of when using
  the Visual Experience Composer (VEC).
keywords: visual experience composer;visual experience composer best practices;visual
  experience composer limitations;visual experience composer caveats;vec best practices;vec
seo-description: Following best practices can help make your experiences work as expected.
  There are also other tips and limitations that you should be aware of when using
  the Visual Experience Composer (VEC).
seo-title: Visual Experience Composer Best Practices and Limitations
solution: Target
title: Visual Experience Composer Best Practices and Limitations
topic: Classic
uuid: 8d1d199b-b3d7-4edb-ba05-bd97372a0b9e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Visual Experience Composer Best Practices and Limitations{#visual-experience-composer-best-practices-and-limitations}

Following best practices can help make your experiences work as expected. There are also other tips and limitations that you should be aware of when using the Visual Experience Composer (VEC).

By following these best practices, you are less likely to encounter unexpected problems with the experiences you design.

## Best Practices {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

<table id="table_E1E01D8E51F94B08888A01219AAA5E2C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Best Practice </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>For mbox.js version 57 and later, and for at.js, place the mbox.js or at.js reference at the top of the &lt;head> section of your page. </p> </td> 
   <td colname="col2"> <p>If you also use the Visitor API Service, place the visitor API script above mbox.js or at.js. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>For versions of mbox.js before version 57, place the mbox.js code as low as possible in the &lt;head> section of your page. </p> </td> 
   <td colname="col2"> <p>Place the mbox.js at the end of the &lt;head> section, with no additional declarations after it. Otherwise, any script or link tags will be moved into the &lt;body> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>You can enable the <span class="wintitle"> Enhanced Experience Composer </span> at the account level (enabled for all activities created in the account) or at the individual activity level. </p> </td> 
   <td colname="col2"> <p>To enable the <span class="wintitle"> Enhanced Experience Composer </span> at the account level, click <span class="uicontrol"> Setup </span> > <span class="uicontrol"> Preferences </span>, then toggle the switch to the On position. </p> <p>To enable the <span class="wintitle"> Enhanced Experience Composer </span> at the activity level while creating an activity in the <span class="wintitle"> Visual Experience Composer </span>, click <span class="uicontrol"> Configure </span> > <span class="uicontrol"> URL </span>, then toggle the switch to the On position. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> You can whitelist certain IP addresses if the Enhanced Visual Experience Composer won't load on secure pages on your site. </p> </td> 
   <td colname="col2"> Problems loading the Enhanced Visual Experience Composer can be resolved by whitelisting the following IP addresses. These IP addresses are for Adobe's server used for the Enhanced Experience Composer proxy. They are only required for activity editing. Visitors to your site do not need these IP addresses whitelisted. <p> 
     <p>United States: 52.55.99.45, 54.80.158.92, and 54.204.197.253</p>
     <p>Europe, Middle East, and Africa (EMEA): 52.51.238.221, 52.210.199.44, and 54.72.56.50</p>
     <p>Asia-Pacific (APAC): 52.193.67.35, 54.199.198.109, and 54.199.241.57</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use unique IDs for top-level elements and any other elements that could be good testing/targeting candidates. </p> </td> 
   <td colname="col2"> <p>Anything immediately inside the body element should have a unique ID. If new elements are injected into the body and code moves around, at least the parent elements have an easier way to be recognized. </p> <p>Adobe Target does not require IDs, but using IDs increases the reliability of experiences created with the experience composer. Target uses CSS selectors to modify your content when the experience is delivered. When you edit an experience, the Visual Experience Composer anchors the selector to the closest ancestor with a non-null id attribute to the HTML element being modified. It is, therefore, not advisable to use any mechanism, including JavaScript libraries, that sets or modifies HTML ID attributes. Although those IDs might be available to the Target experience composer for activity creation, if JavaScript modifies IDs, the ID that was used when the experience was created might not be available when the experience runs. If an ID is not available, the selector anchored to the ID fails. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Name CSS classes so they are easily identifiable. </p> </td> 
   <td colname="col2"> <p>When editing CSS classes in the Visual Experience Composer, it is helpful to make the classes easy to identify by using descriptive class names. This helps to ensure that you edit the right CSS classes, and your pages appear as expected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Don't use the <span class="codeph"> !important </span> CSS property when hiding or removing elements. </p> </td> 
   <td colname="col2"> <p>If the <span class="codeph"> !important </span> CSS property is present, changes made by target.js during delivery will be overridden by the site's CSS rules. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avoid using HTML tables for page layouts. </p> </td> 
   <td colname="col2"> <p>Target Standard and Premium uses JavaScript to format a page. It is difficult to modify table-based layouts with JavaScript. Also, table-based layouts might not display the same way in all browsers. For best results, use CSS to create page layouts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Minimize the use of iFrames. </p> </td> 
   <td colname="col2"> <p>It is a good practice to minimize the use of iFrames, to simplify page and test management. The visual experience composer can apply some actions within an iFrame, but some actions, such as resizing, do not work properly. It is difficult to manage and resize pages that use multiple iFrames. As a result, testing iFrame-heavy pages can create problems. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attempt to arrange all dynamic DOM modifications as soon after DOM ready as possible. </p> </td> 
   <td colname="col2"> <p>If your modifications fail to apply before the experience application by target.js, content delivery could be broken. This happens only when there is a DOM change in the hierarchy of a targeted element. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use only plain text or an image tag in your anchor elements. </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> &lt;a>Anchor Text&lt;/a> </span> </p> <p>OR </p> <p> <span class="codeph"> &lt;a href=""> &lt;img src=""> &lt;/img> &lt;/a> </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avoid block-level elements inside an inline element. </p> </td> 
   <td colname="col2"> <p>Block-level elements should not be used inside inline elements like anchor, span, and so on. Doing so causes inline elements to lose their height and width, so the overlay tool in Visual Experience Composer might not work as expected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>When updating offers for classic mboxes, make sure that mbox is created as described at <a href="https://marketing.adobe.com/resources/help/en_US/tnt/help/t_Creating_a_Single_Mbox.html" format="https" scope="external"> Create a Single Mbox </a> in the Target Classic help. </p> </td> 
   <td colname="col2"> <p>If you are considering placing an element or group of elements in an mbox, wrap them in a new div with class <span class="codeph"> mboxDefault </span>: </p> <p> 
     <code>
       &lt;div class="mboxDefault"> //Content goes here &lt;/div> &lt;script> mboxCreate('mboxName'); &lt;/script> 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Don't use the base tag in your website to resolve URLs and links. </p> </td> 
   <td colname="col2"> <p>The Visual Experience Composer manipulates the website behind the scenes, using a proxy server that updated the links. If you add a base tag, the URLs used by the proxy server are resolved again by the browser and appear broken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Using EDIT HTML to manipulate DOM structure can break selectors. </p> </td> 
   <td colname="col2"> <p>For example, if you have taken two actions: </p> <p> 
     <ul id="ul_8DE119C87A6B42BE8CF8097DEF6B32FA"> 
      <li id="li_92AE664EE93342268543D85B3A6DAB86">Added a class to Element 1 </li> 
      <li id="li_2895F928B6D7483D8306DF03AC2B20A7">Edited the HTML for Element 1 </li> 
     </ul> </p> <p>Each change creates a new element in the Visual Experience Composer. Because the second action modifies Element 1, if you delete Element 1, the second action no longer has anything to modify, so the change no longer works. </p> <p>In other words, if you add an element with text, then in a separate action you edit that element with different text, the code editor shows both actions as separate elements. When you edited the element, you created a new element that modifies the original one you created, containing the edited text. If you then delete the original element, the edited text won't be able to find the element that was edited, and will not display. The second element remains in the list of elements, but it does not affect the page because the element it changes no longer exists. </p> <p>See <a href="../../c-experiences/c-visual-experience-composer/c-vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337" format="dita" scope="local"> Element Selectors Used in the Visual Experience Composer </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Use <span class="codeph"> &lt;b> </span> and <span class="codeph"> &lt;i> </span> tags when styling text elements with the rich-text editor. </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_7815FC70CE414D9B99969C890DD13480"> 
      <li id="li_BC70FC033E5740C99F40240F1EE344F3"> For bold text, use &lt;b> rather than <span class="codeph"> &lt;strong> </span>. </li> 
      <li id="li_28736D8B774343448C2D30DBE44C4A19">For italic text, use &lt;i> rather than <span class="codeph"> &lt;em> </span>. </li> 
     </ul> </p> <p> <span class="codeph"> &lt;strong> </span> and <span class="codeph"> &lt;em> </span> tags might cause unexpected results. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Be careful when removing form fields. </p> </td> 
   <td colname="col2"> Certain form fields might be mandatory for submission. Removing those form fields could impact submissions. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Do not include <span class="codeph"> mboxCreate </span>inside scripts. </p> </td> 
   <td colname="col2"> <p>Because <span class="codeph"> mboxCreate </span> uses <span class="codeph"> document.write </span>, it is not recommended to include <span class="codeph"> mboxCreate </span> in scripts. Instead, use <span class="codeph"> mboxDefine </span> and <span class="codeph"> mboxUpdate </span> for the same purpose. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Don't update an html snippet using Target Standard if it requires JavaScript code for its initialization. </p> </td> 
   <td colname="col2"> <p>When an action (Edit HTML) is performed on page components (such Sliders, Carousels and so on), delivery might appear broken. The Visual Experience Composer performs the action after the page component has been instantiated by JavaScript. </p> <p>However, when the content of the page is delivered to visitors, the action is applied before instantiation of the component. Because of this, this component's functionality may or may not break at the time of delivery. Functionality depends on the nature of the script used on his page to define the component. </p> <p>If you test for delivery and it works the first time, it is not guaranteed that it will continue working. There may (or may not) be a race condition. </p> <p> 
     <ul id="ul_DFDC45F4AD8B4AFCB473D6D990BF0945"> 
      <li id="li_009ACBF2ABDF4766862E12A598630B99"> If there is a race condition, delivery will work intermittently. </li> 
      <li id="li_C34FC755E9F74E24B0D8517EEF43E792"> If there is no race condition, it will always work. </li> 
     </ul> </p> <p> Test your page multiple times to make sure delivery works as expected. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Don't use a base tag in your website to resolve URLs and links. </p> </td> 
   <td colname="col2"> <p>When you use the Enhanced Experience Composer, the website is manipulated behind the scenes by a proxy server that updates all link urls to make them work in the proxy. If you add a base tag, all these URLs are resolved by the browser so they appear broken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Important text on the site that might be used for targeting should be kept in HTML code within an element. </p> </td> 
   <td colname="col2"> <p>For example, you cannot target Shopping Cart text in the VEC if your code is like the following: </p> 
    <code>
      &lt;a href="https://www.botanicchoice.com/shop.axd/Cart"> &lt;img alt="Shopping Cart"src="/images/ico-cart.gif">&lt;/img>  Shopping Cart:  &lt;span id="HeaderCartQtyTotal"> 0  &lt;/span>  Items &lt;span id="HeaderCartPriceTotal">&lt;/span> &lt;/a>
    </code> <p> In this example, the entire anchor element is selected in the VEC, which adversely affect other elements if targeting is performed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Don't use <code>top</code> or <code>self</code> variables in JavaScript code. </p> </td> 
   <td colname="col2"> <p>When the Enhanced Experience Composer is enabled, the value of the <span class="codeph"> <span class="varname"> top </span> </span> and <span class="varname"> self </span> variables are updated to disable iframe busting. Use an X-frame-options header to add iframe busting instead of custom JavaScript codes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Always test your website if parameters are added when loading the page. </p> </td> 
   <td colname="col2"> <p>For example, to open www.abc.com, the following url parameters are used: </p> <p> <span class="codeph"> www.abc.com?mboxEdit=1&amp;mboxDisable=1 </span> </p> <p>These parameters enable editing in an iframe. </p> <p>Make sure your website loads as expected after adding parameters like these. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Make sure your page opens as expected in an iframe. </p> </td> 
   <td colname="col2"> <p>Turn OFF iframe busting techniques on your website and check whether it opens as expected within an iframe on a dummy page. For example: </p> <p> 
     <pre>
&lt;!DOCTYPE 
&lt;html> 
&lt;html> 
&lt;head> 
  &lt;meta charset="utf-8"> 
  &lt;meta name="viewport" content="width=device-width"> 
  &lt;title>JS Bin&lt;/title> 
&lt;/head> 
&lt;body> 
  &lt;iframe src="https://www.homedepot.com"&lt;/iframe> 
&lt;/body> 
&lt;/html> 
     </pre> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Caveats {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Consider the following caveats when using the Visual Experience Composer to design your activity.

<table id="table_4DACCF112F914727826B265FE8B792EE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caveat </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>The Move feature does not support z-index. </p> </td> 
   <td colname="col2"> <p>Because there is no z-index functionality, the moved element can't be moved on top of another element. See <a href="../../c-experiences/c-visual-experience-composer/c-experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721" format="dita" scope="local"> Limitations </a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rearranging elements affects click tracking. </p> </td> 
   <td colname="col2"> <p>If an element marked for click tracking is rearranged, the paths of the rearranged elements are changed. As a result, the element in the location where the original element was before it was rearranged is the one whose clicks are tracked. </p> <p> This occurs because both the code to deliver the activity content and the code to track clicks is included in one piece of code that is delivered to the page. If you browse to a different page and set up click tracking, then the activity content code and the click tracking code are delivered to that page. If the click-tracking page has a similar page structure to the page where the test is run, then the test content might also appear on the click-tracking page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inserting an element might not work in a &lt;div> that is an mbox. </p> </td> 
   <td colname="col2"> <p>If an mbox contains an offer, inserting an element may appear as insertBefore and not insertAfter, if the mbox is implemented incorrectly. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>When editing both a parent and child element, edit the parent first. </p> </td> 
   <td colname="col2"> <p>If you swap an image action on an element, then edit the text or HTML on its parent element, delivery issues can occur. The best workflow is to edit the parent element before swapping the image on the child element. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cannot select page element that includes an mbox as a child element. </p> </td> 
   <td colname="col2"> <p>For example, if your page contains: </p> <p> 
     <code>
       &lt;div> &lt;div class="mboxDefault" > ;&lt;/div> ;&lt;script>mboxCreate('myMbox'); &lt;/div> 
     </code> </p> <p> The outer div should not be selected in an experience because the mbox hardcoded in the page still makes a call to Target and receives a response. This response interferes with the response intended for the larger page element. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Proxy IPs may be blocked in customers environment. </p> </td> 
   <td colname="col2"> <p>If you are using Enhanced Experienced Composer on a non-live site, such as a staging environment, you might see timeouts and access denied errors if your site blocks RIPs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>When adding multiple pages, both the experience rail and page rail are opened at the same time. This eventually decreases the width for the Visual Experience Composer to display the site for optimizations. As a result, reflowable sites might start to appear differently than expected in the reduced space. </p> </td> 
   <td colname="col2"> <p>The workaround is to collapse the experience rail and page rail by clicking the left chevron icons on top. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Limitations {#section_F33C2EA27F2E417AA036BC199DD6C721}

<table id="table_BFCC9711F6A94B56B3A9DDC42270B125"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limitation </th> 
   <th colname="col2" class="entry"> Details </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Move feature </p> </td> 
   <td colname="col2"> <p>An element cannot be moved outside a container that is followed by a CSS property. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Only swap offers are available on mboxes. </p> </td> 
   <td colname="col2"> <p>Actions such as Edit Class and Rearrange are not allowed inside an mbox. Mbox content is served by mbox.js. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>You should not rearrange and move the same element. </p> </td> 
   <td colname="col2"> <p>If an element has been moved to another location, and you select the parent container and try to rearrange the child elements, the moved element is not affected and remains where it is. The rearrangement might not appear as desired. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Swap Image Action does not work on an Image in a carousel. </p> </td> 
   <td colname="col2"> <p>If, for example, your page contains a carousel with six images and you want to swap an image with the second image of the carousel, the Swap Image action won't work. </p> <p>The workaround is to select the parent container and use the Edit HTML action to edit the HTML of the carousel to update the image source of the desired image. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Images cannot be resized in an mbox. </p> </td> 
   <td colname="col2"> <p>If you swap an image in an mbox element, then try to resize that image according to the mbox element size, the resizing is not permitted. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>After you swap an image, you cannot select the Edit action. </p> </td> 
   <td colname="col2"> <p>After you swap the image, you cannot edit the Scene7 URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>HTML elements with external source cannot be edited. </p> </td> 
   <td colname="col2"> <p>For example: Video, audio tags, embed, iFrames, frames. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Click tracking does not work for anchor elements that contain anything other than plain text or image tags. </p> </td> 
   <td colname="col2"> <p>For example, click tracking does not work if the element contains JavaScript. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pages must accept URL parameters for the Visual Experience Composer to work. </p> </td> 
   <td colname="col2"> <p>Some sites strip any URL parameters for their pages. However, the Visual Experience Composer requires those parameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>While using a script as part of html, any variables and functions that are accessed from outside should be declared under window namespace. </p> </td> 
   <td colname="col2"> <p>The script is executed within the scope of target.js after the page loads. Therefore, any variable or function that is declared locally is not accessible from outside the script block. </p> <p><b>Incorrect:</b> </p> <p> 
     <code>
       &lt;script> var myVar = 123; function myFunc() { //  } &lt;/script> 
     </code> </p> <p><b>Correct:</b> </p> <p> 
     <code>
       &lt;script> window.myVar = 123; window.myFunc = function() {  // }; &lt;/script> 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inserting an image from the Content library (Scene7) and editing the HTML breaks the image url. </p> </td> 
   <td colname="col2"> <p> 
     <ol id="ol_7578ED0C7C7D4173BFC25D0FEFF0F8C7"> 
      <li id="li_969E12184B144BB8BDC310829B19D7B6">Add an anchor element inside the 'customHeaderMessage' div with some dummy text: <p> 
        <code>
          &lt;a href="#"> &lt;span> Dummy text &lt;/span> &lt;/a> 
        </code> </p> </li> 
      <li id="li_958BF70672364D6AAC5B5624E87C14FF">Select this div using the Insert Element action to insert a image as a sibling of this dummy text div. <p> After image insertion, it looks like : </p> <p> 
        <code>
          &lt;a href="#">  &lt;span> Dummy text &lt;/span> &lt;img src=""> This is inserted Image. &lt;/img> &lt;/a> 
        </code> </p> </li> 
      <li id="li_D4CC0C23497049288B1803BD13593213">Remove the dummy text span. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>The customCode action in the Visual Experience Composer does not work with Internet Explorer 8. </p> </td> 
   <td colname="col2"> <p>Due to IE8 limitations when handling script content, target.js does not support this in IE8. As a workaround, if the page contains jQuery and is exposed on the <span class="codeph"> window </span> object globally, target.js can use deliver the customCode action. Ensure that <span class="codeph"> window.jQuery </span> and <span class="codeph"> window.jQuery.fn.prepend </span> are defined. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Click tracking is supported only on the page on which experiences are created or on the redirected page. </p> </td> 
   <td colname="col2"> <p>Although Browse mode is available in Click Track VEC, it can't be used to add click tracking on a page. </p> </td> 
  </tr> 
 </tbody> 
</table>

