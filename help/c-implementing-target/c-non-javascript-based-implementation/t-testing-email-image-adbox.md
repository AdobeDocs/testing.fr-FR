---
description: Dynamically test images in email, and even change those images on the
  fly when someone opens the email.
keywords: email;adbox
seo-description: Dynamically test images in email, and even change those images on
  the fly when someone opens the email.
seo-title: Test an email image Adbox
solution: Target
title: Test an email image Adbox
topic: Recommendations
uuid: d0710adb-4649-4b57-9b70-4b49d43fa591
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c228d50443bf2e7ecaff00b2961f535f3c0c7a11

---


# Test an email image Adbox{#test-an-email-image-adbox}

Dynamically test images in email, and even change those images on the fly when someone opens the email.

Redirectors can be used in emails to track clicks and dynamically control which landing page people reach.

Email image testing is achieved through using modified versions of adboxes. Because email clients do not allow cookies to be set, a unique identifier must be generated for each email. This number is appended to the adbox URL and to any redirectors used in the email to track clicks from the email.

>[!NOTE]
>
>Although Target can technically deliver image optimization at open time, each email client handles caching differently, so success will be varied. Regardless of the email service provider used, the email client that the end user uses to open the email (Gmail app, Outlook, Hotmail, and so forth) determines whether the image is actually fetched at open-time. For example, Gmail caches most everything, so the image the end user sees is dependent on when Gmail chooses to call and cache the image.

**Sample code for an email image adbox:**

```
<img src="https://<
<b class="+ topic ph hi-d="" b "="">
 clientcode>.tt.omtrdc.net/m2/​
 <b class="+ topic ph hi-d="" b "="">
  clientcode/ubox/​
  <b class="+ topic ph hi-d="" b "="">
   image?mbox=​
   <b class="+ topic ph hi-d="" b "="">
    email_Header&mboxDefault=​
    <b class="+ topic ph hi-d="" b "="">
     http%3A%2F%2Fwww.domain.com%2Fheader.jpg&​ 
         
     <b class="+ topic ph hi-d="" b "="">
      mboxXDomain=disabled&​
      <b class="+ topic ph hi-d="" b "="">
       mboxSession=123456&​
       <b class="+ topic ph hi-d="" b "="">
        mboxPC=123456" border="0" >

       </b class="+ topic>
      </b class="+ topic>
     </b class="+ topic>
    </b class="+ topic>
   </b class="+ topic>
  </b class="+ topic>
 </b class="+ topic>
</b class="+ topic>
```

Where the bold values are specific to you:

<table id="table_13516D41801B4E58AC6E7724DF168C7B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Value </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>clientcode </p> </td> 
   <td colname="col2"> <p>Your company's client code. Find this in your <span class="codeph"> at.js</span> or <span class="codeph"> mbox.js</span> listed as <span class="codeph"> clientCode='yourclientcode'</span>. This is all lower case and has no special characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>image </p> </td> 
   <td colname="col2"> <p> The offer type. It is always "image" for graphic ads and "page" for redirectors. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>email_header </p> </td> 
   <td colname="col2"> <p>The name of the adbox. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>http%3A%2F%2Fwww.domain.com%2Fheader.jpg </p> </td> 
   <td colname="col2"> <p>The adbox's default content. This must be an absolute reference and must be URL encoded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mboxXDomain=disabled </p> </td> 
   <td colname="col2"> <p> Tells <span class="keyword"> Target</span> to not attempt to set a cookie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mboxSession=123456 and mboxPC=123456 </p> </td> 
   <td colname="col2"> <p>Two values required by <span class="keyword"> Target</span> to merge this user's profile with the existing profile for your site. 123456 is the unique identifier generated per email. Dynamically insert this value into every adbox and redirector URL. This number must be unique for each email sent to each person. If a weekly email is sent to 1,000 people, 1,000 unique IDs need to be generated. </p> <p class="- topic/p ">The unique identifier per email needs to be assigned to the <span class="+ topic/ph pr-d/codeph codeph"> mboxSession</span> and <span class="+ topic/ph pr-d/codeph codeph"> mboxPC</span> in each adbox and redirector URL. The recommended format for this identifier is <span class="+ topic/ph pr-d/codeph codeph"> timestamp-NNNNN</span> where <span class="+ topic/keyword sw-d/varname varname"> NNNNN</span> is a random 5-digit number, but any alphanumeric format will work. Some mass e-mail services and any programming language are capable of generating this unique identifier. </p> </td> 
  </tr> 
 </tbody> 
</table>

