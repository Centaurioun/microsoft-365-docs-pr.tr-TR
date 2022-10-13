---
title: Saldırı simülasyonu eğitimi ile kimlik avı saldırısı simüle etme
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: microsoft-365-security
ms.localizationpriority: medium
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.custom: ''
description: Yöneticiler, Office 365 için Microsoft Defender Plan 2'deki Saldırı simülasyonu eğitimi kullanarak kimlik avı saldırılarının simülasyonunu yapmayı ve kullanıcılarını kimlik avı önleme konusunda eğitmeyi öğrenebilir.
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 144d1788b861566c496ced4e927a8591647a93b8
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68566024"
---
# <a name="simulate-a-phishing-attack-with-attack-simulation-training-in-defender-for-office-365"></a>Office 365 için Defender'de Saldırı simülasyonu eğitimi ile kimlik avı saldırısı simülasyonu

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

[Office 365 için Microsoft Defender plan 2](defender-for-office-365.md) **için geçerlidir**

Office 365 için Microsoft Defender Plan 2 veya Microsoft 365 E5'da Saldırı simülasyonu eğitimi, kuruluşunuzda zararsız siber saldırı simülasyonları çalıştırmanıza olanak tanır. Bu simülasyonlar güvenlik ilkelerinizi ve uygulamalarınızı test eder, ayrıca çalışanlarınızı farkındalıklarını artırmaları ve saldırılara karşı duyarlılıklarını azaltmaları için eğitebilir. Bu makalede, Saldırı simülasyonu eğitimi kullanarak sanal kimlik avı saldırısı oluşturma konusunda size yol gösterir.

Saldırı simülasyonu eğitimi hakkında başlangıç bilgileri için bkz. [Saldırı simülasyonu eğitimi kullanmaya başlama](attack-simulation-training-get-started.md).

Kimlik avı simülasyonu saldırısı başlatmak için aşağıdaki adımları uygulayın:

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Email & işbirliği** \> **Saldırı simülasyonu eğitimi** \> **Benzetimi** sekmesine gidin.

   Doğrudan **Simülasyonlar** sekmesine gitmek için kullanın <https://security.microsoft.com/attacksimulator?viewid=simulations>.

2. **Simülasyonlar sekmesinde Simülasyon** simgesini başlat'ı seçin![.](../../media/m365-cc-sc-create-icon.png) **Simülasyonu başlatın**.

   :::image type="content" source="../../media/attack-sim-training-simulations-launch.png" alt-text="Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi Simülasyonlar sekmesinde simülasyon başlat düğmesi" lightbox="../../media/attack-sim-training-simulations-launch.png":::

3. Simülasyon oluşturma sihirbazı açılır. Bu makalenin geri kalanında sayfalar ve içerdikleri ayarlar açıklanmaktadır.

> [!NOTE]
> Simülasyon oluşturma sihirbazı sırasında herhangi bir noktada Kaydet **ve kapat'a** tıklayarak ilerlemenizi kaydedebilir ve simülasyonu daha sonra yapılandırmaya devam edebilirsiniz. Tamamlanmamış simülasyon, **Simülasyonlar** sekmesinde **Taslak Durum** değerine sahiptir. Simülasyonu seçip Simülasyonu düzenle simgesine tıklayarak ![kaldığınız yerden devam edebilirsiniz.](../../media/m365-cc-sc-edit-icon.png) **Simülasyonu düzenleme** .

## <a name="select-a-social-engineering-technique"></a>Sosyal mühendislik tekniği seçme

