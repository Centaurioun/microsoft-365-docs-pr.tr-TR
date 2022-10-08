---
title: Gelişmiş tehdit avcılığı şemasında AADSignInEventsBeta tablosu
description: Gelişmiş tehdit avcılığı şemasının Azure Active Directory oturum açma olayları tablosu hakkında bilgi edinin
keywords: gelişmiş tehdit avcılığı, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, şema başvurusu, kusto, tablo, sütun, veri türü, açıklama, dosya, IP adresi, cihaz, makine, kullanıcı, hesap, kimlik, AAD
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
ms.topic: article
ms.openlocfilehash: ce62e5c54c8ce74c76cd85aed1d7b51176cec792
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68092147"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Tablo `AADSignInEventsBeta` şu anda beta sürümündedir ve Azure Active Directory (AAD) oturum açma olaylarını izlemenize olanak sağlamak için kısa süreli olarak sunulmaktadır. Müşterilerin bu tabloya yönelik etkinlikleri toplamak ve görüntülemek için Azure Active Directory Premium P2 lisansına sahip olması gerekir. Tüm oturum açma şeması bilgileri sonunda tabloya `IdentityLogonEvents` taşınır.

`AADSignInEventsBeta` Gelişmiş tehdit avcılığı şemasındaki tablo, Azure Active Directory etkileşimli ve etkileşimli olmayan oturum açma işlemleri hakkında bilgi içerir. [Azure Active Directory oturum açma etkinlik raporları - önizlemede oturum açma](/azure/active-directory/reports-monitoring/concept-all-sign-ins) işlemleri hakkında daha fazla bilgi edinin.

Tablodan bilgi döndüren sorgular oluşturmak için bu başvuruyu kullanın. Gelişmiş tehdit avcılığı şemasındaki diğer tablolar hakkında bilgi için gelişmiş [avcılık başvurusuna](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference) bakın.

<br>

****

