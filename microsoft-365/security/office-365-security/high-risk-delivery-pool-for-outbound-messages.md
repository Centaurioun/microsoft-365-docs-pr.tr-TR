---
title: Giden teslim havuzları
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Microsoft 365 veri merkezlerindeki e-posta sunucularının itibarını korumak için teslim havuzlarının nasıl kullanıldığını öğrenin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 0d56f1cb69134da2d0ebe2594a8507ef7e0f5c37
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598439"
---
# <a name="outbound-delivery-pools"></a>Giden teslim havuzları

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 veri merkezlerindeki Email sunucuları geçici olarak istenmeyen posta göndermekle suçlanabilir. Örneğin, Microsoft 365 aracılığıyla giden posta gönderen veya Microsoft 365 hesaplarını tehlikeye atan bir şirket içi e-posta kuruluşunda kötü amaçlı yazılım veya kötü amaçlı istenmeyen posta saldırısı. Saldırganlar ayrıca iletileri Microsoft 365 iletme aracılığıyla geçirerek algılamayı önlemeye çalışır.

Bu senaryolar, etkilenen Microsoft 365 veri merkezi sunucularının IP adresinin üçüncü taraf blok listelerinde görünmesine neden olabilir. Bu blok listelerini kullanan hedef e-posta kuruluşları, bu Microsoft 365 ileti kaynaklarından gelen e-postaları reddeder.

## <a name="high-risk-delivery-pool"></a>Yüksek riskli teslim havuzu

IP adreslerimizin engellenmesini önlemek için, Microsoft 365 veri merkezi sunucularından gelen ve istenmeyen posta olduğu belirlenen tüm giden iletiler _yüksek riskli teslim havuzu_ üzerinden gönderilir.

Yüksek riskli teslim havuzu, giden e-postalar için yalnızca "düşük kaliteli" iletiler (örneğin, istenmeyen posta ve [geri ölçeklendirici](backscatter-messages-and-eop.md)) göndermek için kullanılan ayrı bir IP adresi havuzudur. Yüksek riskli teslim havuzunun kullanılması, giden e-posta için normal IP adresi havuzunun istenmeyen posta göndermesini önlemeye yardımcı olur. Giden e-posta için normal IP adresi havuzu, "yüksek kaliteli" iletiler gönderen saygınlığı korur ve bu da bu IP adresinin IP blok listelerinde görünme olasılığını azaltır.

Yüksek riskli teslim havuzundaki IP adreslerinin IP blok listelerine yerleştirilme olasılığı hala devam eder, ancak bu tasarım gereğidir. Birçok e-posta kuruluşu yüksek riskli teslim havuzundan gelen iletileri kabul etmediğinden hedeflenen alıcılara teslim garanti edilemez.

Daha fazla bilgi için bkz. [Giden istenmeyen postaları denetleme](outbound-spam-controls.md).

> [!NOTE]
> Kaynak e-posta etki alanının A kaydı olmadığı ve genel DNS'de tanımlanmış MX kaydının olmadığı iletiler, istenmeyen posta veya gönderme sınırı eğilimi ne olursa olsun her zaman yüksek riskli teslim havuzu üzerinden yönlendirilir.
>
> Aşağıdaki sınırları aşan iletiler engellenir, bu nedenle yüksek riskli teslim havuzu üzerinden gönderilmez:
>
> - [Hizmetin gönderme sınırları](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).
> - Gönderenlerin posta göndermesinin kısıtlandığı [giden istenmeyen posta ilkeleri](configure-the-outbound-spam-policy.md).

### <a name="bounce-messages"></a>Geri dönen iletiler

Giden yüksek riskli teslim havuzu, tüm teslim dışı raporlar (NDR'ler, geri dönen iletiler, teslim durumu bildirimleri veya DSN'ler olarak da bilinir) için teslimi yönetir.

NDR'lerde bir dalgalanmanın olası nedenleri şunlardır:

