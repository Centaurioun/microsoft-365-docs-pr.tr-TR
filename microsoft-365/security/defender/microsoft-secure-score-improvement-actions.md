---
title: Microsoft Güvenli Puanı aracılığıyla güvenlik duruşunuzu değerlendirme
description: Microsoft 365 Defender portalında Microsoft Güvenli Puanınızı geliştirmek için nasıl işlem yapılacağını açıklar.
keywords: microsoft güvenli puanı, güvenli puan, office 365 güvenli puanı, microsoft güvenlik puanı, Microsoft 365 Defender portalı, iyileştirme eylemleri
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: dac1fa506dbb5de8a74817d20722738640ee2719
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480437"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Microsoft Güvenli Puanı ile güvenlik duruşunuzu değerlendirme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Güvenli Puan, bir kuruluşun güvenlik duruşunun ölçümüdür ve daha yüksek bir sayı daha fazla geliştirme eylemi gerçekleştirildiğini gösterir. [Microsoft 365 Defender portalında](microsoft-365-defender.md) bulunabilirhttps://security.microsoft.com/securescore.

İhtiyacınız olan bilgileri daha hızlı bulmanıza yardımcı olmak için Microsoft geliştirme eylemleri gruplar halinde düzenlenir:

- Kimlik (Azure Active Directory hesapları & rolleri)
- Cihaz (Uç Nokta için Microsoft Defender, [Cihazlar için Microsoft Güvenli Puanı](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices) olarak bilinir)
- Uygulamalar (Office 365 ve Microsoft Defender for Cloud Apps dahil olmak üzere e-posta ve bulut uygulamaları)

>[!NOTE]
>Microsoft Güvenli Puan'ın son sürümünde, Microsoft Güvenli Puan'ın Identity Secure Score ve Graph API ile geçici olarak uyumsuz hale gelen geliştirilmiş bir puanlama modeli yayınlandı. [Ayrıntıları görüntüle](microsoft-secure-score-whats-new.md)

Microsoft Güvenli Puana genel bakış sayfasında, puanların bu gruplar arasında nasıl bölündüğünü ve hangi noktaların kullanılabilir olduğunu görüntüleyin. Ayrıca toplam puanın genel görünümünü, karşılaştırma karşılaştırmalarıyla güvenli puanınızın geçmiş eğilimini ve puanınızı geliştirmek için gerçekleştirilebilecek önceliklendirilmiş iyileştirme eylemlerini de alabilirsiniz.

:::image type="content" source="../../media/secure-score/secure-score-home-page.png" alt-text="Microsoft 365 Defender portalındaki Güvenli Puan giriş sayfası" lightbox="../../media/secure-score/secure-score-home-page.png":::

## <a name="check-your-current-score"></a>Geçerli puanınızı denetleyin

Geçerli puanınızı kontrol etmek için Microsoft Güvenli Puana genel bakış sayfasına gidin ve **Güvenli puanınız** yazan kutucuğu arayın. Puanınız, toplam olası puandan elde ettiğiniz puan sayısıyla birlikte yüzde olarak gösterilir.

Ayrıca, puanınızın yanındaki **Ekle** düğmesini seçerseniz, puanınızın farklı görünümlerini seçebilirsiniz. Puan kutucuğundaki grafikte ve puan döküm grafiğinde bu farklı puan görünümleri görüntülenir.

Genel puanınızın daha kapsamlı bir resmini sunmak için genel puanınızı görünümünüzde ekleyebileceğiniz puanlar aşağıdadır:

- **Planlı puan: Planlı** eylemler tamamlandığında öngörülen puanı göster
- **Geçerli lisans puanı**: Geçerli Microsoft lisansınızla elde edilebilecek puanı göster
- **Ulaşılabilir puan**: Microsoft lisanslarınız ve geçerli risk kabulü ile elde edilebilecek puanı gösterin

Olası tüm puan görünümlerini eklediyseniz bu görünüm şöyle görünür:

:::image type="content" source="../../media/secure-score/secure-score-achievable.png" alt-text="Microsoft 365 Defender portalında planlı puan, geçerli lisans puanı ve ulaşılabilir puan dahil olmak üzere güvenli puanınız" lightbox="../../media/secure-score/secure-score-achievable.png":::

## <a name="take-action-to-improve-your-score"></a>Puanınızı geliştirmek için eyleme geçme

**İyileştirme eylemleri** sekmesi, olası saldırı yüzeylerini ele alan güvenlik önerilerini listeler. Ayrıca durumlarını da içerir (ele almak, planlanan, riski kabul edilen, üçüncü taraf aracılığıyla çözümlenen, alternatif risk azaltma yoluyla çözümlenen ve tamamlanan). Tüm iyileştirme eylemlerini arayabilir, filtreleyebilir ve gruplandırabilirsiniz.  

### <a name="ranking"></a>Sıralama

Derecelendirme, elde edilecek puan sayısına, uygulama zorluğuna, kullanıcı etkisine ve karmaşıklık düzeyine bağlıdır. En yüksek dereceli iyileştirme eylemleri düşük zorluk, kullanıcı etkisi ve karmaşıklık ile çok sayıda puana sahiptir.

### <a name="view-improvement-action-details"></a>İyileştirme eylemi ayrıntılarını görüntüleme

Belirli bir iyileştirme eylemini seçtiğinizde tam sayfa açılır öğesi görüntülenir.  

:::image type="content" source="../../media/secure-score/secure-score-improvement-action-details.png" alt-text="Microsoft 365 Defender portalında geliştirme eyleminin açılır öğesi" lightbox="../../media/secure-score/secure-score-improvement-action-details.png":::

