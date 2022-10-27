---
title: Office 2010'unuzu Microsoft 365'e yükseltme - Microsoft 365 yöneticisi
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Microsoft Office'i kuruluşunuzdaki kullanıcılar için en son Office istemcisine yükseltme hakkında bilgi edinin.
ms.topic: article
ms.openlocfilehash: 8ba242bc6f26f9145b525a13339f9b7105a038dd
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68726298"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>İş için Microsoft 365 kullanıcılarınızı en son Office istemcisine yükseltme

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 destek sonuna ulaştı

Office 2010, 13 Ekim 2020'de destek sonuna ulaşmıştır. Microsoft artık aşağıdakileri sağlamayacaktır:

- Sorunlar için teknik destek

- Bulunan sorunlar için hata düzeltmeleri

- Bulunan güvenlik açıkları için güvenlik düzeltmeleri

Daha fazla bilgi için bkz. [Office 2010 destek sonu yol haritası](/deployoffice/endofsupport/office-2010-end-support-roadmap) .

 **Bu sizin için doğru konu mu?**
  
 Kuruluşunuzda İş için Microsoft 365 aboneliğinden sorumlu yöneticiyseniz, doğru yerdesiniz demektir. Yöneticiler genellikle kullanıcıları yönetme, parolaları sıfırlama, Office yüklemelerini yönetme ve lisans ekleme veya kaldırma gibi görevlerden sorumludur.

 Yönetici değilseniz ve [Microsoft 365 Aile](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) bir ürününüz varsa, Office'in eski, evde kullanım sürümünü yükseltme hakkında bilgi için bkz. Office'i [yükseltme Nasıl yaparım?](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350).

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>Microsoft 365'e yükseltmeye hazır olun

Yönetici olarak, kuruluşunuzdaki Office kullanıcılarının hangi sürümünü yükleyebileceğini denetlersiniz. Kuruluşunuzda Office'in Office 2010, Office 2013 veya Office 2016 gibi eski sürümlerini çalıştıran kullanıcıların güvenlik ve üretkenlik geliştirmelerinden yararlanmak için en son sürüme yükseltmelerine yardımcı olmanız kesinlikle önerilir.

## <a name="upgrade-steps"></a>Yükseltme adımları

Aşağıdaki adımlar, kullanıcılarınızı en son Office masaüstü istemcisine yükseltme işleminde size yol gösterir. Yükseltme işlemine başlamadan önce bu adımları okumanızı öneririz.
  
## <a name="step-1---check-system-requirements"></a>1. Adım - Sistem gereksinimlerini denetleme

Cihazlarınızın Office'in en son sürümüyle uyumlu olduğundan emin olmak için Office'in [sistem gereksinimlerini denetleyin](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources). Örneğin, Office'in daha yeni sürümleri Windows XP veya Windows Vista çalıştıran bilgisayarlara yüklenemez.
  
> [!TIP]
> Kuruluşunuzda bilgisayarlarında veya dizüstü bilgisayarlarında Windows'un eski sürümlerini çalıştıran kullanıcılarınız varsa, Windows 10 yükseltmenizi öneririz. Windows 7 destek sonuna ulaştı. Daha fazla bilgi [için Windows 7 desteği Ocak 2020'de sona eriyor](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) yazısını okuyun.

