---
title: Microsoft 365 grupları adlandırma ilkesi
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: Microsoft 365 grupları için adlandırma ilkesi oluşturmayı öğrenin.
ms.openlocfilehash: 00a1a6cae02b6ddbff784f0151cee4257818841e
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731276"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 grupları adlandırma ilkesi

Kuruluşunuzdaki kullanıcılar tarafından oluşturulan gruplar için tutarlı bir adlandırma stratejisi uygulamak için grup adlandırma ilkesi kullanabilirsiniz. Adlandırma ilkesi sizin ve kullanıcılarınızın grubun, üyeliğin, coğrafi bölgenin veya grubu kimin oluşturduğunu tanımlamanıza yardımcı olabilir. Adlandırma ilkesi, adres defterindeki grupları kategorilere ayırmaya da yardımcı olabilir. Grup adlarında ve diğer adlarında belirli sözcüklerin kullanılmasını engellemek için ilkeyi kullanabilirsiniz.

Adlandırma ilkesi, tüm grup iş yükleri (Outlook, Microsoft Teams, SharePoint, Planner, Yammer vb.) genelinde oluşturulan gruplara uygulanır. Hem grup adına hem de grup diğer adına uygulanır. Ayrıca kullanıcı bir grup oluşturduğunda ve mevcut bir grup için grup adı, diğer ad, açıklama veya avatar düzenlendiğinde de uygulanır.

> [!TIP]
> Microsoft 365 grup adlandırma ilkesi yalnızca Microsoft 365 grupları için geçerlidir. Exchange Online'de oluşturulan dağıtım grupları için geçerli değildir. Dağıtım grupları için adlandırma ilkesi oluşturmak için bkz. [Dağıtım grubu adlandırma ilkesi oluşturma](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

Grup adlandırma ilkesi aşağıdaki özelliklerden oluşur:

- **Ön Ek-Sonek adlandırma ilkesi**: Grupların adlandırma kuralını tanımlamak için ön ekleri veya sonekleri kullanabilirsiniz (örneğin: "ABD\_Grup\_Mühendisliğim"). Ön ekler/sonekler, grubu oluşturan kullanıcıya göre değiştirilecek [Department] gibi sabit dizeler veya kullanıcı öznitelikleri olabilir.

- **Özel Engellenen Sözcükler**: Kuruluşunuza özgü, kullanıcılar tarafından oluşturulan gruplarda engellenecek bir dizi engellenen sözcüğü karşıya yükleyebilirsiniz. (Örneğin: "CEO, Bordro, İk").

## <a name="licensing-requirements"></a>Lisans gereksinimleri

Microsoft 365 Grupları için Azure AD adlandırma ilkesi kullanmak, bir veya daha fazla Microsoft 365 grubunun üyesi olan her benzersiz kullanıcı (konuklar dahil) için bir Azure Active Directory Premium P1 lisansına veya Azure AD Temel EDU lisansına sahip olmanıza gerek yoktur.

Bu, grupları adlandırma ilkesini oluşturan yönetici için de gereklidir.

## <a name="prefix-suffix-naming-policy"></a>adlandırma ilkesini Prefix-Suffix

Ön ekler ve sonekler sabit dizeler veya kullanıcı öznitelikleri olabilir.

### <a name="fixed-strings"></a>Sabit dizeler

Grup iş yüklerinin GAL ve sol gezintisindeki grupları ayırt etmelerine yardımcı olabilecek kısa dizeler kullanabilirsiniz. Yaygın ön eklerden bazıları 'Grp\_Adı' , 'Ad', '\#\_Ad' gibi anahtar sözcüklerdir.

### <a name="attributes"></a>Öznitelik

[Department] gibi grubu kimin oluşturduğunu ve [Ülke] gibi nereden oluşturulduğunu belirlemeye yardımcı olabilecek öznitelikleri kullanabilirsiniz.

Örnekler:

- İlke = "GRP [GroupName] [Department]"
- Kullanıcının bölümü = Mühendislik
- Oluşturulan grup adı = "GRP Grup Mühendisliğim"

Desteklenen Azure Active Directory (Azure AD) öznitelikleri [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] ve [Title] öznitelikleridir.

- Desteklenmeyen kullanıcı öznitelikleri, [postalCode] gibi sabit dizeler olarak kabul edilir.

- Uzantı öznitelikleri ve özel öznitelikler desteklenmez.

