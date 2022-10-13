---
title: Engellenen gönderen listeleri oluşturma
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
description: Yöneticiler, Exchange Online Protection (EOP) içinde gelen iletileri engellemek için kullanılabilir ve tercih edilen seçenekler hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 6a53c888b1817ca490ce0be71f37080bc3aaa7ac
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68565827"
---
# <a name="create-blocked-sender-lists-in-eop"></a>EOP'de engellenen gönderen listeleri oluşturma

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online posta kutusu olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında EOP, istenmeyen gönderenlerden gelen e-postaları engellemenin birden çok yolunu sunar. Bu seçenekler outlook engellenen gönderenler, engellenen gönderen listeleri veya istenmeyen posta önleme ilkelerindeki engellenen etki alanı listeleri, Exchange posta akışı kuralları (aktarım kuralları olarak da bilinir) ve IP Engelleme Listesi 'ni (bağlantı filtreleme) içerir. Bu seçenekleri toplu olarak _engellenen gönderen listeleri_ olarak düşünebilirsiniz.

Gönderenleri engellemek için en iyi yöntem etki kapsamına göre değişir. Tek bir kullanıcı için doğru çözüm Outlook Engellenen Gönderenler olabilir. Birçok kullanıcı için diğer seçeneklerden biri daha uygun olacaktır. Aşağıdaki seçenekler hem etki kapsamına hem de kapsama göre sıralanır. Liste dardan genişe doğru gider, ancak tam öneriler için _ayrıntıları okuyun_ .

1. Outlook Engellenen Gönderenler (her posta kutusunda depolanan Engellenen Gönderenler listesi)

2. Engellenen gönderen listeleri veya engellenen etki alanı listeleri (istenmeyen posta önleme ilkeleri)

3. Posta akışı kuralları

4. IP Blok Listesi (bağlantı filtreleme)

> [!NOTE]
> Hatalı negatifleri (cevapsız istenmeyen postaları) gidermek için kuruluş genelinde blok ayarlarını kullanabilirsiniz ancak bu iletileri analiz için Microsoft'a da göndermelisiniz. Blok listelerini kullanarak hatalı negatifleri yönetmek, yönetim ek yükünüzü önemli ölçüde artırır. Kaçırılan istenmeyen postaları saptırmak için blok listeleri kullanıyorsanız [İletileri ve dosyaları Microsoft'a bildirme](report-junk-email-messages-to-microsoft.md) konusunu hazır tutmanız gerekir.

