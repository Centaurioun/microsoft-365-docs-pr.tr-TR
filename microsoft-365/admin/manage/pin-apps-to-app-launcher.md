---
title: Uygulamaları kullanıcılarınızın uygulama başlatıcısına sabitleme
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Tier3
- scotvorg
- Adm_O365
- M365-subscription-management
- Adm_TOC
ms.service: microsoft-365-business
ms.custom: admindeeplinkMAC
ms.localizationpriority: medium
description: Genel yönetici olarak, kullanıcılarınızın uygulama başlatıcısına en fazla üç uygulama sabitleyebilirsiniz.
ms.openlocfilehash: d3f6874fc0aa3a0731fd426f4d9a110b2b6c4632
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731777"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>Uygulamaları kullanıcılarınızın uygulama başlatıcısına sabitleme

Azure Active Directory portalındaki denetimleri kullanarak Office.com için en fazla üç uygulama ve kuruluşunuzdaki tüm kullanıcılar için uygulama başlatıcıyı sabitleyebilirsiniz. Uygulama gruplarını da düzenleyebilirsiniz. Eklediğiniz tüm uygulamalar daha sonra kullanıcı tarafından istediğiniz zaman kaldırılabilir. Kullanıcılarınız için bir uygulamayı sabitlemek için Bulut uygulama yöneticisi veya Azure Active Directory'de Uygulama yöneticisi ya da Microsoft 365'te bir Genel yönetici olmanız gerekir. Yönetici rolleri hakkında daha fazla bilgi için bkz. [Microsoft 365'te](../add-users/about-admin-roles.md) [yerleşik roller](/azure/active-directory/roles/permissions-reference) ve yönetici rolleri Azure AD. 

Uygulama başlatıcı ve Office.com hakkında daha fazla bilgi için [uygulama başlatıcı ve](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) [office.com güncelleştirmeleri ile Office 365 uygulama başlatıcı blog makalesine](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) bakın.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Uygulamaları sabitlemek için Azure Active Directory portalını kullanma

> [!NOTE]
> Microsoft 365 uygulamaları, Uygulama başlatıcıda zaten görüntülendiğinden bu listenin dışında tutulur.

1. konumundaki Microsoft 365 yönetim merkezi <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>gidin.
2. Sol gezinti bölmesinde **Tümünü göster'i** seçin ve **Yönetici merkezleri** altında **Azure Active Directory'yi** seçin.
3. **Azure Active Directory'de** **Kurumsal uygulamalar** > **Kullanıcı ayarları'nı** seçin.
4. **Office 365 Ayarlar** bölümünde **Uygulama ekle'yi** seçin.
5. Kullanıcıların uygulama başlatıcısına sabitlemek istediğiniz uygulamaları seçin ve ardından **Ekle'yi** seçin.

:::image type="content" source="../../media/add-apps.png" alt-text="Uygulamaları sabitlemek için Microsoft 365 ayarları.":::

### <a name="pin-a-custom-app"></a>Özel uygulama sabitleme

> [!NOTE]
> Kullanıcı arabirimi, bu özelliği kullanmak için ek Azure AD lisansları satın almanız gerekip gerekmediğini belirtir. Daha fazla bilgi için bkz. [Azure Active Directory fiyatlandırması](https://azure.microsoft.com/pricing/details/active-directory/).

1. **Azure Active Directory'de****, Tüm uygulamalar** sayfasının üst kısmındaki **Kurumsal uygulamalar** > **Yeni uygulama'yı** seçin.
2. **Uygulama ekle** sayfasında **Galeri dışı uygulama'yı** veya Azure Active Directory'nin önizleme sürümündeyseniz **Kendi uygulamanızı oluşturun'u** seçin. 
3. Uygulama için bir ad yazın ve kullanıcılar **ve gruplar** sekmesinde kullanıcı atayın.
4. Uygulama için bir simge yüklemek için **Özellikler** sekmesini kullanın.
5. Uygulamaya URL atamak için Çoklu **oturum açma** sekmesinde **Bağlı'yı** seçin ve bir URL girin.
6. **Kaydet**'i seçin.

## <a name="create-application-collections"></a>Uygulama koleksiyonları oluşturma

Kuruluşunuzdaki kullanıcılar için uygulama koleksiyonları da oluşturabilirsiniz. Yönergeler için bkz. [Azure portal Uygulamalarım portalında koleksiyon oluşturma](/azure/active-directory/manage-apps/access-panel-collections).