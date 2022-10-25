---
title: İş için Microsoft Defender sunucuları alma
description: Şu anda önizleme aşamasında olan İş için Microsoft Defender sunucuları nasıl edinmeyi öğrenin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: none
ms.date: 08/11/2022
ms.collection:
- SMB
- m365-security
- tier1
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.openlocfilehash: 111b3e7cd4de996b6c263312acf4368d872e7a50
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687536"
---
# <a name="how-to-get-microsoft-defender-for-business-servers-preview"></a>İş için Microsoft Defender sunucuları nasıl alınır (önizleme)

> [!IMPORTANT]
> Windows Server veya Linux Server örneğini eklemeyi planlıyorsanız, İş için Microsoft Defender sunucuları (önizleme) gibi ek bir lisansa ihtiyacınız olacaktır. Alternatif olarak [Sunucular için Microsoft Defender](/azure/defender-for-cloud/defender-for-servers-introduction) kullanabilirsiniz; ancak Sunucular için Defender Plan 1 veya Plan 2 gibi bir kurumsal plan eklediğinizde İş için Defender deneyiminiz değişebilir. Daha fazla bilgi edinmek için bkz. [Microsoft uç nokta güvenlik aboneliklerinin bir karışımına sahipsem ne olur?](mdb-faq.yml#what-happens-if-i-have-a-mix-of-microsoft-endpoint-security-subscriptions) ve [Cihazları İş için Microsoft Defender ekleme](mdb-onboard-devices.md).

İş için Microsoft Defender sunucuları (önizleme), Windows Server veya Linux Server çalıştıran bir cihazı İş için Defender'a veya Microsoft 365 İş Ekstra eklemenizi sağlar. İş için Microsoft Defender sunucuları lisansı genel kullanıma sunulduğunda, her sunucu örneği için bir lisans gerekir.

**İş için Microsoft Defender sunucuları alma (önizleme) şöyle yapılır**:

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın. 

2. Önizleme ayarlarını açın. 

   1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları** \> **Gelişmiş özellikler** \> **Önizleme özellikleri'ni** seçin. 
   2. Ayarı **Açık** duruma getirin ve ardından **Tercihleri kaydet'i** seçin.

3. Windows Server için zorlama kapsamını açın. 

   1. **Ayarlar** \> **Uç Noktaları** \> **Yapılandırma yönetimi** \> **Zorlama kapsamı'na** gidin. 
   2. **MEM'den güvenlik yapılandırma ayarlarını zorunlu kılmak için MDE kullan'ı** seçin, **Windows Server'ı** ve ardından **Kaydet'i** seçin.

4. Cihazları İş için Microsoft Defender ekleme konusunda Windows Server ve Linux Server [yönergelerini](mdb-onboard-devices.md) izlemeye devam edin.

> [!IMPORTANT]
> İş için Microsoft Defender sunucuları şu anda önizleme aşamasındadır. Genel kullanıma sunulduğunda (GA), Microsoft 365 İş Ekstra ve İş için Defender'ın tek başına sürümüne bir eklenti olarak sunulacaktır. GA'da İş için Microsoft Defender sunucuların fiyatı sunucu örneği başına 3 ABD doları olacaktır.

## <a name="see-also"></a>Ayrıca bkz.

- [Deneme kullanım kılavuzuna bakın: İş için Microsoft Defender](trial-playbook-defender-business.md).
- [İş için Microsoft Defender'da kurulum sihirbazını kullanın](mdb-use-wizard.md).
- [bkz. İş için Defender'ın kurulum ve yapılandırma işlemi](mdb-setup-configuration.md).
- [İş için Defender için nasıl yardım ve destek alabileceğinizi öğrenin](mdb-get-help.md) (yardıma ihtiyacınız olması durumunda).