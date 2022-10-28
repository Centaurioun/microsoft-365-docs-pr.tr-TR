---
title: macOS cihazlarındaki Uç Nokta için Microsoft Defender Jamf Pro'ya kaydetme
description: macOS cihazlarındaki Uç Nokta için Microsoft Defender Jamf Pro'ya kaydetme
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, big sur, monterey, ventura, mde for mac
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ea0872a96a0d020074f3ce9caa6314af3c845ab6
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68769611"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>macOS cihazlarındaki Uç Nokta için Microsoft Defender Jamf Pro'ya kaydetme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>macOS cihazlarını kaydetme

JamF'ye kaydolmanın birden çok yöntemi vardır.

Bu makale iki yöntemde size yol gösterecektir:

- [Yöntem 1: Kayıt Davetleri](#enrollment-method-1-enrollment-invitations)
- [Yöntem 2: Kayıtları Önceden Oluşturun](#enrollment-method-2-prestage-enrollments)

Tam liste için bkz [. Bilgisayar Kaydı Hakkında](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).

## <a name="enrollment-method-1-enrollment-invitations"></a>Kayıt Yöntemi 1: Kayıt Davetleri

1. Jamf Pro panosunda **Kayıt davetleri'ne** gidin.

   :::image type="content" source="images/a347307458d6a9bbfa88df7dbe15398f.png" alt-text="Yapılandırma ayarları1" lightbox="images/a347307458d6a9bbfa88df7dbe15398f.png":::

2. **+ Yeni'yi** seçin.

   :::image type="content" source="images/b6c7ad56d50f497c38fc14c1e315456c.png" alt-text="Logo açıklamasının yakından görüntüsü otomatik olarak oluşturulur" lightbox="images/b6c7ad56d50f497c38fc14c1e315456c.png":::

3. **Email Adresleri'nin altındaki Davet > için Alıcıları Belirtin** alanına  alıcıların e-posta adreslerini girin.

    :::image type="content" source="images/718b9d609f9f77c8b13ba88c4c0abe5d.png" alt-text="Yapılandırma ayarları2" lightbox="images/718b9d609f9f77c8b13ba88c4c0abe5d.png":::

    :::image type="content" source="images/ae3597247b6bc7c5347cf56ab1e820c0.png" alt-text="Yapılandırma ayarları3" lightbox="images/ae3597247b6bc7c5347cf56ab1e820c0.png":::

    Örneğin: janedoe@contoso.com

    :::image type="content" source="images/4922c0fcdde4c7f73242b13bf5e35c19.png" alt-text="Yapılandırma ayarları4" lightbox="images/4922c0fcdde4c7f73242b13bf5e35c19.png":::

4. Davet için iletiyi yapılandırın.

   :::image type="content" source="images/ce580aec080512d44a37ff8e82e5c2ac.png" alt-text="Yapılandırma ayarları5" lightbox="images/ce580aec080512d44a37ff8e82e5c2ac.png":::

   :::image type="content" source="images/5856b765a6ce677caacb130ca36b1a62.png" alt-text="Yapılandırma ayarları6" lightbox="images/5856b765a6ce677caacb130ca36b1a62.png":::

   :::image type="content" source="images/3ced5383a6be788486d89d407d042f28.png" alt-text="Yapılandırma ayarları7" lightbox="images/3ced5383a6be788486d89d407d042f28.png":::

   :::image type="content" source="images/54be9c6ed5b24cebe628dc3cd9ca4089.png" alt-text="Yapılandırma ayarları8" lightbox="images/54be9c6ed5b24cebe628dc3cd9ca4089.png":::

## <a name="enrollment-method-2-prestage-enrollments"></a>Kayıt Yöntemi 2: Kayıtları Önceden Oluşturun

1. Jamf Pro panosunda **Prestage kayıtları'na** gidin.

   :::image type="content" source="images/6fd0cb2bbb0e60a623829c91fd0826ab.png" alt-text="Yapılandırma ayarları9" lightbox="images/6fd0cb2bbb0e60a623829c91fd0826ab.png":::

2. [Bilgisayar Ön Hazırlık Kayıtları'ndaki](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html) yönergeleri izleyin.

## <a name="enroll-macos-device"></a>macOS cihazını kaydetme

1. **Devam'ı** seçin ve **SISTEM Tercihleri** penceresinden CA sertifikasını yükleyin.

   :::image type="content" source="images/jamfpro-ca-certificate.png" alt-text="Jamf Pro kaydı1" lightbox="images/jamfpro-ca-certificate.png":::

2. CA sertifikası yüklendikten sonra tarayıcı penceresine dönün ve **Devam'ı** seçip MDM profilini yükleyin.

   :::image type="content" source="images/jamfpro-install-mdm-profile.png" alt-text="Jamf Pro kaydı2" lightbox="images/jamfpro-install-mdm-profile.png":::

3. JAMF'den indirmelere **izin ver'i** seçin.

   :::image type="content" source="images/jamfpro-download.png" alt-text="Jamf Pro kaydı3" lightbox="images/jamfpro-download.png":::

4. MDM Profili yüklemesine devam etmek için **Devam'ı** seçin.

   :::image type="content" source="images/jamfpro-install-mdm.png" alt-text="Jamf Pro kaydı4" lightbox="images/jamfpro-install-mdm.png":::

5. MDM Profilini yüklemek için **Devam'ı** seçin.

   :::image type="content" source="images/jamfpro-mdm-unverified.png" alt-text="Jamf Pro kaydı5" lightbox="images/jamfpro-mdm-unverified.png":::

6. Yapılandırmayı tamamlamak için **Devam'ı**  seçin.

   :::image type="content" source="images/jamfpro-mdm-profile.png" alt-text="Jamf Pro kaydı6" lightbox="images/jamfpro-mdm-profile.png":::
