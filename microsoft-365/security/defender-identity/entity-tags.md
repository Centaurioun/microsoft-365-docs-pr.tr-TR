---
title: Microsoft 365 Defender'da varlık etiketlerini Kimlik için Microsoft Defender
description: Microsoft 365 Defender'da Kimlik için Microsoft Defender varlık etiketlerinin nasıl uygulanacağını öğrenin
ms.date: 06/08/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: m365-security
search.appverid: met150
ms.openlocfilehash: 70f35603d653f0f6e3f6493a90fd51d357207c60
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68059404"
---
# <a name="defender-for-identity-entity-tags-in-microsoft-365-defender"></a>Microsoft 365 Defender'de Kimlik için Defender varlık etiketleri

**Şunlar için geçerlidir:**

- Microsoft 365 Defender
- Kimlik için Microsoft Defender

Bu makalede[, Kimlik için Microsoft Defender](/defender-for-identity) varlık etiketlerinin [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center) nasıl uygulanacağı açıklanmaktadır.

>[!IMPORTANT]
>Microsoft 365 Defender ile yakınsama kapsamında bazı seçenekler ve ayrıntılar Kimlik için Defender portalındaki konumlarından değişti. Hem tanıdık hem de yeni özellikleri nerede bulabileceğinizi öğrenmek için lütfen aşağıdaki ayrıntıları okuyun.

## <a name="entity-tags"></a>Varlık etiketleri

Microsoft 365 Defender'da üç tür Kimlik için Defender varlık etiketi ayarlayabilirsiniz: **Hassas etiketler**, **Honeytoken etiketleri** ve **Exchange sunucusu etiketleri**.

Bu etiketleri ayarlamak için <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> **Ayarlar'a** ve ardından **Kimlikler'e** gidin.

:::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="Ayarlar sayfasındaki Ad sütununun altındaki Kimlikler seçeneği" lightbox="../../media/defender-identity/settings-identities.png":::

Etiket ayarları **Varlık etiketleri** altında görünür.

:::image type="content" source="../../media/defender-identity/tag-settings.png" alt-text="Varlık etiketleri bölmesi" lightbox="../../media/defender-identity/tag-settings.png":::

Her etiket türünü ayarlamak için aşağıdaki yönergeleri izleyin.

## <a name="sensitive--tags"></a>Hassas etiketler

**Hassas etiketi**, yüksek değerli varlıkları tanımlamak için kullanılır. Yanal hareket yolu da varlığın duyarlılık durumuna bağlıdır. Bazı varlıklar, Kimlik için Defender tarafından otomatik olarak hassas olarak kabul edilir. Bu varlıkların listesi için bkz [. Hassas varlıklar](/defender-for-identity/manage-sensitive-honeytoken-accounts#sensitive-entities).

Ayrıca kullanıcıları, cihazları veya grupları hassas olarak el ile etiketleyebilirsiniz.

1. **Hassas'ı** seçin. Ardından mevcut hassas **Kullanıcılar**, **Cihazlar** ve **Gruplar'ı** görürsünüz.

   :::image type="content" source="../../media/defender-identity/sensitive-entities.png" alt-text="Hassas varlıklar menü öğesindeki Cihazlar sekmesi" lightbox="../../media/defender-identity/sensitive-entities.png":::

1. Her kategorinin altında **Etiket...** öğesini seçerek bu varlık türünü etiketleyin. Örneğin, **Gruplar'ın** altında **Grupları etiketle'yi seçin.** Etiketlemek için seçebileceğiniz grupları içeren bir bölme açılır. Bir grubu aramak için, arama kutusuna grubun adını girin.

   :::image type="content" source="../../media/defender-identity/add-groups.png" alt-text="Grup ekleme seçeneği" lightbox="../../media/defender-identity/add-groups.png":::

1. Grubunuzu seçin ve **Seçim ekle'ye tıklayın.**

   :::image type="content" source="../../media/defender-identity/add-selection.png" alt-text="Seçim ekle seçeneği" lightbox="../../media/defender-identity/add-selection.png":::

## <a name="honeytoken-tags"></a>Honeytoken etiketleri

Honeytoken varlıkları, kötü amaçlı aktörler için tuzak olarak kullanılır. Bu honeytoken varlıklarıyla ilişkili herhangi bir kimlik doğrulaması bir uyarı tetikler.

Kullanıcıları veya cihazları **Honeytoken** etiketiyle hassas hesapları etiketlediğiniz gibi etiketleyebilirsiniz.

1. **Honeytoken'i** seçin. Ardından mevcut honeytoken **Kullanıcıları** ve **Cihazları'nı** görürsünüz.

    ![Honeytoken varlıkları.](../../media/defender-identity/honeytoken-entities.png)

1. Her kategorinin altında **Etiket...** öğesini seçerek bu varlık türünü etiketleyin. Örneğin, **Kullanıcılar'ın** altında **Kullanıcıları etiketle'yi seçin.** Etiketlemek için seçebileceğiniz grupları içeren bir bölme açılır. Bir grubu aramak için, arama kutusuna grubun adını girin.

   :::image type="content" source="../../media/defender-identity/add-users.png" alt-text="Kullanıcı ekleme seçeneği" lightbox="../../media/defender-identity/add-users.png":::

1. Kullanıcınızı seçin ve **Seçim ekle'ye tıklayın.**

   :::image type="content" source="../../media/defender-identity/add-selected-user.png" alt-text="Seçili kullanıcıyı ekleme seçeneği" lightbox="../../media/defender-identity/add-selected-user.png":::

## <a name="exchange-server-tags"></a>Exchange sunucusu etiketleri

Kimlik için Defender, Exchange sunucularını yüksek değerli varlıklar olarak kabul eder ve bunları otomatik olarak **Hassas** olarak etiketler. Ayrıca cihazları Exchange sunucuları olarak el ile etiketleyebilirsiniz.

1. **Exchange sunucusu'nu** seçin. Ardından **, Exchange sunucusu** etiketiyle etiketlenmiş mevcut cihazları görürsünüz.

   :::image type="content" source="../../media/defender-identity/exchange-servers.png" alt-text="Exchange sunucusu menü öğesi" lightbox="../../media/defender-identity/exchange-servers.png":::

1. Bir cihazı Exchange sunucusu olarak etiketlemek için **Cihazları etiketle'yi** seçin.  Etiketlemeyi seçebileceğiniz cihazlarla birlikte bir bölme açılır. Bir cihazı aramak için, arama kutusuna cihazın adını girin.

   :::image type="content" source="../../media/defender-identity/add-devices.png" alt-text="Cihaz ekleme seçeneği" lightbox="../../media/defender-identity/add-devices.png":::

1. Cihazınızı seçin ve **Seçim ekle'ye tıklayın.**

   :::image type="content" source="../../media/defender-identity/select-device.png" alt-text="Cihaz seçimi" lightbox="../../media/defender-identity/select-device.png":::

## <a name="see-also"></a>Ayrıca bkz.

- [Kimlik için Defender güvenlik uyarılarını yönetme](manage-security-alerts.md)
