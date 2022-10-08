---
title: Rol tabanlı erişim denetimi için roller oluşturma ve yönetme
description: Rol oluşturma ve Microsoft 365 Defender rol tabanlı erişim denetimi uygulamasının bir parçası olarak role atanan izinleri tanımlama
keywords: kullanıcı rolleri, roller, erişim rbac
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: e2229e0f0c4e34b71c054f352e4e94fc029daa51
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232858"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>Rol tabanlı erişim denetimi için roller oluşturma ve yönetme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>Rol oluşturma ve rolü bir Azure Active Directory grubuna atama

Aşağıdaki adımlar, Microsoft 365 Defender'da rol oluşturma konusunda size yol gösterir. Azure Active Directory kullanıcı gruplarını önceden oluşturduğunuz varsayılır.

1. Atanmış bir Güvenlik yöneticisi veya <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Genel yönetici</a> rolü olan hesabı kullanarak Microsoft 365 Defender oturum açın.

2. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Rolleri'ni** seçin ( **İzinler'in** altında).

3. **Öğe ekle'yi** seçin.

4. Role atamak istediğiniz rol adını, açıklamasını ve izinlerini girin.

5. Rolü bir Azure AD Güvenlik grubuna atamak için **İleri'yi** seçin.

6. Bu role eklemek istediğiniz Azure AD grubunu seçmek için filtreyi kullanın.

7. **Kaydedip kapatın**.

8. Yapılandırma ayarlarını uygulayın.

> [!IMPORTANT]
> Rolleri oluşturduktan sonra, yeni oluşturduğunuz bir role atayarak bir cihaz grubu oluşturmanız ve cihaz grubuna erişim sağlamanız gerekir.

> [!NOTE]
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.

### <a name="permission-options"></a>İzin seçenekleri

- **Verileri görüntüleme**
  - **Güvenlik işlemleri** - Portalda tüm güvenlik işlemleri verilerini görüntüleme
  - **Tehdit ve güvenlik açığı yönetimi** - Portalda Defender Güvenlik Açığı Yönetimi verilerini görüntüleme

- **Etkin düzeltme eylemleri**
  - **Güvenlik işlemleri** - Yanıt eylemleri gerçekleştirme, bekleyen düzeltme eylemlerini onaylama veya kapatma, otomasyon ve göstergeler için izin verilen/engellenen listeleri yönetme
  - **Tehdit ve güvenlik açığı yönetimi - Özel durum işleme** - Yeni özel durumlar oluşturma ve etkin özel durumları yönetme
  - **Tehdit ve güvenlik açığı yönetimi - Düzeltme işleme** - Yeni düzeltme istekleri gönderme, bilet oluşturma ve mevcut düzeltme etkinliklerini yönetme

- **Uyarı araştırması - Uyarıları** yönetme, otomatik araştırma başlatma, tarama çalıştırma, araştırma paketlerini toplama, cihaz etiketlerini yönetme ve yalnızca taşınabilir yürütülebilir (PE) dosyaları indirme

- **Portal sistem ayarlarını yönetme** - Depolama ayarlarını, SIEM ve tehdit intel API ayarlarını yapılandırma (genel olarak geçerlidir), gelişmiş ayarlar, otomatik dosya yüklemeleri, roller ve cihaz grupları

    > [!NOTE]
    > Bu ayar yalnızca Uç Nokta için Microsoft Defender yöneticisi (varsayılan) rolünde kullanılabilir.

- **Güvenlik Merkezi'nde güvenlik ayarlarını yönetme** - Uyarı engelleme ayarlarını yapılandırma, otomasyon için klasör dışlamalarını yönetme, cihazları ekleme ve çıkarma, e-posta bildirimlerini yönetme ve değerlendirme laboratuvarını yönetme

- **Canlı yanıt özellikleri**
  - **Temel** komutlar:
    - Canlı yanıt oturumu başlatma
    - Uzak cihazda salt okunur canlı yanıt komutları gerçekleştirme (dosya kopyalama ve yürütme hariç)
    - Canlı yanıt aracılığıyla uzak cihazdan bir dosya indirme
  - **Gelişmiş** komutlar:
    - PE ve PE olmayan dosyaları dosya sayfasından indirme
    - Uzak cihaza dosya yükleme
    - Dosya kitaplığından betik görüntüleme
    - Dosya kitaplığından uzak cihazda betik yürütme

Kullanılabilir komutlar hakkında daha fazla bilgi için bkz [. Canlı yanıt kullanarak cihazları araştırma](live-response.md).

## <a name="edit-roles"></a>Rolleri düzenleme

1. Güvenlik yöneticisi veya <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Genel yönetici</a> rolü atanmış hesabı kullanarak Microsoft 365 Defender oturum açın.

2. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Rolleri'ni** seçin ( **İzinler'in** altında).

3. Düzenlemek istediğiniz rolü seçin.

4. **Düzenle**’ye tıklayın.

5. Role atanan ayrıntıları veya grupları değiştirin.

6. **Kaydet'e tıklayın ve kapatın**.

## <a name="delete-roles"></a>Rolleri silme

1. Güvenlik yöneticisi veya <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Genel yönetici</a> rolü atanmış hesabı kullanarak Microsoft 365 Defender oturum açın.

2. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Rolleri'ni** seçin ( **İzinler'in** altında).

3. Silmek istediğiniz rolü seçin.

4. Açılan düğmeye tıklayın ve **Rolü sil'i** seçin.

## <a name="related-topic"></a>İlgili konu

- [Portala erişmek için kullanıcı temel izinleri](basic-permissions.md)
- [Cihaz grupları oluşturun ve yönetin](machine-groups.md)
