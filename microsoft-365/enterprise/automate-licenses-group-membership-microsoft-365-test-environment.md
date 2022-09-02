---
title: Kurumsal test ortamınız için Microsoft 365 için lisanslama ve grup üyeliğini otomatikleştirme
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Kurumsal test ortamınız için Microsoft 365'te grup tabanlı lisanslama ve dinamik grup üyeliği yapılandırma.
ms.openlocfilehash: ba980e0fe6553993cf701bab4d4fb2e4f9826da4
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67560141"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Kurumsal test ortamınız için Microsoft 365 için lisanslama ve grup üyeliğini otomatikleştirme

*Bu Test Laboratuvarı Kılavuzu yalnızca kurumsal test ortamları için Microsoft 365 için kullanılabilir.*

Grup tabanlı lisanslama, grup üyeliğine bağlı olarak bir kullanıcı hesabı için lisansları otomatik olarak atar veya kaldırır. Dinamik grup üyeliği, **Departman** veya **Ülke** gibi kullanıcı hesabı özelliklerine göre gruba üye ekler veya kaldırır. Bu makale, kurumsal test ortamınız için Microsoft 365'te grup üyeleri ekleme ve kaldırma tanıtımlarında size yol gösterir.

Kurumsal test ortamınız için Microsoft 365'te otomatik lisanslama ve dinamik grup üyeliğinin ayarlanması iki aşamadan oluşur:

- [1. Aşama: Kurumsal test ortamı için Microsoft 365'inizi oluşturma](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2. Aşama: Dinamik grup üyeliğini ve otomatik lisanslamayı yapılandırma ve test edin](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft bulutu için Test Laboratuvarı Kılavuzları.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Microsoft 365 kurumsal Test Laboratuvarı Kılavuzu yığınındaki tüm makalelere yönelik görsel bir harita için [, Kurumsal Test Laboratuvarı Kılavuz Yığını için Microsoft 365'e](../downloads/Microsoft365EnterpriseTLGStack.pdf) gidin.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1. Aşama: Kurumsal test ortamı için Microsoft 365'inizi oluşturma

Otomatik lisanslama ve grup üyeliğini yalnızca minimum gereksinimlerle basit bir şekilde test etmek istiyorsanız [Basit temel yapılandırma](lightweight-base-configuration-microsoft-365-enterprise.md) yönergelerini izleyin.
  
Sanal bir kuruluşta otomatik lisanslama ve grup üyeliğini test etmek istiyorsanız [Geçişli kimlik doğrulamasındaki](pass-through-auth-m365-ent-test-environment.md) yönergeleri izleyin.
  
> [!NOTE]
> Otomatik lisanslama ve grup üyeliğinin test edilmesi için İnternet'e bağlı bir sanal intranet ve bir Active Directory Domain Services (AD DS) ormanı için dizin eşitlemesi içeren sanal kurumsal test ortamı gerekmez. Burada, otomatik lisanslama ve grup üyeliğini test edebilmeniz ve tipik bir kuruluşu temsil eden bir ortamda denemeler yapabileceğiniz bir seçenek olarak sağlanır.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>2. Aşama: Dinamik grup üyeliğini ve otomatik lisanslamayı yapılandırma ve test edin

İlk olarak Sales adlı yeni bir grup oluşturun ve **Departman'ın** **Satış** olarak ayarlandığı kullanıcı hesaplarının Sales grubuna otomatik olarak katılması için dinamik bir grup üyeliği kuralı ekleyin.

1. İnternet tarayıcınızın özel bir örneğinde[, Microsoft 365 E5](https://admin.microsoft.com) test laboratuvarı aboneliğinizin genel yönetici hesabıyla Microsoft 365 yönetim merkezi oturum açın.
2. Tarayıcınızın ayrı bir sekmesinde konumundaki Azure portal [https://portal.azure.com](https://portal.azure.com)gidin.
3. Azure portal, arama kutusuna **gruplar** girin ve ardından **Gruplar'ı** seçin.
4. **Tüm gruplar** bölmesinde **Yeni grup'a** tıklayın.
5. **Grup türü'nde** **Microsoft 365'i** seçin.
6. **Grup adı** alanına **Satışlar** yazın.
7. **Üyelik türü'nde** **Dinamik kullanıcı'yı** seçin.
8. **Dinamik kullanıcı üyeleri'ne tıklayın**.
9. **Dinamik üyelik kuralları** bölmesinde: 
   - **Departman** özelliğini seçin.
   - **Eşittir** işlecini seçin.
   - **Değer** kutusuna **Satışlar** yazın.
10. **Kaydet**'i seçin.
11. **Oluştur**’u seçin.

Ardından Satış grubunu, üyelere otomatik olarak Microsoft 365 E5 lisansı atanması için yapılandırın.

1. **Satış** grubunu ve ardından **Lisanslar'ı** seçin.
2. **Lisans atamalarını güncelleştir** bölmesinde **Microsoft 365 E5** ve ardından **Kaydet'i** seçin.
3. Tarayıcınızda Azure portal sekmesini kapatın.

Ardından, User 4 hesabında dinamik grup üyeliğini ve otomatik lisanslamayı test edin:

1. Tarayıcınızdaki **Microsoft Office Giriş** **sekmesinden Yönetici'ı** seçin.
2. **Microsoft 365 yönetim merkezi** sekmesinde **Etkin kullanıcılar'ı** seçin.
3. **Etkin kullanıcılar** sayfasında **Kullanıcı 4** hesabını seçin.
4. **Kullanıcı 4** bölmesinde **Ürün lisansları** için **düzenle'yi** seçin.
5. **Ürün lisansları** bölmesinde **Microsoft 365 E5** lisansını devre dışı bırakın ve Ardından **Kapat'ı Kaydet'i** >  seçin.
6. Kullanıcı 4 hesabının özelliklerinde, hiçbir ürün lisansının atanmadığını ve grup üyeliği olmadığını doğrulayın.
7. **Kişi bilgileri** için **Düzenle'yi** seçin.
8. **Kişi bilgilerini düzenle** bölmesinde **Kişi bilgileri'ni** seçin.
9. **Departman** kutusuna **Satış** yazın ve **Ardından** **Kapat'ı Kaydet'i** >  seçin.
10. Birkaç dakika bekleyin ve ardından Kullanıcı 4 hesabı bölmesinin sağ üst köşesindeki **Yenile** simgesini düzenli aralıklarla seçin.

Zaman içinde şunları görmeniz gerekir:

- **Grup üyelikleri** özelliği **Sales** grubuyla güncelleştirildi.
- **Ürün lisansları** özelliği **Microsoft 365 E5** lisansıyla güncelleştirildi.

Üretimde dinamik grup üyeliği ve otomatik lisanslama dağıtmak için şu makalelere bakın:

- [Azure Active Directory'de grup tabanlı lisanslama](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Azure Active Directory'de dinamik gruplar](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Sonraki adım

Test ortamınızdaki ek [kimlik](m365-enterprise-test-lab-guides.md#identity) özelliklerini ve özelliklerini keşfedin.

## <a name="see-also"></a>Ayrıca bkz.

[Kimliği dağıtma](deploy-identity-solution-overview.md)

[Kurumsal test laboratuvarı kılavuzları için Microsoft 365](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Kurumsal belgeler için Microsoft 365](/microsoft-365-enterprise/)