Kuruluşunuzdaki tüm kullanıcılar için değerleri doldurulmuş öznitelikler kullanmanız ve daha uzun değerlere sahip öznitelikler kullanmamanızı öneririz.

### <a name="things-to-look-out-for"></a>Dikkate almak için gerekenler

- İlke oluşturma sırasında toplam ön ek ve sonek dizesi uzunluğu 53 karakterle sınırlıdır.

- Ön ekler ve sonekler, grup adında ve grup diğer adında desteklenen özel karakterler içerebilir. Ön ekler ve sonekler grup diğer adında izin verilmeyen özel karakterler içerdiğinde, bunlar yalnızca grup adına uygulanır. Bu durumda, grup adına uygulanan ön ekler ve sonekler, grup diğer adına uygulananlardan farklı olabilir.

  > [!NOTE]
  > Adın başında veya sonundakiler dışında, grup adının herhangi bir yerinde nokta (.) veya kısa çizgiye (-) izin verilir. Adın başında veya sonunda da dahil olmak üzere grup adının herhangi bir yerinde alt çizgiye (_) izin verilir.

- Bağlı gruplar Office 365 Yammer kullanıyorsanız, adlandırma ilkenizde şu karakterleri kullanmaktan kaçının: @, \#, \[, \], . \<, and \> Bu karakterler adlandırma ilkesinde yer alırsa, normal Yammer kullanıcıları grup oluşturamaz.

> [!Tip]
> - Sonek olarak kısa dizeler kullanın.
> - Öznitelikleri değerlerle kullanın.
> - Çok yaratıcı olma, toplam ad uzunluğu en fazla 264 karakterdir.
> - Kullanımı kısıtlamak için kuruluşunuza özgü engellenen sözcükleri karşıya yükleyin.

## <a name="custom-blocked-words"></a>Özel engellenen sözcükler

Grup adlarında ve diğer adlarında engellenecek engellenen sözcüklerin virgülle ayrılmış listesini girebilirsiniz.

Alt dize aramaları yapılmaz; özellikle, kullanıcı tarafından girilen ad ile özel engellenen sözcükler arasında bir hatanın tetiklenmesi için tam eşleşme gerekir.

**Dikkat etmek gerekenler**:

- Engellenen sözcükler büyük/küçük harfe duyarlı değildir.

- Kullanıcı engellenen bir sözcük girdiğinde, grup istemcisi engellenen sözcüğü içeren bir hata iletisi gösterir.

- Kullanılan engellenen sözcüklerde karakter kısıtlaması yoktur.

- Engellenen sözcükler olarak ayarlanabilen 5000 sözcük sınırı vardır.

## <a name="admin-override"></a>Yönetici geçersiz kılma

Bazı yöneticiler tüm grup iş yükleri ve uç noktaları genelinde bu ilkelerden muaf tutulur, böylece bu engellenen sözcüklerle ve istenen adlandırma kurallarıyla gruplar oluşturabilirler. Aşağıda, grup adlandırma ilkesinden muaf tutulan yönetici rollerinin listesi yer alır.

- Genel yönetici

- İş Ortağı Katmanı 1 Desteği

- İş Ortağı Katmanı 2 Desteği

- Kullanıcı hesabı yöneticisi

## <a name="how-to-set-up-the-naming-policy"></a>Adlandırma ilkesini ayarlama

Adlandırma ilkesi ayarlamak için:

1. [Azure Active Directory'de](https://aad.portal.azure.com) **Yönet'in** altında **Gruplar'a** tıklayın.
2. **Ayarlar'ın** altında **Adlandırma ilkesi'ne** tıklayın.
3. **Grup adlandırma ilkesi** sekmesini seçin.
4. **Geçerli ilke'nin** altında, bir ön ek mi, sonek mi yoksa her ikisi birden mi istediğinizi seçin ve uygun onay kutularını seçin.
5. Her satır için **Öznitelik** ve **Dize** arasında seçim yapın ve ardından özniteliği veya dizeyi belirtin.
6. İhtiyacınız olan ön ekleri ve sonekleri ekledikten sonra **Kaydet'e** tıklayın.

![Azure Active Directory'de grup adlandırma ilkesi ayarlarının ekran görüntüsü.](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>İlgili konular

[İşbirliği idaresi planlama önerileri](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[İşbirliği idare planınızı oluşturma](collaboration-governance-first.md)

[Grup ayarlarını yapılandırmak için Azure Active Directory cmdlet'leri](/azure/active-directory/enterprise-users/groups-settings-cmdlets)