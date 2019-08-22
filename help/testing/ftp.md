---
git-commit: 4d22987883e7f5ddcabb054c15d4aeaf2086a5f9
last-update: '2019-04-24'
pipeline_filename: aide/test/ftp.md
publish-url: https://docs.adobe.com/content/help/en/./testing/hello/ftp.html
git-commit-file: 7fcf9cb00adc70a5810bca9d6f8e89eac3fcd912
description: Si vous ne téléchargez pas à l'aide de glisser-déposer, vous pouvez télécharger des données d'attribut client via FTP sur le cloud d'expérience.
keywords: attributs clients;services de base
seo-description: Si vous ne téléchargez pas à l'aide de glisser-déposer, vous pouvez télécharger des données d'attribut client via FTP sur le cloud d'expérience.
seo-title: Facultatif - Téléchargez le fichier de données via FTP à l'aide d'Adobe Experience Cloud
title: Facultatif - Téléchargez le fichier de données via FTP
uuid: d5f2ff9f-01d7-482d-9d46-070edc6e8ab4
guide-url: guide-landing.html
guide-title: C'est une fois
solution-title: Matt's Test Repo Ne pas utiliser
solution-hub-url: https://docs.ci.corp.adobe.com
solution-image: aucun
getting-started-url: aide/c-gs/c-gs.md
tutorials-url: https://training.adobe.com/training/courses.html#
git-edit: https://git.corp.adobe.com/AdobeDocs/testing.en/tree/master/help/testing/ftp.md
git-issue: https://git.corp.adobe.com/AdobeDocs/testing.en/issues/new
git-filename: aide/test/ftp.md
git-repo: https://git.corp.adobe.com/AdobeDocs/testing.en
index: n
ROBOTS: NOINDEX, NOFOLLOW, NOARCHIVE, NOSNIPPET
translation-type: tm+mt
source-git-commit: 6267783d239cbca5f35fc07c3978dda3804b0f7a

---

# Facultatif - Téléchargez le fichier de données via FTP

Si vous ne téléchargez pas à l'aide de glisser-déposer, vous pouvez télécharger des données d'attribut client via FTP sur le cloud d'expérience.

protocole

Vous pouvez télécharger les données après avoir créé une source d'attribut client et un compte FTP dans le Cloud Expérience. Vous créez un compte FTP par source d'attribut. Les fichiers téléchargés sont stockés dans le dossier racine de ce compte. Les données doivent [!DNL  .csv] être en [!DNL  .fin] format, avec un deuxième fichier pour indiquer que le téléchargement est terminé.

>[!IMPORTANT]
>
>Examinez les[ exigences de fichiers ](tables.md) de données pour télécharger les attributs des clients avant de télécharger le fichier.



Les téléchargements de fichiers vers le site FTP des attributs du client peuvent être effectués via FTP ou SFTP.

* Vous avez besoin d'un client qui prend en charge les connexions SFTP.
* Vous pouvez vous connecter à SFTP en utilisant soit [ nom ](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/?f=ftp_sftp_cert_auth)d'utilisateur / mot de passe ou en utilisant aucun mot de passe, comme décrit ici .

**Pour télécharger le fichier de données via FTP**

1. [Créez une source d'attribut client et téléchargez le fichier de données... ](tables.md).

   Assurez-vous que vous êtes connecté à [!DNL  ftp.adobe.com/>sftpname<]votre site FTP à .

1. [Créez une source d'attribut client et téléchargez le fichier de données... ](tables.md).
Assurez-vous que vous êtes connecté à [!DNL  ftp.adobe.com/>sftpname<]votre site FTP à .

1. Cliquez **** sur **[!UICONTROL Actions]**- Téléchargement de fichiers .

1. Téléchargez [!DNL  .fin] un fichier, afin que votre fichier puisse être récupéré.
Le type [!DNL  .fin] de fichier est créé par l'utilisateur et signale que le téléchargement est terminé. Il peut s'agit d'un fichier bloc-notes vierge. Par exemple, si [!DNL  crs123.csv]vous téléchargez , vous téléchargez [!DNL  crs123.fin]également .

   Si le téléchargement est réussi, les deux **** fichiers sont déplacés vers un dossier appelé traité .

   Voir [les exigences de fichiers](tables.md) de données pour télécharger les attributs des clients pour obtenir des informations importantes sur les noms et la structure des fichiers.
