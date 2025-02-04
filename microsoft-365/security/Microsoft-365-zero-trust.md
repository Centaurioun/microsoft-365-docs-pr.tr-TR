---
title: Microsoft 365 ile Sıfır Güven dağıtım planı
f1.keywords:
- deploy zero trust
- zero trust strategy
ms.author: bcarter
author: brendacarter
manager: dansimp
audience: Admin
description: Tehditlere karşı savunmak ve hassas verileri korumak için Microsoft 365 ile Sıfır Güven güvenlik ilkelerini uygulamayı öğrenin.
ms.topic: tutorial
ms.service: microsoft-365-security
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- m365solution-zerotrust
- m365solution-overview
- m365-security
- zerotrust-solution
- highpri
- tier1
ms.openlocfilehash: de227a1f4524770709e1a25345cfbdb697076c8d
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68815605"
---
# <a name="zero-trust-deployment-plan-with-microsoft-365"></a>Microsoft 365 ile Sıfır Güven dağıtım planı

Bu makale, Microsoft 365 ile **Sıfır Güven** güvenliği oluşturmaya yönelik bir dağıtım planı sağlar. Sıfır Güven, ihlal olduğunu varsayan ve her isteği kontrolsüz bir ağdan geliyormuş gibi doğrulayan yeni bir güvenlik modelidir. İsteğin nereden kaynaklandığına veya hangi kaynağa eriştiğine bakılmaksızın, Sıfır Güven modeli bize "hiçbir zaman güvenme, her zaman doğrulama" öğretir.

Bu makaleyi bu posterle birlikte kullanın.

| Öğe | Açıklama |
|:-----|:-----|
|[![Microsoft 365 Sıfır Güven dağıtım planının çizimi.](../media/solutions-architecture-center/m365-zero-trust-deployment-plan-thumb.png) ](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.pdf) <br/> [PDF](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.pdf) \| [Visio](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.vsdx) <br/> Mart 2022'de güncelleştirildi | **İlgili çözüm kılavuzları** <br/> <ul><li>[Microsoft 365 için kimlik altyapınızı dağıtma](/microsoft-365/enterprise/deploy-identity-solution-overview)</li><li>[Önerilen kimlik ve cihaz erişim yapılandırmaları](../security/office-365-security/microsoft-365-policies-configurations.md)</li><li>[cihazları Intune ile yönetme](../solutions/manage-devices-with-intune-overview.md)</li><li>[Microsoft 365 Defender'ı değerlendirme ve pilot](../security/defender/eval-overview.md)</li><li>[Microsoft Purview ile bilgi koruma çözümü dağıtma](../compliance/information-protection-solution.md)</li><li>[Microsoft 365 ile veri gizliliği düzenlemeleri için bilgi koruma dağıtma](../solutions/information-protection-deploy.md)</li></ul>

## <a name="zero-trust-security-architecture"></a>Sıfır Güven güvenlik mimarisi

Sıfır Güven bir yaklaşım tüm dijital emlak genelinde genişletilir ve tümleşik bir güvenlik felsefesi ve uçtan uca strateji olarak hizmet eder.

Bu çizim, Sıfır Güven katkıda bulunan birincil öğelerin bir gösterimini sağlar.

:::image type="content" source="../media/zero-trust/zero-trust-architecture.png" alt-text="Sıfır Güven güvenlik mimarisi" lightbox="../media/zero-trust/zero-trust-architecture.png":::

Çizimde:

- Güvenlik ilkesi zorlama, Sıfır Güven mimarisinin merkezindedir. Bu, kullanıcı hesabı riskini, cihaz durumunu ve ayarladığınız diğer ölçütleri ve ilkeleri dikkate alan koşullu erişime sahip Multi Factor kimlik doğrulamasını içerir.
- Kimlikler, cihazlar, veriler, uygulamalar, ağ ve diğer altyapı bileşenlerinin tümü uygun güvenlikle yapılandırılır. Bu bileşenlerin her biri için yapılandırılan ilkeler, genel Sıfır Güven stratejinizle koordine edilir. Örneğin, cihaz ilkeleri iyi durumdaki cihazlar için ölçütleri belirler ve koşullu erişim ilkeleri belirli uygulamalara ve verilere erişmek için iyi durumdaki cihazlar gerektirir.
- Tehdit koruması ve zeka ortamı izler, mevcut riskleri ortaya çıkarır ve saldırıları düzeltmek için otomatik eylem gerçekleştirir.

Sıfır Güven hakkında daha fazla bilgi için bkz. Microsoft'un [_**Sıfır Güven Rehberlik Merkezi**_](/security/zero-trust).

<!---
For more information about this architecture, including deployment objectives for your entire digital estate, see [Zero Trust Rapid Modernization Plan (RaMP)](/security/zero-trust/zero-trust-ramp-overview).
-->

## <a name="deploying-zero-trust-for-microsoft-365"></a>Microsoft 365 için Sıfır Güven dağıtma

Microsoft 365, ortamınızda Sıfır Güven oluşturmanıza yardımcı olmak için kasıtlı olarak birçok güvenlik ve bilgi koruma özelliğiyle derlenir. Kuruluşunuzun kullandığı diğer SaaS uygulamalarına ve bu uygulamalardaki verilere erişimi korumak için özelliklerin çoğu genişletilebilir.

