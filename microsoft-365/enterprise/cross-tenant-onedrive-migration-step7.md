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
ms.openlocfilehash: 22d18111bc45d30fab5cc9012857a979fa510e18
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807595"
---
# <a name="step-7--post-migration-steps"></a>7. Adım: Geçiş sonrası adımları

Bu, Kiracılar Arası OneDrive geçişini tamamlamak için tasarlanmış bir çözümdeki 7. Adımdır. Daha fazla bilgi için bkz. [Kiracılar arası OneDrive geçişine genel bakış](cross-tenant-onedrive-migration.md).

- 1. Adım: [Kaynağa ve hedef kiracılara bağlanma](cross-tenant-onedrive-migration-step1.md)
- 2. Adım: [Kaynak ile hedef kiracı arasında güven oluşturma](cross-tenant-onedrive-migration-step2.md) 
- 3. Adım: [Güvenin kurulduğunu doğrulama](cross-tenant-onedrive-migration-step3.md) 
- 4. Adım: [Kullanıcıları ve grupları önceden oluşturma](cross-tenant-onedrive-migration-step4.md)  
- 5. Adım: [Kimlik eşlemesini hazırlama](cross-tenant-onedrive-migration-step5.md)
- 6. Adım: [Kiracılar arası OneDrive geçişi başlatma](cross-tenant-onedrive-migration-step6.md)
- **7. Adım: [Geçiş sonrası adımları](cross-tenant-onedrive-migration-step7.md)**

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
