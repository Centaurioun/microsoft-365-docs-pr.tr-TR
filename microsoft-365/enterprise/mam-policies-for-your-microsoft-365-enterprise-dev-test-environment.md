---
title: Kurumsal test ortamınız için Microsoft 365'e yönelik cihaz uyumluluk ilkeleri
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Kurumsal test ortamınız için Microsoft 365'e Intune cihaz uyumluluk ilkeleri eklemek için bu Test Laboratuvarı Kılavuzu'nu kullanın.
ms.openlocfilehash: 6d75721bd8b4fa6e707111ffd383c20770da0cda
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178789"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Kurumsal test ortamınız için Microsoft 365'e yönelik cihaz uyumluluk ilkeleri

*Bu Test Laboratuvarı Kılavuzu yalnızca kurumsal test ortamları için Microsoft 365 için kullanılabilir.*

Bu makalede, kurumsal test ortamınız için Microsoft 365'e Windows 10 cihazlar ve Kurumlar için Microsoft 365 Uygulamaları için Intune cihaz uyumluluk ilkesinin nasıl ekleneceği açıklanır.

Intune cihaz uyumluluk ilkesi eklemek iki aşamayı içerir:
- [1. Aşama: Kurumsal test ortamı için Microsoft 365'inizi oluşturma](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2. Aşama: Windows 10 cihazlar için cihaz uyumluluk ilkesi oluşturma](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft bulutu için Test Laboratuvarı Kılavuzları.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Microsoft 365 kurumsal Test Laboratuvarı Kılavuzu yığınındaki tüm makalelere yönelik görsel bir harita için [, Kurumsal Test Laboratuvarı Kılavuz Yığını için Microsoft 365'e](../downloads/Microsoft365EnterpriseTLGStack.pdf) gidin.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1. Aşama: Kurumsal test ortamı için Microsoft 365'inizi oluşturma

MAM ilkelerini en düşük gereksinimlerle yalnızca basit bir şekilde yapılandırmak istiyorsanız [, Basit temel yapılandırma](lightweight-base-configuration-microsoft-365-enterprise.md) yönergelerini izleyin.
  
Mam ilkelerini sanal bir kuruluşta yapılandırmak istiyorsanız Doğrudan [kimlik doğrulaması](pass-through-auth-m365-ent-test-environment.md) bölümündeki yönergeleri izleyin.
  
> [!NOTE]
> Otomatik lisanslama ve grup üyeliğinin test edilmesi için İnternet'e bağlı bir sanal intranet ve bir Active Directory Domain Services (AD DS) ormanı için dizin eşitlemesi içeren sanal kurumsal test ortamı gerekmez. Burada, otomatik lisanslama ve grup üyeliğini test edebilmeniz ve tipik bir kuruluşu temsil eden bir ortamda denemeler yapabileceğiniz bir seçenek olarak sağlanır.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>2. Aşama: Windows 10 cihazlar için cihaz uyumluluk ilkesi oluşturma

Bu aşamada, Windows 10 cihazlar için bir cihaz uyumluluk ilkesi oluşturursunuz. Bu aşamada grup eklemek ve uyumluluk ilkesi oluşturmak için [Microsoft Intune ve Microsoft Endpoint Manager yönetim merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) kullanılır.

1. [Microsoft 365 yönetim merkezi](https://admin.microsoft.com) gidin, genel yönetici hesabınızla Microsoft 365 test laboratuvarı aboneliğinizde oturum açın ve <a href="https://go.microsoft.com/fwlink/?linkid=2109431" target="_blank">Endpoint Manager yönetim merkezini</a> seçin.

    **Henüz cihaz yönetimini etkinleştirmediğinize** benzer bir ileti gösteriliyorsa, MDM yetkilisi olarak Intune seçin. Belirli adımlar için bkz. [Mobil cihaz yönetimi yetkilisini ayarlama](/mem/intune/fundamentals/mdm-authority-set).

    Endpoint Manager yönetim merkezi, cihaz yönetimine ve uygulama yönetimine odaklanır. Bu yönetim merkezi turu için bkz[. Öğretici: Microsoft Endpoint Manager'de izlenecek yol Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. **Gruplar'da**, **Atanan** üyelik türüne sahip **Yönetilen Windows 10 cihaz kullanıcıları** adlı yeni bir **Microsoft 365** veya **Güvenlik** grubu ekleyin. Sonraki adımlarda uyumluluk ilkenizi bu gruba atayacaksınız. 

    Belirli adımlar ve **Microsoft 365** veya **Güvenlik** grupları hakkında bilgi için bkz. [Kullanıcıları ve cihazları düzenlemek için grup ekleme](/mem/intune/fundamentals/groups-add).

3. **Cihazlar'da** bir Windows 10 uyumluluk ilkesi oluşturun. Bu ilkeyi, oluşturduğunuz **Yönetilen Windows 10 cihaz kullanıcıları** grubuna atayın.

    İlkenizde basit parolaları engelleyebilir, güvenlik duvarı gerektirebilir, Microsoft Defender Kötü amaçlı yazılımdan koruma hizmetinin çalışmasını gerektirebilir ve daha fazlasını yapabilirsiniz. Uyumluluk ilkesi genellikle temel ayarları veya her cihazın sahip olması gereken minimum ayarları içerir.

    Belirli adımlar ve yapılandırabileceğiniz kullanılabilir uyumluluk ayarları hakkında bilgi için bkz. [Yönettiğiniz cihazlar için kurallar ayarlamak için uyumluluk ilkelerini kullanma](/mem/intune/protect/device-compliance-get-started).

İşiniz bittiğinde, **Yönetilen Windows 10 cihaz kullanıcıları** grubundaki üyeleri test eden bir cihaz uyumluluk ilkeniz vardır.
  
## <a name="next-step"></a>Sonraki adım

Test ortamınızdaki ek [mobil cihaz yönetimi](m365-enterprise-test-lab-guides.md#mobile-device-management) özelliklerini ve özelliklerini keşfedin.

## <a name="see-also"></a>Ayrıca bkz.

[Kurumsal Test Laboratuvarı Kılavuzları için Microsoft 365](m365-enterprise-test-lab-guides.md).
  
[Kurumsal test ortamınız için Microsoft 365'e iOS ve Android cihazları kaydetme](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
