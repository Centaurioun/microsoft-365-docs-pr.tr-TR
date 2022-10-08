---
title: Microsoft 365 kullanım analizi sorun giderme
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Microsoft 365 Kullanım Analizi şablon uygulamasıyla ilgili sorunları gidermeyi öğrenin.
ms.openlocfilehash: 6b6a293d1627ca4fc91836c0ae9a503903186330
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68165855"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Microsoft 365 kullanım analizi sorun giderme

Microsoft 365 kullanım analizi ilgili en yaygın olarak karşılaşılan sorunlar konusunda yardım almak için aşağıdaki hata iletileri listesini keşfedin.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>İsteğinizi işleyemiyoruz. Önce Microsoft 365 yönetim merkezi bu verilere abone olmanız gerekir

 **Hata Kodu:** 422 
  
 **Bu iletiyi göreceğiniz yer:** Power BI'da Microsoft 365 Kullanım Analizi şablon uygulamasına bağlanırken veya doğrudan Microsoft 365 Raporlama API'lerini çağırırken. 
  
 **Neden:** Uygulamaya bağlanabilmeniz için önce Microsoft 365 yönetim merkezi verilerine abone olmanız gerekir. İlk olarak bu adım gerçekleştirilmezse, Microsoft 365 kiracı kimliğinizi sağlasanız bile şablon uygulamasına bağlanamazsınız. 
  
 **Bu hatayı düzeltmek için:** Verilere abone olmak için yönetim merkezi \> **Kullanımı Raporları'na** \> gidin ve ana pano sayfasında Microsoft 365 kullanım analizi kutucuğunu bulun.<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> **Başlarken** düğmesini seçin ve açılan **Raporlar** bölmesinde Verileri **Power BI için Microsoft 365 kullanım analizinin kullanımına sun** ayarını açın ve **Kaydet'i açın**.
  
