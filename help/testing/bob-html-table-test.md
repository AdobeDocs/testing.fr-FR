---
description: aucun
seo-description: aucun
seo-title: Modèles
title: Modèles
topic: Appendices,Recherche de site et merchandising
internal: n
snippet: y (en)
translation-type: tm+mt
source-git-commit: a0151abf5f67d32c60125575d07aa1fd088b3643

---

# Modèles{#templates}

## Modèles{#concept_A5CFB6BD805D49459A96219AF1B17842}

## Étiquettes de modèle de présentation{#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64}

Une liste des balises et attributs de recherche/merchandising de site pour les modèles de présentation.

<!-- 

r_presentation_template_tags.xml

 -->

Un modèle de présentation est un fichier HTML qui inclut des balises de modèle de présentation que la recherche/le merchandising du site définit. Ces balises indiquent comment les résultats de recherche que les clients voient sont formatés.

## Déclarations{#section_82C5CA734D2941EB858FEFE3B695D2EC}

Les déclarations sont des balises spéciales de déclaration guidée que vous pouvez définir en haut d'un modèle de présentation de haut niveau. Toutes les déclarations ultérieures sont ignorées, y compris les déclarations dans les modèles inclus.

<table id="table_892D11DDDFBE4DDE85374961A9F8973D"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-content-type-header content="content-type"&gt; </span>&lt;/guided-content-type-header&gt; </p> </td> 
   <td colname="col2"> <p>Par défaut, le modèle de présentation est renvoyé avec un type de mime de texte/html. Vous pouvez modifier le type de contenu utilisé avec cette balise. </p> <p>Déclarez cette balise aussi haut que possible dans votre modèle de présentation. N'ajoutez pas d'autre texte sur la même ligne avec cette balise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-xml-declare [charset="charset" ]=""&gt; </span>&lt;/guided-xml-declare&gt; </p> </td> 
   <td colname="col2"> <p> Si vous retournez XML, vous pouvez utiliser cette balise pour créer la déclaration XML. Faites de cette balise la première ligne de votre modèle de présentation. Lorsque vous utilisez cette balise, le type de contenu est automatiquement réglé sur <span class="codeph"> le texte/xml, sauf si vous l'infirmez avec &lt;guided-content-type-header&gt; </span> dans la première ligne.&lt;/guided-content-type-header&gt; Si vous ne spécifiez pas un charset, il est par défaut sur UTF-8. Cette balise donne les résultats suivants dans votre document XML : </p> <p> <span class="codeph">&lt;?xml version="1.0" encoding="charset-name" standalone="yes"?&gt;</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Résultats{#section_06F249C9F6AE4B0F8C32117E19DCC905}

<table id="table_BBC8FA6BDA5040838C9F0BD4F293C6E3"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--><span class="codeph"> &lt;guided-results [gsname="searchname" ]=""&gt;&lt;/guided-results&gt;</span> </p> </td> 
   <td colname="col2"> <p>L'étiquette de résultats guidés définit les limites d'une boucle de résultats. N'importe quel ensemble de <span class="codeph"> résultats peut </span> être consulté en spécifiant un attribut gsname. Si <span class="codeph"> aucun nom </span> gsname n'est donné, les résultats de recherche par défaut sont affichés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--><span class="codeph"> &lt;guided-result-link [gsname="fieldname" ]="" [attr="value" ]+=""&gt;&lt;/guided-result-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Pour créer un lien vers un <span class="codeph"> résultat donné, </span> utilisez l'étiquette de lien de résultat guidé. En définissant <span class="codeph"> un </span> attribut gsname, vous pouvez utiliser un champ à partir de l'index au lieu de l'étiquette standard "loc" qui fait référence à l'"url de recherche". Tous les autres attributs, tels que la classe et la cible, peuvent également être passés, qui sont la sortie dans l'étiquette d'ancrage résultante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--><span class="codeph"> &lt;guided-result-img gsname="fieldname" [attr="value" ]+=""&gt; </span>&lt;/guided-result-img&gt; </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;guided-result-img&gt; </span> L'étiquette aide à créer des balises <span class="codeph"> d'image plutôt que d'intégrer des variables à l'intérieur d'une étiquette </span> img brute.&lt;/guided-result-img&gt; </p> <p>Spécifiez le champ à utiliser <span class="codeph"> pour </span> le chemin d'image dans l'attribut gsname. Le résultat <span class="codeph"> est </span> une balise img avec tous les attributs HTML standard que vous avez défini, passé à travers. Donc, l'exemple suivant: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-result-img gsname="thumbnail"  class="thumb"  border="0"&gt;&lt;/guided-result-img gsname="thumbnail"&gt; 
     </codeblock> </p> <p>Devient: </p> <p> 
     <codeblock class="syntax html">
       &lt;img src="prod8172.jpg" class="thumb"  border="0"&gt;&lt;/img src="prod8172.jpg" class="thumb"&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 1/31/13; search-eng version does not have [escape...] Added ijson on 8/28/2015--><span class="codeph"> &lt;guided-result-field gsname="fieldname" [escape="html|url|js|json|ijson|0" ]/=""&gt; </span>&lt;/guided-result-field&gt; </p> </td> 
   <td colname="col2"> <p> Toute information à présenter dans les résultats <span class="codeph"> est affichée sous forme d'étiquette &lt;guided-result-field&gt; </span> <span class="codeph"> (sauf lorsque vous utilisez des balises génératrices automatiques telles que &lt;guided-result-img&gt; </span> l'étiquette).&lt;/guided-result-img&gt; &lt;/guided-result-field&gt; </p> <p>Spécifiez le nom du <span class="codeph"> champ </span>d'index de recherche dans gsname . La chaîne exacte passée est sortie dans le modèle. </p> <p>Vous pouvez spécifier une option d'évasion si vous voulez que ce champ s'échappe différemment de ce qui a été spécifié dans le modèle de transport. </p> <p>Cet encodage est appliqué sur le dessus de tout codage spécifié dans le modèle de transport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--added 1/31/13 from search-eng version--><span class="codeph">&lt;guided-if[-not]-result-field gsname="fieldname&gt;&lt;/guided-if-result-field&gt; </span> gsname=""&gt;&lt;/guided-if[-not]-result-field gsname="fieldname&gt;&lt;/guided-if-result-field&gt; &lt;a2/&gt;&gt; </p> </td> 
   <td colname="col2"> <p>Cet ensemble de balises conditionnelles est vrai s'il y a du contenu dans le champ spécifique à afficher. S'il n'y a pas de contenu, la condition est fausse. Vous pouvez utiliser les balises pour décider si le HTML environnant est affiché ou non s'il n'existe pas de valeur, ou si une image différente est affichée, et ainsi de suite. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-result-field gsname="thumbnail"&gt; 
          &lt;guided-result-img gsname="thumbnail" class="thumb" &gt;&lt;/guided-result-img gsname="thumbnail" class="thumb" &gt; 
      &lt;guided-else-result-field&gt; 
          &lt;img src="nothumb.jpg" class="nothumb" &gt;&lt;/img src="nothumb.jpg" class="nothumb" &gt; 
      &lt;/guided-else-result-field&gt;&lt;/guided-if-result-field gsname="thumbnail"&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--updated to match search-eng version, 1/31/13--> 
     <codeblock>
       &lt;guided-if[-not]-result-wrap&gt; 
      &lt;guided-else-result-wrap&gt; 
      &lt;/guided-else-result-wrap&gt;&lt;/guided-if[-not]-result-wrap&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Lors de l'affichage des résultats dans les colonnes, cette balise est utilisée pour identifier si le résultat actuel marque la fin d'une colonne. </p> <p>Lorsque la condition Boolean est vraie, HTML est ajouté à la fin du résultat pour terminer la ligne et commencer un nouveau. Quand il est le dernier, une nouvelle ligne n'est pas commencée. </p> <p><span class="codeph"> &lt;guided-if-not-last&gt;Voir </span> pour en savoir plus sur cette balise.&lt;/guided-if-not-last&gt; </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-result-wrap&gt; 
            
           &lt;guided-if-not-last&gt; 
               &lt;div&gt; 
           &lt;/div&gt;&lt;/guided-if-not-last&gt; 
       &lt;/guided-if-result-wrap&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version, 1/31/13--><span class="codeph"> &lt;guided-results-found [gsname="searchname" ]/=""&gt; </span>&lt;/guided-results-found&gt; </p> </td> 
   <td colname="col2"> <p>Retourne un 1 si la demande de recherche back-end a retourné des résultats et 0 si elle n'a pas. Si <span class="codeph"> aucun nom </span> gsname n'est spécifié, l'étiquette suppose la recherche principale. Cette balise est utile pour transmettre la logique aux routines JavaScript. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--><span class="codeph"> &lt;guided-results-total [gsname="searchname" ]/=""&gt; </span>&lt;/guided-results-total&gt; </p> </td> 
   <td colname="col2"> <p>Retourne le nombre total de résultats dans l'ensemble de résultats spécifié. Suppose la recherche par <span class="codeph"> défaut </span> lorsqu'aucun nom gsname n'est donné. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--><span class="codeph"> &lt;guided-results-lower [gsname="searchname" ]/=""&gt; </span>&lt;/guided-results-lower&gt; </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre de résultats du résultat inférieur sur la page pour l'ensemble de résultats spécifié. Suppose la recherche par <span class="codeph"> défaut </span> lorsqu'aucun nom gsname n'est donné. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--><span class="codeph"> &lt;guided-results-upper [gsname="searchname" ]/=""&gt; </span>&lt;/guided-results-upper&gt; </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre de résultats du résultat supérieur sur la page pour l'ensemble de résultats spécifié. Suppose la recherche par <span class="codeph"> défaut </span> lorsqu'aucun nom gsname n'est donné. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 
     <codeblock>
       &lt;guided-if[-not]-results-found [gsname="searchname" ]=""&gt; 
      &lt;guided-else[-not]-results-found&gt; 
      &lt;/guided-else[-not]-results-found&gt;&lt;/guided-if[-not]-results-found&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Affiche le contenu lorsque les résultats sont trouvés. Ou, ne montre pas de résultats HTML lorsque les résultats ne sont pas trouvés. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-results-found gsname="products"&gt; 
          &lt;guided-results gsname="products"&gt;... 
           
      &lt;guided-else-results-found&gt; 
           Aucun résultat n'a été trouvé. 
      &lt;/guided-else-results-found&gt;&lt;/guided-results gsname="products"&gt;&lt;/guided-if-results-found gsname="products"&gt; 
      &lt;/guided-if-results-found&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-result-title&gt;&lt;/guided-result-title&gt;</span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;guided-result-title&gt; </span> L'étiquette donne la valeur du <span class="codeph"> champ de modèle de transport de titre spécifié avec&lt;title&gt;</span> étiquette de transport.&lt;/title&gt;&lt;/guided-result-title&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-result-description&gt;&lt;/guided-result-description&gt;</span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;guided-result-description&gt; </span> L'étiquette donne la valeur du <span class="codeph"> champ de modèle de transport de description spécifié avec &lt;description&gt; </span> l'étiquette&lt;/description&gt; &lt;/guided-result-description&gt; de transport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-result-loc&gt;&lt;/guided-result-loc&gt;</span> </p> </td> 
   <td colname="col2"> <p>&lt;&gt; <span class="codeph"> L'étiquette guidée-résultat-locMD </span> donne de la <span class="codeph"> valeur du champ de modèle de transport loc spécifié avec &lt;loc&gt; </span> l'étiquette&lt;/loc&gt; de transport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-result-field gsname="fieldname"&gt; 
      &lt;guided-else-result-field&gt; 
      &lt;/guided-else-result-field&gt;&lt;/guided-if-result-field&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Vrai s'il y a du contenu dans le champ spécifique à afficher. S'il n'y a pas de contenu, la condition est fausse. Utilisez les balises pour décider si le HTML environnant est affiché ou non si une valeur n'existe pas, ou si une image différente est affichée, et ainsi de suite. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-result-field gsname="thumbnail"&gt; 
           &lt;guided-result-img gsname="thumbnail" class="thumb"&gt;&lt;/guided-result-img gsname="thumbnail" class="thumb"&gt; 
      &lt;guided-else-result-field&gt; 
           &lt;img src="nothumb.jpg" class="nothumb"&gt;&lt;/img src="nothumb.jpg" class="nothumb"&gt; 
      &lt;/guided-else-result-field&gt;&lt;/guided-if-result-field gsname="thumbnail"&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-result-attribute-table gsname="tablename"&gt; </span>&lt;/guided-result-attribute-table&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise fournit une boucle à travers <span class="codeph"> la table d'attribut définie dans le modèle de transport avec &lt;attribute_table&gt; </span> l'étiquette&lt;/attribute_table&gt; de transport. Il <span class="codeph"> y &lt;guided-result-attribute-table-field&gt; </span> &lt;/guided-result-attribute-table-field&gt; a une balise pour afficher les valeurs de champ de table d'attribut. En outre, il <span class="codeph"> est possible d'utiliser la balise de champ </span> de résultat guidé simple à l'intérieur de la boucle pour afficher d'autres champs de résultats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-result-attribute-table-field gsname="fieldname" [escape="html|url|js|json|0" ]/=""&gt; </span>&lt;/guided-result-attribute-table-field&gt; </p> </td> 
   <td colname="col2"> <p>Affiche le champ de table d'attribut tel que défini dans le modèle de transport. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-results&gt;...&lt;ul&gt; 
      &lt;guided-result-attribute-table gsname="downloads"&gt; 
        &lt;li&gt; 
           &lt;&gt;&lt;guided-result-attribute-table-field gsname="download_link" &gt;&lt;/guided-result-attribute-table-field gsname="download_link" &gt;"&gt; 
               &lt;guided-result-attribute-table-field gsname="download_title" &gt;&lt;/guided-result-attribute-table-field gsname="download_title" &gt; 
            (&lt;guided-result-field gsname="title"&gt;&lt;/guided-result-field gsname="title"&gt;)&lt;/li&gt; 
       
      &lt;/guided-result-attribute-table gsname="downloads"&gt;&lt;/ul&gt;...&lt;/guided-results&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release in October 2014--><span class="codeph"> &lt;guided-trace [gsname="searchname" ]/=""&gt; </span>&lt;/guided-trace&gt; </p> </td> 
   <td colname="col2"> <p>Produit les données de trace trouvées dans les données de trace dans la section générale de la sortie de données JSON par le modèle de transport pour la recherche donnée. </p> <p>Si aucun nom de <span class="codeph"> </span> recherche n'est donné, par défaut est supposé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30, 2014)--><span class="codeph"> &lt;guided-result-trace&gt;&lt;/guided-result-trace&gt;</span> </p> </td> 
   <td colname="col2"> <p>Sorties du contenu JSON trouvé dans les résultats - trace zetons les informations de la sortie de données JSON par le modèle de transport pour le résultat de recherche actuel. </p> <p>Cette balise n'est valable que dans la <span class="codeph"> &lt;guided-results&gt;&lt;/guided-results&gt; </span> boucle. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Facettes{#section_EA4C5678D5864B89BAB4D0DFE62A4624}

Les facettes sont des composants de navigation qui vous laissent forer dans les résultats de recherche. Vous pouvez utiliser les balises de facettes pour afficher diverses facettes sur votre modèle de présentation. Vous faites référence aux facettes par nom.