Bu çizim, Sıfır Güven özellikleri dağıtma işlemini temsil eder. Bu çalışma, alttan başlayıp en üste doğru çalışarak birlikte yapılandırılabilir çalışma birimlerine bölünerek önkoşul çalışmasının tamamlanmasını sağlar.

:::image type="content" source="../media/zero-trust/m365-zero-trust-deployment-stack.png" alt-text="Microsoft 365 Sıfır Güven dağıtım yığını" lightbox="../media/zero-trust/m365-zero-trust-deployment-stack.png":::

Bu çizimde:

- Sıfır Güven, kimlik ve cihaz korumasının temeli ile başlar.
- Tehdit koruma özellikleri, güvenlik tehditlerinin gerçek zamanlı izlenmesini ve düzeltilmesi için bu temelin üzerine kurulmuştur.
- Bilgi koruma ve idare, en değerli bilgilerinizi korumak ve kişisel bilgileri korumak da dahil olmak üzere uyumluluk standartlarına uymanıza yardımcı olmak için belirli veri türlerini hedefleyen gelişmiş denetimler sağlar.


Bu makalede, bulut kimliğini zaten yapılandırdığınız varsayılır. Bu amaç için yardıma ihtiyacınız varsa bkz. [**Microsoft 365 için kimlik altyapınızı dağıtma**](/microsoft-365/enterprise/deploy-identity-solution-overview).

## <a name="step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies"></a>Adım 1. Sıfır Güven kimliği ve cihaz erişim korumasını yapılandırma — başlangıç noktası ilkeleri

İlk adım, kimlik ve cihaz erişim korumasını yapılandırarak Sıfır Güven temelinizi oluşturmaktır.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-1b.png" alt-text="Sıfır Güven kimliği ve cihaz erişim korumasını yapılandırma işlemi" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-1b.png":::

Bunu gerçekleştirmek için Sıfır Güven [**_kimlik ve cihaz erişim korumasına_**](office-365-security/microsoft-365-policies-configurations.md) gidin. Bu makale serisinde, kurumsal bulut uygulamaları ve hizmetleri, diğer SaaS hizmetleri ve Azure AD ile yayımlanan şirket içi uygulamalar için Microsoft 365'e erişimi güvenli hale getirmek için bir dizi kimlik ve cihaz erişimi önkoşul yapılandırması ve bir dizi Azure Active Directory (Azure AD) Koşullu Erişim, Microsoft Intune ve diğer ilkeler açıklanmaktadır Uygulama Ara Sunucusu.

