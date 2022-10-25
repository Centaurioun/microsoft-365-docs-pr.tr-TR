---
title: İş için Microsoft Defender gereksinimleri
description: lisans, donanım ve yazılım gereksinimlerini İş için Microsoft Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 10/24/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365solution-mdb-setup
- highpri
- tier1
ms.openlocfilehash: 2e9cddb44139867cae95090c1e73edb45406eabb
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687564"
---
# <a name="microsoft-defender-for-business-requirements"></a>İş için Microsoft Defender gereksinimleri

Bu makalede, İş için Defender gereksinimleri açıklanmaktadır.

## <a name="what-to-do"></a>Yapılması gerekenler

1. [Gereksinimleri gözden geçirin ve karşıladığınızdan emin olun](#review-the-requirements).
2. [Sonraki adımlarınıza geçin](#next-steps).


## <a name="review-the-requirements"></a>Gereksinimleri gözden geçirin

Aşağıdaki tabloda, İş için Defender'ı yapılandırmak ve kullanmak için ihtiyacınız olan temel gereksinimler listeleniyor.

| Gereksinim | Açıklama |
|:---|:---|
| Abonelik | Microsoft 365 İş Ekstra veya İş için Defender (tek başına). Bkz. [İş için Defender'ı edinme](get-defender-business.md).  |
| Datacenter | Aşağıdaki veri merkezi konumlarından biri: <ul><li>Avrupa Birliği</li><li>Birleşik Krallık</li><li>Amerika Birleşik Devletleri</li></ul> |
| Kullanıcı hesapları |<ul><li>Kullanıcı hesapları Microsoft 365 yönetim merkezi ([https://admin.microsoft.com](https://admin.microsoft.com)) içinde oluşturulur.</li><li>İş için Defender (veya Microsoft 365 İş Ekstra) lisansları Microsoft 365 yönetim merkezi atanır.</li></ul>Bu görevle ilgili yardım almak için bkz. [Kullanıcı ekleme ve lisans atama](mdb-add-users.md). |
| İzinler  | İş için Defender'a kaydolmak için Genel Yönetici olmanız gerekir.<br/><br/>Microsoft 365 Defender portalına erişmek için kullanıcıların [Azure AD'da aşağıdaki rollerden](mdb-roles-permissions.md) birine atanmış olması gerekir:<ul><li>Güvenlik Okuyucusu</li><li>Güvenlik Yönetici</li><li>Genel Yönetici</li></ul>Daha fazla bilgi için bkz. [İş için Defender'da roller ve izinler](mdb-roles-permissions.md). |
| Tarayıcı gereksinimleri | Microsoft Edge veya Google Chrome |
| İstemci cihazı işletim sistemi | Microsoft 365 Defender portalındaki cihazları yönetmek için cihazlarınız aşağıdaki işletim sistemlerinden birini çalıştırıyor olmalıdır: <ul><li>Windows 10 veya 11 İş</li><li>Windows 10 veya 11 Professional</li><li>Windows 10 veya 11 Enterprise</li><li>Mac (en güncel üç sürüm desteklenir)</li></ul>Windows cihazlarında [KB5006738'in](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) yüklü olduğundan emin olun. <br/><br/>Cihazları zaten Microsoft Intune yönetiyorsanız Microsoft Endpoint Manager yönetim merkezini kullanmaya devam edebilirsiniz.<sup> [[1](#fn1)]</sup> Bu durumda, aşağıdaki diğer işletim sistemleri desteklenir: <ul><li>iOS ve iPadOS</li><li>Android işletim sistemi</li></ul> |
| Sunucu gereksinimleri | Windows Server veya Linux Server örneğini eklemeyi planlıyorsanız, [İş için Microsoft Defender sunucuları (önizleme)](get-defender-business-servers.md)<sup>[[2](#fn2)]</sup> gibi ek bir lisansa ihtiyacınız olacaktır. Aşağıdaki gereksinimleri karşılamanız gerekir: <ul><li>**Önizleme özellikleri** ayarı açıktır. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ), **Ayarlar** > **Uç Noktaları** > **Genel** > **Gelişmiş özellikler****Önizleme özellikleri'ne** >  gidin.</li><li>Windows Server için zorlama kapsamı açık. Microsoft 365 Defender portalında **Ayarlar** > **Uç Noktaları** > **Yapılandırma yönetimi** > **Zorlama kapsamı'na** gidin. **MEM'den güvenlik yapılandırma ayarlarını zorunlu kılmak için MDE kullan'ı** seçin, **Windows Server'ı** ve ardından **Kaydet'i** seçin.</li><li>Linux Server uç noktaları, [Linux'ta Uç Nokta için Microsoft Defender önkoşullarını karşılar](../defender-endpoint/microsoft-defender-endpoint-linux.md#prerequisites).</li></ul> |

(<a id="fn1">1</a>) Microsoft Intune, İş için Defender'ın tek başına sürümüne dahil değildir. Intune İş için Defender'a eklenebilir. Intune Microsoft 365 İş Ekstra dahildir.

(<a id="fn2">2</a>) Sunucuları eklemek için [İş için Microsoft Defender sunucuları (önizleme)](get-defender-business-servers.md) kullanmanızı öneririz. Alternatif olarak [Sunucular için Microsoft Defender](/azure/defender-for-cloud/defender-for-servers-introduction) kullanabilirsiniz; ancak Sunucular için Defender Plan 1 veya Plan 2 gibi bir kurumsal plan eklediğinizde İş için Defender deneyiminiz değişebilir. Daha fazla bilgi edinmek için bkz. [Microsoft uç nokta güvenlik aboneliklerinin bir karışımına sahipsem ne olur?](mdb-faq.yml#what-happens-if-i-have-a-mix-of-microsoft-endpoint-security-subscriptions) ve [Cihazları İş için Microsoft Defender ekleme](mdb-onboard-devices.md).

> [!NOTE]
> Kullanıcı izinlerini ve cihaz gruplarını yönetmek için [Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) kullanılır. Azure AD, İş için Defender aboneliğinize dahildir. 
> - Deneme sürümüne başlamadan önce Microsoft 365 aboneliğiniz yoksa etkinleştirme işlemi sırasında sizin için Azure AD sağlanır. 
> - İş için Defender deneme sürümünüzü başlattığınızda başka bir Microsoft 365 aboneliğiniz varsa, mevcut Azure AD hizmetinizi kullanabilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

[İş için Defender'da 2. Adım: Rol ve izin atama](mdb-roles-permissions.md) bölümüne gidin.
 
