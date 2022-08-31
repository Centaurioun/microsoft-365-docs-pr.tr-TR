---
title: ABD Hükümeti müşterileri için Microsoft 365 Defender
description: ABD Kamu müşterilerinin gereksinimlerine ve özelliklerine yönelik Microsoft 365 Defender hakkında bilgi edinin
keywords: government, gcc, high, requirements, capabilities, defender, Microsoft 365 Defender, xdr, dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: d1fa56bc797a3f651d79ab87f9ade0a9d753849d
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482152"
---
# <a name="microsoft-365-defender-for-us-government-customers"></a>ABD Hükümeti müşterileri için Microsoft 365 Defender

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Azure US Government ortamında yerleşik olarak bulunan US Government müşterileri için Microsoft 365 Defender, Azure Ticari'deki Microsoft 365 Defender temel alınan teknolojilerin aynısını kullanır.

Bu teklif GCC, GCC High ve DoD müşterilerine sunulur ve ticari sürümle aynı önleme, algılama, araştırma ve düzeltmeyi temel alır. Ancak, bu teklif için özelliklerin kullanılabilirliği ile ilgili bazı farklılıklar vardır.

> [!NOTE]
> Cloud Apps için Defender, Uç Nokta için Defender veya Ticari Kimlik için Defender kullanan bir GCC müşterisiyseniz, Microsoft 365 Defender GCC'ye uygun olmak için bu hizmetleri kendi GCC sürümlerine geçirmelisiniz.

## <a name="licensing-requirements"></a>Lisans gereksinimleri

US Government müşterileri için Microsoft 365 Defender aşağıdaki Microsoft toplu lisanslama tekliflerinden birini gerektirir:

### <a name="desktop-licensing"></a>Masaüstü lisanslama

<br />

****

|Gcc|GCC Yüksek|Dod|
|---|---|---|
|Microsoft 365 GCC G5|GCC High için Microsoft 365 E5|DOD için Microsoft 365 G5|
|Microsoft 365 G5 Güvenlik GCC|GCC High için Microsoft 365 G5 Güvenliği|DOD için Microsoft 365 G5 Güvenliği|
|Enterprise Mobility + Security G5 GCC|GCC High için Enterprise Mobility + Security E5|DOD için E5 Enterprise Mobility + Security|
|Office 365 G5 GCC|GCC High için Office 365 E5|DOD için Office 365 E5|
|GCC'Microsoft Defender for Cloud Apps|GCC High için Microsoft Defender for Cloud Apps|DOD için Microsoft Defender for Cloud Apps|
|Uç Nokta için Microsoft Defender - GCC|GCC High için Uç Nokta için Microsoft Defender|DOD için Uç Nokta için Microsoft Defender|
|Kimlik için Microsoft Defender - GCC|GCC High için Kimlik için Microsoft Defender|DOD için Kimlik için Microsoft Defender|
|Office 365 için Microsoft Defender (Plan 2) GCC|GCC High için Office 365 için Microsoft Defender (Plan 2)|DOD için Office 365 için Microsoft Defender (Plan 2)|
|Windows 10 Enterprise E5 GCC|GCC High için Windows 10 Enterprise E5|DOD için E5 Windows 10 Enterprise|
|

### <a name="server-licensing"></a>Sunucu lisanslama

<br />

****

|Gcc|GCC Yüksek|Dod|
|---|---|---|
|Uç Nokta için Microsoft Defender Sunucusu GCC|GCC High için Uç Nokta için Microsoft Defender Sunucusu|DOD için Uç Nokta için Microsoft Defender Sunucusu|
|Sunucular için Microsoft Defender|Sunucular için Microsoft Defender - Kamu|Sunucular için Microsoft Defender - Kamu|
|

## <a name="portal-urls"></a>Portal URL'leri

US Government müşterileri için Microsoft 365 Defender portalı URL'leri şunlardır:

<br />

****

|Müşteri türü|Portal URL'si|
|---|---|
|Gcc|<https://security.microsoft.com>|
|GCC Yüksek|Kullanıma sunulma|
|Dod|Kullanıma sunulma|
|
> [!NOTE]
> GCC müşterisiyseniz ve ticari Uç Nokta için Microsoft Defender GCC'ye geçiş sürecinde Uç Nokta için Microsoft Defender ticari verilerinize erişmek için kullanınhttps://transition.security.microsoft.com.

## <a name="api"></a>Apı

[API belgelerimizde](api-overview.md) listelenen genel URI'ler yerine aşağıdaki URI'leri kullanmanız gerekir:

<br />

****

|Uç nokta türü|Gcc|GCC High & DoD|
|---|---|---|
|Oturum açma|`https://login.microsoftonline.com`|`https://login.microsoftonline.us`|
|Microsoft 365 Defender API|`https://api-gcc.security.microsoft.us`|`https://api-gov.security.microsoft.us`|
|

## <a name="feature-parity-with-commercial"></a>Ticari özellik eşlik

US Government müşterileri için Microsoft 365 Defender, ticari teklifle tam eşliğe sahip değildir. Hedefimiz tüm ticari özellikleri ve işlevleri ABD Kamu müşterilerimize sunmak olsa da, henüz vurgulamak istediğimiz bazı özellikler mevcut değildir.

Bilinen boşluklar şunlardır:

<br />

****

|Özellik adı|Gcc|GCC Yüksek|Dod|
|---|:---:|:---:|:---:|
|Tümleştirmeler: Microsoft Sentinel (Olaylar & Ham veriler)|![Evet](../defender-endpoint/images/svg/check-yes.svg) Genel önizlemede|![Evet](../defender-endpoint/images/svg/check-yes.svg) Genel önizlemede|![Evet](../defender-endpoint/images/svg/check-yes.svg) Genel önizlemede|
|Microsoft Tehdit Uzmanları|![Hayır](../defender-endpoint/images/svg/check-no.svg) Mühendislik kapsamı üzerinde|![Hayır](../defender-endpoint/images/svg/check-no.svg) Mühendislik kapsamı üzerinde|![Hayır](../defender-endpoint/images/svg/check-no.svg) Mühendislik kapsamı üzerinde|

Olay Akışı API'si tablolarının ayrıntılı listesi için bkz. [Olay Akışı API'sinde desteklenen Microsoft 365 Defender akış olayı türleri](supported-event-types.md).

## <a name="more-details"></a>Diğer ayrıntılar

Daha fazla bilgi için tek tek iş yükleri US Gov sayfalarına bakın:

- [Microsoft Defender for Cloud Apps](/enterprise-mobility-security/solutions/ems-cloud-app-security-govt-service-description).
- [Kimlik için Microsoft Defender](/enterprise-mobility-security/solutions/ems-mdi-govt-service-description).
- [Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/gov).
