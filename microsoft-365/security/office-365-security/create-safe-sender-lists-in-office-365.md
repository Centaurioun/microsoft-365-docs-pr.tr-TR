---
title: Güvenilir gönderen listeleri oluşturma
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.collection: m365-security
ms.localizationpriority: medium
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, Exchange Online Protection (EOP) içinde gelen iletilere izin vermek için kullanılabilir ve tercih edilen seçenekler hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 65520a890be1e7c8e529496b7fb78005139bde9d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68645197"
---
# <a name="create-safe-sender-lists-in-eop"></a>EOP'de güvenilir gönderen listeleri oluşturma

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online posta kutuları olan bir Microsoft 365 müşterisiyseniz veya Exchange Online posta kutusu olmayan tek başına Exchange Online Protection (EOP) müşterisiyseniz, EOP kullanıcıların güvenilir gönderenlerden e-posta almasını sağlamanın çeşitli yollarını sunar. Toplu olarak, bu seçenekleri _güvenilir gönderen listeleri_ olarak düşünebilirsiniz.

Kullanılabilir güvenilir gönderen listeleri, en çok önerilenden en az önerilene kadar aşağıdaki listede açıklanmıştır:

1. Kiracı İzin Ver/Engelle Listesi'nde etki alanları ve e-posta adresleri (sahte gönderenler dahil) için girişlere izin verin.
2. Posta akışı kuralları (taşıma kuralları olarak da bilinir).
3. Outlook Güvenilir Gönderenler (her posta kutusunda depolanan Güvenilir Gönderenler listesi).
4. IP İzin Ver Listesi (bağlantı filtreleme)
5. İzin verilen gönderen listeleri veya izin verilen etki alanı listeleri (istenmeyen posta önleme ilkeleri)

Bu makalenin geri kalanında her yöntemle ilgili ayrıntılar yer alır.

