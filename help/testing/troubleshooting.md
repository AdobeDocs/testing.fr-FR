---
git-commit: 4d22987883e7f5ddcabb054c15d4aeaf2086a5f9
last-update: '2019-04-23'
pipeline_filename: help/testing/troubleshooting.md
publish-url: https://docs.adobe.com/content/help/en/./testing/hello/second-group-c/troubleshooting.html
git-commit-file: 89f53f008964b82faab3870e27bd3015ebece61b
matt: Lawrence
guide-url: guide-landing.html
guide-title: C'est une fois
solution-title: Matt's Test Repo Ne pas utiliser
solution-hub-url: https://docs.ci.corp.adobe.com
solution-image: aucun
getting-started-url: aide/c-gs/c-gs.md
tutorials-url: https://training.adobe.com/training/courses.html#
git-edit: https://git.corp.adobe.com/AdobeDocs/testing.en/tree/master/help/testing/troubleshooting.md
git-issue: https://git.corp.adobe.com/AdobeDocs/testing.en/issues/new
git-filename: help/testing/troubleshooting.md
git-repo: https://git.corp.adobe.com/AdobeDocs/testing.en
index: n
ROBOTS: NOINDEX, NOFOLLOW, NOARCHIVE, NOSNIPPET
translation-type: tm+mt
source-git-commit: 6267783d239cbca5f35fc07c3978dda3804b0f7a

---

# dépannage

## Test BR

* Got à des actifs<br/>![](assets/2018-07-24-13-47-56.png)
* Aide<br/>![](2018-07-24-13-49-21.png)
* Dossier de solution ouverte (launch.fr)<br/>![](2018-07-24-13-51-13.png)
* Cliquez sur l'entrée ditamap pour mettre en place le XML Add On panneau<br/>![](2018-07-24-13-52-20.png)
* Naviguez vers les sorties<br/>![](2018-07-24-13-53-25.png)


## Les phases du pipeline

Il y a trois phases principales du pipeline où des erreurs peuvent se produire :

1. Création Ditamap
2. Markdown à la conversion DITA (et HTML)
3. DITA à AEM Sites Génération en utilisant le XML Add-on For AEM

### Création Ditamap

Il s'agit du processus par lequel les fichiers TOC.md sont lus et une ditamap est créée.

En outre, c'est également là que la réécriture YAML se produit.  Tous les fichiers de markdown sont réécrits pour inclure :

* Toutes les variables YAML dans le fichier TOC.md (si la variable existe déjà dans le fichier de dépréciation, elle est conservée et considérée comme une dérogation locale pour ce fichier)
* Les variables git-repo sont créées (git-edit et git-issue)
* La dernière variable YAML modifiée est générée à partir de la date de validation du fichier et écrite en tant que variable YAML dans l'en-tête du fichier de markdown



### Markdown à Dita (et HTML) Conversion

Le contenu Markdown est d'abord converti en DITA avant de le télécharger sur AEM pour traitement.  En outre, au début du pipeline (Jenkins), HTML est généré à partir de la DITA comme une méthode pour attraper tous les problèmes qui peuvent se produire au cours de la génération de sites AEM avec le XML Add-on.

Ces fichiers DITA et HTML peuvent être consultés dans Jenkins.  Ouvrez le nom de l'emploi (lauch.en par exemple), et les fichiers générés seront dans l'espace de travail :

![](2018-07-24-12-52-17.png)

De l'espace de travail, naviguer vers l'extérieur / dita pour voir la dita brute qui a été généré.  Remarque : Bien que les extensions `.md`de fichiers de ce répertoire soient, le contenu est Dita.  Vous pouvez afficher ou télécharger ces fichiers et les exécuter via un validateur (comme OxygenXML).  En outre, dans l'espace de travail, vous pouvez également afficher les fichiers HTML générés (qui doivent être similaires au contenu créé par le XML Add-On).  Il suffit d'aller à l'annuaire out/html.

