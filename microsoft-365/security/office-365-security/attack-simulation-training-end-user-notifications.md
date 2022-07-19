---
title: Saldırı simülasyonu eğitimi için son kullanıcı bildirimleri
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Yöneticiler, Office 365 için Microsoft Defender Plan 2'de Saldırı simülasyonu eğitimi için son kullanıcı bildirim e-posta iletileri oluşturmayı öğrenebilir.
ms.technology: mdo
ms.openlocfilehash: b26c8060fb869ea9e02ab06396a5a91281bcf3f0
ms.sourcegitcommit: a7cd723fd62b4b0aae9c2c2df04ead3c28180084
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/02/2022
ms.locfileid: "66861751"
---
# <a name="end-user-notifications-for-attack-simulation-training"></a>Saldırı simülasyonu eğitimi için son kullanıcı bildirimleri

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 2](defender-for-office-365.md)

Microsoft 365 E5 veya Office 365 için Microsoft Defender Plan 2'de saldırı simülasyonu eğitimi bölümünde, son kullanıcı bildirimleri [simülasyonlar veya simülasyon otomasyonları](attack-simulation-training.md) sonucunda kullanıcılara gönderilen e-posta iletileridir.[](attack-simulation-training-simulation-automations.md) Aşağıdaki son kullanıcı bildirimi türleri kullanılabilir:

- **Pozitif pekiştirme bildirimi**: Kullanıcılar sanal kimlik avı iletisi bildirdiğinde gönderilir.
- **Simülasyon bildirimi**: Kullanıcılar bir simülasyon veya simülasyon otomasyonuna dahil edildiğinde gönderilir, ancak hiçbir eğitim seçilmez.
- **Eğitim atama bildirimi**: Kullanıcılara simülasyon veya simülasyon otomasyonları sonucunda gerekli eğitimler atandığında gönderilir.
- **Eğitim anımsatıcı bildirimi**: Gerekli eğitimler için anımsatıcı olarak gönderilir.

Kullanılabilir son kullanıcı bildirimlerini görmek için adresinden Microsoft 365 Defender portalını <https://security.microsoft.com>açın **Email & işbirliği** \> **Saldırı simülasyonu eğitimi** \> **Simülasyon içerik kitaplığı** sekmesine \> gidin ve **son kullanıcı bildirimleri'ni** seçin. **Doğrudan Son kullanıcı bildirimleri'ni** seçebileceğiniz **Simülasyon içerik kitaplığı** sekmesine gitmek için kullanın<https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>.

**Son kullanıcı bildirimlerinin** iki sekmesi vardır:

- **Genel bildirimler**: Yerleşik, değiştirilemeyen bildirimleri içerir.
- **Kiracı bildirimleri**: Oluşturduğunuz özel bildirimleri içerir.

Her bildirim için aşağıdaki bilgiler gösterilir:

- **Bildirimler**: Bildirimin adı.
- **Dil**: Bildirim birden çok çeviri içeriyorsa, ilk iki dil doğrudan gösterilir. Kalan dilleri görmek için, sayısal simgenin üzerine gelin (örneğin, **+10**).
- **Tür**: Değer **Pozitif pekiştirme bildirimi**, **Simülasyon bildirimi**, **Eğitim atama bildirimi** veya **Eğitim anımsatıcı bildirimidir**.
- **Kaynak**: Yerleşik bildirimler için değer **Genel'dir**. Özel bildirimler için değer **Kiracı'dır**.
- **Durum**: Değer **Hazır** veya **Taslak'tır**. **Genel bildirimler** sekmesinde değer her zaman **Hazır'dır**.
- **Bağlantılı simülasyonlar**: Bildirimi kullanan [simülasyonların](attack-simulation-training.md) veya [simülasyon otomasyonlarının](attack-simulation-training-simulation-automations.md) toplam sayısı.
- **Oluşturan**: Yerleşik bildirimler için değer **Microsoft'tur**. Özel bildirimler için değer, bildirimi oluşturan kullanıcının UPN değeridir.
- **Oluşturma zamanı**
- **Değiştiren**
- **Son değiştirme zamanı**

Listede bir bildirim bulmak için Ara simgesini kullanın ![.](../../media/m365-cc-sc-search-icon.png) Bildirimin adını bulmak için **arama** kutusu.

