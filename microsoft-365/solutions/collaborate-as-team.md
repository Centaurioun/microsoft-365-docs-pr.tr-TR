---
title: Ekipteki konuklarla işbirliği yapma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- highpri
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkTEAMS
- admindeeplinkSPO
ms.localizationpriority: high
f1.keywords: NOCSH
recommendations: false
description: Teams'de konuklarla görev, konuşma ve belge işbirliği için bir ekip ayarlamak için gereken Microsoft 365 yapılandırma adımları hakkında bilgi edinin.
ms.openlocfilehash: 753b02ef45e0937c09c8707913a2074a26750ae6
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67983178"
---
# <a name="collaborate-with-guests-in-a-team"></a>Ekipteki konuklarla işbirliği yapma

Belgeler, görevler ve konuşmalar arasında konuklarla işbirliği yapmanız gerekiyorsa Microsoft Teams'i kullanmanızı öneririz. Teams, kalıcı sohbet ve birleşik bir kullanıcı deneyiminde özelleştirilebilir ve genişletilebilir işbirliği araçları ile Office ve SharePoint'te kullanılabilen tüm işbirliği özelliklerini sağlar.

Bu makalede, konuklarla işbirliği için bir ekip ayarlamak için gereken Microsoft 365 yapılandırma adımlarını inceleyeceğiz. Konuk erişimini yapılandırdıktan sonra, Teams'de bir takıma konuk ekleme sayfasındaki adımları izleyerek [konukları ekiplere](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f) davet edebilirsiniz.

> [!NOTE]
> [Paylaşılan kanallar](collaborate-teams-direct-connect.md) , diğer Microsoft 365 kuruluşlarıyla işbirliği yaparken konuk hesaplarından daha sorunsuz bir deneyim sunar. Paylaşılan kanallar, dış katılımcıların kuruluşunuzda oturum açmasına gerek kalmadan Teams kanallarını kullanarak kuruluşunuzun dışındaki kişilerle işbirliği yapmanıza olanak tanır. Paylaşılan kanalların belirli bir senaryo için konuklarla işbirliği yapmaya kıyasla daha iyi bir seçenek olup olmadığını görmek için [Dış işbirliği planlayın'ı](plan-external-collaboration.md) gözden geçirmenizi öneririz.

## <a name="video-demonstration"></a>Video tanıtımı

Bu videoda, bu belgede açıklanan yapılandırma adımları gösterilmektedir.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Azure Dış işbirliği ayarları

Microsoft 365'te paylaşım, [Azure Active Directory'deki B2B dış işbirliği ayarları](/azure/active-directory/external-identities/delegate-invitations) tarafından en üst düzeyde yönetilir. Konuk paylaşımı Azure AD devre dışı bırakıldıysa veya kısıtlandıysa, bu ayar Microsoft 365'te yapılandırdığınız paylaşım ayarlarını geçersiz kılar.

Konuklarla paylaşımın engellenmediğinden emin olmak için B2B dış işbirliği ayarlarını denetleyin.

![Azure Active Directory Kuruluş İlişkileri Ayarları sayfasının ekran görüntüsü.](../media/azure-ad-organizational-relationships-settings.png)

Dış işbirliği ayarlarını ayarlamak için

1. adresinden Azure Active Directory'de [https://aad.portal.azure.com](https://aad.portal.azure.com)oturum açın.
2. Sol gezinti bölmesinde **Azure Active Directory'ye** tıklayın.
3. **Dış kimlikler'e** tıklayın.
4. **Başlarken** ekranında, sol gezinti bölmesinde **Dış işbirliği ayarları'na** tıklayın.
5. **Üye kullanıcıların ve belirli yönetici rollerine atanan kullanıcıların, üye izinlerine sahip konuklar dahil konuk kullanıcıları davet etmelerini** sağlayın veya **Kuruluştaki herkes konuk kullanıcıları davet edebilir(konuklar ve yönetici olmayanlar dahil)** seçilidir.
6. Değişiklik yaptıysanız **Kaydet'e** tıklayın.

**İşbirliği kısıtlamaları** bölümündeki ayarları not edin. İşbirliği yapmak istediğiniz konukların etki alanlarının engellenmediğinden emin olun.

