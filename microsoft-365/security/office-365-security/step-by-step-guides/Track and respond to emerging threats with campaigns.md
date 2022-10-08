---
title: Office 365 için Microsoft Defender'da kampanyalar görünümüyle yeni ortaya çıkan güvenlik tehditlerini izleme ve yanıtlama
description: Kuruluşunuza yönelik eşgüdümlü bir e-posta saldırısını araştırmak için nasıl kullanılabileceğini göstermek için Office 365 için Microsoft Defender içindeki tehdit kampanyalarının kılavuzu.
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 32571de4b4eaf5302d14842cda727ddc7850a6d1
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67876641"
---
# <a name="track-and-respond-to-emerging-threats-with-campaigns-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'daki kampanyalarla ortaya çıkan tehditleri izleme ve yanıtlama

Kampanyalar, kuruluşunuza yönelik eşgüdümlü bir e-posta saldırısını araştırmanıza olanak sağladığından, yeni ortaya çıkan tehditleri izlemek ve yanıtlamak için kullanılabilir. Yeni tehditler kuruluşunuzu hedefledikçe, Office 365 için Microsoft Defender kötü amaçlı iletileri otomatik olarak algılar ve ilişkilendirer. 

## <a name="what-you-will-need"></a>İhtiyacınız olan şey
- Office 365 için Microsoft Defender Plan 2 (E5 planlarında bulunur).
- Yeterli izinler (Güvenlik Okuyucusu rolü).
- Bu adımları gerçekleştirmek için beş-on dakika.

## <a name="what-is-a-campaign-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'da kampanya nedir?

Kampanya, bir veya birden çok kuruluşa yönelik eşgüdümlü bir e-posta saldırısıdır. Kimlik bilgilerini ve şirket verilerini çalan Email saldırıları büyük ve kazançlı bir endüstridir. Saldırıları durduran teknolojiler arttıkça ve çoğaldıkça, saldırganlar başarılarını sürdürmek için yöntemlerini değiştirir.

Microsoft, kampanyaların tanımlanmasına yardımcı olmak için tüm hizmet genelinde çok miktarda kimlik avı, istenmeyen posta önleme ve kötü amaçlı yazılımdan koruma verilerinden yararlanıyor. Saldırı bilgilerini çeşitli faktörlere göre analiz edip sınıflandırırız, örneğin:

- **Saldırı kaynağı**: Kaynak IP adresleri ve gönderen e-posta etki alanları.
- **İleti özellikleri**: İletilerin içeriği, stili ve tonu.
- **İleti alıcıları**: Alıcı etki alanları, alıcı iş işlevleri (yöneticiler ve yöneticiler gibi), şirket türleri (büyük, küçük, genel ve özel gibi) ve sektörler gibi alıcıların ilişkisi.
- **Saldırı yükü**: İletilerdeki kötü amaçlı bağlantılar, ekler veya diğer yükler.

Kampanya kısa süreli olabileceği gibi, etkin ve etkin olmayan dönemlerle birkaç gün, hafta veya aya yayılabilir. Belirli bir kuruluşunuzda bir kampanya başlatılabilir veya kuruluşunuz *birden çok* şirket arasında daha büyük bir kampanyanın parçası olabilir.

> [!TIP]
> Bir kampanyadaki veriler hakkında daha fazla bilgi edinmek için [Office 365 için Microsoft Defender'da Kampanya Görünümleri'ni](/microsoft-365/security/office-365-security/campaigns) okuyun.

## <a name="watch-the-exploring-campaign-views-video"></a>*Kampanya görüntülemelerini keşfetme videosunu* izleyin

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGBL8]

## <a name="investigating-a-suspicious-email-campaign-using-threat-reports"></a>Tehdit raporlarını kullanarak şüpheli bir e-posta kampanyasını araştırma