Bildirimleri türe göre gruplandırmak için Gruplandır simgesine tıklayın ![.](../../media/m365-cc-sc-group-icon.png) **Gruplandır'ı** ve ardından **Bildirim türü'nü** seçin. Bildirimlerin grubunu çözmek için **Yok'a** tıklayın.

Yalnızca **Kiracı bildirimleri** sekmesinde Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) bildirimlerini bir veya daha fazla dile göre filtrelemek için.

Görüntülenen bir veya daha fazla sütunu kaldırmak için Sütunları özelleştir simgesine tıklayın ![.](../../media/m365-cc-sc-customize-icon.png) **Sütunları özelleştirin**.

Listeden bir bildirim seçtiğinizde, aşağıdaki bilgilerle birlikte bir ayrıntılar açılır öğesi görüntülenir:

- **Önizleme** sekmesi: Kullanıcıların göreceği şekilde bildirim iletisini görüntüleyin. İletiyi farklı dillerde görüntülemek için **Dil seçin** kutusunu kullanın.
- **Ayrıntılar** sekmesi: Bildirimle ilgili ayrıntıları görüntüleyin:
  - **Bildirim açıklaması**
  - **Kaynak**: Yerleşik bildirimler için değer **Genel'dir**. Özel bildirimler için değer **Kiracı'dır**.
  - **Bildirim türü**
  - **Değiştiren**
  - **Son değiştirme**
  - **Simülasyon**
    - **Simülasyon adları**
    - **Simülasyon durumu**
    - **Bitiş:**

Yalnızca **Kiracı bildirimleri** sekmesindeki ayrıntılar açılır menüsünde **Bildirimi düzenle'ye** tıklayarak bildirimi değiştirin.

## <a name="create-end-user-notifications"></a>Son kullanıcı bildirimleri oluşturma

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Email & işbirliği** \> **Saldırı simülasyonu eğitimi** \> **Simülasyon içerik kitaplığı** sekmesine \> gidin ve **son kullanıcı bildirimleri'ni** seçin. **Doğrudan Son kullanıcı bildirimleri'ni** seçebileceğiniz **Simülasyon içerik kitaplığı** sekmesine gitmek için kullanın<https://security.microsoft.com/attacksimulator?viewid=simulationcontentlibrary>.

2. **Kiracı bildirimleri** sekmesinde Yeni oluştur simgesine tıklayın![.](../../media/m365-cc-sc-create-icon.png) Son kullanıcı bildirim sihirbazını başlatmak için **yeni oluşturun**.

   > [!NOTE]
   > Oluşturma sihirbazı sırasında herhangi bir noktada Kaydet **ve kapat'a** tıklayarak ilerlemenizi kaydedebilir ve bildirimi daha sonra yapılandırmaya devam edebilirsiniz. Son kullanıcı **bildirimleri'ndeki Kiracı bildirimleri** sekmesindeki bildirimi seçip Otomasyonu düzenle simgesine tıklayarak ![**kaldığınız** yerden devam edebilirsiniz.](../../media/m365-cc-sc-edit-icon.png) **Otomasyonu düzenleyin**. Kısmen tamamlanmış bildirimin **Durum** değeri **Taslak** olacaktır.

3. **Ayrıntıları tanımla** sayfasında**, aşağıdaki ayarları yapılandırın:
   - **Bildirim türünü seçin**: Aşağıdaki değerlerden birini seçin:
     - **Pozitif pekiştirme bildirimi**
     - **Simülasyon bildirimi**
     - **Eğitim ataması bildirimi**
     - **Eğitim anımsatıcısı bildirimi**
   - **Ad**: Benzersiz bir ad girin.
   - **Açıklama**: İsteğe bağlı bir açıklama girin.

   İşiniz bittiğinde **İleri'ye** tıklayın.

