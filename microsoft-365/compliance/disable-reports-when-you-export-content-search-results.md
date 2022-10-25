---
title: İçerik Arama sonuçlarını dışarı aktarırken raporları devre dışı bırakma
description: Microsoft Purview uyumluluk portalı bir İçerik Aramasının sonuçlarını dışarı aktardığınızda raporları devre dışı bırakmak için yerel bilgisayarınızda Windows Kayıt Defteri'ni düzenleyin.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.collection:
- tier1
- purview-compliance
- content-search
ms.openlocfilehash: 13e47bc69a72ef5ebfcd38f2dee4c0652b0853f2
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687624"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>İçerik Arama sonuçlarını dışarı aktarırken raporları devre dışı bırakma

Microsoft Purview uyumluluk portalı bir İçerik Aramasının sonuçlarını dışarı aktarmak için eBulma Dışarı Aktarma aracını kullandığınızda, araç dışarı aktarılan içerik hakkında ek bilgi içeren iki raporu otomatik olarak oluşturur ve dışarı aktarır. Bu raporlar Results.csv dosyası ve Manifest.xml dosyasıdır (bu raporların ayrıntılı açıklamaları için bu makalenin [Dışarı aktarma raporlarını devre dışı bırakma hakkında sık sorulan sorular](#frequently-asked-questions-about-disabling-export-reports) bölümüne bakın). Bu dosyalar çok büyük olabileceğinden, indirme süresini hızlandırabilir ve bu dosyaların dışarı aktarılmasını engelleyerek disk alanından tasarruf edebilirsiniz. Bunu yapmak için, arama sonuçlarını dışarı aktarmak için kullandığınız bilgisayardaki Windows Kayıt Defteri'ni değiştirebilirsiniz. Raporları daha sonra eklemek isterseniz kayıt defteri ayarını düzenleyebilirsiniz. 
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="create-registry-settings-to-disable-the-export-reports"></a>Dışarı aktarma raporlarını devre dışı bırakmak için kayıt defteri ayarları oluşturma

Sonuçları bir içerik aramasını dışarı aktarmak için kullanacağınız bilgisayarda aşağıdaki yordamı uygulayın.
  
1. Açıksa eBulma Dışarı Aktarma aracını kapatın.
  
2. Hangi dışarı aktarma raporunu devre dışı bırakmak istediğinize bağlı olarak aşağıdaki adımlardan birini veya her ikisini gerçekleştirin.

    - **Results.csv**

      Bir .reg dosya adı soneki kullanarak aşağıdaki metni bir Windows kayıt defteri dosyasına kaydedin; örneğin, DisableResultsCsv.reg.

      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**

      Bir .reg dosya adı soneki kullanarak aşağıdaki metni bir Windows kayıt defteri dosyasına kaydedin; örneğin, DisableManifestXml.reg.

      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. Windows Gezgini'nde, önceki adımlarda oluşturduğunuz .reg dosyasını seçin veya çift tıklayın.

4. Kullanıcı Access Control penceresinde, Kayıt Defteri Düzenleyicisi'nin değişikliği yapmasına izin vermek için **Evet'i** seçin. 

5. Devam etmek isteyip istemediğiniz sorulduğunda **Evet'i** seçin.

    Kayıt Defteri Düzenleyicisi, ayarın kayıt defterine başarıyla eklendiğini belirten bir ileti görüntüler.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Dışarı aktarma raporlarını yeniden etkinleştirmek için kayıt defteri ayarlarını düzenleme

Önceki yordamda .reg dosyalarını oluşturarak Results.csv ve Manifest.xml raporları devre dışı bırakmışsanız, raporun arama sonuçlarıyla birlikte dışarı aktarılabilmesi için bu dosyaları yeniden etkinleştirebilirsiniz. Yine, sonuçları bir içerik aramasını dışarı aktarmak için kullanacağınız bilgisayarda aşağıdaki yordamı gerçekleştirin.
  
1. Açıksa eBulma Dışarı Aktarma aracını kapatın.

2. Önceki yordamda oluşturduğunuz .reg düzenleme dosyalarının birini veya ikisini birden düzenleyin.

    - **Results.csv**

        DisableResultsCsv.reg dosyasını Not Defteri'nde açın, değerini  `False` olarak  `True`değiştirin ve dosyayı kaydedin. Örneğin, dosyayı düzenledikten sonra şöyle görünür:

        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**

        DisableManifestXml.reg dosyasını Not Defteri'nde açın, değerini  `False` olarak  `True`değiştirin ve dosyayı kaydedin. Örneğin, dosyayı düzenledikten sonra şöyle görünür:

      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. Windows Gezgini'nde, önceki adımda düzenlediğiniz bir .reg dosyasını seçin veya çift tıklayın.

4. Kullanıcı Access Control penceresinde, Kayıt Defteri Düzenleyicisi'nin değişikliği yapmasına izin vermek için **Evet'i** seçin. 

5. Devam etmek isteyip istemediğiniz sorulduğunda **Evet'i** seçin.

    Kayıt Defteri Düzenleyicisi, ayarın kayıt defterine başarıyla eklendiğini belirten bir ileti görüntüler.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Dışarı aktarma raporlarını devre dışı bırakma hakkında sık sorulan sorular

**Results.csv ve Manifest.xml raporları nelerdir?**
  
Results.csv ve Manifest.xml dosyaları, dışarı aktarılan içerik hakkında ek bilgiler içerir.
  
- **Results.csv** Arama sonucu olarak indirilen her öğe hakkında bilgi içeren bir Excel belgesi. E-posta için, sonuç günlüğü her ileti hakkında aşağıdakiler dahil olmak üzere bilgiler içerir: 

  - İletinin kaynak posta kutusunda konumu (iletinin birincil posta kutusunda mı yoksa arşiv posta kutusunda mı olduğu dahil).
  - İletinin gönderildiği veya alındığı tarih.
  - İletideki Konu satırı.
  - İletinin göndereni ve alıcıları.
  - Arama sonuçlarını dışarı aktarırken yinelenenleri kaldırmayı etkinleştirdiyseniz iletinin yinelenen ileti olup olmadığı. Yinelenen iletiler **, Parent ItemId** sütununda iletiyi yinelenen olarak tanımlayan bir değere sahip olur. **Parent ItemId** sütunundaki değer, dışarı aktarılan iletinin **Item DocumentId** sütunundaki değerle aynıdır.

  SharePoint ve OneDrive İş sitelerindeki belgeler için sonuç günlüğü, aşağıdakiler dahil olmak üzere her belge hakkında bilgi içerir:

  - Belgenin URL'si.
  - Belgenin bulunduğu site koleksiyonunun URL'si.
  - Belgenin son değiştirildiği tarih.
  - Belgenin adı (sonuç günlüğündeki Konu sütununda bulunur).

- **Manifest.xml** Arama sonuçlarına dahil edilen her öğe hakkında bilgi içeren bir bildirim dosyası (XML biçiminde). Bu rapordaki bilgiler Results.csv raporuyla aynıdır, ancak Elektronik Bulma Başvuru Modeli (EDRM) tarafından belirtilen biçimdedir. EDRM hakkında daha fazla bilgi için adresine [https://www.edrm.net](https://www.edrm.net)gidin.

**Bu raporları dışarı aktarmayı ne zaman devre dışı bırakmalıyım?**
  
Bu, özel ihtiyaçlarınıza bağlıdır. Çoğu kuruluş arama sonuçları hakkında ek bilgi gerektirmez ve bu raporlara ihtiyaç duymaz.
  
**Bunu hangi bilgisayarda yapmam gerekiyor?**
  
eKeşif Dışarı Aktarma aracını çalıştırdığınız herhangi bir yerel bilgisayarda kayıt defteri ayarını değiştirmeniz gerekir. 
  
**Bu ayarı değiştirdikten sonra bilgisayarı yeniden başlatmam gerekiyor mu?**
  
Hayır, bilgisayarı yeniden başlatmanız gerekmez. Ancak eBulma Dışarı Aktarma aracı çalışıyorsa, kayıt defteri ayarını değiştirdikten sonra aracı kapatıp yeniden başlatmanız gerekir.
  
**Var olan bir kayıt defteri anahtarı düzenlenip düzenlenmiyor mu yoksa yeni bir anahtar mı oluşturuluyor?**
  
Bu makaledeki yordamda oluşturduğunuz .reg dosyasını ilk kez çalıştırdığınızda yeni bir kayıt defteri anahtarı oluşturulur. Ardından ,reg düzenleme dosyasını her değiştirdiğinizde ve yeniden çalıştırdığınızda ayar düzenlenir.
