---
title: Kuruluşunuz için Microsoft geri bildirimlerini yönetme
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
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
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: Kullanıcılarınızın Microsoft ürünleri hakkında Microsoft'a gönderebileceği geri bildirimleri yönetin.
ms.openlocfilehash: 1b062f445558d94a5abca4fa6184ffb49009c79b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68192717"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>Kuruluşunuz için Microsoft geri bildirimlerini yönetme

Microsoft 365 kuruluşunun yöneticisi olarak artık Microsoft 365 uygulamalarını kullanırken kullanıcılarınızın geri bildirim toplama ve müşteri etkileşimi deneyimini yönetmenize yardımcı olacak çeşitli ilkeler vardır. Bu ilkelerin her biri için kuruluşunuzda mevcut Azure Active Directory gruplarını oluşturabilir ve kullanabilirsiniz. Bu ilkelerle, kuruluşunuzdaki farklı departmanların Microsoft'a nasıl geri bildirim gönderebileceğini denetleyebilirsiniz. Microsoft, müşteriler tarafından gönderilen tüm geri bildirimleri inceler ve ürünü geliştirmek için bu geri bildirimi kullanır. Geri bildirim deneyimlerini **Açık** durumda tutmak, kullanıcılarınızın kullandıkları Microsoft ürünleri hakkında ne söylediklerini görmenizi sağlar. Kullanıcılarınızdan topladığımız geri bildirimler <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a>.

Geri bildirim türleri ve Microsoft'un kullanıcı geri bildirimlerini nasıl kullandığı hakkında daha fazla bilgi edinmek için bkz. [Kuruluşunuz için Microsoft geri bildirimi hakkında bilgi edinin](../misc/feedback-user-control.md).

Aşağıdaki tablo, aşağıdaki geri bildirim ilkeleri tablosunda gösterilen geri bildirim ilkelerine şu anda bağlı olan uygulamaları ve hizmetleri temsil eder. Ekran görüntüsü örnekleri için aşağıdaki tabloya bakın.