<table id="table_9C1183C074444179A0C296248A3C0BA1"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 02/27/2014--><span class="codeph"> &lt;guided-dynamic-facets&gt;&lt;/guided-dynamic-facets&gt;</span> </p> </td> 
   <td colname="col2"> 
    <!--NEW 2/2/2014--> <p>Un contexte de boucle pour toutes les facettes dynamiques pour une recherche donnée. </p> <p><span class="codeph"> &lt;guided-facet&gt; </span> L'étiquette de modèle de présentation est modifiée de <span class="codeph"> sorte que l'attribut gsname soit automatiquement fourni par le &lt;guided-dynamic-facets&gt; </span> contexte&lt;/guided-dynamic-facets&gt; &lt;/guided-facet&gt; de boucle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-display-name gsname=" <span class="varname"> facetname </span>"&gt;&lt;/guided-facet-display-name&gt;</span> </p> </td> 
   <td colname="col2"> <p>Retourne l'étiquette d'affichage de la facette. </p> <p>Si la facette <span class="codeph"> utilise l'étiquette &lt;display-name&gt; </span> sur le modèle de transport, le contenu de cette balise devient l'étiquette.&lt;/display-name&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--><span class="codeph"> &lt;guided-facet-rail&gt;&lt;/guided-facet-rail&gt;</span> </p> </td> 
   <td colname="col2"> <p> Définit une section sur le modèle de présentation qui est utilisé comme un modèle répétitif pour chaque facette dans le rail facette. </p> <p> Chaque facette qui appartient au rail à facettes utilise cette section pour évaluer sa production. </p> <p>Ce qui suit est un exemple d'un rail de facette : </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-rail&gt; 
        &lt;guided-facet&gt; 
          &lt;guided-facet-display-name&gt;&lt;/guided-facet-display-name&gt;...&lt;/guided-facet&gt; 
        &lt;/guided-facet-rail&gt; 
     </codeblock> </p> <p>Notez que les balises suivantes n'ont pas besoin d'attribut <span class="codeph"> gsname </span> lorsque la marque intérieure <span class="codeph"> &lt;guided-facet-rail&gt; </span> comme valeur est déterminée dynamiquement au moment de la recherche et est correctement substituée:&lt;/guided-facet-rail&gt; </p> 
    <ul id="ul_5B5ACAFD2B8848DDB27471AB9DA7BE6E"> 
     <li id="li_5A07E78D51FE4708879DD742C877FFFF">face guidée </li> 
     <li id="li_B875DCACD7AB4FC890A456A6939AB657">guide-facet-affichage-nom </li> 
     <li id="li_B70450749E864DE7BA401E3CD6EF5EB3">guided-facet-total-count </li> 
     <li id="li_DECDF5EF6FF7454F86C236D322F2BFEA">guided-facet-undo-link (en) </li> 
     <li id="li_176949227AC14E8CA643A419E10F7B5A">guidé-facet-undo-path </li> 
     <li id="li_B32D981281744462BC680F6EFEAC0069">comportement guidé-facet </li> 
    </ul> <p>Les critères <span class="wintitle"> de tri </span> sur la page Facet Rail déterminent la position des facettes. Vous pouvez choisir l'ordre de tri de la liste de déclassement de la méthode sort facets. </p> <p> 
     <!--NEW 02/27/2014-->Cette balise peut accepter en option <span class="codeph"> une valeur d'attribut gsname de 'dynamic'faitts </span>, qui fournit un contexte de boucle pour toutes les facettes dynamiques de cette recherche. Ce rail à facettes prédéfini est également exposé dans <span class="codeph"> l'interface utilisateur Business Rules pour action push facet </span>X dans le rail à facettes ''dynamic'facettes' pour positionner Y ". </p> <p>voir. </p> <p>Voir aussi . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match current search-eng version 1/31/13--><span class="codeph"> &lt;guided-facet gsname=" <span class="varname"> facetname </span>" height=" <span class="varname"> 60px </span>" width=" <span class="varname"> 120px </span>"&gt;&lt;/guided-facet&gt;</span> </p> </td> 
   <td colname="col2"> <p>Utilisez <span class="codeph"> </span> l'étiquette à facettes guidées pour définir une zone dans laquelle toutes les balises de facettes se rapportent à une facette spécifique. Cette balise est également une balise Boolean qui cache tout le contenu si aucune valeur dans la facette n'existe. Dans un tel cas, il est inutile de démonter les valeurs de la facette). </p> <p>Les attributs de hauteur et de largeur sont facultatifs et les dimensions sont spécifiées en pixels (px). Le Visual Rule Builder (VRB) utilise ces deux attributs et affiche une boîte pointillée comme espace interactif lorsque la facette est cachée. </p> <p> Lorsque le nom d'affichage est dans la facette et que la facette est cachée, le nom est également caché. Toutefois, si le nom est en dehors de la <span class="codeph"> facette, vous ne pouvez masquer le nom que si une balise de zone </span> ou une <span class="codeph"> balise guidée-si-facet-visible </span> est enroulée autour d'elle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--><span class="codeph"> &lt;guided-if[-not]-facet-long [gsname="facetname" ]=""&gt;&lt;/guided-if[-not]-facet-long&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette balise conditionnelle est vraie lorsque le nombre de valeurs de facettes est supérieur au seuil de longueur défini dans la configuration. Utilisez-le pour afficher une facette comme un élément d'interface interface (comme une liste tronquée ou une boîte de défilement) lorsque la liste est trop longue. </p> <p> 
     <codeblock class="syntax xml">
       &lt;guided-facet name="category"&gt; 
          &lt;guided-if-facet-long&gt; 
              &lt;select&gt; 
                  &lt;guided-facet-values&gt; 
                      &lt;guided-facet-option &gt;&lt;/guided-facet-option &gt; 
                  &lt;/guided-facet-values&gt; 
              &lt;/select&gt; 
          &lt;guided-else-facet-long&gt; 
              &lt;guided-facet-values&gt; 
                  &lt;guided-facet-value-link&gt;&lt;guided-facet-value &gt;&lt;/guided-facet-value &gt; 
              &lt;/guided-facet-value-link&gt;&lt;/guided-facet-values&gt; 
          &lt;/guided-else-facet-long&gt;&lt;/guided-if-facet-long&gt; 
      &lt;/guided-facet name="category"&gt; 
     </codeblock> </p> <p>Vous pouvez également utiliser cette condition <span class="codeph"> en dehors </span> du contexte d'un bloc à facettes <span class="codeph"> guidée </span> s'est nommé en faisant référence à une facette spécifique directement par l'utilisation de l'attribut gsname. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-long gsname="category"&gt;La facette de catégorie est très longue!&lt;/guided-if-facet-long gsname="category"&gt; 
      &lt;/guided-if-facet-long&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--><span class="codeph"> &lt;guided-if[-not]-facet-selected [gsname="facetname" ]=""&gt;&lt;/guided-if[-not]-facet-selected&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette balise conditionnelle est vraie lorsque la facette est cliqué au moins une fois et qu'une valeur facette est actuellement sélectionnée. Il est utilisé pour afficher ou masquer les balises HTML ou gs selon qu'une facette a été cliqué. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet name="category"&gt; 
          &lt;guided-if-facet-selected&gt;Cette facette a été sélectionnée.&lt;/guided-if-facet-selected&gt;&lt;/guided-facet name="category"&gt;Vous ne pouvez plus l'affiner. 
          &lt;guided-else-facet-selected&gt; 
          &lt;guided-facet-values&gt; 
              &lt;guided-facet-value-link&gt;&lt;guided-facet-value &gt;&lt;/guided-facet-value &gt; 
          &lt;/guided-facet-value-link&gt;&lt;/guided-facet-values&gt; 
           
      &lt;/guided-else-facet-selected&gt; 
     </codeblock> </p> <p>Vous pouvez également utiliser cette condition <span class="codeph"> en dehors </span> du contexte d'un bloc à facettes <span class="codeph"> guidée </span> s'est nommé en faisant référence à une facette spécifique directement par l'utilisation de l'attribut gsname. </p> <p> 
     <codeblock>
       &lt;guided-if-facet-selected gsname="category"&gt;La facette de la catégorie est sélectionnée!&lt;/guided-if-facet-selected gsname="category"&gt; 
      &lt;/guided-if-facet-selected&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--><span class="codeph"> &lt;guided-if[-not]-facet-single [gsname="facetname" ]=""&gt;&lt;/guided-if[-not]-facet-single&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette balise conditionnelle est vraie lorsqu'il n'y a qu'une seule valeur facette. Utilisez l'étiquette pour modifier l'affichage de la facette lorsqu'elle n'a pas la capacité d'affiner les résultats. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet name="category"&gt; 
          &lt;guided-if-facet-single&gt;La facette n'est pas refinable.&lt;/guided-if-facet-single&gt;&lt;/guided-facet name="category"&gt; 
          &lt;guided-else-facet-single&gt; 
              &lt;guided-facet-values&gt; 
                  &lt;guided-facet-value-link&gt;&lt;guided-facet-value &gt;&lt;/guided-facet-value &gt; 
              &lt;/guided-facet-value-link&gt;&lt;/guided-facet-values&gt; 
           
      &lt;/guided-else-facet-single&gt; 
     </codeblock> </p> <p>Vous pouvez également utiliser cette condition <span class="codeph"> en dehors </span> du contexte d'un bloc à facettes <span class="codeph"> guidée </span> s'est nommé en faisant référence à une facette spécifique directement par l'utilisation de l'attribut gsname. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-single gsname="category"&gt;Il n'y a qu'une seule valeur dans la facette de la catégorie!&lt;/guided-if-facet-single gsname="category"&gt; 
      &lt;/guided-if-facet-single&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Added 7/15/2014--><span class="codeph"> &lt;guided-if[-not]-facet-multiselect [gsname="facetname" ]=""&gt;&lt;/guided-if[-not]-facet-multiselect&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette étiquette conditionnelle est vraie lorsque la facette est multi-sélection. Utilisez l'étiquette pour modifier l'affichage de la facette à l'intérieur <span class="codeph"> &lt;guided-facet-rail&gt; </span> ou <span class="codeph"> &lt;guided-dynamic-facets&gt; </span> des balises.&lt;/guided-dynamic-facets&gt; &lt;/guided-facet-rail&gt; </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-rail&gt; 
        &lt;guided-facet&gt; 
          &lt;guided-facet-display-name&gt;&lt;/guided-facet-display-name&gt; 
          &lt;guided-if-facet-multiselect&gt; 
       ... 
       &lt;guided-else-facet-multiselect&gt; 
       ... 
       &lt;/guided-else-facet-multiselect&gt;&lt;/guided-if-facet-multiselect&gt; 
          ...&lt;/guided-facet&gt; 
        &lt;/guided-facet-rail&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--><span class="codeph"> &lt;guided-facet-values [gsname=" <span class="varname"> facetname </span>" ]=""&gt;&lt;/guided-facet-values&gt;</span> </p> </td> 
   <td colname="col2"> <p>Il s'agit de la balise de l'itérateur de boucle de valeur facette. Vous pouvez le définir dans <span class="codeph"> le contexte </span> d'un bloc à facettes <span class="codeph"> <span class="varname"> guidées </span> </span>nommé, auquel cas vous pouvez omettre le nom gsname . Ou, vous pouvez le <span class="codeph"> définir en </span> dehors de n'importe quel bloc à facettes guidée, mais il faudrait l'attribut <span class="codeph"> <span class="varname"> gsname </span> </span> pour identifier quel ensemble de valeurs de facettes sont affichés. </p> <p>Vous pouvez également utiliser cette balise pour afficher les <span class="codeph"> valeurs de </span> facettes en dehors du contexte d'un bloc à facettes guidées nommé. Vous faites référence directement à <span class="codeph"> <span class="varname"> une facette spécifique en utilisant l'attribut gsname. </span> </span> </p> <p> 
     <codeblock class="syntax html">
       &lt;script&gt; 
           registerFacetValues('category', '&lt;guided-facet-values gsname="category"&gt;&lt;guided-facet-value/&gt;,&lt;/guided-facet-values&gt;'); 
      &lt;/script&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--><span class="codeph"> &lt;guided-facet-value [escape="html|url|js|json|0" ]/=""&gt; </span>&lt;/guided-facet-value&gt; </p> </td> 
   <td colname="col2"> <p>Sortie de la chaîne de la valeur actuelle de la facette. </p> <p>Par défaut, la valeur est HTML échappé. Vous pouvez utiliser l'option d'évasion pour modifier la façon dont la valeur est échappée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--><span class="codeph"> &lt;guided-facet-count&gt;&lt;/guided-facet-count&gt;</span> </p> </td> 
   <td colname="col2"> <p>Produit le nombre de résultats qui correspondent à la valeur actuelle de la facette. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--><span class="codeph"> &lt;guided-facet-value-link [attr="value" ]+=""&gt;&lt;/guided-facet-value-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Crée un lien autour de la chaîne de valeur de la facette pour le visiteur du site à cliquer. Le chemin est automatiquement généré pour réduire les résultats par la valeur actuelle de la facette. Il prend en charge le passage de tout attribut directement à l'étiquette d'ancrage. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values&gt; 
          &lt;guided-facet-value-link class="facetlink"&gt;&lt;guided-facet-value &gt;&lt;/guided-facet-value &gt; 
      &lt;/guided-facet-value-link class="facetlink"&gt;&lt;/guided-facet-values&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 
     <codeblock>
       &lt;guided-if-facet-value-selected&gt; 
      &lt;guided-else-facet- value-selected=""&gt; 
      &lt;/guided-else-facet-&gt;&lt;/guided-if-facet-value-selected&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Modifie l'affichage de la valeur de la facette lorsqu'elle est actuellement sélectionnée. S'il a déjà été choisi, dans la plupart des cas, il n'est plus lié. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values&gt; 
           &lt;guided-if-facet-value-selected&gt; 
               &lt;b&gt;&lt;guided-facet-value&gt;&lt;/guided-facet-value&gt;&lt;/b&gt; 
           &lt;guided-else-facet-value-selected&gt; 
               &lt;guided-facet-link&gt;&lt;guided-facet-value&gt;&lt;/guided-facet-value&gt;&lt;/guided-facet-link&gt;    
           &lt;/guided-else-facet-value-selected&gt;&lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 
     <codeblock>
       &lt;guided-if[-not]-facet-value-ghost&gt; 
      &lt;guided-else[-not]-facet-value-ghost&gt; 
      &lt;/guided-else[-not]-facet-value-ghost&gt;&lt;/guided-if[-not]-facet-value-ghost&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Modifie l'affichage de la valeur de la facette lorsqu'il s'agit d'une valeur fantôme. Lorsqu'une valeur facette est une valeur fantôme, elle est généralement affichée dans le texte italique pour indiquer que la valeur est manquante ou « fantôme ». </p> <p>L'extrait de code suivant est un exemple d'un bloc de facettes : </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values&gt; 
          &lt;guided-if-facet-value-selected&gt; 
              &lt;b&gt;&lt;guided-facet-value &gt;&lt;/guided-facet-value &gt;(&lt;guided-facet-count &gt;&lt;/guided-facet-count &gt;)&lt;/b&gt; &lt;guided-else-facet-value-selected&gt;&lt;guided-if-facet-value-ghost&gt; &lt;i&gt; &lt;guided-facet-value &gt; &lt;/guided-facet-value &gt; ( 0)&lt;/i&gt; &lt;guided-else-facet-value-ghost&gt;&lt;guided-facet-link class="link"&gt; &lt;guided-facet-value &gt; &lt;/guided-facet-value &gt; ( )&lt;guided-facet-count &gt;&lt;/guided-facet-count &gt; 
              &lt;/guided-facet-link class="link"&gt; 
                  &lt;/guided-else-facet-value-ghost&gt; 
                           
                      &lt;/guided-if-facet-value-ghost&gt; 
                       
          &lt;/guided-else-facet-value-selected&gt; 
                  &lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--><span class="codeph"> &lt;guided-facet-undo-link gsname=" <span class="varname"> facetname </span>"&gt;&lt;/guided-facet-undo-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Affiche un lien d'annuler une facette donnée. S'il existe des facettes multi-sélects, ce lien désélectionne toutes les valeurs de la facette donnée. Donne un nom à la facette. Si la facette n'est pas actuellement sélectionnée, le lien est le chemin actuel. </p> <p>Ce qui suit est un exemple de l'utilisation de cette balise : </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-selected gsname="category"&gt; 
          &lt;guided-facet-undo-link gsname="category"&gt;Catégorie Annuler 
      &lt;/guided-facet-undo-link gsname="category"&gt;&lt;/guided-if-facet-selected gsname="category"&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-long [gsname=" [gsname=""&gt;&lt;/guided-if-facet-long [gsname="&gt; 
      <varname>
        facetname 
      </varname>"]&gt;&lt;guided-else-facet-long&gt;&lt;/guided-else-facet-long&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette balise conditionnelle est vraie lorsque le nombre de valeurs de facettes est supérieur au seuil de longueur défini dans la configuration. Utilisez-le pour afficher une facette comme un élément d'interface utilisateur différent (comme une liste tronquée ou une boîte de défilement) lorsque la liste est trop longue. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet gsname="category"&gt; 
           &lt;guided-if-facet-long&gt; 
               &lt;div class="long_facet"&gt; 
                   &lt;guided-facet-values&gt;
                       &lt;guided-facet-link&gt;&lt;guided-facet-value&gt;&lt;/guided-facet-value&gt;&lt;/guided-facet-link&gt; 
                   &lt;/guided-facet-values&gt; 
                
           &lt;guided-else-facet-long&gt; 
               &lt;div class="facet"&gt; 
                   &lt;guided-facet-values&gt; 
                       &lt;guided-facet-link&gt;&lt;guided-facet-value&gt;&lt;/guided-facet-value&gt;&lt;/guided-facet-link&gt; 
                   &lt;/guided-facet-values&gt; 
                
           &lt;/div class="facet"&gt;&lt;/guided-else-facet-long&gt;&lt;/div class="long_facet"&gt;&lt;/guided-if-facet-long&gt; 
       &lt;/guided-facet gsname="category"&gt; 
     </codeblock> </p> <p>Vous pouvez également utiliser cette condition <span class="codeph"> en dehors </span> du contexte d'un bloc à facettes <span class="codeph"> <span class="varname"> guidée </span> </span> s'est nommé en faisant référence à une facette spécifique directement par l'utilisation de l'attribut gsname. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-long gsname="category"&gt;La facette de catégorie est très longue!&lt;/guided-if-facet-long gsname="category"&gt; 
      &lt;/guided-if-facet-long&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-selected [gsname="facetname" ]=""&gt; 
      &lt;guided-else-facet-selected&gt;&lt;/guided-else-facet-selected&gt;&lt;/guided-if-facet-selected&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette balise conditionnelle est vraie lorsque la facette est cliqué au moins une fois et qu'une valeur facette est actuellement sélectionnée. Il peut être utilisé pour afficher ou masquer des balises HTML ou gs selon qu'une facette est cliqué. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet gsname="category"&gt; 
           &lt;guided-if-facet-selected&gt;Cette facette a été sélectionnée.&lt;/guided-if-facet-selected&gt;&lt;/guided-facet gsname="category"&gt;Vous ne pouvez plus l'affiner. 
           &lt;guided-else-facet-selected&gt; 
               &lt;guided-facet-values&gt; 
                   &lt;guided-facet-link&gt;&lt;guided-facet-value&gt;&lt;/guided-facet-value&gt;&lt;/guided-facet-link&gt; 
               &lt;/guided-facet-values&gt; 
            
      &lt;/guided-else-facet-selected&gt; 
     </codeblock> </p> <p>Vous pouvez également utiliser cette condition <span class="codeph"> en dehors </span> du contexte d'un bloc à facettes <span class="codeph"> guidée </span> s'est nommé en faisant référence à une facette spécifique directement par l'utilisation de l'attribut gsname. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-selected gsname="category"&gt;La facette de la catégorie est sélectionnée!&lt;/guided-if-facet-selected gsname="category"&gt; 
      &lt;/guided-if-facet-selected&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-single [gsname=" [gsname=""&gt;&lt;/guided-if-facet-single [gsname="&gt; 
      <varname>
        facetname 
      </varname>"]&gt;&lt;guided-else-facet-single&gt;&lt;/guided-else-facet-single&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette balise conditionnelle est vraie lorsqu'il n'y a qu'une seule valeur facette. Il peut être utilisé pour modifier l'affichage de la facette lorsqu'il n'a pas la capacité d'affiner les résultats. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet gsname="category"&gt; 
           &lt;guided-if-facet-single&gt;La facette n'est pas refinable.&lt;/guided-if-facet-single&gt;&lt;/guided-facet gsname="category"&gt; 
           &lt;guided-else-facet-single&gt; 
               &lt;guided-facet-values&gt; 
                   &lt;guided-facet-link&gt;&lt;guided-facet-value&gt;&lt;/guided-facet-value&gt;&lt;/guided-facet-link&gt; 
               &lt;/guided-facet-values&gt; 
            
      &lt;/guided-else-facet-single&gt; 
     </codeblock> </p> <p>Vous pouvez également utiliser cette condition <span class="codeph"> en dehors </span> du contexte d'un bloc à facettes <span class="codeph"> <span class="varname"> guidée </span> </span> s'est nommé en faisant référence à une facette spécifique directement par l'utilisation de l'attribut gsname. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-facet-single gsname="category"&gt;Il n'y a qu'une seule valeur dans la facette de la catégorie!&lt;/guided-if-facet-single gsname="category"&gt; 
      &lt;/guided-if-facet-single&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-has-values [gsname=" [gsname=""&gt;&lt;/guided-if-facet-has-values [gsname="&gt; 
      <varname>
        facetname 
      </varname>"]&gt;&lt;guided-else-facet-has-values&gt;&lt;/guided-else-facet-has-values&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette condition vous permet de vérifier si la facette spécifiée a des valeurs à tous. Vous pouvez l'utiliser pour montrer une autre facette au lieu d'une facette vide. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-total-count gsname=" <span class="varname"> facetname </span>"&gt;&lt;/guided-facet-total-count&gt;</span> </p> </td> 
   <td colname="col2"> <p>Produit le nombre total de résultats qui se situent dans la facette donnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-value gsname=" <span class="varname"> associated custom facet value </span>" [escape="html|url|js|json|0" ]/=""&gt; </span>&lt;/guided-facet-value&gt; </p> </td> 
   <td colname="col2"> <p>Sortie de la chaîne d'une valeur qui est associée à la facette. Vous pouvez avoir 0 champs ou plus associés à une facette. Avoir des champs associés est rare et pour prendre en charge ce que vous configurez le modèle de transport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-facet-value gsname=" <span class="varname"> associated custom facet value </span>"&gt;&lt;/guided-if-facet-value&gt;&lt;guided-else-facet-value&gt; </span>&lt;/guided-else-facet-value&gt; </p> </td> 
   <td colname="col2"> <p>Teste si la valeur de la facette a une valeur de champ associée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-link [attr=" <span class="varname"> value </span>" ]+=""&gt;&lt;/guided-facet-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Crée un lien autour de la chaîne de valeur de la facette pour que le client clique. Le chemin est automatiquement généré pour réduire les résultats par la valeur actuelle de la facette. Il prend en charge le passage de tout attribut directement à l'étiquette d'ancrage. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values&gt; 
           &lt;guided-facet-link class="facetlink"&gt;&lt;guided-facet-value&gt;&lt;/guided-facet-value&gt; 
      &lt;/guided-facet-link class="facetlink"&gt;&lt;/guided-facet-values&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-value-path [escape="html|url|js|json|0" ]/=""&gt; </span>&lt;/guided-facet-value-path&gt; </p> </td> 
   <td colname="col2"> <p>Crée votre propre lien vers une valeur facette. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values&gt; 
           &lt;guided-lt&gt;&lt;/guided-lt&gt;un href&lt;guided-facet-value-path&gt;&lt;/guided-facet-value-path&gt;" "&lt;guided-gt&gt;&lt;/guided-gt&gt;&lt;guided-facet-value&gt;&lt;/guided-facet-value&gt; 
      &lt;/guided-facet-values&gt; 
     </codeblock> </p> <p>Par défaut, la valeur est URL échappé. Vous pouvez, cependant, ajouter une autre couche d'encodage en spécifiant quel mode d'évasion vous souhaitez utiliser au moyen du paramètre d'échappement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-value-children&gt;&lt;/guided-facet-value-children&gt;</span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;guided-facet-values&gt;Comme </span> itérer à travers chaque valeur facette, cette étiquette itère à travers toutes les valeurs de l'enfant d'une facette nichée.&lt;/guided-facet-values&gt; À l'intérieur de cette balise, utilisez les balises de facettes typiques pour créer des liens, créer des liens de défaire et afficher des valeurs de facettes. Cette balise <span class="codeph"> doit être à l'intérieur &lt;guided-facet-values&gt; </span> parce qu'elle fait le nid en boucle.&lt;/guided-facet-values&gt; </p> <p>Un exemple d'utilisation de cette balise est le suivant : </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-facet-values&gt; 
        &lt;&gt;&lt;guided-facet-value &gt;&lt;/guided-facet-value &gt;'&gt;&lt;guided-facet-value &gt;&lt;/guided-facet-value &gt; (&lt;guided-facet-count &gt;&lt;/guided-facet-count &gt;) 
        &lt;guided-if-facet-value-has-children&gt; 
         &lt;guided-facet-value-children&gt; 
          &lt;&gt;&lt;guided-facet-value &gt;&lt;/guided-facet-value &gt;'&gt;&lt;guided-facet-value &gt;&lt;/guided-facet-value &gt; (&lt;guided-facet-count &gt;&lt;/guided-facet-count &gt;) 
         &lt;/guided-facet-value-children&gt; 
        &lt;/guided-if-facet-value-has-children&gt; 
      &lt;/guided-facet-values&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-value-has-children&gt; 
      &lt;guided-else-facet- value-has-children=""&gt; 
      &lt;/guided-else-facet-&gt;&lt;/guided-if-facet-value-has-children&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Tests si la valeur actuelle de la facette a des valeurs enfantines. Recommandé d'utiliser <span class="codeph"> avant d'utiliser les &lt;guided-facet-value-children&gt; </span> balises.&lt;/guided-facet-value-children&gt; La clause "autre" est facultative. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-facet-value-above-length-threshold&gt;&lt;/guided-if[-not]-facet-value-above-length-threshold&gt;

    &amp;lt;guided-else[-not]-facet-value-above-length-threshold&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-above-length-threshold&amp;gt;
    &lt;/codeblock&gt; &lt;/p&gt; &lt;/td&gt;
<td colname="col2"> <p>Détermine si la valeur actuelle de la facette dans la boucle des valeurs de facettes est supérieure au seuil de longueur. Il est généralement utilisé pour afficher uniquement les valeurs inférieures au seuil sur une longue facette (à moins que l'utilisateur ait précédemment sélectionné un lien « Voir plus » affiché sous la facette). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-facet-value-equals-length-threshold&gt; 
      &lt;guided-else[-not]-facet-value-equals-length-threshold&gt; 
      &lt;/guided-else[-not]-facet-value-equals-length-threshold&gt;&lt;/guided-if[-not]-facet-value-equals-length-threshold&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Détermine si la valeur actuelle de la facette dans la boucle de valeurs de facettes est égale au seuil de longueur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-value-undo-link&gt;&lt;/guided-facet-value-undo-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Affiche un lien d'annuler une valeur facette sélectionnée donnée. Utilisez-le pour afficher un lien d'annuler à côté d'une valeur facette sélectionnée. Étant donné que ce lien d'annuler ne déjoue que cette valeur sélectionnée particulière, il diffère de <span class="codeph"> &lt;guided-facet-undo-link&gt; </span> celui qui désélectionne toutes les valeurs sélectionnées.&lt;/guided-facet-undo-link&gt; </p> <p> <p>Remarque : Si la facette n'a pas de comportement multi-sélect, les deux liens d'annuler ont le même comportement. Autrement dit, la facette ne peut avoir qu'une seule valeur sélectionnée. </p> </p> <p>Si la facette n'est pas actuellement sélectionnée, le lien est le chemin actuel. Utilisez cette balise <span class="codeph"> uniquement dans une </span> boucle de valeurs guidées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>30 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-value-undo-path&gt;&lt;/guided-facet-value-undo-path&gt;</span> </p> </td> 
   <td colname="col2"> <p>Créez votre propre lien de défaire la valeur de votre propre facette. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>31 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-undo-path gsname=" <span class="varname"> facetname </span>"&gt;&lt;/guided-facet-undo-path&gt;</span> </p> </td> 
   <td colname="col2"> <p>Créez votre propre lien de défaire la facette. </p> <p> Semblable à <span class="codeph"> &lt;guided-facet-undo-link&gt; </span> l'étiquette, sauf qu'il vous donne le chemin brut pour construire votre propre lien de défaire.&lt;/guided-facet-undo-link&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>32 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet-value-matches facetname=" facetname=""&gt;&lt;/guided-if-facet-value-matches facetname="&gt; 
      <varname>
        facetname 
      </varname>« valeur »&lt;guided-else-facet-value-matches&gt; 
      &lt;/guided-else-facet-value-matches&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Afficher sous condition HTML lorsque la facette donnée a la valeur sélectionnée ou unique "valeur". Cet ensemble de balises est souvent utilisé pour afficher une facette basée sur la valeur sélectionnée dans une autre facette. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>33 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-facet-behavior gsname=" <span class="varname"> facetname </span>"&gt;&lt;/guided-facet-behavior&gt;</span> </p> </td> 
   <td colname="col2"> <p>Déterminez le comportement d'une facette, comme normal, collant ou multi-sélection. Il est utile pour les clients qui reçoivent des résultats XML et qui souhaitent modifier dynamiquement la façon dont la facette est affichée en fonction de son comportement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>34 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-facet[-not]-visible gsname=" gsname=""&gt;&lt;/guided-if-facet[-not]-visible gsname="&gt; 
      <varname>
        real-facet (en anglais seulement) 
      </varname>"&gt;&lt;guided-else-facet[-not]-visible&gt;&lt;/guided-else-facet[-not]-visible&gt;

    et lt;/guided-if-facet[-pas]-visible et gt; 
    &lt;p&gt;
<td colname="col2"> <p>Le contenu que cette balise enveloppe est soit caché, soit révélé en fonction de l'état de visibilité de la facette. Si une règle d'entreprise cache ou révèle directement la facette, tout contenu à l'intérieur de la facette est caché ou révélé. Il n'est pas nécessaire que ces étiquettes s'enroulent autour de la facette. </p> <p> Une utilisation courante pour cette balise est de masquer le nom d'affichage lorsque le nom est en dehors de la facette. Enveloppant cette balise autour du nom d'affichage fait disparaître le nom lorsque la facette est cachée. </p> <p>Cette balise remplace la zone et présente bon nombre des mêmes avantages de performance que l'utilisation des zones. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb{#section_9B39B71FA6EC49FA8D88AD8A3BA987F7}

<table id="table_752EFE34541E41C6AA521970E40D74E2"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-breadcrumb [gsname=" <span class="varname"> breadcrumbname </span>" ]=""&gt;&lt;/guided-breadcrumb&gt;</span> </p> </td> 
   <td colname="col2"> <p>L'étiquette de boucle pour la chapelure. Tout contenu entre les balises d'ouverture et de clôture est itéré pour chaque numéro de requête de l'état actuel. </p> <p>Si <span class="codeph"> <span class="varname"> le </span> </span> nom gsname est omis, alors la chapelure nommée "par défaut" est utilisée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-breadcrumb-link [gsname="goto|remove|drop" ]="" [attr="value" ]+=""&gt;&lt;/guided-breadcrumb-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Crée un lien dans la chapelure. Le comportement par défaut est le comportement "goto". Si le lien se comporte <span class="codeph"> <span class="varname"> différemment, </span> </span> utilisez l'attribut optionnel gsname pour spécifier « supprimer » ou « laisser tomber ». Tout attribut inclus dans l'étiquette est transmis à l'étiquette d'ancrage résultante. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-breadcrumb&gt; 
           &lt;guided-breadcrumb-link gsname="remove" class="bc_link"&gt; 
               &lt;guided-breadcrumb-value&gt;&lt;/guided-breadcrumb-value&gt; 
            
      &lt;/guided-breadcrumb-link gsname="remove" class="bc_link"&gt;&lt;/guided-breadcrumb&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-breadcrumb-value&gt;&lt;/guided-breadcrumb-value&gt;</span> </p> </td> 
   <td colname="col2"> <p>L'étiquette de valeur imprime la valeur transformée de l'itération actuelle de chapelure. Il n'est utilisé que <span class="codeph"> dans le </span> contexte d'un bloc de chapelure guidée. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-breadcrumb&gt; 
           &lt;guided-breadcrumb-link&gt; 
               &lt;guided-breadcrumb-value&gt;&lt;/guided-breadcrumb-value&gt; 
           &lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-breadcrumb-label&gt;&lt;/guided-breadcrumb-label&gt;</span> </p> </td> 
   <td colname="col2"> <p>L'étiquette produit une étiquette pour une valeur de chapelure détaillant quelle facette a été sélectionnée pour générer cet article de chapelure. Il n'est utilisé que <span class="codeph"> dans le </span> contexte d'un bloc de chapelure guidée. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-breadcrumb&gt; 
           &lt;guided-breadcrumb-link&gt; 
               &lt;guided-breadcrumb-label&gt;&lt;/guided-breadcrumb-label&gt;:&lt;guided-breadcrumb-value&gt;&lt;/guided-breadcrumb-value&gt; 
           &lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if-breadcrumb-label&gt; 
      &lt;guided-else- breadcrumb-label=""&gt; 
      &lt;guided-if-breadcrumb-label&gt;&lt;/guided-if-breadcrumb-label&gt;&lt;/guided-else-&gt;&lt;/guided-if-breadcrumb-label&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette étiquette conditionnelle est utilisée pour afficher le contenu sous condition si la valeur actuelle de la chapelure a une étiquette. Il est utilisé pour afficher uniquement les étiquettes et le contenu relatif lorsqu'une étiquette existe réellement. Il n'est utilisé que <span class="codeph"> dans le </span> contexte d'un bloc de chapelure guidée. </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-breadcrumb&gt; 
           &lt;guided-breadcrumb-link&gt; 
               &lt;guided-if-breadcrumb-label&gt; 
                   &lt;guided-breadcrumb-label&gt;&lt;/guided-breadcrumb-label&gt;:&lt;/guided-if-breadcrumb-label&gt; 
           &lt;guided-breadcrumb-value&gt;&lt;/guided-breadcrumb-value&gt;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-breadcrumb-path [gsname="goto|remove|drop" ]/=""&gt; </span>&lt;/guided-breadcrumb-path&gt; </p> </td> 
   <td colname="col2"> <p>Utilisé pour construire votre propre lien de chapelure. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Menus{#section_1D489ADF041F4351A66E5D5742125CA8}

<table id="table_323B2C09835442DBA51DC39F5848665F"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-menu gsname="menuname"&gt;&lt;/guided-menu&gt;</span> </p> </td> 
   <td colname="col2"> <p>Il s'agit de l'étiquette d'itérateur de boucle de valeur du menu. Utilisez <span class="codeph"> l'attribut </span> gsname pour identifier l'ensemble d'éléments de menu affiché. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-menu-item-link [attr="value" ]+=""&gt;&lt;/guided-menu-item-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Vous donne l'URL pour affiner la recherche en cours pour l'élément de menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-menu-item-option [attr="value" ]+=""&gt;&lt;/guided-menu-item-option&gt;</span> </p> </td> 
   <td colname="col2"> <p>En règle générale, un menu s'affiche dans un contrôle de sélection sur un modèle. Cette balise facilite la construction du contrôle de sélection car elle génère le HTML pour générer l'option pour le contrôle de sélection. </p> <p>Par exemple, le bloc de code suivant : </p> <p> 
     <codeblock class="syntax html">
       &lt;select name="sort" onchange="gcGo(this);"&gt; 
      &lt;guided-menu gsname="sort"&gt; 
      &lt;guided-menu-item-option&gt;&lt;/guided-menu-item-option&gt; 
       
      &lt;/guided-menu gsname="sort"&gt;&lt;/select name="sort" onchange="gcGo(this);"&gt; 
     </codeblock> </p> <p>Peut générer HTML comme suit: </p> <p> 
     <codeblock class="syntax html">
       &lt;select name="sort" onchange="gcGo(this);"&gt; 
        &lt;option value="?sort=relevance;sp_sfvl_field=product-type|category|size;" selected="selected"&gt;Tri par tri de pertinence&lt;option value="?sort=avail-code;sp_sfvl_field=product-type|category|size;"&gt;par tri de disponibilité par&lt;option value="?sort=price;sp_sfvl_field=product-type|category|size;"&gt;prix 
      &lt;/option value="?sort=price;sp_sfvl_field=product-type|category|size;"&gt;  
        &lt;/option value="?sort=avail-code;sp_sfvl_field=product-type|category|size;"&gt; 
        &lt;/option value="?sort=relevance;sp_sfvl_field=product-type|category|size;" selected="selected"&gt;&lt;/select name="sort" onchange="gcGo(this);"&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-menu-item-value&gt;&lt;/guided-menu-item-value&gt;</span> </p> </td> 
   <td colname="col2"> <p>Renvoie la chaîne de la valeur associée au menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-menu-item-label&gt;&lt;/guided-menu-item-label&gt;</span> </p> </td> 
   <td colname="col2"> <p>Renvoie la chaîne de l'étiquette associée au menu. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-menu-item-path&gt;&lt;/guided-menu-item-path&gt;</span> </p> </td> 
   <td colname="col2"> <p>Retourne la chaîne de chemin. Utilisez la balise si vous souhaitez ajouter un paramètre au chemin et créer un lien personnalisé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if-menu-item-selected&gt; 
      &lt;guided-else-menu- item-selected=""&gt; 
      &lt;/guided-else-menu-&gt;&lt;/guided-if-menu-item-selected&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Renvoie un 1 ou 0 indiquant si l'élément de menu actuel est sélectionné. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pagenav Pagenav{#section_2EE397635C514BBC8D668278EA314F35}

Les balises de navigation de page peuvent être utilisées pour créer un ensemble de liens permettant à un utilisateur de parcourir les résultats de recherche.

<table id="table_2B8DFA07CAEE4B8BA156FD55DC9E7068"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-pages&gt;&lt;/guided-pages&gt;</span> </p> </td> 
   <td colname="col2"> <p>L'étiquette de boucle pour la navigation de page. Tout contenu entre les balises d'ouverture et de fermeture est itéré pour chaque page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-page-link [attr="value" ]+=""&gt;&lt;/guided-page-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Crée un lien dans la navigation de page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-page-link gsname="first|prev|next|last|viewall|viewpages" [attr="value" ]+=""&gt;&lt;/guided-page-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Crée un lien vers la première page, la page précédente, la suivante ou la dernière. Il peut également créer un lien pour afficher toutes les pages sur une seule page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-page-number&gt;&lt;/guided-page-number&gt;</span> </p> </td> 
   <td colname="col2"> <p> Renvoie une chaîne avec le numéro de page actuel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if-page-selected&gt; 
      &lt;guided-else-page- selected=""&gt; 
      &lt;/guided-else-page-&gt;&lt;/guided-if-page-selected&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cet ensemble de balises conditionnelles est vrai si la page qui est actuellement itérée est sélectionnée. Il est généralement utilisé pour afficher différemment le numéro de page dans le contrôle de navigation de page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-page-prev&gt; 
      &lt;guided-else-page- prev=""&gt; 
      &lt;/guided-else-page-&gt;&lt;/guided-if[-not]-page-prev&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p> Cet ensemble de balises conditionnelles est vrai si la page actuelle a une page précédente. Il est généralement utilisé pour afficher un lien précédent dans la navigation de page, quand il est logique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-page-next&gt; 
      &lt;guided-else-page- next=""&gt; 
      &lt;/guided-else-page-&gt;&lt;/guided-if[-not]-page-next&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p> Cet ensemble de balises conditionnelles est vrai si la page actuelle a une page suivante. Il est généralement utilisé pour afficher un lien précédent dans la navigation de page, quand il est logique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-page-viewall&gt; 
      &lt;guided-else-page- viewall=""&gt; 
      &lt;/guided-else-page-&gt;&lt;/guided-if[-not]-page-viewall&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p> Lorsqu'une recherche retourne un ensemble de résultats volumineux, vous ne pouvez pas offrir la possibilité d'afficher tous les résultats. Par conséquent, vous pouvez utiliser cet ensemble de balises conditionnelles pour déterminer quand afficher le lien Afficher tous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-page-viewpages&gt; 
      &lt;guided-else-page- viewpages=""&gt; 
      &lt;/guided-else-page-&gt;&lt;/guided-if[-not]-page-viewpages&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Vous pouvez utiliser cet ensemble de balises conditionnelles pour déterminer quand afficher le lien Afficher les pages. Il est généralement utilisé pour permettre à un client de voir certaines pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if&gt;&lt;/guided-if&gt;<!--[-not]-->-page-link gsnameMD"first-prev" 
      next'last'viewall'viewpages"

    et lt;guided-else-page-link et gt; 
et lt;/guided-if[-not]-page-link et     gt; 
    &lt;p&gt;
<td colname="col2"> <p>Tests si la navigation de page a une première page, page précédente, page suivante, et ainsi de suite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-page-total&gt;&lt;/guided-page-total&gt;</span> </p> </td> 
   <td colname="col2"> <p> Retourne une chaîne avec le nombre total de pages de résultats de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-pagination gsname="pagination_name"&gt;&lt;/guided-pagination&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Utilisez <span class="codeph"> l'étiquette de </span> pagination guidée pour définir une zone dans laquelle toutes les balises de pagination se rapportent à un paramètre de pagination spécifique au cas où vous auriez peu de paramètres de navigation de page définis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-page-path[gsname="first|prev|&gt;&lt;/guided-page-path[gsname="first|prev|&gt;

    next'last'viewall'viewpages]/ et gt; 
    &lt;p&gt;
<td colname="col2"> <p>Crée votre propre lien dans la navigation de page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-page-high-eq-last&gt; 
      &lt;guided-else-page- high-eq-last=""&gt; 
      &lt;/guided-else-page-&gt;&lt;/guided-if-page-high-eq-last&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Tests si la page la plus haute de la navigation de page est égale au nombre total de pages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-page-low-eq-first&gt; 
      &lt;guided-else-page-low-eq-first&gt;&lt;/guided-else-page-low-eq-first&gt;&lt;/guided-if-page-low-eq-first&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Tests si la page la plus basse de la navigation de page est égale à celle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-page-is-multipage&gt; &lt;guided-else-page-is-multipage&gt; &lt;/guided-else-page-is-multipage&gt;&lt;/guided-if-page-is-multipage&gt;</span> </p> </td> 
   <td colname="col2"> <p>Teste s'il y a une seule page de résultats ou plusieurs pages de résultats. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recherches récentes{#section_8CD907521F584257B475595B01A5964B}

Vous pouvez utiliser des balises de recherche récentes pour créer un ensemble de liens qui laissent un utilisateur exécuter rapidement une recherche précédente, comme dans l'exemple suivant :

```
<guided-if-recent-searches> 
    <span>Recent Searches</span><br/> 
    <guided-recent-searches> 
        <guided-recent-searches-link><guided-recent-searches-value></guided-recent-searches-link><br/> 
    </guided-recent-searches> 
    <guided-recent-searches-clear-link>Clear Recent Searches</guided-recent-searches-clear-link> 
</guided-if-recent-searches>
```

<table id="table_FBDC9DB8ED2A4974B16ED43508C74B7F"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-recent-searches&gt;&lt;/guided-recent-searches&gt;</span> </p> </td> 
   <td colname="col2"> <p>L'étiquette de boucle pour les recherches récentes. Tout contenu entre les balises d'ouverture et de fermeture est itéré pour chaque page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-recent-searches-link [attr="value" ]+=""&gt; 
      &lt;/guided-recent-searches-link&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Vous permet de créer un lien vers une recherche récente. Il prend en charge le passage de tous les attributs HTML directement à l'étiquette d'ancrage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-recent-searches-path&gt;&lt;/guided-recent-searches-path&gt;</span> </p> </td> 
   <td colname="col2"> <p>Vous permet de saisir le chemin urL <span class="codeph"> relatif pour une </span> recherche récente, dans une boucle de recherche guidée-récente. En règle <span class="codeph"> générale, vous utiliseriez </span>guidée-récente-recherche-lien . Toutefois, si vous vouliez créer votre propre lien, vous pouvez utiliser cette balise. Voici un exemple : </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-lt&gt;&lt;/guided-lt&gt;a etnbsp;href&lt;guided_recent_searches_path&gt;&lt;guided-recent-searches-value&gt; &lt;/guided-recent-searches-value&gt; &lt;/guided_recent_searches_path&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-recent-searches-value&gt; </span>&lt;/guided-recent-searches-value&gt; </p> </td> 
   <td colname="col2"> <p>Vous permet de saisir le terme requête qui est associé à une recherche récente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-recent-searches-clear-link [attr="value" ]+=""&gt;&lt;/guided-recent-searches-clear-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Vous permet d'offrir à vos clients la possibilité d'effacer les recherches récemment enregistrées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-recent-searches-clear-path&gt;&lt;/guided-recent-searches-clear-path&gt;</span> </p> </td> 
   <td colname="col2"> <p>Retourne le <span class="codeph"> chemin qui &lt;guided-recent-searches-clear-link&gt; </span> utilise de sorte que vous pouvez construire votre propre lien.&lt;/guided-recent-searches-clear-link&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-recent-searches&gt; 
      &lt;guided-else-recent-searches&gt;&lt;/guided-else-recent-searches&gt;&lt;/guided-if-recent-searches&gt;

    et lt;/guided-if-recent-searches et gt; 
    &lt;p&gt;
<td colname="col2"> <p>Vous permet d'afficher les recherches récentes lorsqu'un client a effectué une recherche récente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Avez-vous l'un des dires{#section_C1EB3B9D8E1242798A6E04609D1E3543}

Vous pouvez utiliser les balises Did You Mean pour créer un ensemble de liens vers des suggestions lorsqu'une recherche ne renvoie aucun résultat et que le terme de recherche n'est pas dans le dictionnaire du compte. Ce qui suit est un exemple d'utilisation des balises Did You Mean :

```
<guided-if-suggestions> 
    <span>Did You Mean?</span><br/> 
    <guided-suggestions> 
        <guided-suggestion-link><guided-suggestion/></guided-suggestion-link><br/> 
    </guided-suggestions> 
</guided-if-suggestions>
```

<table id="table_A139FC0A7DF7460DBC52D0C05771789C"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-suggestions&gt;&lt;/guided-suggestions&gt;</span> </p> </td> 
   <td colname="col2"> <p>Il s'agit de l'étiquette de boucle pour boucler les suggestions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-suggestion-link [attr="value" ]+=""&gt;&lt;/guided-suggestion-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Crée un lien vers la suggestion donnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Newly added from search-eng version, 2/1/2013--><span class="codeph"> &lt;guided-suggestion-value&gt;&lt;/guided-suggestion-value&gt;</span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-suggestions&gt;&lt;guided-else[-not]- suggestions=""&gt;&lt;/guided-else[-not]-&gt;&lt;/guided-if[-not]-suggestions&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Vous permet de tester s'il ya des suggestions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-suggestion-path&gt;&lt;/guided-suggestion-path&gt;</span> </p> </td> 
   <td colname="col2"> <p>Renvoie la chaîne de chemin à la suggestion. Vous pouvez l'utiliser pour construire votre propre balise d'ancrage. Typiquement, <span class="codeph"> le lien </span> guidé-suggestion-lien est utilisé à la place. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-suggestion&gt;&lt;/guided-suggestion&gt;</span> </p> </td> 
   <td colname="col2"> <p>Une suggestion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-suggestion-result-count&gt;&lt;/guided-suggestion-result-count&gt;</span> </p> </td> 
   <td colname="col2"> <p>Nombre de résultats pour la suggestion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-suggestion-autosearch&gt; 
      &lt;guided-else[-not]-suggestion-autosearch&gt; 
      &lt;/guided-else[-not]-suggestion-autosearch&gt;&lt;/guided-if[-not]-suggestion-autosearch&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Vous permet de tester si la recherche automatique par suggestion sur zéro résultats a été effectuée, au cas où cette fonctionnalité est allumée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-suggestion-original-query&gt;&lt;/guided-suggestion-original-query&gt;</span> </p> </td> 
   <td colname="col2"> <p>Retourne la requête d'origine si la recherche automatique a été effectuée. </p> <p>Exemple d'utilisation : </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-suggestion-autosearch&gt;Recherchez &lt;guided-query-param gsname="q" &gt;&lt;/guided-query-param gsname="q" &gt; au lieu de&lt;guided-suggestion-original-query &gt;&lt;/guided-suggestion-original-query &gt; 
      &lt;/guided-if-suggestion-autosearch&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-suggestion-low-results&gt; 
      &lt;guided-else[-not]-suggestion-low-results&gt; 
      &lt;/guided-else[-not]-suggestion-low-results&gt;&lt;/guided-if[-not]-suggestion-low-results&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette condition est vraie s'il y a des suggestions dues à un nombre bas de résultat, dans le cas où cette fonctionnalité est allumée. </p> <p>Ce qui suit est un exemple d'utilisation de cette balise: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-if-suggestion-low-results&gt;Vous avez un faible &lt;guided-query-param gsname="q" &gt; &lt;/guided-query-param gsname="q" &gt;nombre de résultats pour .&lt;/guided-if-suggestion-low-results&gt; 
      Voulez-vous dire: &lt;guided-suggestions&gt; &lt;guided-suggestion-link&gt;&lt;guided-suggestion &gt; &lt;/guided-suggestion &gt; 
                 
             &lt;/guided-suggestion-link&gt; &lt;guided-if-not-last&gt;,&lt;/guided-if-not-last&gt; 
              
         &lt;/guided-suggestions&gt; 
       
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Autocomplete{#section_897316BEE1454E839A56B565CA4AF018}

Les balises suivantes peuvent être utilisées pour ajouter autocomplete à votre formulaire de recherche. Les balises de contenu de tête et de forme sont nécessaires pour rendre la fonction autocomplète correctement. Il est recommandé d'utiliser les balises par opposition au codage dur du Javascript et du CSS autocomplets dans votre modèle de présentation. La raison en est que les balises permettent à vos modèles de capter les nouveaux ID de cache de défaite chaque fois que vous modifiez vos paramètres autocomplets sans avoir besoin de mettre à jour manuellement votre modèle.

<table id="table_797858E5872545BE98CD59054F459C1D"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-autocomplete&gt; &lt;guided-else-autocomplete&gt; &lt;/guided-else-autocomplete&gt;&lt;/guided-if-autocomplete&gt;</span> </p> </td> 
   <td colname="col2"> <p>Détecte si la fonction d'autocomplete est activée. Vous pouvez utiliser les balises pour prendre la tête et former le contenu nécessaire pour être autocomplete. À son tour, cela vous permet de basculer la fonctionnalité sur et hors tension et ne pas avoir à modifier vos modèles de présentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-ac-css&gt;&lt;/guided-ac-css&gt;</span> </p> </td> 
   <td colname="col2"> <p>Utilisé dans la tête du modèle de présentation et remplacé par le script CSS approprié comprend pour autocomplete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-ac-form-content&gt;&lt;/guided-ac-form-content&gt;</span> </p> </td> 
   <td colname="col2"> <p>Utilisé dans le formulaire <span class="codeph"> de recherche (entre le&lt;form&gt;</span> et <span class="codeph">&lt;/form&gt;</span> tags) du modèle de présentation au lieu de codage dur les balises autocomplete dans le formulaire. Les balises sont remplacées par le HTML approprié qui est nécessaire pour faire fonctionner autocomplete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-ac-javascript&gt;&lt;/guided-ac-javascript&gt;</span> </p> </td> 
   <td colname="col2"> <p>Génére les liens vers le JavaScript autocomplete. Pour de meilleures performances, il est recommandé de placer cette balise près du bas de la page avant la fermeture "corps" tag. </p> </td> 
  </tr> 
 </tbody> 
</table>

## boutique{#section_A33E25DB5E67404A823BD9618665B773}

Utilisez les balises suivantes pour tester et afficher le magasin dans lequel se trouve actuellement un utilisateur.

<table id="table_6B6538E0D678491DB5BDF22A7CB70932"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-store&gt;&lt;/guided-store&gt;</span> </p> </td> 
   <td colname="col2"> <p>Sortie du magasin actuel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-store-defined&gt; &lt;guided-else-store-defined&gt; &lt;/guided-else-store-defined&gt;&lt;/guided-if-store-defined&gt;</span> </p> </td> 
   <td colname="col2"> <p>Détecte si l'utilisateur est dans un magasin. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-store gsname="store"&gt; &lt;guided-else-store&gt; &lt;/guided-else-store&gt;&lt;/guided-if-store&gt;</span> </p> </td> 
   <td colname="col2"> <p>Détecte si l'utilisateur est dans <span class="codeph"> le </span> magasin que le paramètre gsname spécifie. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zones{#section_B9B3179E000C42D492E1541F2FE44CB5}

<table id="table_514E2E1BBCBC45C8999893B4CF28548C"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-zone gsname="zone area" [search="associated search" ]="" [facet="associated facet" ]="" [width="xx" height="yy" ]=""&gt; </span>&lt;/guided-zone&gt; </p> </td> 
   <td colname="col2"> <p>Vous pouvez envelopper n'importe quel contenu dans des balises de zone pour créer une zone hors de cette zone. Cela vous permet d'utiliser les règles d'entreprise pour afficher la zone au besoin. Par défaut, les zones sont toujours affichées. Vous pouvez utiliser les paramètres de recherche et de facettes facultatives pour indiquer quelle recherche ou facette est associée à la zone. Une telle fonctionnalité permet au logiciel de sauter les recherches ou les facettes lorsqu'une zone est cachée, améliorant ainsi les performances en temps de recherche. Les attributs de hauteur et de largeur sont facultatifs et sont utilisés pour configurer la façon dont le support de place est affiché dans le Visual Rule Builder lorsqu'une zone est supprimée. </p> <p> Utilisez <span class="codeph"> l'étiquette guidée-if-facet[-pas]-visible </span> au lieu de la zone si possible. Il simplifie le modèle de présentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-zone gsname="zone area"&gt; &lt;guided-else-zone&gt; &lt;/guided-else-zone&gt;&lt;/guided-if-zone&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cet ensemble de balises permet de tester si une zone est actuellement affichée. Il est utile lorsque vous avez du contenu ailleurs sur la page que vous souhaitez afficher uniquement lorsque la zone est affichée. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Indicateurs de boucle{#section_387322CA0AA843A2ACF2795C328673E9}

Vous pouvez utiliser chacun des indicateurs de boucle suivants dans l'un de ces blocs de boucle :

* résultats guidés
* valeurs guidées-facet
* chapelure guidée
* guides-menu-articles
* pages guidées

<table id="table_1CA600313C7744BEA98532BFC8B39926"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-first&gt;&lt;guided-else[-not]-first&gt; 
      &lt;/guided-else[-not]-first&gt;&lt;/guided-if[-not]-first&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette condition est vraie lorsque l'itération actuelle est la première itération de la boucle. Cela ne signifie pas nécessairement le premier résultat ou la première page, mais le premier affiché. Si le visiteur du site est à la page 2 d'un ensemble de résultats qui est de 10 par page, la première itération est le résultat 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-last&gt;&lt;guided-else[-not]-last&gt; 
      &lt;/guided-else[-not]-last&gt;&lt;/guided-if[-not]-last&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette condition est vraie lorsque l'itération actuelle est la dernière itération de la boucle. Cela ne signifie pas nécessairement le dernier résultat ou la dernière page, mais le dernier montré dans le contexte actuel (page). Si le visiteur du site est à la page 1 d'un ensemble de résultats qui contient 200 résultats mais n'a que 10 résultats par page, la dernière itération est le résultat 10 au lieu du résultat 200. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 
     <codeblock>
       &lt;guided-if[-not]-odd&gt;&lt;guided-else[-not]-odd&gt; 
      &lt;/guided-else[-not]-odd&gt;&lt;/guided-if[-not]-odd&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette condition est vraie lorsque l'itération actuelle est une itération étrange de la boucle (par rapport à une itération même). Ceci est utile pour afficher différentes couleurs de rangée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-else[-not]-even&gt;&lt;/guided-if[-not]-even&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette condition est vraie lorsque l'itération actuelle est une itération égale de la boucle (par rapport à une itération impaire). Ceci est utile pour afficher différentes couleurs de rangée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-else[-not]-alt&gt;&lt;/guided-if[-not]-alt&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette condition est vraie lorsque l'itération actuelle est une itération égale de la boucle. Ceci est utile pour afficher différentes couleurs de rangée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-else[-not]-inner&gt;&lt;/guided-if[-not]-inner&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Inclut le texte entre eux si l'itération actuelle n'est ni la première ni la dernière. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-else[-not]-outer&gt;&lt;/guided-if[-not]-outer&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Inclut le texte entre eux si l'itération actuelle est la première ou la dernière. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-loop-index&gt; </span>&lt;/guided-loop-index&gt; </p> </td> 
   <td colname="col2"> <p>Un entier (à partir de 0) dont la valeur incréments pour chaque itération de la boucle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-loop-counter&gt; </span>&lt;/guided-loop-counter&gt; </p> </td> 
   <td colname="col2"> <p>Un entier (à partir de 1) dont la valeur incréments pour chaque itération de la boucle. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Langage divers{#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C}

Les balises suivantes sont disponibles pour vous permettre de faire des choses plus avancées avec votre modèle, comme la construction de votre propre mini-facet.

<table id="table_7665FC6120A842919EFF325ACB1E1A86"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--><span class="codeph"> &lt;guided-current-path [escape="html|url|js|json|0" ]=""&gt;&lt;/guided-current-path&gt;</span> </p> </td> 
   <td colname="col2"> <p>Vous donne le chemin actuel qui est utilisé. En règle générale, il est utilisé pour créer un lien qui ajoute sur un nouveau paramètre à la recherche existante. Par défaut, le chemin est URL échappé. Vous pouvez spécifier quel mode d'évasion vous souhaitez utiliser au moyen du paramètre d'échappement. </p> <p>échantillon: </p> <p> 
     <codeblock class="syntax html">
       &lt;&gt;&lt;guided-current-path &gt;&lt;/guided-current-path &gt;'lang'fr' 
      version Français 
     </codeblock> </p> <p>Dans cet exemple, une règle de traitement de recherche utilise lang pour sélectionner la version Français. </p> <p>Le chemin actuel a toujours au moins un paramètre de requête. S'il n'existe pas d'autres <span class="codeph"> paramètres </span> de requête, il est défini sur q ' ce qui facilite l'ajout d'autres paramètres. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">Chemin de base</span> </p> </td> 
   <td colname="col2"> <p> Si vous voulez créer un lien en <span class="codeph"> </span> utilisant le chemin <span class="codeph"> </span> de base, utilisez / au début de votre href et ajouter des paramètres. </p> <p> 
     <codeblock class="syntax html">
       &lt;a href="&gt;Tous les produits 
      Créerait un lien "Tous les produits" à votre 
      basepath, par exemple http://search.mycompany.com/&lt;/a href="&gt;

    &lt;p&gt;
</tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--><span class="codeph"> &lt;guided-query-param gsname="query_parameter" [escape="html|url" ]=""&gt;&lt;/guided-query-param&gt;</span> </p> </td> 
   <td colname="col2"> <p>Vous permet de saisir la valeur existante d'un paramètre de requête qui se trouve sur l'URL. Si votre paramètre n'existe pas, cette balise renvoie une chaîne vide. Si vous ne spécifiez pas une option d'évasion, la chaîne retournée est automatiquement échappée HTML, vous pouvez spécifier html ou URL s'échappant. </p> <p>échantillon: </p> <p> 
     <codeblock>
       si 
      mon URL est http://stage.leejeansken.com:2928/?q=pants&amp;lang=en 
      &lt;guided-query-param gsname="q" &gt;&lt;/guided-query-param gsname="q" &gt; 
      vous donne le pantalon de valeur 
      &lt;guided-query-param gsname="lang" &gt;&lt;/guided-query-param gsname="lang" &gt; 
      vous donne la valeur en 
      &lt;guided-query-param gsname="test" &gt;&lt;/guided-query-param gsname="test" &gt; 
      vous donne une chaîne vide 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-query-param-name gsname="param#" offset="offset_number"&gt;&lt;/guided-query-param-name&gt;</span> </p> </td> 
   <td colname="col2"> <p>La recherche guidée a la notion d'un numéro de requête, qui est utilisé dans le contrôle de la chapelure. <span class="codeph">guided-query-param-name </span> vous permet de définir les paramètres dans le cadre d'un lien dans le modèle de présentation où la recherche guidée figure le nombre de requête s'il vous convient. Le <span class="codeph"> gsname </span> a un "x" en elle, qui Guided Search remplace par le nombre correct. La valeur de compensation peut être de 0 à 15, où 0 indique que le prochain numéro de requête disponible est utilisé. A 1 indique que vous voulez ajouter 1 à elle, et ainsi de suite. </p> <p>Combiné <span class="codeph"> avec le courant </span>guidé-chemin, vous pouvez construire votre propre lien de mini-facettes ou permettre un niveau supplémentaire de forage vers le bas. </p> <p>échantillon: </p> <p> 
     <codeblock class="syntax html">
       &lt;&gt;&lt;guided-current-path         /=""&gt;Catégorie&lt;guided-query-param-name gsname="q#" offset="0"         /=""&gt;&lt;guided-query-param-name gsname="x#" offset="0"         /=""&gt;:Hommes  
            &lt;/guided-query-param-name gsname="x#" offset="0"&gt; &lt;/guided-query-param-name gsname="q#" offset="0"&gt;&lt;/guided-current-path&gt; 
     </codeblock> </p> <p> 
     <codeblock class="syntax html">
       &lt;&gt;&lt;guided-current-path         /=""&gt;&lt;guided-query-param-name gsname="sp_q_exact_#" offset="0"         /=""&gt;&lt;guided-query-param-name gsname="sp_x_#" offset="0"         /=""&gt;'mens'''catégorie&lt;guided-query-param-name gsname="sp_q_exact_#" offset="1"         /=""&gt;'Jeans'''''''produit-type'&lt;guided-query-param-name gsname="sp_x_#" offset="1"         /=""&gt;'Cat:Men - Produit:Jeans&lt;/guided-query-param-name gsname="sp_x_#" offset="1"&gt; &lt;/guided-query-param-name gsname="sp_q_exact_#" offset="1"&gt; &lt;/guided-query-param-name gsname="sp_x_#" offset="0"&gt; &lt;/guided-query-param-name gsname="sp_q_exact_#" offset="0"&gt;&lt;/guided-current-path&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-include gsfile="filename"&gt;&lt;/guided-include&gt;</span> </p> </td> 
   <td colname="col2"> <p> Vous permet d'inclure d'autres fichiers de modèle. Cette fonctionnalité signifie que vous pouvez créer plusieurs modèles en utilisant des sous-modèles comme modules. </p> <p>Dans l'exemple <span class="filepath"> suivant, </span> les <span class="filepath"> </span> fichiers de chapelure et de facettes sont inclus : </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-include gsfile='breadcrumbs.tmpl' &gt;&lt;/guided-include gsfile='breadcrumbs.tmpl' &gt; 
      &lt;guided-include gsfile='facets.tmpl' &gt;&lt;/guided-include gsfile='facets.tmpl' &gt; 
     </codeblock> </p> <p>Les incluts dynamiques ne sont pas pris en charge. En d'autres termes, <span class="codeph"> gsfile </span> ne peut pas être une variable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--><span class="codeph"> &lt;guided-search-time&gt; </span>&lt;/guided-search-time&gt; </p> </td> 
   <td colname="col2"> <p> Identifie le temps que la recherche a pris. La valeur de temps de recherche retournée est spécifiée dans ms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--><span class="codeph"> &lt;guided-fall-through-searches&gt; </span>&lt;/guided-fall-through-searches&gt; </p> </td> 
   <td colname="col2"> <p> Retourne le nombre de recherches de cœurs qui sont utilisées pour créer la page des résultats de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--><span class="codeph"> &lt;guided-if-fall-through-search&gt;&lt;/guided-if-fall-through-search&gt;</span> </p> </td> 
   <td colname="col2"> <p>Tests si le nombre de recherches de base est supérieur à un. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-else[-not]-even&gt;&lt;/guided-if[-not]-even&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette condition est vraie lorsque l'itération actuelle est une itération égale de la boucle (par rapport à une itération impaire). Ceci est utile pour afficher différentes couleurs de rangée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-else[-not]-alt&gt;&lt;/guided-if[-not]-alt&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Cette condition est vraie lorsque l'itération actuelle est une itération égale de la boucle. Ceci est utile pour afficher différentes couleurs de rangée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-else[-not]-inner&gt;&lt;/guided-if[-not]-inner&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Inclut le texte entre eux si l'itération actuelle n'est ni la première ni la dernière. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-else[-not]-outer&gt;&lt;/guided-if[-not]-outer&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Inclut le texte entre eux si l'itération actuelle est la première ou la dernière. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <codeblock>
       &lt;guided-if-first-search&gt;&lt;guided-else-first-search&gt; 
      &lt;/guided-else-first-search&gt;&lt;/guided-if-first-search&gt; 
     </codeblock> </p> </td> 
   <td colname="col2"> <p>Vous permet de vérifier si vous êtes sur la recherche initiale ou non (requête a été le résultat d'une recherche à partir de la zone de recherche). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-search-url&gt;&lt;/guided-search-url&gt;</span> </p> </td> 
   <td colname="col2"> <p>Vous pouvez utiliser cette balise dans votre modèle pour vous sauver du codage par code dur de l'action du formulaire de recherche. Il détecte lorsque vous êtes dans l'environnement Mis en scène ou en direct et change en conséquence. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-query-param-defined gsname="query_parameter"&gt; &lt;guided-else-query-param-defined&gt; &lt;/guided-else-query-param-defined&gt;&lt;/guided-if-query-param-defined&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cet ensemble de balises vous permet de tester les paramètres CGI définis dans le chemin de recherche. Vous ne pouvez tester les valeurs des paramètres que s'ils sont définis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-next-query-number [gsname="offset" ]=""&gt;&lt;/guided-next-query-number&gt;</span> </p> </td> 
   <td colname="col2"> <p>Le moteur de recherche guidé qui conduit le modèle a la notion de numéros de requête flottants où chaque nouveau lien que le moteur génère, utilise le prochain numéro de requête disponible. Cette balise vous permet de saisir le numéro de requête ou les décalages suivants afin que vous puissiez créer des liens personnalisés qui forent dans l'ensemble de résultats. Offset vous permet de compenser dans le numéro de requête suivant. Par exemple, si vous avez sélectionné une facette, le numéro de requête suivant est 2, avec un décalage de 1 le numéro de requête retourné est 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-custom-var gsname="custom_variable" [escape="html|url|js|json|0" ]/=""&gt; </span>&lt;/guided-custom-var&gt; </p> </td> 
   <td colname="col2"> <p>Vous permet de saisir la valeur existante d'une variable personnalisée que vos règles de traitement définissent. Si vous ne spécifiez pas une option d'évasion <span class="codeph"> la </span> <span class="codeph"> chaîne </span>retournée <span class="codeph"> est </span>automatiquement <span class="codeph"> </span>HTML échappé, vous pouvez spécifier soit html , URl , js , ou 0 . Si vous utilisez une règle de traitement pour copier un paramètre CGI entrant à une variable personnalisée, puis afficher ou utiliser cette variable dans votre modèle avec l'échappement réglé à aucun ou js, alors vous pouvez créer une vulnérabilité XSS dans votre recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-custom-var-defined gsname="custom_variable"&gt; &lt;guided-else-custom-var-defined&gt; &lt;/guided-else-custom-var-defined&gt;&lt;/guided-if-custom-var-defined&gt;</span> </p> </td> 
   <td colname="col2"> <p>Permet de tester si une variable personnalisée est définie dans les règles de traitement (nettoyage des requêtes, traitement de pré-recherche et traitement post-recherche). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-general-field gsname="searchname" field="fieldname" [escape="html|url|js|json|0" ]/=""&gt; </span>&lt;/guided-general-field&gt; </p> </td> 
   <td colname="col2"> <p>Vous permet d'afficher le contenu d'un champ général défini dans le modèle de transport. Si vous ne spécifiez pas d'option d'échappement, la chaîne retournée est codée dans le format que vous avez spécifié dans le modèle de transport de ce champ. Spécifier une option d'évasion s'applique en plus du format que vous encodez le champ comme dans votre modèle de transport. Vous pouvez <span class="codeph"> spécifier <span class="codeph"> soit </span> <span class="codeph"> html </span> </span>, <span class="codeph"> URl , js , json </span>, ou <span class="codeph"> 0 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-general-field gsname="searchname" field="fieldname"&gt; &lt;guided-else-general-field&gt; &lt;/guided-else-general-field&gt;&lt;/guided-if-general-field&gt;</span> </p> </td> 
   <td colname="col2"> <p>Permet de tester si le contenu d'un champ général, tel que défini dans le modèle de transport, existe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-cookie-value gsname="cookie_name" [escape="html|url|js|json|0" ]/=""&gt; </span>&lt;/guided-cookie-value&gt; </p> </td> 
   <td colname="col2"> <p>Vous permet de saisir la valeur d'un cookie, en supposant que le cookie est disponible. Si vous ne spécifiez pas une option d'évasion <span class="codeph"> la </span> <span class="codeph"> chaîne </span>retournée <span class="codeph"> est automatiquement HTML échappé, vous pouvez spécifier soit html , URl , js </span> <span class="codeph"> , json </span>, ou <span class="codeph"> 0 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-cookie gsname="cookie_name"&gt; &lt;guided-else-cookie&gt; &lt;/guided-else-cookie&gt;&lt;/guided-if-cookie&gt;</span> </p> </td> 
   <td colname="col2"> <p>Permet de tester si un cookie existe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-banner gsname="banner area" [escape="html|url|js|json|0" ]="" [width="xx" height="yy" ]/=""&gt; </span>&lt;/guided-banner&gt; </p> </td> 
   <td colname="col2"> <p>Sortie de la bannière pour une zone donnée. Les attributs optionnels de largeur et de hauteur sont utilisés dans le Visual Rule Builder pour permettre l'affichage d'un porte-lieux significatif pour permettre aux utilisateurs de sélectionner une bannière. Par défaut, les bannières ne sont pas échappées. Au lieu de cela, vous souhaitez injecter HTML dans le modèle de présentation. Toutefois, si vous construisez un modèle JSON envisager d'utiliser l'option d'évasion js. </p> <p>échantillon: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-banner gsname="top" width="400px"  height="50px"&gt;&lt;/guided-banner gsname="top" width="400px"&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-banner-set gsname="banner area"&gt; &lt;guided-else-banner-set&gt; &lt;/guided-else-banner-set&gt;&lt;/guided-if-banner-set&gt;</span> </p> </td> 
   <td colname="col2"> <p>Permet de tester si une zone de bannière est mise en place. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-simulator-mode&gt; &lt;guided-else-simulator-mode&gt; &lt;/guided-else-simulator-mode&gt;&lt;/guided-if-simulator-mode&gt;</span> </p> </td> 
   <td colname="col2"> <p>Vous permet de détecter lorsque vous visualisez votre recherche dans Simulator ou le Visual Rule Builder. Il est normalement utilisé pour afficher des informations supplémentaires de débogage pour vous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-tnt-business-rules&gt; &lt;guided-else-tnt-business-rules&gt; &lt;/guided-else-tnt-business-rules&gt;&lt;/guided-if-tnt-business-rules&gt;</span> </p> </td> 
   <td colname="col2"> <p>Vous permet de détecter si vous <span class="keyword"> avez </span> des règles métier faisant référence à une campagne Adobe Target. Il est normalement utilisé dans le <span class="keyword"> cadre </span> de l'intégration avec Adobe Target pour éviter d'atteindre les <span class="keyword"> serveurs Target </span> lorsque cela n'est pas nécessaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-redirect&gt;&lt;/guided-redirect&gt;</span> </p> </td> 
   <td colname="col2"> <p>Par défaut, les redirections sont exécutées automatiquement. Toutefois, si vous avez configuré la recherche/merchandising du site pour renvoyer une réponse XML ou JSON à votre application web, vous pouvez choisir soit d'analyse de la réponse 302/301 dans votre application web, soit de faire passer la redirection à vous dans le cadre de l'ensemble de résultats. Si vous passez la redirection dans le cadre de l'ensemble de résultats, cette balise peut être utilisée dans le modèle pour sortir l'emplacement de redirection. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-if-redirect&gt; &lt;guided-else-redirect&gt; &lt;/guided-else-redirect&gt;&lt;/guided-if-redirect&gt;</span> </p> </td> 
   <td colname="col2"> <p>Lorsque vous avez configuré la recherche/merchandising du site pour renvoyer les redirections dans l'ensemble de résultats, cet ensemble de balises peut être utilisé pour déterminer s'il y a une redirection vers la sortie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-lt&gt;&lt;/guided-lt&gt; &lt;guided-gt&gt;&lt;/guided-gt&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cet ensemble de balises vous permet d'intégrer des balises de modèle guidées dans des attributs HTML. </p> <p>échantillon: </p> <p> 
     <codeblock class="syntax html">
       &lt;guided-lt&gt;&lt;/guided-lt&gt;div &lt;guided-if-facet-long&gt;(en) 
              style "hauteur: 125px; déborder: 
              auto;"&lt;/guided-if-facet-long&gt;&lt;guided-gt&gt;&lt;/guided-gt&gt; 
     </codeblock> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Étiquettes de modèle de transport{#reference_227D199F5A7248049BE1D405C0584751}

Les modèles de transport sont des modèles XML qui transmettent les données de la recherche backend à la couche de présentation de la recherche guidée.

<!-- 

r_transport_template_tags.xml

 -->

Dans votre couche de présentation, vous pouvez avoir un modèle de présentation unique qui présente les résultats de plusieurs recherches. Chaque recherche peut utiliser le même modèle de transport ou un modèle de transport personnalisé pour transmettre les données à la couche de présentation.

Étant donné que le modèle de transport n'est utilisé que pour transmettre des données à la couche de présentation, il n'a pas de HTML qui est concerné par l'affichage des résultats de recherche. Le modèle de transport utilise le modèle de transport xML pour transmettre les résultats de recherche pour peupler les composants de recherche guidée, tels que les facettes, la chapelure et les menus. Dans ces balises, les balises de modèle de recherche standard sont utilisées pour afficher les valeurs réelles.

<table id="table_C94AA64B3C694C528E25CF0C45833872"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Étiquette de modèle de transport </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;guided-xml&gt;&lt;/guided-xml&gt;</span> </p> </td> 
   <td colname="col2"> <p>Les balises XML racine que la couche de présentation utilise pour détecter ce qui est mis en écart dans le modèle de transport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;general&gt;&lt;/general&gt;</span> </p> </td> 
   <td colname="col2"> <p>Les balises entourent les balises de modèle de recherche qui fournissent des données sommaires basées sur l'ensemble de résultats. En règle générale, ces balises contiennent des balises de recherche pour le nombre total de résultats, un résultat inférieur et un résultat le plus élevé. Vous pouvez définir n'importe quel nombre <span class="codeph"> de </span> champs globaux supplémentaires que vous souhaitez avec l'étiquette de champ général, comme dans l'exemple suivant : </p> <p> 
     <codeblock class="syntax html">
       &lt;general&gt; 
        &lt;total&gt;&lt;search-total &gt;&lt;/search-total &gt;&lt;/total&gt; 
        &lt;lower&gt;&lt;search-lower &gt;&lt;/search-lower &gt;&lt;/lower&gt; 
        &lt;upper&gt;&lt;search-upper &gt;&lt;/search-upper &gt;&lt;/upper&gt; 
        &lt;general-field name="my_custom_field"&gt;Certains contenus globaux 
      &lt;/general-field name="my_custom_field"&gt;&lt;/general&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;results&gt;&lt;/results&gt;</span> </p> </td> 
   <td colname="col2"> <p>Les balises sont enroulées autour des résultats de recherche, de sorte que la recherche guidée sait où les chercher. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;result&gt;&lt;/result&gt;</span> </p> </td> 
   <td colname="col2"> <p>Les balises sont enroulées autour de chaque résultat de recherche, de sorte que la recherche guidée reconnaît où le contenu d'un seul résultat de recherche commence et se termine, comme dans l'exemple suivant : </p> 
    <codeblock class="syntax html">
      &lt;results&gt; 
       &lt;search-results&gt; 
         &lt;result&gt; 
           &lt;index&gt;&lt;search-index &gt;&lt;/search-index &gt;&lt;/index&gt; 
           &lt;loc&gt;&lt;search-cdata&gt;&lt;search-url length="500" &gt;&lt;/search-url length="500" &gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
         &lt;/result&gt; 
       &lt;/search-results&gt; 
     &lt;/results&gt; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;attribute-table name="tablename"&gt; </span>&lt;/attribute-table&gt; </p> </td> 
   <td colname="col2"> <p>Vous permet de boucler chaque élément dans une liste multi-valeur pour un seul résultat. N'utilisez cette balise que dans un résultat. Son but est de vous permettre d'itérer sur les attributs qui appartiennent à un champ de résultat, comme dans l'exemple suivant: </p> 
    <codeblock class="syntax html">
      &lt;results&gt; 
       &lt;search-results&gt; 
         &lt;result&gt; 
           &lt;index&gt;&lt;search-index &gt;&lt;/search-index &gt;&lt;/index&gt; 
           &lt;loc&gt;&lt;search-url &gt;&lt;/search-url &gt;&lt;/loc&gt; 
           &lt;title&gt;&lt;search-title &gt;&lt;/search-title &gt;&lt;/title&gt; 
           &lt;attribute-table name="downloads"&gt; 
             &lt;field name="download_title"&gt;&lt;search-display-field name="download_title" &gt;&lt;/search-display-field name="download_title" &gt; 
             &lt;field name="download_link" delimiter="|"&gt;&lt;search-display-field name="download_link" &gt;&lt;/search-display-field name="download_link" &gt; 
            
         &lt;/field name="download_link" delimiter="|"&gt;&lt;/field name="download_title"&gt;&lt;/attribute-table name="downloads"&gt;&lt;/result&gt; 
       &lt;/search-results&gt; 
     &lt;/results&gt; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;facets&gt;&lt;/facets&gt;</span> </p> </td> 
   <td colname="col2"> <p>Transmet les résultats qui peuplent les facettes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <!--NEW 2/27/2014--><span class="codeph"> &lt;dynamic-facet&gt;&lt;/dynamic-facet&gt;</span> </p> </td> 
   <td colname="col2"> <p> Vous pouvez désigner une facette à la fois comme une facette dynamique et comme un membre d'un rail à facettes. Cependant, leur traitement est indépendant en ce qui concerne les balises de modèle de présentation connexes. </p> <p>En d'autres termes, la nidisation d'un contexte de boucle de rail de facette dans un contexte dynamique de boucle de facette, ou vice versa, n'est pas permise. </p> <p>Pour les facettes à la fois dynamiques et balisées, seules les facettes dynamiques qui ont été retournées pour une recherche donnée sont visibles dans le contexte de boucle de rail de facettes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;facet name="name"&gt;&lt;/facet&gt;</span> </p> </td> 
   <td colname="col2"> <p> Chaque facette a ses propres balises de facettes où le paramètre de nom correspond au nom de facette. Les balises de recherche sont utilisées dans les balises de facettes pour les valeurs de facettes, comme dans l'exemple suivant : </p> 
    <codeblock class="syntax html">
      &lt;facets&gt; 
       &lt;facet name="brand"&gt; 
         &lt;values&gt;&lt;search-field-value-list name="brand" quotes="no" commas="yes" data="values" sortby="values" &gt;&lt;/search-field-value-list name="brand" quotes="no" commas="yes" data="values" sortby="values" &gt;&lt;/values&gt; 
         &lt;counts&gt;&lt;search-field-value-list name="brand" quotes="no" commas="yes" data="counts" sortby="values" &gt;&lt;/search-field-value-list name="brand" quotes="no" commas="yes" data="counts" sortby="values" &gt;&lt;/counts&gt; 
        
       &lt;facet name="category"&gt; 
         &lt;values&gt;&lt;search-field-value-list name="category" quotes="no" commas="yes" data="values" sortby="values" &gt;&lt;/search-field-value-list name="category" quotes="no" commas="yes" data="values" sortby="values" &gt;&lt;/values&gt; 
         &lt;counts&gt;&lt;search-field-value-list name="category" quotes="no" commas="yes" data="counts" sortby="values" &gt;&lt;/search-field-value-list name="category" quotes="no" commas="yes" data="counts" sortby="values" &gt;&lt;/counts&gt; 
        
     &lt;/facet name="category"&gt;&lt;/facet name="brand"&gt;&lt;/facets&gt; 
    </codeblock> <p> Les comptes utilisant des facettes à fentes peuvent utiliser l'étiquette dynamique et l'étiquette des noms d'affichage. Ces deux balises facilitent la cartographie entre les facettes fentes et les facettes réelles tout en créant des règles d'affaires. </p> 
    <codeblock class="syntax html">
      &lt;facets&gt; 
       &lt;facet name="facet_values01"&gt; 
      &lt;dynamic&gt;1&lt;/dynamic&gt; 
      &lt;display-names&gt;&lt;search-field-value-list name="facet_names01" quotes="no" commas="yes" data="values" sortby="values" &gt;&lt;/search-field-value-list name="facet_names01" quotes="no" commas="yes" data="values" sortby="values" &gt;&lt;/display-names&gt; 
         &lt;values&gt;&lt;search-field-value-list name="facet_values01" quotes="no" commas="yes" data="values" sortby="values" &gt;&lt;/search-field-value-list name="facet_values01" quotes="no" commas="yes" data="values" sortby="values" &gt;&lt;/values&gt; 
         &lt;counts&gt;&lt;search-field-value-list name="facet_values01" quotes="no" commas="yes" data="counts" sortby="values" &gt;&lt;/search-field-value-list name="facet_values01" quotes="no" commas="yes" data="counts" sortby="values" &gt;&lt;/counts&gt; 
       &lt;/facet name="facet_values01"&gt;&lt;/facets&gt; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-display-field separator=","&gt; </span>&lt;/search-display-field&gt; </p> </td> 
   <td colname="col2"> <p></span> L'attribut <span class="codeph"> séparateur permet de modifier le délimiteur qui est utilisé lorsque vous extrayez des données de champ de recherche-affichage pour les listes. La valeur par défaut est une virgule. </span></p> <p>En général, le délimiteur que vous utilisez doit être quelque chose qui n'apparaît pas facilement dans votre contenu de terrain. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;suggestions&gt;&lt;/suggestions&gt;</span> </p> </td> 
   <td colname="col2"> <p> Enveloppez vos suggestions Did You Mean avec des balises afin que la recherche guidée reconnaisse quels nœuds XML contiennent des suggestions. </p> <p>voir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph">&lt;suggestion&gt;&lt;/suggestion&gt;</span> </p> </td> 
   <td colname="col2"> <p>Enveloppez chaque suggestion Did You Mean avec des balises, comme dans l'exemple suivant : </p> 
    <codeblock class="syntax html">
      &lt;search-if-suggestions&gt; 
       &lt;suggestions&gt; 
         &lt;search-suggestions&gt; 
           &lt;suggestion&gt;&lt;search-suggestion-text &gt;&lt;/search-suggestion-text &gt;&lt;/suggestion&gt; 
         &lt;/search-suggestions&gt; 
       &lt;/suggestions&gt; 
     &lt;/search-if-suggestions&gt; 
    </codeblock> <p>voir. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Balises de modèle de recherche{#reference_F7AA3FF602314E42842BBC740D2CA1A4}

Un modèle de recherche est un fichier HTML qui inclut des balises de modèle que la recherche/merchandising du site définit. Ces balises indiquent comment vos résultats de recherche sont formatés. La référence suivante contient une brève description de chaque balise de modèle de recherche et de ses attributs.

<!-- 

r_search_template_tags.xml

 -->

>[!NOTE]
>
>N'utilisez que des balises de modèle de recherche dans les fichiers de modèle de transport (.tpl).

Vous pouvez sélectionner parmi les groupes d'étiquettes de modèle de recherche suivants et le matériel de référence.

## À propos des balises de boucle Résultats{#section_D4DC7B4560144663972E8DBC3369C629}

L'étiquette de boucle de résultats est le cheval de bataille du système de modèle. Lorsque la balise est rencontrée lors d'une recherche, le HTML est répété et d'autres balises entre les balises de boucle de résultats de début et de fin, remplaçant toutes les autres balises par vos résultats de recherche.

`<search-results> ... </search-results>`

Les balises de boucle de résultats entourent le HTML qui affiche les résultats de recherche. Le HTML entre les balises est répété pour chaque résultat et s'affiche sur la page.

Les balises suivantes ne sont valables que dans la boucle de résultats :

## Étiquettes de chaîne de boucle de résultats{#section_80D68334E8D04A33937A6E58ABAAA320}

Les balises suivantes renvoient une chaîne.

<table id="table_2B841B64E9744F6881FFE6E16FA98D58"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-index&gt; </span>&lt;/search-index&gt; </p> </td> 
   <td colname="col2"> <p>Retourne l'indice numérique du résultat actuel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-title length="XX"&gt; </span>&lt;/search-title&gt; </p> </td> 
   <td colname="col2"> <p>Renvoie le titre de page du résultat actuel. L'attribut de longueur en option est utilisé pour limiter la longueur des chaînes affichées, avec un défaut de 80 caractères. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-bodytext length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span>&lt;/search-bodytext&gt; </p> </td> 
   <td colname="col2"> <p>Renvoie le texte du corps à partir du haut de la page. Les termes pertinents sont présentés en gras. L'attribut de longueur en option est utilisé pour limiter la longueur des chaînes affichées, avec un défaut de 80 caractères. L'attribut d'encodage est facultatif et il peut coder les caractères de sortie avec l'encodage HTML (par défaut), l'encodage Javascript, l'encodage Perl, ou aucun. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-description length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span>&lt;/search-description&gt; </p> </td> 
   <td colname="col2"> <p> Renvoie la description du résultat actuel. Si l'étiquette de description méta existe et que l'attribut de contenu n'est pas vide, ce texte s'affiche. Dans le cas contraire, le début du texte du corps de la page est affiché. L'attribut de longueur en option est utilisé pour limiter la longueur des chaînes affichées, avec un défaut de 80 caractères. </p> <p>L'attribut </span> de codage optionnel <span class="codeph"> contrôle si la sortie est codée HTML, JavaScript codée, Perl encodé, URL encodé ou non encodé, pour la sortie sur la page de résultats. La valeur <span class="codeph"> par </span> défaut <span class="codeph"> </span>de l'encodage est html . Normalement, vous n'avez pas besoin de spécifier l'attribut de codage. </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-score rank="dynamic/static/dynamic-raw/static-raw/final-raw" precision="XX"&gt; </span>&lt;/search-score&gt; </p> </td> 
   <td colname="col2"> <p>Retourne le score du résultat actuel, qui est un nombre 0 - 100. Si vous avez défini <span class="uicontrol"> un </span> <span class="uicontrol"> champ de </span> <span class="uicontrol"> classement </span>sous Options ' Metadata ' Définitions , <span class="codeph"> vous pouvez afficher le classement dynamique des pages en définissant l'attribut de rang en dynamique ( &lt;search-score rank="dynamic"&gt; </span>).&lt;/search-score&gt; Vous pouvez afficher le rang de page statique <span class="codeph"> en définissant l'attribut de rang statique ( &lt;search-score rank="static"&gt; </span>).&lt;/search-score&gt; Vous pouvez utiliser l'attribut de précision optionnel pour spécifier le nombre de décimales à afficher. La valeur par défaut est 0 qui affiche le score d'intégriste). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-date length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id"&gt; </span>&lt;/search-date&gt; </p> </td> 
   <td colname="col2"> <p>Renvoie la date du résultat actuel. La valeur de texte « aucune » facultative s'affiche s'il n'y a pas de date associée au résultat actuel. Si la valeur optionnelle « aucun » n'est pas donnée, le texte « Aucune date » s'affiche s'il n'y a pas de date associée au résultat actuel. </p> <p>L'attribut "date-format" prend une chaîne de format de date de style UNIX telle que "%A, %B %d, %Y" (pour "lundi, Juillet 25, 2016"). "gmt" par défaut à "oui" et contrôle si la partie temporelle de la chaîne de date doit être sortie dans GMT ("oui") ou le fuseau horaire du compte ("non"). </p> <p>L'attribut « langue » contrôle la langue et les conventions locales de la chaîne de date de sortie. "0" (par défaut) signifie "Utiliser le langage du compte". " 2 " signifie "Utiliser le langage documentaire". La valeur "langue" "1" est réservée à une utilisation future. Toute autre valeur "langue" est interprétée comme un identifiant de langue spécifique, par exemple, "en-US" signifie "anglais (États-Unis)". </p> <p>L'attribut de longueur en option est utilisé pour limiter la longueur des chaînes affichées, avec un défaut de 80 caractères. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-size&gt; </span>&lt;/search-size&gt; </p> </td> 
   <td colname="col2"> <p>Retourne la taille du résultat actuel en octets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-url length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span>&lt;/search-url&gt; </p> </td> 
   <td colname="col2"> <p>Retourne l'URL du résultat actuel. </p> <p>Utilisez l'attribut de longueur <span class="codeph"> </span> optionnel pour limiter la longueur des chaînes affichées, avec un défaut de caractères illimités. </p> <p><span class="codeph"> L'attribut </span> d'encodage est facultatif et il peut coder les caractères de sortie avec l'encodage HTML, l'encodage Javascript, l'encodage Perl, ou aucun. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-url-path-query length="XX"&gt; </span>&lt;/search-url-path-query&gt; </p> </td> 
   <td colname="col2"> <p>Retourne le chemin et les parties de requête, y compris le point d'interrogation de l'URL du résultat actuel. </p> <p>Utilisez l'attribut de longueur <span class="codeph"> </span> optionnel pour limiter la longueur des chaînes affichées, avec un défaut de caractères illimités. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-context length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span>&lt;/search-context&gt; </p> </td> 
   <td colname="col2"> <p>Renvoie la ligne de contexte suivante pour le terme de recherche. Les termes pertinents sont présentés en gras. Appelez cette balise à plusieurs reprises pour afficher plus d'une ligne de contexte pour le résultat actuel. </p> <p>Utilisez l'attribut de longueur <span class="codeph"> </span> optionnel pour limiter la longueur des chaînes affichées, avec un défaut de 80 caractères. L'attribut <span class="codeph"> de longueur </span> est ignoré si cette balise est jointe par l'un ou l'autre <span class="codeph"> &lt;search-if-context&gt; </span> ou <span class="codeph"> &lt;search-if-any-context&gt; </span> &lt;/search-if-any-context&gt; &lt;/search-if-context&gt; des ensembles de balises qui contiennent un attribut de longueur. </p> <p><span class="codeph"> L'attribut </span> d'encodage est facultatif et il peut coder les caractères de sortie avec l'encodage HTML (par défaut), l'encodage Javascript, l'encodage Perl, ou aucun. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-display-field name="field-name" length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id" encoding="html/javascript/json/perl/url/none" quotes="yes/no" commas="yes/no" units="miles/kilometers" separator="|"&gt; </span>&lt;/search-display-field&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise avancée affiche le contenu du champ de métadonnées (url, titre, desc, clés, cible, <span class="uicontrol"> corps, alt, date, charset, et le langage ou les champs définis sous </span> Options - <span class="uicontrol"> Métadonnées </span> - Définitions) spécifiés dans le <span class="codeph"> nom </span> pour le résultat actuel. par exemple: </p> <p> <span class="codeph">&lt;search-display-field name="title" length="70" none="no title"&gt; </span>&lt;/search-display-field&gt; </p> <p>Sortie du titre de la page pour un résultat de recherche. Si l'attribut optionnel <span class="codeph"> none </span> est spécifié, sa valeur n'est affichée sur la page de résultats que s'il n'y a pas de contenu associé au champ. </p> <p>Le <span class="codeph"> format </span>de <span class="codeph"> </span> date, le gmt <span class="codeph"> et les attributs de langue </span> </span> ne sont pertinents que si le type de contenu du champ spécifié est <span class="codeph"> la date . </span></p> <p>L'attribut <span class="codeph"> </span> de format de date prend une <span class="codeph"> chaîne de format de date </span> de style UNIX telle que %A, %B %d, %Y (pour le lundi 25 juillet 2016). <span class="codeph">gmt </span> par <span class="codeph"> défaut </span> à oui et contrôle si la partie <span class="codeph"> temporelle de la chaîne de date est sortie en GMT ( oui </span>) ou le fuseau horaire du compte ( <span class="codeph"> non </span>). </p> <p>voir. </p> <p>L'attribut <span class="codeph"> de langue </span> contrôle la langue et les conventions locales de la chaîne de date de sortie. <span class="codeph">0 </span> (par défaut) signifie « Langage de compte d'utilisation ». <span class="codeph">2 </span> signifie « Utiliser le langage documentaire ». La <span class="codeph"> </span> valeur <span class="codeph"> </span> linguistique 1 est réservée à une utilisation future). Toute <span class="codeph"> autre </span> valeur linguistique est interprétée comme un <span class="codeph"> identifiant </span> de langue spécifique, par exemple, en-US signifie "anglais (États-Unis)". </p> <p>voir. </p> <p>L'attribut </span> de longueur en option <span class="codeph"> est utilisé pour limiter la longueur des chaînes affichées, avec un défaut de 80 caractères. </span></p> <p>L'attribut </span> de codage optionnel <span class="codeph"> contrôle si la sortie est codée HTML, JavaScript codée, Perl encodé, URL encodé ou non encodé, pour la sortie sur la page de résultats. La valeur <span class="codeph"> par </span> défaut <span class="codeph"> </span>de l'encodage est html . Normalement, vous n'avez pas besoin de spécifier l'attribut de codage. </span></p> <p><span class="codeph"> L'attribut </span> de citations facultatives contrôle si la sortie des <span class="codeph"> éléments individuels est </span>entourée de doubles citations (ou de guillemets simples, si l'encodage est le cas). La valeur <span class="codeph"> par </span> <span class="codeph"> défaut </span>des devis n'est pas . </p> <p>L'attribut des virgules en option <span class="codeph"> contrôle si la sortie des éléments individuels est séparée par des virgules. </span> La valeur <span class="codeph"> par défaut </span> <span class="codeph"> des </span>virgules est oui . </span> L'attribut <span class="codeph"> des virgules est ignoré pour les champs de type non-liste. </span></p> <p>L'attribut </span> des unités facultatives <span class="codeph"> contrôle les unités de distance appliquées à un champ de sortie de recherche de proximité. La valeur <span class="codeph"> par </span> défaut des unités est déterminée à partir du paramètre « Unités par défaut » du champ de type de localisation associé au champ de sortie de recherche de proximité donné. </span></p> <p>voir. </p> <p>L'attribut séparateur optionnel <span class="codeph"> définit le caractère unique, ou délimiteur, qui est inséré entre les valeurs de la sortie pour les champs de type liste. </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-display-field-values name="field-name"&gt; ... &lt;search-display-field-values&gt; </span>&lt;/search-display-field-values&gt;&lt;/search-display-field-values&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise crée une boucle pour l'énumération des valeurs de champ de métadonnées (url, titre, desc, <span class="uicontrol"> clés, </span> <span class="uicontrol"> cible, </span>corps, alt, date, charset, et le langage ou les champs définis sous <span class="uicontrol"> Options </span> - Métadonnées - Définitions ) pour le résultat actuel. Ne pas nicquer <span class="codeph"> cette balise à l'intérieur d'une autre &lt;search-display-field-values&gt; </span> balise.&lt;/search-display-field-values&gt; L'attribut <span class="codeph"> de nom </span> spécifie le nom du champ contenant les valeurs à énumérer. Cette balise est plus utile <span class="uicontrol"> avec </span> les champs <span class="uicontrol"> </span> qui <span class="uicontrol"> ont </span> l'attribut Allow Lists vérifié (sous Options ' Metadata ' <span class="uicontrol"> Définitions). </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-display-field-value date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"&gt; </span>&lt;/search-display-field-value&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise produit la valeur du champ de métadonnées (url, titre, desc, clés, cible, <span class="uicontrol"> corps, alt, date, charset, et le langage ou les champs définis sous Options </span> <span class="uicontrol"> - </span> Métadonnées - <span class="uicontrol"> Définitions </span>) pour le courant <span class="codeph"> &lt;search-display-field-values&gt; </span> itération en boucle. &lt;/search-display-field-values&gt; Cette balise n'est valable qu'à l'intérieur d'une <span class="codeph"> &lt;search-display-field-values&gt; </span> boucle.&lt;/search-display-field-values&gt; Le <span class="codeph"> format </span>de <span class="codeph"> </span> date, le gmt et <span class="codeph"> les attributs de </span> langue ne sont pertinents que si le type de contenu du nom de champ spécifié dans l'étiquette d'enclos <span class="codeph"> &lt;search-display-field-values&gt; </span> est <span class="codeph"> la date </span>.&lt;/search-display-field-values&gt; L'attribut <span class="codeph"> </span> de format de date prend une <span class="codeph"> chaîne </span>de <span class="codeph"> format </span> <span class="codeph"> de date de style UNIX telle que « % A , %B %d </span>, <span class="codeph"> % Y </span>» (pour « lundi, 25 juillet 2016 »). L'attribut <span class="codeph"> </span> gmt <span class="codeph"> par </span> défaut à oui et contrôle si la <span class="codeph"> partie </span>temporelle de la chaîne <span class="codeph"> de date est sortie en GMT ( oui ) ou le fuseau horaire du compte ( non </span>). </p> <p>L'attribut <span class="codeph"> de langue </span> contrôle la langue et les conventions locales de la chaîne de date de sortie. <span class="codeph">0 </span> (par défaut) signifie « Langage de compte d'utilisation ». Toute <span class="codeph"> autre </span> valeur linguistique est interprétée comme un <span class="codeph"> identifiant </span> de langue spécifique, par exemple, en-US signifie "anglais (États-Unis)". </p> <p>L'attribut </span> de codage optionnel <span class="codeph"> contrôle si la sortie est codée HTML, JavaScript codée, Perl encodé, URL encodé ou non encodé, pour la sortie sur la page de résultats. La valeur <span class="codeph"> par </span> défaut <span class="codeph"> </span>de l'encodage est html . Normalement, vous n'avez pas besoin de spécifier l'attribut de codage. </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-display-field-value-count name="field-name"&gt; </span>&lt;/search-display-field-value-count&gt; </p> </td> 
   <td colname="col2"> <p>Produit le nombre total de valeurs dans le résultat actuel pour le champ de métadonnées (url, titre, desc, clés, <span class="uicontrol"> </span> cible, corps, alt, date, charset, et le langage ou les champs définis sous Options - <span class="uicontrol"> Métadonnées </span> - <span class="uicontrol"> Définitions </span>) spécifié avec l'attribut de nom. Cette balise peut apparaître n'importe où dans la boucle de résultats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-display-field-value-counter&gt; </span>&lt;/search-display-field-value-counter&gt; </p> </td> 
   <td colname="col2"> <p>Sortie du compteur ordinal (1, 2, 3, et <span class="codeph"> ainsi de suite) pour l'itération de &lt;search-display-field-values&gt; </span> boucle actuelle.&lt;/search-display-field-values&gt; Cette balise n'est valable qu'à l'intérieur d'une <span class="codeph"> &lt;search-display-field-values&gt; </span> boucle.&lt;/search-display-field-values&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-dynamic-facet-fields&gt; </span>&lt;/search-dynamic-facet-fields&gt; </p> </td> 
   <td colname="col2"> <p>Commence un contexte de boucle pour tous les champs à facettes dynamiques retournés pour cette recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-dynamic-facet-field-name&gt; </span>&lt;/search-dynamic-facet-field-name&gt; </p> </td> 
   <td colname="col2"> <p>Sortie du nom du champ dynamique-facet actuel, pour cette itération de boucle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--><span class="codeph"> &lt;search-result-trace encoding="html/javascript/ json/perl/url/none"&gt; </span>&lt;/search-result-trace&gt; </p> </td> 
   <td colname="col2"> <p>Informations sur les extrants liées au placement du résultat actuel, par exemple, toutes les actions axées sur les résultats qui ont affecté la position du résultat. </p> <p>Le format de sortie de cette balise est JSON comme dans l'exemple suivant : </p> <p> 
     <codeblock>
       { 
        "sliceID": 5, 
        "indexID": 5894, 
        "finalScore": 98,5, 
        "dynamicScore": 15.3, 
        "staticScore": 55.456, 
        "position": 1, 
        "rbtaActionListID": 117, 
        "rbtaActionID": 57 
      } 
     </codeblock> </p> 
    <!--<p> Results added to the results set by way of <codeph>rbta</codeph> have a "naturalPosition" value of -1. </p>--> <p><span class="codeph"> L'attribut </span> d'encodage est facultatif; la valeur <span class="codeph"> par </span>défaut est html . </p> <p> <p>Remarque : cette balise <span class="codeph"> n'a de </span> sortie que si le sp-trace 1 est spécifié avec les paramètres de requête de recherche de base. </p> </p> <p>Voir la rangée 48 dans le tableau trouvé dans . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Les résultats bouclent les balises conditionnelles{#section_35C367969E384A06A9865E388F1F9360}

Les balises suivantes incluent conditionnellement le HTML entre eux.

<table id="table_C49347072D074E888DC5A8F3CE7C3113"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-title&gt; ... &lt;/search-if-title&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-title&gt; ... &lt;/search-if-not-title&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le HTML entre <span class="codeph"> eux si le prochain appel à &lt;search-title&gt; </span> retourner (ou ne retourne pas) le texte du titre du document.&lt;/search-title&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-description length="XX"&gt;... /recherche-if-description </span> &lt;/search-if-description&gt; </p> <p> <span class="codeph">&lt;search-if-not-description&gt; ... &lt;/search-if-not-description&gt;</span> </p> </td> 
   <td colname="col2"> <p> Ces balises incluent le HTML entre <span class="codeph"> eux si le prochain appel à &lt;search-description&gt; </span> retourner (ou ne retourne pas) le texte de la description du document.&lt;/search-description&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-bodytext&gt; ... &lt;/search-if-bodytext&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-bodytext&gt; ... &lt;/search-if-not-bodytext&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le HTML entre <span class="codeph"> eux si le prochain appel à &lt;search-bodytext&gt; </span> retourner (ou ne retourne pas) le texte de l'organisme du document.&lt;/search-bodytext&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-context length="XX"&gt; ... &lt;/search-if-context&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-context&gt; ... &lt;/search-if-not-context&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le HTML entre <span class="codeph"> eux si le prochain appel à &lt;search-context&gt; </span> retourner (ou ne retourne pas) une chaîne de contexte non vide.&lt;/search-context&gt; L'attribut de longueur remplace l'attribut de longueur sur n'importe quelle <span class="codeph"> &lt;search-context&gt; </span> balise jointe.&lt;/search-context&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-any-context length="XX"&gt;... /recherche-si-tout-contexte </span> &lt;/search-if-any-context&gt; </p> <p> <span class="codeph">&lt;search-if-not-any-context&gt; ... &lt;/search-if-not-any-context&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le HTML entre eux s'il y a (ou n'est pas) une chaîne de contexte associée au résultat. L'attribut de longueur remplace l'attribut de longueur sur n'importe quelle <span class="codeph"> &lt;search-context&gt; </span> balise jointe.&lt;/search-context&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-score lower="XX" upper="yy" rank="dynamic/static/dynamic-raw/static-raw/final-raw"&gt; ... &lt;/search-if-score&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-score lower="XX" upper="yy" rank="dynamic/static"&gt; ... &lt;/search-if-not-score&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le HTML entre eux si le score du résultat actuel est (ou n'est pas) entre XX et YY. Utile pour l'ajout de balles ou de graphiques pour montrer la pertinence du résultat. Si vous avez défini un <span class="uicontrol"> champ </span> <span class="uicontrol"> de type </span> <span class="uicontrol"> rang </span>sous Options ' Metadata ' Définitions , <span class="codeph"> vous pouvez vérifier le classement dynamique en définissant l'attribut de rang en dynamique ( &lt;search-if-score rank="dynamic" lower="XX" upper="YY"&gt; </span>).&lt;/search-if-score&gt; Vous pouvez vérifier le rang de page statique <span class="codeph"> en définissant l'attribut de rang statique ( &lt;search-if-score rank="static" lower="XX" upper="YY"&gt; </span>).&lt;/search-if-score&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-field name="field-name" value="value"&gt; ... &lt;/search-if-field&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-field name="field-name" value="value"&gt; ... &lt;/search-if-not-field&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises avancées incluent le HTML entre eux en fonction de si le champ spécifié dans l'attribut "nom" a du contenu ou non. Si l'attribut « valeur » optionnel est spécifié, les balises incluent le HTML entre eux en fonction de la valeur donnée correspond (ou ne correspond pas) à la valeur du champ dans le résultat actuel. Ces balises ne fonctionnent que <span class="codeph"> dans la boucle de résultats (entre &lt;search-results&gt; </span> et <span class="codeph"> &lt;/search-results&gt; </span> les balises). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Les résultats bouclent les balises de liaison d'ancrage{#section_C5FAEF520E9E42ADAD1F90651922AA02}

<table id="table_90B49709BD5A459EAE152066529B848B"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt; ... &lt;/search-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette paire de balises crée un lien d'ancrage autour du HTML entre eux. Lorsque le lien est cliqué, la page de résultats s'affiche. Un attribut cible optionnel spécifie la fenêtre nommée dans laquelle les navigateurs capables d'encadrer doivent afficher la page de résultats. </p> <p>Définir l'attribut hbx-activer à "oui" pour profiter de l'analyse disponible via HBX. Définir le nom hbx-linkid au nom d'un champ de métadonnées que vous souhaitez suivre. Par exemple, pour suivre les résultats de recherche par numéro SKU, définir le nom hbx-linkid au nom du champ Meta-data qui contient des informations SKU. </p> <p>Les champs de type date ne sont actuellement pas pris en charge. La valeur du nom hbx-linkid est annexée à l'ID de lien dans l'ancre générée. La valeur de l'attribut hbx-linkid-none est annexée à l'ID de lien chaque fois que le champ de métadonnées nommé est vide. La valeur de hbx-linkid-longueur limite le nombre de caractères récupérés et affichés à partir de l'étiquette Meta. Le nombre par défaut de caractères est de 12. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-smart-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt; ... &lt;/search-smart-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette paire de balises <span class="codeph"> est similaire aux &lt;search-link&gt;...&lt;/search-link&gt; </span> balises. Lorsque les liens d'ancrage générés sont cliqués, la page de résultats s'affiche, mais avec la page défilée à l'étiquette d'ancrage la plus proche précédant le résultat. Pour les liens PDF, le visualiseur Acrobat affiche la page qui contient le résultat. Un attribut cible optionnel spécifie la fenêtre nommée dans laquelle les navigateurs capables d'encadrer doivent afficher la page de résultats. </p> <p>Définir l'attribut hbx-activer à "oui" pour profiter de l'analyse disponible via HBX. Définir le nom hbx-linkid au nom d'un champ de métadonnées que vous souhaitez suivre. Par exemple, pour suivre les résultats de recherche par numéro SKU, définir le nom hbx-linkid au nom du champ Meta-data qui contient des informations SKU. </p> <p>Les champs de type date ne sont actuellement pas pris en charge. La valeur du nom hbx-linkid est annexée à l'ID de lien dans l'ancre générée. La valeur de l'attribut hbx-linkid-none est annexée à l'ID de lien chaque fois que le champ de métadonnées nommé est vide. La valeur de hbx-linkid-longueur limite le nombre de caractères récupérés et affichés à partir de l'étiquette Meta. Le nombre par défaut de caractères est de 12. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-link-extension&gt; ... &lt;/search-if-link-extension&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-link-extension&gt; ... &lt;/search-if-not-link-extension&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le HTML entre eux si un attribut de valeur spécifie une extension qui correspond à la fin de l'URL pour le résultat. Cette balise est utile pour inclure un graphique dans les résultats de recherche basés sur l'extension du lien. L'attribut de valeur est une liste d'une ou plusieurs extensions (espace séparé) comme suit: VALUE '.pdf" ou VALUE '.html .htm". </p> </td> 
  </tr> 
 </tbody> 
</table>

## Étiquettes conditionnelles de position de boucle{#section_E0C29DDA09E043C9A396F36334F05EBB}

Les balises suivantes incluent sous condition le texte entre eux. Ils ne peuvent apparaître qu'à &lt;&gt; `search-results>` l'intérieur des balises "looping": et `<search-field-values>`. Ils sont utilisés pour tester la position du résultat actuel dans l'ensemble de résultats.

<table id="table_9CA9445FC1D4439EB65ADFD17B2D890D"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-first&gt; ... &lt;/search-if-first&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-first&gt; ... &lt;/search-if-not-first&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le texte entre eux si le résultat actuel est (ou <span class="codeph"> n'est pas) le premier résultat sur la page (lorsqu'il est utilisé à l'intérieur &lt;search-results&gt; </span>) ou la première valeur de champ (lorsqu'il est utilisé à l'intérieur <span class="codeph"> &lt;search-field-values&gt; </span>).&lt;/search-field-values&gt; &lt;/search-results&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-last&gt; ... &lt;/search-if-last&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-last&gt; ... &lt;/search-if-not-last&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le texte entre eux si le résultat actuel est (ou <span class="codeph"> n'est pas) le dernier résultat sur la page (lorsqu'il est utilisé à l'intérieur &lt;search-results&gt; </span>) ou la dernière valeur de champ (lorsqu'il est utilisé à l'intérieur <span class="codeph"> &lt;search-field-values&gt; </span>).&lt;/search-field-values&gt; &lt;/search-results&gt; Cette balise peut être utilisée pour insérer un séparateur entre les résultats. Par exemple, cela <span class="codeph"> insère un&lt;hr&gt;</span> tag entre les résultats: </p> <p> 
     <codeblock class="syntax html">
       &lt;search-results&gt; 
         &lt;search-lt&gt;tr&lt;search-if-alt&gt; classe "alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
            &lt;td&gt;&lt;search-url&gt;&lt;/search-url&gt;&lt;/td&gt; 
          
      &lt;/search-gt&gt;&lt;/search-lt&gt;&lt;/search-results&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-inner&gt; ... &lt;/search-if-inner&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-inner&gt; ... &lt;/search-if-not-inner&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le texte entre eux si le résultat actuel n'est <span class="codeph"> pas le premier ni le dernier résultat sur la page (lorsqu'il est utilisé à l'intérieur &lt;search-results&gt; </span>) ou n'est pas la première ou la dernière valeur de champ (lorsqu'il est utilisé à l'intérieur <span class="codeph"> &lt;search-field-values&gt; </span>).&lt;/search-field-values&gt; &lt;/search-results&gt; La version non de l'étiquette teste si le résultat est le premier ou le dernier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-alt&gt; ... &lt;/search-if-alt&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-alt&gt; ... &lt;/search-if-not-alt&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le texte entre eux si le résultat actuel est (ou <span class="codeph"> n'est pas) un résultat alternatif sur la page (lorsqu'il est utilisé à l'intérieur &lt;search-results&gt; </span>) ou une valeur de champ alternative (lorsqu'il est utilisé à l'intérieur <span class="codeph"> &lt;search-field-values&gt; </span>).&lt;/search-field-values&gt; &lt;/search-results&gt; Les résultats « alternatifs » sont les deuxième, quatrième, sixième, et ainsi de suite, sur la page. Cet exemple s'applique à une classe différente pour les rangées de table alternatives. Notez l'utilisation <span class="codeph"> &lt;search-lt&gt; </span> et <span class="codeph"> &lt;search-gt&gt; </span> <span class="codeph"> pour permettre à l'étiquette &lt;search-if-alt&gt; </span> d'être placée « à l'intérieur » de la <span class="codeph">&lt;tr&gt;</span> tag.&lt;/tr&gt;&lt;/search-if-alt&gt;&lt;/search-gt&gt;&lt;/search-lt&gt; </p> <p> 
     <codeblock class="syntax html">
           &lt;search-results&gt; 
             &lt;search-lt&gt;tr&lt;search-if-alt&gt; classe "alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
                &lt;td&gt;&lt;search-url&gt;&lt;/search-url&gt;&lt;/td&gt; 
              
          &lt;/search-gt&gt;&lt;/search-lt&gt;&lt;/search-results&gt; 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-even&gt; ... &lt;/search-if-even&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-even&gt; ... &lt;/search-if-not-even&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent le texte entre eux si le résultat actuel est (ou <span class="codeph"> n'est pas) un résultat pair (lorsqu'il est utilisé à l'intérieur) &lt;search-results&gt; </span>ou une valeur de champ pair (lorsqu'il est utilisé à l'intérieur <span class="codeph"> &lt;search-field-values&gt; </span>).&lt;/search-field-values&gt; &lt;/search-results&gt; Un résultat de recherche est <span class="codeph"> pair-numéroté si sa &lt;search-index&gt; </span> valeur est égale.&lt;/search-index&gt; En d'autres termes, si sa position dans l'ensemble des résultats est égale. Cela peut être <span class="codeph"> différent de &lt;search-if-alt&gt; </span> celui qui teste la position d'un résultat sur la page, pas dans l'ensemble&lt;/search-if-alt&gt; des résultats. Les deux tableaux suivants illustrent la différence : </p> </td> 
  </tr> 
 </tbody> 
</table>

### Première page, sp'n-1{#first_page}

<table id="table_0334F560A1F840A9A1447F357A888B6E">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>index </p> </th> 
   <th colname="col2" class="entry"> <p>résultat </p> </th> 
   <th colname="col3" class="entry"> <p>encore? </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Premier résultat </p> </td> 
   <td colname="col3"> <p>non </p> </td> 
   <td colname="col4"> <p>non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Deuxième résultat </p> </td> 
   <td colname="col3"> <p>ouais </p> </td> 
   <td colname="col4"> <p>ouais </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Troisième résultat </p> </td> 
   <td colname="col3"> <p>non </p> </td> 
   <td colname="col4"> <p>non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Quatrième résultat </p> </td> 
   <td colname="col3"> <p>ouais </p> </td> 
   <td colname="col4"> <p>ouais </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Cinquième résultat </p> </td> 
   <td colname="col3"> <p>non </p> </td> 
   <td colname="col4"> <p>non </p> </td> 
  </tr> 
 </tbody> 
</table>

### Page postérieure, sp-n-10{#later_page}

<table id="table_00DAAFA92C994387B38737C8435AB3D4">  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>index </p> </th> 
   <th colname="col2" class="entry"> <p>résultat </p> </th> 
   <th colname="col3" class="entry"> <p>encore? </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>Dixième résultat </p> </td> 
   <td colname="col3"> <p>ouais </p> </td> 
   <td colname="col4"> <p>non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p>Onzième résultat </p> </td> 
   <td colname="col3"> <p>non </p> </td> 
   <td colname="col4"> <p>ouais </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>12e résultat </p> </td> 
   <td colname="col3"> <p>ouais </p> </td> 
   <td colname="col4"> <p>non </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>Treizième résultat </p> </td> 
   <td colname="col3"> <p>non </p> </td> 
   <td colname="col4"> <p>ouais </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>Quatorzième résultat </p> </td> 
   <td colname="col3"> <p>ouais </p> </td> 
   <td colname="col4"> <p>non </p> </td> 
  </tr> 
 </tbody> 
</table>

Enfin, notez `<search-if-even>` que c'est toujours la même chose que `<search-if-alt>` pour les valeurs de champ de recherche puisque les valeurs de champ ne sont pas bipées.

## Étiquettes de liste de valeur de champ{#section_D3298B5F976447DBA0032B883DCC91B1}

Les balises avancées suivantes indiquent les valeurs de champ de sortie et les données connexes de l'ensemble des résultats de recherche. Ces balises ne donnent que `sp-sfvl-field` des sorties pour les champs spécifiés par les paramètres CGI dans la requête de recherche.

<table id="table_7854EEFBE7BB40338A84F7AE0381C0BA"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-field-value-list name="field-name" quotes="yes/no" commas="yes/no" data="values/counts/results" separator="X" sortby="none/values/counts/results" max-items="XX" date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"&gt; </span>&lt;/search-field-value-list&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise affiche une liste de valeurs de champ uniques, de nombres de valeurs ou de nombres de résultats dans l'ensemble des résultats. </p> <p>Cette balise ne donne de <span class="codeph"> la sortie que pour </span> les champs spécifiés par les paramètres CGI de sp-sfvl-field dans la requête de recherche. L'attribut « citations » en option contrôle si la sortie des éléments individuels est entourée de doubles citations (ou de guillemets simples, si l'encodage est le cas). La valeur par défaut des « devis » est « oui ». L'attribut « virgules » en option contrôle si la sortie des éléments individuels est séparée par des virgules. La valeur par défaut des " virgules " est "oui". L'attribut « données » en option contrôle si chaque valeur de champ unique est la sortie (les « valeurs » de données), le nombre total de chaque valeur de champ unique est la sortie (données » ou le nombre de résultats contenant chaque valeur unique (données » est la sortie. La valeur par défaut des « données » est « valeurs ». Pour les champs non-type de liste, les « comptes » et les « résultats » de données sont équivalents. L'attribut séparateur définit le caractère unique, ou délimiteur, à insérer entre les valeurs de la sortie. L'attribut optionnel "sortby" contrôle la commande de la sortie ; sortby "aucun" signifie pas d'ordre particulier, sortby "valeurs" signifie trier par valeurs de champ (en ordre ascendant ou descendant selon la propriété de tri du champ), triby "comptes" signifie trier dans l'ordre décroissant des comptes de valeur de champ, et triby "résultats" signifie trier dans l'ordre décroissant du nombre de résultats contenant chaque valeur. </p> <p>Notez que les « comptes » et les « résultats » de triby sont équivalents pour les champs non-list-type. L'attribut optionnel « max-items » limite le nombre d'éléments à la sortie. La valeur par défaut des « éléments max » est de -1, ce qui signifie « sortie de tous les éléments ». </p> <p>Il y a une limite absolue de 100 pour les objets max. Les attributs "format date", "gmt" et "langue" ne sont pertinents que si le type de contenu du champ spécifié est "date". L'attribut "date-format" prend une chaîne de format de date de style UNIX telle que "%A, %B %d, %Y" (pour "lundi, Juillet 25, 2016"). "gmt" par défaut à "oui" et contrôle si la partie temporelle de la chaîne de date doit être sortie dans GMT ("oui") ou le fuseau horaire du compte ("non"). </p> <p>voir. </p> <p>L'attribut « langue » contrôle la langue et les conventions locales de la chaîne de date de sortie. "0" (par défaut) signifie "Utiliser le langage du compte". Toute autre valeur "langue" est interprétée comme un identifiant de langue spécifique, par exemple, "en-US" signifie "anglais (États-Unis)". L'attribut « encodage » en option contrôle si les caractères de chaîne de sortie sont codés HTML, JavaScript codés, Perl codés, URL codés ou non codés, pour la sortie sur la page de résultats. La valeur par défaut de "codage" est "html". </p> <p>voir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-field-value-list-count name="field-name" value="field-value" results="yes/no"&gt; </span>&lt;/search-field-value-list-count&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise affiche les informations de comptage pour une liste de valeur donnée du champ de recherche. Il existe trois utilisations distinctes pour cette balise. Si seul l'attribut "nom" est fourni, cette balise donne le nombre de valeurs uniques pour le champ nommé dans l'ensemble des résultats. Si les attributs «nom» et «valeur» sont tous deux fournis, cette balise donne soit le nombre total de la valeur donnée dans l'ensemble des résultats (pour les résultats "non"), soit le nombre total de résultats contenant la valeur donnée dans l'ensemble des résultats (pour les résultats"oui"). La valeur par défaut des "résultats" est "non". Remarque : Pour les champs non-type de liste, les résultats « oui » et les résultats « non » sont équivalents. La valeur des « résultats » est ignorée si l'attribut « valeur » n'est pas fourni. Cette balise ne donne de <span class="codeph"> sortie que pour les </span> champs spécifiés par les paramètres CGI sp-sfvl-champ dans la requête de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-field-value-list-count name="field-name" value="field-value"&gt; ... &lt;/search-if-field-value-list-count&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-field-value-list-count name="field-name" value="field-value"&gt; ... &lt;/search-if-not-field-value-list-count&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises affichent le HTML <span class="codeph"> entre eux si l'appel équivalent avec &lt;search-field-value-list-count name="field-name" value="field-value"&gt; </span> les attributs donnés serait (ou ne serait pas) retourner une valeur supérieure&lt;/search-field-value-list-count&gt; à zéro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-single-field-value-list-count name="field-name"&gt; ... &lt;/search-if-single-field-value-list-count&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises affichent le contenu <span class="codeph"> entre eux si l'appel équivalent avec &lt;search-field-value-list-count name="field-name" value="field-value"&gt; </span> les attributs donnés serait (ou ne serait pas) retourner une valeur unique.&lt;/search-field-value-list-count&gt; Ceci est généralement utilisé lorsqu'un compte utilise des fentes de facettes. Avec les emplacements à facettes, vous ne souhaitez généralement afficher la fente de valeur que lorsque la fente de nom associée a un seul élément. Faire cette vérification dans le modèle de transport est plus efficace que de le faire dans la couche de présentation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Balises de boucle de liste de valeur de champ{#section_0717FA09F0FC449CB916883B0500A60E}

Les balises avancées suivantes énumèrent et évaluent les valeurs de champ de sortie et les données connexes de l'ensemble des résultats de recherche à l'aide d'une construction en boucle. Ces balises ne donnent que `sp-sfvl-field` des sorties pour les champs spécifiés par les paramètres CGI dans la requête de recherche.

<table id="table_BB19BF975DE4470190DB02015E5FABB2"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-field-values name="field-name" sortby="none/values/counts/results" max-items="XX"&gt; ... &lt;/search-field-values&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette balise crée une boucle pour l'énumération des valeurs de champ et des données connexes pour un champ particulier dans l'ensemble des résultats. Ne pas nicquer <span class="codeph"> cette balise à l'intérieur d'une autre &lt;search-field-values&gt; </span> balise.&lt;/search-field-values&gt; L'attribut "nom" spécifie le nom du champ contenant les valeurs à énumérer. L'attribut optionnel "sortby" contrôle l'ordre d'énumération: "aucun" signifie pas d'ordre particulier, "valeurs" signifie trier par les valeurs de champ (en ordre ascendant ou descendant selon la propriété de tri du champ), sortby "comptes" signifie trier dans l'ordre décroissant de compte de la valeur de champ, et les « résultats » de tri par le tri signifient trier dans l'ordre décroissant du nombre de résultats contenant chaque valeur. </p> <p>Notez que les « comptes » et les « résultats » de triby sont équivalents pour les champs non-list-type. . L'attribut optionnel « max-items » limite le nombre d'itérations à la valeur donnée. La valeur par défaut pour les «éléments max» est de -1, ce qui signifie «énumérer toutes les valeurs». </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-field-value date-format="date-format-string" encoding="html/javascript/json/perl/url/none" gmt="yes/no" language="0/language-id"&gt; </span>&lt;/search-field-value&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise dénote la valeur de champ pour l'itération de &lt;search-field-values&gt;boucle actuelle.&lt;/search-field-values&gt; Cette balise n'est valable qu'à l'intérieur d'une <span class="codeph"> &lt;search-field-values&gt; </span> boucle.&lt;/search-field-values&gt; Les attributs "format date", "gmt" et "langue" ne sont pertinents que si le type de contenu du nom de champ spécifié dans l'étiquette ci-même &lt;search-field-values&gt;est "date".&lt;/search-field-values&gt; L'attribut "date-format" prend une chaîne de format de date de style UNIX telle que "%A, %B %d, %Y" (pour "lundi, Juillet 25, 2016"). </p> <p>voir. </p> <p>L'attribut « encodage » en option contrôle si les caractères de chaîne de sortie sont codés HTML, JavaScript codés, Perl codés, URL codés ou non codés, pour la sortie sur la page de résultats. La valeur par défaut de "codage" est "aucun". Normalement, vous n'avez pas besoin de spécifier l'attribut de codage. "gmt" par défaut à "oui" et contrôle si la partie temporelle de la chaîne de date doit être sortie dans GMT ("oui") ou le fuseau horaire du compte ("non"). L'attribut « langue » contrôle la langue et les conventions locales de la chaîne de date de sortie. "0" (par défaut) signifie "Utiliser le langage du compte". Toute autre valeur "langue" est interprétée comme un identifiant de langue spécifique, par exemple, "en-US" signifie "anglais (États-Unis)". </p> <p>voir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-field-value-count results="yes/no"&gt; </span>&lt;/search-field-value-count&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise dénote le <span class="codeph"> nombre associé à l'itération de &lt;search-field-values&gt; </span> boucle actuelle.&lt;/search-field-values&gt; Le nombre de résultats est soit le nombre de résultats dans l'ensemble des résultats contenant la valeur du champ (résultats "oui"), soit le nombre total de la valeur du champ dans l'ensemble des résultats. La valeur par défaut des "résultats" est "non". </p> <p>Pour les champs non-list-type, les résultats « oui » et les résultats « non » sont équivalents. Cette balise n'est valable qu'à l'intérieur d'une <span class="codeph"> &lt;search-field-values&gt; </span> boucle.&lt;/search-field-values&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-field-value-counter&gt; </span>&lt;/search-field-value-counter&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise produit le compteur ordinal pour l'itération de <span class="codeph"> &lt;search-field-values&gt; </span> boucle actuelle.&lt;/search-field-values&gt; Cette balise n'est valable qu'à l'intérieur d'une <span class="codeph"> &lt;search-field-values&gt; </span> boucle.&lt;/search-field-values&gt; </p> </td> 
  </tr> 
 </tbody> 
</table>

## Suggérer des balises{#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC}

Suggest fournit un convivial "Avez-vous l'un des besoins?" pour suggérer d'autres termes de recherche. Si un utilisateur a mal orthographié un terme de recherche, par exemple, Suggest peut aider l'utilisateur à trouver des résultats en suggérant une orthographe correcte. Le système peut également suggérer des mots clés connexes qui peuvent aider un utilisateur à découvrir des résultats. Lorsque vous génèrez des suggestions, le service Suggest utilise deux dictionnaires **[!UICONTROL :]** **[!UICONTROL l'un basé sur la langue du compte (set under Indexing - Mots et Langues]** - **[!UICONTROL Langue]), et l'autre qui est uniquement construit à partir des mots clés dans l'index de** compte.

>[!NOTE]
>
>Le service Suggest ne fonctionne pas pour le chinois, le japonais ou le coréen.

<table id="table_8E014DED2453470596AD5FBCE371CF29"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-suggestions&gt; ... &lt;/search-if-suggestions&gt;</span> </p> </td> 
   <td colname="col2"> <p>Entourez ces balises avec n'importe <span class="codeph"> quel "Suggérer" balises de modèle, tels que &lt;search-suggestion&gt; </span>, <span class="codeph"> &lt;search-suggestion-link&gt; </span>, et ainsi de suite.&lt;/search-suggestion-link&gt; &lt;/search-suggestion&gt; Si la recherche génère des suggestions, le moteur de recherche s'en sort et traite tout ce qui se trouve entre l'étiquette ouverte et la balise étroite. Si la recherche ne génère pas de suggestions, aucun contenu imparable n'est la sortie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-suggestions&gt; ... &lt;/search-suggestions&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette balise génère la boucle "Suggérer", qui contient une liste de termes de recherche suggérés (par exemple, "intention", "intention" et "intention", pour une requête initialement saisie comme "intendées"). Lors de la génération de la liste des termes, le moteur de recherche répète toutes les balises HTML et/ou modèles imparables jusqu'à cinq fois, soit le nombre maximum de suggestions. Utilisez l'attribut de comptage pour spécifier le nombre de suggestions générées (entre 0 et 5). </p> <p><span class="codeph"> &lt;search-suggestions&gt; </span> L'étiquette peut apparaître plusieurs fois sur la page pour répéter la liste des suggestions.&lt;/search-suggestions&gt; Plusieurs suggestions sont triées en fonction du nombre de résultats que chaque donne. </p> <p>Nest <span class="codeph"> &lt;search-suggestions&gt; </span> l'étiquette entre <span class="codeph"> &lt;search-if-suggestions&gt; </span> les balises&lt;/search-if-suggestions&gt; ouvertes et proches.&lt;/search-suggestions&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-suggestion-link&gt; ... &lt;/search-suggestion-link&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette balise génère un lien vers la requête de recherche originale à l'aide du terme de recherche suggéré sélectionné au lieu du terme original. La balise accepte et imprime simplement n'importe quel attribut HTML tel que la classe, la cible et le style. La balise peut également accepter un attribut URL, dont la valeur est utilisée comme URL de base pour le lien généré. Les balises ne <span class="codeph"> peuvent apparaître qu'à l'intérieur de la &lt;search-suggestions&gt; </span> boucle.&lt;/search-suggestions&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-suggestion-text&gt;&lt;/search-suggestion-text&gt;</span> </p> </td> 
   <td colname="col2"> <p>Cette balise imprime le terme de requête actuellement suggéré (par exemple, « intention » pour une requête initialement saisie sous le titre « intendds »). L'étiquette n'a pas d'attributs et ne peut apparaître qu'à l'intérieur de la <span class="codeph"> &lt;search-suggestions&gt; </span> boucle.&lt;/search-suggestions&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-not-suggestions&gt; ... &lt;/search-if-not-suggestions&gt;</span> </p> </td> 
   <td colname="col2"> <p>Si la recherche ne génère aucune suggestion, le moteur de recherche s'en sort et traite tout ce qui se trouve entre l'étiquette ouverte et la balise étroite. Si la recherche génère des suggestions, aucun contenu imparable n'est la sortie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if[-not]-first-suggestion&gt; ... &lt;/search-if[-not]-first-suggestion&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises conditionnelles incluent le HTML entre eux en fonction de la question de savoir si le terme suggéré est le premier terme de la boucle Suggest. Les balises doivent apparaître <span class="codeph"> entre les balises ouvertes et les &lt;search-suggestion&gt; </span> balises étroites.&lt;/search-suggestion&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if[-not]-last-suggestion&gt; ... &lt;/search-if[-not]-last-suggestion&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises conditionnelles incluent le HTML entre eux en fonction de si le terme suggéré est le dernier terme dans la boucle Suggest. Les balises doivent apparaître <span class="codeph"> entre les balises ouvertes et les &lt;search-suggestion&gt; </span> balises étroites.&lt;/search-suggestion&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-suggestion-index&gt; </span>&lt;/search-suggestion-index&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise renvoie l'index numérique du terme de recherche suggéré en cours. L'étiquette doit apparaître <span class="codeph"> entre les balises ouvertes et les &lt;search-suggestion&gt; </span> balises étroites.&lt;/search-suggestion&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-suggestion-total&gt; </span>&lt;/search-suggestion-total&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise renvoie le nombre total de termes de recherche suggérés générés. L'étiquette doit apparaître <span class="codeph"> entre les balises ouvertes et les &lt;search-suggestion&gt; </span> balises étroites.&lt;/search-suggestion&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-suggestion-result-count&gt; </span>&lt;/search-suggestion-result-count&gt; </p> </td> 
   <td colname="col2"> <p>Cette balise renvoie le nombre total de résultats pour le terme de recherche suggéré. L'étiquette doit apparaître <span class="codeph"> entre les balises ouvertes et les &lt;search-suggestion&gt; </span> balises étroites.&lt;/search-suggestion&gt; </p> </td> 
  </tr> 
 </tbody> 
</table>

## Étiquettes de chaîne de modèle{#section_67E3D529661F4F03A1FF469D9D658CAF}

Les balises suivantes extradent une chaîne dans le HTML à ce point du modèle.

<table id="table_141DA461BC7442C4A343159F151277B3"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-body&gt; </span>&lt;/search-body&gt; </p> </td> 
   <td colname="col2"> <p>La balise de corps HTML avec tous les paramètres de couleur de lien de recherche que la section De base de l'apparence définit sous le lien Template. Ajoutez un attribut d'arrière-plan à cette balise pour afficher des images d'arrière-plan sur la page de résultats. Tous les attributs de couleur ajoutés à cette balise l'emportent sur les paramètres de couleur search Link que la section Basic Look définit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-header&gt; </span>&lt;/search-header&gt; </p> </td> 
   <td colname="col2"> <p>Le HTML pour l'en-tête des résultats de recherche tel que définir dans la section Regard de base sous le lien Template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-cdata&gt; ... &lt;/search-cdata&gt;</span> </p> </td> 
   <td colname="col2"> <p>Les balises de recherche-cdata sont remplacées <span class="codeph"> par leurs équivalents XML &lt;search-cdata&gt; </span> : <span class="codeph"> &lt;! &lt;/search-cdata&gt;[CDATA[" et </span> le tag <span class="codeph"> est remplacé </span>par " ]] ". Un parser XML n'inclut aucune information entre l'étiquette ouverte et la balise étroite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-query query-number="XX" encoding="html/javascript/json/perl/url/none"&gt; </span>&lt;/search-query&gt; </p> </td> 
   <td colname="col2"> <p>La requête que le visiteur a saisie. L'attribut avancé et optionnel "qui est le nombre de requêtes" contrôle la chaîne de requête numérotée qui est sortie par cette balise. Par exemple, <span class="codeph"> &lt;search-query query-number="1"&gt; </span> produit le <span class="codeph"> contenu du paramètre </span> sp-q-1 cgi.&lt;/search-query&gt; Si le "numéro de requête" n'est pas spécifié, ou si le <span class="codeph"> nombre de </span>requêtes est "0", la requête principale ( sp-q ) est la sortie. L'attribut « encodage » en option contrôle si la sortie est codée HTML, JavaScript codée, Perl codée, URL codée ou non encodée, pour la sortie sur la page de résultats. La valeur par défaut de "codage" est "html". Normalement, vous n'avez pas besoin de spécifier l'attribut de codage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-total&gt; </span>&lt;/search-total&gt; </p> </td> 
   <td colname="col2"> <p>Nombre total de résultats pour cette recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-count&gt; </span>&lt;/search-count&gt; </p> </td> 
   <td colname="col2"> <p>Nombre de résultats rapportés pour cette page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-lower&gt; </span>&lt;/search-lower&gt; </p> </td> 
   <td colname="col2"> <p>Le nombre du premier résultat déclaré pour cette page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-upper&gt; </span>&lt;/search-upper&gt; </p> </td> 
   <td colname="col2"> <p>Le nombre du dernier résultat déclaré pour cette page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-prev-count&gt; </span>&lt;/search-prev-count&gt; </p> </td> 
   <td colname="col2"> <p>Nombre de résultats communiqués pour la page précédente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-next-count&gt; </span>&lt;/search-next-count&gt; </p> </td> 
   <td colname="col2"> <p>Nombre de résultats communiqués pour la page suivante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-time&gt; </span>&lt;/search-time&gt; </p> </td> 
   <td colname="col2"> <p>Le temps en quelques secondes pour cette recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-logo&gt; </span>&lt;/search-logo&gt; </p> </td> 
   <td colname="col2"> <p>Le HTML pour le logo de recherche qui est configuré pour votre compte, le cas échéant. Ce logo est l'image qui donne crédit à la recherche de site / merchandising </p> <p>La plupart des comptes n'ont pas de logo de recherche associé pour le moment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-collection all="name"&gt; </span>&lt;/search-collection&gt; </p> </td> 
   <td colname="col2"> <p>La collecte des résultats de cette recherche. L'attribut « tout » en option est utilisé pour donner le nom de la collection qui représente l'ensemble du site Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-form&gt; ...&lt;/search-form&gt;</span> </p> </td> 
   <td colname="col2"> <p>Les inserts commencent et terminent les balises de forme. Insère la méthode et les attributs d'action dans l'étiquette de formulaire de début. Accepte les attributs supplémentaires, y compris l'attribut dir'"RTL" pour la langue ainsi que les attributs "nom" et "onSubmit" liés à JavaScript. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-input-account&gt; </span>&lt;/search-input-account&gt; </p> </td> 
   <td colname="col2"> <p>Insère une balise d'entrée de formulaire qui spécifie le numéro de votre compte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-input-gallery&gt; </span>&lt;/search-input-gallery&gt; </p> </td> 
   <td colname="col2"> <p>Insère une balise d'entrée de formulaire qui spécifie le numéro de la galerie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-input-query query-number="XX"&gt; </span>&lt;/search-input-query&gt; </p> </td> 
   <td colname="col2"> <p>Insère une balise d'entrée de formulaire qui spécifie la chaîne de requête. L'attribut avancé et optionnel « nombre de requêtes » contrôle la requête numérotée utilisée pour l'étiquette d'entrée de formulaire. Par exemple, <span class="codeph"> &lt;search-input-query query-number="1"&gt; </span> dédite une <span class="codeph"> balise d'entrée </span> de formulaire pour la requête sp-q-1.&lt;/search-input-query&gt; Si le « numéro de requête » n'est pas spécifié ou si « numéro <span class="codeph"> de requête </span> » est « 0 », une balise d'entrée pour la requête sp-q principale est insérée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-input-collections all="name"&gt; </span>&lt;/search-input-collections&gt; </p> </td> 
   <td colname="col2"> <p>Insère une balise de sélection de formulaire et HTML associé qui affichent le menu de sélection des collections. L'attribut « tout » en option est utilisé pour donner le nom de la collection qui représente l'ensemble du site Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-lt&gt; </span>&lt;/search-lt&gt; </p> </td> 
   <td colname="col2"> <p>Insère la sortie de l'une des balises de modèle de recherche dans d'autres balises HTML ou modèles sur la page des résultats. <span class="codeph">insère un caractère inférieur à celui. &lt;search-lt&gt; </span> &lt;/search-lt&gt; Utilisez <span class="codeph"> &lt;search-lt&gt; </span> et <span class="codeph"> &lt;search-gt&gt;fournit un moyen d'échapper à la définition d'une balise afin que vous puissiez utiliser les balises de modèle de recherche comme valeurs d'attribut. </span> &lt;/search-gt&gt; &lt;/search-lt&gt; Lorsque le modèle est rendu en réponse à une&lt;) replaces="" the=""&gt; &lt;/)&gt; <span class="codeph"> recherche, un signe inférieur à &lt;search-lt&gt; </span> l'étiquette ( tag.&lt;/search-lt&gt; Par exemple, <span class="codeph"> &lt;search-link&gt; </span> est équivalent à .&lt;/search-link&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-gt&gt; </span>&lt;/search-gt&gt; </p> </td> 
   <td colname="col2"> <p>Insère la sortie de l'une des balises de modèle de recherche dans d'autres balises HTML ou modèles sur la page des résultats. <span class="codeph">&lt;search-gt&gt;insère un caractère supérieur à celui. </span> &lt;/search-gt&gt; L'utilisation <span class="codeph"> &lt;search-lt&gt; </span> et <span class="codeph"> &lt;search-gt&gt; </span> fournit un moyen d'échapper à la définition d'une balise afin que vous puissiez utiliser d'autres balises de modèle comme valeurs d'attribut.&lt;/search-gt&gt; &lt;/search-lt&gt; Lorsque le modèle est rendu en réponse à une recherche, un <span class="codeph"> signe supérieur à l'étiquette remplace &lt;search-gt&gt; </span> l'étiquette.&lt;/search-gt&gt; Par exemple, <span class="codeph"> &lt;search-link&gt; </span> est équivalent à .&lt;/search-link&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-param name="param-name" length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span>&lt;/search-param&gt; </p> </td> 
   <td colname="col2"> <p>Renvoie la valeur du paramètre cgi nommé « param-name » de la demande de recherche actuelle. L'attribut « encodage » en option contrôle si la sortie est codée HTML, JavaScript codée, Perl codée, URL codée ou non encodée, pour la sortie sur la page de résultats. La valeur par défaut de "codage" est "html". Normalement, vous n'avez pas besoin de spécifier l'attribut de codage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--><span class="codeph"> &lt;search-trace encoding="html/javascript/ json/perl/url/none"&gt; </span>&lt;/search-trace&gt; </p> </td> 
   <td colname="col2"> 
    <!--<p>This global core search template tag outputs a representation of the submitted core search query, including any "fuzzy-search" query term expansions that happen by way of synonyms, sound-alikes, and so forth. </p>--> <p><span class="codeph"> L'attribut </span> d'encodage est facultatif; la valeur <span class="codeph"> par </span>défaut est json . </p> <p> <p>Remarque : cette balise <span class="codeph"> n'a de </span> sortie que si le sp-trace 1 est spécifié avec les paramètres de requête de recherche de base. </p> </p> <p>Voir la rangée 48 dans le tableau trouvé dans . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Étiquettes de lien d'ancrage de modèle{#section_3A51D27616C541E2B818CC52B2B856BA}

Ce qui suit sont des balises qui provoquent un lien d'ancrage pour entourer le HTML entre eux. Lorsqu'il est cliqué, le lien d'ancrage demande une autre page de résultats à afficher. L'attribut optionnel "compte" demande que de nombreux résultats sur la page à afficher. S'il n'est pas spécifié, le décompte demandé sur la page actuelle est utilisé. L'attribut « URL » avancé et optionnel contrôle le domaine vers lequel le lien associé est dirigé. Par défaut, le domaine est http://search.atomz.com/search/, mais vous pouvez le modifier à l'aide de l'attribut URL.

<table id="table_F940A41509A2488DAB04ACC144A3FB8A"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-next url="http://search.yourdomain.com/search/"&gt; ... &lt;/search-next&gt;</span> </p> <p> <span class="codeph">&lt;search-prev url="http://search.yourdomain.com/search/"&gt; ... &lt;/search-prev&gt;</span> </p> </td> 
   <td colname="col2"> <p>Affiche la page suivante ou précédente des résultats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-sort-by-date url="http://search.yourdomain.com/search/"&gt; ... &lt;/search-sort-by-date&gt;</span> </p> <p> <span class="codeph">&lt;search-sort-by-score url="http://search.yourdomain.com/search/"&gt; ... &lt;/search-sort-by-score&gt;</span> </p> </td> 
   <td colname="col2"> <p>Trie les résultats par date ou par pertinence. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-show-summaries url="http://search.yourdomain.com/search/"&gt; ... &lt;/search-show-summaries&gt;</span> </p> <p> <span class="codeph">&lt;search-hide-summaries url="http://search.yourdomain.com/search/"&gt; ... &lt;/search-hide-summaries&gt;</span> </p> </td> 
   <td colname="col2"> <p>Montre ou cache les résumés. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Étiquettes conditionnelles de modèle{#section_18D9BC66DE484881932FD2F7EA9D170D}

Tags qui vous laissent inclure conditionnellement HTML entre eux.

<table id="table_A1842D42AB8F4F5688AC57C44F817042"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-results&gt; ... &lt;/search-if-results&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-results&gt; ...&lt;/search-if-not-results&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent HTML si la page actuelle contient des résultats de recherche (ou pas). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-prev-count&gt; ... &lt;/search-if-prev-count&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-prev-count&gt; ... &lt;/search-if-not-prev-count&gt;</span> </p> <p> <span class="codeph">&lt;search-if-next-count&gt; ... &lt;/search-if-next-count&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-next-count&gt; ... &lt;/search-if-not-next-count&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent HTML si la page précédente ou la page suivante a des résultats (ou aucun) qui lui sont associés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-sort-by-score&gt; ... &lt;/search-if-sort-by-score&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-sort-by-score&gt; ... &lt;/search-if-not-sort-by-score&gt;</span> </p> <p> <span class="codeph">&lt;search-if-sort-by-date&gt; ... &lt;/search-if-sort-by-date&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-sort-by-date&gt; ... &lt;/search-if-not-sort-by-date&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent HTML si la page actuelle est, ou n'est pas, triée par pertinence ou par date. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-show-summaries&gt; ... &lt;/search-if-show-summaries&gt;</span> </p> <p> <span class="codeph">&lt;search-if-hide-summaries&gt; ... &lt;/search-if-hide-summaries&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent HTML si la page actuelle affiche ou cache des résumés. Vous pouvez utiliser ces balises pour inclure ou exclure une partie du résultat de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-input-collections&gt; ... &lt;/search-if-input-collections&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-input-collections&gt; ... &lt;/search-if-not-input-collections&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent HTML si une collection a été spécifiée dans la génération de résultats de recherche pour la page actuelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-advanced&gt; ... &lt;/search-if-advanced&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-advanced&gt; ... &lt;/search-if-not-advanced&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent <span class="codeph"> HTML si le </span> paramètre CGI sp-advanced1 a été spécifié pour la requête de recherche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-bad-param name="parameter-name"&gt; ... &lt;/search-if-bad-param&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-bad-param name="parameter-name"&gt; ... &lt;/search-if-not-bad-param&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises incluent ou excluent le HTML entre eux si le paramètre donné est, ou n'est pas, invalide. </p> <p>À l'heure actuelle, seul le <span class="codeph"> </span> paramètre sp-q-localisation est pris en charge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-param name="param-name" value="param-value"&gt; ... &lt;/search-if-param&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-param name="param-name" value="param-value"&gt; ... &lt;/search-if-not-param&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises avancées incluent le HTML entre eux en fonction de la question de savoir si le paramètre CGI spécifié dans l'attribut « nom » a la valeur spécifiée dans l'attribut « valeur ». </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-if-sort-by-field name="field-name"&gt; ... &lt;/search-if-sort-by-field&gt;</span> </p> <p> <span class="codeph">&lt;search-if-not-sort-by-field name="field-name"&gt; ... &lt;/search-if-not-sort-by-field&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises avancées incluent le HTML entre eux si la page actuelle est, ou n'est pas, triée par le nom de champ donné. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Étiquettes de contrôle de formulaire de modèle{#section_45AFC414ACA74825B72FEAA8456F8DD2}

Les balises qui vous laissent contrôler l'état de sélection par `<form>` défaut pour les cases à cocher, les boutons radio et les cases de liste dans un modèle de recherche.

<table id="table_F77D41DADC064DC48AB06A24A00DB472"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>étiquette </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>1 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-input&gt; </span>&lt;/search-input&gt; </p> </td> 
   <td colname="col2"> <p>Utilisé dans un modèle <span class="codeph"> à la place d'un&lt;input&gt;</span> tag. Lorsque l'étiquette est écrite sur <span class="codeph"> </span> le <span class="codeph"> navigateur, </span> l'entrée de mot remplace l'entrée de recherche et toutes les autres informations de l'étiquette sont sorties en l'actualité. En outre, <span class="codeph"> si </span> le nom spécifié dans l'étiquette <span class="codeph"> est </span> répertorié comme un paramètre CGI et <span class="codeph"> si </span> la valeur spécifiée dans l'étiquette est la valeur de ce paramètre CGI, alors le mot coché est ajouté à la fin de l'étiquette. De cette façon, vous pouvez automatiquement faire le bouton radio par défaut ou l'état de la case à cocher dans votre résultat de recherche le même que la requête actuelle. </p> <p>Par exemple, le code HTML d'une case à cocher peut ressembler à ce qui suit : </p> <p> <span class="codeph">&lt;input type="checkbox" name="sp_w" value="exact"&gt;Pas d'appariement sonore</span> </p> <p>Le code de modèle correspondant pour cette case à cocher est le suivant : </p> <p> <span class="codeph">&lt;search-input type="checkbox" name="sp_w" value="exact"&gt;Pas d'appariement </span> sonore&lt;/search-input&gt; </p> <p>Si la chaîne de paramètres <span class="codeph"> CGI pour la </span>requête contient sp-w-exact , puis l'étiquette <span class="codeph"> écrite </span> au navigateur avec les résultats de recherche ressemble à ce qui suit (le mot coché est inséré à la fin de l'étiquette): </p> <p> <span class="codeph">&lt;input type="checkbox" name="sp_w" value="exact" checked=""&gt;Pas d'appariement sonore</span> </p> <p>Si la chaîne de paramètres CGI <span class="codeph"> pour la requête </span>ne contient pas sp-w-exact , puis l'étiquette écrite au navigateur avec les résultats de recherche ressemble à ce qui suit (le mot <span class="codeph"> coché </span> n'est pas répertorié dans l'étiquette): </p> <p> <span class="codeph">&lt;input type="checkbox" name="sp_w" value="exact"&gt;Pas d'appariement sonore</span> </p> <p><span class="codeph"> &lt;search-input&gt; </span> L'étiquette est utile pour mettre des cases à cocher et&lt;/search-input&gt; des boutons radio dans votre modèle de recherche. Si vous avez des cases à cocher ou <span class="codeph"> des boutons radio que vous souhaitez ajouter à la&lt;form&gt;</span> dans votre modèle <span class="codeph"> de recherche, utilisez &lt;search-input...&gt; </span> à la place de <span class="codeph"> &lt;input...&gt; </span>.&lt;/input...&gt; &lt;/search-input...&gt;&lt;/form&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-select&gt; ... &lt;/search-select&gt;</span> </p> <p> <span class="codeph">&lt;search-option&gt; ... &lt;/search-option&gt;</span> </p> </td> 
   <td colname="col2"> <p>Boîtes de liste déroulantes dans un <span class="codeph">&lt;form&gt;</span> tag sont commencés avec un <span class="codeph">&lt;select&gt;</span> tag et s'est terminée par un <span class="codeph">&lt;/select&gt;</span> tag.&lt;/form&gt; Le <span class="codeph"> </span> nom du paramètre CGI <span class="codeph"> associé est indiqué à l'intérieur de la&lt;select&gt;</span> tag.&lt;/select&gt; À <span class="codeph"> la suite de la&lt;select&gt;</span> tag est une <span class="codeph"> liste de&lt;option&gt;</span> les balises qui spécifient les valeurs à afficher à l'intérieur de la case liste.&lt;/select&gt; </p> <p>Le <span class="codeph"> </span> <span class="codeph"> </span> <span class="codeph"> &lt;search-select&gt;, <span class="codeph"> , , et les balises fournissent des fonctionnalités similaires à </span>&lt;/search-select&gt; &lt;search-input&gt; </span> l'étiquette.&lt;/search-input&gt; &lt;search-option&gt; </span> <span class="codeph"> &lt;/search-option&gt; C'est-à-dire que le mot <span class="codeph"> sélectionné </span> est automatiquement ajouté à la fin de la <span class="codeph">&lt;option&gt;</span> l'étiquette envoyée au <span class="codeph"> </span> navigateur <span class="codeph"> si le nom de l'étiquette &lt;search-select&gt; </span> est répertorié comme un paramètre CGI et si la <span class="codeph"> valeur </span> de ce paramètre CGI est répertoriée comme <span class="codeph"> valeur </span> dans un <span class="codeph"> &lt;search-option&gt; </span> tag.&lt;/search-option&gt; &lt;/search-select&gt; De cette façon, vous pouvez automatiquement faire le choix de la boîte de liste par défaut dans votre résultat de recherche le même que la requête en cours. </span></span></p> <p>Par exemple, une boîte de liste typique ressemble à la suivante : </p> <p> 
     <codeblock class="syntax html">
       &lt;select name="sp_x" size=1&gt; 
      &lt;option value="any" selected&gt;N'importe où&lt;option value="title"&gt;Titre&lt;option value="desc"&gt;Description&lt;option value="keys"&gt;Mots-clés&lt;option value="body"&gt;Corps Texte alternatif CIBLE&lt;option value="alt"&gt;&lt;option value="url"&gt;URL&lt;option value="target"&gt; 
      &lt;/option value="target"&gt;  
      &lt;/option value="url"&gt;  
      &lt;/option value="alt"&gt;  
      &lt;/option value="body"&gt;  
      &lt;/option value="keys"&gt;  
      &lt;/option value="desc"&gt;  
      &lt;/option value="title"&gt; 
      &lt;/option value="any" selected&gt;&lt;/select name="sp_x" size=1&gt; 
     </codeblock> </p> <p>Le code de modèle correspondant pour cette case de liste est le suivant : </p> <p> 
     <codeblock class="syntax html">
       &lt;search-select name="sp_x" size=1&gt; 
      &lt;search-option value="any"&gt;N'importe où&lt;search-option value="title"&gt;Titre&lt;search-option value="desc"&gt;Description&lt;search-option value="keys"&gt;Mots-clés&lt;search-option value="body"&gt;Corps Texte alternatif CIBLE&lt;search-option value="alt"&gt;&lt;search-option value="url"&gt;URL&lt;search-option value="target"&gt; 
      &lt;/search-option value="target"&gt;  
      &lt;/search-option value="url"&gt;  
      &lt;/search-option value="alt"&gt;  
      &lt;/search-option value="body"&gt;  
      &lt;/search-option value="keys"&gt;  
      &lt;/search-option value="desc"&gt;  
      &lt;/search-option value="title"&gt; 
      &lt;/search-option value="any"&gt;&lt;/search-select name="sp_x" size=1&gt; 
     </codeblock> </p> <p>Si vous avez des cases de <span class="codeph"> liste que vous souhaitez ajouter à la&lt;form&gt;</span> dans votre modèle <span class="codeph"> de recherche, utiliser &lt;search-select...&gt; </span> à la place de <span class="codeph"> &lt;select...&gt; </span>, <span class="codeph"> </span> à la place de <span class="codeph"> </span>, <span class="codeph"> &lt;search-option...&gt; </span> à la place de <span class="codeph"> &lt;option...&gt; </span>, et <span class="codeph"> </span>à la <span class="codeph"> </span>place de .&lt;/option...&gt; &lt;/search-option...&gt; &lt;/select...&gt; &lt;/search-select...&gt;&lt;/form&gt; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph">&lt;search-sort-by-field name="field-name" count="XX"&gt; ... &lt;/search-sort-by-field&gt;</span> </p> </td> 
   <td colname="col2"> <p>Ces balises avancées créent un lien d'ancrage autour du HTML entre eux. Lorsque cette ancre est cliqué, une page de résultats triés sur le champ donné s'affiche. L'attribut </span> de comptage optionnel <span class="codeph"> spécifie le nombre de résultats à afficher sur la page de résultat. Si <span class="codeph"> </span> le comptage est omis, le nombre utilisé sur la page actuelle est utilisé. </span></p> </td> 
  </tr> 
 </tbody> 
</table>

## Chaînes de format de date{#section_4BBDBBEF2B96414497617CD4B52D96E4}

Vous pouvez utiliser les spécifications de conversion suivantes dans les chaînes de format de date :

<table id="table_00090E2D245D490FAB5DF7E35600D851"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Chaîne de format de date </p> </th> 
   <th colname="col2" class="entry"> <p>description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p> Correspond à la représentation nationale du nom complet en semaine, par exemple, "lundi". Le paramètre </span> <span class="uicontrol"> linguistique <span class="uicontrol"> , <span class="uicontrol"> mots </span> et langues </span> , détermine la représentation nationale. </span></p> <p>voir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> Correspond à la représentation nationale du nom abrégé en semaine, où l'abréviation est les trois premiers caractères, par exemple "Mon". Le paramètre </span> <span class="uicontrol"> linguistique <span class="uicontrol"> , <span class="uicontrol"> mots </span> et langues </span> , détermine la représentation nationale. </span></p> <p>voir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> Correspond à la représentation nationale du nom du mois complet, par exemple "Juin". Le paramètre </span> <span class="uicontrol"> linguistique <span class="uicontrol"> , <span class="uicontrol"> mots </span> et langues </span> , détermine la représentation nationale. </span></p> <p>voir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> Correspond à la représentation nationale du nom abrégé du mois, où l'abréviation est les trois premiers caractères, par exemple "Jun". Le paramètre </span> <span class="uicontrol"> linguistique <span class="uicontrol"> , <span class="uicontrol"> mots </span> et langues </span> , détermine la représentation nationale. </span></p> <p>voir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p>Équivalent à "%m/%d/%y", par exemple "07/25/13". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> Correspond au jour du mois comme un nombre décimal (01-31). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e %e </p> </td> 
   <td colname="col2"> <p> Correspond au jour du mois comme un nombre décimal (1-31). Un blanc précède les chiffres simples. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H (en) </p> </td> 
   <td colname="col2"> <p> Correspond à l'horloge de 24 heures comme un nombre décimal (00-23). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h (en %) </p> </td> 
   <td colname="col2"> <p> Correspond à la représentation nationale du nom abrégé du mois, où l'abréviation est les trois premiers caractères, par exemple "Jun" (le même que %b). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> Correspond à l'horloge de 12 heures comme un nombre décimal (01-12). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j (en) </p> </td> 
   <td colname="col2"> <p> Correspond au jour de l'année comme un nombre décimal (001-366). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k (en) </p> </td> 
   <td colname="col2"> <p> Correspond à l'horloge de 24 heures comme un nombre décimal (0-23). Un blanc précède les chiffres simples. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> Correspond à l'horloge de 12 heures comme un nombre décimal (1-12). Un blanc précède les chiffres simples. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> Correspond à la minute comme un nombre décimal (00-59). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> Correspond au mois comme un nombre décimal (01-12). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p (en) </p> </td> 
   <td colname="col2"> <p> Correspond à la représentation nationale de «ante meridiem» ou «post meridiem» le cas échéant, par exemple «PM». Le paramètre </span> <span class="uicontrol"> linguistique <span class="uicontrol"> , <span class="uicontrol"> mots </span> et langues </span> , détermine la représentation nationale. </span></p> <p>voir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R (en) </p> </td> 
   <td colname="col2"> <p>Équivalent à "%H:%M", par exemple, "13:23". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r (en) </p> </td> 
   <td colname="col2"> <p>Équivalent à "%I:%M:%S %p", par exemple, "01:23:45 PM". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%S (%S) </p> </td> 
   <td colname="col2"> <p> Correspond à la seconde comme un nombre décimal (00-60). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p>Équivalent à "%H:%%M:%S", par exemple, "13:26:47". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> Correspond au numéro de la semaine de l'année (dimanche comme premier jour de la semaine) comme un nombre décimal (00-53). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v (en) </p> </td> 
   <td colname="col2"> <p>Équivalent à "%e-%b-%Y", par exemple, "25-Jul-2013". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> Correspond à l'année avec siècle comme un nombre décimal, par exemple, "2013". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> Correspond à l'année sans siècle comme un nombre décimal (00-99). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z (en) </p> </td> 
   <td colname="col2"> <p> Correspond au nom du fuseau horaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> Correspond à "%". </p> </td> 
  </tr> 
 </tbody> 
</table>

## Identificateurs linguistiques{#section_0490DECC00E34691ADE5A9ED90A6D911}

Le tableau suivant contient les identifiants linguistiques de chaque langue prise en charge. Vous pouvez utiliser ces identifiants comme valeurs pour l'attribut « langue » optionnel dans les balises de modèle suivantes :

<table id="table_5960FA4A816C47ECA8D8F1F937558FB5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>langage </p> </th> 
   <th colname="col2" class="entry"> <p>Identificateur linguistique </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Bulgare (Bulgarie) </p> </td> 
   <td colname="col2"> <p> bg-BG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinois (Chine) </p> </td> 
   <td colname="col2"> <p> zh-CN (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinois (Hong Kong) </p> </td> 
   <td colname="col2"> <p> zh-HK (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinois (Singapour) </p> </td> 
   <td colname="col2"> <p>zh-SG (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chinois (Taïwan) </p> </td> 
   <td colname="col2"> <p> zh-TW (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tchèque (République tchèque) </p> </td> 
   <td colname="col2"> <p> cs-CZ (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Danois (Danemark) </p> </td> 
   <td colname="col2"> <p> da-DK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Néerlandais (Belgique) </p> </td> 
   <td colname="col2"> <p> nl-BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Néerlandais (Pays-Bas) </p> </td> 
   <td colname="col2"> <p> nl-NL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anglais (Australie) </p> </td> 
   <td colname="col2"> <p> fr </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anglais (Canada) </p> </td> 
   <td colname="col2"> <p> en-CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anglais (Grande-Bretagne) </p> </td> 
   <td colname="col2"> <p> en GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anglais (États-Unis) </p> </td> 
   <td colname="col2"> <p> En_us </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Français (Belgique) </p> </td> 
   <td colname="col2"> <p> fr-BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Français (Canada) </p> </td> 
   <td colname="col2"> <p>fr-CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Finlandais (Finlande) </p> </td> 
   <td colname="col2"> <p> fi-FI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Français (France) </p> </td> 
   <td colname="col2"> <p> fr-FR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Français (Suisse) </p> </td> 
   <td colname="col2"> <p> fr-CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allemand (Autriche) </p> </td> 
   <td colname="col2"> <p> de-AT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allemand (Allemagne) </p> </td> 
   <td colname="col2"> <p> de-DE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allemand (Suisse) </p> </td> 
   <td colname="col2"> <p> deCH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grec (Grèce) </p> </td> 
   <td colname="col2"> <p> el-GR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gaélique irlandais (Irlande) </p> </td> 
   <td colname="col2"> <p> ga-IE (en anglais) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Italien (Italie) </p> </td> 
   <td colname="col2"> <p> it-IT (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Japonais (Japon) </p> </td> 
   <td colname="col2"> <p> ja-JP (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Coréen (Corée) </p> </td> 
   <td colname="col2"> <p> ko-KR (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Norvégien (Norvège) </p> </td> 
   <td colname="col2"> <p> non-NO </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Polonais (Pologne) </p> </td> 
   <td colname="col2"> <p> pl-PL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Portugais (Brésil) </p> </td> 
   <td colname="col2"> <p> Pt_br </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Portugais (Portugal) </p> </td> 
   <td colname="col2"> <p> pt-PT (pt-PT) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Russe (ancienne Union soviétique) </p> </td> 
   <td colname="col2"> <p> ru-SU (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slovaque (Slovaquie) </p> </td> 
   <td colname="col2"> <p> sk-SK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slovaque (Slovénie) </p> </td> 
   <td colname="col2"> <p>sl-SI (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Espagnol (Mexique) </p> </td> 
   <td colname="col2"> <p> es-MX (en anglais seulement) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Espagnol (Espagne) </p> </td> 
   <td colname="col2"> <p> es-ES </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Suédois (Suède) </p> </td> 
   <td colname="col2"> <p> sv-SE (en anglais seulement) </p> </td> 
  </tr> 
 </tbody> 
</table>

## Spécifier l'en-tête HTTP de type contenu{#section_AEED823E9938448A9EDB2F286D9CFD90}

Vous pouvez spécifier l'en-tête de réponse HTTP De Type de Contenu en utilisant l'étiquette suivante :

`<search-content-type-header [content="MIME-type"] [charset="charset-name"]>`

Les `content` `charset` attributs et les attributs sont facultatifs. Cette balise doit apparaître le plus tôt possible dans le modèle. Il est également recommandé qu'il apparaissent avant ou `<search-html-meta-charset>` `<search-xml-decl>`, parce qu'il affecte le comportement de ces balises.

If you do not specify the `content` attribute, then the value of `MIME-type` defaults to the value that is set in **[!UICONTROL Settings]** &gt; **[!UICONTROL Crawling]** &gt; **[!UICONTROL Content Types]**. Si vous `content` spécifiez un attribut, `content` il `<search-html-meta-charset>` est utilisé comme attribut par défaut pour l'étiquette.

Si vous ne `charset` spécifiez `charset` pas l'attribut, aucune valeur n'est écrite à l'en-tête. `content-type`

Si vous `charset="1"` spécifiez `charset-name` alors la valeur `sp_f` réelle pour est la valeur du paramètre CGI. Si `sp_f` aucun paramètre CGI n'est soumis `charset-name` avec la recherche, la valeur réelle est lue à partir des paramètres de votre compte. You can view or change the character set that is associated with your account under **[!UICONTROL Settings]** &gt; **[!UICONTROL My Profile]** &gt; **[!UICONTROL Personal Information]** &gt; **[!UICONTROL Character Encoding]**.

Vous pouvez choisir un nom de définir `charset` un caractère `charset="iso-8859-1"` `charset="Shift-JIS"`spécifique en l'énumérant comme valeur, comme ou .

Si vous `charset` spécifiez un attribut, `charset` il est `<search-html-meta-charset>` `<search-xml-decl>` utilisé comme attribut par défaut `content-type` pour les balises et, en plus d'être la sortie de l'en-tête.

## Spécifier un ensemble de caractères dans un modèle HTML{#section_E0D1816ABB5846BEBE9C26D5980CCBE6}

Les modèles de résultats de recherche HTML par défaut spécifient l'ensemble de caractères associé au compte courant via la balise suivante :

`<search-html-meta-charset [content="MIME-type"] [charset="charset-name"]>`

Le contenu et les attributs de charssont sont facultatifs. Cette balise doit `<head>` apparaître dans la section HTML du modèle. Cette balise donne les résultats de la balise suivante sur la page HTML générée à partir du modèle :

`<meta http-equiv="content-type" content="MIME-type; charset=charset-name">`

Si vous ne spécifiez pas l'attribut de contenu, la valeur réelle des `MIME-type` défauts est de l'une des deux valeurs. Si `<search-content-type-header>` l'étiquette `content` spécifié un attribut, alors cette valeur est utilisée. Dans le cas contraire, la valeur **[!UICONTROL utilisée]** **[!UICONTROL est]** **[!UICONTROL celle]** qui se trouve dans l'onglet Templates 'Paramètres ' Type de contenu.

Si vous ne `charset` spécifiez pas l'attribut, la valeur réelle des défauts est `charset-name` de l'une des deux valeurs. Si `<search-content-type-header>` l'étiquette `charset` spécifié un attribut, alors cette valeur est utilisée. Dans le cas `charset-name` contraire, la valeur réelle est lue à partir des paramètres de votre compte. You can view or change the character set that is associated with your account under **[!UICONTROL Settings]** &gt; **[!UICONTROL My Profile]** &gt; **[!UICONTROL Personal Information]** &gt; **[!UICONTROL Character Encoding]**.

Si vous `charset="1"` spécifiez `charset-name` alors la valeur `sp_f` réelle pour est la valeur du paramètre CGI. Si `sp_f` aucun paramètre CGI n'est soumis `charset-name` avec la recherche, `<search-content-type-header>` la valeur réelle est soit la valeur fixée dans l'étiquette si elle a été spécifiée, soit la valeur qui est fixée dans les paramètres de votre compte.

Vous pouvez spécifier un nom de `charset="charset-name"`définir de caractère spécifique, comme dans . Par `charset="iso-8859-1"` exemple, `charset="Shift-JIS"`ou .

L'étiquette `<search-html-meta-charset>` est facultative. Si vous le supprimez, le navigateur `content-type`assume les valeurs `content="text/html; charset=ISO-8859-1"`par défaut pour , qui est le suivant: . Vous pouvez également choisir `<search-html-meta-charset>` de remplacer `http-equiv` l'étiquette par votre propre balise.

## Spécifier un personnage dans un modèle XML{#section_17DC31CDCC104F5F8081466B41A96E9D}

Le modèle de résultat de recherche par défaut XML spécifie l'ensemble de caractères associé au compte courant au moyen de la balise suivante :

`<search-xml-decl [charset="charset-name"]>`

L'attribut `charset` est facultatif. Cette balise doit apparaître en haut du `<search-content-type-header>` modèle, mais après n'importe quelle balise. Cette balise donne les résultats de l'étiquette suivante sur le document XML qui est généré à partir du modèle :

`<?xml version="1.0" encoding="charset-name" standalone="yes" ?>`

Si vous ne `charset`spécifiez pas `charset-name` le , puis la valeur réelle des défauts à l'une des deux valeurs. Si `<search-content-type-header>` un `charset` attribut spécifié est spécifié, cette valeur est utilisée. Dans le cas `charset-name` contraire, la valeur réelle est lue à partir des paramètres de votre compte. You can view or change the character set that is associated with your account under **[!UICONTROL Settings]** &gt; **[!UICONTROL My Profile]** &gt; **[!UICONTROL Personal Information]** &gt; **[!UICONTROL Character Encoding]**.

Si vous `charset="1"` spécifiez `charset-name` alors la valeur `sp_f` réelle pour est la valeur du paramètre CGI. Si `sp_f` aucun paramètre CGI n'est soumis `charset-name` avec la recherche, la `<search-content-type-header>` valeur réelle est soit la valeur qui est défini dans l'étiquette si elle a été spécifiée, soit la valeur qui est défini dans les paramètres de votre compte.

Vous pouvez spécifier un nom de `charset="charset-name"`définir de caractère spécifique, comme dans , si vous le désirez. Par exemple, `charset="iso-8859-1" or charset="Shift-JIS"`.

Vous pouvez choisir `<search-xml-decl>` de remplacer `?xml` l'étiquette par votre propre balise.

## Inclure un modèle de recherche dans un autre{#section_7D1FCD3D9E2340C291E354C9720E8BC0}

Pour inclure un modèle de `<search-include>` recherche dans un autre, utilisez la balise, en définissant l'attribut de fichier au nom du fichier de modèle que vous souhaitez inclure comme dans l'exemple suivant :

`<search-include file="seo/seo_search_title.tpl" />`

Les segments de modèle `seo/` de recherche DE SEO sont `templates/` dans le sous-folder et les modèles de recherche normaux sont dans le sous-folder. Seuls les fichiers .tpl sont significatifs à inclure dans ce contexte.

## Gestion de plusieurs modèles de transport pour votre site Web{#reference_12AAB3B9F4C74C11956F1DBA95714C2F}

Vous pouvez contrôler l'apparence des résultats de recherche sur votre site Web en utilisant différents modèles de transport de recherche pour chaque zone.

<!-- 

r_managing_multiple_templates.xml

 -->

Pour réaliser ce type de fonctionnalité de recherche, vous pouvez gérer vos modèles de transport dans la recherche/merchandising du site. Ou, vous pouvez gérer vos modèles de transport dans Publish. Comme la recherche/merchandising de site, Publish vous permet d'éditer, de prévisualiser et de publier plusieurs modèles de transport de recherche.

Pour configurer vos formulaires de recherche pour utiliser un modèle `sp_t` de transport spécifique (autre que par défaut), utilisez le paramètre de requête. Supposons, par exemple, que vous ayez un modèle de recherche appelé « dédouanement » pour la zone de vente marquée de votre site Web. Vous utilisez le formulaire de recherche HTML standard avec le code de formulaire supplémentaire suivant :

`<input type=hidden name="sp_t" value="clearance">`

Lorsqu'un client clique sur un formulaire standard qui contient cette ligne de code, le modèle de transport de recherche « dédouanement » s'affiche avec ses résultats de recherche.
