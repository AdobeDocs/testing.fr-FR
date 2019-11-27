---
description: en savoir plus sur les nouvelles fonctionnalités et corrections dans le cloud marketing adobe.
keywords: release notes
seo-description: en savoir plus sur les nouvelles fonctionnalités et corrections dans le cloud marketing adobe.
seo-title: notes de sortie - mai 2015
title: notes de sortie - mai 2015
internal: n
snippet: y
translate: y
matt: lawrence
translation-type: tm+mt
source-git-commit: c850cfab909bb749de17d5e953fe5d6c9c2a7380

---

# [!DNL Table Tests]

## AsideBlock (en)

```
| one 

| two |

|--|--|
| a | b |
```

## Largeurs de table HTML

<table>
  <col style="width:10%">
  <col style="width:70%">
  <col style="width:20%">
  <thead>
  <tr>
    <th>Fruits</th>
    <th>Vitamine A</th>
        <th>Vitamine C</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <th>Pommes</th>
        <td>98 ui (en)</td>
        <td>8,4 mg</td>
    </tr>
    <tr>
        <th>Oranges</th>
        <td>295 ui</td>
        <td>69,7 mg</td>
    </tr>
    <tr>
        <th>Bananes</th>
        <td>76 ui</td>
        <td>10,3 mg</td>
    </tr>
    </tbody>
</table>

## Code de gestionnaire d'expérience dans les tableaux

>[!CONTEXTUALHELP]
>id '"aemtables"
>titre "AEM Tables"
>abstractMD "Comment l'équipe AEM utilise les tables"
>extra_url"http://extra.url" text "Plus d'infos"

<table> 
 <tbody>
  <tr>
   <td><strong>Emplacement précédent</strong></td> 
   <td><codeblock>/etc/workflow/modèles</codeblock></td> 
  </tr>
  <tr>
   <td><strong>Nouvel emplacement (s)</strong></td> 
   <td><p><pre>PRÉ</pre></p><p><code>CODE</code></p><p><span class="code">/libs/settings/workflow/models</span></p> <p><span class="code">/conf/global/settings/workflow/models</span></p> <p><span class="code">/var/workflow/modèles</span></p> </td> 
  </tr>
  <tr>
   <td><strong>Orientation de restructuration</strong></td> 
   <td><p>Tout modèle de flux de travail nouveau ou modifié doit être migré vers /conf/global/workflow/models.</p> 
    <codeblock>
        C'est pré texte doit être monospace
        </codeblock>
    <ol> 
     <li>Déployez les modèles de flux de travail modifiés dans une instance de développement AEM 6.4 locale, de sorte qu'ils existent dans l'emplacement précédent.</li> 
     <li>Modifier le modèle de flux de travail à l'aide de l'éditeur de modèles de flux de travail d'AEM chez AEM , Outils et modèles de workflow.</li> 
     <li>Lors de la migration des modèles de flux de travail modifiés fournis par AEM
      <ol> 
       <li>Avec l'éditeur de modèle de flux de travail ouvert, modifiez l'URL d'adresse du navigateur et remplacez le segment de chemin /libs/settings/workflow/models par /etc/workflow/models.
        <ul> 
         <li>Par exemple, <em>modifier<strong>: http://localhost:4502/editor.html /libs/settings/workflow/models</strong></em> /dam/update_asset.html to <em>http://localhost:4502/editor.html<strong>/etc/workflow/models</strong>/dam/update_asset.html</em></li> 
        </ul> </li> 
      </ol> </li> 
     <li>Activer le mode Modifier dans l'éditeur de modèle de flux de travail qui copiera la définition du modèle de flux de travail à /conf/global/workflow/models.</li> 
     <li>Appuyez sur le bouton Sync pour synchroniser les modifications apportées au modèle de flux de travail runtime sous /var/workflow/models.</li> 
     <li>Exporter à la fois le modèle de flux de travail (/conf/global/workflow/models/&lt;workflow-model&gt;) et runtime Workflow Model (/var/workflow/models/&lt;workflow-model&gt;) et s'intégrer dans le projet AEM.&lt;/workflow-model&gt; &lt;/workflow-model&gt;
      <ol> 
       <li>Par exemple, exporter :
        <ul> 
         <li><span class="code">/config/settings/workflow/models/dam/my_workflow_model</span> <br /> and </li> 
         <li><span class="code">/var/workflow/models/dam/my_workflow_model</span></li> 
        </ul> </li> 
      </ol> </li> 
    </ol> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td><p>La résolution du modèle de flux de travail se produit dans l'ordre suivant :</p> 
    <ol> 
     <li><span class="code">/conf/global/settings/workflow/models</span></li> 
     <li><span class="code">/libs/settings/workflow/models</span></li> 
     <li><span class="code">/etc/workflow/modèles</span></li> 
    </ol> <p>Ainsi, toute personnalisation des modèles de flux de travail fournis par AEM persiste dans l'emplacement précédent doit être déplacée vers /conf/global/settings/workflow/models s'ils doivent être conservés, sinon ils seront remplacés par la définition du modèle de flux de travail fournie par aEM dans /libs/settings/workflow/models.</p> </td> 
  </tr>
 </tbody>