İşletim sistemlerini yükseltip yükseltemediğini görmek için [Windows 10 sistem gereksinimlerini](https://www.microsoft.com/windows/windows-10-specifications) gözden geçirin.

### <a name="check-application-compatibility"></a>Uygulama uyumluluğunu denetleme

Yükseltmenin başarılı olmasını sağlamak için VBA betikleri, makrolar, üçüncü taraf eklentileri, karmaşık belgeler ve elektronik tablolar dahil olmak üzere Office uygulamalarınızı tanımlamanızı ve bunların Office'in en son sürümüyle uyumluluğunu değerlendirmenizi öneririz.
  
Örneğin, geçerli Office yüklemenizde üçüncü taraf eklentileri kullanıyorsanız, office'in en son sürümüyle uyumlu olduklarından emin olmak için üreticiye başvurun.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>2. Adım - Mevcut abonelik planınızı denetleme

Bazı Microsoft 365 planları Office'in tam masaüstü sürümlerini içermez ve planınız Office'i içermiyorsa yükseltme adımları farklıdır.
  
Hangi abonelik planına sahip olduğunuzdan emin değil misiniz? Bkz [. hangi İş için Microsoft 365 aboneliğine sahibim?](../admin-overview/what-subscription-do-i-have.md)
  
Mevcut planınız Office içeriyorsa [, 3. Adım - Office'i kaldırma'ya](#step-3---uninstall-office) geçin.
  
Mevcut planınız Office içermiyorsa aşağıdaki seçeneklerden birini belirleyin:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Office içermeyen planlar için yükseltme seçenekleri

 **Seçenek 1: Office aboneliklerini değiştirme**

Office içeren bir aboneliğe geçin. Bkz. [Farklı bir İş için Microsoft 365 planına geçme](../../commerce/subscriptions/switch-to-a-different-plan.md).

**2. Seçenek: Bireysel, tek seferlik Office satın almaları satın alma veya toplu lisans aracılığıyla Office satın alma**

 - Tek seferlik bir Office satın alma işlemi satın alın. Bkz. [Office Ev &amp; İş](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b) veya [Office Profesyonel](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)

     VEYA

 - Toplu lisans aracılığıyla Office'in birden çok kopyasını satın alın. Bkz. [Toplu lisanslama ile kullanılabilen paketleri karşılaştırma](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>3. Adım - Office'i kaldırma

Office'in en son sürümünü yüklemeden önce, Office'in tüm eski sürümlerini kaldırmanızı öneririz. Ancak, Office'i yükseltme konusunda fikrinizi değiştirirseniz, Office'i kaldırdıktan sonra yeniden yükleyemeyeceğiniz aşağıdaki örnekleri not edin.
  
Üçüncü taraf eklentileriniz varsa, Office'in en son sürümüyle çalışacak bir güncelleştirme olup olmadığını görmek için üreticiye başvurmanızı öneririz.

> [!TIP]
> Office'i kaldırırken sorunlarla karşılaşırsanız, Office'i kaldırmanıza yardımcı olması için Microsoft Desteği ve Kurtarma Yardımcısı aracını kullanabilirsiniz: [Microsoft Desteği ve Kurtarma Yardımcısı'nı indirip çalıştırın](https://go.microsoft.com/fwlink/?LinkID=2155008).

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Kaldırmak istediğiniz Office sürümünü seçin

- [Bilgisayardan](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Mac'ten](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Kaldırma sonrasında Office'in eski sürümlerini yeniden yüklemeye çalışırken karşılaşılan bilinen sorunlar

 **Toplu lisans aracılığıyla Office** Office'in bu toplu lisans sürümlerinin kaynak dosyalarına artık erişiminiz yoksa, yeniden yükleyemezsiniz.

 **Bilgisayarınızda önceden yüklenmiş Office** Artık disk veya ürün anahtarınız yoksa (Office bir diskle birlikte geldiyse) diski yeniden yükleyemezsiniz.

 **Desteklenmeyen abonelikler** Office kopyanız Office 365 Küçük İşletme Ekstra veya Orta Ölçekli İşletme Office 365 gibi kesintiye neden olan abonelikler aracılığıyla alındıysa, aboneliğinizle birlikte gelen ürün anahtarına sahip değilseniz Office'in eski bir sürümünü yükleyemezsiniz.

Office'in eski sürümünü en son sürümle yan yana yüklemeyi tercih ederseniz, bu sürümün desteklendiği sürümlerin listesini görebilir, [Aynı bilgisayarda Office'in farklı sürümlerini yükleyip kullanabilirsiniz](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). Örneğin, eski Office sürümünüzle kullandığınız üçüncü taraf eklentileri yüklediyseniz ve bunların en son sürümle uyumlu olduğundan henüz emin değilseniz, yan yana yükleme sizin için doğru seçim olabilir.

## <a name="step-4---assign-office-licenses-to-users"></a>4. Adım - Kullanıcılara Office lisansları atama

Henüz yapmadıysanız, kuruluşunuzda Office'i yüklemesi gereken kullanıcılara lisans atayın, bkz. [İş için Microsoft 365'te kullanıcılara lisans atama](../manage/assign-licenses-to-users.md).
  
## <a name="step-5---install-office"></a>5. Adım - Office'i yükleme

Yükseltmek istediğiniz tüm kullanıcıların lisansları olduğunu doğruladıktan sonra, son adım Office'i yüklemelerini sağlamaktır. Bkz. [PC veya Mac bilgisayarınıza Office'i indirme ve yükleme veya yeniden yükleme](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).
  
> [!TIP]
> Kullanıcılarınızın Office'i kendilerinin yüklemesini istemiyorsanız bkz. [Office 365'de yazılım indirme ayarlarını yönetme](/DeployOffice/manage-software-download-settings-office-365). [Office Dağıtım Aracı'nı kullanarak Office](/DeployOffice/overview-office-deployment-tool) yazılımını yerel ağınıza indirebilir ve ardından genellikle kullandığınız yazılım dağıtım yöntemini kullanarak Office'i dağıtabilirsiniz.