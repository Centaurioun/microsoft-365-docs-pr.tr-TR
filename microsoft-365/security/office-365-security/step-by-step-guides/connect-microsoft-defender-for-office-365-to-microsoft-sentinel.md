---
title: Office 365 için Microsoft Defender'ı Microsoft Sentinel'e bağlayın
description: Office 365 için Microsoft Defender Sentinel'e bağlama adımları. Güvenlik olayı dahil olmak üzere Office 365 için Microsoft Defender verilerinizi (*ve* Microsoft 365 Defender paketinin geri kalanındaki verileri) tek bir cam bölmesi için Microsoft Sentinel'e ekleyin.
search.product: ''
ms.service: microsoft-365-security
ms.subservice: mdo
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
search.appverid: met150
ms.openlocfilehash: 019dd5ff70dae2041955882ed0c63b13f20015cd
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799318"
---
# <a name="connect-microsoft-defender-for-office-365-to-microsoft-sentinel"></a>Office 365 için Microsoft Defender'ı Microsoft Sentinel'e bağlayın

Olaylar da dahil olmak üzere Office 365 için Microsoft Defender verilerinizi (*ve* Microsoft 365 Defender paketinin geri kalanındaki verileri) Microsoft Sentinel'e alabilirsiniz.

Diğer Microsoft 365 kaynaklarından alınan verilerle birlikte zengin güvenlik bilgileri olay yönetiminden (SIEM), olayların ve uyarıların eşitlenmesinden ve gelişmiş avcılıktan yararlanın.

> [!IMPORTANT]
> Microsoft 365 Defender bağlayıcısı şu anda **ÖNİzLEME aşamasındadır**. Beta, önizleme aşamasında olan veya henüz genel kullanıma sunulmamış Azure özellikleri için geçerli olan ek yasal koşullar için Bkz. Microsoft Azure Önizlemeleri için Ek Kullanım Koşulları.>

## <a name="what-you-will-need"></a>İhtiyacınız olan şey
- Plan 2 veya üzerini Office 365 için Microsoft Defender. (E5 planlarında bulunur)
- Microsoft Sentinel [Hızlı Başlangıç kılavuzu](/azure/sentinel/quickstart-onboard).
- Yeterli izinler (M365'te Güvenlik Yöneticisi & Sentinel'de Okuma/Yazma izinleri).

## <a name="add-the-microsoft-365-defender-connector"></a>Microsoft 365 Defender Bağlayıcısı'nı ekleme
1. [Azure Portal'da oturum açın](https://portal.azure.com) ve **Microsoft Sentinel'e** gidin > Microsoft 365 Defender ile tümleştirmek için ilgili çalışma alanını seçin
    1. Sol taraftaki gezinti menüsünde **Yapılandırma** > **Veri bağlayıcıları'nı** seçin.
2. Sayfa yüklendiğinde Microsoft 365 Defender **arayın** **ve Microsoft 365 Defender (önizleme) bağlayıcısını seçin**.
3. Sağ taraftaki açılır listede **Bağlayıcı Sayfasını Aç'ı** seçin.
4. Yüklenen sayfanın **Yapılandırma** bölümünde **Olayları & uyarıları bağla'yı** seçerek Bu ürünler için tüm Microsoft olay oluşturma kurallarını kapat seçeneğini işaretleyin.
5. Sayfayı kaydırarak sayfanın **Olayları bağlama** bölümünde **Office 365 için Microsoft Defender**. **EmailEvents, EmailUrlInfo, EmailAttachmentInfo & EmailPostDeliveryEvents'i** ve ardından sayfanın en altındaki **Değişiklikleri Uygula'yı** seçin. (Bu adım sırasında yararlı ve uygulanabilirse diğer Defender ürünlerinden tabloları seçin.)

## <a name="next-steps"></a>Sonraki Adımlar

Yöneticiler artık Microsoft Sentinel'de olayları, uyarıları ve ham verileri görebilir ve microsoft Defender'daki mevcut ve yeni verileri özetleyerek *gelişmiş tehdit avcılığı* için bu verileri kullanabilir.

## <a name="more-information"></a>Daha Fazla Bilgi

[Microsoft 365 Defender verilerini Microsoft Sentinel |'a bağlama Microsoft Docs](/azure/sentinel/connect-microsoft-365-defender?tabs=MDE)

[Microsoft Teams'i Microsoft Sentinel'e bağlama](/microsoftteams/teams-sentinel-guide)
