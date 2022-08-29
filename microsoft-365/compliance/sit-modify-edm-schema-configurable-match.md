---
title: Yapılandırılabilir eşleşmeyi kullanmak için Tam Veri Eşleştirme şemasını değiştirme
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Yapılandırılabilir eşleşme kullanmak için edm şemasını nasıl değiştireceğinizi öğrenin.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 107a910068f3f0dfbae56530c5b589e19e0d2621
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405652"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>Yapılandırılabilir eşleşmeyi kullanmak için Tam Veri Eşleştirme şemasını değiştirme

## <a name="applies-to"></a>Uygulandığı öğe

- PowerShell kullanılarak tam veri eşleşmesi (EDM) hassas bilgi türü (SIT) oluşturma.

Tam Veri Eşleşmesi (EDM) tabanlı sınıflandırma, hassas bilgi veritabanındaki tam değerlere başvuran özel hassas bilgi türleri oluşturmanıza olanak tanır. Tam bir dizenin çeşitlemelerine izin vermeniz gerektiğinde, Microsoft Purview'a büyük/küçük harf ve bazı sınırlayıcıları yoksaymalarını bildirmek için *yapılandırılabilir eşleşmeyi* kullanabilirsiniz.

> [!IMPORTANT]
> Mevcut bir EDM şemasını ve veri dosyasını değiştirmek için bu yordamı kullanın.

1. EDM şeması ve veri dosyası karşıya yükleme amacıyla Microsoft 365'e bağlanmak için kullandığınız bilgisayardan **EdmUploadAgent.exe** kaldırın.

2. Aşağıdaki bağlantıları kullanarak aboneliğiniz için uygun **EdmUploadAgent.exe** dosyasını indirin:
    - [Ticari + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - çoğu ticari müşteri bunu kullanmalıdır
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - Bu özellikle yüksek güvenlikli kamu bulut abonelerine yöneliktir
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - Bu özellikle Birleşik Devletler Savunma Bakanlığı bulut müşterilerine yöneliktir

3. EDM Karşıya Yükleme Aracısı'nı yetkilendileyin, bir Komut İstemi penceresi açın (yönetici olarak) ve aşağıdaki komutu çalıştırın:

   ```dos
   EdmUploadAgent.exe /Authorize
   ```

4. Mevcut şemanın geçerli bir kopyasına sahip değilseniz, mevcut şemanın bir kopyasını indirmeniz gerekir ve şu komutu çalıştırın:

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]
   ```

5. Şemayı özelleştirerek her sütunun "caseInsensitive" ve / veya "ignoredDelimiters" kullanmasını sağlayın.  "caseInsensitive" için varsayılan değer "false" ve "ignoredDelimiters" için boş bir dizedir.

    > [!NOTE]
    > Genel regex desenini algılamak için kullanılan temel alınan özel hassas bilgi türü veya yerleşik hassas bilgi türü, ignoredDelimiters ile listelenen varyasyon girişlerinin algılanması için destek olmalıdır. Örneğin, ABD'de yerleşik sosyal güvenlik numarası (SSN) hassas bilgi türü, verilerdeki tireler, boşluklar veya SSN'yi oluşturan gruplandırılmış sayılar arasında boşluk olmaması gibi değişimleri algılayabilir. Sonuç olarak, EDM'nin SSN verileri için ignoredDelimiters'larına dahil etmek için yalnızca sınırlayıcılar şunlardır: tire ve boşluk.

    Burada, hassas verilerdeki büyük/küçük harf çeşitlemelerini tanımak için gereken ek sütunları oluşturarak büyük/küçük harfe duyarsız eşleşme simülasyonu sağlayan örnek bir şema verilmiştir.

    ```xml
    <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
      <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
               <Field name="PolicyNumber" searchable="true" />
               <Field name="PolicyNumberLowerCase" searchable="true" />
               <Field name="PolicyNumberUpperCase" searchable="true" />
               <Field name="PolicyNumberCapitalLetters" searchable="true" />
      </DataStore>
    </EdmSchema>
    ```

    Yukarıdaki örnekte, hem hem de `caseInsensitive` `ignoredDelimiters` eklenirse özgün `PolicyNumber` sütunun varyasyonları artık gerekli olmayacaktır.

    EDM yapılandırılabilir eşleşme kullanacak şekilde bu şemayı `caseInsensitive` güncelleştirmek için ve `ignoredDelimiters` bayraklarını kullanın.  Şöyle görünür:

    ```xml
    <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
      <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
             <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
      </DataStore>
    </EdmSchema>
    ```

    Bayrağı `ignoredDelimiters` alfasayısal olmayan herhangi bir karakteri destekler, aşağıda bazı örnekler verilmiştir:
    - \.
    - \-
    - \/
    - \_
    - \*
    - \^
    - \#
    - \!
    - \?
    - \[
    - \]
    - \{
    - \}
    - \\
    - \~
    - \;

    Bayrak `ignoredDelimiters` aşağıdakileri desteklemez:
    - 0-9 arası karakterler
    - A-Z
    - a-z
    - \"
    - \,

6. [Güvenlik & Uyumluluğu PowerShell'e bağlanın](/powershell/exchange/connect-to-scc-powershell).

    > [!NOTE]
    > Kuruluşunuz [Microsoft 365 için Müşteri Anahtarı'nı kiracı düzeyinde (genel önizleme)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview) ayarladıysa, tam veri eşleşmesi şifreleme işlevini otomatik olarak kullanır. Bu yalnızca Ticari buluttaki E5 lisanslı kiracılar tarafından kullanılabilir.

7. Aşağıdaki komutu çalıştırarak şemanızı güncelleştirin:

   ```powershell
   Set-DlpEdmSchema -FileData ([System.IO.File]::ReadAllBytes('.\\edm.xml')) -Confirm:$true
   ```

8. Gerekirse veri dosyasını yeni şema sürümüyle eşleşecek şekilde güncelleştirin.

    > [!TIP]
    > İsteğe bağlı olarak, şunu çalıştırarak karşıya yüklemeden önce csv dosyanızda bir doğrulama çalıştırabilirsiniz:
    >
    > `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
    >
    > Örneğin: `EdmUploadAgent.exe /ValidateData /DataFile  C:\data\testdelimiters.csv /Schema C:\EDM\patientrecords.xml`
    >
    > Desteklenen tüm EdmUploadAgent.exe parametreleri hakkında daha fazla bilgi için
    >
    > `EdmUploadAgent.exe /?`

9. Komut İstemi penceresini açın (yönetici olarak) ve hassas verilerinizi karma ve karşıya yüklemek için aşağıdaki komutu çalıştırın:

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]
   ```

## <a name="related-articles"></a>İlgili makaleler

- [Tam veri eşleşmesine dayalı hassas bilgi türleri hakkında daha fazla bilgi edinme](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [Hassas bilgi türü-varlık tanımları](sensitive-information-type-entity-definitions.md)
- [Özel hassas bilgi türleri](./sensitive-information-type-learn-about.md)
- [Microsoft Purview Veri Kaybı Önleme hakkında bilgi edinin](dlp-learn-about-dlp.md)
- [Bulut Uygulamaları için Microsoft Defender](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)