Buna karşılık, _güvenilir gönderen listelerini_ kullanarak belirli kaynaklardan gelen e-postalara her zaman izin vermek için çeşitli seçenekleriniz de vardır. Daha fazla bilgi için bkz. [Güvenilir gönderen listeleri oluşturma](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>İletinin temellerini Email

Standart smtp e-posta iletisi, _ileti zarfı ve ileti_ içeriğinden oluşur. İleti zarfı, iletiyi SMTP sunucuları arasında iletmek ve teslim etmek için gereken bilgileri içerir. İleti içeriği, ileti üst bilgisi alanlarını (topluca _ileti üst bilgisi_ olarak adlandırılır) ve ileti gövdesini içerir. İleti zarfı RFC 5321'de ve ileti üst bilgisi RFC 5322'de açıklanmıştır. İleti iletim işlemi tarafından oluşturulduğundan ve iletinin bir parçası olmadığından alıcılar gerçek ileti zarfını asla görmez.

- Adres `5321.MailFrom` ( **POSTA KIMDEN** adresi, P1 gönderen veya zarf gönderen olarak da bilinir), iletinin SMTP iletiminde kullanılan e-posta adresidir. Bu **e-posta** adresi genellikle ileti üst bilgisindeki Dönüş Yolu üst bilgisi alanına kaydedilir (ancak gönderenin farklı bir **Dönüş Yolu e-posta** adresi belirlemesi mümkündür). İleti teslim edilemiyorsa, teslim edilemedi raporunun alıcısıdır (NDR veya geri dönen ileti olarak da bilinir).

- `5322.From` (**Kimden** adresi veya P2 göndereni olarak da bilinir) **Kimden** üst bilgisi alanındaki e-posta adresidir ve gönderenin e-posta istemcilerinde görüntülenen e-posta adresidir.

Ve adresleri sıklıkla `5321.MailFrom` `5322.From` aynıdır (kişiden kişiye iletişim). Ancak, başka biri adına e-posta gönderildiğinde, adresler farklı olabilir.

EOP'deki istenmeyen posta önleme ilkelerinde engellenen gönderen listeleri ve engellenen etki alanı listeleri yalnızca `5322.From` adresleri inceler. Bu davranış, adresi kullanan `5322.From` Outlook Engellenen Gönderenlere benzer.

## <a name="use-outlook-blocked-senders"></a>Outlook Engellenen Gönderenleri kullanma

Yalnızca az sayıda kullanıcı istenmeyen e-posta aldığında, kullanıcılar veya yöneticiler gönderen e-posta adreslerini posta kutusunda Engellenen Gönderenler listesine ekleyebilir. Yönergeler için bkz[. Exchange Online posta kutularında gereksiz e-posta ayarlarını yapılandırma](configure-junk-email-settings-on-exo-mailboxes.md).

bir kullanıcının Engellenen Gönderenler listesi nedeniyle iletiler başarıyla engellendiğinde, **X-Forefront-Antispam-Report** üst bilgi alanı değerini `SFV:BLK`içerir.

> [!NOTE]
> İstenmeyen iletiler saygın ve tanınabilir bir kaynaktan gelen bültenlerse, kullanıcının iletileri almasını durdurmak için e-postadan abonelikten çıkmak da başka bir seçenektir.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Engellenen gönderen listelerini veya engellenen etki alanı listelerini kullanma

Birden çok kullanıcı etkilendiğinde kapsam daha geniştir, bu nedenle bir sonraki en iyi seçenek istenmeyen posta önleme ilkelerinde engellenen gönderen listeleri veya engellenen etki alanı listeleridir. Listelerdeki gönderenlerden gelen iletiler **Yüksek güvenilirlikli istenmeyen posta** olarak işaretlenir ve iletiler üzerinde **Yüksek Güvenilirlikli İstenmeyen Posta** filtresi kararı için yapılandırdığınız eylem oluşturulduğunda. Daha fazla bilgi için bkz. [İstenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md).

Bu listeler için en yüksek sınır yaklaşık 1000 giriştir.

## <a name="use-mail-flow-rules"></a>Posta akışı kurallarını kullanma

Belirli kullanıcılara veya kuruluşun tamamına gönderilen iletileri engellemeniz gerekiyorsa, posta akışı kurallarını kullanabilirsiniz. Posta akışı kuralları, istenmeyen iletilerde anahtar sözcükleri veya diğer özellikleri de arayabildiği için engellenen gönderen listelerinden veya engellenen gönderen etki alanı listelerinden daha esnektir.

İletileri tanımlamak için kullandığınız koşullar veya özel durumlar ne olursa olsun, eylemi iletinin istenmeyen posta güvenilirlik düzeyini (SCL) 9 olarak ayarlayacak şekilde yapılandırabilirsiniz ve bu da iletiyi **Yüksek güvenilirlikli istenmeyen posta** olarak işaretler. Daha fazla bilgi için bkz. [İletilerde SCL'yi ayarlamak için posta akışı kurallarını kullanma](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

> [!IMPORTANT]
> Aşırı _agresif kurallar_ oluşturmak kolaydır, bu nedenle yalnızca engellemek istediğiniz iletileri çok özel ölçütler kullanarak tanımlamanız önemlidir. Ayrıca, her şeyin beklendiği gibi çalıştığından emin olmak için kural üzerinde denetimi etkinleştirdiğinizden ve kuralın sonuçlarını test edin.

## <a name="use-the-ip-block-list"></a>IP Bloğu Listesini Kullanma

Bir göndereni engellemek için diğer seçeneklerden birini kullanmak mümkün olmadığında, _bağlantı_ filtresi ilkesinde IP Engelleme Listesi'ni kullanmanız gerekir. Daha fazla bilgi için bkz [. Bağlantı filtresi ilkesini yapılandırma](configure-the-connection-filter-policy.md). Engellenen IP'lerin sayısını en az düzeyde tutmak önemlidir, bu nedenle IP adresi aralıklarının tamamının engellenmesi _önerilmez._

_Özellikle_ tüketici hizmetlerine (örneğin, outlook.com) veya paylaşılan altyapılara ait IP adresi aralıkları eklemekten kaçınmanız ve ayrıca düzenli bakım kapsamında engellenen IP adreslerinin listesini gözden geçirmeniz gerekir.
