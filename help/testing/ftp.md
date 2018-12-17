---
git-commit: 929f281af2114d7ed4173f66e85085ded450a8c8
last-update: 2018-10-17T00:00:00Z
description: If you do not upload using drag-and-drop, you can upload customer attribute
  data via FTP to the Experience Cloud.
keywords: customer attributes;core services
seo-description: If you do not upload using drag-and-drop, you can upload customer
  attribute data via FTP to the Experience Cloud.
seo-title: Optional - Upload the data file via FTP using Adobe Experience Cloud
title: Optional - Upload the data file via FTP
uuid: d5f2ff9f-01d7-482d-9d46-070edc6e8ab4
index: y
internal: n
snippet: y
translate: y
guide-url: guide-landing.html
guide-title: リリースノート
solution-title: Matt's Test Repo
solution-hub-url: https://docs.ci.corp.adobe.com
solution-image: None
getting-started-url: help/c-gs/c-gs.md
tutorials-url: https://training.adobe.com/training/courses.html#
git-edit: https://git.corp.adobe.com/AdobeDocs/testing.en/tree/master/help/testing/ftp.md
git-issue: https://git.corp.adobe.com/AdobeDocs/testing.en/issues/new
git-filename: help/testing/ftp.md
git-repo: https://git.corp.adobe.com/AdobeDocs/testing.en
translation-type: tm+mt
source-git-commit: 2c12e0f224f51dbe3cf0cf81176451db256716a0

---

# Optional - Upload the data file via FTP

If you do not upload using drag-and-drop, you can upload customer attribute data via FTP to the Experience Cloud.

ftp

You can upload the data after you create a customer attribute source and an FTP account in the Experience Cloud. You create one FTP account per attribute source. The uploaded files are stored in the root folder of that account. The data must be in [!DNL  .csv] format, with a second [!DNL  .fin] file to indicate the upload is complete.

>[!IMPORTANT]
>
>Review[ Data file requirements for uploading customer attributes ](tables.md)  before uploading the file.



File uploads to the customer attributes FTP site can be done via FTP or SFTP.

* You need a client that supports SFTP connections.
* You can connect with SFTP using either username/password or using no password, as described [ here ](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/?f=ftp_sftp_cert_auth).

**To upload the data file via FTP**

1. [Create a customer attribute source and upload the data file...](tables.md).

   Ensure that you are logged in to your FTP site at [!DNL  ftp.adobe.com/&gt;sftpname&lt;].

1. [Create a customer attribute source and upload the data file...](tables.md).
Ensure that you are logged in to your FTP site at [!DNL  ftp.adobe.com/<sftpname>].

1. Click **[!UICONTROL  Actions]** > **[!UICONTROL  File Upload]**.

1. Upload a [!DNL  .fin] file, so that your file can be retrieved.
The file type [!DNL  .fin] is user-created and signals that the upload is finished. It can be a blank notepad file. For example, if you upload [!DNL  crs123.csv], you also upload [!DNL  crs123.fin].

   If the upload is successful, both files are moved to a folder called **processed**.

   See [Data file requirements for uploading customer attributes](tables.md) for important information about file names and structure.
