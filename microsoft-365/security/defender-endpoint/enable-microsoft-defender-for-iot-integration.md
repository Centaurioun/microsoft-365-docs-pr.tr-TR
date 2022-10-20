---
title: Uç Nokta için Microsoft Defender ile IoT için Microsoft Defender ekleme
description: IoT cihazlarına odaklanan görünürlük ve güvenlik değerlendirmeleri elde etmek için IoT için Microsoft Defender ekleyin.
keywords: siem bağlayıcısını, siem'i, bağlayıcıyı, güvenlik bilgilerini ve olayları etkinleştirme
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 6f5c91ff837213f0824fbc2f2b149430ea9b3266
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68643019"
---
# <a name="onboard-with-microsoft-defender-for-iot"></a>IoT için Microsoft Defender ile ekleme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender P2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Uç Nokta için Microsoft Defender artık IoT için Microsoft Defender ile sorunsuz bir şekilde tümleştirildi. Bu tümleştirme, IoT için Defender tarafından sağlanan aracısız izleme özellikleriyle cihaz bulma özelliklerinizi genişletir. IoT için Defender tümleştirmesi, ağınızdaki İnternet Üzerinden Ses Protokolü (VoIP) cihazları, yazıcılar ve kameralar gibi kurumsal IoT cihazlarının bulunmasına, tanımlanmasına ve güvenliğinin sağlanmasına yardımcı olmak için daha fazla görünürlük sağlar.

Bu, kuruluşların tüm IoT ve Operasyonel Teknoloji (OT) altyapılarının güvenliğini sağlayan tek bir tümleşik çözümden yararlanmasına olanak tanır. Daha fazla bilgi için bkz [. Kurumsal IoT ağ koruması](/azure/defender-for-iot/organizations/overview-eiot).

IoT için Defender tümleştirmesi, bt cihazlarınızın (iş istasyonları, sunucular ve mobil) yanı sıra tüm OT/IoT envanterinizin tek bir birleşik görünümünü sunar. IoT için Defender'a eklenen müşteriler, IoT cihazları için uyarılar, güvenlik açıkları ve güvenlik önerileri hakkında da bilgi edinecektir.

## <a name="prerequisites"></a>Önkoşullar

Uç Nokta için Defender tümleştirmenizin ayarlarını değiştirmek için kullanıcının aşağıdaki rollere sahip olması gerekir:

- Azure Active Directory'de Kiracı Genel Yöneticisi
- IoT tümleştirmesi için Microsoft Defender kullanılacak Azure aboneliğinin Güvenlik Yöneticisi

## <a name="onboard-a-defender-for-iot-plan"></a>IoT için Defender planı ekleme

