---
title: Deneme playbook'u - Uç Nokta için Microsoft Defender
description: 90 günlük ücretsiz denemenizden en iyi şekilde yararlanmak için bu kılavuzu kullanın. Uç Nokta için Defender'ın gelişmiş tehditleri önlemeye, algılamaya, araştırmaya ve yanıtlamaya nasıl yardımcı olabileceğini görün.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: 07/07/2022
ms.collection:
- m365-security
- tier2
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
ms.reviewer: ''
f1.keywords: NOCSH
ms.openlocfilehash: 2432a7aea0f9c2d2431d1fc189fcd9393d689b27
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68205453"
---
# <a name="trial-playbook-microsoft-defender-for-endpoint"></a>Deneme playbook'u: Uç Nokta için Microsoft Defender

Uç Nokta için Microsoft Defender Plan 2 deneme playbook'una hoş geldiniz!

Bu playbook, ücretsiz denemenizden en iyi şekilde yararlanabilirsiniz. Microsoft Defender ekibinden bu makalede önerilen adımları kullanarak Uç Nokta için Defender'ın gelişmiş tehditleri önlemenize, algılamanıza, araştırmanıza ve yanıtlamanıza nasıl yardımcı olabileceğini öğreneceksiniz.

## <a name="what-is-defender-for-endpoint"></a>Uç Nokta için Defender nedir?

[Uç Nokta için Defender](microsoft-defender-endpoint.md) , Windows ve Microsoft'un sağlam bulut hizmetinde yerleşik olarak bulunan aşağıdaki teknoloji bileşimini kullanan bir kurumsal uç nokta güvenlik platformudur: 

- **Uç nokta davranış algılayıcıları**: Windows'a eklenmiş olan bu algılayıcılar işletim sisteminden davranış sinyallerini toplar ve işler ve algılayıcı verilerini Uç Nokta için Defender'ın özel, yalıtılmış, bulut örneğine gönderir.

- **Bulut güvenlik analizi**: Windows ekosistemi, kurumsal bulut ürünleri (Microsoft 365 gibi) ve çevrimiçi varlıklar genelinde büyük veri, cihaz öğrenmesi ve benzersiz Microsoft optiği kullanılarak davranış sinyalleri içgörülere, algılamalara ve gelişmiş tehditlere yönelik önerilen yanıtlara çevrilir.

- **Tehdit bilgileri**: Microsoft avcıları ve güvenlik ekipleri tarafından oluşturulan ve iş ortakları tarafından sağlanan tehdit bilgileriyle genişletilen tehdit bilgileri, Uç Nokta için Defender'ın saldırgan araçlarını, tekniklerini ve yordamlarını tanımlamasını ve toplanan algılayıcı verilerinde gözlemlendiğinde uyarılar oluşturmasını sağlar.

<center><h2>Uç Nokta için Microsoft Defender</center></h2>
<table>
<tr>
<td><a href="microsoft-defender-endpoint.md#tvm"><center><img src="images/logo-mdvm.png" alt="Vulnerability Management"> <br><b> Core Defender Güvenlik Açığı Yönetimi</b></center></a></td>
<td><a href="microsoft-defender-endpoint.md#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Saldırı yüzeyini azaltma</b></center></a></td>
<td><center><a href="microsoft-defender-endpoint.md#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Yeni nesil koruma</b></a></center></td>
<td><center><a href="microsoft-defender-endpoint.md#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Uç nokta algılama ve yanıt</b></a></center></td>
<td><center><a href="microsoft-defender-endpoint.md#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Otomatik araştırma ve düzeltme</b></a></center></td>
<td><center><a href="microsoft-defender-endpoint.md#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft Tehdit Uzmanları</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="microsoft-defender-endpoint.md#apis"><center><b>Merkezi yapılandırma ve yönetim, API'ler</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="microsoft-defender-endpoint.md#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

**Başlayalım!**

## <a name="set-up-your-trial"></a>Deneme sürümünüzü ayarlama