Birden çok kuruluşun konuklarıyla çalışıyorsanız, dizin verilerine erişimlerini kısıtlamak isteyebilirsiniz. Bu, dizinde başka kimlerin konuk olduğunu görmelerini engeller. Bunu yapmak için **Konuk kullanıcı erişim kısıtlamaları'nın** altında **Konuk kullanıcılar dizin nesneleri ayarlarının özelliklerine ve üyeliğine sınırlı erişime sahip** veya **Konuk kullanıcı erişimi kendi dizin nesnelerinin özellikleri ve üyelikleriyle sınırlıdır'ı** seçin.

## <a name="teams-guest-access-settings"></a>Teams konuk erişim ayarları

Teams,konuk erişimi için bir ana açma/kapatma anahtarına ve konukların bir ekipte neler yapabileceğini denetlemek için çeşitli ayarlara sahiptir. **Teams'de konuk erişiminin çalışması için Teams'de konuk erişimine izin ver** ana anahtarı **Açık** olmalıdır.

Teams'de konuk erişiminin etkinleştirildiğinden emin olun ve işletme gereksinimlerinize göre konuk ayarlarında herhangi bir ayarlama yapın. Bu ayarların tüm ekipleri etkilediğini unutmayın.

![Teams konuk erişimi iki durumlu düğmesinin ekran görüntüsü.](../media/teams-guest-access-toggle-on.png)

Teams konuk erişim ayarlarını ayarlamak için

1. konumundaki Microsoft 365 yönetim merkezi oturum [https://admin.microsoft.com](https://admin.microsoft.com)açın.
2. Sol gezinti bölmesinde **Tümünü göster'e** tıklayın.
3. **Yönetici merkezleri'nin** altında **Teams'e** tıklayın.
4. Teams yönetim merkezinde, sol gezinti bölmesinde **Kullanıcılar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**Konuk erişimi'ni**</a> seçin.
5. **Teams'de konuk erişimine izin ver seçeneğinin** **Açık** olarak ayarlandığından emin olun.
6. Ek konuk ayarlarında istediğiniz değişiklikleri yapın ve **kaydet'e** tıklayın.

Teams konuk erişimi açıldıktan sonra, duyarlılık etiketlerini kullanarak isteğe bağlı olarak tek tek ekiplere ve ilişkili SharePoint sitelerine konuk erişimini denetleyebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Teams, Microsoft 365 grupları ve SharePoint sitelerindeki içeriği korumak için duyarlılık etiketlerini kullanma](../compliance/sensitivity-labels-teams-groups-sites.md).

> [!NOTE]
> Teams konuk ayarlarını açtıktan sonra etkin hale gelmesi yirmi dört saat kadar sürebilir.

## <a name="microsoft-365-groups-guest-settings"></a>Konuk ayarlarını Microsoft 365 Grupları

Teams, ekip üyeliği için Microsoft 365 Grupları kullanır. Teams'te konuk erişiminin çalışabilmesi için Microsoft 365 Grupları konuk ayarlarının açık olması gerekir.

![Microsoft 365 yönetim merkezi Microsoft 365 Grupları konuk ayarlarının ekran görüntüsü.](../media/office-365-groups-guest-settings.png)

Microsoft 365 Grupları konuk ayarlarını ayarlamak için

1. Microsoft 365 yönetim merkezi, sol gezinti bölmesinde **Ayarlar'ı** genişletin.
2. **Kuruluş ayarları'na** tıklayın.
3. Listede **Microsoft 365 Grupları'e** tıklayın.
4. **Grup sahiplerinin Microsoft 365 Grupları için kuruluşunuz dışındaki kişileri konuk olarak eklemesine izin ver** ve **Konuk grup üyelerinin grup içeriğine erişmesine izin ver** onay kutularının da işaretli olduğundan emin olun.
5. Değişiklik yaptıysanız Değişiklikleri **kaydet'e** tıklayın.


## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint kuruluş düzeyi paylaşım ayarları

