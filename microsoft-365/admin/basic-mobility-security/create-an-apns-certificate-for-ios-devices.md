---
title: iOS cihazları için APN sertifikası oluşturma
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Basic Mobility ve Security'de iPad ve iPhone gibi iOS cihazlarını yönetmek için bir APNs sertifikası oluşturarak başlayın.
ms.openlocfilehash: b85976c2c6f07672635b6474e036accd2b3789d7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68166867"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>iOS cihazları için APN sertifikası oluşturma

Basic Mobility ve Security'de iPad ve iPhone gibi iOS cihazlarını yönetmek için bir APNs sertifikası oluşturun.

1. Genel yönetici hesabınızla Microsoft 365'te oturum açın.

1. [Microsoft 365 yönetim merkezi](https://portal.office.com/adminportal/home?#/MifoDevices) gidin ve **iOS için APNs Sertifikası'nı** seçin.

1. Apple Anında İletme Bildirimi Sertifika Ayarları sayfasında **İleri'yi** seçin.

1. CSR dosyanızı indirin'i seçin ve sertifika imzalama isteğini bilgisayarınızda anımsayacağınız bir yere kaydedin. **İleri**'yi seçin.

1. APNs sertifikası oluştur sayfasında:

    1. Apple Anında İletme Sertifikaları Portalı'nı açmak için Apple APNS Portalı'nı seçin.

    2. Apple Kimliği ile oturum açın.

       > [!IMPORTANT]
       > Hesabı yöneten kullanıcı ayrılsa bile kuruluşunuzda kalacak bir e-posta hesabıyla ilişkilendirilmiş bir şirket Apple Kimliği kullanın. Sertifikayı yenileme zamanı geldiğinde aynı kimliği kullanmanız gerektiğinden bu kimliği kaydedin.

    3. **Sertifika Oluştur'u** seçin ve Kullanım Koşulları'nı kabul edin.

    4. Microsoft 365'ten bilgisayarınıza indirdiğiniz sertifika imzalama isteğine göz atın ve **Karşıya Yükle'yi** seçin.

       Apple Anında İletme Sertifikası Portalı tarafından oluşturulan APNs sertifikasını bilgisayarınıza indirin.

       > [!TIP]
       > Sertifikayı indirirken sorun yaşıyorsanız tarayıcınızı yenileyin.

1. Microsoft 365'e Geri dön ve **İleri'yi** seçerek **APNS sertifikasını karşıya yükle** sayfasına gidin.

1. Apple Anında İletme Sertifikaları Portalı'ndan indirdiğiniz APN sertifikasına göz atın.

1. **Bitir'i** seçin.

Kurulumu tamamlamak için Güvenlik & Uyumluluk Merkezi \> **Güvenlik ilkeleri** \> **Cihaz yönetimi** \> **Ayarları yönet'e** geri dönün.
