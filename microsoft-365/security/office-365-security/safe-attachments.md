---
title: Güvenli Ekler
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Yöneticiler, Office 365 için Microsoft Defender'daki Güvenli Ekler özelliği hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 4ee9bfea06d1bc3e4b5b49bc4759b9d59166cd1f
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67671401"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'da Güvenli Ekler

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Office 365 için Microsoft Defender'deki](defender-for-office-365.md) Güvenli Ekler, [Exchange Online Protection'de (EOP) kötü amaçlı yazılımdan koruma](anti-malware-protection.md) tarafından zaten taranmış e-posta ekleri için ek bir koruma katmanı sağlar. Özellikle, Güvenli Ekler, e-posta iletilerindeki ekleri alıcılara teslim etmeden önce denetlemek için bir sanal ortam kullanır ( _patlama_ olarak bilinen bir işlem).

E-posta iletileri için Güvenli Ekler koruması, Güvenli Ekler ilkeleri tarafından denetlenmektedir. Varsayılan Güvenli Ekler ilkesi olmasa **da, Yerleşik koruma** önceden ayarlanmış güvenlik ilkesi tüm alıcılara Güvenli Ekler koruması sağlar (Standart veya Katı önceden ayarlanmış güvenlik ilkeleri veya özel Güvenli Ekler ilkelerinde tanımlanmayan kullanıcılar). Daha fazla bilgi için bkz. [EOP'de önceden ayarlanmış güvenlik ilkeleri ve Office 365 için Microsoft Defender](preset-security-policies.md). Ayrıca belirli kullanıcılar, gruplar veya etki alanları için geçerli olan Güvenli Ekler ilkeleri de oluşturabilirsiniz. Yönergeler için bkz. [Office 365 için Microsoft Defender'da Güvenli Ekler ilkelerini ayarlama](set-up-safe-attachments-policies.md).

Aşağıdaki tabloda, Office 365 için Microsoft Defender içeren Microsoft 365 ve Office 365 kuruluşlarında Güvenli Ekler senaryoları açıklanmaktadır (başka bir deyişle, lisans eksikliği örneklerde hiçbir zaman sorun oluşturmaz).

|Senaryo|Sonuç|
|---|---|
|Pat'in Microsoft 365 E5 kuruluşunda Yapılandırılmış Güvenli Ekler ilkesi yok.|Pat, Güvenli Ekler ilkelerinde aksi tanımlanmayan tüm alıcılar için geçerli olan **Yerleşik koruma** önayarlı güvenlik ilkesi nedeniyle Güvenli Ekler tarafından korunur.|
|Lee'nin kuruluşu, yalnızca finans çalışanları için geçerli olan bir Güvenli Ekler ilkesine sahiptir. Lee satış departmanının bir üyesi.|Lee ve satış departmanının geri kalanı, Güvenli Ekler ilkelerinde aksi şekilde tanımlanmayan tüm alıcılar için geçerli olan **Yerleşik koruma** ön ayarı güvenlik ilkesi nedeniyle Güvenli Ekler tarafından korunur.|
|Dün Jean'in kuruluşundaki bir yönetici, tüm çalışanlar için geçerli olan bir Güvenli Ekler ilkesi oluşturdu. Bugün erken saatlerde Jean ek içeren bir e-posta iletisi aldı.|Jean, bu özel Güvenli Ekler ilkesi nedeniyle Güvenli Ekler tarafından korunur. <br/><br/> Genellikle yeni bir ilkenin geçerlilik kazanması yaklaşık 30 dakika sürer.|
|Chris'in kuruluşu, kuruluştaki herkes için uzun süredir devam eden Güvenli Ekler ilkelerine sahiptir. Chris eki olan bir e-posta alır ve ardından iletiyi dış alıcılara iletir.|Chis, Güvenli Ekler tarafından korunur. <br/><br/> Dış alıcılar bir Microsoft 365 kuruluşundaysa, iletilen iletiler de Güvenli Ekler tarafından korunur.|

