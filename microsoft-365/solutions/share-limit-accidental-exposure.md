---
title: Kazara maruz kalmayı sınırlayın
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
ms.custom: admindeeplinkSPO
ms.localizationpriority: high
f1.keywords: NOCSH
recommendations: false
description: Kuruluşunuz dışındaki kişilerle dosya paylaşırken bilgilerin yanlışlıkla açığa çıkmalarını nasıl sınırlayacağınızı öğrenin.
ms.openlocfilehash: 66d55a59175b812d305ab3e1c4868f7be689cbaa
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67586104"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a>Kuruluşunuzun dışındaki kişilerle paylaşım yaparken dosyaların yanlışlıkla açığa çıkmalarını sınırlayın

Kuruluşunuz dışındaki kişilerle dosya ve klasör paylaşırken, hassas bilgilerin yanlışlıkla paylaşılması olasılığını azaltmak için çeşitli seçenekler vardır. Kuruluşunuzun gereksinimlerini en iyi şekilde karşılamak için bu makaledeki seçenekler arasından seçim yapabilirsiniz.

## <a name="use-best-practices-for-anyone-links"></a>Herkes bağlantıları için en iyi yöntemleri kullanma

Kuruluşunuzdaki kişilerin kimliği doğrulanmamış paylaşım yapması gerekiyorsa ancak kimliği doğrulanmamış kişilerin içeriği değiştirmesinden endişe duyuyorsanız, kuruluşunuzda [kimliği doğrulanmamış paylaşımla çalışma yönergeleri için Doğrulanmamış paylaşım için en iyi yöntemler](best-practices-anonymous-sharing.md) makalesini okuyun.

## <a name="turn-off-anyone-links"></a>Herkes bağlantılarını kapatma

Paylaşmanın en kolay yolu olduğundan ve kullanıcıların BT departmanınızın denetimi dışında kalan diğer çözümleri arama riskini azaltmaya yardımcı olabileceğinden uygun içerik için *Herkes* bağlantılarının etkin kalmasını öneririz. *Herhangi bir* bağlantı başkalarına iletilebilir, ancak dosya erişimi yalnızca bağlantıya sahip olanlar tarafından kullanılabilir.

Kuruluşunuz dışındaki kişilerin SharePoint, Gruplar veya Teams'deki içeriğe erişirken her zaman kimlik doğrulamasını istiyorsanız *, Herkes* paylaşım özelliğini kapatabilirsiniz. Bu, kullanıcıların kimliği doğrulanmamış içerik paylaşımını engeller.

*Herkes* bağlantılarını devre dışı bırakırsanız, kullanıcılar *Belirli kişiler* bağlantılarını kullanarak konuklarla kolayca paylaşımda bulunabilir. Bu durumda, kuruluşunuzun dışındaki tüm kişilerin paylaşılan içeriğe erişebilmeleri için kimlik doğrulamasından geçmesi gerekir.

gereksinimlerinize bağlı olarak, belirli siteler veya tüm kuruluşunuz için *Herkes* bağlantılarını devre dışı bırakabilirsiniz.

Kuruluşunuz için *Herkes* bağlantılarını kapatmak için

