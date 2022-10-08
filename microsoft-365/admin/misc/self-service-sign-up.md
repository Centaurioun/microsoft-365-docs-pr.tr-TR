---
title: Kuruluşunuzda self servis kaydolmayı kullanma
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_signup
- AdminSurgePortfolio
- okr_SMB
search.appverid: MET150
description: Microsoft Power Apps, Microsoft Power Automate ve Dynamics 365 for Finance gibi Microsoft 365 self servis kaydolma ve kullanılabilir self servis programları hakkında bilgi edinin.
ms.date: 03/17/2021
ms.openlocfilehash: e12e3b75be80a78640fb57cceb7aeca1cbd85a45
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68204881"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Kuruluşunuzda self servis kaydolmayı kullanma

Self servis kaydolma, kuruluşunuzdaki kullanıcıların Microsoft'tan çevrimiçi hizmetler kaydolmasını kolaylaştırır. Bu kaydolma işlemine "self servis kaydolma" diyoruz çünkü kullanıcılarınız aboneliğiniz tarafından ödenen hizmetleri kullanmak için kaydolabilir veya kendi adlarına işlem yapmanıza gerek kalmadan ücretsiz hizmetleri kullanabilir.

## <a name="how-self-service-sign-up-works"></a>Self servis kaydolma nasıl çalışır?

Aşağıdaki örnekte, bir okulda kendi kendine kaydolmanın nasıl çalıştığı açıklanmaktadır. Aynı işlem, kiracısında self servis programları etkinleştirilmiş olan tüm kuruluşlar için de geçerlidir.