|Sütun adı|Veri türü|Açıklama|
|---|---|---|
|`Timestamp`|`datetime`|Kaydın oluşturulduğu tarih ve saat|
|`Application`|`string`|Kaydedilen eylemi gerçekleştiren uygulama|
|`ApplicationId`|`string`|Uygulama için benzersiz tanımlayıcı|
|`LogonType`|`string`|Oturum açma oturumunun türü, etkileşimli, uzaktan etkileşimli (RDP), ağ, toplu işlem ve hizmet|
|`ErrorCode`|`int`|Oturum açma hatası oluşursa hata kodunu içerir. Belirli bir hata kodunun açıklamasını bulmak için adresini ziyaret edin <https://aka.ms/AADsigninsErrorCodes>.|
|`CorrelationId`|`string`|Oturum açma olayının benzersiz tanımlayıcısı|
|`SessionId`|`string`|Ziyaret veya oturum sırasında bir web sitesinin sunucusu tarafından kullanıcıya atanan benzersiz numara|
|`AccountDisplayName`|`string`|Adres defterinde görüntülenen hesap kullanıcısının adı. Genellikle belirli bir adın veya adın, ikinci bir adın ve soyadının veya soyadının birleşimidir.|
|`AccountObjectId`|`string`|Azure AD'daki hesap için benzersiz tanımlayıcı|
|`AccountUpn`|`string`|Hesabın kullanıcı asıl adı (UPN)|
|`IsExternalUser`|`int`|Oturum açan kullanıcının dış kullanıcı olup olmadığını gösterir. Olası değerler: -1 (ayarlanmadı), 0 (dış değil), 1 (dış).|
|`IsGuestUser`|`boolean`|Oturum açan kullanıcının kiracıda konuk olup olmadığını gösterir|
|`AlternateSignInName`|`string`|Azure AD oturum açmış kullanıcının şirket içi kullanıcı asıl adı (UPN)|
|`LastPasswordChangeTimestamp`|`datetime`|Oturum açan kullanıcının parolasını en son değiştirdiği tarih ve saat|
|`ResourceDisplayName`|`string`|Erişilen kaynağın görünen adı|
|`ResourceId`|`string`|Erişilen kaynağın benzersiz tanımlayıcısı|
|`ResourceTenantId`|`string`|Erişilen kaynağın kiracısının benzersiz tanımlayıcısı|
|`DeviceName`|`string`|Makinenin tam etki alanı adı (FQDN)|
|`AadDeviceId`|`string`|Azure AD'da cihaz için benzersiz tanımlayıcı|
|`OSPlatform`|`string`|Makinede çalışan işletim sisteminin platformu. Windows 11, Windows 10 ve Windows 7 gibi aynı aile içindeki varyasyonlar da dahil olmak üzere belirli işletim sistemlerini gösterir.|
|`DeviceTrustType`|`string`|Oturum açan cihazın güven türünü gösterir. Yalnızca yönetilen cihaz senaryoları için. Olası değerler Workplace, AzureAd ve ServerAd'dır.|
|`IsManaged`|`int`|Oturum açmayı başlatan cihazın yönetilen bir cihaz (1) olup olmadığını gösterir (0)|
|`IsCompliant`|`int`|Oturum açmayı başlatan cihazın uyumlu (1) veya uyumlu olmadığını gösterir (0)|
|`AuthenticationProcessingDetails`|`string`|Kimlik doğrulama işlemcisi hakkındaki ayrıntılar|
|`AuthenticationRequirement`|`string`|Oturum açma için gereken kimlik doğrulama türü. Olası değerler: multiFactorAuthentication (MFA gerekiyordu) ve singleFactorAuthentication (MFA gerekli değildi).|
|`TokenIssuerType`|`int`|Belirteç verenin Azure Active Directory (0) veya Active Directory Federasyon Hizmetleri (AD FS) (1) olup olmadığını gösterir|
|`RiskLevelAggregated`|`int`|Oturum açma sırasında toplu risk düzeyi. Olası değerler: 0 (toplam risk düzeyi ayarlanmadı), 1 (yok), 10 (düşük), 50 (orta) veya 100 (yüksek).|
|`RiskDetails`|`int`|Oturum açan kullanıcının riskli durumuyla ilgili ayrıntılar|
|`RiskState`|`int`|Riskli kullanıcı durumunu gösterir. Olası değerler: 0 (yok), 1 (güvenli onaylandı), 2 (düzeltildi), 3 (kapatıldı), 4 (risk altında) veya 5 (güvenliği aşıldığı onaylandı).|
|`UserAgent`|`string`|Web tarayıcısından veya diğer istemci uygulamasından kullanıcı aracısı bilgileri|
|`ClientAppUsed`|`string`|Kullanılan istemci uygulamasını gösterir|
|`Browser`|`string`|Oturum açmak için kullanılan tarayıcı sürümüyle ilgili ayrıntılar|
|`ConditionalAccessPolicies`|`string`|Oturum açma olayına uygulanan koşullu erişim ilkelerinin ayrıntıları|
|`ConditionalAccessStatus`|`int`|Oturum açma işlemine uygulanan koşullu erişim ilkelerinin durumu. Olası değerler 0 (ilkeler uygulandı), 1 (ilke uygulama girişimi başarısız oldu) veya 2 (ilkeler uygulanmadı) değerleridir.|
|`IPAddress`|`string`|Uç noktaya atanan ve ilgili ağ iletişimleri sırasında kullanılan IP adresi|
|`Country`|`string`|İstemci IP adresinin coğrafi olarak konumlandırıldığı ülkeyi gösteren iki harfli kod|
|`State`|`string`|Varsa oturum açma işleminin gerçekleştiği durum|
|`City`|`string`|Hesap kullanıcısının bulunduğu şehir|
|`Latitude`|`string`|Oturum açma konumunun kuzeyden güneye koordinatları|
|`Longitude`|`string`|Oturum açma konumunun doğudan batıya koordinatları|
|`NetworkLocationDetails`|`string`|Oturum açma olayının kimlik doğrulama işlemcisinin ağ konumu ayrıntıları|
|`RequestId`|`string`|İsteğin benzersiz tanımlayıcısı|
|`ReportId`|`string`|Olayın benzersiz tanımlayıcısı|

## <a name="related-articles"></a>İlgili makaleler

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [Gelişmiş avcılığa genel bakış](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [Sorgu dilini öğrenin](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [Şemayı anlayın](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
