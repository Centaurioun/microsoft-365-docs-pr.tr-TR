---
title: İki hesap arasında el ile veri aktarma
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: Plan veya şirket adını değiştirdiğinizde veya birden çok aboneliği tek bir abonelikte birleştirdiğinizde iki Microsoft 365 hesabı arasında el ile veri aktarmayı öğrenin.
ms.openlocfilehash: 742e15ed2b99d059898596d0dc99255117a0ca0f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68197953"
---
# <a name="transfer-data-manually-between-two-accounts"></a>İki hesap arasında el ile veri aktarma

Kollarınızı sıvamaya ve takviminizde belirli bir zaman dilimini engellemeye hazırlanın: İki Microsoft 365 hesabı arasında veri aktarmak el ile gerçekleştirilen, karmaşık ve zaman alan bir işlemdir. Bu otomatik veya desteklenen bir işlem değildir. Başlamanızı sağlayacağız.
  
> [!CAUTION]
> Microsoft 365'te barındırılan e-posta, Skype Kurumsal ve genel bir web sitesinin çalışmadığı işlem sırasında çalışma zamanı olacaktır. Kullanıcılar yeni kullanıcı adları ve parolalar alır ve Outlook'u sıfırlamaları gerekir.

**Aşağıdakilerden biri geçerliyse yalnızca bu konudaki yönergeleri kullanarak verileri el ile aktarın:**
  
- Farklı bir hizmet ailesindeki bir plana geçiş yapmanız gerekir.

- Şirketinizin adı değişti ve farklı ilk etki alanı adları kullanmak istediğiniz için yeni bir abonelik oluşturmaya ve verilerinizi geçirmeye karar verdiniz.

- Birden çok aboneliği tek bir yeni abonelikte birleştirmeniz gerekir.

> [!IMPORTANT]
> [Abonelik planınızı değiştirmeniz](../../commerce/subscriptions/switch-to-a-different-plan.md) gerekiyorsa ve Plan değiştir sihirbazını kullanabilirseniz veya Plan değiştir sihirbazı çalışmadığında bile aynı abonelik ailesindeki yeni bir abonelik planına aktarmanız gerekiyorsa, verilerinizi el ile aktarmanız gerekmez ve çalışma zamanı yoktur.

