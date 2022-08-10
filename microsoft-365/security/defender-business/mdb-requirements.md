---
title: İş için Microsoft Defender gereksinimleri
description: lisans, donanım ve yazılım gereksinimlerini İş için Microsoft Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
ms.openlocfilehash: 20de14ce0357ecb28a205d1699a8756b78e542aa
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67301282"
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
| İstemci cihazı işletim sistemi | Microsoft 365 Defender portalındaki cihazları yönetmek için cihazlarınız aşağıdaki işletim sistemlerinden birini çalıştırıyor olmalıdır: <ul><li>Windows 10 veya 11 İş</li><li>Windows 10 veya 11 Professional</li><li>Windows 10 veya 11 Enterprise</li><li>Mac (en güncel üç sürüm desteklenir)</li></ul><br/><br/>Windows cihazlarında [KB5006738'in](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) yüklü olduğundan emin olun. <br/><br/>Cihazları zaten Microsoft Intune yönetiyorsanız Microsoft Endpoint Manager yönetim merkezini kullanmaya devam edebilirsiniz. Bu durumda, aşağıdaki diğer işletim sistemleri desteklenir: <ul><li>iOS ve iPadOS</li><li>Android işletim sistemi</li></ul> |
| Sunucu gereksinimleri | Windows Server veya Linux Server örneğini eklemeyi planlıyorsanız aşağıdaki gereksinimleri karşılamanız gerekir: <ul><li>**Önizleme özellikleri** ayarı açıktır. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ), **Ayarlar** > **Uç Noktaları** > **Genel** > **Gelişmiş özellikler****Önizleme özellikleri'ne** >  gidin.</li><li>Windows Server için zorlama kapsamı açık. Microsoft 365 Defender portalında **Ayarlar** > **Uç Noktaları** > **Yapılandırma yönetimi** > **Zorlama kapsamı'na** gidin. **MEM'den güvenlik yapılandırma ayarlarını zorunlu kılmak için MDE kullan'ı** seçin, **Windows Server'ı** ve ardından **Kaydet'i** seçin.</li><li>Linux Server uç noktaları, [Linux'ta Uç Nokta için Microsoft Defender önkoşullarını karşılar](../defender-endpoint/microsoft-defender-endpoint-linux.md#prerequisites).</li></ul> |

> [!NOTE]
> Kullanıcı izinlerini ve cihaz gruplarını yönetmek için [Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) kullanılır. Azure AD, İş için Defender aboneliğinize dahildir. 
> - Deneme sürümüne başlamadan önce Microsoft 365 aboneliğiniz yoksa etkinleştirme işlemi sırasında sizin için Azure AD sağlanır. 
> - İş için Defender deneme sürümünüzü başlattığınızda başka bir Microsoft 365 aboneliğiniz varsa, mevcut Azure AD hizmetinizi kullanabilirsiniz. 
> - İş için Defender denemenizi başlatırken [Microsoft 365 İş Ekstra](../../business/index.yml) kullanıyorsanız cihazlarınızı Intune kullanarak yönetme seçeneğiniz vardır.

## <a name="next-steps"></a>Sonraki adımlar

[İş için Defender'da 2. Adım: Rol ve izin atama](mdb-roles-permissions.md) bölümüne gidin.
 
