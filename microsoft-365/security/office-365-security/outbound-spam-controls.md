---
title: Giden istenmeyen posta koruması
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, Exchange Online Protection(EOP) içindeki giden istenmeyen posta denetimleri hakkında bilgi edinebilir ve toplu posta göndermeniz gerekirse ne yapmanız gerektiğini öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 76e9e11d0b49237ff3a29dcb9eadf113f9db112e
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598329"
---
# <a name="outbound-spam-protection-in-eop"></a>EOP'de giden istenmeyen posta koruması

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

posta kutuları olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları Exchange Online olan Microsoft 365 kuruluşlarında, giden istenmeyen postaların yönetilmesini ciddiye alıyoruz. Bir müşteri bilerek veya istemeden kuruluşundan istenmeyen posta gönderse bile, bu eylem tüm hizmetin itibarını düşürebilir ve diğer müşteriler için e-posta teslimini etkileyebilir.

Bu makalede, giden istenmeyen postaları önlemeye yardımcı olmak için tasarlanan denetimler ve bildirimler ve toplu posta göndermeniz gerektiğinde neler yapabileceğiniz açıklanmaktadır.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Yöneticilerin giden istenmeyen postaları denetlemek için yapabilecekleri

- **Yerleşik bildirimleri kullanma**: Bir kullanıcı [hizmet](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) veya [giden istenmeyen posta ilkelerinin](configure-the-outbound-spam-policy.md) gönderme sınırlarını aştığında ve e-posta göndermesi kısıtlandığında, **Kullanıcı'nın e-posta göndermesi kısıtlandı** adlı varsayılan uyarı ilkesi **TenantAdmins** (**Genel yöneticiler**) grubunun üyelerine e-posta bildirimleri gönderir. Bu bildirimleri başka kimlerin alacağını yapılandırmak için bkz. [Kısıtlı kullanıcılar için uyarı ayarlarını doğrulama](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Ayrıca, **Email gönderme sınırı aşıldı** ve **Şüpheli e-posta gönderme düzenleri algılandı** adlı varsayılan uyarı ilkeleri **TenantAdmins** (**Genel yöneticiler**) grubunun üyelerine e-posta bildirimleri gönderir. Uyarı ilkeleri hakkında daha fazla bilgi için bkz. [Microsoft 365'te uyarı ilkeleri](../../compliance/alert-policies.md).

- **Üçüncü taraf e-posta sağlayıcılarından gelen istenmeyen posta şikayetlerini gözden geçirin**: Outlook.com, Yahoo ve AOL gibi birçok e-posta hizmeti, hizmetinde herhangi bir kullanıcının Microsoft 365'ten gelen bir e-postayı istenmeyen posta olarak işaretlemesi durumunda iletinin paketlendiği ve gözden geçirilmek üzere bize geri gönderildiği bir geri bildirim döngüsü sağlar. Outlook.com gönderen desteği hakkında daha fazla bilgi edinmek için adresine <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>gidin.

## <a name="how-eop-controls-outbound-spam"></a>EOP giden istenmeyen postaları nasıl denetler?

- **Giden e-posta trafiğinin ayrılması**: Hizmet aracılığıyla gönderilen her giden ileti istenmeyen posta için taranır. İletinin istenmeyen posta olduğu belirlenirse, _yüksek riskli teslim havuzu_ adlı ikincil, daha az saygın bir IP adresi havuzundan teslim edilir. Daha fazla bilgi için bkz. [Giden iletiler için yüksek riskli teslim havuzu](high-risk-delivery-pool-for-outbound-messages.md).

- **Kaynak IP adresi itibarımızı izleme**: Microsoft 365 çeşitli üçüncü taraf IP blok listelerini sorgular. Giden e-posta için kullandığımız IP adreslerinden herhangi biri bu listelerde görünüyorsa bir uyarı oluşturulur. Bu izleme, istenmeyen posta ünümüzün düşmesine neden olduğunda hızlı bir şekilde tepki vermemizi sağlar. Bir uyarı oluşturulduğunda IP adreslerimizin blok listelerinden nasıl kaldırılacağını (listeden çıkarıldığını) açıklayan iç belgelerimiz vardır.

