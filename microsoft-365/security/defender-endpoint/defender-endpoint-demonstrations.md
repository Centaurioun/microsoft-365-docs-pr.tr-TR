---
title: Uç Nokta için Microsoft Defender gösterim senaryoları
description: Çalıştırabileceğiniz Uç Nokta için Microsoft Defender tanıtım senaryolarını listeler.
keywords: tanıtım, Uç Nokta için Microsoft Defender gösterimi, Kötü Amaçlı Yazılımdan Koruma, Bulut tabanlı koruma, İlk Bakışta Engelle (BAFS), İstenmeyebilecek uygulamalar (PUA), Microsoft güvenlik zekası VDI, VDI güvenliği, Saldırı Yüzeyi Azaltma (ASR) kuralları gösterimi, Kontrollü klasör erişimi gösterimi, Exploit Protection, Ağ Koruması, Microsoft Defender SmartScreen, edge SmartScreen,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 1eb7b12c77231a475d745903d1b665da77430cf0
ms.sourcegitcommit: 4f8200453d347de677461f27eb5a3802ce5cc888
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68542947"
---
<!--- v-jweston resumes authorship and ms.authorship appx April-May 2023 ---> 

# <a name="microsoft-defender-for-endpoint---demonstration-scenarios"></a>Uç Nokta için Microsoft Defender - tanıtım senaryoları

Aşağıdaki tanıtım senaryoları, Windows'ta Uç Nokta için Microsoft Defender özellikleri hakkında bilgi edinmenize yardımcı olur (Mac ve Linux kapsam dışındadır). Aşağıdaki Uç Nokta için Microsoft Defender koruma alanları için gösterim senaryoları sağlanır:

:::image type="content" source="images/microsoft-defender-for-endpoint-cloud-protection.png" alt-text="Bu koleksiyonda ele alınan Uç Nokta için Microsoft Defender tanıtım senaryolarının alanlarını gösterir" lightbox="images/microsoft-defender-for-endpoint-cloud-protection.png":::

- Saldırı yüzeyi koruması (ASR)
- Yeni Nesil Koruma (NGP)
- Uç nokta algılama ve yanıt (EDR)

> [!NOTE]
> Bu koleksiyonda sağlanan örnek dosyaların veya _şüpheli_ bağlantıların hiçbiri aslında kötü amaçlı değil; tüm bağlantılar ve tanıtım dosyaları zararsızdır.
>
> [Microsoft Defender Virüsten Koruma belgelerini](next-generation-protection.md) okumanızı ve [Değerlendirme kılavuzunu](evaluate-microsoft-defender-antivirus.md) indirmenizi öneririz.

## <a name="demonstrations"></a>Gösteri

Aşağıdaki tabloda kullanılabilir gösterimler, ilişkili koruma alanlarıyla birlikte alfabetik olarak listelemektedir.

| # | Tanıtım adı | Koruma alanı | Açıklama |
|:--|:---|:---|:---|
| 1 | [Uygulama saygınlığı tanıtımı](defender-endpoint-demonstration-app-reputation.md) | Ngp | Microsoft Edge kullanarak tanıtım senaryolarını görmek için uygulama saygınlığı sayfasına gidin. |
| 2 | [Saldırı yüzeyi azaltma kuralları tanıtımları](defender-endpoint-demonstration-attack-surface-reduction-rules.md) | Asr | Her ASR kuralını tetikleyen örnek dosyaları indirin. |
| 3 | [İlk Bakışta Engelle (BAFS) gösterimi](defender-endpoint-demonstration-block-at-first-sight-bafs.md) | Ngp | Microsoft Defender Virüsten Koruma'daki BAFS özelliğiyle, yeni bulunan dosyalar analiz edilir ve gerekirse engellenir. |
| 4 | [Bulut tabanlı koruma tanıtımı](defender-endpoint-demonstration-cloud-delivered-protection.md) | Ngp |  Bilgisayarınızda bulut tabanlı korumanın düzgün çalıştığını onaylayın. |
| 5 | [Denetimli klasör erişimi (CFA) gösterimi (blok betiği)](defender-endpoint-demonstration-controlled-folder-access-test-tool.md) | Asr | CFA test aracını indirin. |
| 6 | [Denetimli klasör erişimi (CFA) tanıtımları (fidye yazılımını engelle)](defender-endpoint-demonstration-controlled-folder-access.md) | Asr | CFA fidye yazılımı korumasını tetikleme amacıyla örnek bir dosya indirin ve yürütin. |
| 7 | [Açıklardan yararlanma koruması (EP) tanıtımları](defender-endpoint-demonstration-exploit-protection.md) | Asr | Özel yararlanma koruması ayarlarını uygulayın. |
| 8 | [Ağ koruma tanıtımları](defender-endpoint-demonstration-network-protection.md) | Asr | Ağ korumasını tetikleme için şüpheli bir URL'ye gidin. |
| 9 | [İstenmeyebilecek uygulamalar (PUA) gösterimi](defender-endpoint-demonstration-potentially-unwanted-applications.md) | Ngp | Sahte (güvenli) bir PUA dosyası indirerek ağınızda istenmeyebilecek uygulamaların (PUA) engellendiğini onaylayın. |
| 10 | [URL saygınlığı tanıtımları](defender-endpoint-demonstration-smartscreen-url-reputation.md) | Ngp | Microsoft Edge kullanarak tanıtım senaryolarını görmek için URL Saygınlığı sayfasına gidin. |

## <a name="see-also"></a>Ayrıca bkz.

[Saldırı yüzeyi koruması \( ASR'ye\) genel bakış](overview-attack-surface-reduction.md)
[Test saldırısı yüzey azaltma kuralları](attack-surface-reduction-rules-deployment-test.md)
[Yeni Nesil Koruma \(NGP'ye\) genel bakış](next-generation-protection.md)
[Uç nokta algılama ve yanıt \(EDR'ye\) genel bakış](overview-endpoint-detection-response.md)

[Uç Nokta için Microsoft Defender güvenlik blogu](https://www.microsoft.com/security/blog/microsoft-defender-for-endpoint/)
