---
title: Contoso için Windows 10 Enterprise dağıtımı
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
description: Contoso'nın Windows 10 Enterprise için yerinde yükseltmeleri dağıtmak için Microsoft Endpoint Configuration Manager nasıl kullandığını anlayın.
ms.openlocfilehash: 2d71bb45aff9a61e80470ee834dbfe645298a218
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68171421"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Contoso için Windows 10 Enterprise dağıtımı

Kuruluş için Microsoft 365'in geniş bir dağıtımından önce Contoso,Windows uyumlu bilgisayarlara ve Windows 7 (%10), Windows 8.1 (%65) ve Windows 10 (%25) çalıştıran cihazlara sahipti. Contoso, gelişmiş güvenlikten yararlanmak Windows 10 Enterprise için bilgisayarlarını yükseltmek istedi ve güncelleştirmelerin otomatik dağıtımları nedeniyle BT ek yükünü azaltmıştı. 

Contoso, altyapı ve iş gereksinimlerini değerlendirdikten sonra dağıtım için şu önemli gereksinimleri tanımladı:

- Mümkün olduğunca çok sayıda bilgisayar ve cihaz Windows 10 Enterprise
- Yerinde yükseltmelerin dağıtımı mevcut Configuration Manager altyapısından yararlanıyor
- Dağıtım ve güncelleştirmelerin halkalar aracılığıyla hangi Windows 10 Enterprise sürümlerinin yapılacağını denetleme
- Bilgisayarlar ve cihazlar, en düşük BT yönetim maliyetleriyle ve son kullanıcılara en az etkiyle güncel kalmalıdır

Güncel, contoso'nun iş gereksinimlerini karşılayan desteklenen Windows 10 Enterprise sürümü olarak tanımlanır. Bu sürüm, Windows 10 Enterprise en son sürümünü çalıştıran Tüm Windows uyumlu bilgisayarlara sahip olmaktan farklı olabilir.

## <a name="deployment-tools"></a>Dağıtım araçları

Contoso, Windows 10 Enterprise yerinde yükseltmelerinden önce ve sırasında aşağıdaki Windows Analytics çözümlerini kullanıyordu:

- Yükseltme Hazırlığı  

  Analiz için sistem, uygulama ve sürücü verilerini toplar ve ardından yükseltmeyi engelleyebilecek uyumluluk sorunlarını tanımlar ve sorunları Microsoft tarafından bilinen düzeltmeler önerilir.

- Güncelleştirme Uyumluluğu  

  En güncel güncelleştirmelerde uygun olduklarından emin olabilmeniz için cihazlarınızın Windows güncelleştirmeleriyle ilgili durumunu gösterir.

- Cihaz Durumu  

  Sık sık kilitlenen ve bu nedenle yeniden oluşturulması veya değiştirilmesi gerekebilecek cihazları ve cihaz kilitlenmelerine neden olan cihaz sürücülerini tanımlar ve bu sürücülerin kilitlenme sayısını azaltabilecek alternatif sürümlerinin önerileriyle birlikte. Son kullanıcılara istem gönderen Windows Information Protection yanlış yapılandırmaları bildirimi sağlar.
 
Contoso'nun mevcut bir Configuration Manager (Geçerli Dal) altyapısı vardır. Configuration Manager büyük ortamlar için ölçeklendirilir ve yükleme, güncelleştirmeler ve ayarlar üzerinde kapsamlı denetim sağlar. Ayrıca, Windows 10 Enterprise dağıtmayı ve yönetmeyi daha kolay ve verimli hale getirmek için yerleşik özelliklere sahiptir.

## <a name="planning-process"></a>Planlama süreci

Contoso, yüklü uygulama kümesini ve bunların Windows 10 Enterprise uyumluluğunu belirlemek için Windows Analytics'te Yükseltme Hazırlığı'nı kullandı.

## <a name="deployment-process"></a>Dağıtım işlemi

Contoso, Windows 10 Enterprise yerinde yükseltme dağıtımını tamamlamak için Microsoft'un en iyi uygulama önerilerini içeren aşağıdaki işlemi uyguladı:

1. Configuration Manager için eş önbelleği etkinleştirildi.
2. Toplu Lisanslama Hizmet Merkezi'nden alınan görüntüleri temel alan özelleştirilmiş Windows paketleri oluşturuldu.
3. Windows paketlerini ağlarındaki dağıtım noktalarına dağıtmak ve derlemeleri üç doğrulama ve dağıtım hazırlama grubuna dağıtmak için Configuration Manager kullanılır.
4. Windows Analytics'in Cihaz Durumu ve Güncelleştirme Uyumluluğu çözümlerini kullanarak üç doğrulama ve dağıtım hazırlama kademesindeki bilgisayarlar ve cihazlar için başarı değerlendirmesi gerçekleştirildi.
5. Contoso, Windows Analytics bilgilerine dayanarak geniş dağıtım grubuna dağıtılacak Windows 10 Enterprise sürümünü belirledi.
6. Seçilen Windows paketini geniş dağıtım grubuna dağıtmak için Configuration Manager dağıtım görev dizilerini çalıştırmıştı.
7. Sorunları gidermek için Cihaz Durumu ve Güncelleştirme Uyumluluğu çözümlerini kullanarak geniş dağıtım grubundaki izlenen bilgisayarlar ve cihazlar.

Contoso'nun yerinde yükseltmesi ve devam eden güncelleştirmeler dağıtım mimarisi aşağıdadır.

![Contoso'nun Windows 10 Enterprise dağıtım altyapısı.](../media/contoso-win10/contoso-win10-fig1.png)

Bu altyapı şunlardan oluşur:

- Configuration Manager, hangi:
  - Windows 10 Enterprise paketleri için görüntüleri Microsoft Ağı'ndaki Microsoft Toplu Lisanslama Merkezi'nden alır.
  - Dağıtım paketleri için merkezi yönetim noktasıdır.
- Genellikle Contoso'nun bölgesel merkez ofislerinde bulunan bölgesel dağıtım noktaları.
- Yerinde yükseltme veya grup üyeliğine bağlı olarak devam eden güncelleştirmeler için dağıtım paketlerini alan ve yükleyen çeşitli konumlardaki Windows bilgisayarları ve cihazları.

## <a name="next-step"></a>Sonraki adım

Contoso'un kuruluş genelinde [geçerli Kurumlar için Microsoft 365 Uygulamaları dağıtmak ve tutmak için Configuration Manager](contoso-o365pp.md) altyapısından nasıl yararlandığı hakkında bilgi edinin. 

## <a name="see-also"></a>Ayrıca bkz.

[Windows 10 Enterprise](/windows/deployment/)

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Test laboratuvarı kılavuzları](m365-enterprise-test-lab-guides.md)