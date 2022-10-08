---
title: Microsoft 365'te paylaşımı sınırlama
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
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom:
- admindeeplinkMAC
- admindeeplinkTEAMS
- admindeeplinkSPO
ms.localizationpriority: high
recommendations: false
description: Microsoft 365'te paylaşımı sınırlama veya devre dışı bırakma seçenekleri hakkında bilgi edinin.
ms.openlocfilehash: f9833e1c033644e117a4009720a627d783e4e946
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985619"
---
# <a name="limit-sharing-in-microsoft-365"></a>Microsoft 365'te paylaşımı sınırlama

şirket içi paylaşımı tamamen devre dışı bırakamaz veya sitelerden Paylaş düğmesini kaldıramazsınız ancak microsoft 365'te kuruluşunuzun gereksinimlerini karşılamak için paylaşımı sınırlandırmanın çeşitli yolları vardır.

Dosya paylaşma yöntemleri aşağıdaki tabloda listelenmiştir. Ayrıntılı bilgi için **Paylaşım yöntemi** sütunundaki bağlantıya tıklayın.

|Sharing yöntemi|Açıklama|Sınırlama seçenekleri|
|:-------------|:----------|:-------------|
|[Microsoft 365 grubu veya ekibi](#microsoft-365-group-or-team)|Microsoft Teams ekibine veya Microsoft 365 grubuna erişim verilen Kişiler, ilişkili SharePoint sitesindeki dosyalara düzenleme erişimine sahiptir.|Grup veya ekip özelse, ekibe katılma davetlerini paylaşma onayı için sahibine gider. Yöneticiler konuk erişimini devre dışı bırakabilir veya kuruluş dışındaki kişilerin erişimini engellemek için duyarlılık etiketlerini kullanabilir.|
|[SharePoint sitesi](#sharepoint-site)|Kişiler SharePoint sitesine Sahip, Üye veya Ziyaretçi erişimi verilebilir ve sitedeki dosyalara bu düzeyde erişim sağlanacaktır.|Site izinleri, yalnızca site sahiplerinin siteyi paylaşabilmesi için kısıtlanabilir. Yöneticiler bir siteyi salt okunur olarak ayarlayabilir veya erişimi tamamen engelleyebilir.|
|[Belirli kişilerle paylaşma](#sharing-with-specific-people)|Site üyeleri ve düzenleme izinleri olan kişiler dosya ve klasörlere doğrudan izin verebilir veya *Belirli kişiler* bağlantılarını kullanarak bunları paylaşabilir.|Yalnızca site sahiplerinin dosya ve klasörleri paylaşabilmesi için site izinleri kısıtlanabilir. Bu durumda, site üyeleri tarafından doğrudan erişim ve *Belirli kişiler* bağlantı paylaşımı, onay için site sahibine gider.|
|[SharePoint ve OneDrive konuk paylaşımı](#sharepoint-guest-sharing)|SharePoint sitesi sahipleri ve üyeleri ile OneDrive sahipleri, kuruluş dışındaki kişilerle dosya ve klasör paylaşabilir.|Konuk paylaşımı kuruluşun tamamı veya tek tek siteler için devre dışı bırakılabilir.|
|[*Kuruluşunuzda bağlantıları* paylaşan Kişiler](#people-in-your-organization-sharing-links)|SharePoint site sahipleri ve üyeleri *, kuruluş bağlantılarınızdaki Kişiler* kullanarak dosyaları paylaşabilir ve bu da kuruluş içindeki herkes için kullanılabilir.|*Kuruluşunuzdaki Kişiler* bağlantıları site düzeyinde devre dışı bırakılabilir.|
|[Site, grup ve ekip oluşturma](#create-sites-groups-and-teams)|Varsayılan olarak, kullanıcılar içerik paylaşabilecekleri yeni siteler, gruplar ve ekipler oluşturabilir.|Yöneticiler kimlerin site, grup ve ekip oluşturabileceğini kısıtlayabilir.|
|[E-posta](#email)|Bir dosyaya erişimi olan Kişiler dosyayı e-posta yoluyla başkalarına gönderebilir.|Yöneticiler, yetkisiz kişilerle paylaşılmasını önlemek için duyarlılık etiketlerini kullanarak dosyaları şifreleyebilir.|
|[İndirme veya dosya kopyalama](#download-or-file-copy)|Bir dosyaya erişimi olan Kişiler dosyayı indirebilir veya kopyalayabilir ve Microsoft 365 kapsamı dışında başkalarıyla paylaşabilir.|Yöneticiler, yetkisiz kişilerle paylaşılmasını önlemek için duyarlılık etiketlerini kullanarak dosyaları şifreleyebilir.|

Ayrıca, kişilerin paylaşılan içeriğe erişme koşullarını da kısıtlayabilirsiniz. Daha fazla bilgi için bu makalenin devamında [yer alan koşullu erişim](#conditional-access) bölümüne bakın.

Kuruluşunuzda paylaşımı sınırlamak için bu makalede açıklanan yönetici denetimlerini kullanabilirsiniz ancak güvenli bir paylaşım ortamı oluşturmak için Microsoft 365'teki güvenlik ve uyumluluk özelliklerini kullanmayı kesinlikle göz önünde bulundurmanızı öneririz. Bilgi için bkz. [Microsoft 365 ile SharePoint'te dosya işbirliği](/sharepoint/deploy-file-collaboration) ve [Güvenlik yalıtımıyla ekip yapılandırma](secure-teams-security-isolation.md) .

Paylaşımın kuruluşunuzda nasıl kullanıldığını anlamak için [dosya ve klasör paylaşımıyla ilgili bir rapor çalıştırın](/sharepoint/sharing-reports).

## <a name="microsoft-365-group-or-team"></a>Microsoft 365 grubu veya ekibi

Microsoft 365 grubunda veya Microsoft Teams ekibinde paylaşımı sınırlamak istiyorsanız, grubu veya ekibi özel hale getirmek önemlidir. Kuruluşunuzun içindeki Kişiler istediğiniz zaman genel bir gruba veya ekibe katılabilir. Grup veya ekip özel olmadığı sürece, ekibin veya kuruluş içindeki dosyalarının paylaşımını sınırlamanın hiçbir yolu yoktur.

### <a name="guest-sharing"></a>Konuk paylaşımı

Teams'te konuk erişimini engellemek istiyorsanız, Teams yönetim merkezinde konuk paylaşımını kapatabilirsiniz.

Teams'de konuk paylaşımını kapatmak için
1. Teams yönetim merkezinde **Kuruluş genelinde ayarlar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**Konuk erişimi** sekmesini</a> genişletin.
2. **Teams'de konuk erişimine izin ver'i** kapatın.
3. **Kaydet**'e tıklayın.

Microsoft 365 Grupları konuk erişimini engellemek istiyorsanız, Microsoft 365 yönetim merkezi grup konuk erişim ayarlarını kapatabilirsiniz.

Microsoft 365 Grupları'da konuk paylaşımını kapatmak için
1. Microsoft 365 yönetim merkezi **Ayarlar** > **Kuruluş Ayarları** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Hizmetleri** sekmesine</a> tıklayın.
2. **Microsoft 365 Grupları'a** tıklayın.
3. **Kuruluşunuzun dışındaki grup üyelerinin grup içeriğine erişmesine izin ver** ve **Grup sahiplerinin kuruluşunuz dışındaki kişileri gruplara eklemesine izin ver** onay kutularını temizleyin.
4. **Değişiklikleri kaydet**’e tıklayın.

    ![Microsoft 365 yönetim merkezi Microsoft 365 Grupları paylaşım ayarlarının ekran görüntüsü.](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> Belirli bir grup veya ekip için konuk paylaşımını engellemek istiyorsanız, [Microsoft PowerShell](per-group-guest-access.md) veya [duyarlılık etiketlerini](../compliance/sensitivity-labels-teams-groups-sites.md) kullanarak bunu yapabilirsiniz.

Azure Active Directory'de etki alanlarına izin vererek veya engelleyerek konuk paylaşımını belirli etki alanlarındaki kullanıcılarla sınırlayabilirsiniz. Azure AD [B2B ile SharePoint ve OneDrive tümleştirmesini etkinleştirdiyseniz, bu durum SharePoint'te](/sharepoint/sharepoint-azureb2b-integration-preview) konuk paylaşımını da etkiler.

Yalnızca belirtilen etki alanlarından davet paylaşımına izin vermek için
1. Azure Active Directory'de Genel Bakış sayfasında **Kuruluş ilişkileri'ne** tıklayın.
2. **Ayarlar'a** tıklayın.
3. **İşbirliği kısıtlamaları'nın** altında **Belirtilen etki alanlarına davetleri reddet'i veya Yalnızca belirtilen etki alanlarına** **davetlere izin ver'i** seçin ve kullanmak istediğiniz etki alanlarını yazın.
4. **Kaydet**'e tıklayın.

    ![Azure Active Directory'deki işbirliği kısıtlamaları ayarlarının ekran görüntüsü.](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a>SharePoint sitesi

SharePoint site paylaşımını yalnızca site sahiplerine sınırlayabilirsiniz. Bu, site üyelerinin siteyi paylaşmasını engeller. Site bir Microsoft 365 grubuna bağlıysa, grup üyelerinin başkalarını gruba davetebileceğini ve bu kullanıcıların site erişimine sahip olacağını unutmayın.

Site paylaşımını sahiplere sınırlamak için
1. Sitede dişli simgesine ve ardından **Site izinleri'ne** tıklayın.
2. **Paylaşım ayarları'nın** altında **Paylaşım ayarlarını değiştir'e** tıklayın.
3. **Site sahipleri ve üyeleri'ni seçtiğinizde Düzenleme izinlerine sahip kişiler dosya ve klasörleri paylaşabilir, ancak siteyi yalnızca site sahipleri paylaşabilir**.
4. **Kaydet**'e tıklayın.

    ![SharePoint sitesindeki paylaşım izinleri ayarlarının ekran görüntüsü.](../media/sharepoint-site-sharing-permissions-level-two.png)

Erişim isteklerini kapatarak sitenin üyesi olmayan kullanıcıların erişim istemesini engelleyebilirsiniz.

Erişim isteklerini kapatmak için
1. Sitede dişli simgesine ve ardından **Site izinleri'ne** tıklayın.
2. **Paylaşım ayarları'nın** altında **Paylaşım ayarlarını değiştir'e** tıklayın.
3. **Erişim isteklerine izin ver'i** kapatın ve **kaydet'e** tıklayın.

Site için etki alanlarına izin vererek veya engelleyerek site paylaşımını belirli etki alanlarıyla sınırlayabilirsiniz.

Site paylaşımını etki alanına göre sınırlamak için

1. SharePoint yönetim merkezindeki **Siteler'in** altında <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Etkin siteler'i**</a> seçin.
2. Yapılandırmak istediğiniz siteyi seçin.
3. **İlkeler** sekmesindeki **Dış paylaşım'ın** altında **Düzenle'yi** seçin.
4. **Dış paylaşım için gelişmiş ayarlar'ın** altında Etki **alanına göre paylaşımı sınırla'yı** seçin.
5. İzin vermek veya engellemek istediğiniz etki alanlarını ekleyin ve **kaydet'i** seçin.
6. **Kaydet**'i seçin.

    ![İzin verilen etki alanları site düzeyi ayarının ekran görüntüsü.](../media/limit-site-sharing-by-domain.png)

### <a name="block-access-to-a-site"></a>Siteye erişimi engelleme

Sitenin kilit durumunu değiştirerek siteye erişimi engelleyebilir veya siteyi salt okunur yapabilirsiniz. Ayrıntılar için bkz. [Siteleri kilitleme ve kilidini açma](/sharepoint/manage-lock-status).

### <a name="permissions-inheritance"></a>İzin devralma

Önerilmiyor olsa da, [sitelere ve alt sitelere erişim düzeylerini özelleştirmek için SharePoint izin devralmayı](/sharepoint/what-is-permissions-inheritance) kullanabilirsiniz.

## <a name="sharing-with-specific-people"></a>Belirli kişilerle paylaşma

Bir sitenin veya içeriğinin paylaşımını sınırlamak istiyorsanız, siteyi yalnızca site sahiplerinin dosya, klasör ve siteyi paylaşmasına izin verecek şekilde yapılandırabilirsiniz. Bu yapılandırıldığında, site üyelerinin *Belirli kişiler* bağlantılarını kullanarak dosya veya klasör paylaşma girişimleri onay için site sahibine gider.

Site, dosya ve klasör paylaşımını sahiplere sınırlamak için
1. Sitede dişli simgesine ve ardından **Site izinleri'ne** tıklayın.
2. **Paylaşım ayarları'nın** altında **Paylaşım ayarlarını değiştir'e** tıklayın.
3. **Yalnızca site sahipleri dosyaları, klasörleri ve siteyi paylaşabilir'i** seçin.
4. **Kaydet**'e tıklayın.

    ![SharePoint sitesinde yalnızca sahiplere ayarlanmış paylaşım izinleri ayarlarının ekran görüntüsü.](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a>SharePoint konuk paylaşımı

SharePoint veya OneDrive dosya ve klasörlerinin kuruluşunuzun dışındaki kişilerle paylaşılmasını önlemek istiyorsanız, tüm kuruluş veya tek bir site için konuk paylaşımını kapatabilirsiniz.

Kuruluşunuzda SharePoint konuk paylaşımını kapatmak için

1. SharePoint yönetim merkezinde, **İlkeler'in** altında <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Paylaşım'ı**</a> seçin.
2. **Dış paylaşım'ın** altında SharePoint kaydırıcısını **Yalnızca kuruluşunuzdaki kişiler'e** sürükleyin.
3. **Kaydet**'i seçin.

    ![Herkes olarak ayarlanan SharePoint kuruluş düzeyinde paylaşım ayarlarının ekran görüntüsü.](../media/sharepoint-tenant-sharing-off.png)


Site için konuk paylaşımını kapatmak için
1. SharePoint yönetim merkezindeki **Siteler'in** altında <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Etkin siteler'i**</a> seçin.
2. Yapılandırmak istediğiniz siteyi seçin.
3. **İlkeler** sekmesindeki **Dış paylaşım'ın** altında **Düzenle'yi** seçin.
4. **Dış paylaşım'ın** **altında Yalnızca kuruluşunuzdaki kişiler'i ve ardından Kaydet'i** seçin.

    ![SharePoint site düzeyinde paylaşım ayarlarının Yalnızca kuruluşunuzdaki kişiler olarak ayarlandığının ekran görüntüsü.](../media/sharepoint-site-external-sharing-settings-off.png)

Microsoft 365 yönetim merkezi kullanıcıya tıklayıp OneDrive sekmesinde **Dış paylaşımı yönet'i** seçerek tek bir **OneDrive** için konuk paylaşımını kapatabilirsiniz.

Kuruluşunuzun dışındaki kişilerle paylaşıma izin vermek istiyorsanız ancak herkesin kimlik doğrulamasından emin olmak istiyorsanız, kuruluşun tamamı veya tek bir site için *Herkes* (anonim paylaşım) bağlantılarını devre dışı bırakabilirsiniz.

Kuruluş *düzeyindeki Herkes* bağlantılarını kapatmak için

1. SharePoint yönetim merkezinde, **İlkeler'in** altında <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Paylaşım'ı**</a> seçin.
2. **Dış paylaşım'ın** altında SharePoint kaydırıcısını **Yeni ve mevcut konuklar'a** sürükleyin.
3. **Kaydet**'i seçin.

    ![Yeni ve mevcut konuklar olarak ayarlanan SharePoint kuruluş düzeyinde paylaşım ayarlarının ekran görüntüsü.](../media/sharepoint-guest-sharing-new-existing-guests.png)

Sitenin *Herkes* bağlantılarını kapatmak için

1. SharePoint yönetim merkezindeki **Siteler'in** altında <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Etkin siteler'i**</a> seçin.
2. Yapılandırmak istediğiniz siteyi seçin.
3. **İlkeler** sekmesindeki **Dış paylaşım'ın** altında **Düzenle'yi** seçin.
4. **Dış paylaşım'ın** altında **Yeni ve mevcut konuklar'ı** ve ardından **Kaydet'i** seçin.

    ![SharePoint site düzeyinde paylaşım ayarlarının Yeni ve mevcut ayarlar olarak ayarlandığı ekran görüntüsü.](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a>*Kuruluşunuzda bağlantıları* paylaşan Kişiler

Varsayılan olarak, bir sitenin üyeleri kuruluşunuzdaki bir *Kişiler* kullanarak kuruluşunuzdaki diğer kişilerle dosya ve klasör paylaşabilir. PowerShell kullanarak *kuruluşunuzun bağlantılarındaki Kişiler* devre dışı bırakabilirsiniz:

```powershell
Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks Disabled
```

Örneğin:

```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks Disabled
```

## <a name="create-sites-groups-and-teams"></a>Site, grup ve ekip oluşturma

Varsayılan olarak, kullanıcılar içerik paylaşabilecekleri yeni siteler, gruplar ve ekipler oluşturabilir (paylaşım ayarlarınıza bağlı olarak). Kimlerin site, grup ve ekip oluşturabileceğini kısıtlayabilirsiniz. Aşağıdaki başvurulara bakın:

- [SharePoint'te site oluşturmayı yönetme](/sharepoint/manage-site-creation)
- [Kimlerin Microsoft 365 Grupları oluşturabileceğini yönetme](./manage-creation-of-groups.md)

> [!NOTE]
> Grup oluşturmayı kısıtlamak, ekip oluşturmayı kısıtlar.

## <a name="email"></a>E-posta

Şifreleme kullanarak e-postaların istenmeyen paylaşımını önleyebilirsiniz. Bu, e-postaların yetkisiz kullanıcılarla iletilmesini veya başka bir şekilde paylaşılmasını önler. Email şifreleme duyarlılık etiketleri kullanılarak etkinleştirilebilir. Ayrıntılar için bkz. [Duyarlılık etiketlerinde şifreleme kullanarak içeriğe erişimi kısıtlama](../compliance/encryption-sensitivity-labels.md) .

## <a name="download-or-file-copy"></a>İndirme veya dosya kopyalama

Microsoft 365'teki dosya ve klasörlere erişimi olan kullanıcılar dosyaları indirebilir ve dış medyaya kopyalayabilir. İstenmeyen dosya paylaşımı riskini azaltmak için duyarlılık etiketlerini kullanarak içeriği şifreleyebilirsiniz.

## <a name="conditional-access"></a>Koşullu erişim

Azure Active Directory koşullu erişimi, ağ konumu, cihaz durumu, oturum açma riski ve diğer faktörlere bağlı olarak kişilerle paylaşımı sınırlamaya veya engellemeye yönelik seçenekler sağlar. Bkz. [Koşullu Erişim nedir?](/azure/active-directory/conditional-access/overview).

SharePoint, yönetilmeyen cihazlar ve ağ konumu için Azure AD koşullu erişim ile doğrudan tümleştirme sağlar. Ayrıntılar için aşağıdaki başvurulara bakın:

- [Yönetilmeyen cihazlardan erişimi denetleme](/sharepoint/control-access-from-unmanaged-devices)
- [Ağ konumuna göre SharePoint ve OneDrive verilerine erişimi denetleme](/sharepoint/control-access-based-on-network-location)

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 365 konuk paylaşımı ayarları başvurusu](microsoft-365-guest-settings.md)