1. [Lisans durumunuzu onaylayın](#step-1-confirm-your-license-state).
2. [Rol tabanlı erişim denetimini ayarlayın ve güvenlik ekibinize izin verin](#step-2-set-up-role-based-access-control-and-grant-permissions-to-your-security-team).
3. [Microsoft 365 Defender portalını ziyaret edin](#step-3-visit-the-microsoft-365-defender-portal).
4. [Desteklenen yönetim araçlarından herhangi birini kullanarak uç noktaları ekleme](#step-4-onboard-endpoints-using-any-of-the-supported-management-tools).
5. [Özellikleri yapılandırın](#step-5-configure-capabilities).
6. [Sanal saldırılar aracılığıyla Uç Nokta için Microsoft Defender deneyimi yaşayın](#step-6-experience-microsoft-defender-for-endpoint-through-simulated-attacks).
7. [Uç Nokta için Microsoft Defender değerlendirme laboratuvarını ayarlayın](#step-7-set-up-the-microsoft-defender-for-endpoint-evaluation-lab).

## <a name="step-1-confirm-your-license-state"></a>1. Adım: Lisans durumunuzu onaylayın

Uç Nokta için Defender aboneliğinizin düzgün bir şekilde sağlandığından emin olmak için lisans durumunuzu Microsoft 365 yönetim merkezi ([https://admin.microsoft.com](https://admin.microsoft.com)) veya Azure Active Directory'de ([https://portal.azure.com](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)) de kontrol edebilirsiniz.

[Lisans durumunuzu denetleyin](production-deployment.md#check-license-state).

## <a name="step-2-set-up-role-based-access-control-and-grant-permissions-to-your-security-team"></a>2. Adım: Rol tabanlı erişim denetimi ayarlama ve güvenlik ekibinize izin verme

Microsoft, en az ayrıcalık kavramını kullanmanızı önerir. Uç Nokta için Defender, Azure Active Directory'deki yerleşik rolleri kullanır. [Kullanılabilen farklı rolleri gözden geçirin](/azure/active-directory/roles/permissions-reference) ve güvenlik ekibiniz için uygun rolleri seçin. Deneme tamamlandıktan sonra bazı rollerin geçici olarak uygulanması ve kaldırılması gerekebilir.

Dizin izinlerine sahip kullanıcılar için ek denetim, denetim ve erişim gözden geçirmesi sağlamak üzere rollerinizi yönetmek için [Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure) kullanın.

Uç Nokta için Defender izinleri yönetmek için iki yolu destekler:

- Temel izin yönetimi: İzinleri tam erişim veya salt okunur olarak ayarlayın. Azure Active Directory'de Genel Yönetici veya Güvenlik Yöneticisi rollerine sahip kullanıcılar tam erişime sahiptir. Güvenlik okuyucusu rolü salt okunur erişime sahiptir ve makineleri/cihaz envanterini görüntüleme erişimi vermez.
- Rol tabanlı erişim denetimi (RBAC): Rolleri tanımlayarak, rollere Azure AD kullanıcı grupları atayarak ve kullanıcı gruplarına cihaz gruplarına erişim vererek ayrıntılı izinleri ayarlayın. Daha fazla bilgi için bkz. [Rol tabanlı erişim denetimini kullanarak portal erişimini yönetme](rbac.md).

    > [!NOTE]
    > Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.

## <a name="step-3-visit-the-microsoft-365-defender-portal"></a>3. Adım: Microsoft 365 Defender portalını ziyaret edin

Microsoft 365 Defender portalı ([https://security.microsoft.com](https://security.microsoft.com)), Uç Nokta için Defender özelliklerinize erişebileceğiniz yerdir.

1. Microsoft 365 Defender portalında [neler bekleyebileceğinizi gözden geçirin](../defender/microsoft-365-defender-portal.md).

2. [https://security.microsoft.com](https://security.microsoft.com) adresine gidin ve oturum açın.

3. Gezinti bölmesinde, özelliklerinize erişmek için **Uç Noktalar** bölümüne bakın. 

## <a name="step-4-onboard-endpoints-using-any-of-the-supported-management-tools"></a>4. Adım: Desteklenen yönetim araçlarından herhangi birini kullanarak uç noktaları ekleme 

Bu bölümde cihazları (uç noktalar) eklemeye yönelik genel adımlar özetlenmektedir.

1. Ekleme işlemine hızlı bir genel bakış için [bu videoyu izleyin](https://www.microsoft.com/videoplayer/embed/RE4bGqr) ve kullanılabilir araçlar ve yöntemler hakkında bilgi edinin.

2. [Cihaz ekleme aracı seçeneklerinizi](onboarding.md) gözden geçirin ve ortamınız için en uygun seçeneği belirleyin. 

## <a name="step-5-configure-capabilities"></a>5. Adım: Özellikleri yapılandırma 

Cihazları (uç noktalar) ekledikten sonra uç nokta algılama ve yanıt, yeni nesil koruma ve saldırı yüzeyini azaltma gibi çeşitli özellikleri yapılandıracaksınız.

Yapılandıracak bileşenleri seçmek için [bu tabloyu](onboarding.md) kullanın. Tüm kullanılabilir özellikleri yapılandırmanızı öneririz, ancak geçerli olmayan özellikleri atlayabilirsiniz.

## <a name="step-6-experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>6. Adım: Sanal saldırılar aracılığıyla Uç Nokta için Microsoft Defender deneyimi

Hizmete birkaç cihazdan fazlasını eklemeden önce Uç Nokta için Defender'ı deneyimlemek isteyebilirsiniz. Bunu yapmak için, birkaç test cihazında denetimli saldırı simülasyonları çalıştırabilirsiniz. Sanal saldırıları çalıştırdıktan sonra Uç Nokta için Defender'ın kötü amaçlı etkinliği nasıl ortaya atdığını gözden geçirebilir ve verimli bir yanıta nasıl olanak sağladığını keşfedebilirsiniz.

Sağlanan simülasyonlardan herhangi birini çalıştırmak için en az [bir yerleşik cihaza](onboard-configure.md) ihtiyacınız vardır.

1. Öğreticilere erişin. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)), gezinti bölmesindeki **Uç Noktalar'ın** altında **Öğreticiler'i** seçin.

2. Her saldırı senaryosuyla birlikte sağlanan kılavuz belgesini okuyun. Her belgede işletim sistemi ve uygulama gereksinimleri ile bir saldırı senaryosuna özgü ayrıntılı yönergeler bulunur.

3. [Bir simülasyon çalıştırın](attack-simulations.md).

## <a name="step-7-set-up-the-microsoft-defender-for-endpoint-evaluation-lab"></a>7. Adım: Uç Nokta için Microsoft Defender değerlendirme laboratuvarını ayarlama   

Uç Nokta için Microsoft Defender değerlendirme laboratuvarı, platformun özelliklerini değerlendirmeye, simülasyon çalıştırmaya ve önleme, algılama ve düzeltme özelliklerini çalışırken görmeye odaklanabilmeniz için cihaz ve ortam yapılandırmasının karmaşıklıklarını ortadan kaldıracak şekilde tasarlanmıştır. Değerlendirme laboratuvarında basitleştirilmiş kurulum deneyimini kullanarak, Uç Nokta için Defender'ın nasıl performans sergilediğini görmek için kendi test senaryolarınızı ve önceden hazırlanmış simülasyonları çalıştırmaya odaklanabilirsiniz.

- Değerlendirme [laboratuvarına genel bakış videosunu izleyin](https://www.microsoft.com/videoplayer/embed/RE4qLUM)
- [Laboratuvarı kullanmaya başlama](evaluation-lab.md) 


## <a name="see-also"></a>Ayrıca bkz.

- [Uç Nokta için Defender teknik belgeleri](microsoft-defender-endpoint.md)
- [Microsoft Güvenlik teknik içerik kitaplığı](https://www.microsoft.com/security/content-library/Home/Index)
- [Uç Nokta için Defender tanıtımı](https://cdx.transform.microsoft.com/experience-detail/d5eca65d-13a3-464d-9171-c24cf9dd6050)