Dosyalar, klasörler ve listeler gibi Teams içeriğinin tümü SharePoint'te depolanır. Konukların Teams'de bu öğelere erişebilmesi için SharePoint kuruluş düzeyinde paylaşım ayarlarının konuklarla paylaşıma izin vermesi gerekir.

Kuruluş düzeyindeki ayarlar, ekiplerle ilişkilendirilmiş siteler de dahil olmak üzere tek tek siteler için hangi ayarların kullanılabilir olduğunu belirler. Site ayarları, kuruluş düzeyindeki ayarlardan daha izinli olamaz.

Kimliği doğrulanmamış kişilerle dosya ve klasör paylaşımına izin vermek istiyorsanız **Herkes'i** seçin. Tüm konukların kimlik doğrulaması yapmak zorunda olduğundan emin olmak istiyorsanız **Yeni ve mevcut konuklar'ı** seçin. Kuruluşunuzdaki herhangi bir sitenin ihtiyaç duyduğu en izin veren ayarı seçin.

![SharePoint kuruluş düzeyinde paylaşım ayarlarının ekran görüntüsü.](../media/sharepoint-organization-external-sharing-controls.png)


SharePoint kuruluş düzeyinde paylaşım ayarlarını ayarlamak için

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> sol gezinti bölmesindeki **Yönetici merkezleri'nin** altında **SharePoint'i** seçin.
2. SharePoint yönetim merkezinde, sol gezinti bölmesinde **İlkeler'i** genişletin ve <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**paylaşım'ı**</a> seçin.
3. SharePoint için dış paylaşımın **Herkes** veya **Yeni ve mevcut konuklar olarak ayarlandığından** emin olun.
4. Değişiklik yaptıysanız **Kaydet'i** seçin.


## <a name="sharepoint-organization-level-default-link-settings"></a>SharePoint kuruluş düzeyinde varsayılan bağlantı ayarları

Varsayılan dosya ve klasör bağlantısı ayarları, kullanıcılara bir dosya veya klasör paylaştıklarında varsayılan olarak gösterilecek bağlantı seçeneğini belirler. Kullanıcılar, isterseniz bağlantı türünü paylaşmadan önce diğer seçeneklerden biriyle değiştirebilir.

Bu ayarın kuruluşunuzdaki tüm ekipleri ve SharePoint sitelerini etkilediğini unutmayın.

Kullanıcılar dosya ve klasörleri paylaştığında varsayılan olarak seçilecek aşağıdaki bağlantı türlerinden birini seçin:

- **Bağlantıya sahip herkes** - Dosya ve klasörlerin kimliği doğrulanmamış çok sayıda paylaşımını yapmayı bekliyorsanız bu seçeneği belirtin. *Herkes* bağlantılarına izin vermek istiyorsanız ancak yanlışlıkla kimliği doğrulanmamış paylaşımla ilgileniyorsanız, diğer seçeneklerden birini varsayılan olarak göz önünde bulundurun. Bu bağlantı türü yalnızca **Herkes** paylaşımını etkinleştirdiyseniz kullanılabilir.
- **Yalnızca kuruluşunuzdaki kişiler** - Çoğu dosya ve klasör paylaşımının kuruluşunuzdaki kişilerle olmasını bekliyorsanız bu seçeneği belirleyin.
- **Belirli kişiler** - Konuklarla çok fazla dosya ve klasör paylaşımı yapmayı bekliyorsanız bu seçeneği göz önünde bulundurun. Bu bağlantı türü konuklarla birlikte çalışır ve kimlik doğrulaması yapılmasını gerektirir.
 
![SharePoint kuruluş düzeyinde dosya ve klasör paylaşım ayarlarının ekran görüntüsü.](../media/sharepoint-organization-files-folders-sharing-settings.png)


SharePoint kuruluş düzeyinde varsayılan bağlantı ayarlarını ayarlamak için

1. SharePoint yönetim merkezinde <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Paylaşım'a**</a> gidin.
2. **Dosya ve klasör bağlantıları'nın** altında, kullanmak istediğiniz varsayılan paylaşım bağlantısını seçin.
3. Değişiklik yaptıysanız **Kaydet'i** seçin.

## <a name="create-a-team"></a>Ekip oluşturma