- Hizmeti kullanan müşterilerden birini etkileyen kimlik sahtekarlığına yönelik bir kampanya.
- Dizin toplama saldırısı.
- İstenmeyen posta saldırısı.
- Sahte bir e-posta sunucusu.

Bu sorunların tümü, hizmet tarafından işlenen NDR'lerin sayısında ani bir artışa neden olabilir. Çoğu zaman, bu NDR'ler diğer e-posta sunucularına ve hizmetlerine istenmeyen posta olarak görünür ( _[geri ölçeklendirici](backscatter-messages-and-eop.md)_ olarak da bilinir).

### <a name="relay-pool"></a>Geçiş havuzu

Belirli senaryolarda Microsoft 365 aracılığıyla iletilen veya geçirilen iletiler özel bir geçiş havuzu kullanılarak gönderilir çünkü hedef, Microsoft 365'i gerçek gönderen olarak değerlendirmemelidir. Microsoft 365'in e-postasını otomatik iletme veya aktarmaya yönelik geçerli ve geçersiz senaryolar olduğundan, bu e-posta trafiğini yalıtmak bizim için önemlidir. Yüksek riskli teslim havuzuna benzer şekilde, geçişli posta için ayrı bir IP adresi havuzu kullanılır. Bu adres havuzu, sık sık değişebileceğinden ve Microsoft 365 için yayımlanmış SPF kaydının bir parçası olmadığından yayımlanmaz.

Microsoft 365'in, iletilen iletiyi güvenle teslim edebilmemiz için özgün gönderenin meşru olduğunu doğrulaması gerekir.

İletilen veya geçirilen ileti, geçiş havuzunu kullanmaktan kaçınmak için aşağıdaki ölçütlerden birini karşılamalıdır:

- Giden gönderen [kabul edilen bir etki alanında](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
- İleti Microsoft 365'e geldiğinde SPF geçer.
- gönderen etki alanındaki DKIM, ileti Microsoft 365'e geldiğinde geçer.

Giden sunucu IP'sine bakarak (geçiş havuzu 40.95.0.0/16 aralığında olacak) veya giden sunucu adına bakarak (adında "rly" olacak) geçiş havuzu aracılığıyla bir ileti gönderildiğini anlayabilirsiniz.

Gönderenin kimliğini doğrulayabildiğimiz durumlarda, alıcı e-posta sisteminin iletilen iletinin güvenilir bir kaynaktan geldiğini bilmesine yardımcı olmak için Gönderen Yeniden Yazma Şeması'nı (SRS) kullanırız. Bunun nasıl çalıştığı ve gönderen etki alanının kimlik doğrulamasını [Office 365'daki Gönderen Yeniden Yazma Düzeni'nde (SRS)](/office365/troubleshoot/antispam/sender-rewriting-scheme) geçtiğinden emin olmak için yapabilecekleriniz hakkında daha fazla bilgi edinebilirsiniz.

DKIM'in çalışması için etki alanı göndermek için DKIM'i etkinleştirdiğinizden emin olun. Örneğin, fabrikam.com contoso.com bir parçasıdır ve kuruluşun kabul edilen etki alanlarında tanımlanır. İletiyi gönderen sender@fabrikam.com ise DKIM'in fabrikam.com için etkinleştirilmesi gerekir. [özel etki alanınızdan gönderilen giden e-postayı doğrulamak için DKIM kullanma](use-dkim-to-validate-outbound-email.md) sayfasında etkinleştirmeyi okuyabilirsiniz.

Özel etki alanları eklemek için [Microsoft 365'e etki alanı ekleme](../../admin/setup/add-domain.md) başlığındaki adımları izleyin.

Etki alanınızın MX kaydı üçüncü taraf bir hizmete veya şirket içi e-posta sunucusuna işaret ediyorsa [Bağlayıcılar için Gelişmiş Filtreleme'yi](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) kullanmanız gerekir. Gelişmiş Filtreleme, gelen postalar için SPF doğrulamasının doğru olmasını sağlar ve geçiş havuzu üzerinden e-posta gönderilmesini önler.
