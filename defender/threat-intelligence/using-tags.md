---
title: Microsoft Defender Tehdit Analizi'de Etiketleri Kullanma (Defender TI)
Description: Bu nasıl yapılır makalesinde etiket türleri ve Microsoft Defender Tehdit Analizi (Defender TI) içinde özel etiketler ekleme, değiştirme, silme ve arama hakkında bilgi edinin.
author: alexroland24
ms.author: aroland
ms.service: threat-intelligence
ms.topic: how-to
ms.date: 08/02/2022
ms.custom: template-how-to
ms.openlocfilehash: d9e77b52e7f36bb0458a0638c0b0d2ee24e8bbff
ms.sourcegitcommit: d7193ee954c01c4172e228d25b941026c8d92d30
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175520"
---
# <a name="using-tags"></a>Etiketleri kullanma
Microsoft Defender Tehdit Analizi (Defender TI) etiketleri, sistem tarafından türetilen veya diğer kullanıcılar tarafından oluşturulan bir yapıt hakkında hızlı içgörü sağlamak için kullanılır. Etiketler, analistlerin mevcut olaylar ve araştırmalarla bunların geçmiş bağlamları arasındaki noktaları daha iyi analiz için bağlamalarına yardımcı oluyor.

Defender TI platformu iki tür etiket sunar: sistem ve özel etiketler.

![Etiketleri Kullanma Chrome Giriş Sayfası](media/UsingTagsChromeHomePage.png)

## <a name="prerequisites"></a>Önkoşullar

