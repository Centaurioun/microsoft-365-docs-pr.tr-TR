---
title: Güvenlik ekipleriniz için e-posta bildirimlerini ayarlama
description: İşletmeler için Microsoft Defender ile uyarı ve güvenlik açıkları hakkında bilgi almak için e-posta bildirimlerini ayarlama
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/07/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.openlocfilehash: 5a6d896b3b18b4eea0721197c0a4766add4a20b6
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2022
ms.locfileid: "63016708"
---
# <a name="set-up-email-notifications"></a>E-posta bildirimlerini ayarlama

> [!IMPORTANT]
> İş için Microsoft Defender şu anda önizlemede ve istekte etmek için buraya kaydolan müşterilere ve IT [İş Ortaklarına aşamalı](https://aka.ms/mdb-preview) olarak aşamalı olarak aşamalı olarak sunulmaktadır. Önümüzdeki haftalarda bir ilk müşteri ve iş ortağı kümesi sunuyoruz ve genel kullanılabilirlik durumuna kadar önizlemeyi genişleteceğiz. Önizlemenin bir dizi ilk [senaryoyla başlat olacağını](mdb-tutorials.md#try-these-preview-scenarios) ve düzenli olarak özellikler ekley olacacaz.
> 
> Bu makaledeki bazı bilgiler, ticari olarak piyasaya sürmeden önce önemli ölçüde değiştirilmiş olabileceği önceden satın alınan ürünler/hizmetlerle ilgilidir. Microsoft, burada sağlanan bilgiler için açık veya zımni hiçbir garanti vermez. 


Güvenlik ekipleriniz için e-posta bildirimlerini kurabilirsiniz. Daha sonra, uyarılar oluşturulur veya yeni güvenlik açıkları keşfedilirse, güvenlik ekibi belirsiz kişilerine otomatik olarak bu uyarıyı yapılır. 

## <a name="what-to-do"></a>Ne yapmalı?

1. [E-posta bildirimi türleri hakkında bilgi alın](#types-of-email-notifications).

2. [E-posta bildirimi ayarlarını görüntüleme ve düzenleme](#view-and-edit-email-notifications).

3. [Sonraki adımlarınıza devam edin](#next-steps).


## <a name="types-of-email-notifications"></a>E-posta bildirimi türleri

E-posta bildirimlerini ayarsanız, aşağıdaki tabloda açıklandığı gibi iki tür arasında seçim yapabilirsiniz: <br/><br/>

| Bildirim türü  | Açıklama  |
|---------|---------|
| Güvenlik açıkları  | Yeni açıklardan yararlanan veya güvenlik açığı olan olaylar algılandığında alıcılara bir e-posta gönderilir. |
| Güvenlik açıkları & uyarılar  | Cihazlar üzerinde tehdit algılandığında veya yeni açıklardan yararlanan ya da güvenlik açığı olayları algılandığında uyarı geldiğinde alıcılara bir e-posta gönderilir. |

> [!TIP]
> **Güvenlik ekibinin yeni uyarıları veya güvenlik açıklarını bulmanın tek yolu e-posta bildirimleri değildir**.
> 
> E-posta bildirimleri, güvenlik ekibinizi gerçek zamanlı olarak bilgi sahibi tutmaya yardımcı olacak kullanışlı bir yol sağlar. Ama başka da var! Örneğin, güvenlik ekibiniz Microsoft 365 Defender portalında ()[https://security.microsoft.com](https://security.microsoft.com) her oturum aişında kartları yeni tehditleri, uyarıları ve güvenlik açıklarını vurgulayan kartlar görebilir. İş için Defender (önizleme), güvenlik ekibinin oturum açması sırasında önem verdiği önemli bilgileri vurgulanacak şekilde tasarlanmıştır.
> 
> Güvenlik ekibinin bilgileri görüntülemek için **gezinti bölmesinde** Olaylar'ı da seçmesi gerekir. Daha fazla bilgi edinmek için bkz [. İş için Microsoft Defender'da (önizleme) olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md).

## <a name="view-and-edit-email-notifications"></a>E-posta bildirimlerini görüntüleme ve düzenleme

Kuruluşun e-posta bildirimi ayarlarını görüntülemek veya düzenlemek için şu adımları izleyin:

1. Erişim portalına Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com) ) ve oturum açın.

2. Gezinti bölmesinde Seçenekler'i **Ayarlar** uç **noktalar'ı seçin**. Ardından, **Genel'in altında** **E-posta bildirimleri'ne seçin**. 

3. Uyarılar ve Güvenlik Açıkları **sekmelerinde yer alan** **bilgileri gözden** geçirebilirsiniz.

   - Uyarılar sekmesinde listelenen hiçbir öğe görmüyorsanız, uyarı oluşturulsa  bile kişilerin bildirilecekleri bir kural oluşturabilirsiniz. Bu görevle ilgili yardım almak için bkz [. Uyarı bildirimleri için kural oluşturma](../defender-endpoint/configure-email-notifications.md).

   - Güvenlik Açıkları sekmesinde listelenen hiçbir öğe görmüyorsanız, yeni  bir güvenlik açığı keşfedilene kadar kişilerin bildirilleri için bir kural oluşturabilirsiniz. Bu görevle ilgili yardım almak için bkz [. Güvenlik açığı olayları için kural oluşturma](../defender-endpoint/configure-vulnerability-email-notifications.md).

   - Oluşturduğunuz kurallarız varsa, düzenlemek için bir kural seçin. Ayrıca bir kuralı silebilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

Şu şekilde devam edin:

- [4. Adım: Cihazları İş için Microsoft Defender'a ekleme (önizleme)](mdb-onboard-devices.md)
