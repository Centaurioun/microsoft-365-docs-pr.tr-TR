---
title: Microsoft 365 Lighthouse izinlerine genel bakış
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: magarlan, chrigreen
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için Lighthouse izin gereksinimleri hakkında daha fazla bilgi edinin.
ms.openlocfilehash: 9626712c9363e6079cbc5a367e1f7fe79ea7e36f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193201"
---
# <a name="overview-of-permissions-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouse izinlerine genel bakış

Yönetilen Hizmet Sağlayıcılarının (MSP) Microsoft 365 Lighthouse kullanabilmesi için müşteri kiracılarına temsilci erişimi gerekir. Ayrıntılı Temsilcili Yönetici Ayrıcalıkları (GDAP), [Azure Active Directory (Azure AD) yerleşik rolleri](/azure/active-directory/roles/permissions-reference) aracılığıyla müşteri erişimi sağlayarak MSP'lere yüksek düzeyde denetim ve esneklik sağlar. GDAP aracılığıyla göreve göre en az ayrıcalıklı rolleriN MSP teknisyenlerine atanması hem MSP'ler hem de müşteriler için güvenlik riskini azaltır. Göreve göre en az ayrıcalıklı roller hakkında daha fazla bilgi için bkz. Azure Active Directory'de [en az ayrıcalıklı roller - İş Ortağı Merkezi](/partner-center/gdap-least-privileged-roles-by-task) ve [Göreve göre en az ayrıcalıklı roller](/azure/active-directory/roles/delegate-by-task). Müşteri kiracısıyla GDAP ilişkisi ayarlama hakkında daha fazla bilgi için bkz. Müşterinin [hizmetini yönetmek için ayrıntılı yönetici izinleri alma - İş Ortağı Merkezi.](/partner-center/gdap-obtain-admin-permissions-to-manage-customer)