Sonraki adım, konuklarla işbirliği yapmak için kullanmayı planladığınız ekibi oluşturmaktır.

Ekip oluşturmak için
1. Teams'te, **Teams** sekmesinde, sol bölmenin alt kısmındaki **Katıl'a tıklayın veya ekip oluşturun** .
2. **Ekip oluştur'a** tıklayın.
3. **Sıfırdan ekip oluştur'a** tıklayın.
4. **Özel** veya **Genel'i** seçin.
5. Ekip için bir ad ve açıklama yazın ve **Oluştur'a** tıklayın.
6. **Atla'ya** tıklayın.

Kullanıcıları daha sonra davet edeceğiz. Ardından, ekiple ilişkilendirilmiş SharePoint sitesinin site düzeyinde paylaşım ayarlarını denetlemek önemlidir.

## <a name="sharepoint-site-level-sharing-settings"></a>SharePoint site düzeyinde paylaşım ayarları

Bu ekip için istediğiniz erişim türüne izin verdiklerinden emin olmak için site düzeyinde paylaşım ayarlarını denetleyin. Örneğin, kuruluş düzeyi ayarlarını **Herkes** olarak ayarladıysanız ancak tüm konukların bu ekip için kimlik doğrulaması yapmasını istiyorsanız, site düzeyinde paylaşım ayarlarının **Yeni ve mevcut konuklar** olarak ayarlandığından emin olun.

![SharePoint sitesi dış paylaşım ayarlarının ekran görüntüsü.](../media/sharepoint-site-external-sharing-settings.png)

Site düzeyinde paylaşım ayarlarını ayarlamak için
1. SharePoint yönetim merkezinde, sol gezinti bölmesinde **Siteler'i** genişletin ve <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Etkin siteler'i**</a> seçin.
2. Yeni oluşturduğunuz ekip için siteyi seçin.
3. Seçin... ve **Paylaşım'ı** seçin.
4. Paylaşımın **Herkes** veya **Yeni ve mevcut konuklar olarak ayarlandığından** emin olun.
5. Değişiklik yaptıysanız **Kaydet'i** seçin.

## <a name="invite-users"></a>Kullanıcıları davet etme

Artık konuk paylaşım ayarları yapılandırıldığından, ekibinize dahili kullanıcılar ve konuklar eklemeye başlayabilirsiniz. 

Takıma iç kullanıcıları davet etmek için
1. Ekipte **Diğer seçenekler** ()**\*\*\*** öğesine ve ardından **Üye ekle'ye** tıklayın.
2. Davet etmek istediğiniz kişinin adını yazın.
3. **Ekle'ye** ve ardından **Kapat'a** tıklayın.

Bir takıma konuk davet etmek için
1. Ekipte **Diğer seçenekler** ()**\*\*\*** öğesine ve ardından **Üye ekle'ye** tıklayın.
2. Davet etmek istediğiniz konuğun e-posta adresini yazın.
3. **Konuk bilgilerini düzenle'ye** tıklayın.
4. Konuğun tam adını yazın ve onay işaretine tıklayın.
5. **Ekle'ye** ve ardından **Kapat'a** tıklayın.

> [!NOTE]
> İş veya okul hesabı olan konuklar yalnızca Kullanıcı Asıl Adı (UPN) (örneğin, adele@contoso.com) kullanılarak davet edilebilir. EAS Kimliği veya diğer e-posta biçimlerini kullanarak konukları davet etme desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[Kimliği doğrulanmamış kullanıcılarla dosya ve klasör paylaşmaya yönelik en iyi yöntemler](best-practices-anonymous-sharing.md)

[Konuklarla paylaşırken dosyaların yanlışlıkla açığa alınmasını sınırlayın](share-limit-accidental-exposure.md)

[Güvenli bir konuk paylaşım ortamı oluşturma](create-secure-guest-sharing-environment.md)

[Yönetilen konuklarla B2B extranet oluşturma](b2b-extranet.md)

[Azure Active Directory B2B ile SharePoint ve OneDrive tümleştirmesi](/sharepoint/sharepoint-azureb2b-integration-preview)