> [!IMPORTANT]
> Kötü amaçlı yazılım veya yüksek güvenilirlikli kimlik avı olarak tanımlanan iletiler, kullandığınız güvenilir gönderen listesi seçeneğine bakılmaksızın her zaman karantinaya alınır. Daha fazla bilgi için bkz[. Office 365'de varsayılan olarak güvenlidir](secure-by-default.md).
>
> Güvenilir gönderen listelerini kullanarak istenmeyen posta filtrelemesinde _yaptığınız özel durumları_ yakından izlemeye dikkat edin.
>
> Her zaman güvenilir gönderen listelerinizdeki iletileri analiz için Microsoft'a gönderin. Yönergeler için bkz. [Microsoft'a iyi e-posta bildirme](admin-submission.md#report-good-email-to-microsoft). İletilerin veya ileti kaynaklarının zararsız olduğu belirlenirse, Microsoft iletilere otomatik olarak izin verebilir ve girişi güvenli gönderen listelerinde el ile tutmanız gerekmez.
>
> E-postaya izin vermek yerine, _engellenen gönderen listelerini_ kullanarak belirli kaynaklardan gelen e-postaları engellemek için çeşitli seçenekleriniz de vardır. Daha fazla bilgi için bkz. [EOP'de engelleyici gönderen listeleri oluşturma](create-block-sender-lists-in-office-365.md).

## <a name="use-allow-entries-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinde izin ver girdilerini kullanma

Gönderenlerden veya etki alanlarından gelen postalara izin vermek için önerilen bir numaralı seçenek Kiracı İzin Ver/Engelle Listesi'dir. Yönergeler için bkz. [Kiracı İzin Verme/Engelleme Listesi'ni kullanarak e-postaya izin verme veya engelleme](allow-block-email-spoof.md).

Yalnızca Kiracı İzin Ver/Engelle Listesi'ni bir nedenle kullanamıyorsanız gönderenlere izin vermek için farklı bir yöntem kullanmayı düşünmelisiniz.

## <a name="use-mail-flow-rules"></a>Posta akışı kurallarını kullanma

> [!NOTE]
> bir iç göndereni güvenilir gönderen olarak belirtmek için ileti üst bilgilerini ve posta akışı kurallarını kullanamazsınız. Bu bölümdeki yordamlar yalnızca dış gönderenler için geçerlidir.

Exchange Online ve tek başına EOP'deki posta akışı kuralları, iletileri tanımlamak için koşulları ve özel durumları ve bu iletilere ne yapılması gerektiğini belirten eylemleri kullanır. Daha fazla bilgi için bkz. [Exchange Online'de Posta akışı kuralları (aktarım kuralları).](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

Aşağıdaki örnekte, istenmeyen posta filtrelemeyi atlamak için contoso.com e-postasına ihtiyacınız olduğu varsayılır. Bunu yapmak için aşağıdaki ayarları yapılandırın:

1. **Koşul**: **Gönderen** \> **etki alanı** \> contoso.com.

2. Aşağıdaki ayarlardan birini yapılandırın:

   - **Posta akışı kuralı koşulu**: **İleti üst bilgisi** \> **şu sözcüklerden** \> herhangi birini içerir **Üst bilgi adı**: `Authentication-Results` \> **Üst bilgi değeri**: `dmarc=pass` veya `dmarc=bestguesspass`.

     Bu koşul, gönderen etki alanının sahte olmadığından emin olmak için gönderen e-posta etki alanının e-posta kimlik doğrulama durumunu denetler. E-posta kimlik doğrulaması hakkında daha fazla bilgi için bkz. [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md) ve [DMARC](use-dmarc-to-validate-email.md).

   - **IP İzin Verme Listesi**: Bağlantı filtresi ilkesinde kaynak IP adresini veya adres aralığını belirtin. Yönergeler için bkz. [Bağlantı filtrelemeyi yapılandırma](configure-the-connection-filter-policy.md).

     Gönderen etki alanı e-posta kimlik doğrulaması kullanmıyorsa bu ayarı kullanın. IP İzin Ver Listesindeki kaynak IP adresleri söz konusu olduğunda mümkün olduğunca kısıtlayıcı olun. /24 veya daha az BIR IP adresi aralığı öneririz (daha azı daha iyidir). Tüketici hizmetlerine (örneğin, outlook.com) veya paylaşılan altyapılara ait IP adresi aralıklarını kullanmayın.

   > [!IMPORTANT]
   >
   > - İstenmeyen posta filtrelemeyi atlamak için koşul olarak posta akışı kurallarını _hiçbir zaman yalnızca_ gönderen etki alanıyla yapılandırmayın. Bunun yapılması, saldırganların gönderen etki alanını taklit etme (veya tam e-posta adresinin kimliğine bürünme), tüm istenmeyen posta filtrelemesini atlama ve iletinin alıcının Gelen Kutusu'na ulaşması için gönderen kimlik doğrulama denetimlerini atlama olasılığını _önemli ölçüde_ artırır.
   >
   > - Sahip olduğunuz etki alanlarını (kabul edilen etki alanları olarak da bilinir) veya popüler etki alanlarını (örneğin, microsoft.com) posta akışı kurallarında koşul olarak kullanmayın. Bunu yapmak, saldırganların başka türlü filtrelenecek e-posta gönderme fırsatları oluşturması nedeniyle yüksek risk olarak kabul edilir.
   >
   > - Ağ adresi çevirisi (NAT) ağ geçidinin arkasındaki bir IP adresine izin verirseniz, IP İzin Verme Listenizin kapsamını bilmek için NAT havuzuna dahil olan sunucuları bilmeniz gerekir. IP adresleri ve NAT katılımcıları değişebilir. Standart bakım yordamlarınızın bir parçası olarak IP İzin Ver Listesi girdilerinizi düzenli aralıklarla denetlemeniz gerekir.

3. **İsteğe bağlı koşullar**:

   - **Gönderen** \> **iç/dış** \> **Kuruluş dışında**: Bu koşul örtülüdür, ancak doğru yapılandırılmamış olabilecek şirket içi e-posta sunucularını hesaba eklemek için bu koşulu kullanabilirsiniz.
   - **Konu veya gövde** \> **konu veya gövde bu sözcüklerden** \> herhangi birini içerir \<keywords\>: İletileri konu satırında veya ileti gövdesinde anahtar sözcüklere veya tümceciklere göre daha fazla kısıtlayabilirseniz, bu sözcükleri bir koşul olarak kullanabilirsiniz.

4. **Eylem**: Kuralda bu eylemlerin ikisini de yapılandırın:

   1. **İleti özelliklerini** \> değiştirme **istenmeyen posta güvenilirlik düzeyini (SCL)** \> ayarlama **İstenmeyen posta filtrelemeyi atla**.
   2. **İleti özelliklerini** \> değiştirme **ileti üst bilgisi ayarlama**: **İleti üst bilgisini** \<CustomHeaderName\> **değerine** \<CustomHeaderValue\>ayarlayın.

      Örneğin, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Kuralda birden fazla etki alanınız varsa, üst bilgi metnini uygun şekilde özelleştirebilirsiniz.

      Bir ileti posta akışı kuralı nedeniyle istenmeyen posta filtrelemeyi atladığında, değer `SFV:SKN` değeri **X-Forefront-Antispam-Report** üst bilgisinde damgalanır. İleti IP İzin Verme Listesi'nde bulunan bir kaynaktan geliyorsa, değer `IPV:CAL` de eklenir. Bu değerler sorun giderme konusunda size yardımcı olabilir.

      :::image type="content" source="../../media/1-AllowList-SkipFilteringFromContoso.png" alt-text="İstenmeyen posta filtrelemesini atlamak için EAC'deki Posta akışı kuralı ayarları" lightbox="../../media/1-AllowList-SkipFilteringFromContoso.png":::

## <a name="use-outlook-safe-senders"></a>Outlook Güvenilir Gönderenlerini kullanma

> [!CAUTION]
> Bu yöntem, saldırganların Gelen Kutusu'na e-postayı başarıyla teslim etme riski oluşturur ve aksi takdirde filtrelenebilir; Ancak, kullanıcının Güvenilir Gönderenler veya Güvenli Etki Alanları listelerindeki bir girdiden gelen bir iletinin kötü amaçlı yazılım veya yüksek güvenilirlikli kimlik avı olduğu belirlenirse, ileti filtrelenir.

Kuruluş ayarı yerine, kullanıcılar veya yöneticiler gönderen e-posta adreslerini posta kutusunda Güvenilir Gönderenler listesine ekleyebilir. Yönergeler için bkz[. Office 365 Exchange Online posta kutularında gereksiz e-posta ayarlarını yapılandırma](configure-junk-email-settings-on-exo-mailboxes.md).

Gönderenler filtreleme yığınının bölümlerini atlayacağı için çoğu durumda bu yöntem tercih edilmez. Gönderene güvenseniz de, gönderenin güvenliği tehlikeye girebilir ve kötü amaçlı içerik gönderebilir. Filtrelerimizin her iletiyi denetlemesine izin vermeli ve yanlış [pozitif/negatifi yanlış aldıysak Microsoft'a bildirmelisiniz](report-junk-email-messages-to-microsoft.md) . Filtreleme yığınının atlanması da [sıfır saatlik otomatik temizlemeyi (ZAP)](zero-hour-auto-purge.md) engeller.

Tasarım gereği ve Exchange Online posta kutularının daha fazla güvenliği için, yalnızca güvenilir gönderenler, engellenen gönderenler ve engellenen etki alanları için gereksiz e-posta ayarları tanınır. Güvenli posta listesi ayarları yoksayılır.

**Not**: Exchange Online'de, Outlook Güvenilir Gönderenler listesindeki veya TrustedSendersAndDomains parametresindeki etki alanı girişleri tanınmaz, bu nedenle yalnızca e-posta adreslerini kullanın.

İletiler, kullanıcının Güvenilir Gönderenler listesinden dolayı istenmeyen posta filtrelemeyi atladığında, **X-Forefront-Antispam-Report** üst bilgi alanı, istenmeyen posta, kimlik sahtekarlığı ve kimlik avı filtrelemesinin atlandığını gösteren değerini `SFV:SFE`içerir.

## <a name="use-the-ip-allow-list"></a>IP İzin Ver Listesini Kullanma

> [!CAUTION]
> Posta akışı kuralları gibi ek doğrulama olmadan, IP İzin Ver Listesindeki kaynaklardan gelen e-postalar istenmeyen posta filtreleme ve gönderen kimlik doğrulaması (SPF, DKIM, DMARC) denetimlerini atlar. Bu sonuç, saldırganların Gelen Kutusu'na e-postayı başarıyla teslim etme riski oluşturur ve aksi takdirde filtrelenebilir; ancak, IP İzin Ver Listesindeki bir girdiden gelen bir iletinin kötü amaçlı yazılım veya yüksek güvenilirlikli kimlik avı olduğu belirlenirse, ileti filtrelenir.

Bir sonraki en iyi seçenek, kaynak e-posta sunucusunu veya sunucuları bağlantı filtresi ilkesindeki IP İzin Verme Listesi'ne eklemektir. Ayrıntılar için bkz [. EOP'de bağlantı filtrelemeyi yapılandırma](configure-the-connection-filter-policy.md).

**Notlar**:

- İzin verilen IP adreslerinin sayısını en az düzeyde tutmanız önemlidir, bu nedenle mümkün olduğunda tüm IP adresi aralıklarını kullanmaktan kaçının.
- Tüketici hizmetlerine (örneğin, outlook.com) veya paylaşılan altyapılara ait IP adresi aralıklarını kullanmayın.
- IP İzin Ver Listesindeki girdileri düzenli olarak gözden geçirin ve artık ihtiyacınız olmayan girdileri kaldırın.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>İzin verilen gönderen listelerini veya izin verilen etki alanı listelerini kullanma

> [!CAUTION]
>
> Bu yöntem, saldırganların Gelen Kutusu'na e-postayı başarıyla teslim etme riski oluşturur ve aksi takdirde filtrelenebilir; ancak, izin verilen gönderenler veya izin verilen etki alanları listelerindeki bir girdiden gelen bir iletinin kötü amaçlı yazılım veya yüksek güvenilirlikli kimlik avı olduğu belirlenirse, ileti filtrelenir.
>
> İzin verilen etki alanı listelerinde sahip olduğunuz etki alanlarını (kabul edilen etki alanları olarak da bilinir) veya popüler etki alanlarını (örneğin, microsoft.com) kullanmayın.

İstenmeyen en az seçenek, istenmeyen posta önleme ilkelerinde izin verilen gönderen listesini veya izin verilen etki alanı listesini kullanmaktır. Gönderenler tüm istenmeyen posta, kimlik sahtekarlığı, kimlik avı koruması (yüksek güvenilirlikli kimlik avı hariç) ve gönderen kimlik doğrulamasını (SPF, DKIM, DMARC) atladığından _mümkünse_ bu seçenekten kaçınmalısınız. Bu yöntem yalnızca geçici test için en iyi şekilde kullanılır. Ayrıntılı adımlar [EOP'de istenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md) konusunda bulunabilir.

Bu listeler için en yüksek sınır yaklaşık 1000 giriştir; ancak portala yalnızca 30 giriş girebilirsiniz. 30'dan fazla girdi eklemek için PowerShell'i kullanmanız gerekir.

## <a name="considerations-for-bulk-email"></a>Toplu e-posta ile ilgili dikkat edilmesi gerekenler

Standart smtp e-posta iletisi, _ileti zarfı ve ileti_ içeriğinden oluşur. İleti zarfı, iletiyi SMTP sunucuları arasında iletmek ve teslim etmek için gereken bilgileri içerir. İleti içeriği, ileti üst bilgisi alanlarını (topluca _ileti üst bilgisi_ olarak adlandırılır) ve ileti gövdesini içerir. İleti zarfı RFC 5321'de ve ileti üst bilgisi RFC 5322'de açıklanmıştır. İleti iletim işlemi tarafından oluşturulduğundan ve iletinin bir parçası olmadığından alıcılar gerçek ileti zarfını asla görmez.

- Adres `5321.MailFrom` ( **POSTA KIMDEN** adresi, P1 gönderen veya zarf gönderen olarak da bilinir), iletinin SMTP iletiminde kullanılan e-posta adresidir. Bu **e-posta** adresi genellikle ileti üst bilgisindeki Dönüş Yolu üst bilgisi alanına kaydedilir (ancak gönderenin farklı bir **Dönüş Yolu e-posta** adresi belirlemesi mümkündür). İleti teslim edilemiyorsa, teslim edilemedi raporunun alıcısıdır (NDR veya geri dönen ileti olarak da bilinir).
- `5322.From` (**Kimden** adresi veya P2 göndereni olarak da bilinir) **Kimden** üst bilgisi alanındaki e-posta adresidir ve gönderenin e-posta istemcilerinde görüntülenen e-posta adresidir.

Ve adresleri sıklıkla `5321.MailFrom` `5322.From` aynıdır (kişiden kişiye iletişim). Ancak, başka biri adına e-posta gönderildiğinde, adresler farklı olabilir. Bu durum en sık toplu e-posta iletileri için gerçekleşir.

Örneğin, Blue Yonder Airlines'ın reklam e-posta iletileri göndermek için Margie'nin Seyahat'ini kiraladığını varsayalım. Gelen Kutunuzda aldığınız ileti aşağıdaki özelliklere sahiptir:

- Adres `5321.MailFrom` blueyonder.airlines@margiestravel.com.
- Adres `5322.From` blueyonder@news.blueyonderairlines.com, Outlook'ta göreceğiniz adrestir.

EOP'deki istenmeyen posta önleme ilkelerindeki güvenilir gönderen listeleri ve güvenli etki alanı listeleri yalnızca `5322.From` adresleri inceler. Bu davranış, adresi kullanan Outlook Güvenilir Gönderenleri'ne `5322.From` benzer.

Bu iletinin filtrelenmesini önlemek için aşağıdaki adımları uygulayabilirsiniz:

- blueyonder@news.blueyonderairlines.com ( `5322.From` adres) Outlook Güvenilir Göndereni olarak ekleyin.
- blueyonder@news.blueyonderairlines.com (adres), blueyonder.airlines@margiestravel.com (`5322.From`adres) veya her ikisinden gelen iletilerin aranması koşuluyla `5321.MailFrom` bir [posta akışı kuralı kullanın](#use-mail-flow-rules).
