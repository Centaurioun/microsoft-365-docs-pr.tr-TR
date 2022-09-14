---
title: Yönetim ve API'lere genel bakış
ms.reviewer: ''
description: Uç Nokta için Microsoft Defender'deki yönetim araçları ve API kategorileri hakkında bilgi edinin
keywords: ekleme, api, siem, rbac, access, portal, tümleştirme, araştırma, yanıt, varlıklar, varlık, kullanıcı bağlamı, uygulama bağlamı, akış
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
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 447440dfb93d8e0c3814ae531c8feb7fc318d27f
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67689809"
---
# <a name="overview-of-management-and-apis"></a>Yönetim ve API'lere genel bakış

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mgt-apis-abovefoldlink)


Uç Nokta için Defender, müşterilerin platformu kolayca benimseyebilmesini sağlamak için çok çeşitli seçenekleri destekler.

Müşteri ortamlarının ve yapılarının farklılık gösterebileceğini kabul eden Uç Nokta için Defender, çeşitli müşteri gereksinimlerine uyacak şekilde esneklik ve ayrıntılı denetimle oluşturulmuştur.

## <a name="endpoint-onboarding-and-portal-access"></a>Uç nokta ekleme ve portal erişimi

Cihaz ekleme, istemci cihazlar için Microsoft Endpoint Manager ve Microsoft Intune ve sunucu cihazları için Microsoft Defender ile tamamen tümleşiktir ve yapılandırma, dağıtım ve izleme konusunda uçtan uca eksiksiz bir deneyim sağlar. Ayrıca Uç Nokta için Microsoft Defender, cihaz yönetimi için kullanılan grup ilkesi ve diğer üçüncü taraf araçları destekler.

Uç Nokta için Defender, portala erişimi olan kullanıcıların rol tabanlı erişim denetimi (RBAC) esnekliği aracılığıyla görebilecekleri ve yapabilecekleri üzerinde ayrıntılı denetim sağlar. RBAC modeli, güvenlik ekipleri yapısının tüm çeşitlerini destekler:

- Küresel olarak dağıtılmış kuruluşlar ve güvenlik ekipleri
- Katmanlı model güvenlik operasyonları ekipleri
- Tek merkezi küresel güvenlik operasyonları ekipleri ile tamamen ayrılmış bölümler

## <a name="available-apis"></a>Kullanılabilir API'ler

Uç Nokta için Microsoft Defender çözümü, tümleştirmeye hazır bir platformun üzerine kurulmuştur.

Uç Nokta için Defender, bir dizi programlı API aracılığıyla verilerinin ve eylemlerinin büyük bir kısmını kullanıma sunar. Bu API'ler iş akışlarını otomatikleştirmenize ve Uç Nokta için Defender özelliklerine göre yenilik yapmanızı sağlar.

:::image type="content" source="images/mdatp-apis.png" alt-text="Uç Nokta için Microsoft Defender'de kullanılabilir API ve tümleştirme" lightbox="images/mdatp-apis.png":::

Uç Nokta için Defender API'leri üç olarak gruplandırılabilir:

- api'leri Uç Nokta için Microsoft Defender
- Ham veri akışı API'si
- SIEM tümleştirmesi

## <a name="microsoft-defender-for-endpoint-apis"></a>api'leri Uç Nokta için Microsoft Defender

Uç Nokta için Defender, kullanıcılar veya SaaS uygulamaları bağlamında erişime olanak sağlayan standart bir Azure AD tabanlı kimlik doğrulama ve yetkilendirme modeli aracılığıyla kullanıma sunulan yapılandırılmış, net ve kullanımı kolay bir modelde verileri ve özellikleri kullanıma sunan katmanlı bir API modeli sunar. API modeli, varlıkları ve özellikleri tutarlı bir biçimde kullanıma sunma amacıyla tasarlanmıştır.

Uç Nokta için Defender API'lerine hızlı bir genel bakış için bu videoyu izleyin.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

**Araştırma API'si** Uç Nokta için Defender'ın zenginliğini ortaya çıkarır. Hesaplanan veya 'profili oluşturulmuş' varlıkları (örneğin, cihaz, kullanıcı ve dosya) ve genellikle bir varlıkla ilgili davranışı açıklayan ayrık olayları (örneğin, işlem oluşturma ve dosya oluşturma) kullanıma sunar ve verilere sorgu tabanlı erişim sağlayan araştırma arabirimleri aracılığıyla verilere erişim sağlar. Daha fazla bilgi için bkz [. Desteklenen API'ler](exposed-apis-list.md).

**Yanıt API'si**, hizmette ve cihazlarda eylem gerçekleştirme özelliğini kullanıma sunarak müşterilerin cihazları ağdan yalıtma, dosyaları karantinaya alma ve diğer cihazlarda göstergeleri alma, ayarları yönetme, uyarı durumu gibi yanıt eylemlerini program aracılığıyla gerçekleştirmesini sağlar.

## <a name="raw-data-streaming-api"></a>Ham veri akışı API'si

Uç Nokta için Defender ham veri akışı API'si, müşterilerin tek bir veri akışında gerçekleşen gerçek zamanlı olayları ve uyarıları kendi örneklerinden gönderebilmesini sağlayarak düşük gecikme süresi ve yüksek aktarım hızına sahip bir teslim mekanizması sağlar.

Uç Nokta için Defender olay bilgileri, uzun süreli veri saklama veya görselleştirme hizmetleri veya ek veri işleme altyapıları tarafından kullanılmak üzere Azure Event Hubs için doğrudan Azure depolamaya gönderiliyor.

Daha fazla bilgi için bkz [. Ham veri akışı API'si](raw-data-export.md).

Yeni Microsoft 365 Defender Akış API'sinde cihaz olaylarının yanı sıra e-posta ve uyarı olayları da bulunur.
Daha fazla bilgi için bkz[. Microsoft 365 Defender Akış API'si](../defender/streaming-api.md).

## <a name="siem-api"></a>SIEM API

Güvenlik bilgilerini ve olay yönetimi (SIEM) tümleştirmesini etkinleştirdiğinizde, SIEM çözümünüzü kullanarak veya doğrudan algılamalar REST API'sine bağlanarak algılamaları Microsoft 365 Defender çekmenize olanak tanır. Bu, SIEM bağlayıcısı erişim ayrıntıları bölümünü önceden doldurulmuş değerlerle etkinleştirir ve Azure Active Directory (Azure AD) kiracınız altında bir uygulama oluşturulur. 

## <a name="related-topics"></a>İlgili konular

- [Uç Nokta için Microsoft Defender API’lere erişin](apis-intro.md)
- [Desteklenen API'ler](exposed-apis-list.md)
- [Teknik iş ortağı fırsatları](partner-integration.md)