|**Görevler**|**Adımlar**|
|:-----|:-----|
|Taşımak istediğiniz planı satın alın.  <br/> |Kaydolduğunda, ilk etki alanı adlarında kullanılacak şirket adını belirtirsiniz:  *şirketiniz*  .onmicrosoft.com,  *şirketiniz*  -public.sharepoint.com ve  *şirketiniz*  .sharepoint.com. Mevcut abonelikler için  *kullandığınızdan*  farklı bir şirketinizin adını kullanmanız gerekir.  <br/> > [!NOTE]> Sistemimizde  *şirketinizin*  kullanıldığı ilk etki alanı adlarının serbest bırakılması genellikle aboneliği iptal ettikten sonra en az birkaç ay sürer. Eski Microsoft 365 aboneliğinizdeki tüm verilerinizi kaydetmeyi ve bu aboneliği iptal etme  *planınız*  olsa bile, eski şirketinizin değeri yeni bir abonelikte hemen kullanılamaz.           |
|Eski Microsoft 365 aboneliğinizden özel etki alanınızı kaldırın.  <br/> | Kullanıcı e-posta adreslerinden etki alanı adını kaldırmak ve e-posta için DNS kayıtlarını ve özel etki alanı için Lync'i kaldırmak için bir etki alanını [kaldırmadan önce gerekli adımları](remove-a-domain.md) izleyin. Genel web sitenizi Microsoft 365'te barındırdıysanız, buna işaret eden CNAME kaydını da kaldırmanız gerekir.  <br/> > [!IMPORTANT]> E-postayı bu özel etki alanına yönlendiren MX kaydını kaldırdıktan sonra, etki alanını yeni hesabınıza ekleyene, yeni MX kaydını ayarlayana ve kullanıcılarınızı ayarlayana kadar e-posta çalışmayı durdurur. Lync için DNS kayıtlarını kaldırdığınızda Lync çalışmayı durdurur. Genel web sitenize işaret eden CNAME kaydını kaldırdıktan sonra bu kayıt kullanılamaz.           [etki alanını kaldırın](remove-a-domain.md) .  <br/> |
|Yeni aboneliğiniz için özel etki alanınızı ayarlayın ve kullanıcılarınızı ayarlayın.  <br/> | Özel etki alanınız için gerekli DNS kayıtlarını oluşturmak da dahil olmak üzere yeni aboneliğinizi ayarlayın.  <br/>  Özel etki alanınızda e-posta adresleriyle kullanıcılarınızı oluşturun.  <br/> |
|Eski aboneliğinizden yeni aboneliğinize veri aktarabilirsiniz.  <br/> | Ayrı tarayıcı pencerelerinde her iki hesapta da oturum açın:  <br/>  Tarayıcı simgenize sağ tıklayın ve iki özel tarayıcı penceresi açın. her iki hesapta da oturum açmak için iki penceredeki farklı kimlik bilgilerini kullanabilirsiniz.  <br/> [Abonelikler arasında yönetim ayarlarını aktarma](#email) <br/> [Ekip sitesi yapısını ve verilerini aktarma](#transfer-team-site-structure-and-data) <br/> [Abonelikler arasında genel web sitesi aktarma](#transfer-a-public-website-between-subscriptions) <br/> [Abonelikler arasında yönetim ayarlarını aktarma](#email) <br/> |
|Microsoft 365 için Microsoft Desteği'ı arayarak işinize sonladığınız planın aboneliğini iptal edin.  <br/> | Yeni aboneliğinizin çalıştığını ve tüm verilerin aktarıldığını doğrulayın.  <br/>  Eski aboneliğinizi iptal etmek için [müşteri desteğine başvurun](../../business-video/get-help-support.md).  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>Abonelikler arasında yönetim ayarlarını aktarma

Her hesapta aşağıdaki sayfalara gidin ve eski hesabın ayarlarına göre yeni hesabı ayarlayın.
  
Microsoft 365'ten Microsoft 365 Orta Ölçekli İşletme'ye veya Microsoft 365 Kurumsal veri aktarıyorsanız, yönetici sayfaları farklı yapılandırılmıştır. Video izleyin[: Microsoft 365 Kurumsal tanıtımı](../index.yml) ve yönetici ayarlarına bakmak için aşağıdaki yerlere gidin.
  
Microsoft 365 Kurumsal ve Microsoft 365 Orta Ölçekli İşletmeler için:
  
|**Konum**|**Amaç**|
|:-----|:-----|
| \> **Microsoft 365** \> **Hizmet ayarlarını** Yönetici <br/> |Posta, siteler, Lync, kullanıcı yazılımı, parolalar, topluluk, hak yönetimi ve mobil cihazlar için her sekmeyi seçin.  <br/> |
|\> **Exchange'i Yönetici**  <br/> | Exchange Online ayarları  <br/> |
|**SharePoint'i** \> Yönetici  <br/> | SharePoint Online ayarları  <br/> |
| \> Yönetici **Skype Kurumsal** <br/> |Ek Skype Kurumsal ayarları  <br/> |

Microsoft 365 Küçük İşletme için
  
|**Konum**|**Amaç**|
|:-----|:-----|
| \> **Yönetici Kuruluş genelinde ayarları yönetme** <br/> |Yönetim ayarları  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>Abonelikler arasında genel web sitesi aktarma

Microsoft 365'te barındırılan bir genel web siteniz varsa, bunu kaydetmeniz ve yeni aboneliğinizde yeniden oluşturmanız gerekir.
  
> [!NOTE]
> Genel web siteniz bir DNS barındırma sağlayıcısında barındırılıyorsa herhangi bir değişiklik yapılması gerekmez. Geçişinizden etkilenmez.
  
SharePoint Online ortamındaki belge kitaplığını veya liste içeriğini dosya paylaşımlarına veya yerel bir bilgisayara kaydetmek için bkz. [SharePoint Online içeriğinin el ile geçişi](/sharepoint/troubleshoot/migration-tool/content-manual-migration).
  
> [!NOTE]
> Genel site geçiş uygulaması farklı bir aboneliğe veri aktaramaz.
  
## <a name="transfer-team-site-structure-and-data"></a>Ekip sitesi yapısını ve verilerini aktarma

Ekip sitesi verilerini kaydetmenin veya aktarmanın birkaç yolu vardır:
  
- Eski siteyi şablon olarak kaydedebilir ve şablonu yeni siteye aktarabilirsiniz.

- Belgeleri aktarmak için öncelikle hiyerarşinizi yeni sitede el ile yeniden oluşturun. Ardından her iki SharePoint ekip sitesini de aynı anda açabilir, Windows Gezgini ile her iki belge kitaplığını da açabilir ve belgeleri kopyalayıp yapıştırabilirsiniz. Bkz [. Video: Explorer ile Aç'ı kullanarak kitaplık dosyalarını kopyalama veya taşıma](https://support.microsoft.com/office/d18d21a0-1f9f-4f6c-ac45-d52afa0a4a2e).

- Liste verilerini aktarmak için bir [liste şablonu](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393) kaydedin ve kaydedilen şablonu kullanarak listeyi yeni sitede yeniden oluşturun.

- SharePoint Online ortamındaki (OneDrive İş veya ekip siteleri) belge kitaplığını veya liste içeriğini dosya paylaşımlarına veya yerel bir bilgisayara kaydetmek için bkz. [SharePoint Online içeriğinin el ile geçişi hakkında bilgiler](/sharepoint/troubleshoot/migration-tool/content-manual-migration).

## <a name="transfer-users-data-between-subscriptions"></a>Abonelikler arasında kullanıcıların verilerini aktarma

### <a name="email"></a>Email:

Yeni aboneliğinizi ayarladıktan sonra kullanıcılardan [e-postalarını, kişilerini, görevlerini ve takvim bilgilerini taşımalarını](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) isteyin. Sue@contoso.onmicrosoft.com gibi ilk kullanıcı adlarını kullanarak eski e-postalarına ulaşabilirler.
  
### <a name="onedrive-for-business-data"></a>OneDrive İş verileri:

Kullanıcılardan [OneDrive İş içeriğini kendi bilgisayarlarına kopyalamalarını/eşitlemelerini](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd) isteyin ve ardından yeni aboneliklerine geri ekleyin.

### <a name="onenote"></a>OneNote 

Kullanıcılardan [OneNote'u yedeklemelerini](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) ve [notları yedekten yeni aboneliklerine geri yüklemelerini](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) isteyin.