Eylemi tamamlamak için birkaç seçeneğiniz vardır:

- Yapılandırma ekranına gitmek ve değişikliği yapmak için **Microsoft 365 Defender'de Yönet'i** seçin. Ardından, eylemin değer olduğu ve açılır öğede görünür olduğu noktaları elde edersiniz. Noktaların güncelleştirilmek genellikle yaklaşık 24 saat sürer.

- İyileştirme eyleminin doğrudan bağlantısını kopyalamak için **Paylaş'ı** seçin. Bağlantıyı paylaşmak için e-posta, Microsoft Teams veya Microsoft Planner gibi platformu da seçebilirsiniz.

İlerleme durumunu veya yorum yapmak istediğiniz diğer her şeyi izlemek için **Notlar** ekleyin. İyileştirme eylemine kendi **etiketlerinizi** eklerseniz, bu etiketlere göre filtreleyebilirsiniz.

### <a name="choose-an-improvement-action-status"></a>İyileştirme eylemi durumunu seçme

İyileştirme eylemine özgü durumları seçin ve notları kaydedin.

- **Ele almak için** - İyileştirme eyleminin gerekli olduğunu fark eder ve bunu gelecekte bir noktada ele almayı planlıyorsunuz. Bu durum kısmen olarak algılanan ancak tam olarak tamamlanmamış eylemler için de geçerlidir.
- **Planlı** - İyileştirme eylemini tamamlamak için somut planlar vardır.
- **Risk kabul edildi** - Güvenlik her zaman kullanılabilirlik ile dengelenmelidir ve her öneri ortamınızda çalışmaz. Bu durumda, riski veya kalan riski kabul etmeyi ve iyileştirme eylemini gerçekleştirmemeyi seçebilirsiniz. Size herhangi bir puan verilmez, ancak eylem artık iyileştirme eylemleri listesinde görünmez. Bu eylemi geçmişte görüntüleyebilir veya istediğiniz zaman geri alabilirsiniz.
- **Üçüncü taraf aracılığıyla çözümlendi** ve **Alternatif risk azaltma yoluyla çözümlendi** - İyileştirme eylemi bir üçüncü taraf uygulama veya yazılım ya da bir iç araç tarafından zaten ele alınmıştır. Eylemin değerindeki puanları kazanırsınız, böylece puanınız genel güvenlik duruşunuzu daha iyi yansıtır. Bir üçüncü taraf veya iç araç artık denetimi kapsamazsa, başka bir durum seçebilirsiniz. İyileştirme eylemi bu durumlardan biri olarak işaretlenirse Microsoft'un uygulamanın tamamında görünürlük elde etmiyeceğini unutmayın.

#### <a name="microsoft-defender-vulnerability-management-improvement-actions"></a>Microsoft Defender Güvenlik Açığı Yönetimi iyileştirme eylemleri

"Cihaz" kategorisindeki iyileştirme eylemleri için durumları seçemezsiniz. Bunun yerine, eylemde bulunabilmek için [Microsoft 365 Defender ilişkili Microsoft Defender Güvenlik Açığı Yönetimi güvenlik önerisine](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) yönlendirilirsiniz. Seçtiğiniz özel durum ve yazdığınız gerekçe bu portala özgü olacaktır. Microsoft Güvenli Puan portalında sunulmaz.

#### <a name="completed-improvement-actions"></a>Tamamlanan iyileştirme eylemleri

İyileştirme eylemi için tüm olası noktalar elde edildikten sonra iyileştirme eylemleri "tamamlandı" durumuna sahiptir. Tamamlanan iyileştirme eylemleri Microsoft verilerine rağmen onaylanır ve durumu değiştiremezsiniz.

### <a name="assess-information-and-review-user-impact"></a>Bilgileri değerlendirme ve kullanıcı etkisini gözden geçirme

**Bir bakışta** adlı bölüm size kategoriyi, koruyabileceği saldırıları ve ürünü söyler.

**Kullanıcı etkisi** , iyileştirme eylemi gerçekleştirilirse kullanıcıların karşılaşacağı etkidir ve **etkilenen kullanıcılar** etkilenecek kişilerdir.

### <a name="implement-the-improvement-action"></a>İyileştirme eylemini uygulama

**Uygulama** bölümünde önkoşullar, iyileştirme eylemini tamamlamak için adım adım sonraki adımlar, iyileştirme eyleminin geçerli uygulama durumu ve daha fazla bilgi edinin.

Önkoşullar, iyileştirme eylemi ele almadan önce tamamlanması gereken lisansları veya eylemleri içerir. İyileştirme eylemini tamamlamak için lisansınızda yeterli yer olduğundan ve bu lisansların gerekli kullanıcılara uygulandığından emin olun.  

## <a name="we-want-to-hear-from-you"></a>Sizden haber almak istiyoruz

Herhangi bir sorununuz varsa [Güvenlik, Gizlilik & Uyumluluk](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) topluluğuna göndererek bize bildirin. Topluluğu izliyoruz ve yardım sağlayacağız.

## <a name="related-resources"></a>İlgili kaynaklar

- [Microsoft Güvenli Puanına genel bakış](microsoft-secure-score.md)
- [Microsoft Güvenli Puan geçmişinizi izleme ve hedefleri karşılama](microsoft-secure-score-history-metrics-trends.md)
- [Yapılacak yenilikler](microsoft-secure-score-whats-coming.md)
- [Yenilikler](microsoft-secure-score-whats-new.md)
