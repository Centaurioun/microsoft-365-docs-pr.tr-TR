---
title: Önemsiz e-posta ile toplu e-posta arasındaki fark nedir?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Yöneticiler, Exchange Online Protection (EOP) içindeki gereksiz e-posta (istenmeyen posta) ile toplu e-posta (gri posta) arasındaki farklar hakkında bilgi edinebilir.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5117954e668c4e64444628078f38dab61b0597cb
ms.sourcegitcommit: 031b3e963478f642a0d23be37a01f23a01cb3d84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2022
ms.locfileid: "67441799"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP'de gereksiz e-posta ile toplu e-posta arasındaki fark nedir?

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

posta kutuları Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları Exchange Online olmayan Microsoft 365 kuruluşlarında müşteriler bazen şunu sorar: "Gereksiz e-posta ile toplu e-posta arasındaki fark nedir?" Bu konu, farkı açıklar ve EOP'de kullanılabilen denetimleri açıklar.

- **Gereksiz e-posta** istenmeyen ve evrensel olarak istenmeyen iletiler olan istenmeyen postadır (doğru tanımlandığında). Varsayılan olarak, EOP kaynak e-posta sunucusunun itibarına bağlı olarak istenmeyen postaları reddeder. Bir ileti kaynak IP incelemesini geçerse istenmeyen posta filtrelemeye gönderilir. İleti istenmeyen posta filtreleme ile istenmeyen posta olarak sınıflandırılırsa, ileti (varsayılan olarak) hedeflenen alıcılara teslim edilir ve Gereksiz Email klasörüne taşınır.

  - İstenmeyen posta filtreleme kararlarında gerçekleştirebileceğiniz eylemleri yapılandırabilirsiniz. Yönergeler için bkz. [EOP'de istenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md).

  - İstenmeyen posta filtreleme kararına katılmıyorsanız, iletileri ve dosyaları Microsoft'a bildirme bölümünde açıklandığı gibi, istenmeyen posta veya istenmeyen posta olmadığını düşündüğünüz [iletileri çeşitli yollarla Microsoft'a](report-junk-email-messages-to-microsoft.md) bildirebilirsiniz.

- **Toplu e-postayı** ( _gri posta_ olarak da bilinir) sınıflandırmak daha zordur. İstenmeyen postalar sürekli bir tehdit olsa da toplu e-posta genellikle tek seferlik reklamlar veya pazarlama iletileridir. Bazı kullanıcılar toplu e-posta iletilerini (ve aslında bunları almak için kasıtlı olarak kaydolmuşlardır) isterken, diğer kullanıcılar toplu e-postayı istenmeyen posta olarak kabul eder. Örneğin, bazı kullanıcılar Contoso Corporation'dan reklam iletileri veya siber güvenlikle ilgili yaklaşan bir konferansa davetler almak isterken, diğer kullanıcılar aynı iletileri istenmeyen posta olarak kabul eder.

  Toplu e-postanın nasıl tanımıldığı hakkında daha fazla bilgi için bkz. [EOP'de toplu şikayet düzeyi (BCL).](bulk-complaint-level-values.md)

## <a name="how-to-manage-bulk-email"></a>Toplu e-postayı yönetme

Toplu e-postaya yönelik karışık tepki nedeniyle, her kuruluş için geçerli olan evrensel rehberlik yoktur.

İstenmeyen posta önleme ilkeleri, toplu e-postayı istenmeyen posta olarak tanımlamak için kullanılan varsayılan bir BCL eşiğine sahiptir. Yöneticiler eşiği artırabilir veya azaltabilir. Daha fazla bilgi için, aşağıdaki konulara bakın:

- [EOP'de istenmeyen posta önleme ilkelerini yapılandırın](configure-your-spam-filter-policies.md).

- [EOP istenmeyen posta önleme ilkesi ayarları](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

Gözden kaçırması kolay başka bir seçenek: Bir kullanıcı toplu e-posta almaktan şikayetçiyse ancak iletiler EOP'de istenmeyen posta filtrelemesi geçiren saygın gönderenlerden geliyorsa, kullanıcının toplu e-posta iletisinde abonelikten çıkma seçeneğini denetlemesini sağlayın.

## <a name="how-to-tune-bulk-email"></a>Toplu e-postayı ayarlama

Septemeber 2022'de, Office 365 için Microsoft Defender Plan 2 müşterileri [gelişmiş avlanmadan](/microsoft-365/security/defender/advanced-hunting-overview) BCL'ye erişebilir. Bu özellik yöneticilerin, karşılık gelen BCL değerleri ve alınan e-posta birimiyle birlikte, kuruluşlarına posta gönderen tüm toplu gönderenlere bakmasını sağlar. **Email & işbirliği** şemasındaki **EmailEvents** tablosundaki diğer sütunları kullanarak toplu gönderenlerin detayına gidebilirsiniz. Daha fazla bilgi için bkz. [EmailEvents](/microsoft-365/security/defender/advanced-hunting-emailevents-table).

Örneğin, Contoso istenmeyen posta önleme ilkelerinde geçerli toplu eşiklerini 7 olarak ayarlamışsa, Contoso alıcıları gelen kutularında BCL \< 7 bulunan tüm gönderenlerden e-posta alır. Yöneticiler, kuruluştaki tüm toplu gönderenlerin listesini almak için aşağıdaki sorguyu çalıştırabilir:

```console
EmailEvents
| where BulkComplaintLevel >= 1 and Timestamp > datetime(2022-09-XXT00:00:00Z)
| summarize count() by SenderMailFromAddress, BulkComplaintLevel
```

Bu sorgu, yöneticilerin istenen ve istenmeyen gönderenleri tanımlamasına olanak tanır. Toplu gönderenin toplu eşiği karşılamayan bir BCL puanı varsa, yöneticiler [analiz için gönderenin iletilerini Microsoft'a gönderebilir](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal) ve bu da göndereni Kiracı İzin Verme/Engelleme Listesi'ne izin verme girdisi olarak ekler.

Office 365 için Defender Plan 2 olmayan kuruluşlar, aranan ve istenmeyen toplu gönderenleri belirlemek için [Tehdit koruması durum raporunu](view-email-security-reports.md#threat-protection-status-report) kullanabilir:

1. adresinde <https://security.microsoft.com/reports/URLProtectionActionReport> Tehdit koruması durum raporuna gidin ve **Verileri Email İstenmeyen**\> **Posta'ya göre görüntüle'ye göre** filtreleyin.
 
2. Toplu e-posta filtresi, araştırmak için bir e-posta seçin ve gönderen hakkında daha fazla bilgi edinmek için e-posta varlığına tıklayın. Email varlığı yalnızca Office 365 için Defender Plan 2 müşterileri tarafından kullanılabilir.

3. İstenen ve istenmeyen gönderenleri belirledikten sonra toplu eşiği istediğiniz düzeye ayarlayın. Toplu eşiğinize sığmayan BCL puanına sahip toplu gönderenler varsa, [iletileri analiz için Microsoft'a gönderin](allow-block-email-spoof.md#use-the-microsoft-365-defender-portal-to-create-allow-entries-for-domains-and-email-addresses-in-the-submissions-portal); bu da göndereni Kiracı İzin Ver/Engelle Listesi'ne izin verilen giriş olarak ekler.

Yöneticiler, önerilen toplu eşik değerlerini izleyebilir veya kuruluşlarının gereksinimlerine uygun bir toplu eşik değeri seçebilir.
