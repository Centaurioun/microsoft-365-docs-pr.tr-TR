---
title: ServiceNow ile Microsoft 365 destek tümleştirme sorunlarını giderme
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow için Kapsamlı Sertifikalı uygulama yükleme ve yapılandırma kılavuzu.
ms.openlocfilehash: f0972b937c864191ba5f6d2eb5689c879d1d5d5e
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68734329"
---
# <a name="troubleshooting-microsoft-365-support-integration-with-servicenow"></a>ServiceNow ile Microsoft 365 destek tümleştirme sorunlarını giderme

| \#  | Sorun  | Tanılama eylemi     |
|-----|--------------------------------|----------------------|
| 1   | **Microsoft 365 destek** sekmesi görünmüyor                                                                                                                                                                                    | Geçerli görünümü ve **Sistem Günlükleri** &gt; **Tümünü** filtre x\_mioms\_m365\_assit ile doğrulayın                        |
| 2   | **Microsoft tarafından önerilen çözümler'i** seçin ancak "Lütfen ServiceNow yöneticinize başvurun ve uygulama için kurulum adımlarını tamamlamasını isteyin" hatasını alın.                                                                      | Formun üst kısmındaki hata iletisini ve x mioms m365\_assit filtresiyle\_ **Sistem Günlükleri** &gt;\_**Tümünü** Denetleyin     |
| 3   | **Microsoft tarafından önerilen çözümler'i** seçin ancak "Lütfen ServiceNow yöneticinize başvurun ve uygulama için son kurulum adımını tamamlamasını isteyin" hatasını alın.                                                                | Formun üst kısmındaki hata iletisini ve x mioms m365\_assit filtresiyle\_ **Sistem Günlükleri** &gt;\_**Tümünü** Denetleyin     |
| 4   | Sorunu arama kutusuna yazın ve **Microsoft tarafından önerilen çözümler'i** seçin ancak "Lütfen ServiceNow yöneticinize başvurun ve uygulama için kurulum adımlarını tamamlamalarını isteyin" hatasını alın.                                   | Formun üst kısmındaki hata iletisini ve x mioms m365\_assit filtresiyle\_ **Sistem Günlükleri** &gt;\_**Tümünü** Denetleyin     |
| 5   | Arama kutusuna sorun yazın ve **Microsoft tarafından önerilen çözümler'i** seçin ancak "Lütfen ServiceNow yöneticinize başvurun ve uygulama için son kurulum adımını tamamlamasını isteyin" hatasını alın.                                 | Formun üst kısmındaki hata iletisini ve x mioms m365\_assit filtresiyle\_ **Sistem Günlükleri** &gt;\_**Tümünü** Denetleyin     |
| 6   | **Microsoft desteğine başvurun'u** seçin, ancak "Lütfen ServiceNow yöneticinize başvurun ve uygulama için kurulum adımlarını tamamlamasını isteyin" hatasını alın.                                                                       | Formun üst kısmındaki hata iletisini ve x mioms m365\_assit filtresiyle\_ **Sistem Günlükleri** &gt;\_**Tümünü** Denetleyin     |
| 7   | **Microsoft desteğine başvurun'u** seçin, ancak "Lütfen ServiceNow yöneticinize başvurun ve uygulama için son kurulum adımını tamamlamasını isteyin" hatasını alın.                                                                 | Formun üst kısmındaki hata iletisini ve x mioms m365\_assit filtresiyle\_ **Sistem Günlükleri** &gt;\_**Tümünü** Denetleyin     |
| 8   | **Microsoft desteğine başvurun'u** seçin ancak "{EmailAddress} geçerli bir Microsoft 365 yönetici hesabı değil. Hizmet isteğini açmak için Microsoft 365 yönetici ayrıcalıklarına sahip olmanız gerekir. Uygulamada yönetici hesabını bağlayın." | Formun üst kısmındaki hata iletisini ve x mioms m365\_assit filtresiyle\_ **Sistem Günlükleri** &gt;\_**Tümünü** Denetleyin     |
| 9   | **Microsoft tarafından önerilen çözümleri** seçin ancak hiçbir şey gösterilmez                                                                                                                                                            | Sistem Günlüklerini Denetleme – Filtre login.microsoftonline.com ve connector.rave.microsoft.com ile **giden HTTP günlükleri** |
| 10  | **Microsoft tarafından önerilen çözümler'i** seçin ancak "Lütfen uygulama desteğine başvurun" hatası alın.                                                                                                                                     | Formun üst kısmındaki hata iletisini ve x mioms m365\_assit filtresiyle\_ **Sistem Günlükleri** &gt;\_**Tümünü** Denetleyin     |
| 11  | Arama kutusuna sorun yazın ve **Microsoft tarafından önerilen çözümler'i** seçin ancak hiçbir şey gösterilmez                                                                                                                             | Sistem Günlüklerini Denetleme – Filtre login.microsoftonline.com ve connector.rave.microsoft.com ile **giden HTTP günlükleri** |
| 12  | Arama kutusuna sorun yazın ve **Microsoft tarafından önerilen çözümler'i** seçin ancak "Lütfen uygulama desteğine başvurun" hatası alın.                                                                                                      | Formun üst kısmındaki hata iletisini ve x mioms m365\_assit filtresiyle\_ **Sistem Günlükleri** &gt;\_**Tümünü** Denetleyin     |
| 13  | Kullanıcı **Microsoft desteğine başvurun'u** seçer ancak hiçbir şey olmaz                                                                                                                                                            | Sistem Günlüklerini Denetleme – Filtre login.microsoftonline.com ve connector.rave.microsoft.com ile **giden HTTP günlükleri** |
| 14  | Olay yeniden açıldıktan sonra Microsoft tarafından önerilen çözüm görünmüyor                                                                                                                                                      | **Sistem Günlüklerinin** &gt; **Tümünü** filtre x\_mioms\_m365\_assit ile denetleyin                                              |
| 15  | Microsoft desteğine aktarılan olay yeniden açılırken Microsoft servis taleplerini göremiyorum                                                                                                                            | **Sistem Günlüklerinin** &gt; **Tümünü** filtre x\_mioms\_m365\_assit ile denetleyin                                              |
| 16  | Bilet ayrıntıları kaydedilemiyor, "Bilet ayrıntıları kaydedilemiyor. Lütfen Uygulama desteğine başvurun."                                                                                                                          | Formun üstündeki hata iletisini denetleyin                                                                            |
