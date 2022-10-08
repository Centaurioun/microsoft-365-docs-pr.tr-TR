---
title: Microsoft 365 Defender portalındaki izinler
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
ms.localizationpriority: high
ms.collection:
- m365-security
search.appverid:
- MOE150
- MET150
description: Yöneticiler, güvenlikle ilgili tüm görevler için Microsoft 365 Defender portalında izinleri yönetmeyi öğrenebilir.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: a968a74ab113b79148dfb502091e0c84b485d54a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68090585"
---
# <a name="permissions-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalındaki izinler

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Tüm Microsoft 365 hizmetlerini kapsayan güvenlik senaryolarını yönetmeniz gerekir. Ayrıca kuruluşunuzdaki doğru kişilere doğru yönetici izinlerini verme esnekliğine sahip olmanız gerekir.

konumundaki <https://security.microsoft.com> Microsoft 365 Defender portalı, Microsoft 365'te güvenlik görevlerini gerçekleştiren kullanıcılar için izinleri doğrudan yönetmeyi destekler. İzinleri yönetmek için Microsoft 365 Defender portalını kullanarak, güvenlikle ilgili tüm görevler için izinleri merkezi olarak yönetebilirsiniz.

Microsoft 365 Defender portalındaki izinleri yönetmek için **İzinler & rolleri** veya <https://security.microsoft.com/securitypermissions>bölümüne gidin. Microsoft 365 Defender portalında **genel yönetici** veya **Kuruluş Yönetimi** rol grubunun üyesi olmanız gerekir. Özellikle, **Rol Yönetimi** rolü kullanıcıların Microsoft 365 Defender portalında rol gruplarını görüntülemesine, oluşturmasına ve değiştirmesine olanak tanır ve bu rol varsayılan olarak yalnızca **Kuruluş Yönetimi** rol grubuna atanır.

> [!NOTE]
> Microsoft Purview uyumluluk portalı izinler hakkında bilgi için bkz. [Microsoft Purview uyumluluk portalı İzinler](../../compliance/microsoft-365-compliance-center-permissions.md).

## <a name="relationship-of-members-roles-and-role-groups"></a>Üyelerin, rollerin ve rol gruplarının ilişkisi

Microsoft 365 Defender portalındaki izinler rol tabanlı erişim denetimi (RBAC) izin modelini temel alır. RBAC, Microsoft 365 hizmetlerinin çoğu tarafından kullanılan izin modeliyle aynıdır, bu nedenle bu hizmetlerdeki izin yapısı hakkında bilgi sahibiyseniz, Microsoft 365 Defender portalında izinler vermek çok tanıdık olacaktır.

**Rol**, bir dizi görevi yerine getirmek için izinler verir.

**Rol grubu**, kişilerin işlerini Microsoft 365 Defender portalında yapmalarına olanak tanıyan bir dizi roldür.

Microsoft 365 Defender portalı>, atamanız gereken en yaygın görevler ve işlevler için varsayılan rol gruplarını içerir. Genel olarak, varsayılan rol gruplarına tek tek kullanıcıları **üye** olarak eklemenizi öneririz.

:::image type="content" source="../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png" alt-text="Rol grubunun rolleri ve üyeleriyle ilişkisi" lightbox="../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png":::

## <a name="roles-and-role-groups-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalındaki roller ve rol grupları

Aşağıdaki rol ve rol grubu türleri, Microsoft 365 Defender portalındaki **İzinler & rolleri** sayfasında <https://security.microsoft.com/securitypermissions> bulunabilir:

- **Azure AD rolleri**: Rolleri ve atanan kullanıcıları görüntüleyebilirsiniz, ancak bunları doğrudan Microsoft 365 Defender portalında yönetemezsiniz. Azure AD rolleri **, tüm** Microsoft 365 hizmetleri için izin atayan merkezi rollerdir.

