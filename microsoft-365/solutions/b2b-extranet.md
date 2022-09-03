---
title: Yönetilen konuklarla B2B extranet oluşturma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: İş ortağı kuruluştan yönetilen konuklarla B2B extranet sitesi veya ekip oluşturmayı öğrenin.
ms.openlocfilehash: 35410cc13b771a6f22d0e85d2f1592f1c7dbb048
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67579743"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a>Yönetilen konuklarla B2B extranet oluşturma

[Azure Active Directory Yetkilendirme Yönetimi'ni kullanarak, Azure Active Directory](/azure/active-directory/governance/entitlement-management-overview) kullanan bir iş ortağı kuruluşuyla işbirliği yapmak üzere B2B extranet oluşturabilirsiniz. Bu, kullanıcıların extranet sitesine veya ekibine kendi kendine kaydolmasına ve onay iş akışı aracılığıyla erişim almasına olanak tanır.

İş ortağı kuruluş, işbirliğine yönelik bu kaynak paylaşımı yöntemiyle, konukların kendi başlarına bakımını yapmaya ve onaylamaya yardımcı olarak BT departmanınızın üzerindeki yükü azaltabilir ve işbirliği anlaşmasına en aşina olanların kullanıcı erişimini yönetmesine olanak tanıyabilir.

Bu makalede, self servis erişim kayıt modeli aracılığıyla bir iş ortağı kuruluşla paylaşabileceğiniz bir kaynak paketi (bu örnekte bir site veya ekip) oluşturma adımları gösterilir. 

Başlamadan önce, iş ortağı kuruluşla paylaşmak istediğiniz siteyi veya ekibi oluşturun ve konuk paylaşımı için etkinleştirin. Daha fazla bilgi için bkz. [Sitedeki konuklarla işbirliği](collaborate-in-site.md) [yapma veya Ekipteki konuklarla işbirliği yapma](collaborate-as-team.md) . Ayrıca, konuklarla işbirliği yaparken idare ilkelerinizin korunmasına yardımcı olmak için kullanabileceğiniz güvenlik ve uyumluluk özellikleri hakkında bilgi için [Güvenli bir konuk paylaşım ortamı oluşturma](create-secure-guest-sharing-environment.md) bölümünü gözden geçirmenizi öneririz.

## <a name="license-requirements"></a>Lisans gereksinimleri

Bu özelliği kullanmak için Azure AD Premium P2 lisansı gerekir. 

Azure Almanya ve Azure China 21Vianet gibi özelleştirilmiş bulutlar şu anda kullanılamıyor.

## <a name="video-demonstration"></a>Video tanıtımı

Bu videoda, bu makalede ele alınan yordamlar gösterilmektedir.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a>İş ortağı kuruluşuna bağlanma

Bir iş ortağı kuruluşundan konuk davet etmek için iş ortağının etki alanını Azure Active Directory'de bağlı bir kuruluş olarak eklemeniz gerekir.

Bağlı kuruluş eklemek için
1. [Azure Active Directory'de](https://aad.portal.azure.com) **Kimlik İdaresi'ne** tıklayın.
2. **Bağlı kuruluşlar'a** tıklayın.
4. **Bağlı kuruluş ekle'ye** tıklayın.
5. Kuruluş için bir ad ve açıklama yazın ve ardından **İleri: Dizin + etki alanı'na** tıklayın.
6. **Dizin + etki alanı ekle'ye** tıklayın.
7. Bağlanmak istediğiniz kuruluşun etki alanını yazın ve **Ekle'ye** tıklayın.
8. **Bağlan'a** ve ardından **İleri: Sponsorlar'a** tıklayın.
9. Kuruluşunuzdan veya bağlandığınız kuruluştan, konuklar için erişimi onaylamak istediğiniz kişileri ekleyin.
10. **İleri: Gözden Geçir + Oluştur'a** tıklayın.
11. Seçtiğiniz ayarları gözden geçirin ve **Oluştur'a** tıklayın.

    ![Azure Active Directory'de bağlı kuruluşlar sayfasının ekran görüntüsü.](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a>Paylaşacak kaynakları seçme

İş ortağı kuruluşla paylaşacak kaynakları seçmenin ilk adımı, bunları içerecek bir katalog oluşturmaktır.

Katalog oluşturmak için
1. [Azure Active Directory'de](https://aad.portal.azure.com) **Kimlik İdaresi'ne** tıklayın.
2. **Kataloglar'a** tıklayın.
3. **Yeni katalog'a** tıklayın.
4. Katalog için bir ad ve açıklama yazın ve **dış kullanıcılar için** **Etkin** ve Etkin'in her ikisinin de **Evet** olarak ayarlandığından emin olun.
5. **Oluştur'a** tıklayın.

   ![Azure Active Directory Kimlik İdaresi'ndeki kataloglar sayfasının ekran görüntüsü.](../media/identity-governance-catalogs.png)

Katalog oluşturulduktan sonra, iş ortağı kuruluşla paylaşmak istediğiniz SharePoint sitesini veya ekibi eklersiniz.

Bir kataloğa kaynak eklemek için
1. Azure AD Kimlik İdaresi'nde **Kataloglar'a** tıklayın ve sonra da kaynak eklemek istediğiniz kataloğa tıklayın.
2. **Kaynaklar'a** ve ardından **Kaynak ekle'ye** tıklayın.
3. Extranetinize eklemek istediğiniz ekipleri veya SharePoint sitelerini seçin ve **ekle'ye** tıklayın.

   ![Azure Active Directory Kimlik İdaresi'ndeki katalog kaynakları sayfasının ekran görüntüsü.](../media/identity-governance-catalog-resource.png)

Paylaşmak istediğiniz kaynakları tanımladıktan sonra, bir sonraki adım, iş ortağı kullanıcılarına verilen erişim türünü ve erişim isteyen yeni iş ortağı kullanıcıları için onay işlemini tanımlayan bir erişim paketi oluşturmaktır.

Erişim paketi oluşturmak için
1. Azure AD Kimlik İdaresi'nde **Kataloglar'a** tıklayın ve ardından erişim paketi oluşturmak istediğiniz kataloğa tıklayın.
2. **Paketlere eriş'e** ve ardından **Yeni erişim paketi'ne** tıklayın.
3. Erişim paketi için bir ad ve açıklama yazın ve **ardından İleri: Kaynak rolleri'ne** tıklayın.
4. Extranet'iniz için kullanmak istediğiniz kaynakları katalogdan seçin.
5. Her kaynak için **Rol** sütununda, extranet kullanan konuklara vermek istediğiniz kullanıcı rolünü seçin.
6. **İleri: İstekler'e** tıklayın.
7. **Erişim isteyebilecek kullanıcılar'ın** altında **Dizininizde bulunmayan kullanıcılar için'i** seçin.
8. **Belirli bağlı kuruluşlar** seçeneğinin belirlendiğinden emin olun ve ardından **Dizin ekle'ye** tıklayın.
9. Daha önce eklediğiniz bağlı kuruluşu seçin ve ardından **Seç'e** tıklayın
10. **Onay'ın** altında **Onay gerektir** için **Evet'i** seçin.
11. **İlk onaylayan'ın** altında, daha önce eklediğiniz sponsorlardan birini seçin veya belirli bir kullanıcıyı seçin.
12. **Geri dönüş ekle'ye** tıklayın ve bir geri dönüş onaylayıcısı seçin.
13. **Etkinleştir'in** altında **Evet'i** seçin.
14. **İleri: Yaşam Döngüsü'ne** tıklayın.
15. Kullanmak istediğiniz süre sonu ve erişim gözden geçirme ayarlarını seçin ve ardından **İleri: Gözden Geçir + Oluştur'a** tıklayın.
16. Ayarlarınızı gözden geçirin ve **oluştur'a** tıklayın.

    ![Azure Active Directory Kimlik İdaresi'ndeki erişim paketleri ekranının ekran görüntüsü.](../media/identity-governance-access-packages.png)

Büyük bir kuruluşla iş ortaklığı ediyorsanız erişim paketini gizlemek isteyebilirsiniz. Paket gizliyse, iş ortağı kuruluştaki kullanıcılar *paketi Kendi Erişimim* portalında görmez. Bunun yerine, pakete kaydolmaları için doğrudan bir bağlantı gönderilmelidir. Erişim paketinin gizlenmesi, uygunsuz erişim isteklerinin sayısını azaltabilir ve kullanılabilir erişim paketlerinin iş ortağı kuruluşun portalında düzenli tutulmasına da yardımcı olabilir.

Erişim paketini gizli olarak ayarlamak için
1. Azure AD Kimlik İdaresi'nde **, Erişim paketleri'ne** ve ardından erişim paketinize tıklayın.
2. **Genel Bakış** sayfasında **Düzenle'ye** tıklayın.
3. **Özellikler'in** altında **Gizli** için **Evet'i** seçin ve **kaydet'e** tıklayın.

   ![Erişim paketi özelliklerini düzenle ekranının ekran görüntüsü.](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a>İş ortağı kullanıcılarını davet etme

Erişim paketini gizli olarak ayarlarsanız, sitenize veya ekibinize erişim isteğinde bulunabilmesi için iş ortağı kuruluşuna doğrudan bağlantı göndermeniz gerekir.

Erişim portalı bağlantısını bulmak için
1. Azure AD Kimlik İdaresi'nde **, Erişim paketleri'ne** ve ardından erişim paketinize tıklayın.
2. **Genel Bakış** sayfasında, **Erişimim portalı** bağlantısı için **Panoya kopyala** bağlantısına tıklayın.

   ![Erişim portalı bağlantısına sahip erişim paketi özelliklerinin ekran görüntüsü.](../media/identity-governance-access-portal-link.png)

Bağlantıyı kopyaladıktan sonra, iş ortağı kuruluşundaki kişinizle paylaşabilirsiniz ve bu kişiler bu bağlantıyı işbirliği ekibindeki kullanıcılara gönderebilir.

## <a name="see-also"></a>Ayrıca Bkz

[Güvenli bir konuk paylaşım ortamı oluşturma](create-secure-guest-sharing-environment.md)