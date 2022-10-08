---
title: Engellenen bağlayıcıları Microsoft 365'teki Kısıtlı varlıklar portalından kaldırma
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- m365-security
ms.custom: ''
description: Microsoft 365 Defender'da engellenen bağlayıcıları kaldırmayı öğrenin.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: e376676045a68d4127fbdd7eb05e0000c6e0788d
ms.sourcegitcommit: edc9d4dec92ca81cff39bbf9590f1cd3a75ec436
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68484313"
---
# <a name="remove-blocked-connectors-from-the-restricted-entities-portal"></a>Engellenen bağlayıcıları Kısıtlı varlıklar portalından kaldırma

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**

- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Gelen bağlayıcının risk altında olduğu algılanırsa, herhangi bir geçiş e-postası göndermesi kısıtlanır. Bağlayıcı daha sonra Microsoft 365 Defender portalındaki **Kısıtlı varlıklar** sayfasına eklenir. Bağlayıcı e-posta göndermek için kullanıldığında, ileti 550;5.7.711 hata kodu ve aşağıdaki metinle birlikte teslim edilmedi raporunda (NDR veya geri dönen ileti olarak da bilinir) döndürülür:

> İletiniz teslim edilemedi. Bunun en yaygın nedeni, kuruluşunuzun e-posta bağlayıcısının istenmeyen posta veya kimlik avı gönderdiğinden şüphelenilmiş olması ve artık e-posta göndermesine izin verilmemiş olmasıdır. Yardım için e-posta yöneticinize başvurun.
> Uzak Sunucu '550;5.7.711 Erişim reddedildi, hatalı gelen bağlayıcı döndürdü. AS(2204).'

Yöneticiler, Microsoft 365 Defender veya Exchange Online PowerShell'deki Kısıtlı varlıklar sayfasından bağlayıcıları kaldırabilir.

## <a name="learn-more-on-restricted-entities"></a>Kısıtlanmış varlıklar hakkında daha fazla bilgi edinin

Kısıtlanmış varlık, gizliliği tehlikeye girmiş veya gönderme sınırını aşmış olduğundan e-posta göndermesi engellenmiş bir varlıktır.

2 tür kısıtlanmış varlık vardır:

- **Kısıtlanmış kullanıcı**: Bir kullanıcının neden kısıtlandığı ve kısıtlı kullanıcıların nasıl işlendiği hakkında daha fazla bilgi için bkz. [Kısıtlı varlıklar portalından engellenen kullanıcıları kaldırma](removing-user-from-restricted-users-portal-after-spam.md).

- **Kısıtlanmış bağlayıcı**: Bağlayıcının neden kısıtlandığını ve kısıtlanmış bağlayıcıların nasıl işleyebileceğinizi öğrenin (bu makale).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- adresinde Microsoft 365 Defender portalını <https://security.microsoft.com>açın. **Doğrudan Kısıtlı varlıklar** sayfasına gitmek için kullanın<https://security.microsoft.com/restrictedentities>.

- Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

