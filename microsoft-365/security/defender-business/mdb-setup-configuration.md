---
title: İş için Microsoft Defender ayarlama ve yapılandırma
description: İş için Defender siber güvenlik çözümünüzü ayarlamayı öğrenin. Cihazları ekleyin, ilkelerinizi gözden geçirin ve ayarlarınızı gerektiği gibi düzenleyin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
- highpri
ms.openlocfilehash: 8f04e3d557b6cce71a64f62f3b91f76641b4b5d3
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598032"
---
# <a name="set-up-and-configure-microsoft-defender-for-business"></a>İş için Microsoft Defender ayarlama ve yapılandırma

İş için Defender, özellikle küçük ve orta ölçekli işletmeler için tasarlanmış kolaylaştırılmış bir kurulum ve yapılandırma deneyimi sağlar. Bu makaleyi genel süreç için kılavuz olarak kullanın.

> [!TIP]
> [Kurulum sihirbazını](mdb-use-wizard.md) kullandıysanız, temel kurulum işleminizin birkaç adımını tamamladınız demektir. Bu durumda şunları yapabilirsiniz:
> - [Daha fazla cihaz ekleme](mdb-onboard-devices.md)
> - [Güvenlik ilkelerinizi ve ayarlarınızı yapılandırma](mdb-configure-security-settings.md)
> - [Microsoft Defender Güvenlik Açığı Yönetimi panonuzu ziyaret edin](mdb-view-tvm-dashboard.md)


## <a name="the-setup-and-configuration-process"></a>Kurulum ve yapılandırma işlemi

Aşağıdaki diyagramda, İş için Defender için genel kurulum ve yapılandırma işlemi gösterilmiştir. Kurulum sihirbazını kullandıysanız, büyük olasılıkla 1-3 arası adımları ve muhtemelen 4. adımı tamamladınız demektir. 

:::image type="content" source="media/mdb-setup-process-2.png" alt-text="İş için Defender için kurulum ve yapılandırma işlemi.":::

| Adım  | Makale | Açıklama  |
|---------|---------|--------|
| 1 | [Gereksinimleri gözden geçirin](mdb-requirements.md) | İş için Defender için desteklenen işletim sistemleri de dahil olmak üzere gereksinimleri gözden geçirin. Bkz. [İş için Defender gereksinimleri](mdb-requirements.md). |
| 2 | [Rol ve izin atama](mdb-roles-permissions.md)     | Güvenlik ekibinizdeki Kişiler algılanan tehditleri & düzeltme eylemlerini gözden geçirme, & düzenleme ilkelerini görüntüleme, cihazları ekleme ve raporları kullanma gibi görevleri gerçekleştirmek için izinlere ihtiyaç duyar. Bu izinleri belirli roller aracılığıyla vekleyebilirsiniz. Bkz [. Rol ve izin atama](mdb-roles-permissions.md).        |
| 3 | [E-posta bildirimlerini ayarlama](mdb-email-notifications.md) | Uyarılar tetiklendiğinde veya yeni güvenlik açıkları bulunduğunda kimlerin e-posta bildirimleri alacağını belirtebilirsiniz. Bkz. [E-posta bildirimlerini ayarlama](mdb-email-notifications.md).| 
| 4 | [Cihazları ekleme](mdb-onboard-devices.md)     | şirketinizin cihazlarını eklemek için indirilebilir betik kullanma veya cihazları Microsoft Intune kaydetme gibi çeşitli seçenekler arasından seçim yapabilirsiniz. Bkz [. Cihazları İş için Defender'a ekleme](mdb-onboard-devices.md).         |
| 5 | [Güvenlik ayarlarınızı ve ilkelerinizi yapılandırma](mdb-configure-security-settings.md) | İş için Defender'daki [basitleştirilmiş yapılandırma işlemi](mdb-simplified-configuration.md) veya Microsoft Intune gibi güvenlik ayarlarınızı ve ilkelerinizi yapılandırmak için çeşitli seçenekler arasından seçim yapabilirsiniz. Bkz [. Güvenlik ayarlarınızı ve ilkelerinizi yapılandırma](mdb-configure-security-settings.md). |

## <a name="next-steps"></a>Sonraki adımlar

1. [Adım: İş için Microsoft Defender gereksinimlerini gözden geçirin](mdb-requirements.md).