- **Email & işbirliği rolleri**: Bunlar, Güvenlik & Uyumluluk Merkezi'nde kullanılabilen rol gruplarıyla aynıdır, ancak bunları doğrudan Microsoft 365 Defender portalından yönetebilirsiniz. Burada atadığınız izinler Microsoft 365 Defender portalına, Microsoft Purview uyumluluk portalı ve Güvenlik & Uyumluluk Merkezi'ne özeldir ve diğer Microsoft 365 iş yüklerinde gereken tüm izinleri kapsamaz.

:::image type="content" source="../../media/m365-sc-permissions-and-roles-page.png" alt-text="Microsoft 365 Defender portalındaki İzinler & rolleri sayfası" lightbox="../../media/m365-sc-permissions-and-roles-page.png":::

### <a name="azure-ad-roles-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında rolleri Azure AD

Microsoft 365 Defender portalını adresinde <https://security.microsoft.com> açıp **Email & işbirliği rollerine** \> **izinler & roller Azure AD rollere** \>  \> **(veya** doğrudan) <https://security.microsoft.com/aadpermissions>gittiğinizde, bu bölümde açıklanan Azure AD rolleri görürsünüz.

Bir rol seçtiğinizde, rolün açıklamasını ve kullanıcı atamalarını içeren ayrıntılar açılır öğesi görüntülenir. Ancak bu atamaları yönetmek için ayrıntılar açılır **öğesinde Azure AD üyeleri yönet'e** tıklamanız gerekir.

:::image type="content" source="../../media/permissions-manage-in-azure-ad-link.png" alt-text="Azure Active Directory'de izinleri yönetme bağlantısı" lightbox="../../media/permissions-manage-in-azure-ad-link.png":::