1. SharePoint yönetim merkezinde, sol gezinti bölmesinde <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Paylaşım'ı**</a> seçin.
2. SharePoint dış paylaşım ayarlarını **Yeni ve mevcut konuklar** olarak ayarlayın.

   ![Kuruluş düzeyinde SharePoint sitesi dış paylaşım ayarlarının ekran görüntüsü.](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. **Kaydet**'e tıklayın.

Sitenin *Herkes* bağlantılarını kapatmak için

1. SharePoint yönetim merkezinde, sol gezinti bölmesinde **Siteler'i** genişletin ve <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Etkin siteler'i**</a> seçin.
2. Yapılandırmak istediğiniz siteyi seçin.
3. Şeritte **Paylaşım'ı** seçin.
4. Paylaşımın **Yeni ve mevcut konuklar** olarak ayarlandığından emin olun.

   ![Site düzeyinde SharePoint sitesi dış paylaşım ayarlarının ekran görüntüsü.](../media/sharepoint-site-external-sharing-settings.png)

5. Değişiklik yaptıysanız **Kaydet'i** seçin.

## <a name="domain-filtering"></a>Etki alanı filtreleme

Kullanıcılarınızın kuruluşunuz dışındaki kişilerle paylaşım yaparken hangi etki alanlarını kullanabileceğini belirtmek için etki alanına izin verme veya reddetme listelerini kullanabilirsiniz.

İzin verme listesiyle, kuruluşunuzdaki kullanıcıların kuruluşunuz dışındaki kişilerle paylaşabileceği etki alanlarının listesini belirtebilirsiniz. Diğer etki alanlarıyla paylaşım engellenir. Kuruluşunuz yalnızca belirli etki alanları listesinden kişilerle işbirliğiiyorsa, diğer etki alanlarıyla paylaşımı önlemek için bu özelliği kullanabilirsiniz.

Reddetme listesiyle, kuruluşunuzdaki kullanıcıların kuruluşunuz dışındaki kişilerle paylaşamayacağı etki alanlarının listesini belirtebilirsiniz. Listelenen etki alanlarıyla paylaşım engellenir. Örneğin kuruluşunuzdaki içeriğe erişmesini engellemek istediğiniz rakipleriniz varsa bu yararlı olabilir.

İzin ver ve reddet listeleri yalnızca konuklarla paylaşımı etkiler. Kullanıcılar, devre dışı bırakmıyorsanız *Herkes* bağlantılarını kullanarak yasaklanmış etki alanlarından kişilerle paylaşmaya devam edebilir. Etki alanı izin verme ve reddetme listeleriyle ilgili en iyi sonuçları elde etmek için yukarıda açıklandığı gibi *Herkes* bağlantılarını devre dışı bırakmayı göz önünde bulundurun.

Etki alanı izin verme veya reddetme listesi ayarlamak için

1. SharePoint yönetim merkezinde, sol gezinti bölmesinde <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Paylaşım'ı** seçin</a>
2. **Dış paylaşım için gelişmiş ayarlar'ın** altında **Dış paylaşımı etki alanına göre sınırla** onay kutusunu seçin.
3. **Etki alanı ekle'ye** tıklayın.
4. Etki alanlarını engellemek isteyip istemediğinizi seçin, etki alanlarını yazın ve **Tamam'a** tıklayın.

   ![SharePoint dış paylaşımı etki alanına göre sınırla ayarının ekran görüntüsü.](../media/sharepoint-sharing-block-domain.png)

5. **Kaydet**'e tıklayın.

Etki alanına göre paylaşımı SharePoint ve OneDrive'dan daha yüksek bir düzeyde sınırlamak istiyorsanız, Azure Active Directory'deki [belirli kuruluşların B2B kullanıcılarına yönelik davetlere izin verebilir veya bunları engelleyebilirsiniz](/azure/active-directory/b2b/allow-deny-list) . (Bu ayarların [SharePoint ve OneDrive'ı etkilemesi için SharePoint ve OneDrive tümleştirmesini Azure AD B2B Preview ile](/sharepoint/sharepoint-azureb2b-integration-preview) yapılandırmanız gerekir.)

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a>Dosya, klasör ve site paylaşımını kuruluşunuzun dışındaki kişilerle belirtilen güvenlik gruplarıyla sınırlayın

Dosya, klasör ve site paylaşımını kuruluşunuzun dışındaki kişilerle belirli bir güvenlik grubunun üyeleriyle kısıtlayabilirsiniz. Dış paylaşımı etkinleştirmek istiyorsanız ancak onay iş akışı veya istek işlemiyle bu yararlı olur. Alternatif olarak, kullanıcılarınızın güvenlik grubuna eklenmeden ve dışarıdan paylaşmalarına izin verilmeden önce bir eğitim kursu tamamlamalarını isteyebilirsiniz.

Dış paylaşımı bir güvenlik grubunun üyeleriyle sınırlamak için

1. SharePoint yönetim merkezinde, sol gezinti bölmesinde, **İlkeler'in** altında <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Paylaşım'ı**</a> seçin.
2. **Dış paylaşım'ın** altında **Diğer dış paylaşım ayarları'nı** genişletin.

3. **Yalnızca belirli güvenlik gruplarındaki kullanıcıların dış paylaşımlarına izin ver'i** ve ardından **Güvenlik gruplarını yönet'i** seçin.

    ![Güvenlik gruplarını yönet panelinin ekran görüntüsü.](/sharepoint/sharepointonline/media/manage-security-groups.png)

4. **Güvenlik grubu ekle kutusuna güvenlik grubu** için bir ad girin. Güvenlik grubu kutusu görüntülenir.

5. Güvenlik grubu adının yanındaki **Şununla paylaşabilir** açılan listesinden birini seçin:

    - **Yalnızca kimliği doğrulanmış konuklar** (varsayılan)
    - **Kimse**

6. **Kaydet**'i seçin.

Bunun dosyaları, klasörleri ve siteleri etkilediğini ancak Microsoft 365 gruplarını veya Teams'i etkilemediğini unutmayın. Üyeler özel bir Microsoft 365 grubuna veya Microsoft Teams'deki özel bir ekise konuk davet ettiğinde, davet onay için grup veya ekip sahibine gönderilir.

## <a name="see-also"></a>Ayrıca Bkz

[Güvenli bir konuk paylaşım ortamı oluşturma](create-secure-guest-sharing-environment.md)

[Anonim kullanıcılarla dosya ve klasör paylaşmaya yönelik en iyi yöntemler](best-practices-anonymous-sharing.md)
