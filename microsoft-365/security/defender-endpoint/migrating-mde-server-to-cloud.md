---
title: Sunucuları Uç Nokta için Microsoft Defender'dan Bulut için Microsoft Defender geçirme
description: Sunucuları Uç Nokta için Microsoft Defender'dan Bulut için Microsoft Defender geçirmeyi öğrenin.
keywords: sunucuyu geçirme, sunucu, Uç Nokta için Microsoft Defender sunucusu, Bulut için Microsoft Defender, MDE, azure, azure bulutu, CSPM, CWP, bulut iş yükü koruması, tehdit koruması, gelişmiş tehdit koruması, Microsoft Azure, çoklu bulut bağlayıcısı
author: alekyaj
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-security
ms.localizationpriority: medium
ms.collection:
- m365-security
- tier2
ms.custom: migrationguides
ms.date: 07/19/2022
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 4da3b103597802b309a643876c40668d436ca37d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68641391"
---
# <a name="migrating-servers-from-microsoft-defender-for-endpoint-to-microsoft-defender-for-cloud"></a>Sunucuları Uç Nokta için Microsoft Defender'dan Bulut için Microsoft Defender geçirme

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Bu makale, sunucuları Uç Nokta için Microsoft Defender'den (MDE) Bulut için Defender'a geçirme konusunda size yol gösterir.

