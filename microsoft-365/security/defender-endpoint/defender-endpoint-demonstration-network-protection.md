---
title: ağ koruması tanıtımlarını Uç Nokta için Microsoft Defender
description: Ağ korumasının, çalışanların İnternet'te kimlik avı dolandırıcılığı, açıklardan yararlanma ve diğer kötü amaçlı içeriğe ev sahipliği yapabilen tehlikeli etki alanlarına erişmek için herhangi bir uygulamayı kullanmasını nasıl önlediğini gösterir.
keywords: ağ koruması, kimlik avı dolandırıcılığına karşı koruma, açıklardan yararlanmaya karşı koruma, kötü amaçlı içeriğe karşı koruma, tanıtım
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
ms.openlocfilehash: 200b390bfaac0777d6373ca5573a4118e580fe01
ms.sourcegitcommit: 4f8200453d347de677461f27eb5a3802ce5cc888
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68542683"
---
<!--- v-jweston resumes authorship and ms.authorship appx April-May 2023 ---> 

# <a name="network-protection-demonstrations"></a>Ağ koruma tanıtımları

Ağ Koruması, cihazlarınızın saldırı yüzeyini İnternet tabanlı olaylardan azaltmaya yardımcı olur. Çalışanların, İnternet'te kimlik avı dolandırıcılığı, açıklardan yararlanma ve diğer kötü amaçlı içeriğe ev sahipliği yapabilen tehlikeli etki alanlarına erişmek için herhangi bir uygulama kullanmasını engeller.

## <a name="scenario-requirements-and-setup"></a>Senaryo gereksinimleri ve kurulumu

- Windows 10 1709 derleme 16273
- Microsoft Defender Virüsten Koruma

## <a name="powershell-command"></a>PowerShell komutu

Set-MpPreference -EnableNetworkProtection Etkin

### <a name="states"></a>Devletleri
- Etkin = Blok modu (1)
- AuditMode = Denetim Modu (2)
- Devre Dışı = Kapalı (0)

## <a name="verify-configuration"></a>Yapılandırmayı doğrulama

Get-MpPreference

## <a name="scenario"></a>Senaryo

1. PowerShell komutunu kullanarak Ağ Koruması'nı açın: Set-MpPreference -EnableNetworkProtection Enabled
2. Seçtiğiniz tarayıcıyı (Microsoft Edge*'i değil) kullanarak [Ağ Koruması web sitesi testine](https://smartscreentestratings2.net/) gidin (Microsoft Edge'de bu güvenlik açığından (SmartScreen) korunmak için başka güvenlik önlemleri vardır). 

## <a name="expected-results"></a>Beklenen sonuçlar

Web sitesine gezinti engellenmelidir ve bir "Bağlantı engellendi" bildirimi görmeniz gerekir.

## <a name="clean-up"></a>Temizleme

Set-MpPreference -EnableNetworkProtection Devre Dışı

## <a name="see-also"></a>Ayrıca bkz.

[Ağ Koruması](network-protection.md)

[Uç Nokta için Microsoft Defender - tanıtım senaryoları](defender-endpoint-demonstrations.md)
