---
title: Office Betikleri ayarlarını yönetme
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: Kuruluşunuzdaki kullanıcılar için Office Betikleri ayarlarını yönetmeyi öğrenin.
ms.openlocfilehash: 5fc83c585fd7edb288cc709e91f44f45b9c9d79c
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68734395"
---
# <a name="manage-office-scripts-settings"></a>Office Betikleri ayarlarını yönetme

[Office Betikleri](/office/dev/scripts), kullanıcıların Web üzerinde Excel betikleri kaydederek, düzenleyerek ve çalıştırarak görevleri otomatikleştirmesine olanak tanır. Office Betikleri Power Automate ile çalışır ve kullanıcılar Excel Online (business) bağlayıcısını kullanarak çalışma kitaplarında betikler çalıştırır. Microsoft 365 yöneticileri Office Betikleri ayarlarını Microsoft 365 yönetim merkezi yönetebilir.

## <a name="before-you-begin"></a>Başlamadan önce

- Office Betikleri ayarlarını yönetmek için Genel yönetici olmanız gerekir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../add-users/about-admin-roles.md).

- Kuruluşunuzdaki kullanıcıların, aşağıdaki planlardan biri gibi Office masaüstü uygulamalarına erişimi içeren bir Microsoft 365 veya Office 365 ticari veya EDU planı için geçerli bir lisansa sahip olduğundan emin olun:

- Microsoft 365 Business Standard
- Microsoft 365 Kurumsal Uygulamaları
- Microsoft 365 Kurumsal Uygulamaları
- Office 365 E3
- Office 365 E5
- Office 365 A3
- Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Office Betiklerinin kullanılabilirliğini ve betik paylaşımını yönetme