Au cours de la conversion, de nombreuses erreurs peuvent se produire à la suite de :

* Markdown invalide
* HTML non pris en charge dans le fichier Markdown


### DITA à AEM Sites Génération en utilisant le XML Add-on For AEM

Il est inhabituel de faire face à des *problèmes avec le DITA à AEM Sites* Generation qui n'est pas pris par le DITA à la transformation html plus tôt dans le pipeline .

Toutefois, s'il y a des difficultés, examinez les journaux Add On dans AEM (peut-être besoin de consulter un administrateur).  L'instance d'étape [actuelle](https://docs-author-stg.corp.adobe.com)pour Docs est https://docs-author-stg.corp.adobe.com .

Les journaux peuvent être trouvés dans :

<!-- markdownlint-disable MD037 -->
<!-- markdownlint-disable MD033 -->

* Got à des actifs<br/>![](assets/2018-07-24-13-47-56.png)
* Aide<br/>![](2018-07-24-13-49-21.png)
* Dossier de solution ouverte (launch.fr)<br/>![](2018-07-24-13-51-13.png)
* Cliquez sur l'entrée ditamap pour mettre en place le XML Add On panneau<br/>![](2018-07-24-13-52-20.png)
* Naviguez vers les sorties<br/>![](2018-07-24-13-53-25.png)
* Cliquez sur la date/heure de la sortie générée pour voir le journal<br/>![](2018-07-24-13-54-12.png)

## Problèmes courants

### Contenu non présenté dans aEM

#### problème

Le contenu est passé par le pipeline et le travail Jenkins a été couronnée de succès, cependant, aucun contenu ne peut être vu dans AEM.

#### résolution

Cela est le plus souvent attribuable au fait que le fichier TOC.md associé n'a pas été mis à jour pour inclure le fichier de balisage.

*Si un fichier de dépréciation n'est pas trouvé dans un TOC.md, il ne sera pas inclus dans le ditamap et ne sera pas téléchargé sur AEM.*

### Erreurs DITA

Lorsqu'un fichier de débarquement est traité via le pipeline, il est d'abord converti de Markdown à DITA à l'aide de la boîte à outils ouverte DITA, en particulier le plugin nommé lwDita (ou léger-dita).

Au cours de ce traitement, la dita résultante qui est générée à partir du fichier de balisage d'entrée peut être invalide.

#### problème

Facilement l'erreur la plus `DOTJ013E`commune encoutered est , indique le DITA généré est invalide.  échantillon:

```log
[DOTJ013E][ERROR] Failed to parse the referenced file 'file:/apps/jenkins/2.121.1/workspace/testing.en/out/dita/color.md'.: file:/apps/jenkins/2.121.1/workspace/testing.en/out/dita/color.md Line 16:Attribute "style" must be declared for element type "ph".
00:00:28.459 Build step 'Execute shell' marked build as failure
```

<!-- <font color="blue">Hello</font> -->

#### résolution

Examiner la source dita [générée](https://docs.ci.corp.adobe.com) en allant à Jenkins et en examinant le travail défaillant.
Le Dita généré est dans le

### Tables de Markdown mal formées

#### problème

`Error: Failed to run pipeline: No renderer configured for com.vladsch.flexmark.ext.aside.AsideBlock`

```markdown
| This
| is |
| a bad |table |
```

#### résolution

Un bloc de côté est une extension de la syntaxe `|`Markdown qui est indiquée par une ligne commençant par un tuyau .  Ceci n'est actuellement pas pris en charge par le processeur lwDita (markdown to dita).

Fixez la syntaxe de markdown pour la table (préférée) **ou, dans le cas des travées, créez une table html simple** :

<table>
    <tr>
        <td>lundi</td>
        <td>Est</td>
    </tr>
    <tr>
        <td>une mauvaise</td>
        <td>table</td>
    </tr>
</table>