1. Öğrenciler ve öğretim üyeleri, kurumunuzla ilişkili olduklarını belirten okul e-posta adreslerine sahiptir. Örneğin, jakob@uw.edu e-posta adresi, Washington Üniversitesi'ndeki bir öğrenciyi gösterebilir.
2. Öğrenciler ve öğretim üyeleri [web sitemize](https://go.microsoft.com/fwlink/p/?LinkId=536628) gidip e-posta adreslerini kullanarak kuruluşunuzun sunduğu hizmetlere (örneğin, Kurumlar için Microsoft 365 Uygulamaları) kaydolabilir. Ayrıca sunduğumuz diğer ücretsiz hizmetlere de kaydolabilir.
3. E-posta adreslerini doğrularız ve ardından Microsoft 365, Power BI veya diğer hizmetleri kullanmaya hemen başlayabilirler.
4. İşletme yöneticisi olarak, Microsoft 365 yönetim merkezi **Lisanslama** sayfasında aboneliği seçerek kimlerin aboneliğe kaydolmuş olduğunu görebilirsiniz. Bu şekilde, kiracınızdaki hizmetler için yeni veya tanınmayan lisansların ne zaman olduğunu görebilirsiniz. Kullanıcıların self servis aboneliklere kaydolup kaydolamayacağını denetlemek için **AllowAdHocSubscriptions** parametresiyle [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) PowerShell cmdlet'ini kullanın. Daha fazla bilgi için bkz. [Self servis ayarları Nasıl yaparım? denetlensin mi?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Kullanılabilir self servis programları

Şu anda kullanılabilir self servis programları aşağıdadır. Yeni programlar eklendikçe bu liste güncelleştirilir.

| Program <br/> | Açıklama <br/> | Ek Bilgiler <br/> | Self servis kaydolma web sitesi <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1** <br/> |Herhangi bir öğrenci veya öğretmen, ücretsiz Office 365 kaydolmak ve web için Office uygulamaları, 1 TB OneDrive bulut depolama alanı ve sınıf, ekip ve proje siteleri için SharePoint Online almak için bir okul e-posta adresi kullanabilir.  <br/> |[Office 365 Eğitim Teknik SSS](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Eğitim](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Uygun öğrenciler ve öğretmenler, yukarıda belirtilen her şeyi ve Kurumlar için Microsoft 365 Uygulamaları içeren Office 365 A1 Plus'a kaydolabilir. Kurumlar için Microsoft 365 Uygulamaları, masaüstü veya dizüstü bilgisayarınızda yüklü olan Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access ve Skype Kurumsal dahil üretkenlik yazılımıdır.  <br/> |[Office 365 Eğitim Teknik SSS](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Eğitim](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI, kullanıcıların verileri görselleştirmesine, keşifleri paylaşmasına ve sezgisel yeni yollarla işbirliği yapmasına olanak tanır. <br/> Kuruluşunuz zaten aboneyse, kullanıcılara gelişmiş özelliklere sınırlı ve ücretsiz erişim sunan "Power BI Pro Bireysel Kullanıcı Deneme Sürümü" lisanslarını da görebilirsiniz.  <br/> |[Kuruluşunuzda Power BI](/power-bi/enterprise/service-admin-org-subscription) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |Kişiler için RMS, Azure Rights Management (Azure RMS) tarafından korunan, ancak BT departmanları Azure Rights Management (Azure RMS) veya Active Directory Rights Management Services (AD RMS) uygulamamış olan hassas dosyalar gönderilen bir kuruluştaki kullanıcılar için ücretsiz bir self servis aboneliğidir.  <br/> |[Kişiler için RMS ve Azure Rights Management](/azure/information-protection/rms-for-individuals) <br/> |Belirli bir hak korumalı belgeyi açıp açamayacağınızı denetleyebilmeniz için [Microsoft Rights Management portalı](https://portal.azure.com/).  <br/> |
|**Microsoft Power Apps** <br/> |Power Apps'te, oluşturduğunuz veya başka birinin oluşturup sizinle paylaştığı bir uygulamayı çalıştırarak kuruluş verilerini yönetebilirsiniz. Uygulamalar telefonlar gibi mobil cihazlarda çalışır veya Dynamics 365'i açarak bunları tarayıcıda çalıştırabilirsiniz. C# gibi bir programlama dilini öğrenmeden sonsuz çeşitli uygulamalar oluşturabilirsiniz.  <br/> |[Power Apps için self servis kaydolma](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Küçük ve orta ölçekli işletmeler için eksiksiz bir iş ve finansal yönetim çözümü edinin. Dynamics 365 for Financials, ilk günden başlayarak sipariş verme, satış, faturalama ve raporlamayı kolaylaştırır.  <br/> |[Finansallar için Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Finansallar için Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |İş yapma hızınızı artırın. Dynamics 365 for Operations'daki erp araçlarının tamamı, hızınızı artırmanıza yardımcı olmak için küresel ölçeklenebilirlik ve dijital zeka sağlar.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource, Microsoft bulut platformunda oluşturulan hizmet olarak yazılım iş uygulamaları için bir hedeftir. AppSource, Azure, Dynamics 365, Office 365 ve Power BI gibi Microsoft ürünlerinin işlevselliğini genişleten yüzlerce uygulama, eklenti ve içerik paketi içerir.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft İş Ortağı Teşvikleri** <br/> |Microsoft İş Ortağı Ağı üç tür üyelik sağlar. Her tür, işletmenizin büyümesine yardımcı olmak için bir dizi avantaj sağlar. Hedeflerinize ulaşırken, daha fazla avantaja erişmek ve bizimle ve ağdaki diğer iş ortaklarıyla ilişkinizi geliştirmek için benzersiz ihtiyaçlarınıza uygun düzeyde programa katılın.  <br/> |[Microsoft İş Ortağı Teşvikleri](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft İş Ortağı Teşvikleri](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft İş Merkezi** <br/> |Microsoft İş Merkezi, Microsoft Ürün ve Hizmet Sözleşmesi (MPSA) aracılığıyla alışveriş yapan müşterilerin portalıdır. <br/> |[Hızlı Başlangıç: Microsoft İş Merkezi'ne kaydolma](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft İş Merkezi](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft Toplu Lisans Hizmeti Merkezi** <br/> |Microsoft Toplu Lisans Hizmet Merkezi, Enterprise, Select, Education (Campus veya School), Open Value, Open License ve ISV Royalty agreements altında satın alınan lisansları görüntüler.  <br/> |[VLSC Eğitimi ve Kaynakları](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Toplu Lisans Hizmet Merkezi](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Eğitimciler Minecraft'ı öğrenme platformu olarak kullanarak her öğrenciyi daha fazlasını başarmaya teşvik edebilir ve ilham verebilir ve öğrenmeye yönelik bir tutkuyu ateşleyebilir. Minecraft'ı kullanarak öğrenci potansiyelini ortaya çıkarma hakkında bilgi edinen eğitimcilerden oluşan bir topluluğa katılın.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |İletişimi, katılımı ve öğrenmeyi geliştirmek için videoları kuruluşunuz genelinde karşıya yükleyin ve paylaşın.  <br/> |[0. Gün deneyimine kaydolma &amp;](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate, dosyaları eşitlemek, bildirim almak, veri toplamak ve daha fazlası için sık kullandığınız uygulamalar ve hizmetler arasında otomatik iş akışları ayarlamanıza yardımcı olan bir üründür.  <br/> |[Power Automate'e kaydolma ve oturum açma](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agents** <br/> |Power Virtual Agents, veri bilimcilerine veya geliştiricilere ihtiyaç duymadan kılavuzlu, kod içermeyen bir grafik arabirimi kullanarak ekipleri kolayca güçlü botlar oluşturma konusunda güçlendirir. Power Virtual Agents bugün sektörde bot oluşturmayla ilgili önemli sorunların çoğunu ele almaktadır. Konu uzmanlarıyla botları oluşturan geliştirme ekipleri arasındaki boşluğu ve sorunu fark eden ekipler ile sorunu gidermek için botu güncelleştirme arasındaki uzun gecikme süresini ortadan kaldırır.  <br/> |[Lisanslama ve erişim ayrıntıları](/power-virtual-agents/requirements-licensing) <br/> |[Power Virtual Agents'a kaydolma](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) işletmeler arası (B2B) işbirliği, dış kullanıcıları (veya "konuk kullanıcıları") ücretli Azure AD hizmetlerinizi kullanmaya davet etmenizi sağlar. Bazı özellikler ücretsizdir, ancak ücretli Azure AD özellikleri için, kiracınızdaki bir çalışan veya konuk olmayan bir kullanıcı için sahip olduğunuz her Azure AD sürümü lisansı için en fazla beş konuk kullanıcı davet edebilirsiniz. <br/> |[Azure AD B2B işbirliğine kaydolma için self servis](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active Directory B2B işbirliği lisanslama kılavuzu](/azure/active-directory/b2b/licensing-guidance) <br/> |
