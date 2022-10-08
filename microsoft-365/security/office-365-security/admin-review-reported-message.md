---
title: Bildirilen iletiler için yönetici incelemesi
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
ms.collection:
- m365-security
ms.custom: ''
description: Bildirilen iletileri gözden geçirmeyi ve kullanıcılarınıza geri bildirim vermeyi öğrenin.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 4fbb592512eb9bc872a5c721f48e43ec5ad25a2a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066838"
---
# <a name="admin-review-for-reported-messages"></a>Bildirilen iletiler için yönetici incelemesi

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online posta kutuları ve Office 365 için Microsoft Defender sahip Microsoft 365 kuruluşlarında, yöneticiler artık bildirilen iletileri gözden geçirdikten sonra son kullanıcılara şablonlu iletiler gönderebilir. Şablonlar, kuruluşunuz için ve yöneticinizin kararına göre özelleştirilebilir.

Bu özellik kullanıcılarınıza geri bildirim sağlamak üzere tasarlanmıştır ancak sistemdeki iletilerin kararlarını değiştirmez. Microsoft'un filtrelerini güncelleştirmesine ve iyileştirmesine yardımcı olmak için, [Yönetici gönderimi](admin-submission.md) kullanarak analiz için ileti göndermeniz gerekir.

Yalnızca [iletinin hatalı pozitif veya hatalı negatif](report-false-positives-and-false-negatives.md) olarak bildirilmesi durumunda kullanıcıları gözden geçirme sonuçlarını işaretleyebilir ve bilgilendirebilirsiniz.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Microsoft 365 Defender portalını adresinde <https://security.microsoft.com>açarsınız. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

- Kullanıcı gönderimleri yapılandırmasını değiştirmek için aşağıdaki rol gruplarından birinin üyesi olmanız gerekir:
  - [Microsoft 365 Defender portalında](permissions-microsoft-365-security-center.md) Kuruluş Yönetimi veya Güvenlik Yöneticisi.
  - [Exchange Online'de](/Exchange/permissions-exo/permissions-exo#role-groups) Kuruluş Yönetimi.

- Ayrıca Exchange Online PowerShell'e de erişmeniz gerekir. Kullanmaya çalıştığınız hesabın Exchange Online PowerShell'e erişimi yoksa etki *alanınızda e-posta adresi belirtin* hatasını alırsınız. Exchange Online PowerShell'e erişimi etkinleştirme veya devre dışı bırakma hakkında daha fazla bilgi için aşağıdaki konulara bakın:
  - [Exchange Online PowerShell'e erişimi etkinleştirme veya devre dışı bırakma](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Exchange Online'da İstemci Erişim Kuralları](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="notify-users-from-within-the-portal"></a>Portaldan kullanıcılara bildirme

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, **Email & işbirliği** \> **Gönderimleri** sayfasındaki **Gönderimler** sayfasına gidin. Doğrudan **Gönderimler** sayfasına gitmek için kullanın <https://security.microsoft.com/reportsubmission>.

2. **Kullanıcı tarafından bildirilen iletiler'e** tıklayın ve işaretlemek ve bildirmek istediğiniz iletiyi seçin.

3. **Farklı işaretle ve bildir** açılan listesini seçin ve ardından **Tehdit bulunamadı**, **Kimlik Avı** veya **Gereksiz'i** seçin.

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/admin-review-send-message-from-portal.png" alt-text="Kullanıcı tarafından bildirilen iletilerin görüntülendiği sayfa" lightbox="../../media/admin-review-send-message-from-portal.png":::

Bildirilen ileti hatalı pozitif veya hatalı negatif olarak işaretlenir ve portalın içinden iletiyi bildiren kullanıcıyı bilgilendiren bir e-posta otomatik olarak gönderilir.

## <a name="customize-the-messages-used-to-notify-users"></a>Kullanıcıları bilgilendirmek için kullanılan iletileri özelleştirme

1. konumundaki Microsoft 365 Defender portalında<https://security.microsoft.com>, Email & **İşbirliği** \> **İlkeleri & Kurallar** \> **Tehdit ilkeleri** \> **Kullanıcı tarafından bildirilen ileti ayarlarının** **Diğerleri** bölümündeki Kullanıcı **gönderimleri** sayfasına gidin. Doğrudan **Kullanıcı gönderimleri** sayfasına gitmek için kullanın <https://security.microsoft.com/userSubmissionsReportMessage>.

2. **Kullanıcı gönderimleri** sayfasında, gönderenin görünen adını belirtmek istiyorsanız, **Yönetici gözden geçirme sonuçları** için Email bildirimleri bölümünün Altında **Gönderen olarak kullanılacak Office 365 e-posta adresini belirtin** kutusunu işaretleyin ve kullanmak istediğiniz adı girin. Outlook'ta görünür olacak e-posta adresi ve tüm yanıtlar oraya gider.

3. Şablonlardan herhangi birini özelleştirmek istiyorsanız, sayfanın alt kısmındaki **E-posta bildirimini özelleştir'e** tıklayın. Açılan açılır öğede yalnızca aşağıdakileri özelleştirebilirsiniz:

    - Kimlik Avı
    - Önemsiz
    - Tehdit bulunamadı
    - Altbilgi

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/admin-review-customize-message.png" alt-text="Onayı özelleştir ileti sayfası" lightbox="../../media/admin-review-customize-message.png":::

4. Bitirdiğinizde, **Kaydet**'i tıklatın. Bu değerleri temizlemek için **Kullanıcı gönderimleri** sayfasında **At'a** tıklayın.
