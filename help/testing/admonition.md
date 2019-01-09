---
source-git-commit: 4728718a1378e779cd2647f453967c256ce3a5cb
translation-type: tm+mt

---
# ![](/help/assets/premium.png) Admonitions

## Testing asterisk

This is a * test.  An * is cool.

Options marked with an asterisk (*) are not supported...

## Testing bookmarklet

# Hello

```javascript
(function%20()%20{var%20parts%20=%20window.location.href.split('at_preview_token',2);%20if%20(parts.length%20>%201)%20{window.location.href%20=%20parts[0].concat('at_preview_token=');}%20})();
```

The bookmarklet should then appear on the toolbar for re-use.



## Markdown Link
[Hello World](javascript:%28function%28%29%7Balert%28%22Hello%20World%22%29%7D%29%28%29%3B)

[QA Bookmarklet](javascript
(function%20()%20{var%20parts%20=%20window.location.href.split('at_preview_token',2);%20if%20(parts.length%20>%201)%20{window.location.href%20=%20parts[0].concat('at_preview_token=');}%20})();)


## HTML Link
<a href="javascript
(function%20()%20{var%20parts%20=%20window.location.href.split('at_preview_token',2);%20if%20(parts.length%20>%201)%20{window.location.href%20=%20parts[0].concat('at_preview_token=');}%20})();">QA Bookmarklet</a>

## Testing superscript

e=mc<sup>2</sup>


## Testing italics

This is *italics*

This is not \*italics\*.

[[!DNL Adobe Cloud Platform]](https://www.adobe.com)

## Testing BR


| one | two |
|---|---|
| >[!NOTE] hello<br>three | four<br>five<br/>six<a href="http://www.aksjfasjkjahdfkjhakjhdfs.com">BadLink</a> |


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