Güvenli Ekler taraması, Microsoft 365 verilerinizin bulunduğu bölgede gerçekleşir. Veri merkezi coğrafyası hakkında daha fazla bilgi için bkz. [Verileriniz nerede bulunur?](https://products.office.com/where-is-your-data-located?geo=All)

> [!NOTE]
> Aşağıdaki özellikler, Microsoft 365 Defender portalındaki Güvenli Ekler ilkelerinin genel ayarlarında yer alır. Ancak, bu ayarlar genel olarak etkinleştirilir veya devre dışı bırakılır ve Güvenli Ekler ilkeleri gerektirmez:
>
> - [SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler](mdo-for-spo-odb-and-teams.md).
> - [Microsoft 365 E5 aboneliğinde Güvenli Belgeler](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a>Güvenli Ekler ilke ayarları

Bu bölümde, Güvenli Ekler ilkelerindeki ayarlar açıklanmaktadır:

- **Alıcı filtreleri**: İlkenin kime uygulanacağını belirleyen alıcı koşullarını ve özel durumlarını belirtmeniz gerekir. Koşullar ve özel durumlar için şu özellikleri kullanabilirsiniz:
  - **Kullanıcılar**
  - **Gruplar**
  - **Etki alanları**

  Bir koşulu veya özel durumu yalnızca bir kez kullanabilirsiniz, ancak koşul veya özel durum birden çok değer içerebilir. Aynı koşula veya özel duruma ait birden çok değer OR mantığını kullanır (örneğin, _\<recipient1\>_ veya _\<recipient2\>_). Farklı koşullar veya özel durumlar AND mantığını kullanır (örneğin, _\<recipient1\>_ ve _\<member of group 1\>_).

  > [!IMPORTANT]
  > Birden çok farklı koşul veya özel durum türü ek değildir; Onlar kapsayıcı. İlke _yalnızca_ belirtilen alıcı filtrelerinin _tümüyle_ eşleşen alıcılara uygulanır. Örneğin, ilkede aşağıdaki değerlerle bir alıcı filtresi koşulu yapılandırabilirsiniz:
  >
  > - Kullanıcılar: romain@contoso.com
  > - Gruplar: Yöneticiler
  >
  > İlke, _romain@contoso.com yalnızca_ Yöneticiler grubunun da üyesiyse uygulanır. Grubun üyesi değilse ilke ona uygulanmaz.
  >
  > Benzer şekilde, ilkenin özel durumu olarak aynı alıcı filtresini kullanırsanız, ilke _romain@contoso.com yalnızca_ Yöneticiler grubunun da üyesiyse uygulanmaz. Grubun üyesi değilse, ilke hala onun için geçerlidir.

- **Güvenli Ekler bilinmeyen kötü amaçlı yazılım yanıtı**: Bu ayar, e-posta iletilerinde Güvenli Ekler kötü amaçlı yazılım taraması eylemini denetler. Kullanılabilir seçenekler aşağıdaki tabloda açıklanmıştır:

  |Seçeneği|Etkisi|Şunu yapmak istediğinizde kullanın:|
  |---|---|---|
  |**Devre Dışı**|Ekler, Güvenli Ekler tarafından kötü amaçlı yazılımlara karşı taranmıyor. EOP'de kötü amaçlı yazılımdan [koruma tarafından iletiler yine de kötü amaçlı yazılımlara](anti-malware-protection.md) karşı taranır.|Seçili alıcılar için taramayı kapatın. <br/><br/> İç posta yönlendirmede gereksiz gecikmeleri önleyin. <br/><br/> **Bu seçenek çoğu kullanıcı için önerilmez. Bu seçeneği yalnızca güvenilir gönderenlerden yalnızca ileti alan alıcılar için Güvenli Ekler taramasını kapatmak için kullanmalısınız. Güvenli Ekler kapatılırsa ve kötü amaçlı yazılım sinyali alınmazsa ZAP iletileri karantinaya almayacaktır. Ayrıntılar için bkz. [Sıfır saatlik otomatik temizleme](zero-hour-auto-purge.md)**|
  |**Monitör**|Ekleri olan iletileri teslim eder ve ardından algılanan kötü amaçlı yazılımla ne olduğunu izler. <br/><br/> Güvenli Eklerin taranma nedeniyle güvenli iletilerin teslimi gecikebilir.|Algılanan kötü amaçlı yazılımların kuruluşunuzda nereye gittiğini görün.|
  |**Engelle**|Algılanan kötü amaçlı yazılım eklerine sahip iletilerin teslim edilmesini engeller. <br/><br/> İletiler karantinaya alınır. Varsayılan olarak, iletileri yalnızca yöneticiler (kullanıcılar değil) gözden geçirebilir, yayımlayabilir veya silebilir.<sup>\*</sup> <br/><br/> İletilerin ve eklerin gelecekteki örneklerini otomatik olarak engeller. <br/><br/> Güvenli Eklerin taranma nedeniyle güvenli iletilerin teslimi gecikebilir.|Aynı kötü amaçlı yazılım eklerini kullanarak kuruluşunuzu tekrarlanan saldırılara karşı korur. <br/><br/> Bu varsayılan değerdir ve Standart ve Katı [önceden belirlenmiş güvenlik ilkeleri](preset-security-policies.md) için önerilen değerdir.|
  |**Değiştirmek**|**Not**: Bu eylem kullanım dışı bırakılacaktır. Daha fazla bilgi için bkz. [MC424901](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC424901). <br/><br/> Algılanan kötü amaçlı yazılım eklerini kaldırır. <br/><br/> Alıcılara eklerin kaldırıldığını bildirir. <br/><br/>  Kötü amaçlı ekler içeren iletiler karantinaya alınır. Varsayılan olarak, iletileri yalnızca yöneticiler (kullanıcılar değil) gözden geçirebilir, yayımlayabilir veya silebilir.<sup>\*</sup> <br/><br/> Güvenli Eklerin taranma nedeniyle güvenli iletilerin teslimi gecikebilir.|Algılanan kötü amaçlı yazılım nedeniyle eklerin kaldırıldığı alıcılara görünürlük sağlayın.|
  |**Dinamik Teslim**|İletileri hemen teslim eder, ancak Güvenli Ekler taraması tamamlanana kadar ekleri yer tutucularla değiştirir. <br/><br/> Kötü amaçlı ekler içeren iletiler karantinaya alınır. Varsayılan olarak, iletileri yalnızca yöneticiler (kullanıcılar değil) gözden geçirebilir, yayımlayabilir veya silebilir.<sup>\*</sup> <br/><br/> Ayrıntılar için, bu makalenin [devamında yer alan Güvenli Ekler ilkelerinde Dinamik Teslim](#dynamic-delivery-in-safe-attachments-policies) bölümüne bakın.|Alıcıları kötü amaçlı dosyalardan korurken ileti gecikmelerinden kaçının.|

  <sup>\*</sup>**Karantina ilkesi**: Yöneticiler, _kullanıcıların karantinaya alınan iletilere_ ne yapmalarına izin verildiğini tanımlayan Güvenli Ekler ilkelerinde karantina ilkeleri oluşturabilir ve atayabilir. Daha fazla bilgi için bkz [. Karantina ilkeleri](quarantine-policies.md).

- **Algılanan ekleri olan iletileri yeniden yönlendirme**: **Yeniden yönlendirmeyi etkinleştirin** ve **Engellenen, izlenen veya değiştirilen ekleri içeren iletileri belirtilen e-posta adresine gönderin**: **Engelleme**, **İzleme** veya **Değiştirme** eylemleri için, analiz ve araştırma için belirtilen iç veya dış e-posta adresine kötü amaçlı yazılım ekleri içeren iletiler gönderin.

  Standart ve Katı ilke ayarları için öneri, yeniden yönlendirmeyi etkinleştirmektir. Daha fazla bilgi için bkz [. Güvenli Ekler ayarları](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

  > [!NOTE]
  > Yeniden yönlendirme yakında yalnızca **İzleyici** eylemi için kullanılabilir olacak. Daha fazla bilgi için bkz. [MC424899](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter/:/messages/MC424899).

- **Tarama tamamlanamadıysa Güvenli Ekler algılama yanıtını uygulayın (zaman aşımı veya hatalar)**: **Güvenli Ekler bilinmeyen kötü amaçlı yazılım yanıtı** tarafından belirtilen eylem, Güvenli Ekler taraması tamamlanamadıklarında bile iletilere uygulanır. **Yeniden yönlendirmeyi etkinleştir'i** seçerseniz her zaman bu seçeneği belirleyin. Aksi takdirde iletiler kaybolabilir.

- **Öncelik**: Birden çok ilke oluşturursanız, bunların uygulanacağı sırayı belirtebilirsiniz. hiçbir iki ilke aynı önceliğe sahip olamaz ve ilke işleme ilk ilke uygulandıktan sonra durur.

  Öncelik sırası ve birden çok ilkenin nasıl değerlendirilip uygulandığı hakkında daha fazla bilgi için bkz [. E-posta korumasının sırası ve önceliği](how-policies-and-protections-are-combined.md).

### <a name="dynamic-delivery-in-safe-attachments-policies"></a>Güvenli Eklerde Dinamik Teslim ilkeleri

> [!NOTE]
> Dinamik Teslim yalnızca Exchange Online posta kutuları için çalışır.

Güvenli Ekler ilkelerindeki Dinamik Teslim eylemi, Güvenli Ekler taramasının neden olabileceği e-posta teslim gecikmelerini ortadan kaldırmaya çalışır. E-posta iletisinin gövdesi, her ek için bir yer tutucu ile alıcıya teslim edilir. Yer tutucu, ek güvenli bulunana kadar kalır ve ek açılabilir veya indirilebilir hale gelir.

Bir ekin kötü amaçlı olduğu tespit edilirse, ileti karantinaya alınır.

Güvenli Ekler taraması devam ederken ÇOĞU PDF ve Office belgesi güvenli modda önizlenebilir. Bir ek Dinamik Teslim önİzleyicisi ile uyumlu değilse, Güvenli Ekler taraması tamamlanana kadar alıcılar ek için bir yer tutucu görür.

Mobil cihaz kullanıyorsanız ve PDF'ler mobil cihazınızda dinamik teslim önizleyicisinde işlenmiyorsa, mobil tarayıcınızı kullanarak iletiyi Web üzerinde Outlook (eski adıyla Outlook Web App) açmayı deneyin.

Dinamik Teslim ve iletilen iletiler için dikkat edilmesi gereken bazı noktalar şunlardır:

- İletilen alıcı Dinamik Teslim seçeneğini kullanan güvenli ekler ilkesiyle korunuyorsa, alıcı yer tutucuyu görür ve uyumlu dosyaların önizlemesini görebilir.
- İletilen alıcı Güvenli Ekler ilkesi tarafından korunmuyorsa, ileti ve ekler Güvenli Ekler taraması veya ek yer tutucuları olmadan teslim edilir.

Dinamik Teslim'in iletilerdeki ekleri değiştiremediği senaryolar vardır. Bu senaryolar şunlardır:

- Ortak klasörlerdeki iletiler.
- Özel kurallar kullanılarak kullanıcının posta kutusundan dışarı ve sonra geri yönlendirilen iletiler.
- Bulut posta kutularından arşiv klasörleri de dahil olmak üzere diğer konumlara taşınan (otomatik veya el ile) iletiler.
- Gelen kutusu kuralları, iletiyi Gelen Kutusu'nun dışına farklı bir klasöre taşır.
- İletiler silindi.
- Kullanıcının posta kutusu arama klasörü hata durumunda.
- Exclaimer'ın etkinleştirildiği kuruluşları Exchange Online. Bu sorunu çözmek için bkz [. KB4014438](https://support.microsoft.com/help/4014438).
- [S/MIME)](/exchange/security-and-compliance/smime-exo/smime-exo) şifrelenmiş iletiler.
- Dinamik Teslim eylemini Güvenli Ekler ilkesinde yapılandırdıysanız, ancak alıcı Dinamik Teslim'i desteklemez (örneğin, alıcı şirket içi Exchange kuruluşundaki bir posta kutusudur). Ancak[, Office 365 için Microsoft Defender'daki Güvenli Bağlantılar URL'ler](set-up-safe-links-policies.md) içeren Office dosya eklerini tarar (geçerli Güvenli Bağlantılar ilkesinde Destek Office uygulamalarının Güvenli Bağlantılar taraması açıksa).

## <a name="submitting-files-for-malware-analysis"></a>Kötü amaçlı yazılım analizi için dosya gönderme

- Analiz için Microsoft'a göndermek istediğiniz bir dosya alırsanız, bkz. [Analiz için Microsoft'a kötü amaçlı yazılım ve kötü amaçlı olmayan yazılım gönderme](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).
- Analiz için Microsoft'a göndermek istediğiniz bir e-posta iletisi (ekli veya eksiz) alırsanız bkz. [İletileri ve dosyaları Microsoft'a bildirme](report-junk-email-messages-to-microsoft.md).