Her grubun müşteri adına gerçekleştirmesi gereken görevlere göre MSP teknisyenleri gruplarına roller atamanızı öneririz. Örneğin, Service Desk Teknisyenlerinin yalnızca müşteri kiracı verilerini okuması veya kullanıcı parolalarını sıfırlaması gerekebilir. Buna karşılık, Yükseltme Mühendislerinin müşteri kiracısı güvenlik ayarlarını güncelleştirmek için daha düzeltici eylemler gerçekleştirmesi gerekebilir. Müşteri ve iş ortağı verilerinin güvende tutulması için bir görevi tamamlamak için gereken en az izin veren rolü atamak en iyi yöntemdir. Gerekirse Genel Yönetici rolüne zaman kapsamlı erişimi etkinleştirmek için Privileged Identity Management (PIM) kullanmanızı öneririz. Çok fazla kullanıcıya genel erişim vermek bir güvenlik riskidir ve bunu mümkün olduğunca sınırlamanızı öneririz. PIM'i etkinleştirme hakkında daha fazla bilgi için bkz[. AZURE AD PIM'i ayarlama.](m365-lighthouse-configure-portal-security.md#set-up-azure-ad-privileged-identity-management-pim)

Sonraki bölümdeki tablolarda, hangi GDAP rollerinin müşteri verilerini okuma ve Lighthouse'daki müşteri kiracıları üzerinde eylem gerçekleştirme izni vermesi açıklanmaktadır. Lighthouse varlıklarını yönetmek için gereken ek roller (örneğin, etiketler ve Lighthouse hizmet istekleri) için bu [makaledeki iş ortağı kiracısında izinler](#permissions-in-the-partner-tenant) bölümüne bakın.

## <a name="example-msp-service-tiers-recommended-gdap-roles-and-permissions"></a>Örnek MSP hizmet katmanları, önerilen GDAP rolleri ve izinleri

Aşağıdaki tabloda bazı örnek MSP hizmet katmanları için önerilen GDAP rolleri listelenmiştir. 

|| Hesap Yöneticileri| Servis Masası Teknisyenleri | Sistem Yöneticileri | Yükseltme Mühendisleri|
|---|---|---|---|---|
| **Önerilen GDAP rolleri** |<ul><li>Yardım Masası Yöneticisi</li></ul> |<ul><li>Güvenlik Okuyucusu<br>+</li><li>Yardım Masası Yöneticisi</li></ul> |<ul><li>Genel Okuyucu<br>+</li><li>Kullanıcı Yöneticisi<br>+</li><li>Kimlik Doğrulama Yöneticisi</li></ul> |<ul><li>Genel Okuyucu<br>+</li><li>Kullanıcı Yöneticisi<br>+</li><li>Intune Yöneticisi<br>+</li><li>Güvenlik Yöneticisi</li></ul>|

Aşağıdaki tabloda, örnek MSP hizmet katmanlarının atanan GDAP rolleri (önceki tabloda belirtilmiştir) tarafından belirlenen farklı Lighthouse sayfalarında gerçekleştirebileceği eylemler listelenmiştir.

| Deniz Feneri sayfası | Hesap Yöneticilerine izin verilen eylemler| Hizmet Masası Teknisyenlerine izin verilen eylemler |Sistem Yöneticilerine izin verilen eylemler | Yükseltme Mühendislerine izin verilen eylemler|
|---|---|---|---|---|
| Home  | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | 
| Kiracı     | <ul><li>Kiracı listesini görüntüleme</li><li>Müşteri kişilerini ve web sitesini güncelleştirme</li><li>Dağıtım planlarını görüntüleme</li></ul>  | <ul><li>Kiracı listesini görüntüleme</li><li>Müşteri kişilerini ve web sitesini güncelleştirme</li><li>Dağıtım planlarını görüntüleme</li></ul>   |  <ul><li>Kiracı listesini görüntüleme</li><li>Müşteri kişilerini ve web sitesini güncelleştirme</li><li>Dağıtım planlarını görüntüleme</li><li>Microsoft 365 hizmetleri kullanımını görüntüleme</li></ul> | <ul><li>Kiracı listesini görüntüleme</li><li>Müşteri kişilerini ve web sitesini güncelleştirme</li><li>Dağıtım planlarını görüntüleme</li><li>Microsoft 365 hizmetleri kullanımını görüntüleme</li></ul>  |
| Kullanıcılar   | <ul><li>Kiracı düzeyi (kullanıcıya özgü olmayan) verileri görüntüleme</li><li>Kiracılar arasında kullanıcı hesaplarını arama</li><li>Yönetici olmayanlar için parola sıfırlama*</li></ul>  | <ul><li>Kullanıcıya özgü tüm verileri görüntüleme</li><li>Kiracılar arasında kullanıcı hesaplarını arama</li><li>Yönetici olmayanlar için parola sıfırlama*</li></ul>|  <ul><li>Kullanıcıya özgü tüm verileri görüntüleme</li><li>Kiracılar arasında kullanıcı hesaplarını arama</li><li>Yönetici olmayanlar için parola sıfırlama*</i><li>Oturum açmayı engelle</li></ul>  | <ul><li>Kullanıcıya özgü tüm verileri görüntüleme</li><li>Kiracılar arasında kullanıcı hesaplarını arama</li><li>Yönetici olmayanlar için parola sıfırlama*</li><li>Oturum açmayı engelle</li><li>Güvenliği aşılmış kullanıcıları onaylama</li><li>Kullanıcılar için riski kapatma</li></ul> |
| Aygıtları    | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li><li>Cihazı eşitleme</li><li>Cihazı yeniden başlatma</li><li>Tanılama toplama</li></ul>|
| Tehdit yönetimi  | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li><li>Tam tarama çalıştırma</li><li>Hızlı tarama çalıştırma</li><li>Virüsten korumayı güncelleştirme</li><li>Cihazı yeniden başlatma</li></ul>|
| Temel    | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul>  | <ul><li>Tüm verileri görüntüleme</li></ul> |
| Windows 365 | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> | <ul><li>Tüm verileri görüntüleme</li></ul> |
| Hizmet durumu**| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Yok | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Yok | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Yok | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Yok |
| Denetim günlükleri**| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Yok | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Yok | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Yok | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Yok |

*Bkz. Müşteri kiracı yöneticilerinin [parolalarını sıfırlamak](/azure/active-directory/roles/permissions-reference#password-reset-permissions) için hangi rollerin gerekli olduğunu listeleyen bir tablo için parola sıfırlama izinleri.

**Hizmet durumu ve Denetim günlüklerini görüntülemek için farklı roller ve izinler gerekir. Daha fazla bilgi için bkz. [İş ortağı kiracısında izinler](#permissions-in-the-partner-tenant).

> [!NOTE]
> Lighthouse'da bilgileri görüntüleme veya düzenleme izniniz olmadığını belirten bir ileti alırsanız, size eylemi gerçekleştirmek için uygun izinlere sahip olmayan bir rol atanır. İş ortağı kiracınızda, gerçekleştirmeye çalıştığınız eylem için size uygun rolü atayabilecek bir yöneticiye ulaşmanız gerekir.

## <a name="delegated-admin-privileges-dap-in-lighthouse"></a>Lighthouse'da Temsilci Yönetici Ayrıcalıkları (DAP)

GDAP sonunda müşteri kiracıları için temsilci erişimi yapılandırmak için birincil yöntem olarak DAP'yi değiştirir. Ancak GDAP ayarlanmamışsa MSP teknisyenleri Lighthouse'a Yardım Masası Aracısı veya DAP aracılığıyla verilen Yönetici Aracısı rollerini kullanarak erişmeye devam edebilir. GDAP ve DAP'ın bir arada bulunduğu müşteriler için GDAP aracılığıyla MSP teknisyenlerine verilen roller önceliklidir. GDAP veya DAP'ın kullanımdan kaldırılması hakkında daha fazla bilgi için bkz. [GDAP hakkında sık sorulan sorular](/partner-center/gdap-faq) veya [tarihler ve zaman çizelgeleri için İş Ortağı Merkezi duyuruları](/partner-center/announcements/2022-march#15) .

DAP'ı olan ve GDAP olmayan müşteriler için Yönetici Aracısı rolü tüm kiracı verilerini görüntüleme ve Lighthouse'da herhangi bir eylem gerçekleştirme izinleri verir (iş ortağı kiracısında rol gerektiren diğer eylemler için aşağıya bakın).

Yardım Masası Aracısı rolü, tüm kiracı verilerini görüntüleme ve Lighthouse'da kullanıcı parolalarını sıfırlama, kullanıcı oturum açma işlemlerini engelleme ve müşteri iletişim bilgilerini ve web sitelerini güncelleştirme gibi sınırlı işlem gerçekleştirme izinleri verir.

DAP rollerine sahip iş ortağı kullanıcılara verilen geniş izinler göz önünde bulundurulduğunda, GDAP'ı en kısa sürede benimsemenizi öneririz. 

## <a name="permissions-in-the-partner-tenant"></a>İş ortağı kiracısında izinler

Lighthouse'daki belirli eylemler için iş ortağı kiracısında rol atamaları gereklidir. Aşağıdaki tabloda iş ortağı kiracı rolleri ve ilişkili izinleri listelenmektedir.

| İş ortağı kiracı rolleri | İzinler |
|--|--|
| İş ortağı kiracısının Genel Yöneticisi | <ul><li>Microsoft 365 yönetim merkezi Lighthouse'a kaydolun.</li><li>İlk çalıştırma deneyimi sırasında iş ortağı sözleşmesi değişikliklerini kabul edin.</li><li>Kiracıyı etkinleştirme ve devre dışı bırakma.</li><li>Etiketleri oluşturun, güncelleştirin ve silin.</li><li>Müşteri kiracısından etiket atama ve kaldırma.</li><li>Denetim günlüklerini gözden geçirme</li></ul> |
| Aşağıdaki özellik kümesiyle atanmış en az bir Azure AD rolüne sahip iş ortağı kiracı üyesi:<br>**microsoft.office365.supportTickets/allEntities/allTasks**<br>(Azure AD rollerin tam listesi için bkz. [yerleşik rolleri Azure AD](/azure/active-directory/roles/permissions-reference).) | Lighthouse hizmet istekleri oluşturun. |
| Aşağıdaki gereksinimlerin *ikisini de* karşılayan iş ortağı kiracı üyesi: <ul><li>Aşağıdaki özellik kümesiyle atanmış en az bir Azure AD rolü vardır:<br>**microsoft.office365.serviceHealth/allEntities/allTasks**<br>(Azure AD rollerin tam listesi için bkz. [yerleşik rolleri Azure AD](/azure/active-directory/roles/permissions-reference).)</li><li>Atanmış en az bir DAP temsilcisi rolü var (Yönetici Aracısı veya Yardım Masası Aracısı)</li></ul> | Hizmet durumu bilgilerini görüntüleyin. |

## <a name="related-content"></a>İlgili içerik

[Microsoft 365 Lighthouse gereksinimleri](m365-lighthouse-requirements.md) (makale)  
[Temsilci yönetim ayrıcalıkları (DAP) SSS](/partner-center/dap-faq) (makale)  
[Microsoft 365 Lighthouse'de Azure Active Directory rollerinizi görüntüleme](m365-lighthouse-view-your-roles.md) (makale)  
[Kullanıcılara rol ve izin atama](/partner-center/permissions-overview) (makale)  
[Microsoft 365 Lighthouse genel bakış](m365-lighthouse-overview.md) (makale)  
[Microsoft 365 Lighthouse için kaydolma](m365-lighthouse-sign-up.md) (makale)  
[Microsoft 365 Lighthouse SSS](m365-lighthouse-faq.yml) (makale)