**Tekniği seçin** sayfasında, [MITRE ATT&CK® çerçevesinden](https://attack.mitre.org/techniques/enterprise/) seçilen kullanılabilir bir sosyal mühendislik tekniği seçin. Farklı teknikler için farklı yükler kullanılabilir. Aşağıdaki sosyal mühendislik teknikleri mevcuttur:

- **Kimlik bilgisi toplama**: Kullanıcı adı ve parola göndermek için kullanıcıları giriş kutularıyla iyi bilinen bir web sitesine götürerek kimlik bilgilerini toplamaya çalışır.
- **Kötü amaçlı yazılım eki**: İletiye kötü amaçlı bir ek ekler. Kullanıcı eki açtığında, saldırganın hedefin cihazını tehlikeye atılmasına yardımcı olacak rastgele kod çalıştırılır.
- **Ekteki bağlantı**: Kimlik bilgisi toplama karma türü. Saldırgan bir e-posta ekine URL ekler. Ek içindeki URL, kimlik bilgisi toplama ile aynı tekniği izler.
- **Kötü amaçlı yazılım bağlantısı**: İyi bilinen bir dosya paylaşım hizmetinde barındırılan bir dosyadan rastgele kod çalıştırır. Kullanıcıya gönderilen ileti bu kötü amaçlı dosyanın bağlantısını içerir. Dosyayı açmak, saldırganın hedefin cihazını tehlikeye atılmasına yardımcı olur.
- **Sürücü URL'si**: İletideki kötü amaçlı URL, kullanıcıyı sessizce çalışan ve/veya kullanıcının cihazına kod yükleyen tanıdık görünen bir web sitesine götürür.
- **OAuth Onayı Verme**: Kötü amaçlı URL, kullanıcılardan kötü amaçlı bir Azure Uygulaması için verilere izin vermelerini ister.

Açıklamadaki **Ayrıntıları görüntüle** bağlantısına tıklarsanız, tekniği ve teknikten kaynaklanan simülasyon adımlarını açıklayan bir ayrıntı açılır öğesi açılır.

:::image type="content" source="../../media/attack-sim-training-simulations-select-technique-sim-steps.png" alt-text="Seçme tekniği sayfasındaki kimlik bilgisi toplama tekniği için Ayrıntılar açılır öğesi" lightbox="../../media/attack-sim-training-simulations-select-technique-sim-steps.png":::

İşiniz bittiğinde **İleri'ye** tıklayın.

## <a name="name-and-describe-the-simulation"></a>Benzetimi adlandırma ve açıklama

**Ad benzetimi** sayfasında aşağıdaki ayarları yapılandırın:

- **Ad**: Simülasyon için benzersiz, açıklayıcı bir ad girin.
- **Açıklama**: Simülasyon için isteğe bağlı ayrıntılı bir açıklama girin.

İşiniz bittiğinde **İleri'ye** tıklayın.

## <a name="select-a-payload-and-login-page"></a>Bir yük ve oturum açma sayfası seçin

**Yükü ve oturum açma bilgilerini seçin** sayfasında, listeden mevcut bir yükü seçmeniz veya yeni bir yük oluşturmanız gerekir.

Ayrıca yükte kullanılan oturum açma sayfasını görüntüleyebilir, kullanılacak farklı bir oturum açma sayfası seçebilir veya kullanmak üzere yeni bir oturum açma sayfası oluşturabilirsiniz.

### <a name="payload"></a>Yükü

Her yük için aşağıdaki ayrıntılar gösterilir:

- **Yük adı**
- **Dil**: Yük içeriğinin dili. Microsoft'un yük kataloğu (genel), filtrelenebilen 10'undan fazla dilde yük sağlar.
- **Tıklama oranı**: Bu yüke kaç kişinin tıklamış olduğu.
- **Tahmin edilen risk oranı**: Microsoft 365 genelinde, bu yükte güvenliği tehlikeye atılacak kişilerin yüzdesini tahmin eden geçmiş veriler (yükü alan kullanıcıların/ toplam kullanıcı sayısı).
- **Başlatılan simülasyonlar** , bu yükün diğer simülasyonlarda kaç kez kullanıldığını sayar.

![Ara simgesinde.](../../media/m365-cc-sc-search-icon.png) **Arama** kutusuna yük adının bir kısmını yazabilir ve sonuçları filtrelemek için Enter tuşuna basabilirsiniz.

**Filtre'ye** tıklarsanız aşağıdaki filtreler kullanılabilir:

- **Karmaşıklık**: Yükteki olası bir saldırıyı (yazım hataları, aciliyet vb.) gösteren gösterge sayısına göre hesaplanır. Daha fazla göstergenin saldırı olarak tanımlanması daha kolaydır ve daha düşük karmaşıklığı gösterir. Kullanılabilir değerler şunlardır:
  - **Yüksek**
  - **Orta**
  - **Düşük**

- **Dil**: Kullanılabilir değerler şunlardır: **İngilizce**, **İspanyolca**, **Almanca**, **Japonca**, **Fransızca**, **Portekizce**, **Felemenkçe**, **İtalyanca**, **İsveççe**, **Çince (Basitleştirilmiş)**, **Norveççe Bokmål**, **Lehçe**, **Rusça**, **Fince**, **Korece**, **Türkçe**, **Macarca**, **İbranice**, **Tayca**, **Arapça**, **Vietnamca**, **Slovakça**, **Yunanca**, **Endonezya dili**, **Rumence**, **Slovence**, **Hırvat**, **Katalanca** veya **Diğer**.

- **Etiket ekleme**

- **Temaya göre filtrele**: Hesap **etkinleştirme**, **Hesap doğrulama**, **Faturalama**, **Posta temizleme**, **Alınan belge**, **Gider**, **Faks**, **Finans raporu**, **Gelen iletiler**, **Fatura**, **Alınan Öğeler**, **Oturum açma uyarısı**, **Alınan posta**, **Parola**, **Ödeme**, **Bordro**, **Kişiselleştirilmiş teklif**, **Karantina**, **Uzaktan çalışma**, **İletiyi gözden geçirme**, **Güvenlik güncelleştirmesi**, **Hizmet askıya alındı**, **İmza gerekiyor**, **Posta kutusu depolama alanını yükselt Posta kutusunu**, **Sesli mesajı** ve **Diğer'i** doğrulayın.

- **Markaya göre filtrele**: Kullanılabilir değerler şunlardır: **American Express**, **Capital One**, **DHL**, **DocuSign**, **Dropbox**, **Facebook**, **First American**, **Microsoft**, **Netflix**, **Scotiabank**, **SendGrid**, **Stewart Title**, **Tesco**, **Wells Fargo**, **Syrinx Cloud** ve **Diğer**.

- **Sektöre göre filtrele**: **Bankacılık**, **İş hizmetleri**, **Tüketici hizmetleri**, **Eğitim**, **Enerji**, **İnşaat**, **Danışmanlık**, **Finansal hizmetler**, **Kamu**, **Konaklama**, **Sigorta**, **Yasal**, **Kurye hizmetleri**, **BT**, **Sağlık**, **İmalat**, **Perakende**, **Telekom**, **Emlak**, ve **Diğer**.

- **Geçerli olay**: Kullanılabilir değerler **Evet** veya **Hayır'dır**.

- **Tartışmalı**: Kullanılabilir değerler **Evet** veya **Hayır'dır**.

Filtreleri yapılandırmayı bitirdiğinizde **Uygula**, **İptal veya**![ Filtreleri temizle simgesi **Filtreleri temizle'ye**](../../media/m365-cc-sc-clear-filters-icon.png) tıklayın.

Onay kutusunu seçerek listeden bir yük seçerseniz, ![Test yükü gönder simgesi.](../../media/m365-cc-sc-create-icon.png) Ana sayfada yük e-postasının bir kopyasını inceleme için kendinize (şu anda oturum açmış olan kullanıcı) gönderebileceğiniz **bir test** düğmesi görüntülenir.

Kendi yükünüzü oluşturmak için Yük oluştur simgesine tıklayın ![.](../../media/m365-cc-sc-create-icon.png) **Yük oluşturma**. Daha fazla bilgi için bkz. [Saldırı simülasyonu eğitimi için özel yük oluşturma](attack-simulation-training-payloads.md#create-payloads).

:::image type="content" source="../../media/attack-sim-training-simulations-select-payload.png" alt-text="Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi yük seçin sayfası" lightbox="../../media/attack-sim-training-simulations-select-payload.png":::

Listeden onay kutusunun dışındaki herhangi bir yere tıklayarak bir yük seçerseniz, yükle ilgili ayrıntılar açılır pencerede gösterilir:

- **Yük** sekmesi bir örnek ve yükle ilgili diğer ayrıntıları içerir.
- **Oturum Açma sayfası** sekmesi yalnızca Ek yüklerinde **Kimlik Bilgisi Toplama** veya **Bağlantı'da** kullanılabilir ve sonraki bölümde açıklanmaktadır.
- **Başlatılan Simülasyonlar** sekmesi **Benzetimi adı**, **Tıklama oranı**, **Risk altındaki hız** ve **Eylem'i** içerir.

:::image type="content" source="../../media/attack-sim-training-simulations-select-payload-details-payload-tab.png" alt-text="Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi yük ayrıntıları açılır öğesindeki Yük sekmesi" lightbox="../../media/attack-sim-training-simulations-select-payload-details-payload-tab.png":::

### <a name="login-page"></a>Oturum açma sayfası

> [!NOTE]
> **Oturum Açma sayfası** sekmesi yalnızca **Kimlik Bilgisi Toplama** veya **Ek yüklerinde bağlantı** olarak kullanılabilir.

Ayrıntılar açılır penceresini açmak için, satırda onay kutusu dışında herhangi bir yere tıklayarak yükü listeden seçin.

Yük ayrıntıları açılır öğesindeki **Oturum açma sayfası** sekmesi, yük için seçili olan oturum açma sayfasını gösterir.

Oturum açma sayfasının tamamını görüntülemek için, iki sayfalı oturum açma sayfaları için sayfanın altındaki **Sayfa 1** ve **Sayfa 2** bağlantılarını kullanın.

:::image type="content" source="../../media/attack-sim-training-simulations-select-payload-details-login-page-tab.png" alt-text="Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi yük ayrıntıları açılır öğesindeki oturum açma sayfası sekmesi" lightbox="../../media/attack-sim-training-simulations-select-payload-details-login-page-tab.png":::

Yükte kullanılan oturum açma sayfasını değiştirmek için Oturum açma sayfasını değiştir simgesine tıklayın ![.](../../media/m365-cc-sc-edit-icon.png) **Oturum açma sayfasını değiştirin**.

Görüntülenen **Oturum açma bilgilerini seçin sayfasında** , her oturum açma sayfası için aşağıdaki bilgiler gösterilir:

- **Ad**
- **Dil**
- **Kaynak**: Yerleşik oturum açma sayfaları için değer **Genel'dir**. Özel oturum açma sayfaları için değer **Kiracı'dır**.
- **Durum**: **Hazır** veya **Taslak**.
- **Oluşturan**: Yerleşik oturum açma sayfaları için değer **Microsoft'tur**. Özel oturum açma sayfaları için değer, oturum açma sayfasını oluşturan kullanıcının UPN değeridir.
- **Son değiştirme**
- **Eylemler**: Önizleme simgesine tıklayın ![.](../../media/m365-cc-sc-eye-icon.png) Oturum açma sayfasının önizlemesini görüntülemek için **önizleme**.

Listede oturum açma sayfası bulmak için Ara simgesini kullanın ![.](../../media/m365-cc-sc-search-icon.png) Oturum açma sayfasının adını bulmak için **arama** kutusu.

Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) Oturum açma sayfalarını **Kaynağa** veya Dile göre filtrelemek için **filtreleyin**.

:::image type="content" source="../../media/attack-sim-training-simulations-select-payload-select-login-page.png" alt-text="Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi yük ayrıntıları açılır öğesindeki Oturum açma sayfası sekmesindeki Oturum açma bilgilerini seçin sayfası" lightbox="../../media/attack-sim-training-simulations-select-payload-select-login-page.png":::

Yeni oturum açma sayfası oluşturmak için [Yeni oluştur simgesine tıklayın.](../../media/m365-cc-sc-create-icon.png) Son kullanıcı oturum açma sayfası oluşturma sihirbazını başlatmak için **yeni oluşturun**. Adımlar, **Saldırı simülasyonu eğitimi** \> **Sanal içerik kitaplığı** sekmesindeki **Oturum açma sayfalarıyla** aynıdır. Yönergeler için bkz. [Oturum açma sayfaları oluşturma](attack-simulation-training-login-pages.md#create-login-pages).

**Oturum açma seç sayfasına** geri dönün, oluşturduğunuz yeni oturum açma sayfasının seçili olduğunu doğrulayın ve **kaydet'e** tıklayın.

Yük ayrıntıları açılır menüsüne geri dönüp [Kapat simgesine tıklayın.](../../media/m365-cc-sc-close-icon.png) **Kapat'ı seçin**.

**Yük seçin ve oturum açın sayfasında** işiniz bittiğinde **İleri'ye** tıklayın.

## <a name="configure-oauth-payload"></a>OAuth Yükünü Yapılandırma

> [!NOTE]
> Bu sayfa yalnızca [Tekniği seçin](#select-a-social-engineering-technique) sayfasında **OAuth Onayı Ver'i** seçtiyseniz kullanılabilir. Aksi takdirde **Hedef kullanıcılar** sayfasına yönlendirilirsiniz.

**OAuth yükünü yapılandır** sayfasında aşağıdaki ayarları yapılandırın:

- **Uygulama adı**

- **Uygulama logosu**: Kullanılacak .png, .jpeg veya .gif dosyasını seçmek için **Gözat'a** tıklayın. Dosyayı seçtikten sonra kaldırmak için **Kaldır'a** tıklayın.

- **Uygulama kapsamını seçin**: Aşağıdaki değerlerden birini seçin:
  - **Kullanıcı takvimlerini okuma**
  - **Kullanıcı kişilerini okuma**
  - **Kullanıcı postasını okuma**
  - **Tüm sohbet iletilerini okuma**
  - **Kullanıcının erişebileceği tüm dosyaları okuma**
  - **Kullanıcı postasına okuma ve yazma erişimi**
  - **Postayı kullanıcı olarak gönderme**

## <a name="target-users"></a>Hedef kullanıcılar

**Hedef kullanıcılar** sayfasında simülasyonu alacak kullanıcıları seçin. Aşağıdaki ayarlardan birini yapılandırın:

- **Kuruluşunuzdaki tüm kullanıcıları dahil et**: Etkilenen kullanıcılar 10'lu listelerde gösterilir. Listede gezinmek için doğrudan kullanıcı listesinin altındaki **İleri** ve **Önceki** düğmelerini kullanabilirsiniz. Arama simgesini de kullanabilirsiniz ![.](../../media/m365-cc-sc-search-icon.png) Etkilenen kullanıcıları bulmak için sayfadaki **arama** simgesi.

- **Yalnızca belirli kullanıcıları ve grupları dahil et**: Aşağıdaki seçeneklerden birini belirleyin:
  - ![Kullanıcı ekle simgesi.](../../media/m365-cc-sc-create-icon.png) **Kullanıcı ekle**: Görüntülenen **Kullanıcı ekle** açılır listesinde, aşağıdaki ölçütlere göre kullanıcıları ve grupları bulabilirsiniz:

    - **Kullanıcıları veya grupları arayın**: Kutusuna, kullanıcı veya grubun **Ad** veya **Email adresinin** bir bölümünü yazıp Enter tuşuna basabilirsiniz. Sonuçların bir kısmını veya tümünü seçebilirsiniz. İşiniz bittiğinde **X kullanıcı ekle'ye** tıklayın.

      > [!NOTE]
      > **Kullanıcıları kategorilere göre filtrele** seçeneklerine dönmek için **Filtre ekle** düğmesine tıklanması, arama sonuçlarında seçtiğiniz tüm kullanıcıları veya grupları temizler.

    - **Kullanıcıları kategorilere göre filtrele**: Aşağıdaki seçeneklerden hiçbiri, bazıları veya tümü arasından seçim yapın:

      - **Önerilen kullanıcı grupları**: Aşağıdaki değerlerden birini seçin:
        - **Önerilen tüm kullanıcı grupları**
        - **Son üç ay içinde bir simülasyon tarafından hedeflenmemiş kullanıcılar**
        - **Tekrar eden suçlular**

      - **Kullanıcı etiketleri**: Kullanıcı etiketleri, belirli kullanıcı gruplarının tanımlayıcılarıdır (örneğin, Öncelik hesapları). Daha fazla bilgi için bkz. [Office 365 için Microsoft Defender'de kullanıcı etiketleri](user-tags.md).

          Aşağıdaki seçenekleri kullanın:

        - **Arama**: ![Kullanıcı etiketlerine göre ara simgesi.](../../media/m365-cc-sc-search-icon.png) **Kullanıcı etiketlerine göre arama** yapın, kullanıcı etiketinin bir kısmını yazıp Enter tuşuna basabilirsiniz. Sonuçların bir kısmını veya tümünü seçebilirsiniz.
        - **Tüm kullanıcı etiketlerini** seçin
        - Mevcut kullanıcı etiketlerini seçin.

      - **Departman**: Aşağıdaki seçenekleri kullanın:
        - **Arama**: ![Bölüme Göre Ara simgesinde.](../../media/m365-cc-sc-search-icon.png) **Departmana göre arama** yapın, Bölüm değerinin bir kısmını yazıp Enter tuşuna basabilirsiniz. Sonuçların bir kısmını veya tümünü seçebilirsiniz.
        - **Tüm Departman'ı** seçin
        - Mevcut Departman değerlerini seçin.

      - **Başlık**: Aşağıdaki seçenekleri kullanın:
        - **Arama**: ![Başlığa Göre Ara simgesi.](../../media/m365-cc-sc-search-icon.png) **Başlığa göre arama** yapın, Başlık değerinin bir kısmını yazıp Enter tuşuna basabilirsiniz. Sonuçların bir kısmını veya tümünü seçebilirsiniz.
        - **Tüm Başlığı** Seç
        - Mevcut Başlık değerlerini seçin.

      :::image type="content" source="../../media/attack-sim-training-simulations-target-users-filter-by-category.png" alt-text="Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi Hedef kullanıcılar sayfasında Kullanıcı filtrelemesi" lightbox="../../media/attack-sim-training-simulations-target-users-filter-by-category.png":::

      Ölçütlerinizi belirledikten sonra, etkilenen kullanıcılar görüntülenen **Kullanıcı listesi** bölümünde gösterilir ve burada bulunan alıcılardan bazılarını veya tümünü seçebilirsiniz.

      İşiniz bittiğinde **Uygula(x)**'e ve ardından **X kullanıcı ekle'ye** tıklayın.

  **Ana Hedef kullanıcılar** sayfasına döndüğünüzde ![Ara simgesini kullanabilirsiniz.](../../media/m365-cc-sc-search-icon.png) Etkilenen kullanıcıları bulmak için **arama** kutusu. Kullanıcıları sil simgesine de tıklayabilirsiniz ![.](../../media/m365-cc-sc-search-icon.png) Belirli kullanıcıları kaldırmak için **silin**.

- ![İçeri aktar simgesi.](../../media/m365-cc-sc-create-icon.png) **İçeri Aktarma**: Açılan iletişim kutusunda, satır başına bir e-posta adresi içeren bir CSV dosyası belirtin.

  CSV dosyasını seçtikten sonra, kullanıcı listesi içeri aktarılır ve **Hedeflenen kullanıcılar** sayfasında gösterilir. Arama simgesini kullanabilirsiniz ![.](../../media/m365-cc-sc-search-icon.png) Etkilenen kullanıcıları bulmak için **arama** kutusu. Hedeflenen kullanıcıları sil simgesine de tıklayabilirsiniz ![.](../../media/m365-cc-sc-delete-icon.png) Belirli kullanıcıları kaldırmak için **silin**.

İşiniz bittiğinde **İleri'ye** tıklayın.

## <a name="assign-training"></a>Eğitim atama

**Eğitim ata** sayfasında simülasyon için eğitimler atayabilirsiniz. Eğitimden geçen çalışanlar benzer saldırılara daha az duyarlı olduğundan her simülasyon için eğitim atamanızı öneririz. Aşağıdaki ayarlar kullanılabilir:

- **Eğitim içeriği tercihini seçin**: Aşağıdaki seçeneklerden birini belirleyin:
  - **Microsoft eğitim deneyimi**: Bu, yapılandırmak için aşağıdaki ilişkili seçenekleri içeren varsayılan değerdir:
    - Aşağıdaki seçeneklerden birini seçin:
      - **Benim için eğitim ata**: Bu varsayılan ve önerilen değerdir. Kullanıcının önceki simülasyon ve eğitim sonuçlarına göre eğitim atarız ve sihirbazın sonraki adımlarında seçimleri gözden geçirebilirsiniz.
      - **Eğitim kurslarını ve modülleri kendim seçin**: Bu değeri seçerseniz, sihirbazın bir sonraki adımında önerilen içeriğin yanı sıra tüm kullanılabilir kursları ve modülleri görmeye devam edebilirsiniz.
    - **Son tarih**: Aşağıdaki değerlerden birini seçin:
      - **Simülasyon sona erdikten 30 gün sonra**: Bu varsayılan değerdir.
      - **Simülasyon bittikten 15 gün sonra**
      - **Simülasyon bittikten 7 gün sonra**
  - **Özel URL'ye yeniden yönlendirme**: Bu değer, yapılandırmak için aşağıdaki ilişkili seçeneklere sahiptir:
    - **Özel eğitim URL'si** (gerekli)
    - **Özel eğitim adı** (gerekli)
    - **Özel eğitim açıklaması**
    - **Özel eğitim süresi (dakika cinsinden):** Varsayılan değer 0'dır ve bu da eğitim için belirtilen süre olmadığı anlamına gelir.
    - **Son tarih**: Aşağıdaki değerlerden birini seçin:
      - **Simülasyon sona erdikten 30 gün sonra**: Bu varsayılan değerdir.
      - **Simülasyon bittikten 15 gün sonra**
      - **Simülasyon bittikten 7 gün sonra**
  - **Eğitim yok**: Bu değeri seçerseniz sayfadaki tek seçenek, sizi [**Giriş sayfası**](#landing-page) sayfasına götüren **İleri** düğmesidir.

:::image type="content" source="../../media/attack-sim-training-simulations-assign-training-add-recommended-training.png" alt-text="Önerilen eğitimi Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi Eğitim ataması sayfasına ekleme seçeneği" lightbox="../../media/attack-sim-training-simulations-assign-training-add-recommended-training.png":::

### <a name="training-assignment"></a>Eğitim ataması

> [!NOTE]
> **Eğitim ataması** sayfası yalnızca önceki sayfada Eğitim **kursları ve modüllerini kendim seç** **Microsoft eğitim deneyimini** \> seçtiyseniz kullanılabilir.

**Eğitim ataması** sayfasında Eğitim ekle simgesine tıklayarak ![simülasyona eklemek istediğiniz eğitimleri seçin.](../../media/m365-cc-sc-create-icon.png) **Eğitimler ekleyin**.

Görüntülenen **Eğitim ekle** açılır öğesinde, aşağıdaki sekmelerde kullanılacak eğitimleri seçebilirsiniz:

- **Önerilen** sekmesi: Simülasyon yapılandırmasına göre önerilen yerleşik eğitimleri gösterir. Bunlar, önceki sayfada **Eğitimi benim için ata'yı** seçtiğinizde atanmış olan eğitimlerle aynıdır.
- **Tüm eğitimler** sekmesi: Kullanılabilir olan tüm yerleşik eğitimleri gösterir.

  Her eğitim için aşağıdaki bilgiler gösterilir:

  - **Eğitim adı**
  - **Kaynak**: Değer **Genel'dir**.
  - **Süre (mins)**
  - **Önizleme**: Eğitimi görmek için **Önizleme** düğmesine tıklayın.

  ![Ara simgesinde.](../../media/m365-cc-sc-search-icon.png) **Arama** kutusuna eğitim adının bir kısmını yazabilir ve geçerli sekmedeki sonuçları filtrelemek için Enter tuşuna basabilirsiniz.

  Geçerli sekmeden eklemek istediğiniz tüm eğitimleri seçin ve **ekle'ye** tıklayın.

Ana **Eğitim ödevi** sayfasına döndüğünüzde, seçtiğiniz eğitimler gösterilir. Her eğitim için aşağıdaki bilgiler gösterilir:

- **Eğitim adı**
- **Kaynak**
- **Süre (mins)**

Listedeki her eğitim için **, Ata** sütunundaki değerleri seçerek eğitimi kimlerin aldığını seçmeniz gerekir:

- **Tüm kullanıcılar**

  veya aşağıdaki değerlerden biri veya her ikisi:

- **Tıklanan yük**
- **Tehlikeye**

Gösterilen bir eğitimi kullanmak istemiyorsanız Eğitimi sil simgesine tıklayın ![.](../../media/m365-cc-sc-delete-icon.png) **Sil'i seçin**.

:::image type="content" source="../../media/attack-sim-training-training-assignment.png" alt-text="Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi Eğitim atama sayfası" lightbox="../../media/attack-sim-training-training-assignment.png":::

İşiniz bittiğinde **İleri'ye** tıklayın.

### <a name="landing-page"></a>Giriş sayfası

**Giriş sayfası sayfasında**, simülasyonda yükü açan kullanıcıların götürülecekleri web sayfasını yapılandırabilirsiniz.

Microsoft tarafından seçilmiş giriş sayfaları 12 dilde kullanılabilir: Çince (Basitleştirilmiş), Çince (Geleneksel), İngilizce, Fransızca, Almanca, İtalyanca, Japonca, Korece, Portekizce, Rusça, İspanyolca ve Felemenkçe.

- **Giriş sayfası tercihini seçin**: Kullanılabilir değerler şunlardır:
  - **Microsoft varsayılan giriş sayfasını kullan**: Bu, yapılandırmak için aşağıdaki ilişkili seçenekleri içeren varsayılan değerdir:
    - **Giriş sayfası düzenini seçin**: Kullanılabilir şablonlardan birini seçin.
    - **Logo ekle**: .png, .jpeg veya .gif dosyasını bulmak ve seçmek için **Gözat'a** tıklayın. Bozulmayı önlemek için logo boyutu en fazla 210 x 70 olmalıdır. Logoyu kaldırmak için **Kaldır'a** tıklayın.
    - **E-postaya yük göstergeleri ekleme**: Daha önce [Tekniği seç](#select-a-social-engineering-technique) sayfasında **Kötü amaçlı yazılım eki** veya **Kötü amaçlı yazılım bağlantısı'nı** seçtiyseniz bu ayar kullanılamaz.

    Sayfanın alt kısmındaki **Önizleme panelini aç** düğmesine tıklayarak sonuçların önizlemesini görüntüleyebilirsiniz.

  - **Özel URL kullanın**: Daha önce [Teknik seç](#select-a-social-engineering-technique) sayfasında **Kötü amaçlı yazılım eki** veya **Kötü amaçlı yazılım bağlantısı'nı** seçtiyseniz bu ayar kullanılamaz.

    **Özel URL kullan'ı** seçerseniz, görüntülenen **Özel giriş sayfası URL'sini girin** kutusuna URL'yi eklemeniz gerekir. Sayfada başka seçenek yoktur.

  - **Kendi giriş sayfanızı oluşturun**: Bu değer, yapılandırmak için aşağıdaki ilişkili seçeneklere sahiptir:
    - **E-postaya yük göstergeleri ekleme**:Bu ayar yalnızca aşağıdaki deyimlerin ikisi de doğruysa seçilebilir:
      - Teknik seçin sayfasında **Kimlik bilgisi toplama**, **Ekteki bağlantı**, **Sürücüye göre URL** veya **OAuth Onayı Verme'yi** [seçtiniz](#select-a-social-engineering-technique) .
      - Bu sayfadaki giriş sayfası **içeriğine Yük İçeriği Ekle** adlı **Dinamik etiketi** eklediniz.

    - Giriş sayfası içeriği: İki sekme kullanılabilir:
      - **Metin**: Giriş sayfanızı oluşturmak için zengin bir metin düzenleyicisi kullanılabilir. Tipik yazı tipi ve biçimlendirme ayarlarına ek olarak aşağıdaki ayarlar da kullanılabilir:
        - **Dinamik etiket**: Aşağıdaki etiketler arasından seçim yapın:

          |Etiket adı|Etiket değeri|
          |---|---|
          |**Kullanıcı adı ekle**|`${userName}`|
          |**Ad Ekle**|`${firstName}`|
          |**Soyadı Ekle**|`${lastName}`|
          |**UPN ekleme**|`${upn}`|
          |**Email ekle**|`${emailAddress}`|
          |**Bölüm Ekle**|`${department}`|
          |**Yönetici Ekle**|`${manager}`|
          |**Cep telefonu ekle**|`${mobilePhone}`|
          |**Şehir Ekle**|`${city}`|
          |**Gönderen adı ekle**|`${FromName}`|
          |**Gönderen e-postası ekleme**|`${FromEmail}`|
          |**Yük konu ekle**|`${EmailSubject}`|
          |**Payload içeriği ekleme**|`${EmailContent}`|
          |**Tarih Ekle**|`${date|MM/dd/yyyy|offset}`|

        - **Varsayılandan kullanın**: Başlamak için kullanılabilir bir şablon seçin. Düzenleme alanındaki metni ve düzeni değiştirebilirsiniz. Giriş sayfasını şablonun varsayılan metnine ve düzenine geri döndürmek **için Varsayılana sıfırla'ya** tıklayın.
    - **Kod**: HTML kodunu doğrudan görüntüleyebilir ve değiştirebilirsiniz.

    Sayfanın ortasındaki **Önizleme panelini aç** düğmesine tıklayarak sonuçların önizlemesini görüntüleyebilirsiniz.

İşiniz bittiğinde **İleri'ye** tıklayın.

> [!NOTE]
> Bazı ticari markalar, logolar, simgeler, insignias ve diğer kaynak tanımlayıcıları, yerel, eyalet ve federal tüzükler ve yasalar kapsamında yüksek koruma alır. Bu tür göstergelerin yetkisiz kullanımı, kullanıcıları cezai para cezaları da dahil olmak üzere cezalara tabi yapabilir. Kapsamlı bir liste olmasa da, buna Başkanlık, Başkan Yardımcısı ve Kongre mühürleri, CIA, FBI, Sosyal Güvenlik, Medicare ve Medicaid, Birleşik Devletler İç Gelir Servisi ve Olimpiyatlar dahildir. Bu ticari marka kategorilerinin ötesinde, herhangi bir üçüncü taraf ticari markanın kullanılması ve değiştirilmesi doğal bir risk taşır. Yükte kendi ticari markalarınızı ve logolarınızı kullanmak, özellikle de kuruluşunuzun kullanıma izin vermesinde daha az riskli olabilir. Yük oluştururken veya yapılandırırken nelerin kullanılması uygun veya uygun olmadığı hakkında başka sorularınız varsa, hukuk danışmanlarınıza danışmanız gerekir.

## <a name="select-end-user-notification"></a>Son kullanıcı bildirimini seçme

**Son kullanıcı bildirimini seçin** sayfasında aşağıdaki bildirim seçeneklerinden birini belirleyin:

- **Bildirimleri teslim etme**: Görüntülenen uyarı iletişim kutusunda **Devam'a** tıklayın. Bu seçeneği seçerseniz **İleri'ye** tıkladığınızda [Başlatma ayrıntıları](#launch-details) sayfasına yönlendirilirsiniz.

- **Microsoft varsayılan bildirimi (önerilen)**: Sayfada aşağıdaki ek ayarlar kullanılabilir:

  - **Varsayılan dili seçin**: Kullanılabilir değerler şunlardır: **İngilizce**, **İspanyolca**, **Almanca**, **Japonca**, **Fransızca**, **Portekizce**, **Felemenkçe**, **İtalyanca**, **İsveççe**, **Çince (Basitleştirilmiş)**, **Norveççe Bokmål**, **Lehçe**, **Rusça**, **Fince**, **Korece**, **Türkçe**, **Macarca**, **İbranice**, **Tayca**, **Arapça**, **Vietnamca**, **Slovakça**, **Yunan**, **Endonezya**, **Rumence**, **Slovence**, **Hırvat**, **Katalanca** veya **Diğer**.

  - Varsayılan olarak, aşağıdaki bildirimler dahil edilir:
    - **Microsoft pozitif takviye bildirimi**
    - **Microsoft varsayılan eğitim ataması bildirimi**
    - **Microsoft varsayılan eğitim anımsatıcı bildirimi**

    Her bildirim için aşağıdaki bilgiler sağlanır:
    - **Bildirimler**: Bildirimin adı.
    - **Dil**: Bildirim birden çok çeviri içeriyorsa, ilk iki dil doğrudan gösterilir. Kalan dilleri görmek için, sayısal simgenin üzerine gelin (örneğin, **+10**).
    - **Tür**: Aşağıdaki değerlerden biri:
      - **Pozitif pekiştirme bildirimi**
      - **Eğitim ataması bildirimi**
      - **Eğitim anımsatıcısı bildirimi**
    - **Teslim tercihleri**: **Pozitif pekiştirme bildirimi** ve **Eğitim anımsatıcısı bildirim** türleri için aşağıdaki değerler kullanılabilir
      - **Teslim etme**
      - **Kampanya sona erdikten sonra teslim**
      - **Kampanya sırasında teslim**
    - **Eylemler**: Görünüm simgesine ![tıklarsanız.](../../media/m365-cc-sc-view-icon.png) **Görünüm** simgesi, **Gözden geçir bildirimi** sayfası aşağıdaki bilgilerle birlikte görüntülenir:
      - **Önizleme** sekmesi: Kullanıcıların göreceği şekilde bildirim iletisini görüntüleyin.
        - İletiyi farklı dillerde görüntülemek için **Dil seçin** kutusunu kullanın.
        - Birden çok yük içeren simülasyonlar için bildirim iletisini seçmek için **Önizlemeye yük seçin** kutusunu kullanın.
      - **Ayrıntılar** sekmesi: Bildirimle ilgili ayrıntıları görüntüleyin:
        - **Bildirim açıklaması**
        - **Kaynak**: Yerleşik bildirimler için değer **Genel'dir**. Özel bildirimler için değer **Kiracı'dır**.
        - **Bildirim türü**: Aşağıdaki türlerden biri başlangıçta seçtiğiniz bildirimi temel alır:
          - **Pozitif pekiştirme bildirimi**
          - **Eğitim ataması bildirimi**
          - **Eğitim anımsatıcısı bildirimi**
        - **Değiştiren**
        - **Son değiştirme**

        İşlemi tamamladığınızda, **Kapat**'a tıklayın.

  **İleri'ye** tıkladığınızda [Başlatma ayrıntıları](#launch-details) sayfasına yönlendirilirsiniz.

- **Özelleştirilmiş son kullanıcı bildirimleri**: **İleri'ye** tıkladığınızda, sonraki bölümlerde açıklandığı gibi **Eğitim ataması bildirim** sayfasına yönlendirilirsiniz.

### <a name="training-assignment-notification"></a>Eğitim ataması bildirimi

**Eğitim ataması bildirim** sayfası yalnızca **[Son](#select-end-user-notification)** **kullanıcı bildirimini seçin sayfasında Özelleştirilmiş son kullanıcı bildirimleri'ni** seçtiğinizde kullanılabilir.

Bu sayfada aşağıdaki bildirimler ve yapılandırılan dilleri gösterilir:

- **Microsoft varsayılan eğitim ataması bildirimi**
- Daha önce oluşturduğunuz tüm özel eğitim atama bildirimleri.

  Bu bildirimler, konumundaki Saldırı simülasyonu eğitimi **Simülasyon içerik kitaplığı** sekmesindeki **Son kullanıcı bildirimlerinde** <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>de kullanılabilir. **Microsoft varsayılan eğitim ataması bildirimi** Genel **bildirimler** sekmesinde bulunur. Özel eğitim ataması bildirimleri **Kiracı bildirimleri** sekmesinde bulunur. Daha fazla bilgi için bkz. [Saldırı simülasyonu eğitimi için son kullanıcı bildirimleri](attack-simulation-training-end-user-notifications.md).

Var olan bir eğitim ataması bildirimini seçebilir veya kullanmak için yeni bir bildirim oluşturabilirsiniz:

- Mevcut bir bildirimi seçmek için bildirim adının yanındaki boş alana tıklayın. Bildirim adına tıklarsanız bildirim seçilir ve önizleme açılır öğesi görüntülenir. Bildirimin seçimini kaldırmak için bildirimin yanındaki onay kutusunu temizleyin.
- Var olan bir bildirimi aramak için Ara simgesini kullanın ![.](../../media/m365-cc-sc-search-icon.png) Adı aramak için **arama kutusu.**

  Kullanmak istediğiniz bildirimi seçin ve **İleri'ye** tıklayın.

- Yeni bildirim oluşturmak ve kullanmak için Yeni oluştur simgesine tıklayın ![.](../../media/m365-cc-sc-create-icon.png) **Yeni oluşturun**.

#### <a name="create-new-training-assignment-notification-wizard"></a>Yeni eğitim ataması bildirim sihirbazı oluşturma

Yeni oluştur simgesine ![tıkladıysanız.](../../media/m365-cc-sc-create-icon.png) **Eğitim ataması bildirim** sayfasında **yeni oluşturun**; bildirim oluşturma sihirbazı açılır.

Oluşturma adımları [, Son kullanıcı bildirimleri oluşturma](attack-simulation-training-end-user-notifications.md#create-end-user-notifications) bölümünde açıklandığı gibi aynıdır.

> [!NOTE]
> **Ayrıntıları tanımla** sayfasında, **Bildirim türünü seçin** için **Eğitim atama bildirimi** değerini seçtiğinizden emin olun.

İşiniz bittiğinde, yeni oluşturduğunuz **bildirimin listede göründüğü Eğitim ataması bildirim** sayfasına geri dönersiniz.

Kullanmak istediğiniz bildirimi seçin ve **İleri'ye** tıklayın.

### <a name="training-reminder-notification"></a>Eğitim anımsatıcısı bildirimi

**Eğitim anımsatıcısı bildirim** sayfası yalnızca **[Son kullanıcı](#select-end-user-notification)** **bildirimini seçin sayfasında Özelleştirilmiş son kullanıcı bildirimleri'ni** seçtiğinizde kullanılabilir.

- **Anımsatıcı bildirimi için sıklık ayarla**: **Haftalık** (varsayılan) veya **Haftada iki kez'yi** seçin.

- **Anımsatıcı bildirimi seçin**: Bu bölümde aşağıdaki bildirimler ve yapılandırılan dilleri gösterilir:

  - **Microsoft varsayılan eğitim anımsatıcı bildirimi**
  - Daha önce oluşturduğunuz tüm özel eğitim anımsatıcı bildirimleri.

    Bu bildirimler, konumundaki Saldırı simülasyonu eğitimi **Simülasyon içerik kitaplığı** sekmesindeki **Son kullanıcı bildirimlerinde** <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>de kullanılabilir. **Microsoft varsayılan eğitim anımsatıcı bildirimi** Genel **bildirimler** sekmesinde bulunur. Özel eğitim anımsatıcısı bildirimleri **Kiracı bildirimleri** sekmesinde bulunur. Daha fazla bilgi için bkz. [Saldırı simülasyonu eğitimi için son kullanıcı bildirimleri](attack-simulation-training-end-user-notifications.md).

  Var olan bir eğitim anımsatıcısı bildirimini seçebilir veya kullanmak için yeni bir bildirim oluşturabilirsiniz:

  - Mevcut bir bildirimi seçmek için bildirim adının yanındaki boş alana tıklayın. Bildirim adına tıklarsanız bildirim seçilir ve önizleme açılır öğesi görüntülenir. Bildirimin seçimini kaldırmak için bildirimin yanındaki onay kutusunu temizleyin.
  - Var olan bir bildirimi aramak için Ara simgesini kullanın ![.](../../media/m365-cc-sc-search-icon.png) Adı aramak için **arama kutusu.**

    Kullanmak istediğiniz bildirimi seçin ve **İleri'ye** tıklayın.

  - Yeni bildirim oluşturmak ve kullanmak için Yeni oluştur simgesine tıklayın ![.](../../media/m365-cc-sc-create-icon.png) **Yeni oluşturun**.

#### <a name="create-new-training-reminder-notification-wizard"></a>Yeni eğitim anımsatıcısı bildirim sihirbazı oluşturma

Yeni oluştur simgesine ![tıkladıysanız.](../../media/m365-cc-sc-create-icon.png) **Eğitim anımsatıcısı bildirim** sayfasında **yeni oluşturun**; bildirim oluşturma sihirbazı açılır.

Oluşturma adımları [, Son kullanıcı bildirimleri oluşturma](attack-simulation-training-end-user-notifications.md#create-end-user-notifications) bölümünde açıklandığı gibi aynıdır.

> [!NOTE]
> **Ayrıntıları tanımla** sayfasında, **Bildirim türünü seçin** için **Eğitim anımsatıcı bildirimi** değerini seçtiğinizden emin olun.

İşiniz bittiğinde, yeni oluşturduğunuz **bildirimin listede göründüğü Eğitim anımsatıcısı bildirim** sayfasına geri dönersiniz.

Kullanmak istediğiniz bildirimi seçin ve **İleri'ye** tıklayın.

### <a name="positive-reinforcement-notification"></a>Pozitif pekiştirme bildirimi

**Pozitif pekiştirme bildirimi** sayfası yalnızca **[Son kullanıcı](#select-end-user-notification)** **bildirimlerini seçin sayfasında Özelleştirilmiş son kullanıcı bildirimleri'ni** seçtiğinizde kullanılabilir.

- **Teslim tercihleri**: Aşağıdaki değerlerden birini seçin:

  - **Teslim etme**: Bu seçeneği seçerseniz **, İleri'ye** tıkladığınızda [Başlatma ayrıntıları](#launch-details) sayfasına yönlendirilirsiniz.

  - **Kullanıcı kimlik avı ve kampanya sona erdikten** sonra **teslim etme veya Kullanıcı kimlik avı bildirdikten hemen sonra teslim etme**: Bu bölümlerde, görüntülenen **Pozitif bir pekiştirme bildirimi seçin** bölümünde aşağıdaki bildirimler ve yapılandırılan dilleri gösterilir:

  - **Microsoft varsayılan pozitif takviye bildirimi**
  - Daha önce oluşturduğunuz tüm özel pozitif takviye bildirimleri.

    Bu bildirimler, konumundaki Saldırı simülasyonu eğitimi **Simülasyon içerik kitaplığı** sekmesindeki **Son kullanıcı bildirimlerinde** <https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>de kullanılabilir. **Microsoft varsayılan pozitif takviye bildirimi** Genel **bildirimler** sekmesinde bulunur. Kiracı bildirimleri sekmesinde özel pozitif takviye **bildirimleri** bulunur. Daha fazla bilgi için bkz. [Saldırı simülasyonu eğitimi için son kullanıcı bildirimleri](attack-simulation-training-end-user-notifications.md).

  Mevcut bir pozitif takviye bildirimi seçebilir veya kullanmak için yeni bir bildirim oluşturabilirsiniz:

  - Mevcut bir bildirimi seçmek için bildirim adının yanındaki boş alana tıklayın. Bildirim adına tıklarsanız bildirim seçilir ve önizleme açılır öğesi görüntülenir. Bildirimin seçimini kaldırmak için bildirimin yanındaki onay kutusunu temizleyin.
  - Var olan bir bildirimi aramak için Ara simgesini kullanın ![.](../../media/m365-cc-sc-search-icon.png) Adı aramak için **arama kutusu.**

    Kullanmak istediğiniz bildirimi seçin ve **İleri'ye** tıklayın.

  - Yeni bildirim oluşturmak ve kullanmak için Yeni oluştur simgesine tıklayın ![.](../../media/m365-cc-sc-create-icon.png) **Yeni oluşturun**.

#### <a name="create-new-positive-reinforcement-notification-wizard"></a>Yeni pozitif takviye bildirimi oluşturma sihirbazı

Yeni oluştur simgesine ![tıkladıysanız.](../../media/m365-cc-sc-create-icon.png) **Pozitif pekiştirme bildirimi** sayfasında **yeni bir oluşturma** sihirbazı açılır.

Oluşturma adımları [, Son kullanıcı bildirimleri oluşturma](attack-simulation-training-end-user-notifications.md#create-end-user-notifications) bölümünde açıklandığı gibi aynıdır.

> [!NOTE]
> **Ayrıntıları tanımla** sayfasında Bildirim **türünü seçin** için **Pozitif destek bildirimi** değerini seçtiğinizden emin olun.

İşiniz bittiğinde, yeni oluşturduğunuz **bildirimin listede göründüğü Pozitif pekiştirme bildirimi** sayfasına geri dönersiniz.

Kullanmak istediğiniz bildirimi seçin ve **İleri'ye** tıklayın.

## <a name="launch-details"></a>Başlatma ayrıntıları

**Başlatma ayrıntıları** sayfasında simülasyonu ne zaman başlatabileceğinizi ve simülasyonu ne zaman sonlandırabileceğinizi seçersiniz. Belirttiğiniz bitiş tarihinden sonra bu simülasyonla etkileşimi yakalamayı durduracağız.

Aşağıdaki ayarlar kullanılabilir:

- Aşağıdaki değerlerden birini seçin:
  - **bitirdiğim anda bu simülasyonu başlat**
  - **Bu simülasyonu daha sonra başlatılacak şekilde zamanlayın**: Bu değer, yapılandırmak için aşağıdaki ilişkili seçeneklere sahiptir:
    - **Başlatma tarihini seçin**
    - **Başlatma zamanını seçin**
- **Benzetimi sona erdirecek gün sayısını yapılandırın**: Varsayılan değer 2'dir.
- **Bölge algılamalı saat dilimi teslimini etkinleştirme**: Çalışanlarınıza bölgelerine göre çalışma saatleri içinde sanal saldırı iletileri iletin.
- **Toplanan sürücüye göre teknik ara verileri görüntüleme sayfası**: Sürücüye göre URL tekniği saldırıları için görünen katmanı gösterebilirsiniz. Bu katmanı gizlemek ve doğrudan giriş sayfasına gitmek için bu seçeneği kaldırın.

- **Toplanan sürücüye göre teknik ara verileri görüntüleme sayfası**: Bu ayar yalnızca [bir teknik seçin sayfasında](#select-a-social-engineering-technique) **Drive-by URL'sini** seçtiyseniz kullanılabilir. Sürücüye göre URL tekniği saldırıları için ortaya çıkan katmanı gösterebilirsiniz. Katmanı gizlemek ve doğrudan giriş sayfasına gitmek için bu seçeneği belirtmeyin.

İşiniz bittiğinde **İleri'ye** tıklayın.

## <a name="review-simulation"></a>Benzetimi gözden geçirme

**Simülasyonu gözden geçir** sayfasında simülasyonunuzun ayrıntılarını gözden geçirebilirsiniz.

![Test gönder simgesine tıklayın.](../../media/m365-cc-sc-send-icon.png) Yük e-postasının bir kopyasını inceleme için kendinize (şu anda oturum açmış olan kullanıcı) göndermek için **bir test düğmesi gönderin**.

Bölümün içindeki ayarları değiştirmek için her bölümde **Düzenle'yi** seçebilirsiniz. Ya da **Geri'ye** tıklayabilir veya sihirbazdaki belirli bir sayfayı seçebilirsiniz.

İşiniz bittiğinde **Gönder'e** tıklayın.

:::image type="content" source="../../media/attack-sim-training-simulations-review-simulation.png" alt-text="Microsoft 365 Defender portalındaki Saldırı simülasyonu eğitimi simülasyon sayfasını gözden geçirin" lightbox="../../media/attack-sim-training-simulations-review-simulation.png":::
