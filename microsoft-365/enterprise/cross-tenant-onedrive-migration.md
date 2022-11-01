---
title: Kiracılar arası OneDrive geçişi
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: Kiracılar arası OneDrive geçişi
ms.openlocfilehash: 6e2d925d6512df4fa62d3b8d5b71138439f836e8
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807551"
---
# <a name="cross-tenant-onedrive-migration"></a>Kiracılar arası OneDrive geçişi

>[!Note]
> Bu makaledeki bilgiler **, Kiracılar arası OneDrive geçişi** anlamına gelir. Posta kutusu geçişi için bkz. [Kiracılar arası posta kutusu geçişi](/microsoft-365/enterprise/cross-tenant-mailbox-migration).

Birleştirmeler veya dalışlar sırasında, genellikle kullanıcılar OneDrive hesaplarını yeni bir Microsoft 365 kiracısına taşıyabilmeniz gerekir. Kiracılar arası OneDrive geçişiyle, kiracı yöneticileri kullanıcıları yeni kuruluşlarına aktarmak için *SharePoint Online PowerShell* gibi tanıdık araçları kullanabilir.

İki ayrı kiracının SharePoint yöneticileri, bir kuruluş ilişkisi oluşturmak için *Set-SPOCrossTenantRelationship* cmdlet'ini ve kiracılar arası OneDrive taşımalarını başlatmak için *Start-SPOCrossTenantUserContentMove* komutunu kullanabilir.

Belirli bir zamanda geçiş için en fazla 4.000 OneDrive hesabı zamanlanabilir. Zamanlandıktan sonra, geçişler kullanıcının verileri Microsoft 365 bulutunu terk etmeden ve minimum kesintiyle gerçekleşir ve kullanıcının OneDrive'ını salt okunur hale gelmesi için yalnızca birkaç dakika gerekir. Geçişler tamamlandığında, kullanıcının özgün OneDrive konumuna bir yeniden yönlendirme yerleştirilir, böylece dosya ve klasörlere yönelik tüm bağlantılar yeni konumda çalışmaya devam edebilir. 

>[!Note]
> Bu özellik şu anda GCC, Tüketici, GCC High veya DoD gibi Kamu Bulutu kullanıcıları için desteklenmemaktadır.



>[!Important]
>- OneDrive'ları kiracılar arası geçirilen her kullanıcının **Kiracılar Arası Kullanıcı Verileri Geçişi** lisansına sahip olması gerekir.
>- Microsoft Purview Müşteri Anahtarı ile Hizmet Şifrelemesi kullanan müşteriler için kiracılar arası OneDrive geçişi kullanılamaz. [Microsoft Purview Müşteri Anahtarı ile Hizmet şifrelemesi hakkında bilgi edinin - Microsoft Purview](/microsoft-365/compliance/customer-key-overview)



## <a name="prerequisites-and-settings"></a>Önkoşullar ve ayarlar

- **PowerShell'i Microsoft Office SharePoint Online**. En son sürümün yüklü olduğunu onaylayın. [SharePoint Online Yönetim Kabuğunu Resmi Microsoft İndirme Merkezi'nden indirin](/download/details.aspx?id=35588)

- **Müşteri Anahtarı etkin durumdayken hizmet şifrelemeyi kapatın.** Kaynak OneDrive kiracısının Microsoft Purview Müşteri Anahtarı'nın etkin olduğu Hizmet şifrelemesinin etkin **olmadığını** onaylayın. Kaynak kiracıda etkinleştirilirse geçiş başarısız olur. [Microsoft Purview Müşteri Anahtarı ile hizmet şifrelemesi hakkında daha fazla bilgi edinin](/microsoft-365/compliance/customer-key-overview)

- Kaynak OneDrive hesapları Okuma/Yazma olarak ayarlanmalıdır. Salt okunur olarak ayarlanırsa başarısız olur.

## <a name="pre-create-target-accounts"></a>Hedef hesapları önceden oluşturma

- Geçiş için tanımlanan tüm kullanıcıların ve grupların hedef kiracıda önceden oluşturulduğundan emin olun.
- Hedef kiracıdaki her kullanıcıya uygun lisansları atayın.
- Kullanıcıların OneDrive siteleri oluşturmasını önlemek için hedef kiracıda OneDrive site oluşturmanın kısıtlanmasını öneririz. Hedef kiracıdaki kullanıcı için bir OneDrive sitesi zaten varsa, geçiş başarısız olur.  Varolan bir sitenin üzerine yazamazsınız.

