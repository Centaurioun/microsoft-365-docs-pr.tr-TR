---
title: Contoso Corporation için bilgi koruması
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso'nın buluttaki dijital varlıklarının güvenliğini sağlamak için kuruluş için Microsoft 365'teki bilgi koruma özelliklerini nasıl kullandığını anlayın.
ms.openlocfilehash: 29c31138a11966510a393dafbe2f5a3741b78f5b
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851446"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Contoso Corporation için bilgi koruması

Contoso, bilgi güvenliği konusunda ciddidir. Ürün tasarımlarını ve özel üretim tekniklerini açıklayan fikri mülkiyetin sızıntısı veya yok edilmesi, onları rekabet dezavantajına yerleştirir.

Contoso, hassas dijital varlıklarını buluta taşımadan önce, şirket içi bilgi sınıflandırması ve koruma gereksinimlerinin Kuruluş için Microsoft 365'in bulut tabanlı hizmetleri tarafından desteklendiğinden emin oldu.

## <a name="contoso-data-security-classification"></a>Contoso veri güvenliği sınıflandırması

Contoso verilerinin analizini yaptı ve aşağıdaki sınıflandırma düzeylerini belirledi.

| Düzey 1: Temel | Düzey 2: Hassas | Düzey 3: Yüksek oranda düzenlenmiş |
|:-------|:-----|:-----|
| Veriler şifrelenir ve yalnızca kimliği doğrulanmış kullanıcılar tarafından kullanılabilir.<BR> <BR> Şirket içinde ve bulut tabanlı depolama ve iş yüklerinde depolanan tüm veriler için sağlanır. Veriler, hizmette bulunduğu ve hizmet ile istemci cihazları arasında aktarım sırasında şifrelenir. <BR><BR>Düzey 1 verilerine örnek olarak normal iş iletişimleri (e-posta) ve yönetim, satış ve destek çalışanlarının dosyaları verilebilir. | Düzey 1 artı güçlü kimlik doğrulaması ve veri kaybı koruması.<BR> <BR> Güçlü kimlik doğrulaması, SMS doğrulaması ile Azure AD Multi-Factor Authentication (MFA) içerir. Microsoft Purview Veri Kaybı Önleme, hassas veya kritik bilgilerin Microsoft bulutunun dışına çıkmamasını sağlar.<BR><BR>Düzey 2 verilerine örnek olarak yeni ürünler için finansal ve yasal bilgiler ile araştırma ve geliştirme verileri verilebilir. | Düzey 2 ile en yüksek şifreleme, kimlik doğrulama ve denetim düzeyleri.<BR><BR>Bekleyen ve buluttaki veriler için en yüksek şifreleme düzeyleri, bölgesel düzenlemelere uygun, akıllı kartlar ve ayrıntılı denetim ve uyarı ile MFA ile birlikte.<BR> <BR>Düzey 3 verilerine örnek olarak müşteri ve iş ortağı kişisel bilgileri, ürün mühendisliği özellikleri ve özel üretim teknikleri verilebilir.  |
||||

## <a name="contoso-information-policies"></a>Contoso bilgi ilkeleri
Aşağıdaki tabloda Contoso bilgi ilkeleri listeledik.


| Değer | Access | Veri saklama | Bilgi koruması |
|:-------|:-----|:-----|:-----|
| Düşük iş değeri (Düzey 1: Temel) | Tümüne erişime izin ver.  | 6 ay | Şifrelemeyi kullanın. |
| Orta iş değeri (Düzey 2: Hassas) | Contoso çalışanlarına, alt yüklenicilerine ve iş ortaklarına erişime izin verin. <BR><BR> MFA, Aktarım Katmanı Güvenliği (TLS) ve Mobil Uygulama Yönetimi (MAM) kullanın. | 2 yıl  | Veri bütünlüğü için karma değerleri kullanın.  |
| Yüksek iş değeri (Düzey 3: Yüksek oranda düzenlenmiş) | Mühendislik ve üretimde yöneticilere ve müşteri adaylarına erişime izin verin. <BR> <BR> Yalnızca yönetilen ağ cihazlarıyla Rights Management System (RMS).  | 7 yıl  | İnkar edilemezler için dijital imzalar kullanın.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Kuruluş için Microsoft 365 ile bilgi koruma için Contoso yolu

Contoso, Microsoft 365'i bilgi koruma gereksinimlerine hazırlamak için şu adımları izlemektedir:

1. Hangi bilgilerin korunacaklarını belirleme

   Contoso, şirket içi SharePoint sitelerinde ve dosya paylaşımlarında bulunan mevcut dijital varlıklarını kapsamlı bir şekilde gözden geçirdi ve her varlığı sınıflandırdı.

2. Veri düzeyleri için erişim, saklama ve bilgi koruma ilkelerini belirleme

   Contoso, veri düzeylerine göre buluta taşınan mevcut dijital varlıkları korumak için kullanılan ayrıntılı ilke gereksinimlerini belirledi.

3. Farklı bilgi düzeyleri için duyarlılık etiketleri ve bunların ayarlarını oluşturma

   Contoso veri düzeyleri için şifreleme, izinler ve filigranlar içeren yüksek oranda düzenlenmiş etiketiyle duyarlılık etiketleri oluşturmuştur.