|**Uygulamalar & Hizmetleri**|**Ürünle ilgili geri bildirim** <br> |**Ürün içi anketler** <br> |**Meta veri koleksiyonu** <br> |**Müşteri etkileşimi** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Erişim**|Evet|Evet|Evet|Evet|
|**Excel**|Evet|Evet|Evet|Evet|
|**Forms**|Evet|Evet|Evet|Evet|
|**Intune Şirket Portalı (Android)**|Evet|Evet|Evet|Evet|
|**Microsoft Stream (Android, iOS)**|Evet|Evet|Evet|Evet|
|**Microsoft Whiteboard**|Evet|Evet|Evet|Evet|
|**Office.com**|Evet|Evet|Evet|Evet|
|**OneNote**|Evet|Evet|Evet|Evet|
|**OneDrive**|[Şu anda diğer denetimler tarafından yönetilen bazı ayarlar.](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook (Web, iOS)**|Çok yakında|Çok yakında|Çok yakında|Çok yakında|
|**Outlook (Masaüstü, Android, Mac)**|Evet|Evet|Evet|Evet|
|**PowerPoint**|Evet|Evet|Evet|Evet|
|**Project**|Evet|Evet|Evet|Evet|
|**Publisher**|Evet|Evet|Evet|Evet|
|**SharePoint**|[Şu anda diğer denetimler tarafından yönetilen bazı ayarlar.](/powershell/module/sharepoint-online/set-spotenant)||||
|**Takım**|[Şu anda diğer denetimler tarafından yönetilen bazı ayarlar.](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Yapılacaklar**|Evet|Evet|Evet|Evet|
|**Word**|Evet|Evet|Evet|Evet|
|**Visio**|Evet|Evet|Evet|Evet|
|**Viva Hedefleri**|Evet|Evet|Evet|Evet|
|**Viva Analizler**|Evet|Evet|Evet|Evet|
|**Tahta**|Evet|Evet|Evet|Evet|
|**Yammer**|Evet|Evet|Evet|Evet|

[Ürün içi anketler ve geri bildirim örnekleri için buraya bakın.](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**Meta veri koleksiyonu**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Ekran görüntüsü: Meta veri örneğini gösteren geri bildirim sayfası":::

**Müşteri etkileşimi**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Ekran görüntüsü: Ürün içi müşteri araştırması soru örneği":::

## <a name="before-you-begin"></a>Başlamadan önce

Bu ilkeleri kullanabilmek için cihazlarınızın en düşük derleme numarasına sahip olması gerekir. Daha fazla bilgi için aşağıdaki tabloya bakın.

|**Oluşturmak #**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ürünle ilgili geri bildirim|En az Sürüm 2010|En az 2,42|En az 16.0.13328|En az 16,42|Genel kullanıma açık|
|Ürün içi anketler|En az Sürüm 2010|En az 2,42|En az 16.0.13426|En az 16,42|Bekleyen dağıtım|
|Meta veri koleksiyonu|En az Sürüm 2010|En az 2,42|En az 16.0.13328|En az 16,42|Genel kullanıma açık|
|Müşteri etkileşimi|En az Sürüm 2010|En az 2,42|En az 16.0.13426|En az 16,42|Bekleyen dağıtım|

## <a name="specific-policies-you-can-configure"></a>Yapılandırabileceğiniz belirli ilkeler

### <a name="feedback-policies"></a>Geri bildirim ilkeleri

|**İlke adı**|**Varsayılan durum**|**Denetim özeti**|
|:-----|:-----|:-----|
|Kullanıcıların geri bildirim portalına erişmesine izin ver|-Inı|Geri bildirim portalına kullanıcı erişimini yönetme|
|Kullanıcıların Microsoft'a geri bildirim göndermesine izin verme|-Inı|Uygulamalar arasında geri bildirim giriş noktalarını denetler|
|Kullanıcıların Microsoft'tan ürün içi anketleri almasına ve yanıtlamasına izin verme|-Inı|Ürün içindeki anket istemlerini denetler|
|Kullanıcıların Microsoft'a geri bildirim gönderirken ekran görüntülerini ve ekleri eklemesine izin verme|Devre Dışı|Kullanıcının geri bildirim/anket ile göndermeye karar verebileceği meta verileri belirler|
|Microsoft'un kullanıcılar tarafından gönderilen geri bildirimleri izlemesine izin ver|Devre Dışı|Kullanıcının geri bildirim/anket ile iletişim bilgilerini paylaşabileceğini belirler|
|Microsoft'a geri bildirim gönderildiğinde kullanıcıların günlük dosyalarını ve içerik örneklerini eklemesine izin ver|Devre Dışı|Kullanıcının geri bildirim/anket ile göndermeye karar verebileceği meta verileri belirler|

> [!NOTE]
> **Kullanıcıların geri bildirim portalına erişmesine izin ver** ilkesi bir bulut ilkesidir. Bu ilke ADMX'te tanımlanmamıştır ve ilkeyi ayarlamak için uygun bir kayıt defteri anahtarı yoktur. Bunu zorunlu kılmak için bir bulut ilkesi oluşturmanız gerekir. Bu bir bulut ilkesidir çünkü geri bildirim portalı, aynı zamanda bir web uygulaması olan ve oturum açan kişi için ilkeleri isteyen bulut ilkesi hizmetine çağrı yapan bir web uygulamasıdır. Bu ilke yapılandırılırsa geri bildirim portalı, bulut ilkesi hizmetinden gelen yanıtta yapılandırılan ilke değerini alır.

## <a name="configure-policies"></a>İlkeleri yapılandırma

Bu ilke ayarlarını yapılandırmak için Office bulut ilkesi hizmetini kullanabilirsiniz. Daha fazla bilgi için bkz. [Office bulut ilkesi hizmetine genel bakış](/deployoffice/overview-office-cloud-policy-service). Bunları yapılandırmak için ilke ayarlarını bulmak için Office bulut ilkesi hizmeti kullanıcı arabiriminde "geri bildirim" veya "anket" araması yapabilirsiniz. 

Bu ilke ayarları, grup ilkesi kullanıyorsanız da kullanılabilir. Bu ilke ayarlarını kullanmak için, 22 Mart 2021'de yayımlanan [Yönetim Şablonu dosyalarının (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) en az 5146.1000 sürümünü indirin.

Bu ilke ayarlarını Kullanıcı Yapılandırması\İlkeler\Yönetim Şablonları\Microsoft Office 2016\Gizlilik\Güven Merkezi altında bulabilirsiniz.

> [!NOTE]
> İstemci uygulamalarının güncelleştirilmiş olması birkaç saat sürer.
