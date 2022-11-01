---
title: OneDrive Kiracılar Arası Kullanıcı Verileri Geçişi 7. Adım
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sharepoint-migration
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: OneDrive Kiracılar arası geçiş özelliğinin 7. adımı
ms.openlocfilehash: acd9130b6058ef0dceae0dcc8c6e60699a4fd39e
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806132"
---
# <a name="step-7--post-migration-steps"></a>7. Adım: Geçiş sonrası adımları

## <a name="removing-trust-relationship"></a>Güven ilişkisi kaldırılıyor

>[!Important]
>Kaynak kiracı lisanslarınızın süresi dolmadan önce hem kaynak hem de hedef kiracılardaki Güven İlişkisini kaldırdığınızdan emin olun. Lisansların süresi dolduğunda, güven kaldırma komutu kaynakta çalışmaz.

1. Kaynak kiracıda, Kaynak ve Hedef kiracı arasındaki güven ilişkisini kaldırmak için bu komutu çalıştırın.

```powershell
Remove-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Target -PartnerCrossTenantHostUrl <TARGETCrossTenantHostUrl>

```
</br>

2. Hedef kiracıda, hedef ve kaynak kiracı arasındaki güven ilişkisini kaldırmak için bu komutu çalıştırın.

```powershell

Remove-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Target -PartnerCrossTenantHostUrl <TARGETCrossTenantHostUrl>

```


### <a name="parameter-definitions"></a>Parametre tanımları

|Parametre|Tanım|
|:-----|:-----|
|PartnerRole|Güven oluşturduğunuz iş ortağı kiracısının rolleri.  OneDrive geçişlerinin kaynağı iş ortağı kiracısı ise *kaynak* , *hedef* ise hedef olarak kaynak kullanın.
|PartnerCrossTenantHostURL|İş ortağı kiracısının kiracılar arası ana bilgisayar URL'si.  İş ortağı kiracısı, kiracıların her birinde *Get-SPOCrossTenantHostURL* komutunu çalıştırarak bunu sizin için belirleyebilir.|


## <a name="other-post-migration-steps"></a>Geçiş sonrası diğer adımlar

Geçiş tamamlandıktan sonra OneDrive kullanıcılarının yeni kimliklerini kullanarak oturum açması ve hedef kiracıdaki cihazlarına dosyalarını yeniden eşitlemesi gerekir.

### <a name="onedrive-for-business"></a>OneDrive İş
Yeni kimlik bilgileriyle, kullanıcıların Microsoft 365 uygulama başlatıcısını veya bir web tarayıcısını kullanarak OneDrive'da oturum açmasını sağlayın.

### <a name="permissions-on-onedrive-content"></a>OneDrive içeriğindeki izinler
OneDrive içeriğine erişme izni olan kullanıcılar, kimlik eşleme dosyasına dahil edilmeleri koşuluyla bu içeriğe erişmeye devam eder

### <a name="onedrive-sync-client"></a>OneDrive Eşitleme İstemcisi
Kullanıcının yeni kimliğini kullanarak **OneDrive Eşitleme İstemcisi'nde** ve yeni OneDrive konumunda oturum açması gerekir. Bu adımı tamamladıktan sonra dosyalar ve klasörler cihaza yeniden eşitlemeye başlar.

### <a name="sharing-links"></a>Paylaşım Bağlantıları
Geçirilen dosyalar için mevcut paylaşılan bağlantılar otomatik olarak yeni hedef konuma yönlendirilir.