Bir kampanyanın kuruluşunuzu hedef aldığı ve etki hakkında daha fazla bilgi edinmek istediğiniz durumlarda: 
1. [Kampanya sayfasına](https://security.microsoft.com/campaigns) gidin.
1. Araştırmak istediğiniz kampanya adını seçin. 
1. Açılır öğe açıldığında **Tehdit raporunu indir'i** seçin.
1. Tehdit raporunu açtığınızda kampanyayla ilgili daha fazla bilgi sağlanır. Rapordaki bilgiler şunları içerir: 
- **Yönetici özeti:** Kampanya türünün ve kuruluşunuzda hedeflenen kullanıcı sayısının üst düzey özeti. 
- **Analysis:** Kampanyanın ne zaman başladığını, kuruluşunuzu hedefleyen iletilerin sayısını ve iletilerin hedefini ve kararlarını açıklayan zaman çizelgesi grafiği. 
- **Saldırı kaynağı:** Kuruluşunuzdaki gelen kutularına teslim edilen iletilerin sayısıyla en çok gönderen IP adresleri ve etki alanları. Bu, kuruluşunuzu hedef alan kişiyi araştırmanıza olanak tanır. 
- **Email şablonu ve yükü:** Kampanyanın parçası olan e-postaların konu satırı ve URL'ler (ve sıklıkları) kampanyanın bir parçası olarak bulunur.
- **Öneri:** İletileri düzeltmeye yönelik sonraki adımlara yönelik öneriler.

## <a name="investigate-inboxed-messages-that-are-part-of-a-email-threat-campaign"></a>E-posta tehdit kampanyasının parçası olan gelen kutusuna alınan iletileri araştırma

1. [Kampanya sayfasına](https://security.microsoft.com/campaigns) gidin.
1. **Ayrıntılar görünümünde**, grafiğin altındaki kampanya listesini kaydırın.
1. Araştırmak istediğiniz kampanya adını seçin. Kampanyanın tıklama sayısı sıfırdan fazlaysa, bu durum kuruluşunuzdaki bir kullanıcının bir URL'ye tıkladığını veya e-postadan bir dosya indirdiğini gösterir.
1. Kampanya açılır öğesi kampanya hakkında daha fazla bilgi görüntüler, grafik kampanyanın başlangıç tarihinden bitiş tarihine kadar olan zaman çizelgesini görüntüler ve yatay akış diyagramında kampanyanın kaynağından, kararından ve iletilerin geçerli konumundan itibaren aşamaları görüntülenir.
1. Akış diyagramının altında, tıklamayla ilgili bilgileri görüntülemek için **URL tıklamaları** sekmesini seçin. Burada, bir URL'ye tıklayan kullanıcıyı, kullanıcı öncelikli hesap kullanıcısı olarak etiketlenmişse, URL'nin kendisini ve tıklama zamanını görebilirsiniz. 
1. Gelen kutusuna alınan ve tıklanan iletiler hakkında daha fazla bilgi edinmek istiyorsanız **İletileri** >  araştır **Gelen kutusuna alınan iletiler'i** seçin. Yeni bir sekme açılır ve Tehdit Gezgini'ne gider. 
1. Gezgin'in **ayrıntılar görünümünde** , bir iletinin hala gelen kutusunda olup olmadığını veya sistem ZAP tarafından karantinaya alınıp alınmadığını belirlemek için **En son teslime** başvurabilirsiniz. _Belirli ileti hakkında daha fazla ayrıntı almak için iletiyi seçin. Açılır öğe ek bilgi sağlar. Açılır listenin sol üst kısmındaki **E-posta varlığını aç sayfası** seçildiğinde yeni bir sekme açılır ve ileti hakkında daha fazla bilgi verir._
1.  Bir eylem gerçekleştirmek ve iletileri gelen kutusundan taşımak isterseniz, iletiyi ve ardından **İleti eylemleri** > **Gereksiz klasöre taşı'yı** seçebilirsiniz. Bu, kullanıcınızın olası bir ihlale neden olabilecek kötü amaçlı iletiyle etkileşime devam etmemesini sağlar. 

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi edinmek için [Office 365 için Microsoft Defender'da Kampanya Görünümleri'ne](/microsoft-365/security/office-365-security/campaigns) bakın.