- **Çok fazla istenmeyen posta gönderen hesapları devre dışı bırakın**: Giden istenmeyen postaları yüksek riskli teslim havuzuna ayırmamıza rağmen, bir hesabın (genellikle güvenliği aşılmış bir hesap) süresiz olarak istenmeyen posta göndermesine izin veremiyoruz.<sup>\*</sup> İstenmeyen posta gönderen hesapları izliyoruz ve açıklanmayan bir sınırı aştığında hesabın e-posta göndermesi engelleniyor. Tek tek kullanıcılar ve kiracının tamamı için farklı eşikler vardır.

- **Çok hızlı bir şekilde çok fazla e-posta gönderen hesapları devre dışı bırakma**: İstenmeyen posta olarak işaretlenen iletilerin aranma sınırlarına ek olarak, giden iletilerdeki istenmeyen posta filtreleme kararı ne olursa olsun, genel bir giden ileti sınırına ulaştıklarında hesapları engelleyen sınırlar da vardır.<sup>\*</sup> Güvenliği aşılmış bir hesap, istenmeyen posta filtresi tarafından kaçırılan sıfır gün (önceden tanınmayan) istenmeyen postalar gönderebilir. Yasal bir toplu posta kampanyasını ve istenmeyen posta kampanyasını tanımlamak zor olabileceğinden, bu sınırlar olası zararları en aza indirmeye yardımcı olur.

<sup>\*</sup> Tam sınırların reklamını yapmadığımız için istenmeyen posta gönderenler sisteme oyun yapamaz ve bu nedenle sınırları gerektiği gibi artırabilir veya azaltabiliriz. Limitler, ortalama bir işletme kullanıcısının bunları aşmasını engelleyecek kadar yüksek ve istenmeyen posta gönderenin neden olduğu hasarı kapsamaya yardımcı olacak kadar düşüktür.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>EOP aracılığıyla toplu posta göndermek isteyen müşteriler için öneriler

Çok büyük miktarda e-posta göndermek isteyen müşteriler ile hizmeti güvenliği aşılmış hesaplardan ve kötü alıcı alma uygulamalarıyla toplu e-posta gönderenlerden korumak arasında denge oluşturmak zordur. Üçüncü taraf IP bloğu listesine microsoft 365 e-posta kaynağı girişinin maliyeti, çok fazla e-posta gönderen bir kullanıcıyı engellemekten daha yüksektir.

[Exchange Online Hizmet Açıklaması'nda](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits) açıklandığı gibi, toplu e-posta göndermek için EOP kullanmak hizmetin desteklenen bir kullanımı değildir ve yalnızca "en iyi çaba" temelinde izin verilir. Toplu e-posta göndermek isteyen müşteriler için aşağıdaki çözümleri öneririz:

- **Şirket içi e-posta sunucuları aracılığıyla toplu e-posta gönderme**: Müşteriler toplu postalar için kendi e-posta altyapılarını korur.

- **Üçüncü taraf toplu e-posta sağlayıcısı kullanma**: Toplu posta göndermek için kullanabileceğiniz birkaç üçüncü taraf toplu e-posta çözümü sağlayıcısı vardır. Bu şirketler, iyi e-posta gönderme uygulamalarından emin olmak için müşterilerle çalışmaya çok ilgi gösteriyor.

Mesajlaşma, Mobil, Kötü Amaçlı Yazılımdan Koruma Çalışma Grubu (MAAWG), adresinde üyelik listesini <https://www.maawg.org/about/roster>yayımlar. Listede birçok toplu e-posta sağlayıcısı vardır ve internet vatandaşlarının sorumlu olduğu bilinmektedir.