- Bir Azure Active Directory veya kişisel Microsoft hesabı. [Oturum açma veya hesap oluşturma](https://signup.microsoft.com/)
- Microsoft Defender Tehdit Analizi (Defender TI) Premium lisansı.
    > [!NOTE]
    > Defender TI Premium lisansı olmayan kullanıcılar Defender Tehdit Bilgileri Portalı'na giriş yapmaya ve ücretsiz Defender TI teklifimize erişmeye devam edebilir.

## <a name="system-tags"></a>Sistem etiketleri

Bu etiketler, kullanıcıların analizlerine rehberlik etmeleri için platform tarafından otomatik olarak oluşturulur ve kullanıcı açısından herhangi bir giriş veya çaba gerektirmez.

Sistem etiketleri şunları içerebilir:

- **Yönlendirilebilir:** Yapıtın erişilebilir olduğunu gösterir.
- **ASN:** Analistlere IP adresinin kime ait olduğu hakkında bağlam sağlamak için IP adresi ASN açıklamasının kısaltılmış bir bölümünü bir etikete çeker.
- **Dinamik:** Bir etki alanının IP Olmayan veya IP'yi Değiştir gibi dinamik bir DNS hizmetine ait olup olmadığını gösterir.
- **Havuz deliği:** IP adresinin güvenlik kuruluşları tarafından saldırı kampanyalarını araştırmak için kullanılan bir araştırma havuzu olduğunu ve bu nedenle ilişkili etki alanlarının birbiriyle doğrudan bağlantılı olmadığını gösterir.

![Etiketler Sistemi](media/tagsSystem.png)

## <a name="custom-tags"></a>Özel etiketler

Gizliliği tehlikeye girme göstergelerine (ICS) bağlam getirmek ve genel raporlamadan kötü bilinen veya şirketinizin analistleri tarafından kategorilere ayrılmış olan etki alanlarını belirleyerek analizi daha da basit hale getirmek için Defender TI'nin içindeki Özel Etiketler. Bu etiketler kullanıcılar tarafından kendi araştırmalarına göre el ile oluşturulur. Bu etiketler kullanıcıların bir yapıt hakkındaki önemli içgörüleri kiracılarındaki diğer Defender TI Premium lisans kullanıcılarıyla paylaşmasına olanak tanır.

![Etiketler Özel](media/tagsCustom.png)

## <a name="adding-modifying-and-removing-tags"></a>Etiket Ekleme, Değiştirme ve Kaldırma

Kullanıcılar, özel etiketlerini etiket çubuğuna girerek etiket kümesine kendi etiketlerini ekleyebilir. Bu etiketler, kuruluşu Bir Defender TI müşterisiyse tek tek kullanıcı ve kullanıcının ekip üyeleri tarafından görüntülenebilir. Sisteme girilen etiketler özeldir ve büyük toplulukla paylaşılmaz.

Kullanıcıların etiket ekleyebildiği gibi, bunları da değiştirebilir veya kaldırabilirler. Bir kullanıcı tarafından bir etiket eklendikten sonra, aynı kullanıcı veya kurumsal kuruluştaki başka bir ücretli lisanslı kullanıcı tarafından değiştirilebilir veya kaldırılabilir. Bu, Güvenlik ekibi arasında kolay işbirliğine olanak tanır.

1. [Defender Tehdit Bilgileri Portalı'na](https://ti.defender.microsoft.com/) erişin.
2. Portala erişmek için Microsoft kimlik doğrulamasını tamamlayın.
3. Tehdit Bilgileri arama çubuğunda etiket eklemek istediğiniz bir göstergeyi arayın.

    ![Etiket Arama](media/tagsSearch.png)

4. Defender TI portalının sol üst köşesindeki 'Etiketleri Düzenle' açılan listesini seçin.

    ![Etiketler Arama Etiketleri Düzenle](media/tagsSearchEditTags.png)

5. Bu göstergeyle ilişkilendirmek istediğiniz etiketleri ekleyin.

    > [!Note]
    > Yeni bir gösterge eklemek için Sekme tuşuna basın.

    ![Etiketler Arama Etiket Ekle](media/tagsSearchAddTags.png)

6. Tüm etiketleriniz eklendikten sonra Kaydet düğmesini seçerek değişikliklerinizi kaydedin.

    ![Etiketler Arama Etiketleri Kaydet](media/tagsSearchSaveTags.png)

7. Etiketleri düzenlemek için 3. adımı yineleyin. Etiket adının sonundaki 'X' işaretini seçerek veya 4. adımda yaptığınız gibi yeni etiketler ekleyerek etiketleri kaldırın.

8. Değişikliklerinizi kaydedin.

    ![Etiketler Arama Etiketleri](media/tagsSearchTags.png)

## <a name="viewing-and-searching-tags"></a>Etiketleri Görüntüleme ve Arama

Kullanıcılar bir IP, etki alanı veya konak yapıtında arama yaptıktan sonra kendileri veya kiracılarındaki diğer kişiler tarafından eklenen etiketleri görüntüleyebilir.

![Etiketler Özel](media/tagsCustom.png)

1. [Defender Tehdit Bilgileri Portalı'na](https://ti.defender.microsoft.com/) erişin.
2. Portala erişmek için Microsoft kimlik doğrulamasını tamamlayın.
3. Kullanıcılar, Tehdit Bilgileri arama çubuğu açılan listesinde Etiket arama türünü seçerek ve aynı etiket değerini paylaşan diğer tüm göstergeleri tanımlamak için etiket değeriyle arama yaparak Defender TI'nin Tehdit Bilgileri Araması aracılığıyla özel etiketlerde arama yapabilir.

    ![Arama Etiketi](media/searchTag.png)

Ortak Etiket Kullanım Örneği İş Akışı Bir önceliklendirme analisti bir olayı araştırır ve bunun kimlik avıyla ilgili olduğunu bulur. Bu analist, bu olayla ilgili risk göstergelerine etiket olarak "kimlik avı" ekleyebilir. Daha sonra, olay yanıtı ve tehdit avcılığı ekibi bu güvenlik ihlali göstergelerini daha fazla analiz edebilir ve kimlik avı olayından hangi aktör grubunun sorumlu olduğunu belirlemek için siber tehdit zekası muadilleriyle birlikte çalışabilir. Daha sonra bu risk göstergelerine veya "[SHA-1 karma]" özel etiketi gibi diğer ilgili güvenlik ihlal göstergelerine bağlanan hangi altyapının kullanıldığına ilişkin başka bir "[aktör adı]" etiketi ekleyebilirler.

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için bkz.:

- [Microsoft Defender Tehdit Bilgileri (Defender TI) nedir?](index.md)
- [Veri kümeleri](data-sets.md)
- [Verileri sıralama, filtreleme ve indirme](sorting-filtering-and-downloading-data.md)
- [İtibar puanlaması](reputation-scoring.md)
- [Çözümleyici içgörüleri](analyst-insights.md)
- [Projeleri kullanma](using-projects.md)