>[!Note]
>OneDrive site oluşturmayı kısıtlama hakkında daha fazla bilgi edinmek için bkz. [Bazı kullanıcılar için OneDrive oluşturmayı devre dışı bırakma](/sharepoint/manage-user-profiles#disable-onedrive-creation-for-some-users)


## <a name="path-size-limits"></a>Yol boyutu sınırları

Microsoft, bir yoldaki karakter sayısını 400 karakteri aşmamak üzere sınırlar. Bu, yalnızca dosya adı değil tam yol sınırıdır. Geçişlerinizi planlamak için hedef kiracınızdaki OneDrive URL adlarının uzunluğunu gözden geçirin. Hata genellikle kaynaktan gelen dosyalar veya klasör yolları hedefte OneDrive URL'si ile birlikte 400 karakterlik yol sınırını aştığında oluşur. 

Geçiş, karakter sınırını aştığınızı algılar. Dosya yolu uzunluklarını azaltmak için dosya/klasör dizin yapısını güncelleştirmek için site sahibiyle birlikte çalışın.

Geçişleriniz için Kaynaktan Hedefe Kimlik Eşlemenizi oluştururken tüm yasal URL'ler kabul edilir. Şu anda kullanıcı adı/URL'de kesme işareti karakteri ( **'** ) içeren kullanıcı adları/URL'ler, geçiş denenirken "geçersiz karakter" hatasıyla başarısız olur.

>[!Tip]
>Karakter sınırını aşmamak için hedef OneDrive URL adlarınızı kısa tutmanızı öneririz.

## <a name="onedrive-account-size-limits"></a>OneDrive hesap boyutu sınırları
Her OneDrive hesabı en fazla 2 TB içeriğe veya 1 milyon öğeye sahip olabilir.


## <a name="permissions"></a>İzinler

Hedef kiracıya yüklediğiniz kimlik eşleme dosyasına dahil olan tüm kullanıcılar ve gruplar, geçirilen OneDrive sitesiyle ilgili hedef kiracıda izinleri korur.

## <a name="legal-holds"></a>Yasal tutmalar
Ayrı Tutma ilkesi uygulanmış OneDrive hesaplarının geçişi engellenir.
Bu OneDrive hesaplarını geçirmek için ayrı tutma ilkesini kaldırın, geçirin ve ardından bekletmeyi hedef kiracıda gerektiği gibi yeniden uygulayın.

## <a name="shared-files"></a>Paylaşılan dosyalar

OneDrive hesabı geçirildikten sonra, eski konumun paylaşılan bağlantısına tıklayan herkes, hedefe hala erişimi olması koşuluyla yenisine yönlendirilir. 

Bu yeniden yönlendirmeler, kaynak kiracının yetkisi kaldırılana kadar kalır. Yönetici ayrıca yeniden yönlendirmeleri siteden siteye seçmeli olarak kaldırabilir.

## <a name="how-does-it-work"></a>Nasıl çalışır?

- **1. Adım:** [Kaynağa ve hedef kiracılara bağlanın](cross-tenant-onedrive-migration-step1.md).  
- **2. Adım:** [Kaynak ile hedef kiracı arasında güven oluşturma](cross-tenant-onedrive-migration-step2.md) 
- **3. Adım:** [Güvenin kurulduğunu doğrulama](cross-tenant-onedrive-migration-step3.md) 
- **4. Adım:** [Kullanıcıları ve grupları önceden oluşturma](cross-tenant-onedrive-migration-step4.md)  
- **5. Adım:** [Kimlik eşlemesini hazırlama](cross-tenant-onedrive-migration-step5.md)
- **6. Adım:** [Kiracılar arası OneDrive geçişini başlatma]
- **7. Adım:** [Geçiş sonrası adımları](cross-tenant-onedrive-migration-step7.md)

## <a name="step-1-connect-to-source-and-target-tenants"></a>1. Adım: [Kaynak ve hedef kiracılara bağlanma](cross-tenant-onedrive-migration-step1.md)