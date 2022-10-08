---
title: Contoso için Kurumlar için Microsoft 365 Uygulamaları dağıtımı
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso'nın Kurumlar için Microsoft 365 Uygulamaları dağıtmak için Microsoft Endpoint Configuration Manager'ı nasıl kullandığını anlayın.
ms.openlocfilehash: 13838ab77ac485055ec0be64a52f245fa2955f99
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68171531"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Contoso için Kurumlar için Microsoft 365 Uygulamaları dağıtımı

Contoso daha etkili işbirliği, daha iyi güvenlik ve daha modern bir masaüstü deneyimi sağlamak için bilgisayarlarını Windows 10 Enterprise ve Kurumlar için Microsoft 365 Uygulamaları yükseltti. Contoso, altyapı ve iş gereksinimlerini değerlendirdikten sonra dağıtım için şu önemli gereksinimleri tanımladı:

- Tüm bilgisayarlar Kurumlar için Microsoft 365 Uygulamaları çalıştırılmalıdır.
- Dağıtım mümkün olduğunda mevcut yönetim araçlarını ve altyapısını kullanmalıdır.
- Dağıtımın kullanıcıların cihazlarında birden çok dili ve mevcut mimarileri desteklemesi gerekir.
- Bilgisayarlar en düşük BT yönetim maliyetleriyle ve kullanıcılara minimum etkiyle güncel ve güvenli kalmalıdır.

## <a name="deployment-tools"></a>Dağıtım araçları

Contoso, gereksinimlerine göre Configuration Manager (Geçerli Dal) aracılığıyla Windows 10 Enterprise ve Kurumlar için Microsoft 365 Uygulamaları dağıtmayı seçti. Configuration Manager büyük ortamlar için ölçeklendirilir ve yükleme, güncelleştirmeler ve ayarlar üzerinde kapsamlı denetim sağlar. Ayrıca, Office'i dağıtmayı ve yönetmeyi daha kolay ve verimli hale getirmek için yerleşik özelliklere de sahiptir:

- Eş önbelleği, uzak konumlardaki cihazlara dağıtılırken sınırlı ağ kapasitesine yardımcı olabilir.
- Office'i dağıtmayı ve güncelleştirmeleri izlemeyi kolaylaştıran ve yöneticilere en son dağıtım ve yönetim özelliklerine erişim sağlayan Office İstemci Yönetimi panosu.
- İşletim sistemiyle aynı dili otomatik olarak dağıtma dahil olmak üzere akıllı dil paketi dağıtımı.
- Dağıtım sırasında office'in mevcut sürümlerini bir istemciden kaldırmaya yönelik, tam olarak desteklenen ve kullanımı kolay bir yöntemdir.