1. Microsoft 365 yönetim merkezi **Ayarlar** \> **Kuruluş ayarları** \> **[Hizmetler](https://go.microsoft.com/fwlink/p/?linkid=2053743)** sekmesine gidin.

2. **Office Betikleri'ne** tıklayın.

3. Office Betikleri varsayılan olarak açıktır ve kuruluşunuzdaki herkes özelliğe erişebilir ve bu özelliği kullanabilir ve betikleri paylaşabilir. Kuruluşunuz için Office Betikleri'ni kapatmak için **Kullanıcıların görevlerini Web üzerinde Excel otomatikleştirmesine izin ver** onay kutusunu temizleyin.

4. Kuruluşunuz için Office Betikleri'ni daha önce kapattıysanız ve yeniden açmak istiyorsanız, **Kullanıcıların Web üzerinde Excel görevlerini otomatikleştirmesine izin ver'i** seçin ve ardından özelliğe kimlerin erişip kullanabileceğini belirtin:

    - Kuruluşunuzdaki tüm kullanıcıların Office Betiklerine erişmesine ve bunları kullanmasına izin vermek için **Herkes** (varsayılan) seçeneğini seçili bırakın.

    - Yalnızca belirli bir grubun üyelerinin Office Betiklerine erişmesine ve bunları kullanmasına izin vermek için **Belirli grup'ı** seçin ve ardından grubun adını veya e-posta diğer adını girerek izin verme listesine ekleyin. İzin ver listesine yalnızca bir grup ekleyebilirsiniz ve bu grup aşağıdaki türlerden biri olmalıdır:
        - Microsoft 365 grubu
        - Dağıtım grubu
        - Güvenlik grubu
        - Posta etkin güvenlik grubu

        Farklı grup türleri hakkında daha fazla bilgi edinmek için bkz. [Grupları karşılaştırma](../create-groups/compare-groups.md).

5. Office Betiklerine erişimi olan kullanıcıların betiklerini kuruluşunuzdaki diğer kişilerle paylaşmasına izin vermek **için Office Betiklerine erişimi olan kullanıcıların betiklerini kuruluştaki diğer kullanıcılarla paylaşmasına izin ver'i** seçin. Betikleri kuruluş dışında paylaşmaya izin verilmez.

    > [!NOTE]
    > Daha sonra kuruluşunuz için betik paylaşımını kapatırsanız, kullanıcılar daha önce paylaşılan betikleri çalıştırmaya devam eder.

6. Office Betiklerine erişimi olan kullanıcıların betiklerini paylaşabileceğini belirtin:

    - Office Betiklerine erişimi olan tüm kullanıcıların betiklerini paylaşmasına izin vermek için **Herkes** (varsayılan) seçeneğini seçili bırakın.

    - Yalnızca Office Betiklerine erişimi olan belirli bir grubun üyelerinin betiklerini paylaşmasına izin vermek için **Belirli grup'ı** seçin ve ardından grubun adını veya e-posta diğer adını girerek izin verme listesine ekleyin. İzin ver listesine yalnızca bir grup ekleyebilirsiniz ve bu grup aşağıdaki türlerden biri olmalıdır:
        - Microsoft 365 grubu
        - Dağıtım grubu
        - Güvenlik grubu
        - Posta etkin güvenlik grubu

        Farklı grup türleri hakkında daha fazla bilgi edinmek için bkz. [Grupları karşılaştırma](../create-groups/compare-groups.md).

7. Kullanıcıların Office Betiklerini Power Automate akışlarında çalıştırmasına izin vermek için Office **Betiklerine erişimi olan kullanıcıların betiklerini Power Automate ile çalıştırmasına izin ver'i** seçin. Bu, kullanıcıların [Excel Online (business) Bağlayıcısı'nın](/connectors/excelonlinebusiness) **Betik çalıştır** seçeneğiyle akış adımları eklemesine olanak tanır.

    - Office Betiklerine erişimi olan tüm kullanıcıların akışlarda betiklerini kullanmasına izin vermek için **Herkes** (varsayılan) seçeneğini seçili bırakın.

    - Yalnızca Office Betiklerine erişimi olan belirli bir grubun üyelerinin akışlarda betiklerini kullanmasına izin vermek için **Belirli grup'ı** seçin ve ardından grubun adını veya e-posta diğer adını girerek izin ver listesine ekleyin. İzin ver listesine yalnızca bir grup ekleyebilirsiniz ve bu grup aşağıdaki türlerden biri olmalıdır:
        - Microsoft 365 grubu
        - Dağıtım grubu
        - Güvenlik grubu
        - Posta etkin güvenlik grubu

        Farklı grup türleri hakkında daha fazla bilgi edinmek için bkz. [Grupları karşılaştırma](../create-groups/compare-groups.md).

    - Power Automate ile Office Betiklerini kullanma hakkında daha fazla bilgi edinmek için bkz. [Power Automate ile Office Betiklerini Çalıştırma](/office/dev/scripts/develop/power-automate-integration).

8. **Kaydet**'i seçin.

    Office Betikleri ayarlarında yapılan değişikliklerin etkili olması 48 saate kadar sürebilir.

## <a name="next-steps"></a>Sonraki adımlar

Office Betikleri Power Automate ile çalıştığından, kullanıcılar Office Betiklerini kullanırken kuruluşunuzun verilerinin korunduğundan emin olmak için mevcut Microsoft Purview Veri Kaybı Önleme (DLP) ilkelerinizi gözden geçirmenizi öneririz. Daha fazla bilgi için bkz. [Veri kaybı önleme (DLP) ilkeleri](/power-automate/prevent-data-loss).

## <a name="related-content"></a>İlgili içerik

[Office Betikleri teknik belgeleri](/office/dev/scripts/) (bağlantı sayfası)\
[Excel'de Office Betiklerine Giriş](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (makale)\
[Web için Excel'de Office Betiklerini Paylaşma](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (makale)\
[Web üzerinde Excel'de Office Betiklerini kaydetme, düzenleme ve oluşturma](/office/dev/scripts/tutorials/excel-tutorial) (makale)