[Uç Nokta için Microsoft Defender](https://www.microsoft.com/security/business/endpoint-security/microsoft-defender-endpoint) (MDE), kurumsal ağların gelişmiş tehditleri engellemesine, algılamasına, araştırmasına ve yanıtlamasına yardımcı olmak için tasarlanmış bir kurumsal uç nokta güvenlik platformudur.

[Bulut için Microsoft Defender](https://azure.microsoft.com/services/defender-for-cloud/), bulut yapılandırmanızda zayıf noktalar bulan bulut güvenliği duruş yönetimi (CSPM) ve bulut iş yükü koruması (CWP) için bir çözümdür. Ayrıca ortamınızın genel güvenlik duruşunu güçlendirmeye yardımcı olur ve çok bulutlu ve hibrit ortamlardaki iş yüklerini gelişen tehditlere karşı koruyabilir.

Her iki ürün de sunucu koruma özellikleri sunsa da bulut için Microsoft Defender, sunucular da dahil olmak üzere altyapı kaynaklarını korumak için birincil çözümümüzdür. 

## <a name="how-do-i-migrate-my-servers-from-microsoft-defender-for-endpoint-to-microsoft-defender-for-cloud"></a>Sunucularımı Uç Nokta için Microsoft Defender'dan Bulut için Microsoft Defender'a Nasıl yaparım? geçirme

Uç Nokta için Defender'a eklenen sunucularınız varsa, geçiş işlemi makine türüne bağlı olarak değişir, ancak bir dizi paylaşılan önkoşul vardır. 

Bulut için Microsoft Defender, Microsoft Azure portal abonelik tabanlı bir hizmettir. Bu nedenle Bulut için Defender ve Sunucular için Microsoft Defender Plan 2 gibi temel planların Azure aboneliklerinde etkinleştirilmesi gerekir.

Azure [ARC özellikli sunucular](/azure/azure-arc/servers/overview) aracılığıyla bağlanan Azure VM'leri ve Azure dışı makineler için Sunucular için Defender'ı etkinleştirmek için şu yönergeleri izleyin:

1. Henüz Azure kullanmıyorsanız ortamınızı [Azure Well-Architected Framework'ün](/azure/architecture/framework/) ardından planlayın.

2. Aboneliklerinizde [Bulut için Microsoft Defender](/azure/defender-for-cloud/get-started) etkinleştirin.

3. [Aboneliklerinizde](/azure/defender-for-cloud/enable-enhanced-security) Sunucu planları için Microsoft Defender birini etkinleştirin. Sunucular için Defender Plan 2 kullanıyorsanız, makinelerinizin bağlı olduğu Log Analytics çalışma alanında da etkinleştirdiğinizden emin olun; Dosya Bütünlüğünü İzleme, Uyarlamalı Uygulama Denetimleri ve daha fazlası gibi isteğe bağlı özellikleri kullanmanıza olanak tanır.

4. Aboneliğinizde [MDE tümleştirmesinin](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows) etkinleştirildiğinden emin olun. Önceden var olan Azure abonelikleriniz varsa, aşağıdaki resimde gösterilen iki kabul etme düğmesinden birini (veya her ikisini) görebilirsiniz.

     :::image type="content" source="images/mde-integration.png" alt-text="MDE tümleştirmesini etkinleştirmeyi gösteren ekran görüntüsü." lightbox="images/mde-integration.png":::

   Ortamınızda bu düğmelerden herhangi biri varsa her ikisi için de tümleştirmeyi etkinleştirdiğinizden emin olun. Yeni aboneliklerde her iki seçenek de varsayılan olarak etkinleştirilir. Bu durumda, ortamınızda bu düğmeleri görmezsiniz.

5. Azure Arc için bağlantı gereksinimlerinin karşılandığından emin olun. Bulut için Microsoft Defender, tüm şirket içi ve Azure dışı makinelerin Azure Arc aracısı aracılığıyla bağlanması gerekir. Ayrıca Azure Arc, MDE tarafından desteklenen tüm işletim sistemlerini desteklemez. Bu nedenle Azure [Arc dağıtımlarını](/azure/azure-arc/servers/plan-at-scale-deployment) planlamayı buradan öğrenebilirsiniz.

6. *Önerilen:* Bulut için Defender'da güvenlik açığı bulgularını görmek istiyorsanız Bulut için Defender için [Microsoft Defender Güvenlik Açığı Yönetimi](/azure/defender-for-cloud/enable-data-collection?tabs=autoprovision-va) etkinleştirdiğinizden emin olun.

   :::image type="content" source="images/enable-threat-and-vulnerability-management.png" alt-text="Güvenlik açığı yönetimini etkinleştirmeyi gösteren ekran görüntüsü." lightbox="images/enable-threat-and-vulnerability-management.png"::: 

## <a name="how-do-i-migrate-existing-azure-vms-to-microsoft-defender-for-cloud"></a>Mevcut Azure VM'lerini Bulut için Microsoft Defender'a Nasıl yaparım? geçirme

Azure VM'leri için ek adım gerekmez; Azure platformu ile Bulut için Defender arasındaki yerel tümleştirme sayesinde bunlar otomatik olarak Bulut için Microsoft Defender eklenir.

## <a name="how-do-i-migrate-on-premises-machines-to-microsoft-defender-for-servers"></a>Şirket içi makineleri Sunucular için Microsoft Defender'a Nasıl yaparım? geçirin?

Tüm önkoşullar karşılandığında, şirket içi makinelerinizi Azure Arc'a bağlı sunucular aracılığıyla [bağlayın](/azure/defender-for-cloud/quickstart-onboard-machines?pivots=azure-arc) .

## <a name="how-do-i-migrate-vms-from-aws-or-gcp-environments"></a>VM'leri AWS veya GCP ortamlarından geçirmek Nasıl yaparım??

1. Aboneliğinizde yeni bir çoklu bulut bağlayıcısı oluşturun. (Bağlayıcı hakkında daha fazla bilgi için bkz. [AWS hesapları](/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings) veya [GCP projeleri](/azure/defender-for-cloud/quickstart-onboard-gcp?pivots=env-settings).

2. Çoklu bulut bağlayıcınızda [AWS](/azure/defender-for-cloud/quickstart-onboard-aws?pivots=env-settings#prerequisites) veya [GCP](/azure/defender-for-cloud/quickstart-onboard-gcp?pivots=env-settings#configure-the-servers-plan) bağlayıcılarında Sunucular için Defender'ı etkinleştirin.

3. Azure Arc aracısı, Uç Nokta için Microsoft Defender uzantısı, Güvenlik Açığı Değerlendirmesi ve isteğe bağlı olarak Log Analytics uzantısı için çoklu bulut bağlayıcısı üzerinde otomatik sağlamayı etkinleştirin.

     :::image type="content" source="images/select-plans-aws-gcp.png" alt-text="Azure Arc aracısı için otomatik sağlamayı etkinleştirmeyi gösteren ekran görüntüsü." lightbox="images/select-plans-aws-gcp.png":::

   Daha fazla bilgi için bkz. [Bulut için Defender'ın çoklu bulut özellikleri](https://aka.ms/mdcmc).

## <a name="what-happens-once-all-migration-steps-are-completed"></a>Tüm geçiş adımları tamamlandıktan sonra ne olur?

İlgili geçiş adımlarını tamamladıktan sonra Bulut için Microsoft Defender, veya `MDE.Linux` uzantısını `MDE.Windows` Azure Arc üzerinden bağlanan Azure vm'lerinize ve Azure dışı makinelerinize (AWS ve GCP işlemdeki VM'ler dahil) dağıtır.

Uzantı, işletim sistemi içindeki MDE yükleme betiklerini düzenleyip sarmalayan ve sağlama durumunu Azure yönetim düzlemine yansıtan bir yönetim ve dağıtım arabirimi işlevi görür. Yükleme işlemi mevcut Bir Uç Nokta için Defender yüklemesini tanır ve Uç Nokta için Defender hizmet etiketlerini otomatik olarak ekleyerek bunu Bulut için Defender'a bağlar.

Eski Log Analytics tabanlı Uç Nokta için Microsoft Defender çözümüyle sağlanan Windows Server 2012 R2 veya 2016 makineleriniz varsa, Bulut'un dağıtım işlemi için Microsoft Defender Uç Nokta için Defender [birleşik çözümünü](configure-server-endpoints.md#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution) dağıtır. Başarılı bir dağıtımdan sonra, bu makinelerde eski Uç Nokta için Defender işlemini durdurur ve devre dışı bırakır.
