---
title: Uç Nokta için Microsoft Defender iş ortağı olun
ms.reviewer: ''
description: Çözümünüzü Uç Nokta için Microsoft Defender ile tümleştirme ve iş ortağı olma adımlarını ve gereksinimlerini öğrenin
keywords: iş ortağı, tümleştirme, çözüm doğrulama, sertifikasyon, gereksinimler, üye, misa, uygulama portalı
ms.service: microsoft-365-security
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
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: cef657818549e28375ea1ab44de815dc46f6da86
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67696055"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>Uç Nokta için Microsoft Defender iş ortağı olun

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Uç Nokta için Defender çözüm ortağı olmak için aşağıdaki adımları izlemeniz ve tamamlamanız gerekir.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-license"></a>1. Adım: Uç Nokta için Microsoft Defender lisansına abone olma

Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink). Abone olmak, Uç Nokta için Microsoft Defender ile tümleşen çözümler geliştirmek için üç adede kadar cihazı olan bir Uç Nokta için Microsoft Defender kiracısı kullanmanıza olanak tanır.

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>2. Adım: Çözüm doğrulama ve sertifikasyon gereksinimlerini karşılama

Teknoloji iş ortaklarının tümleştirme çalışmalarını onaylamasının en iyi yolu, ortak bir müşterinin önerilen tümleştirme tasarımını onaylamasını sağlamaktır (müşteri, Microsoft 365 Defender **İş Ortağı Uygulaması sayfasında İş Ortağı öner** seçeneği İş Ortakları ve API > [İş Ortağı](https://security.microsoft.com/interoperability/partnersapps) uygulamalarını\) kullanabilir ve bu seçeneği \(test edip indirgemelerini sağlayabilir Uç Nokta için Microsoft Defender ekibi.

Uç Nokta için Microsoft Defender ekibi tümleştirmeyi gözden geçirip onayladıktan sonra sizi Microsoft Akıllı Güvenlik Derneği'ne iş ortağı olarak dahil edilmeniz için yönlendiririz.

## <a name="step-3-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>3. Adım: Uç Nokta için Microsoft Defender iş ortağı uygulama portalında listelenme

Uç Nokta için Microsoft Defender, Uç Nokta için Microsoft Defender yönetim portalına eklenmiş olan ürün içi [iş ortağı sayfasını](partner-applications.md) kullanarak üçüncü taraf uygulamaları bulmayı ve tümleştirmeyi destekler.

Şirketinizin ürün içi iş ortağı sayfasında iş ortağı olarak listelenmiş olması için aşağıdaki bilgileri sağlamanız gerekir:

1. Kare logo (SVG).
2. Sunulacak ürünün adı.
3. 15 sözcüklü bir ürün açıklaması sağlayın.
4. Müşteriler için yeterli bilgileri içerecek tümleştirmeyi veya blog gönderisini tamamlamak için müşterinin giriş sayfasına bağlantı. Uç Nokta için Microsoft Defender ürün adı da dahil olmak üzere tüm basın açıklamaları pazarlama ve mühendislik ekipleri tarafından gözden geçirilmelidir. Gözden geçirme işleminin yapılması için en az 10 gün bekleyin.
5. Çok kiracılı bir Azure AD yaklaşımı kullanıyorsanız, uygulamanın kullanımını izlemek için Azure AD uygulama adına ihtiyacımız olacaktır.
6. Genel API'ler veya Graph Güvenlik API'leri kümesini Uç Nokta için Microsoft Defender yapılan her API çağrısına User-Agent alanını ekleyin. Bu, istatistiksel amaçlar, sorun giderme ve iş ortağı tanıma için kullanılır. Ayrıca, bu adım Microsoft Intelligent Security Association (MISA) üyeliği için bir gereksinimdir.

   Şu adımları izleyin:

   - Her HTTP isteği üst bilgisindeki User-Agent alanını aşağıdaki biçime ayarlayın.

     ```http
     MdePartner-{CompanyName}-{ProductName}/{Version}
     ```

     Örneğin, Kullanıcı Aracısı:

     ```http
     MdePartner-Contoso-ContosoCognito/1.0.0
     ```

   - Daha fazla bilgi için bkz. [RFC 2616 section-14.43](https://tools.ietf.org/html/rfc2616#section-14.43).

Uç Nokta için Microsoft Defender ile ortaklıklar, karşılıklı müşterilerimizin savunmayı daha da kolaylaştırmalarına, tümleştirmelerine ve düzenlemelerine yardımcı olur. Uç Nokta için Microsoft Defender iş ortağı olmayı ve modern tehditleri birlikte önleyip yanıtlayarak müşterileri ve varlıklarını etkili bir şekilde koruma ortak hedefimize ulaşmayı seçtiğiniz için mutluyuz.

## <a name="misa-nomination"></a>MISA adaylığı 
Yönetilen güvenlik hizmeti sağlayıcıları (MSSP) ve bağımsız yazılım satıcıları (ISV), Microsoft Akıllı Güvenlik Birliği'ne (MISA) aday gösterilebilir. Daha fazla bilgi için bkz. [MISA bilgileri sayfası](https://www.microsoft.com/security/business/intelligent-security-association).


## <a name="related-topics"></a>İlgili konular

- [Teknik iş ortağı fırsatları](partner-integration.md)