- Bu makalede belirtilen yordamları izleyebilmeniz için **önce Exchange Online'da** izinleriniz olmalıdır:
  - Kısıtlanmış varlıklar portalından bağlayıcıları kaldırmak için **Kuruluş Yönetimi** veya **Güvenlik Yöneticisi** rol gruplarının üyesi olmanız gerekir.
  - Kısıtlı varlıklar portalına salt okunur erişim için **Genel Okuyucu** veya **Güvenlik Okuyucusu** rol gruplarının üyesi olmanız gerekir.

  Daha fazla bilgi için bkz. [Exchange Online'de İzinler](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - kullanıcıları Microsoft 365 yönetim merkezi ilgili Azure Active Directory rolüne eklemek, kullanıcılara Microsoft 365'teki diğer özellikler için gerekli izinleri _ve_ izinleri verir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../../admin/add-users/about-admin-roles.md).
  >
  > - [Exchange Online'daki](/Exchange/permissions-exo/permissions-exo#role-groups) **Yalnızca Görüntüleme Kuruluş Yönetimi** rol grubu da özelliğe salt okunur erişim sağlar.

- Bağlayıcıyı Kısıtlı varlıklar portalından kaldırmadan önce, bağlayıcının denetimini yeniden kazanmak için gerekli adımları izlediğinizden emin olun. Daha fazla bilgi için bkz. [Güvenliği aşılmış bağlayıcıya yanıt verme](respond-compromised-connector.md).

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-connector-from-the-restricted-entities-list"></a>Bağlayıcıyı Kısıtlı varlıklar listesinden kaldırmak için Microsoft 365 Defender portalını kullanma

1. [Microsoft 365 Defender portalında](https://security.microsoft.com)**, Email & işbirliği** \> **Kısıtlı varlıkları** **gözden geçirme** \> bölümüne gidin. **Doğrudan Kısıtlı varlıklar** sayfasına gitmek için kullanın<https://security.microsoft.com/restrictedentities>.

2. **Kısıtlı varlıklar** sayfasında, bağlayıcıya tıklayarak engellemesini kaldırmak istediğiniz bağlayıcıyı bulun ve seçin.

3. Görüntülenen **Engellemeyi Kaldır** eylemine tıklayın.

4. Görüntülenen **Engeli Kaldır varlığı** açılır öğesinde, kısıtlanmış bağlayıcı hakkındaki ayrıntıları okuyun. Bağlayıcının gizliliğinin ihlal edilmesi durumunda uygun eylemleri gerçekleştirdiğinizden emin olmak için önerileri gözden geçirmeniz gerekir.

5. İşiniz bittiğinde **Engellemeyi Kaldır'a** tıklayın.

   > [!NOTE]
   > Bağlayıcıdan tüm kısıtlamaların kaldırılması 1 saat kadar sürebilir.

## <a name="verify-the-alert-settings-for-restricted-connectors"></a>Kısıtlanmış bağlayıcılar için uyarı ayarlarını doğrulama

Şüpheli bağlayıcı etkinliği adlı varsayılan uyarı ilkesi **, bağlayıcıların** e-posta geçişi engellendiğinde yöneticileri otomatik olarak bilgilendirir. Uyarı ilkeleri hakkında daha fazla bilgi için bkz. [Microsoft 365'te uyarı ilkeleri](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Uyarıların çalışması için denetim günlüğü aramanın açık olması gerekir. Daha fazla bilgi için bkz [. Denetim günlüğü aramasını açma veya kapatma](../../compliance/turn-audit-log-search-on-or-off.md).

1. Microsoft 365 Defender portalında **Email & işbirliği** \> **İlkeleri & kuralları** \> **Uyarı ilkesi'ne** gidin.

2. **Uyarı ilkesi** sayfasında **Şüpheli bağlayıcı etkinliği** adlı uyarıyı bulun ve seçin. İlkeleri ada göre sıralayabilir veya **arama kutusunu** kullanarak ilkeyi bulabilirsiniz.

3. Görüntülenen **Şüpheli bağlayıcı etkinliği** açılır öğesinde aşağıdaki ayarları doğrulayın veya yapılandırın:
   - **Durum**: Uyarının açık ![olduğunu doğrulayın.](../../media/scc-toggle-on.png)
   - **alıcıları Email: Alıcıları** düzenle **açılır penceresinde** **Düzenle'ye** tıklayın ve aşağıdaki ayarları doğrulayın veya yapılandırın:
     - **E-posta bildirimleri gönder**: Bunun seçili olduğunu doğrulayın (**Açık**).
     - **Email alıcılar**: Varsayılan değer **TenantAdmins'tir** (genel **yönetici** üyeleri anlamına gelir). Daha fazla alıcı eklemek için kutunun boş bir alanına tıklayın. Alıcıların listesi görüntülenir ve bir alıcıyı filtrelemek ve seçmek için bir ad yazmaya başlayabilirsiniz. Kaldır simgesine tıklayarak ![kutudan var olan bir alıcıyı kaldırabilirsiniz.](../../media/m365-cc-sc-remove-selection-icon.png) öğesini seçin.
     - **Günlük bildirim sınırı**: Sınır, bağlayıcı başına günde en fazla 3 bildirimdir.

     Bitirdiğinizde, **Kaydet**'i tıklatın.

4. **Şüpheli bağlayıcı etkinliği** açılır menüsüne geri dönüp **Kapat'a** tıklayın.

## <a name="use-exchange-online-powershell-to-view-and-remove-connectors-from-the-restricted-entities-list"></a>Bağlayıcıları Kısıtlı varlıklar listesinden görüntülemek ve kaldırmak için Exchange Online PowerShell kullanma

E-posta göndermesi kısıtlanmış bağlayıcıların listesini görüntülemek için aşağıdaki komutu çalıştırın:

```powershell
Get-BlockedConnector
```

Belirli bir bağlayıcıyla ilgili ayrıntıları görüntülemek için aşağıdaki komutu değiştirin \<connectorId\> ve çalıştırın:

```powershell
Get-BlockedConnector -ConnectorId <connectorId>
```

Bir bağlayıcıyı Kısıtlı varlıklar listesinden kaldırmak için aşağıdaki komutu değiştirin \<connectorId\> ve çalıştırın:

```powershell
Remove-BlockedConnector -ConnectorId <connectorId>
```

## <a name="more-information"></a>Daha fazla bilgi

- [Risk altındaki bağlayıcıyı yanıtlama](respond-compromised-connector.md)
- [Engellenen kullanıcıları kaldırma](removing-user-from-restricted-users-portal-after-spam.md)