Contoso, Configuration Manager ek olarak[, Office makroları ve eklentileriyle uyumluluk sorunlarını değerlendirmek için Office Eklentileri için Hazırlık Araç Seti'ni ve](/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps) Microsoft'un ücretsiz bir aracı olan VBA'yı kullandı.

## <a name="managing-deployment-and-updates"></a>Dağıtım ve güncelleştirmeleri yönetme

Kurumlar için Microsoft 365 Uygulamaları yeni bir sürüm modeline sahiptir: Hizmet olarak Office. Hizmet modeli, yeni özelliklerle güncel kalmayı kolaylaştırır. Ancak genellikle BT departmanlarının yeni sürümleri dağıtma ve test etme şeklini değiştirmesini gerektirir. Uyumluluk sorunlarını en aza indirmek ve bilgisayarlarının güncel kalmasını sağlamak için Contoso, Windows ve Office'i iki aşamada dağıttı:

- İlk olarak, Kurumlar için Microsoft 365 Uygulamaları kuruluş genelinde küçük bir temsilci cihaz kümesine dağıttılar. Bu pilot grup uygulamaları, eklentileri ve donanımları Kurumlar için Microsoft 365 Uygulamaları ile test etmek için kullanılmıştır.
- Dört ay sonra, pilot gruptaki uygulamalar, eklentiler ve donanımlarla ilgili tüm kritik sorunları ele aldıktan sonra Contoso, kuruluştaki diğer cihazlara (geniş grup) Kurumlar için Microsoft 365 Uygulamaları dağıttı.

Contoso, office güncelleştirmelerini Configuration Manager kullanarak yönetmek yerine buluttan otomatik güncelleştirmeleri etkinleştirdi. Bulut tabanlı güncelleştirmeler, yönetim yükünü azaltırken cihazların güncel kalmasını sağlar.

Contoso, Office'i dağıtmak için kullandıkları özellik güncelleştirmeleri için de aynı iki aşamalı yaklaşımı izlemektedir: Pilot gruptaki cihazlar, kuruluşun geri kalanındaki cihazlardan (geniş grup) dört ay önce özellik güncelleştirmeleri aldı. Bunu Office için etkinleştirmek için Contoso önerilen iki [güncelleştirme kanalını](/DeployOffice/overview-update-channels) kullandı:

- Pilot grup güncelleştirmeleri için Enterprise Channel'ı (Önizleme) Semi-Annual
- Geniş grup güncelleştirmeleri için Enterprise Channel'ı Semi-Annual

Semi-Annual Enterprise Channel (Önizleme) Semi-Annual Enterprise Channel'dan dört ay önce Kurumlar için Microsoft 365 Uygulamaları sürümünü yayımladığından, Contoso'nun güncelleştirmeleri yönetmek zorunda kalmadan doğrulamak için zamanı vardır.

## <a name="deployment-process"></a>Dağıtım işlemi

Contoso, Office dağıtımını tamamlamak için Microsoft'un en iyi uygulama önerilerini içeren aşağıdaki işlemi uyguladı:

1. Contoso dağıtımdan önce Office Eklentisi ve VBA için Hazırlık Araç Seti'ni kullanarak uygulamalarını ve Office Eklentilerini test ederek Kurumlar için Microsoft 365 Uygulamaları uyumluluğunu değerlendirdi.
1. Configuration Manager'da istemci cihazlarında eş önbelleği etkinleştirerek uzak konumlardaki istemci cihazlara dağıtım yaparken sınırlı ağ kapasitesine yardımcı olur. 
1. Contoso, Configuration Manager cihaz koleksiyonu olarak iki dağıtım grubu tanımlamıştı: pilot grup ve geniş bir grup. Kuruluş genelinde küçük bir temsili cihaz kümesini içeren pilot grup, Windows 10 Enterprise ve Kurumlar için Microsoft 365 Uygulamaları ile uygulamaların, eklentilerin ve donanımların ek testinde kullanıldı.
1. Office İstemci Yönetimi panosunu ve her ikisi de Configuration Manager konsolunun parçası olan Office 365 Yükleyicisi sihirbazını kullanarak Office için dağıtım paketleri oluşturdular. Biri Semi-Annual Enterprise Channel 'da (Önizleme) pilot grup, diğeri de Semi-Annual Enterprise Channel'da yer alan geniş grup için iki Kurumlar için Microsoft 365 Uygulamaları paketi oluşturmİşlerdir.
2. Her Office paketinde İngilizce, Fransızca ve Almanca Dil paketleri bulunur. Bir cihaz Office paketine dahil olmayan bir dil gerektiriyorsa, bu dil paketi otomatik olarak Office content Delivery Network'ten (CDN) indirilir.
3. Kurumlar için Microsoft 365 Uygulamaları yüklemeden önce Office'in tüm mevcut MSI sürümlerini otomatik olarak kaldırmak için Office paketindeki yerleşik özelliği kullandılar.
4. Configuration Manager'da Windows ve Office paketlerini ağlarındaki dağıtım noktalarına dağıttılar. Ardından pilot Kurumlar için Microsoft 365 Uygulamaları paketini pilot gruba dağıtmak için Configuration Manager dağıtım görev dizilerini çalıştırdılar.
5. Pilot grupla ilgili uyumluluk sorunlarını giderdikten sonra Contoso, Kurumlar için Microsoft 365 Uygulamaları paketini geniş gruba dağıtmak için görev dizilerini çalıştırdı.

Contoso cihazları buluttan otomatik olarak güncelleştirmeyi seçtiğinden, işlemi Configuration Manager'da yönetmeye gerek yoktu. Cihazları, ilk dağıtımda tanımlanan güncelleştirme kanalına bağlı olarak doğrudan buluttan otomatik olarak güncelleştirilir.

Contoso Kurumlar için Microsoft 365 Uygulamaları yüklemesi ve devam eden güncelleştirmeler dağıtım mimarisi aşağıdadır.

![Kurumlar için Microsoft 365 Uygulamaları için Contoso dağıtım altyapısı.](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Sonraki adım

Contoso'un kuruluş genelinde çalıştırdıkları cihazları ve uygulamaları yönetmek için kuruluş için Microsoft 365'te Microsoft Intune nasıl [kullandığını](contoso-mdm.md) öğrenin.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 365 Kurumsal Uygulamaları](/deployoffice/deployment-guide-microsoft-365-apps)

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Test laboratuvarı kılavuzları](m365-enterprise-test-lab-guides.md)