## <a name="we-are-processing-your-data"></a>Verilerinizi işliyoruz

 **Bu iletiyi göreceğiniz yer:** Microsoft 365 yönetim merkezi Kullanım panosundaki **Microsoft 365 kullanım analizi** kutucuğunda. 
  
 **Neden:** Microsoft 365 yönetim merkezi [şablon uygulamasındaki verileri görmeyi kabul](enable-usage-analytics.md) ettiğinizde, Microsoft 365 sistemi kuruluşunuz için geçmiş kullanım verileri oluşturmaya başlar. Kiracınızın boyutuna bağlı olarak bu adım 2 saat ile 48 saat arasında sürebilir. 
  
 **Bunu düzeltmek için:** Sabırlı olun, ancak ileti 3 gün sonra **Verileriniz hazır olarak** değişmezse [İş için Microsoft 365 desteğine başvurun](Destek alın](.. /get-help-support.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Şu anda isteğinizi işleyemiyoruz. Kuruluşunuz için verilerin hazırlanması sürüyor

 **Hata Kodu:** 423 
  
 **Bu iletiyi göreceğiniz yer:** Power BI'da, Microsoft 365 Kullanım Analizi şablon uygulamasına bağlanırken veya doğrudan Microsoft 365 Raporlama API'lerini çağırırken. 
  
 **Neden:** Yönetim [merkezinden şablon uygulamasındaki verileri görmeyi kabul](enable-usage-analytics.md) ettiğinizde, Microsoft 365 sistemi kuruluşunuz için geçmiş kullanım verileri oluşturmaya başlar. Kiracınızın boyutuna bağlı olarak, bu adım iki saat ile 48 saat arasında sürebilir. 
  
 **Bunu düzeltmek için:** Sabırlı olun, ancak iletinin başlatılmasından bu yana 3 gün içinde **verileriniz hazır olarak** değişmezse [, İş için Microsoft 365 desteğine başvurun](../../business-video/get-help-support.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>Sağladığınız kiracı kimliği doğru biçimde değil

 **Hata Kodu:** 400 
  
 **Bu iletiyi göreceğiniz yer:** Power BI'da, Microsoft 365 Kullanım Analizi şablon uygulamasına bağlanırken veya doğrudan Microsoft 365 Raporlama API'lerini çağırırken. 
  
 **Neden:** Kiracı kimliği bir guid'dir ve xxxxxx-xxxx-xxxx-xxxx-xxxx-xxxx biçiminde olmalıdır. Kiracı giriş kutusuna başka bir dize girerseniz bu hatayı alırsınız. 
  
 **Bu hatayı düzeltmek için:** Yönetim merkezi \> **Kullanımı Raporları'na** \> gidin ve ana pano sayfasında Microsoft 365 kullanım analizi kutucuğunu bulun.<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Kiracı kimliği kutucukta listelenir. Şablon uygulamasına bağlanmak için buradan kopyalayıp iletişim kutusuna yapıştırabilirsiniz. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>Sağladığınız kiracı kimliği sistemimiz tarafından tanınmıyor

 **Hata Kodu:** 404 
  
 **Bu iletiyi göreceğiniz yer:** Power BI'da Microsoft 365 Kullanım Analizi şablon uygulamasına bağlanırken veya doğrudan Microsoft 365 Raporlama API'lerini çağırırken. 
  
 **Neden:** Sağladığınız kiracı kimliği geçerli değil veya yok. 
  
 **Bu hatayı düzeltmek için:** Yönetim merkezi \> **Kullanımı Raporları'na** \> gidin ve ana pano sayfasında Microsoft 365 kullanım analizi kutucuğunu bulun.<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Kiracı kimliği kutucukta listelenir. Şablon uygulamasına bağlanmak için buradan kopyalayıp iletişim kutusuna yapıştırabilirsiniz. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Power BI'da yeniden oturum açmak için lütfen kimlik bilgilerinizi tekrar girin

Hata Kodu: 302
  
 **Bu iletiyi göreceğiniz yer:** Power BI'da Microsoft 365 Kullanım Analizi şablon uygulamasına bağlanırken veya doğrudan Microsoft 365 Raporlama API'lerini çağırırken. 
  
 **Neden:** Yetkilendirme kodu başarısız oldu ve kimlik bilgilerinizi yeniden girmeniz gerekebilir. 
  
 **Bu hatayı düzeltmek için:** Power BI oturumunu kapatın ve sonra yeniden oturum açın. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins

 **Hata Kodu:** 403 
  
 **Bu iletiyi göreceğiniz yer:** Power BI'da Microsoft 365 Kullanım Analizi şablon uygulamasına bağlanırken veya doğrudan Microsoft 365 Raporlama API'lerini çağırırken. 
  
 **Neden:** Şablon uygulamasına bağlanmayı deneyen kullanıcı bu verilere erişmek için doğru yetkilendirme düzeyine sahip olmadığından yetkilendirme kodu başarısız oldu. 
  
 **Bu hatayı düzeltmek için:** Şablon uygulamasına bağlanmak için **Genel yönetici**, **Exchange yöneticisi**, **Skype Kurumsal yöneticisi**, **SharePoint yöneticisi**, **Genel okuyucu** veya **Rapor okuyucusu** olan bir kullanıcının kimlik bilgilerini sağlayın. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../add-users/about-admin-roles.md) . 
  
## <a name="refresh-failed"></a>Yenileme başarısız oldu

 **Bu iletiyi göreceğiniz durum:** Power BI'dan e-posta alındı veya yenileme geçmişinde başarısız durum var. 
  
 **Neden:** Bazen şablon uygulamasına bağlanan kullanıcının kimlik bilgileri sıfırlanır ve şablon uygulamasının bağlantı ayarlarında güncelleştirilmez ve bu da kullanıcının yenileme hatası hatalarını görmesine neden olur. 
  
 **Bu hatayı düzeltmek için:** Power BI'da Microsoft 365 Kullanım Analizi şablon uygulamasına karşılık gelen veri kümesini bulun, **yenilemeyi zamanla'yı** seçin ve yönetici kimlik bilgilerinizi sağlayın. 
  
Bu işe yaramazsa önbelleği temizleyin ve şablon uygulamasını yeniden oluşturun.
  
  
