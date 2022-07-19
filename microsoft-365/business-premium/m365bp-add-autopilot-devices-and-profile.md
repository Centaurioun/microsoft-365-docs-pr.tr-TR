---
title: Autopilot cihazları ve profili eklemek için bu adım adım kılavuzu kullanın
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.localizationpriority: high
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Windows Autopilot'ı kullanarak işletmeniz için yeni Windows 10 cihazları çalışanların kullanımına hazır olacak şekilde ayarlamayı öğrenin.
ms.openlocfilehash: 4ab7925f751d987e9508732202908ad10c9d46b7
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66862066"
---
# <a name="use-this-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Autopilot cihazları ve profili eklemek için bu adım adım kılavuzu kullanın

Windows Autopilot'ı kullanarak işletmeniz için **yeni** Windows 10 cihazları, çalışanlarınıza verdiğinizde kullanıma hazır olacak şekilde ayarlayabilirsiniz.
  
## <a name="device-requirements"></a>Cihaz gereksinimleri

Cihazların şu gereksinimleri karşılaması gerekir:
  
- Windows 10, sürüm 1703 veya üzeri

- Windows ilk çalıştırma deneyiminden geçmemiş yeni cihazlar

## <a name="use-the-setup-guide-to-add-devices-and-profiles"></a>Cihaz ve profil eklemek için kurulum kılavuzunu kullanma

Henüz cihaz grupları veya profilleri oluşturmadıysanız, başlamanın en iyi yolu adım adım kılavuzu kullanmaktır. Ayrıca kılavuzu kullanmadan [Autopilot cihazları ekleyebilir](m365bp-create-and-edit-Autopilot-devices.md) ve bunlara [profil atayabilirsiniz](../admin/devices/create-and-edit-Autopilot-profiles.md) .
  
1. Şuradan yönetim merkezine gidin: <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Sol gezinti bölmesinde **Cihazlar** \> **Otomatik Pilotu'nu** seçin.

    ![Yönetim merkezinde cihazlar'ı ve ardından Autopilot'ı seçin.](../media/Autopilot.png)
  
3. **Autopilot** sayfasında **Başlangıç kılavuzu'na** tıklayın veya dokunun.

    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
4. **Cihaz listesi içeren .csv dosyasını karşıya yükle** sayfasında, hazır .CSV dosyasının bulunduğu konuma gidin ve **ardından İleri'yi** **Aç'ı seçin**\>. Dosyanın üç üst bilgisi olmalıdır:

    - A sütunu: Cihaz Seri Numarası
    - B sütunu: Windows Ürün Kimliği
    - C sütunu: Donanım Numarası

Bu bilgileri donanım satıcınızdan alabilir veya [Get-WindowsAutopilotInfo PowerShell betiğini](https://www.powershellgallery.com/packages/Get-WindowsAutopilotInfo) kullanarak CSV dosyası oluşturabilirsiniz.

Daha fazla bilgi için bkz. [Cihaz listesi CSV dosyası](../admin/misc/device-list.md). **Cihaz listesiyle .csv dosyası yükleme** sayfasında bir örnek dosya da indirebilirsiniz.

> [!NOTE]
> Bu betik, bir müşterinin Cihazı Windows Autopilot'a kaydetmesi için gereken özellikleri almak için WMI kullanır. Bir cihazı kaydetmek için gerekli olmadığından ve çıkış CSV'sinde NULL olan PKID tamamen iyi olduğundan, sonuçta elde edilen CSV dosyasının Bir Windows Ürün Kimliği (PKID) değeri toplamamasının normal olduğunu unutmayın. Yalnızca seri numarası ve donanım karması doldurulur.

5. **Profil ata** sayfasında var olan bir profili seçebilir veya yeni bir profil oluşturabilirsiniz. Henüz bir tane yoksa, oluşturmanız istenir.

    Profil, tek bir cihaza veya bir cihaz grubuna uygulanabilen ayarlar koleksiyonudur.

    Varsayılan özellikler gereklidir ve otomatik olarak ayarlanır. Varsayılan özellikler şunlardır:

    - Cortana, OneDrive ve OEM kaydını atlayın.

    - Şirketinizin markasıyla oturum açma deneyimi oluşturma.

    - Cihazlarınızı Azure Active Directory hesaplarına bağlayın ve Microsoft 365 İş Ekstra tarafından yönetilecek şekilde otomatik olarak kaydedin.

    Daha fazla bilgi için bkz. [Autopilot Profili ayarları hakkında](m365bp-Autopilot-profile-settings.md).

6. Diğer ayarlar, **Gizlilik ayarlarını atla** ve **Kullanıcının yerel yönetici olmasına izin verme** şeklindedir. Varsayılan olarak ikisi de **Kapalı** durumdadır.

    **İleri**'yi seçin.

7. **İşiniz bitti** , oluşturduğunuz (veya seçtiğiniz) profilin, cihaz listesini karşıya yükleyerek oluşturduğunuz cihaz grubuna uygulanacağını gösterir. Cihaz kullanıcıları bir sonraki oturum açışında ayarlar geçerli olur. **Kapat**'ı seçin.

## <a name="related-content"></a>İlgili içerik

- [Autopilot Profili ayarları](../business-premium/m365bp-Autopilot-profile-settings.md) hakkında (makale)\
- [Cihazlarınızı ve uygulama verilerinizi koruma seçenekleri](../admin/devices/choose-device-security.md) (makale)
- [İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)
