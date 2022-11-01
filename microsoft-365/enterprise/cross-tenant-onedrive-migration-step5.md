---
title: OneDrive Kiracılar Arası Kullanıcı Verileri Geçişi 5. Adım
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sharepoint-migration
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: OneDrive Kiracılar arası geçiş özelliğinin 5. adımı
ms.openlocfilehash: 5e8706b88b255132bb4db36cd6010668b36b3f26
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807683"
---
# <a name="step-5-identity-mapping"></a>5. Adım: Kimlik eşleme

Bu, Kiracılar Arası OneDrive geçişini tamamlamak için tasarlanmış bir çözümdeki 5. Adımdır. Daha fazla bilgi için bkz. [Kiracılar arası OneDrive geçişine genel bakış](cross-tenant-onedrive-migration.md).

- 1. Adım: [Kaynağa ve hedef kiracılara bağlanma](cross-tenant-onedrive-migration-step1.md)
- 2. Adım: [Kaynak ile hedef kiracı arasında güven oluşturma](cross-tenant-onedrive-migration-step2.md) 
- 3. Adım: [Güvenin kurulduğunu doğrulama](cross-tenant-onedrive-migration-step3.md) 
- 4. Adım: [Kullanıcıları ve grupları önceden oluşturma](cross-tenant-onedrive-migration-step4.md)  
- **5. Adım: [Kimlik eşlemesini hazırlama](cross-tenant-onedrive-migration-step5.md)**
- 6. Adım: [Kiracılar arası OneDrive geçişi başlatma](cross-tenant-onedrive-migration-step6.md)
- 7. Adım: [Geçiş sonrası adımları](cross-tenant-onedrive-migration-step7.md)

## <a name="create-the-identity-mapping-file"></a>Kimlik eşleme dosyasını oluşturma 

Kiracılar arası geçiş işleminin bu adımında, kaynak kiracıdaki kullanıcıların ve grupların hedef kiracıdaki ilgili kullanıcı ve gruplarıyla eşlemesini içeren tek bir CSV (virgülle ayrılmış değerler) dosyası oluşturacaksınız.

Hedef kiracıya geçişleri başlatmadan önce eşlemelerinizi doğrulamak için zaman ayırmanızı ve bunların doğru olduğundan emin olmanız önerilir.

Kimlik eşleme dosyasında bire bir ilişki vardır.  Aynı kullanıcıyı hedef kiracıdaki birden çok kullanıcıyla eşleyemezsiniz. Örneğin, yöneticinin birden çok OneDrive hesabının sahibi olduğu örnekleriniz varsa, sahipliğin Kaynaktan Hedefe geçirmek istediğiniz ilgili kullanıcıyla eşleşecek şekilde değiştirilmesi gerekir.  Bunu yapmazsanız, bu hesap dosyaları geçirilmez.

**Örnek:** Bu örnekte yöneticinin birden çok OneDrive hesabı vardır.

|Kaynak Kiracı Sahibi |Hedef Kiracı Kullanıcısı|
|:-----|:-----|
|admin@source.com  |new.userA@target.com|
|admin@source.com |new.userB@target.com|
|admin@source.com |new.userC@target.com|


Kiracılar arası geçiş şu senaryoları destekler:

**Örnek**

|Kaynak Kiracı Sahibi|Hedef Kiracı Kullanıcısı|
|:-----|:-----|
|userA@source.com|new.userA@target.com|
|userB@source.com|new.userB@target.com|
|userC@source.com|new.userC@target.com|


### <a name="create-the-csv-file"></a>CSV dosyasını oluşturma

CSV dosyanızda altı sütun gerekir. İlk üçü kaynak değerlerinizdir ve her biri verilerinizin bulunduğu konum hakkında ayrıntılı bilgi sağlar. Kalan üç sütun, hedef kiracıya karşılık gelen bilgilerdir. Altı sütunun tümü dosyada hesaba eklenmelidir. Dosyanızı Excel'de oluşturun ve .csv dosyası olarak kaydedin. 

Kullanıcılar ve gruplar aynı dosyaya eklenir. Kullanıcı veya grup olmasına bağlı olarak, sütuna girdiğiniz şey farklıdır. Sütunların her birine örneklerde gösterildiği gibi değerleri girin.  **Sütun başlıklarını EKLEMEYİN.**