Daha fazla bilgi için bkz. [Azure Active Directory'de yönetici rollerini görüntüleme ve atama](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

|Rol|Açıklama|
|---|---|
|**Genel yönetici**|Tüm Microsoft 365 hizmetlerindeki tüm yönetim özelliklerine erişim. Yalnızca genel yöneticiler diğer yönetici rollerini atayabilir. Daha fazla bilgi için bkz. [Genel Yönetici / Şirket Yöneticisi](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Uyumluluk veri yöneticisi**|Microsoft 365 genelinde kuruluşunuzun verilerini takip edin, korunduğundan emin olun ve riskleri azaltmaya yardımcı olacak sorunlarla ilgili içgörüler edinin. Daha fazla bilgi için bkz [. Uyumluluk Verileri Yöneticisi](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Uyumluluk yöneticisi**|Kuruluşunuzun tüm mevzuat gereksinimleriyle uyumlu kalmasına, eBulma servis taleplerini yönetmeye ve Microsoft 365 konumları, kimlikleri ve uygulamaları genelinde veri idare ilkelerini korumalarına yardımcı olun. Daha fazla bilgi için bkz [. Uyumluluk Yöneticisi](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Güvenlik operatörü**|Microsoft 365 kullanıcılarınıza, cihazlarınıza ve içeriğinize yönelik etkin tehditleri görüntüleyin, araştırın ve yanıt verin. Daha fazla bilgi için bkz [. Güvenlik İşleci](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Güvenlik gözetmeni**|Microsoft 365 kullanıcılarınıza, cihazlarınıza ve içeriğinize yönelik etkin tehditleri görüntüleyin ve araştırın, ancak (Güvenlik operatörünün aksine) eylem gerçekleştirerek yanıt verme izinleri yoktur. Daha fazla bilgi için bkz [. Güvenlik Okuyucusu](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Güvenlik yöneticisi**|Güvenlik ilkelerini yöneterek, Microsoft 365 ürünleri genelinde güvenlik analizlerini ve raporlarını gözden geçirerek ve tehdit ortamı konusunda güncel kalarak kuruluşunuzun genel güvenliğini denetleyin. Daha fazla bilgi için bkz [. Güvenlik Yöneticisi](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Genel okuyucu**|**Genel yönetici** rolünün salt okunur sürümü. Microsoft 365 genelindeki tüm ayarları ve yönetim bilgilerini görüntüleyin. Daha fazla bilgi için bkz. [Genel Okuyucu](/azure/active-directory/roles/permissions-reference#global-reader).|
|**Saldırı benzetimi yöneticisi**|[Saldırı simülasyonu](attack-simulation-training.md) oluşturma, simülasyon başlatma/zamanlama ve simülasyon sonuçlarının gözden geçirilmesinin tüm yönlerini oluşturun ve yönetin. Daha fazla bilgi için bkz [. Saldırı Benzetimi Yöneticisi](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Saldırı yükü yazarı**|Saldırı yükleri oluşturun, ancak aslında başlatmayı veya zamanlamayı değil. Daha fazla bilgi için bkz [. Saldırı Yükü Yazarı](/azure/active-directory/roles/permissions-reference#attack-payload-author).|

### <a name="email--collaboration-roles-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında işbirliği rollerini Email &

Microsoft 365 Defender portalını adresinde <https://security.microsoft.com> açıp **Email & işbirliği rollerine** \> **izinler & roller** \> **Email & işbirliği rolleri** \> **Roller'e** (veya doğrudan adresine<https://security.microsoft.com/emailandcollabpermissions>) gittiğinizde, Güvenlik & Uyumluluk Merkezi'nde bulunan rol gruplarının aynısını görürsünüz.

Bu rol grupları hakkında tam bilgi için bkz [. Güvenlik & Uyumluluk Merkezi'nde İzinler](permissions-in-the-security-and-compliance-center.md)

#### <a name="modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında Email & işbirliği rolü üyeliğini değiştirme

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Email & işbirliği rolleri** \> **İzinler & roller** \> **Email & işbirliği rolleri** \> **Rolleri'ne** gidin. **doğrudan İzinler** sayfasına gitmek için kullanın<https://security.microsoft.com/emailandcollabpermissions>.

2. **İzinler** sayfasında, listeden değiştirmek istediğiniz rol grubunu seçin. Listeyi ada göre sıralamak için **Ad** sütunu üst bilgisine veya **Arama Arama** ![simgesine tıklayabilirsiniz.](../../media/m365-cc-sc-search-icon.png) öğesini seçin.

3. Görüntülenen rol grubu ayrıntıları açılır öğesinde **, Üyeler** bölümünde **Düzenle'ye** tıklayın.

4. Görüntülenen **Üyeleri seçmeyi düzenleme** sayfasında aşağıdaki adımlardan birini yapın:
   - Rol grubu üyesi yoksa **Üye seç'e** tıklayın.
   - Mevcut rol grubu üyeleri varsa **Düzenle'ye** tıklayın

5. Görüntülenen **Üyeleri seçin** açılır öğesinde aşağıdaki adımlardan birini yapın:

   - **Ekle**'ye tıklayın. Görüntülenen kullanıcı listesinde bir veya daha fazla kullanıcı seçin. İsterseniz Arama **Arama** ![simgesine de tıklayabilirsiniz.](../../media/m365-cc-sc-search-icon.png) ögesini seçerek kullanıcıları bulun ve seçin.

     Eklemek istediğiniz kullanıcıları seçtiğinizde **Ekle'ye** tıklayın.

   - **Kaldır**'a tıklayın. Mevcut üyelerden birini veya daha fazlasını seçin. İsterseniz Arama **Arama** ![simgesine de tıklayabilirsiniz.](../../media/m365-cc-sc-search-icon.png) ögesini seçerek üyeleri bulun ve seçin.

     Kaldırmak istediğiniz kullanıcıları seçtiğinizde **Kaldır'a** tıklayın.

6. **Üyeleri seçin** açılır menüsüne geri dönüp **Bitti'ye** tıklayın.

7. **Üyeleri seçmeyi düzenleme** sayfasına geri dönüp **Kaydet'e** tıklayın.

8. Rol grubu ayrıntıları açılır menüsüne geri dönüp **Bitti'ye** tıklayın.