</table>


## Connectez-vous et gérez les paramètres de votre profil

>[!NOTE]
>
>Vous devez coder n'importe quelle `destURL` URL avant de la transmettre au paramètre. (Des sites d'encodeur comme [LE](https://meyerweb.com/eric/tools/dencoder/) décodeur url / Encoder sont disponibles.)


## Tableau des services de base avec URL et une cellule longue

| Paramètre | Description | Exemple | Obligatoire / Facultatif |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|------------------------------------|
| locataireId | Nom du locataire dans qui l'utilisateur doit se connecter. | aem62tenant | Optionnel |
| destURL | L'URL complète à l'endroit où l'utilisateur doit être pris. | https://sc.omniture.com/x/1_7xxzf | Optionnel |
| nom de solution | Nom de la solution MAC qui est le propriétaire du paramètre destURL. Il est utilisé pour vérifier que l'utilisateur a accès à la solution qui est le propriétaire de l'URL.  Il est de la responsabilité des solutions de s'assurer que le nom de la solution est en synchronisation avec le paramètre destURL.  Par exemple : Si l'URL contient le nom de solution comme social et que le destURL fourni est une URL analytique, alors l'utilisateur serait redirigé vers l'URL même s'il n'a pas accès à l'analyse. MAC ne vérifie PAS la météo le propriétaire de la destURL est en phase avec le nom de la solution. | Analytique | Nécessaire si destURL param est utilisé. |


## Grande table avec beaucoup de cols

| Nom du produit et lien d'aide | Espace de travail d'analyse | Rapports et analyses | Analyse Ad Hoc | Constructeur de rapports | Entrepôt de données | Établi de données |
|------------------------|------------------|-------------------|---------------|--------------|--------------|--------------|
| Méthode d'accès | Solution de navigateur pour la construction de projets robustes et d'analyse personnalisé s'il démocratise les idées. | Solution de navigateur pour l'analyse numérique. | Outil basé sur Java pour l'analyse numérique avancée. | L'add-in Excel vous permet de créer des demandes personnalisées à partir de données de Recherche et D.A. et de visualiser à l'aide de Microsoft Excel. | Solution de navigateur qui génère des rapports en format .csv. Peut générer des fichiers de format Tableau. | Outil d'analyse multicanal pour l'analyse avancée, comme la modélisation d'attribution personnalisée, l'analyse prédictive et l'analyse client 360. |
| Répartition des rapports | Illimité | Jusqu'à 2 corrélations | Illimité | Jusqu'à 2 corrélations | Effectue des ventilations illimitées et entièrement étendues, ventilées par segment. | Illimité |
| Comparaisons sectorielles | Illimité | Jusqu'à 2 segments | Illimité | Illimité (empilement de demande de données) | 1 segment. Prend en charge plusieurs segments (empilés). | Illimité |
| Limite de sortie de ligne | 400 | 200 | 50,000 | 50,000 | Illimité | Personnalisable |
| Limites de valeur uniques (dans les rapports eVar/prop) | 500K-2MM | 500K-2MM | 500K-2MM | 500K-2MM | Illimité | Personnalisable |
| Entonnoir/Pathing | Oui Fallout Flow | Oui | Oui | Oui | non | Oui |
| Analyse avancée du parcours client | Prévu | non | Oui | non | non | Oui |
| Analyse de cohorte | Oui | non | non | non | non | Oui |
| Attribution avancée | Limité actuellement - premier/dernier/linéaire | Limité - premier/dernier/linéaire | Limité - premier/dernier/linéaire | Limité - premier/dernier/linéaire | Limité - premier/dernier/linéaire | Oui |
Découvrez les nouvelles fonctionnalités et corrections dans le Cloud Marketing Adobe.

>[!NOTE]
>
>Pour recevoir des notes de sortie une semaine[avant la](https://www.adobe.com/subscription/priority-product-update.html)mise à jour mensuelle du produit, abonnez-vous à la mise à jour adobe Priority Product . Les informations de publication dans la mise à jour du produit prioritaire sont disponibles une semaine avant la date de sortie et peuvent être modifiées. S'il vous plaît vérifier à l'heure de sortie pour les mises à jour.

<!-- <p>This file is the template for the monthly RNs. To update all links, open this file in notepad++, search for <span class="filepath"> 05212015 </span> and replace all occurrences with the current file name (usually release date). When adding content, edit only the tables and Fixes ULs. Do not overwrite Concepts, Sections, or the topic maps ULs. </p> -->
Mai 2015

## Tableau Markdown avec de petits cols

| Bonjour | Il |
|---|---|
| Un | B |


## Tableau Markdown avec listes et pauses intégrées

| Fonction | Description |
| --- | --- |
| Quelque chose va ici ... | Les menus de navigation de gauche ont été mis à jour et disposés pour donner accès à tous les services et solutions de base.  Parmi les changements notables, mentionnons : <ol> <li>Les sélections de menus de la Bibliothèque d'audience et des attributs des clients sont maintenant situées sous Audiences . </li> <li>La sélection du menu Exchange a été déplacée du menu Help down au rail de navigation gauche. </li><li> Les solutions ont été supprimées. Vous pouvez lancer toutes les solutions à partir de la moitié inférieure du rail de navigation. </li></ol><br>Voir [À propos](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) des services et solutions de base pour les descriptions des sélections dans le menu de navigation à gauche. |


## Tableau Markdown avec images et trois cols presque identiques à l'équilibrage de test

| Fonction | Description | Description2 | Description 3 |
| --- | --- | --- | --- |
| Quelque chose va ici ... | Les menus de navigation de gauche ont été mis à jour et disposés pour donner accès à tous les services et solutions de base. ![Avertissement](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png) Les changements notables incluent : <ol> <li>Les sélections de menus de la Bibliothèque d'audience et des attributs des clients sont maintenant situées sous Audiences . </li> <li>La sélection du menu Exchange a été déplacée du menu Help down au rail de navigation gauche. </li><li> Les solutions ont été supprimées. Vous pouvez lancer toutes les solutions à partir de la moitié inférieure du rail de navigation. </li></ol><br>Voir [À propos](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) des services et solutions de base pour les descriptions des sélections dans le menu de navigation à gauche. | Les menus de navigation de gauche ont été mis à jour et disposés pour donner accès à tous les services et solutions de base. <br>![Avertissement](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png) <br> Les changements notables incluent : <ol> <li>Les sélections de menus de la Bibliothèque d'audience et des attributs des clients sont maintenant situées sous Audiences . </li> <li>La sélection du menu Exchange a été déplacée du menu Help down au rail de navigation gauche. </li><li> Les solutions ont été supprimées. Vous pouvez lancer toutes les solutions à partir de la moitié inférieure du rail de navigation. </li></ol><br>Voir [À propos](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) des services et solutions de base pour les descriptions des sélections dans le menu de navigation à gauche. | Les menus de navigation de gauche ont été mis à jour et disposés pour donner accès à tous les services et solutions de base. ![Avertissement](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png) Les changements notables incluent : <ol> <li>Les sélections de menus de la Bibliothèque d'audience et des attributs des clients sont maintenant situées sous Audiences . </li> <li>La sélection du menu Exchange a été déplacée du menu Help down au rail de navigation gauche. </li><li> Les solutions ont été supprimées. Vous pouvez lancer toutes les solutions à partir de la moitié inférieure du rail de navigation. </li></ol><br>Voir [À propos](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names) des services et solutions de base pour les descriptions des sélections dans le menu de navigation à gauche. |


## Simple HTML Table

<table>
<tr>
<td>
Bonjour
</td>
<td>
Il
</td>
</tr>
<tr>
<td>
</td>
<td>
Il<br><br>s'agit d'un<br>test
</td>
</tr>
</table>

## Fonction de table HTML/Description

<table id="table_14E7B35E06C84A258A21D09691B58354"> 
 <thead> 
  <tr> 
   <th colname="col1" > Fonction </th> 
   <th colname="col2" > Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Quelque chose va ici ...</p> </td> 
   <td colname="col2"> <p>Les menus de navigation de gauche ont été mis à jour et disposés pour donner accès à tous les services et solutions de base. Parmi les changements notables, mentionnons : </p> 
    <ul id="ul_5BEBAB86B9234A239C4E2DAF8826D8E3"> 
     <li id="li_7FA9F64CE69144B8A8A92746BF40E5A1">Les <span class="term"> sélections <span class="term"> de </span> menus de la Bibliothèque <span class="term"> </span> d'audience et des attributs des clients sont maintenant situées sous Audiences </span>. </li> 
     <li id="li_95D62A43AE6243DBB2A65EDB830D05C4">La <span class="term"> </span> sélection du menu Exchange a été déplacée du menu Help down au rail de navigation gauche. </li> 
     <li id="li_0443FD50C78446CD8AA27A4F272CAD31"> <span class="term">Les </span> solutions ont été supprimées. Vous pouvez lancer toutes les solutions à partir de la moitié inférieure du rail de navigation. </li> 
    </ul> <p>Voir <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=solutions_capability_names" format="https" scope="external"> À propos </a> des services et solutions de base pour les descriptions des sélections dans le menu de navigation à gauche. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

* Correction d'un problème empêchant les attributs des clients de se synchroniser pour certains clients.
* Correction d'un [problème empêchant](https://marketing.adobe.com/resources/help/ja_JP/target/a4t/) Adobe Target Product Documentation page d'afficher en japonais.
* Correction d'un problème empêchant l'utilisation [!DNL  Creative Cloud] du [!DNL  Marketing Cloud]texte japonais dans les commentaires entre le .

Voir [Marketing Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/) Product Documentation pour obtenir de l'aide produit.
