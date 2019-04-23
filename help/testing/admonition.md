---
git-commit: 0e5452ad941d957757295595b4475ae4df4397dc
last-update: '2019-04-08'
pipeline_filename: help/testing/admonition.md
publish-url: https://docs.adobe.com/content/help/en_US.UTF-8/primetime/testing/hello/internal-group/admonition.html
git-commit-file: 53f523daba3d0e275f727f59199f3030689c946a
guide-url: guide-landing.html
guide-title: リリースノート
solution-title: Matt's Test Repo
solution-hub-url: https://docs.ci.corp.adobe.com
solution-image: None
getting-started-url: help/c-gs/c-gs.md
tutorials-url: https://training.adobe.com/training/courses.html#
git-edit: https://git.corp.adobe.com/AdobeDocs/testing.en/tree/master/help/testing/admonition.md
git-issue: https://git.corp.adobe.com/AdobeDocs/testing.en/issues/new
git-filename: help/testing/admonition.md
git-repo: https://git.corp.adobe.com/AdobeDocs/testing.en
translation-type: tm+mt
source-git-commit: 7b1d7dc2884498a3260ca1f2affa096a88196489

---

# ![](/help/assets/premium.png) Admonitions


## Space between emphasis and link problem

There should be a space between **the text and the ** [link](http://www.google.com)


## 1. Testing ordered list start {#foo}


hi

4. One
5. Two
6. Three

## 2. Testing ordered list start {#testing-ordered-list-start}

4. One
5. Two
6. Three


## 3. Testing ordered list start {#n3-testing-ordered-list-start}

4. One
5. Two
6. [Three](#foo)


Hello

4. One
4. Two
4. Three

Superscript:
* x^2
* x<sup>2</sup>

Footnote:
* [footnote]

Insertion:


## Testing asterisk

This is a * test.  An * is cool.

Options marked with an asterisk (*) are not supported...

## Testing bookmarklet

```javascript
(function%20()%20{var%20parts%20=%20window.location.href.split('at_preview_token',2);%20if%20(parts.length%20>%201)%20{window.location.href%20=%20parts[0].concat('at_preview_token=');}%20})();
```

The bookmarklet should then appear on the toolbar for re-use.



## Testing superscript

e=mc<sup>2</sup>


## Testing italics

This is *italics*

This is not \*italics\*.

[[!DNL Adobe Cloud Platform]](https://www.adobe.com)

## Testing BR


| one | two |
|---|---|
| &gt;[!NOTE] hello<br>three | four<br>five<br/>six<a href="http://www.aksjfasjkjahdfkjhakjhdfs.com">BadLink</a> |


* hello<br>there
* hello<br/>there

hi<br>there<br/>again


<table>
<tr>
<td>
one<br>two<br/>three
</td>
<td>
<a href="http://www.alksdjfsdkjf.com">Hello</a>
</td>
</tr>
</table>

>[!NOTE]
>HELLO

* Got to Assets<br/>![](assets/2018-07-24-13-47-56.png)
* help<br/>![](2018-07-24-13-49-21.png)
* Open solution folder (launch.en)<br/>![](2018-07-24-13-51-13.png)
* Click on the ditamap entry to bring up the XML Add On panel<br/>![](2018-07-24-13-52-20.png)
* Navigate to Outputs<br/>![](2018-07-24-13-53-25.png)

## NOTE BLOCK

>[!NOTE]
>This is a note block

## WARNING BLOCK

>[!WARNING]
>This is a warning block

## CAUTION BLOCK

>[!CAUTION]
>This is a caution block

## IMPORTANT BLOCK

>[!IMPORTANT]
>This is an important block

## TIP BLOCK

>[!TIP]
>This is a tip block
