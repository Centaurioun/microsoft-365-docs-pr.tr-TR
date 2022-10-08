---
title: İş için Microsoft Defender'de rol ve izin atama
description: Siber güvenlik ekibinize roller atayın. İş için Defender'da bu roller ve izinler hakkında bilgi edinin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365solution-mdb-setup
- highpri
- tier1
ms.openlocfilehash: 6ba902089a7949e242be554ac763d0c873626a6e
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097785"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business"></a>İş için Microsoft Defender'de rol ve izin atama

Microsoft 365 Defender portalında İş için Defender'ı yapılandırma, raporları görüntüleme veya algılanan tehditlerle ilgili yanıt eylemleri gerçekleştirme gibi görevleri gerçekleştirmek için güvenlik ekibinize uygun izinlerin atanması gerekir. İzinler, Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)) veya [Azure Active Directory'de](/azure/active-directory/roles/manage-roles-portal) atanan roller aracılığıyla verilir. 

## <a name="what-to-do"></a>Yapılması gerekenler

1. [İş için Defender'daki roller hakkında bilgi edinin](#roles-in-defender-for-business).
2. [Güvenlik ekibiniz için rol atamalarını görüntüleyin veya düzenleyin](#view-or-edit-role-assignments).
3. [Sonraki adımlarınıza geçin](#next-steps).


## <a name="roles-in-defender-for-business"></a>İş için Defender'daki roller

Aşağıdaki tabloda, İş için Defender'da atanabilecek üç rol açıklanmaktadır. [Yönetici rolleri hakkında daha fazla bilgi edinin](../../admin/add-users/about-admin-roles.md).

| İzin düzeyi | Açıklama |
|:---|:---|
| **Genel yöneticiler** (genel yöneticiler olarak da adlandırılır) <p> *En iyi yöntem olarak genel yönetici sayısını sınırlayın.* | Genel yöneticiler her türlü görevi gerçekleştirebilir. Şirketinizi Microsoft 365 veya İş için Defender'a kaydolan kişi varsayılan olarak genel yöneticidir. <p> Genel yöneticiler, aşağıdakiler gibi tüm Microsoft 365 portallarında ayarları değiştirebilir: <ul><li>Microsoft 365 yönetim merkezi ([https://admin.microsoft.com](https://admin.microsoft.com))</li><li>Microsoft 365 Defender portalı ([https://security.microsoft.com](https://security.microsoft.com))</li></ul> |
| **Güvenlik yöneticileri** (güvenlik yöneticileri olarak da adlandırılır) | Güvenlik yöneticileri aşağıdaki görevleri gerçekleştirebilir: <ul><li>Güvenlik ilkelerini görüntüleme ve yönetme</li><li>Güvenlik tehditlerini ve uyarılarını görüntüleme ve yönetme (bu etkinlikler uç noktalarda yanıt eylemleri gerçekleştirmeyi içerir)</li><li>Güvenlik bilgilerini ve raporlarını görüntüleme</li></ul> |
| **Güvenlik gözetmeni** | Güvenlik okuyucuları aşağıdaki görevleri gerçekleştirebilir:<ul><li>Güvenlik ilkelerini görüntüleme</li><li>Güvenlik tehditlerini ve uyarılarını görüntüleme</li><li>Güvenlik bilgilerini ve raporlarını görüntüleme</li></ul>  |


## <a name="view-or-edit-role-assignments"></a>Rol atamalarını görüntüleme veya düzenleme

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **İzinler & roller'i** seçin ve **Azure AD** altında **Roller'i** seçin.

3. Yan bölmesini açmak için aşağıdaki rollerden birini seçin:

   - Genel yönetici
   - Güvenlik yöneticisi
   - Güvenlik gözetmeni

   > [!IMPORTANT]
   > Microsoft, kişilere yalnızca görevlerini gerçekleştirmeleri için gerekenlere erişim vermenizi önerir. Bu kavramı izinler için *en az ayrıcalık* olarak adlandırıyoruz. Daha fazla bilgi edinmek için bkz. [Uygulamalar için en az ayrıcalıklı erişim için en iyi yöntemler](/azure/active-directory/develop/secure-least-privileged-access). 

4. Yan bölmede **üyeleri Azure AD yönet** bağlantısını seçin. Bu eylem sizi rol atamalarınızı görüntüleyip yönetebileceğiniz Azure Active Directory'ye (Azure AD) götürür.

5. Profilini açmak için bir kullanıcı seçin ve ardından **Atanan roller'i** seçin.

   - Rol eklemek için **+ Atama ekle'yi** seçin.
   - Rolü kaldırmak için **X Atamaları kaldır'ı** seçin. 

## <a name="need-to-add-users"></a>Kullanıcı eklemeniz mi gerekiyor?

Aboneliğinize henüz kullanıcı eklemediyseniz bkz. [Aynı anda kullanıcı ekleme ve lisans atama](mdb-add-users.md).

## <a name="next-steps"></a>Sonraki adımlar

Git:

- [3. Adım: E-posta bildirimlerini ayarlama](mdb-email-notifications.md)
- [4. Adım: Cihazları İş için Defender'a ekleme](mdb-onboard-devices.md)