4. Şirket içi SharePoint sitelerinden ve dosya paylaşımlarından yeni SharePoint sitelerine veri taşıma

    Yeni SharePoint sitelerine geçirilen dosyalar, siteye atanan varsayılan bekletme etiketlerini devraldı.

5. Çalışanları yeni belgeler için duyarlılık etiketlerini kullanmayı, yeni SharePoint siteleri oluştururken Contoso BT ile etkileşim kurmayı ve dijital varlıkları her zaman SharePoint sitelerinde depolamayı eğitin

    Kötü çalışan bilgi depolama alışkanlıklarının değiştirilmesi genellikle bulut için bilgi koruma geçişinin en zor kısmı olarak kabul edilir. Contoso BT ve yönetimi, çalışanların dijital varlıklarını her zaman bulutta etiketlemesini ve depolamasını, şirket içi dosya paylaşımlarını kullanmaktan kaçınmasını ve üçüncü taraf bulut depolama hizmetlerini veya USB sürücülerini kullanmamalarını sağlamak için gereklidir.

## <a name="conditional-access-policies-for-information-protection"></a>Bilgi koruması için Koşullu Erişim ilkeleri

Contoso, Exchange Online ve SharePoint dağıtımı kapsamında aşağıdaki Koşullu Erişim ilkeleri kümesini yapılandırdı ve bunları uygun gruplara uyguladı:

- [Cihaz ilkelerinde yönetilen ve yönetilmeyen uygulama erişimi](../security/office-365-security/identity-access-policies.md)
- [erişim ilkelerini Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint erişim ilkeleri](../security/office-365-security/sharepoint-file-access-policies.md)

Burada bilgi koruması için contoso ilkeleri elde edilir.

:::image type="content" alt-text="Cihaz, Exchange Online ve SharePoint Koşullu Erişim ilkeleri." source="../media/contoso-info-protect/contoso-info-protect-fig1.png" lightbox="../media/contoso-info-protect/contoso-info-protect-fig1.png":::

>[!Note]
>Contoso ayrıca kimlik ve oturum açma için ek Koşullu Erişim ilkeleri yapılandırdı. Bkz. [Contoso Corporation için Kimlik](contoso-identity.md#conditional-access-policies-for-zero-trust-identity-and-device-access).
>

Bu ilkeler şunları sağlar:

- İzin verilen uygulamalar ve kuruluşun verileriyle gerçekleştirebilecekleri eylemler, uygulama koruma ilkeleri tarafından tanımlanır.
- Bilgisayarlar ve mobil cihazlar uyumlu olmalıdır.
- Exchange Online Exchange Online için Office 365 ileti şifrelemesi (OME) kullanır.
- SharePoint, uygulama tarafından zorunlu kılınan kısıtlamaları kullanır.
- SharePoint, yalnızca tarayıcı erişimi için erişim denetimi ilkelerini kullanır ve yönetilmeyen cihazlara erişimi engeller.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Kurumsal özellikler için Microsoft 365'i Contoso veri düzeylerine eşleme

Aşağıdaki tabloda Contoso veri düzeyleri, Kuruluş için Microsoft 365'teki bilgi koruma özellikleriyle eşlenmiştir.

| Düzey | Microsoft 365 bulut hizmetleri | Windows 10 ve Kurumlar için Microsoft 365 Uygulamaları | Güvenlik ve uyumluluk |
|:-------|:-----|:-----|:-----|
| Düzey 1: Temel  | SharePoint ve Exchange Online Koşullu Erişim ilkeleri <BR> SharePoint sitelerindeki izinler | Duyarlılık etiketleri <BR> Bitlocker <BR> Windows Information Protection | Cihaz Koşullu Erişim ilkeleri ve Mobil Uygulama Yönetimi ilkeleri |
| Düzey 2: Hassas | Düzey 1 artı: <BR> <BR> Duyarlılık etiketleri <BR> SharePoint sitelerinde Microsoft 365 bekletme etiketleri <BR> SharePoint ve Exchange Online için Veri Kaybı Önleme <BR> Yalıtılmış SharePoint siteleri  | Düzey 1 artı: <BR> <BR> Dijital varlıklardaki duyarlılık etiketleri  | Düzey 1 |
| Düzey 3: Yüksek oranda düzenlenmiş | Düzey 2 artı: <BR><BR> Ticari gizli bilgiler için kendi anahtarını getir (BYOK) şifreleme ve koruma <BR> Microsoft 365 hizmetleriyle etkileşim kuran iş kolu uygulamaları için Azure Key Vault | Düzey 2 | Düzey 1 |
|||||

Elde edilen Contoso bilgi koruma yapılandırması aşağıdadır.

:::image type="content" alt-text="Contoso'nun sonuçta elde edilen bilgi koruma yapılandırması." source="../media/contoso-info-protect/contoso-info-protect-fig2.png":::

## <a name="next-step"></a>Sonraki adım

Contoso'nın [kuruluş için Microsoft 365'te](contoso-security-summary.md) kimlik ve erişim yönetimi, tehdit koruması, bilgi koruması ve güvenlik yönetimi için güvenlik özelliklerini nasıl kullandığını öğrenin.

## <a name="see-also"></a>Ayrıca bkz.

[Office 365 için Microsoft Defender](/microsoft-365/security/office-365-security/overview)

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Test laboratuvarı kılavuzları](m365-enterprise-test-lab-guides.md)