---
title: Windows 10 cihazlarda Microsoft Whiteboard'u dağıtma
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Microsoft Whiteboard'u Windows 10 veya sonraki sürümleri çalıştıran cihazlara dağıtmayı öğrenin.
ms.openlocfilehash: 96670b594babd8a2c61723ceab6ef826c1229764
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66943474"
---
# <a name="deploy-microsoft-whiteboard-on-windows-10-devices"></a>Windows 10 cihazlarda Microsoft Whiteboard'u dağıtma

Whiteboard, Microsoft Intune veya Microsoft Configuration Manager (eski adıyla System Center Configuration Manager) kullanılarak Windows 10 veya üzerini çalıştıran cihazlara dağıtılabilir. Whiteboard, Windows Server'da desteklenmez.

- **çevrimiçi lisans modu kullanarak Microsoft Intune** – Bu işlem, Whiteboard uygulamasına erişim alacak kullanıcı gruplarını belirtmenize olanak tanır.

- **Microsoft, el ile çevrimdışı yükleme ve güncelleştirmeleri kullanarak Configuration Manager** – Bu işlem Whiteboard'u yüklemenize ve ardından 2-4 haftada bir el ile güncelleştirmenize olanak tanır.

>[!NOTE]
> Microsoft Intune kullanmanızı öneririz. Microsoft Configuration Manager kullanmak, BT'nin kullanıcıların güncel bir sürüm çalıştırdığından emin olmak için güncelleştirmeleri sürekli olarak yeniden paketlemesini ve yüklemesini gerektirir.

## <a name="install-whiteboard-using-microsoft-intune"></a>Microsoft Intune kullanarak Whiteboard'u yükleme

1. Bu makaledeki adımları kullanarak Whiteboard'u kullanılabilir bir uygulama olarak [ekleyin: microsoft store uygulamalarını Microsoft Intune ekleme](/mem/intune/apps/store-apps-windows).

2. Bu makaledeki adımları kullanarak uygulamayı bir gruba [atayın: uygulamaları Microsoft Intune olan gruplara atama](/mem/intune/apps/apps-deploy).

## <a name="install-whiteboard-using-microsoft-configuration-manager"></a>Microsoft Configuration Manager kullanarak Whiteboard'u yükleme

1. Genel yönetici hesabı kullanarak [İş İçin Microsoft Store](https://businessstore.microsoft.com) oturum açın.

2. Üst bilgide **Yönet'i** seçin.

3. Sağ gezinti bölmesinde **Ayarlar'ı** seçin ve **ardından Çevrimdışı uygulamaları göster'i** açın.

4. Yayılma için 10-15 dakika bekleyin.

5. Ardından [Whiteboard uygulamasına](https://businessstore.microsoft.com/store/details/microsoft-whiteboard/9mspc6mp8fm4) gidin.

6. **Uygulamayı edinin'i** seçin ve lisans koşullarını kabul edin.

7. Uygulama sayfasına Geri dön.

8. **Lisans türü** açılan menüsünde **Çevrimdışı'yı** seçin.

9. **Yönet'i** seçin.

10. Bu eylem sizi envanter yönetimi sayfasına götürür ve bu sayfada artık **çevrimdışı kullanım için Paketi indir** seçeneği sunulur.

11. Mimari sürümünü seçin ve ardından indirin.

12. Uygulamayı indirdiğiniz anda Configuration Manager aracılığıyla dağıtabilirsiniz. Güncelleştirme paketi oluşturmak için 7-10 adımlarını izleyerek daha yeni bir sürüm indirin ve Configuration Manager için paketleyin.

13. Daha fazla bilgi için bkz. [Cihaz için uygulama yükleme](/mem/configmgr/apps/deploy-use/install-app-for-device).

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard'a erişimi yönetme](manage-whiteboard-access-organizations.md)

[Whiteboard için verileri yönetme](manage-data-organizations.md)

[Whiteboard için paylaşımı yönetme](manage-sharing-organizations.md)