|Sütun|Kullanıcı|Grup|
|:-----|:-----|:-----|
|1|Kullanıcı|Grup|
|2|SourceTenantCompanyID|SourceTenantCompanyID|
|3|SourceUserUpn|SourceGroupObjectID|
|4|TargetUserUpn|TargetGroupObjectID|
|5|TargetUserEmail|GroupName|
|6|Usertype|GroupType|


>[!Important]
>CSV dosyanıza sütun başlıkları eklemeyin.  Aşağıdaki örneklerde bunları yalnızca açıklama amacıyla ekleyeceğiz. 

**Kullanıcılar**. Konuklar için bu örnekte gösterildiği gibi değerlerinizi girin:

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-mapping-users-columns.png" alt-text="kullanıcıları eşlemek için kullanılacak biçim":::

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-mapping-users-example.png" alt-text="kullanıcılar için csv örneği":::

**Gruplar'a tıklayın**. Konuklar için bu örnekte gösterildiği gibi değerlerinizi girin:
</br>
:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-mapping-groups-columns.png" alt-text="gruplar için csv dosyası biçimi":::
</br>

*Örnek*:

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-group-example.png" alt-text="csv dosyasına grup ekleme örneği":::


**Konuk kullanıcılar**. Kaynak kiracıdaki konuk hesaplarını hedef kiracıdaki üye hesaplarıyla eşleyebilirsiniz. Ayrıca, daha önce oluşturulduysa, kaynaktaki bir konuk hesabını hedefteki bir konuk hesabıyla eşleyebilirsiniz. Konuklar için bu örnekte gösterildiği gibi değerlerinizi girin:
</br>

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-csv-mapping-users-guests.png" alt-text="bir konuğu üyeye eşlerken csv örneği":::

*CSV dosyasında birden çok kullanıcı örneği:* </br>

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-migration-csv-users-groups.png" alt-text="Eşleme dosyasında hem kullanıcılar hem de gruplar örneği":::

## <a name="obtain-the-source-tenant-company-id"></a>Kaynak kiracı şirket kimliğini alma
Kaynak Kiracı Şirket Kimliğini almak için:

1. Azure portal Yönetici olarak oturum açın [](https://ms.portal.azure.com/)
2. **Azure Active Directory'yi** seçin veya Arayın.
3. Sol panelde aşağı kaydırın ve **Özellikler'i** seçin.
4. **Kiracı Kimliği Alanını** bulun. Gerekli Kiracı Kimliği bu kutuda olacaktır.

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-azure-tenant-id.png" alt-text="kaynak kiracı kimliğini alma":::



## <a name="to-obtain-source-group-object-id"></a>Kaynak grup nesne kimliğini almak için:

1. [Azure Grupları'nda](https://ms.portal.azure.com) Yönetici olarak kaynak kiracıda oturum açın.
2. Gerekli gruplarınızı arayın.
3. Gerekli Grup örneğini ve ardından **Panoya kopyala'yı** seçin.  Bu değeri eşleme CSV dosyanızın sourceGroupObjectId sütununa yapıştırın.
4. Eşlediğiniz birden çok Grup varsa, her grup için bu adımları yineleyin.

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-source-group-objectid.png" alt-text="kaynak grup nesne kimliğini alma":::

### <a name="to-obtain-target-group-object-id"></a>Hedef grup nesne kimliğini almak için:

1. Hedef kiracıda [Azure Gruplarında](https://ms.portal.azure.com) Yönetici olarak oturum açın
2. Gerekli gruplarınızı arayın.
3. Gerekli grup örneğini ve ardından **Panoya kopyala'yı** seçin. Bu değeri eşleme CSV dosyanızın targetGroupObjectId sütununa yapıştırın.
4. Eşlenmeniz gereken birden çok grubunuz varsa, bu belirli targetGroupObjectId'leri almak için yukarıdaki işlemi yineleyin.
5. GroupName için, aldığınız *TargetGroupObjectId* ile aynı kimliği kullanın.
 
:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-target-group-objectid.png" alt-text="hedef nesne kimliğini alma":::

## <a name="upload-the-identity-map"></a>Kimlik haritasını karşıya yükleme

Kimlik eşleme dosyası hazırlandıktan sonra, hedef kiracıdaki SharePoint Yöneticisi dosyayı SharePoint'e yükler. Bu, kimlik eşlemesinin kiracılar arası geçişin bir parçası olarak otomatik olarak gerçekleşmesini sağlar.

>[!Important]
>*Add-SPOTenantIdentityMap –IdentityMapPath* komutunu çalıştırmadan önce Masaüstü/OneDrive/SharePoint'inizde identitymap.csv dosyasını kaydedin ve kapatın. Dosya açık kalırsa aşağıdaki hatayı alırsınız.
>
>*Add-SPOTenantIdentityMap: başka bir işlem tarafından kullanıldığından işlem 'C:\Users\myuser\Test-Identity-Map.csv' dosyasına erişemiyor.*


1. Kimlik Eşlemesini hedef kiracıya yüklemek için aşağıdaki komutu çalıştırın.  *-IdentityMapPath* için, kimlik eşleme CSV dosyasının tam yolunu ve dosya adını sağlayın.


```powershell
Add-SPOTenantIdentityMap –IdentityMapPath <identitymap.csv>  

```



>[!Important]
>Geçişin yaşam döngüsü sırasında Kimlik Eşlemenizde değişiklik yapmanız veya yapmanız gerekiyorsa, bu değişikliklerin geçişe uygulandığından emin olmak için **her** değişiklik yapıldığında *Add-SPOTenantIdentityMap –IdentityMapPath <identitymap.csv>* komutunu çalıştırmanız gerekir.

Herhangi bir yeni kimlik eşlemesinin karşıya yüklenmesi geçerli olanın üzerine yazılır. Tüm düzeltmelerin veya eklemelerin tam geçiş için ALL kullanıcılarını ve gruplarını içerdiğinden emin olun. Kimlik haritanız her zaman geçirmek istediğiniz herkesi içermelidir.

Belirli bir kullanıcının kimlik eşleme dosyasındaki eşleme girişlerine bakmak için *Get-SPOTenantIdentityMappingUser* komutunu ve *SourceUserKey* olarak Alan ve Taşıdığınız kullanıcının UPN'sini Değer olarak kullanın. 

**Örnek:**

```powershell

get-spoTenantIdentityMappingUser -Field SourceUserKey -Value usera@Contoso.onmicrosoft.com 
```

## <a name="verify-cross-tenant-compatibility-status"></a>Kiracılar arası uyumluluk durumunu doğrulama

Kiracılar arası geçişlere başlamadan önce, her iki SharePoint veritabanı şemasının da kaynak ve hedef arasında güncel ve uyumlu olduğundan emin olun.

Bu denetimi gerçekleştirmek için Kaynak kiracınızda aşağıdaki cmdlet'i çalıştırın.

```Powershell

Get-SPOCrossTenantCompatibilityStatus –PartnerCrossTenantHostURL [Target tenant hostname]

Get-SPOCrossTenantCompatibilityStatus –PartnerCrossTenantHostURL https://m365x12395529-my.sharepoint.com
```

- Kiracılar uyumluysa, kiracılar arası geçişleri başlatmanın bir sonraki adımına geçebilirsiniz.  
- Kiracılar uyumsuzsa, uyumluluk sağlamak için kiracılarınıza düzeltme eki yapılması/güncelleştirilmesi gerekir.

>[!Note]
>24 saat beklemenizi öneririz. Kiracılarınız hala *uyumsuz* olarak bildiriliyorsa desteğe başvurun. 

>[!Note]
>Uyumluluk durumu denetimini sık sık ve kiracılar arası geçişlerin HERHANGI bir örneğini başlatmadan önce gerçekleştirmenizi öneririz. Kiracılar uyumlu değilse, bu durum kiracılar arası geçişlerin başarısız geçmesine neden olabilir.


## <a name="step-6-start-a-onedrive-cross-tenant-migration"></a>6. Adım: [OneDrive kiracılar arası geçişi başlatma](cross-tenant-onedrive-migration-step6.md)