|Içerir|Önkoşullar|Şunları içermez:|
|---------|---------|---------|
|Üç koruma katmanı için önerilen kimlik ve cihaz erişim ilkeleri: <ul><li>Başlangıç noktası</li><li>Kurumsal (önerilir)</li><li>Özel</li></ul> <br> Ek öneriler: <ul><li>Dış kullanıcılar (konuklar)</li><li>Microsoft Teams</li><li>SharePoint Online</li><li>Bulut Uygulamaları için Microsoft Defender</lu></ul>|Microsoft E3 veya E5 <br><br> Şu modlardan birinde Azure Active Directory: <ul><li>Yalnızca bulut</li><li>Parola karması eşitleme (PHS) kimlik doğrulaması ile karma</li><li>Doğrudan kimlik doğrulaması (PTA) ile karma</li><li>Federe</li></ul>|Yönetilen cihazlar gerektiren ilkeler için cihaz kaydı. Bkz[. 2. Adım. Cihazları kaydetmek için Intune ile uç noktaları yönetme](#step-2-manage-endpoints-with-intune)|

Başlangıç noktası katmanını uygulayarak başlayın. Bu ilkeler, cihazların yönetime kaydedilmesini gerektirmez.

:::image type="content" source="../media/zero-trust/identity-access-starting-point-tier.png" alt-text="Sıfır Güven kimlik ve cihaz erişim ilkeleri — başlangıç noktası katmanı" lightbox="../media/zero-trust/identity-access-starting-point-tier.png":::

## <a name="step-2-manage-endpoints-with-intune"></a>Adım 2. uç noktaları Intune ile yönetme

Ardından, cihazlarınızı yönetime kaydedin ve bunları daha gelişmiş denetimlerle korumaya başlayın.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-2.png" alt-text="uç noktaları Intune ile yönet öğesi" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-2.png":::

Bunu gerçekleştirmek için açıklayıcı yönergeler için [**_Cihazları Intune ile yönetme_**](../solutions/manage-devices-with-intune-overview.md) konusuna gidin.

|Içerir|Önkoşullar|Şunları içermez:|
|---------|---------|---------|
|Cihazları Intune ile kaydetme: <ul><li>Şirkete ait cihazlar</li><li>Otomatik pilot/otomatik</li><li>Kayıt</li></ul> <br> İlkeleri yapılandırma: <ul><li>Uygulama Koruma ilkeleri</li><li>Uyumluluk ilkeleri</li><li>Cihaz profili ilkeleri</li></ul>|Uç noktaları Azure AD ile kaydetme|Aşağıdakiler dahil olmak üzere bilgi koruma özelliklerini yapılandırma: <ul><li>Hassas bilgi türleri</li><li>Etiket</li><li>DLP ilkeleri</li></ul> <br> Bu özellikler için bkz [. 5. Adım. Hassas verileri koruma ve yönetme](#step-5-protect-and-govern-sensitive-data) (bu makalenin ilerleyen bölümlerinde).|

## <a name="step-3-add-zero-trust-identity-and-device-access-protection--enterprise-policies"></a>Adım 3. Sıfır Güven kimlik ve cihaz erişim koruması ekleme — Kurumsal ilkeler

Yönetime kayıtlı cihazlar sayesinde artık uyumlu cihazlar gerektiren önerilen Sıfır Güven kimlik ve cihaz erişim ilkelerinin tamamını uygulayabilirsiniz.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png" alt-text="Cihaz yönetimiyle Sıfır Güven kimliği ve erişim ilkeleri" lightbox="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png":::

[**_Ortak kimlik ve cihaz erişim ilkelerine_**](office-365-security/identity-access-policies.md) dönün ve ilkeleri Kurumsal katmana ekleyin.

:::image type="content" source="../media/zero-trust/identity-access-enterprise-tier.png" alt-text="Sıfır Güven kimlik ve erişim ilkeleri — Kurumsal (önerilen) katmanı" lightbox="../media/zero-trust/identity-access-enterprise-tier.png":::

## <a name="step-4-evaluate-pilot-and-deploy-microsoft-365-defender"></a>Adım 4. Microsoft 365 Defender değerlendirme, pilot uygulama ve dağıtma

Microsoft 365 Defender, Uç nokta, e-posta, uygulamalar ve kimlikler dahil olmak üzere Microsoft 365 ortamınızda sinyal, tehdit ve uyarı verilerini otomatik olarak toplayan, ilişkilendiren ve analiz eden genişletilmiş bir algılama ve yanıt (XDR) çözümüdür.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-defender.png" alt-text="Sıfır Güven mimarisine Microsoft 365 Defender ekleme işlemi" lightbox="../media/zero-trust/m365-zero-trust-architecture-defender.png":::

Microsoft 365 Defender bileşenleri pilot oluşturma ve dağıtmaya yönelik yöntemsel bir kılavuz için [**_Değerlendirme_**](defender/eval-overview.md) ve pilot Microsoft 365 Defender bölümüne gidin.

|Içerir|Önkoşullar|Şunları içermez:|
|---------|---------|---------|
|Tüm bileşenler için değerlendirme ve pilot ortamı ayarlayın: <ul><li>Kimlik için Microsoft Defender</li><li>Office 365 için Defender</li><li>Uç Nokta için Defender</li><li>Bulut Uygulamaları için Microsoft Defender</li></ul> <br> Tehditlere karşı korunun <br><br> Tehditleri araştırın ve karşı yanıt verin|Microsoft 365 Defender her bileşeni için mimari gereksinimleri hakkında bilgi edinmek için kılavuza bakın.| Azure AD Kimlik Koruması bu çözüm kılavuzuna dahil değildir. [1. Adım'a dahildir. Sıfır Güven kimliği ve cihaz erişim korumasını yapılandırın](#step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies).|

## <a name="step-5-protect-and-govern-sensitive-data"></a>Adım 5. Hassas verileri koruma ve yönetme

Hassas bilgileri nerede olursa olsun keşfetmenize, sınıflandırmanıza ve korumanıza yardımcı olmak için Microsoft Purview Bilgi Koruması uygulayın.

Microsoft Purview Bilgi Koruması özellikleri Microsoft Purview'a dahil edilir ve verilerinizi bilmeniz, verilerinizi korumanız ve veri kaybını önlemeniz için size araçlar sağlar.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-info-protect.png" alt-text="Bilgi koruma özellikleri, ilke uygulama yoluyla verileri koruma" lightbox="../media/zero-trust/m365-zero-trust-architecture-info-protect.png":::

Bu çalışma, bu makalenin önceki bölümlerinde gösterilen dağıtım yığınının en üstünde gösteriliyor olsa da, bu çalışmaya istediğiniz zaman başlayabilirsiniz.

Microsoft Purview Bilgi Koruması, belirli iş hedeflerinizi gerçekleştirmek için kullanabileceğiniz bir çerçeve, süreç ve özellikler sağlar.

![Microsoft Purview Bilgi Koruması](../media/zero-trust/mip-solution-overview.png)

Bilgi korumasını planlama ve dağıtma hakkında daha fazla bilgi için bkz. [**_Microsoft Purview Bilgi Koruması çözümü dağıtma_**](../compliance/information-protection-solution.md). 

Veri gizliliği düzenlemeleri için bilgi koruması dağıtıyorsanız, bu çözüm kılavuzu tüm süreç için önerilen bir çerçeve sağlar: [**_Microsoft 365 ile veri gizliliği düzenlemeleri için bilgi koruması dağıtma_**](../solutions/information-protection-deploy.md).
