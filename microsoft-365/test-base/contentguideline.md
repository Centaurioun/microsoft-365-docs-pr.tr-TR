---
title: Test paketi yönergeleri
description: Test paketiyle ilgili yönergeleri gözden geçirin
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 02/04/2022
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: eea9d04f2a50ce7a9a858a302eeef2c9feef8868
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315558"
---
# <a name="test-package-guidelines"></a>Test paketi yönergeleri

## <a name="1-script-referencing"></a>1. Betik başvuruyor

Portala bir .zip dosyası yüklediğinizde, bu dosyanın tüm içeriğini kök klasöre ayırırız. Bu ilk sıkıştırmayı açma işlemini yapmak için herhangi bir kod yazmanız gerekmez. Karşıya yüklenen zip dosyasına göre yolu kullanarak da .zip içindeki herhangi bir dosyaya başvurabilirsiniz.

Aşağıdaki örnekte, Görevler sekmesindeki giriş alanından ikili dosyalarınıza/betiklerinize nasıl başvurabileceğinizi göstereceğiz. Mavi renkli metin, **Tırnak işaretleri olmadan** **Betik yolu** alanına girilmelidir.

Zip dosyanızı karşıya yüklemeden önce içeriği bilmeniz önemlidir. Genellikle bir klasörü sıkıştırırken yerel makineniz zip dosyasının altında bir ana klasör oluşturur. Bu durumda, başvuru aşağıda **kalın** olarak gösterildiği gibi olacaktır:

**Contoso_App_Folder.zip**:

```console
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│      ├── file3.exe

│      ├── script.ps1
```

- ScriptX.ps1 - **"Contoso_App_Folder/ScriptX.ps1"**
- Script.ps1 - **"Contoso_App_Folder/klasör1/script.ps1"**

Diğer durumlarda, zip dosyanızın hemen altında dosyalarınız veya içeriğiniz olabilir (örneğin, 2. düzey klasör yoktur):

**Zip_file_uploaded.zip**:

```console
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
```

- ScriptX.ps1 - **"ScriptX.ps1"**
- Script.ps1 - **"klasör1/script.ps1"**

## <a name="2-script-execution"></a>2. Betik yürütme

**kullanıma ait olmayan testler:** Uygulama paketinin en az üç PowerShell betik içermesi gerekir. Bu betikler, uygulamanın ve bağımlılıklarının katılımsız yüklenmesi, başlatılması ve kapatılmasını yürütür. Her betik kendi önkoşullarını denetlemeyi, kendi başarısını doğrulamayı ve kendi sonrasını temizlemeyi (gerekirse) işlemelidir.

**İşlevsel testler:** Uygulama paketinin en az bir PowerShell betiği içermesi gerekir. Birden fazla betik sağlandığında, betikler karşıya yükleme sırasında çalıştırılır ve belirli bir betikteki bir hata, izleyen betiklerin yürütülmesini durdurur.

### <a name="script-requirements"></a>Betik gereksinimleri

- PowerShell Sürüm 5.1+
- Katılımsız yürütme
- Hata dönüş kodu
- Başarıyı doğrulama
- Betike özgü günlük klasörüne günlüğe kaydetme

Her betiğin test işlem hattında başarıyla yürütülebilmesi için katılımsız (kullanıcı istemleri olmadan) çalıştırılması gerekir.

> [!NOTE]
> Betikler başarıyla tamamlandığında "0" döndürmelidir ve yürütme sırasında herhangi bir hata oluşursa sıfır olmayan bir hata kodu döndürür.

Her betik, başarıyla çalıştırıldığını doğrulamalıdır. Örneğin yükleme betiği, yükleyici ikili dosyasının yürütülmesi tamamlandıktan sonra sistemde belirli ikili dosyaların ve/veya kayıt defteri anahtarlarının olup olmadığını denetlemelidir. Bu denetim, yüklemenin başarılı olduğundan makul ölçüde emin olmak için yardımcı olur.

Doğrulama, bir test çalıştırması sırasında hataların oluştuğu yeri düzgün bir şekilde tanılamak için gereklidir. Örneğin, betik uygulamayı başarıyla yükleyemiyorsa ve başlatılamıyorsa.

> [!IMPORTANT]
> **Aşağıdakilerden kaçının:** Betikler makineyi yeniden başlatmamalıdır, yeniden başlatma gerekiyorsa lütfen betiklerinizin karşıya yüklenmesi sırasında bunu belirtin.

## <a name="3-log-collection"></a>3. Günlük koleksiyonu

Her betik, oluşturduğu günlüklerin çıkışını adlı `logs`bir klasöre vermelidir. adlı `logs` dizindeki tüm klasörler kopyalanır ve sayfada indirilsin `Test Results` .

Örneğin, yükleme betiği ( **Uygulama/betikler/yükleme** dizininde bulunabilir) günlüklerinin çıkışını şu konuma alabilir: **logs/install.log**; böylece son günlük şu konumda olur: **Uygulamalar/betikler/yükleme/logs/install.log**

Sistem, dosyayı diğer `logs` klasörlerdeki `install.log` diğer dosyalarla birlikte alır ve indirmek üzere harmanlar.

## <a name="4-application-binaries"></a>4. Uygulama ikili dosyaları

Tüm ikili dosyalar ve bağımlılıklar tek bir zip dosyasına eklenmelidir.

Bu ikili dosyalar, uygulamanın yüklenmesi için gereken her şeyi (örneğin, uygulama yükleyicisi) içermelidir. Uygulamanın .NET Core/Standard veya .NET Framework gibi herhangi bir çerçeveye bağımlılığı varsa, bu çerçeveler dosyaya eklenmelidir ve sağlanan betiklerde doğru başvurulmalıdır.

> [!NOTE]
> Karşıya yüklenen zip dosyasının adında boşluk veya özel karakter olamaz

## <a name="5-applicationtest-rules"></a>5. Uygulama/Test kuralları

Uygulamalarınızın/testlerinizin Test Temeli altyapısı altında doğru şekilde çalışması için Uygulama [/Test kuralları ](rules.md)bölümünde açıklanan kurallara uymaları gerekir. 

## <a name="next-steps"></a>Sonraki adımlar

**Bazı Sık Sorulan Soruları (SSS)** görüntülemek için sonraki makaleye ilerleyin
> [!div class="nextstepaction"]
> [Sonraki adım](faq.md)