1. Portalın gezinti bölmesinde [https://security.microsoft.com](https://security.microsoft.com/) **Ayarlar** \> **Cihaz bulma** \> **Kurumsal IoT'yi** seçin.

2. Planınız için aşağıdaki seçenekleri belirleyin:

   - Azure Active Directory kiracınızda plan eklemek istediğiniz kullanılabilir abonelikler listesinden Azure aboneliğini seçin.

   - Aylık veya yıllık taahhüt ya da deneme sürümü olmak üzere bir fiyatlandırma planı seçin. IoT için Microsoft Defender, değerlendirme amacıyla ilk 1.000 cihaz için 30 günlük ücretsiz deneme sağlar.

      Daha fazla bilgi [için IoT fiyatlandırması Microsoft Defender sayfasına](https://azure.microsoft.com/pricing/details/iot-defender/) bakın.

   - İzlemek istediğiniz kaydedilmiş cihaz sayısını seçin. Bir deneme sürümü seçtiyseniz, varsayılan olarak 1000 cihazınız olduğundan bu bölüm görünmez.

3. **Hüküm ve koşulları** kabul edin ve **Kaydet'i** seçin.

> [!NOTE]
> Kurumsal IoT ağ algılayıcısı ayarlama işlemi şu anda genel önizleme aşamasındadır. Daha fazla bilgi için bkz. [Paylaşılan cihaz envanteri](#shared-device-inventory).

## <a name="managing-your-iot-devices"></a>IoT cihazlarınızı yönetme

[ioT cihazlarınızı Microsoft 365 Defender portalında](https://security.microsoft.com/) görüntülemek ve yönetmek için **Uç Noktalar** gezinti menüsünden **Cihaz envanterine** gidin ve **IoT cihazları** sekmesini seçin.

IoT için Defender'da cihazları görüntüleme hakkında bilgi için bkz. [IoT cihazlarınızı kuruluşlar için cihaz envanteriyle yönetme](/azure/defender-for-iot/organizations/how-to-manage-device-inventory-for-organizations).

## <a name="view-devices-alerts-recommendations-and-vulnerabilities"></a>Cihazları, uyarıları, önerileri ve güvenlik açıklarını görüntüleme

IoT için Defender planına eklendikten sonra aşağıdaki konumlarda algılanan verileri ve güvenlik değerlendirmelerini görüntüleyin:

- Uç Nokta için Defender'da veya IoT için Defender'da cihaz verilerini görüntüleme
- [Microsoft 365 Defender portalında](https://security.microsoft.com) [uyarıları](alerts-queue-endpoint-detection-response.md), [önerileri](../defender-vulnerability-management/tvm-security-recommendation.md) ve [güvenlik açıklarını](../defender-vulnerability-management/tvm-weaknesses.md) görüntüleyin.

### <a name="shared-device-inventory"></a>Paylaşılan cihaz envanteri

Uç Nokta için Defender müşterileri, kurumsal ağın daha önce Uç Nokta için Defender kapsamında olmayan ek IoT segmentlerine daha fazla görünürlük elde etmek için Kurumsal IoT ağ algılayıcısını da (şu anda **Genel Önizleme'de**) ayarlayabilir. Kurumsal IoT ağ algılayıcısı ayarlayan müşteriler, bulunan tüm cihazları Uç Nokta için Defender veya IoT için Defender'daki **Cihaz envanterinde** görebilir.

Ağ algılayıcısı eklemek için portalın gezinti bölmesinde [https://security.microsoft.com](https://security.microsoft.com/) :

1. **Ayarlar** \> **Cihaz bulma** **Kurumsal IoT'yi** \> seçin
2. **Ağ algılayıcılarını ayarlama** bölümünde **IoT bağlantısı için Microsoft Defender** seçin

Bu sizi Azure portal algılayıcı kurulum işlemine getirir. Daha fazla bilgi için bkz. [Kurumsal IoT'yi kullanmaya başlama](/azure/defender-for-iot/organizations/tutorial-getting-started-eiot-sensor).

> [!IMPORTANT]
> Kurumsal IoT Ağ algılayıcısı ayarlama işlemi şu anda ÖNİzLEME aşamasındadır. Beta, önizleme aşamasında olan veya henüz genel kullanıma sunulmamış Azure özellikleri için geçerli olan ek yasal koşullar için [Bkz. Microsoft Azure Önizlemeleri için Ek Kullanım Koşulları](https://azure.microsoft.com/support/legal/preview-supplemental-terms/) .

## <a name="cancel-your-defender-for-iot-plan"></a>IoT için Defender planınızı iptal etme

Portaldaki Uç Nokta için Defender ayarları sayfasından [https://security.microsoft.com](https://security.microsoft.com/) IoT için Defender planınızı iptal edin. Planınızı iptal ettikten sonra tümleştirme durdurulur ve artık Uç Nokta için Defender'da güvenlik değerlendirmesi değeri alamaz veya IoT için Defender'da yeni cihazları algılamazsınız.

Plan iptali ve veri konusunda dikkat edilmesi gerekenler hakkında daha fazla bilgi [için ioT için Defender belgelerindeki IoT için Defender planını iptal etme](/azure/defender-for-iot/organizations/how-to-manage-subscriptions#cancel-a-defender-for-iot-plan-from-a-subscription) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

- [Cihaz keşfine genel bakış](configure-device-discovery.md)
- [Cihaz keşfi hakkında SSS](device-discovery-faq.md)
