---
git-commit: 4d22987883e7f5ddcabb054c15d4aeaf2086a5f9
last-update: '2019-05-08'
pipeline_filename: help/testing/audience-lab-faq.md
publish-url: https://docs.adobe.com/content/help/en/./testing/hello/second-group-c/audience-lab-faq.html
git-commit-file: 0dd86c17204472f130e1552e72e2615020b9be78
description: Questions fréquemment posées sur la fonction Audience Lab.
seo-description: Questions fréquemment posées sur la fonction Audience Lab.
seo-title: FAQ de laboratoire d'audience
solution: Gestionnaire d'audience
title: FAQ de laboratoire d'audience
topic: API DIL
uuid: 24ac421a-edc3-4d0b-af45-2da78562e519
internal: n
snippet: y (en)
translate: y (en)
guide-url: guide-landing.html
guide-title: C'est une fois
solution-title: Matt's Test Repo Ne pas utiliser
solution-hub-url: https://docs.ci.corp.adobe.com
solution-image: aucun
getting-started-url: aide/c-gs/c-gs.md
tutorials-url: https://training.adobe.com/training/courses.html#
git-edit: https://git.corp.adobe.com/AdobeDocs/testing.en/tree/master/help/testing/audience-lab-faq.md
git-issue: https://git.corp.adobe.com/AdobeDocs/testing.en/issues/new
git-filename: help/testing/audience-lab-faq.md
git-repo: https://git.corp.adobe.com/AdobeDocs/testing.en
index: n
ROBOTS: NOINDEX, NOFOLLOW, NOARCHIVE, NOSNIPPET
translation-type: tm+mt
source-git-commit: 6267783d239cbca5f35fc07c3978dda3804b0f7a

---

# FAQ de laboratoire d'audience

**Les segments de test créés dans les groupes de test ont-ils des identifiants de segment différents ? Comment puis-je cartographier les iD vers différentes destinations ?**


Oui, les segments de test ont des identifiants de segment différents. Pour les destinations avec La cartographie de destination [!UICONTROL  auto-remplie ou les segments envoyés à Google, Audience Lab] gérera les valeurs de cartographie comme les destinations normalement.

**Le même trait de conversion peut-il être associé à plusieurs groupes de test ?**

Oui, c'est permis. Pensez à un cas d'un test utilisant un segment masculin associé à la conversion X et un test à l'aide d'un segment féminin associé à la conversion X. Il n'a pas d'importance que les deux tests sont la conduite des conversions car ils testent deux publics différents.

**Supposons qu'un groupe de test utilise un profil authentifié pour le fractionnement du segment de test. Le profil authentifié[est lié à 4](https://marketing.adobe.com/resources/help/en_US/aam/ids-in-aam.html)UUID de Gestionnaire d'Audience. Lorsque le visiteur présente un trait de conversion de l'un des quatre UUID, le laboratoire d'audience compte-t-il cela comme une ou quatre conversions ?**

Dans ce cas, Audience Lab ne compte qu'une seule conversion. Dans d'autres cas, Audience Lab compte de nombreuses conversions. Ce n'est qu'une réponse de test.

**Que se passe-t-il si le visiteur de l'affaire ci-dessus présente d'abord le trait de conversion de l'un des quatre UUID liés à leur profil authentifié, puis présente également le trait de conversion de deux autres UUID liés au profil authentifié ? Ce cas compte-t-il comme une ou trois conversions ?**

Dans ce [!UICONTROL  cas,] Audience Lab compte trois conversions, une pour chaque appareil qui a exposé le trait d'authentification.

**Un utilisateur peut-il avoir un accès Segment: Read-Only, mais aussi audience Lab test segment d'accès à la création?**

Voir [ Créer des](https://marketing.adobe.com/resources/help/en_US/aam/ids-in-aam.html) groupes de test [!UICONTROL  de] segment pour obtenir de l'information sur la façon d'utiliser le laboratoire d'audience avec les privilèges RBAC.

**Puis-je utiliser Audience Lab en conjonction avec le Profil[Link Device Graph](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html)et external Device Graphs (Adobe Experience Cloud Device Co-op , Tapad Device Graph, Liveramp Device Graph)?**

Pour l'instant, Audience Lab ne peut diviser les populations de segments que par les appareils connectés à un appareil de qualification, lors de l'utilisation du graphique de l'appareil De lien de profil. Nous travaillons sur l'ajout de support dans Audience Lab pour les autres graphiques de périphériques et vous ferons savoir quand nous le faisons.