4. **İçerik tanımla** sayfasında, kullanılabilen tek ayar **İş dilinde içerik ekle** düğmesidir. Buna tıkladığınızda, aşağıdaki ayarları içeren **Varsayılan dilde içerik ekle** açılır öğesi görüntülenir:
   - **Görünen addan**
   - **E-posta adresinden**
   - **E-postanın dilini seçin**: Listeden bir dil seçin.
   - **Bunu varsayılan dil olarak işaretleyin**: Bildirim için ilk ve tek dil olduğundan, bu değer seçilir ve değiştiremezsiniz.
   - **Konu**: Kimlik **avı bildirdiğiniz için** varsayılan değer Teşekkürler'dir, ancak bunu değiştirebilirsiniz.
   - **E-postayı içeri aktar**: İsteğe bağlı olarak bu düğmeye ve ardından **Dosya seç'e** tıklayarak var olan bir düz metin iletisi dosyasını içeri aktarabilirsiniz.
   - Email içerik alanı: İki sekme kullanılabilir:
     - **Metin** sekmesi: Bildirim e-postanızı oluşturmak için zengin bir metin düzenleyicisi kullanılabilir. Tipik yazı tipi ve biçimlendirme ayarlarına ek olarak aşağıdaki ayarlar da kullanılabilir:
       - **Dinamik etiket**: Aşağıdaki etiketler arasından seçim yapın:
         - **Ad ekle**
         - **Soyadını ekle**
         - **UPN ekleme**
         - **E-posta adresi ekle**
         - **Yük ekle**
     - **Kod** sekmesi: HTML kodunu doğrudan görüntüleyebilir ve değiştirebilirsiniz.

   Sayfanın üst kısmındaki **E-posta** önizleme düğmesine tıklayarak sonuçların önizlemesini görüntüleyebilirsiniz.

   Bitirdiğinizde, **Kaydet**'i tıklatın.

   Yeni oluşturduğunuz bildirimin aşağıdaki bilgilerle özetlendiği **İçerik tanımla** sayfasına geri dönersiniz:

   - **Dil**
   - **Konu**
   - **Kategori**
   - **Eylemler**: Aşağıdaki simgeler kullanılabilir:
     - ![Düzenle simgesi.](../../media/m365-cc-sc-edit-icon.png) **Düzenleyin**
     - ![Görünüm simgesi.](../../media/m365-cc-sc-view-icon.png) **Görünüm**
     - ![Sil simgesi.](../../media/m365-cc-sc-delete-icon.png) **Sil**: Bildirimin yalnızca dil sürümü varsa, silemezsiniz.

   Bildirimin farklı bir dilde sürümünü eklemek için Çeviri ekle simgesine tıklayın ![.](../../media/m365-cc-sc-create-icon.png). Görüntülenen **Çeviri ekle** açılır penceresinde, daha önce açıklanan **Varsayılan dilde içerik ekle açılır öğesinde** olduğu gibi aynı ayarlar sağlanır. Tek fark, bunu ek çevirilerde **varsayılan dil olarak işaretle'yi** seçebilmenizdir.

   İşiniz bittiğinde **Kaydet'e** tıklayın

   Bildirimin çevrilmiş sürümlerini desteklenen 12 dilde oluşturmak için bu adımları gerektiği kadar tekrarlayabilirsiniz.

   İşiniz bittiğinde **İleri'ye** tıklayın

5. **Bildirimi gözden geçir** sayfasında, bildiriminizin ayrıntılarını gözden geçirebilirsiniz.

   Bölümün içindeki ayarları değiştirmek için her bölümde **Düzenle'yi** seçebilirsiniz. Ya da **Geri'ye** tıklayabilir veya sihirbazdaki belirli bir sayfayı seçebilirsiniz.

   İşiniz bittiğinde **Gönder'e** tıklayın.

   **Yeni simülasyon bildirimi oluşturuldu** sayfasında, bağlantıları kullanarak yeni bir bildirim oluşturabilir, simülasyon başlatabilir veya tüm bildirimleri görüntüleyebilirsiniz.

   İşiniz bittiğinde **Bitti'ye** tıklayın.

Son kullanıcı **bildirimleri'ndeki Kiracı bildirimleri** sekmesine **döndüğünüzde**, oluşturduğunuz bildirim artık listeleniyor.

## <a name="modify-end-user-notifications"></a>Son kullanıcı bildirimlerini değiştirme

Genel bildirimler sekmesinde yerleşik **bildirimleri** değiştiremezsiniz. Özel bildirimleri yalnızca **Kiracı** bildirimleri sekmesinde değiştirebilirsiniz.

**Kiracı bildirimleri** sekmesinde var olan bir özel bildirimi değiştirmek için aşağıdaki adımlardan birini yapın:

- Onay kutusuna tıklayarak listeden bildirimi seçin. Düzenle simgesine ![tıklayın.](../../media/m365-cc-sc-edit-icon.png) Görüntülenen **Düzenle** simgesi.
- Listedeki bildirimin **Bildirimler** ve **Dil** değerleri arasında **⋮** (**Eylemler**) öğesine tıklayın ve ardından Düzenle simgesi'ni seçin![.](../../media/m365-cc-sc-edit-icon.png) **Düzenle'yi seçin**.
- Onay kutusu dışında satırda herhangi bir yere tıklayarak listeden bildirimi seçin. Açılan ayrıntılar açılır listesinde **Bildirimi düzenle'ye** tıklayın.

Son kullanıcı bildirim sihirbazı, seçili bildirimin ayarları ve değerleriyle birlikte açılır. Adımlar, [Son kullanıcı bildirimleri oluşturma bölümünde açıklanan adımlarla](#create-end-user-notifications) aynıdır.

## <a name="copy-end-user-notifications"></a>Son kullanıcı bildirimlerini kopyalama

**Kiracı bildirimleri** veya **Genel bildirimler** sekmelerinde var olan bir bildirimi kopyalamak için aşağıdaki adımlardan birini yapın:

- Onay kutusuna tıklayarak listeden bildirimi seçin ve ardından Kopya oluştur simgesine ![tıklayın.](../../media/m365-cc-sc-edit-icon.png) Görüntülenen **bir kopyalama simgesi oluşturun**.
- Listedeki **bildirimin Bildirimler** ve **Dil** değerleri arasında **⋮** (**Eylemler**) öğesine tıklayın ve ardından Kopya oluştur simgesi'ni seçin![.](../../media/m365-cc-sc-edit-icon.png) **Bir kopya oluşturun**.

**Kiracı bildirimleri** sekmesinde özel bir bildirim kopyaladığınızda, bildirimin "\<OriginalName\>- Kopyala" adlı bir kopyası listede bulunur.

**Genel bildirimler** sekmesinde yerleşik bir bildirimi kopyaladığınızda, **Kopya oluştur** iletişim kutusu görüntülenir. İletişim kutusu bildirimin bir kopyasının oluşturulduğunu onaylar ve **Kiracı bildirimleri** sekmesinde kullanılabilir. **Kiracı bildirimine git'e** tıklarsanız **, kopyalanan yerleşik bildirimin** listede "\<OriginalName\> - Kopyala" olarak adlandırıldığı Kiracı bildirimleri sekmesine yönlendirilirsiniz. İletişim kutusunda **Burada kal'a** tıklarsanız **Genel bildirimler** sekmesine dönersiniz.

Kopya oluşturulduktan sonra, [daha önce açıklandığı](#modify-end-user-notifications) gibi değiştirebilirsiniz.

> [!NOTE]
> Bildirim sihirbazındaki **Varsayılan dilde içerik ekle açılır menüsündeki Varsayılandan** **kullan** denetimi, yerleşik bildirimin içeriğini kopyalamanıza olanak tanır.

## <a name="remove-notifications"></a>Bildirimleri kaldırma

Genel bildirimler sekmesinden yerleşik **bildirimleri** kaldıramazsınız. Özel bildirimleri yalnızca **Kiracı** bildirimleri sekmesinde kaldırabilirsiniz.

**Kiracı bildirimleri** sekmesinden var olan bir özel bildirimi kaldırmak için aşağıdaki adımlardan birini yapın:

- Onay kutusuna tıklayarak listeden bildirimi seçin ve ardından Sil simgesine ![tıklayın.](../../media/m365-cc-sc-delete-icon.png) Görüntülenen **Sil** simgesi.
- Listedeki bildirimin **Bildirimler** ve **Dil** değerleri arasında **⋮** (**Eylemler**) öğesine tıklayın ve ardından Sil simgesi'ni seçin![.](../../media/m365-cc-sc-delete-icon.png) **Sil'i seçin**.

## <a name="related-links"></a>İlgili bağlantılar

[Saldırı simülasyonu eğitimini kullanmaya başlama](attack-simulation-training-get-started.md)

[Kimlik avı saldırısı simülasyonu oluşturma](attack-simulation-training.md)

[Saldırı simülasyonu eğitimi için simülasyon otomasyonları](attack-simulation-training-simulation-automations.md)
