---
title: Microsoft 365 İş Ekstra deneme akış planı
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.collection: m365-security-compliance
ms.localizationpriority: high
ms.date: 08/24/2022
ms.prod: m365-security
search.appverid:
- MOE150
- MET150
description: Microsoft 365 İş Ekstra denemenizden en iyi şekilde geçin. Temel üretkenlik ve güvenlik özelliklerinden bazılarını deneyin.
ms.openlocfilehash: 8a74d5b107f8142c7d0b733e558540fecaff3346
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497027"
---
# <a name="trial-playbook-microsoft-365-business-premium"></a>Deneme playbook'u: Microsoft 365 İş Ekstra

Microsoft Business Premium deneme playbook'una hoş geldiniz. Bu playbook, Microsoft 365 İş Ekstra üretkenliği nasıl artırdığını deneyimleyerek 30 günlük ücretsiz denemenizden en iyi şekilde yararlanabilir ve kuruluşunuzun gelişmiş güvenlik özellikleriyle korunmasına yardımcı olur. Microsoft önerilerini kullanarak tehdit koruma özelliklerinizi ayarlamayı, algılanan tehditleri analiz etmeyi ve siber saldırılara yanıt vermeyi öğrenin.

## <a name="set-up-the-microsoft-365-business-premium-trial"></a>Microsoft 365 İş Ekstra deneme sürümünü ayarlama

[Deneme sürümü başlattığınızda veya Microsoft 365 İş Ekstra satın](get-microsoft-365-business-premium.md) aldığınızda, ilk adımınız her şeyi ayarlamaktır.

> [!TIP]
> Bu playbook'u tarayıcı sık kullanılanlarınıza kaydedin. Playbook'taki bağlantılar sizi bu konumdan uzaklaştırdığında, devam etmek için bu playbook'a dönmeniz yeterlidir.

İlk olarak [, denemenizi ayarlayın](../business-premium/m365bp-setup.md)!

Deneme sürümünü başlattıktan ve kurulum işlemini tamamladıktan sonra değişikliklerin geçerli olması iki saate kadar sürebilir.

Microsoft 365 İş Ekstra ortamınızda kullanabileceğiniz [Önceden Ayarlanmış güvenlik ilkeleri](/security/office-365-security/preset-security-policies.md) içerir. Bu ilkeler, çoğu kullanıcı için uygun bir temel koruma profilini temsil eder. Standart koruma şunları içerir:

- Tüm kiracı veya deneme kurulum işlemi sırasında seçmiş olabileceğiniz kullanıcı alt kümesini kapsayan [Güvenli Bağlantılar](../security/office-365-security/safe-links.md), [Güvenli Ekler](../security/office-365-security/safe-attachments.md) ve [Kimlik Avı](../security/office-365-security/anti-phishing-protection.md) önleme ilkeleri. (Deneme aboneliğiniz en fazla 25 kullanıcıya yöneliktir.)

- [SharePoint](/sharepoint/introduction), [OneDrive](/onedrive/one-drive-quickstart-small-business), [Office uygulamaları](/deployoffice/about-microsoft-365-apps) ve [Microsoft Teams](/microsoftteams/teams-overview) gibi üretkenlik uygulamaları için koruma.

## <a name="add-a-domain"></a>Etki alanı ekleme

Microsoft 365 İş Ekstra denediğinizde veya satın aldığınızda, sahip olduğunuz bir etki alanını kullanma veya kaydolma işlemi sırasında bir etki alanı satın alma seçeneğiniz vardır.

> [!NOTE]
> Kaydolduğunda yeni bir etki alanı satın aldıysanız, etki alanınız ayarlanmıştır ve Kullanıcı ekle ve lisans ata'ya geçebilirsiniz. Yönetim merkezine()[https://admin.microsoft.com](https://admin.microsoft.com) gidin.

1. Sihirbazı başlatmak için yönetim merkezi **menüsünden Kurulum'u** seçin.

2. **Özel bir etki alanıyla e-posta ayarla'yı** ve ardından **Zaten sahip olduğunuz etki alanını kullan'ı** `contoso.com`seçin.

3. İşlemi tamamlamak için sihirbazdaki diğer adımları izleyin.

   > [!Important]
   > Kayıt sırasında bir etki alanı satın aldıysanız, burada **Etki alanı ekle** adımını görmezsiniz. Bunun yerine **Kullanıcı ekle'ye** gidin.

4. Etki alanının sahibi olduğunuzu doğrulayan [Office 365 için herhangi bir DNS barındırma sağlayıcısında DNS kayıtları oluşturmak için](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) sihirbazdaki adımları izleyin. Etki alanı konağınızı biliyorsanız bkz. [Microsoft 365'e etki alanı ekleme](/microsoft-365/admin/setup/add-domain).

5. Barındırma sağlayıcınız GoDaddy veya etki alanı bağlantısı etkinleştirilmiş başka bir konaksa oturum açmanız ve Microsoft'un sizin adınıza otomatik olarak kimlik doğrulaması yapmasına izin vermeniz istenir.

## <a name="onboard-and-protect-devices"></a>Cihazları ekleme ve koruma

Microsoft 365 İş Ekstra, cihazları korumaya yönelik yeni bir güvenlik çözümü olan İş için Defender'ı içerir. Bkz[. cihazları İş için Microsoft Defender ekleme](../security/defender-business/mdb-onboard-devices.md).

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. [Kurulum sihirbazını](../security/defender-business/mdb-use-wizard.md) çalıştırın.

3. [Cihazları ekleme](../security/defender-business/mdb-onboard-devices.md).

4. [Güvenlik ilkelerinizi gözden geçirin](../security/defender-business/mdb-configure-security-settings.md).

## <a name="use-microsoft-365-apps-on-devices"></a>Cihazlarda Microsoft 365 Uygulamaları kullanma

1. İlk olarak[, Microsoft 365 Uygulamaları yüklemeniz](m365bp-install-office-apps.md) gerekir.

2. [https://office.com](https://office.com) adresine gidin ve oturum açın. (Bkz [. Office.com Başlarken](https://support.microsoft.com/office/get-started-at-office-com-91a4ec74-67fe-4a84-a268-f6bdf3da1804).)

3. Word belgesi gibi bir Office [belgesi](https://support.microsoft.com/office/basic-tasks-in-word-87b3243c-b0bf-4a29-82aa-09a681999fdc) oluşturun.

4. [Bir belgeyi](https://support.microsoft.com/office/share-your-documents-651e1cb9-9a51-46dc-8d32-bdb7d928eedd) ekip üyesiyle paylaşın.

## <a name="start-using-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalını kullanmaya başlama 

1. adresinden Microsoft 365 Defender portalına [https://security.microsoft.com](https://security.microsoft.com)erişin.

2. [Portal hakkında](../security/defender-business/mdb-get-started.md) bilgi sahibi olmak için biraz zaman ayırın.

3. Şimdi [güvenlik duruşunuzu değerlendirin](../security/defender/microsoft-secure-score.md) ve puanınızı nasıl geliştirebileceğinize bakın.

4. [Bir güvenlik olayına nasıl yanıt vereceğinizi](../security/defender-business/mdb-respond-mitigate-threats.md) öğrenin.

5. Son olarak düzeltme [eylemlerini gözden geçirin](../security/defender-business/mdb-review-remediation-actions.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft 365 İş Ekstra - küçük işletmeler için siber güvenlik](index.md)
- [İş için Microsoft Defender nedir?](../security/defender-business/mdb-overview.md)
