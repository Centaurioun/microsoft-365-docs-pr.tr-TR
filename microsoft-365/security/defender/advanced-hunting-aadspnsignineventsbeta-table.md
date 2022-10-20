---
title: Gelişmiş tehdit avcılığı şemasında AADSpnSignInEventsBeta tablosu
description: Azure Active Directory'nin hizmet sorumlusu ve yönetilen kimlik oturum açma olayları tablosuyla ilişkili bilgiler hakkında bilgi edinin.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: d24a67f6323e0f556e25021470d808b2fc67d918
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68637056"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

> [!IMPORTANT]
> Tablo `AADSpnSignInEventsBeta` şu anda beta sürümündedir ve Azure Active Directory (AAD) oturum açma olaylarını izlemenize olanak sağlamak için kısa süreli olarak sunulmaktadır. Müşterilerin bu tabloya yönelik etkinlikleri toplamak ve görüntülemek için Azure Active Directory Premium P2 lisansına sahip olması gerekir. Microsoft sonunda tüm oturum açma şeması bilgilerini tabloya `IdentityLogonEvents` taşıyacaktır.

`AADSpnSignInEventsBeta` Gelişmiş tehdit avcılığı şemasındaki tablo, Azure Active Directory hizmet sorumlusu ve yönetilen kimlik oturum açma işlemleri hakkında bilgi içerir. [Azure Active Directory oturum açma etkinlik raporlarında (önizleme](/azure/active-directory/reports-monitoring/concept-all-sign-ins)) farklı oturum açma türleri hakkında daha fazla bilgi edinebilirsiniz.

Tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın.

Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) bakın.

<br>

****

|Sütun adı|Veri türü|Açıklama|
|---|---|---|
|`Timestamp`|`datetime`|Kaydın oluşturulduğu tarih ve saat|
|`Application`|`string`|Kaydedilen eylemi gerçekleştiren uygulama|
|`ApplicationId`|`string`|Uygulama için benzersiz tanımlayıcı|
|`IsManagedIdentity`|`boolean`|Oturum açma işleminin yönetilen kimlik tarafından başlatılıp başlatılmadığını gösterir|
|`ErrorCode`|`int`|Oturum açma hatası oluşursa hata kodunu içerir. Belirli bir hata kodunun açıklamasını bulmak için adresini ziyaret edin <https://aka.ms/AADsigninsErrorCodes>.|
|`CorrelationId`|`string`|Oturum açma olayının benzersiz tanımlayıcısı|
|`ServicePrincipalName`|`string`|Oturum açmayı başlatan hizmet sorumlusunun adı|
|`ServicePrincipalId`|`string`|Oturum açmayı başlatan hizmet sorumlusunun benzersiz tanımlayıcısı|
|`ResourceDisplayName`|`string`|Erişilen kaynağın görünen adı|
|`ResourceId`|`string`|Erişilen kaynağın benzersiz tanımlayıcısı|
|`ResourceTenantId`|`string`|Erişilen kaynağın kiracısının benzersiz tanımlayıcısı|
|`IPAddress`|`string`|Uç noktaya atanan ve ilgili ağ iletişimleri sırasında kullanılan IP adresi|
|`Country`|`string`|İstemci IP adresinin coğrafi olarak konumlandırıldığı ülkeyi gösteren iki harfli kod|
|`State`|`string`|Varsa oturum açma işleminin gerçekleştiği durum|
|`City`|`string`|Hesap kullanıcısının bulunduğu şehir|
|`Latitude`|`string`|Oturum açma konumunun kuzeyden güneye koordinatları|
|`Longitude`|`string`|Oturum açma konumunun doğudan batıya koordinatları|
|`RequestId`|`string`|İsteğin benzersiz tanımlayıcısı|
|`ReportId`|`string`|Olayın benzersiz tanımlayıcısı|
||||

## <a name="related-articles"></a>İlgili makaleler

- [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
- [Gelişmiş avcılığa genel bakış](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Sorgu dilini öğrenin](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [Şemayı anlayın](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
