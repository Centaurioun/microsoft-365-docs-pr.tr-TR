---
title: Uç Nokta için Microsoft Defender’daki yenilikler
description: Uç Nokta için Microsoft Defender'nin en son sürümünde genel kullanıma sunulan özelliklerin (GA) yanı sıra Windows 10 ve Windows Server'daki güvenlik özelliklerini görün.
keywords: Uç Nokta için Microsoft Defender, ga, genel kullanıma sunulan, özellikler, kullanılabilir, yeni sürümündeki yenilikler
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
ms.date: 08/25/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 07f9aa517ae0cc4b442d0296df82f219e242debf
ms.sourcegitcommit: 6f565d9e0f91ebc76fd13d7005619531391ab5f9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2022
ms.locfileid: "67439618"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender’daki yenilikler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Aşağıdaki özellikler önizleme aşamasındadır veya Uç Nokta için Microsoft Defender en son sürümünde genel kullanıma sunulmuştur (GA).

Önizleme özellikleri hakkında daha fazla bilgi için bkz. [Önizleme özellikleri](preview.md).

> [!TIP]
> RSS akışı: Aşağıdaki URL'yi kopyalayıp akış okuyucunuza yapıştırarak bu sayfa güncelleştirildiğinde bildirim alın:
>
> ```https
> https://docs.microsoft.com/api/search/rss?search=%22features+are+generally+available+%28GA%29+in+the+latest+release+of+Microsoft+Defender+for+Endpoint%22&locale=en-us&facet=
> ```

Diğer Microsoft Defender güvenlik ürünleriyle ilgili yenilikler hakkında daha fazla bilgi için bkz:

- [Microsoft 365 Defender'daki yenilikler](../defender/whats-new.md)
- [Office 365 için Microsoft Defender’daki yenilikler](../office-365-security/whats-new-in-defender-for-office-365.md)
- [Kimlik için Microsoft Defender'deki yenilikler](/defender-for-identity/whats-new)
- [Microsoft Cloud App Security'deki yenilikler](/cloud-app-security/release-notes)

Diğer işletim sistemleriyle ilgili Uç Nokta için Microsoft Defender hakkında daha fazla bilgi için:

- [macOS'ta Uç Nokta için Defender'daki yenilikler](mac-whatsnew.md)
- [iOS'ta Uç Nokta için Defender'daki yenilikler](ios-whatsnew.md)
- [Linux'ta Uç Nokta için Defender'daki yenilikler](linux-whatsnew.md)

## <a name="august-2022"></a>Ağustos 2022

- [Cihaz durumu](investigate-machines.md#device-health-status)<br>Cihaz sistem durumu kartı, belirli bir cihaz için özetlenmiş bir sistem durumu raporu gösterir.
- [Cihaz durumu raporlama (Önizleme)](/microsoft-365/security/defender-endpoint/machine-reports)<br> Cihazlar durum raporu, kuruluşunuzdaki cihazlar hakkında üst düzey bilgiler sağlar. Rapor algılayıcı durumunu, virüsten koruma durumunu, işletim sistemi platformlarını ve Windows 10 sürümlerini gösteren popüler bilgiler içerir.
- [macOS'ta kurcalama koruması genel kullanıma sunuldu](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/tamper-protection-on-macos-is-now-generally-available/ba-p/3595422)<br> Bu özellik varsayılan olarak denetim modu etkin olarak yayımlanır ve özelliği zorunlu kılmaya (engellemeye) veya kapatmaya karar vekleyebilirsiniz. Bu yılın ilerleyen bölümlerinde uç noktaları otomatik olarak blok moduna geçirebilecek aşamalı bir dağıtım mekanizması sunacağız; Bunun yalnızca özelliği etkinleştirme (blok modu) veya devre dışı bırakma seçeneği belirtmediyseniz geçerli olacağını unutmayın.
- [macOS ve Linux için Ağ Koruması ve Web Koruması artık Genel Önizleme'de!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-protection-and-web-protection-for-macos-and-linux-is-now/ba-p/3601576)<br>Ağ Koruması, cihazlarınızın saldırı yüzeyini İnternet tabanlı olaylardan azaltmaya yardımcı olur. Çalışanların, İnternet'te kimlik avı dolandırıcılığı, açıklardan yararlanma ve diğer kötü amaçlı içeriğe ev sahipliği yapabilen tehlikeli etki alanlarına erişmek için herhangi bir uygulama kullanmasını engeller. Uç Nokta için Microsoft Defender için Web Korumamızın temelidir. Bu özellikler Arasında Web tehdit koruması, Web içeriği filtreleme ve IP/URL Özel göstergeleri bulunur. Web koruması, cihazlarınızı web tehditlerine karşı korumanıza olanak tanır ve istenmeyen içeriği düzenlemeye yardımcı olur.
- [Windows Server 2012 R2 ve Windows Server 2016 için geliştirilmiş Uç Nokta için Microsoft Defender (MDE) ekleme](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2207#improved-microsoft-defender-for-endpoint-mde-onboarding-for-windows-server-2012-r2-and-windows-server-2016)<br>Configuration Manager sürüm 2207 artık Windows Server 2012 R2 & 2016 için modern, birleşik Uç Nokta için Microsoft Defender otomatik dağıtımını destekliyor. Uç Nokta için Microsoft Defender ekleme ilkesiyle hedeflenen Windows Server 2012 ve 2016 cihazları, İstemci Ayarları aracılığıyla yapılandırıldıysa birleşik aracıyı ve mevcut Microsoft Monitoring Agent tabanlı çözümü kullanır.


## <a name="july-2022"></a>Temmuz 2022
- [Etki alanı denetleyicisi cihazları ekleme - Değerlendirme laboratuvarı geliştirmesi](evaluation-lab.md#add-a-domain-controller)<br>Genel kullanıma sunuldu - Birden çok cihazda yanal hareket ve çok aşamalı saldırılar gibi karmaşık senaryoları çalıştırmak için bir etki alanı denetleyicisi ekleyin.
- [Uç Nokta için Microsoft Defender'de Dosya sayfası iyileştirmeleri duyurulıyor](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-file-page-enhancements-in-microsoft-defender-for/ba-p/3584004)<br>hiç Uç Nokta için Microsoft Defender dosyaları araştırdınız mı? Dosya sayfasında ve yan panelde yapılan son geliştirme duyurumuz sayesinde artık daha da kolaylaştık. Kullanıcılar artık tüm bu bilgileri tek bir yerde barındıran daha verimli bir gezinti deneyimine sahip olarak işlemleri kolaylaştırabilir.
- [Yeni uyarı engelleme deneyimine giriş](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/introducing-the-new-alert-suppression-experience/ba-p/3562719)<br>Yeni ve gelişmiş uyarı engelleme deneyiminin genel kullanıma sunulduğundan dolayı heyecanlıyız. Yeni deneyim daha sıkı ayrıntı düzeyi ve denetim sağlayarak kullanıcıların Uç Nokta için Microsoft Defender uyarılarını ayarlamasına olanak sağlar.
- [Güvenliği aşılmış yönetilmeyen cihazların kuruluşunuzda "İçerir](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/prevent-compromised-unmanaged-devices-from-moving-laterally-in/ba-p/3482134)<br>Bugünden itibaren, Uç Nokta için Microsoft Defender kayıtlı olmayan bir cihazın gizliliğinin tehlikeye atıldığından şüphelenildiğinde, soC analisti olarak cihazı "Içerebileceksiniz". Sonuç olarak, Uç Nokta için Microsoft Defender kaydedilen tüm cihazlar artık şüpheli cihazla gelen/giden tüm iletişimi engeller.
- [Mobil cihaz desteği artık Uç Nokta için Defender kullanan ABD Kamu Müşterileri için kullanılabilir](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/mobile-device-support-is-now-available-for-us-government/ba-p/3472590)<br>US Government müşterileri için Uç Nokta için Microsoft Defender, Azure ABD Kamu ortamında oluşturulmuştur ve Azure Ticari'de Defender ile aynı temel teknolojileri kullanır. Bu teklif GCC, GCC High ve DoD müşterilerine sunulur ve platform kullanılabilirliğimizi Windows, MacOS ve Linux'tan Android ve iOS cihazlara da genişletir.


## <a name="june-2022"></a>Haziran 2022
- [Sunucular için Defender Plan 2 artık MDE birleşik çözümüyle tümleşiyor](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/defender-for-servers-plan-2-now-integrates-with-mde-unified/ba-p/3527534)<br>Artık tek bir düğme kullanarak Windows Server 2012 R2 ve 2016 için modern, birleşik çözümü Sunucular için Defender Plan 2 kapsamındaki sunuculara dağıtmaya başlayabilirsiniz.
- [Android & iOS'ta Uç Nokta için Microsoft Defender Mobil Ağ Koruması artık Genel Önizleme'de](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/mobile-network-protection-in-microsoft-defender-for-endpoint-on/ba-p/3559121)<br>Microsoft, Uç Nokta için Defender'da kuruluşların güçlü tehdit bilgileri yardımıyla uç nokta zayıflıklarını tanımlamalarına, değerlendirmelerine ve düzeltmelerine yardımcı olan bir mobil ağ koruma özelliği sunar. Kullanıcıların artık Uç Nokta için Microsoft Defender ile hem Android hem de iOS platformlarında bu yeni özellikten yararlanabileceğini duyurmaktan mutluluk duyuyoruz.

## <a name="may-2022"></a>Mayıs 2022
- [macOS için kurcalama koruması (önizleme)](tamperprotection-macos.md)<br>Kurcalama koruması, macOS'ta Uç Nokta için Microsoft Defender yetkisiz olarak kaldırılmasını önlemeye yardımcı olur.
- [Etki alanı denetleyicisi cihazları ekleme - Değerlendirme laboratuvarı geliştirmesi (önizleme)](evaluation-lab.md#add-a-domain-controller)<br>Birden çok cihazda yanal hareket ve çok aşamalı saldırılar gibi karmaşık senaryoları çalıştırmak için bir etki alanı denetleyicisi ekleyin.
- [Uç Nokta için Microsoft Defender için sorun giderme modu genel kullanıma sunuldu](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/troubleshooting-mode-for-microsoft-defender-for-endpoint-now/ba-p/3347344)<br>Cihazlarınızdaki yapılandırmaları araştırmanın ve ayarlamanın benzersiz, yenilikçi ve güvenli bir yolu olan sorun giderme moduna giriş. Bu mod, cihazdaki yerel yöneticinin cihazda kurcalama koruması da dahil olmak üzere Microsoft Defender Virüsten Koruma güvenlik ilkesi yapılandırmalarını geçersiz kılabilmesini sağlar. 
- [Android Kurumsal için Uç Nokta için Defender kişisel profilinin genel önizlemesi duyurulmaktadır](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-the-public-preview-of-defender-for-endpoint-personal/ba-p/3370979)<br>Kendi cihazlarını iş yerlerinin KCG programına kaydetmek isteyen kullanıcıların artık kişisel profillerinde de Uç Nokta için Microsoft Defender tarafından sağlanan korumadan yararlanabileceklerini duyurmaktan mutluluk duyuyoruz.
- [Uç Nokta için Microsoft Defender'da Güvenlik Ayarları Yönetimi genel kullanıma sunuldu](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/security-settings-management-in-microsoft-defender-for-endpoint/ba-p/3356970)<br>2021'in sonlarında Uç Nokta için Microsoft Defender yapılandırma yönetimi özelliklerini genişlettik. Bu sürüm, güvenlik ekiplerine ek araçlar veya altyapı dağıtmaya ve uygulamaya gerek kalmadan cihazları istedikleri güvenlik ayarlarıyla yapılandırma gücü verdi.  Microsoft Endpoint Manager ile mümkün hale gelen kuruluşlar, tüm listeye alınan cihazlar için virüsten koruma (AV), uç nokta algılama ve yanıt (EDR) ve güvenlik duvarı (FW) ilkelerini tek bir görünümden yönetebildi. Bugün, bu özelliğin Windows 10, Windows 11 ve Windows Server 2012 R2 veya sonraki sürümleri destekleyen Windows istemcisi ve Windows server için genel kullanıma sunulduğu duyurulmaktadır.

## <a name="april-2022"></a>Nisan 2022
- [Windows Server 2012 R2 ve Windows Server 2016) için ekleme ve özellik eşlikleri güncelleştirildi](configure-server-endpoints.md)<br/> Yeni birleşik çözüm paketi genel kullanıma sunuldu ve bağımlılıkları ve yükleme adımlarını kaldırarak sunucuları eklemeyi kolaylaştırıyor. Ayrıca, bu birleşik çözüm paketi birçok yeni özellik geliştirmesi ile birlikte gelir.
- [iOS için Tunnel ile tümleştirme](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/what-s-new-in-microsoft-endpoint-manager-2204-april-edition/ba-p/3297995). iOS'ta Uç Nokta için Microsoft Defender artık tek bir uygulamada güvenliği ve bağlantıyı etkinleştirmek için bir VPN ağ geçidi çözümü olan Microsoft Tunnel ile tümleştirilebilir. Bu özellik daha önce yalnızca Android'de kullanılabilirdi.
- [Uç Nokta için Microsoft Defender Android'de Gelişmiş Kötü Amaçlı Yazılımdan Koruma](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/enhanced-antimalware-protection-in-microsoft-defender-for/ba-p/3290320)<br>Android'de Uç Nokta için Microsoft Defender Kötü Amaçlı Yazılımdan koruma özelliklerine yönelik önemli güncelleştirmeleri paylaşmak için heyecanlıyız. Bu yeni özellikler, Uç Nokta için Microsoft Defender'da yeni nesil korumanızın önemli bir bileşenini oluşturur. Bu koruma, kuruluşunuzdaki Android cihazlarını (veya uç noktalarını) korumak için makine öğrenmesini, büyük veri analizini, ayrıntılı tehdit araştırmalarını ve Microsoft bulut altyapısını bir araya getirir.
- [Linux ve macOS için geliştirilmiş kötü amaçlı yazılımdan koruma altyapısı özellikleri](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/enhanced-antimalware-engine-capabilities-for-linux-and-macos/ba-p/3292003)<br>Yeni, gelişmiş bir altyapıyla Linux ve macOS'ta yeni nesil korumamıza önemli bir yükseltme duyuruyoruz. Microsoft Defender Virüsten Koruma kötü amaçlı yazılımdan koruma altyapısı, yeni nesil korumanın önemli bir bileşenidir. Bu koruma, kuruluşunuzdaki cihazları (veya uç noktaları) korumak için makine öğrenmesi, büyük veri analizi, ayrıntılı tehdit araştırması ve Microsoft bulut altyapısını getirir. Bu önemli güncelleştirmenin temel avantajları performans ve önleme geliştirmelerinin yanı sıra macOS ve Linux'ta özel dosya göstergeleri için destek eklemektir.
- [Cihaz Denetimi ve Windows Defender Güvenlik Duvarı için Yeni Raporlama İşlevleri](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/new-reporting-functionality-for-device-control-and-windows/ba-p/3290601)<br>Microsoft 365 Defender portalındaki yeni Uç nokta raporlama özelliklerini duyurmaktan heyecanlıyız. Bu çalışma, ortamınızda neler olduğunu yalnızca birkaç tıklamayla görebilmeniz için yeni uç nokta raporlarını bir araya getirir. Raporlarımız, cihaz davranışı ve etkinliği hakkında içgörü sağlarken Microsoft 365 Defender portalındaki cihaz zaman çizelgesi ve gelişmiş avcılık gibi tümleşik deneyimlerden tam olarak yararlanmanızı sağlayacak şekilde tasarlanmıştır.
- [Microsoft 365 Defender'deki birleşik gönderimler genel kullanıma sunuldu!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/unified-submissions-in-microsoft-365-defender-now-generally/ba-p/3270770)<br>Güvenlik ekibiniz artık e-postaları, URL'leri, e-posta eklerini ve dosyaları tek bir kullanımı kolay gönderim deneyiminde göndermek için bir "tek adresli mağaza" kullanıyor. Gönderim sürecini basitleştirmek için Microsoft 365 Defender portalında (https://security.microsoft.com)) yeni bir birleşik gönderim deneyimini duyurmaktan heyecanlıyız. Birleştirilmiş gönderimlerle, portaldan gözden geçirebilmek için dosyaları Microsoft 365 Defender gönderebilirsiniz. Ayrıca doğrudan bir Uç Nokta için Microsoft Defender Uyarısı sayfasından dosya gönderme özelliği de ekliyoruz.  
- [Canlı Yanıt API'leri için genişletilmiş destek ve işlevsellik duyurulması](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-expanded-support-and-functionality-for-live-response/ba-p/3178432)<br>Uç Nokta için Microsoft Defender'da desteklenen tüm platformlarımızda mevcut API'lerin desteğini genişletmeye devam ettiğimizi ve kuruluşun yanıt otomasyon ve düzenlemesini kolaylaştırmaya ve artırmaya yardımcı olacak yenilerini duyurmaktan mutluluk duyuyoruz.

## <a name="february-2022"></a>Şubat 2022

- [Microsoft Güvenliği için Splunk Eklentisi kullanıma sunuldu](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/the-splunk-add-on-for-microsoft-security-is-now-available/ba-p/3171272)<br>Microsoft Security için Splunk tarafından desteklenen Splunk Eklentisinin kullanıma sunulduğundan mutluluk duyuyoruz. Bu eklenti Splunk 1.3.0 için Microsoft 365 Defender Eklentisi'ni oluşturur ve Uç Nokta için Microsoft Defender Uyarıları API özelliklerini veya Microsoft 365 Defender Olayları API'sinin özelliklerini Splunk'un Ortak Bilgi Modeli (CIM) ile eşler.
- [Eski SIEM API'sini kullanımdan kaldırma - Ertelendi](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/deprecating-the-legacy-siem-api-postponed/ba-p/3139643)<br>Daha önce SIEM REST API'sinin 1/4/2022 tarihinde kullanım dışı bırakılacağı duyurulmuştu. Müşteri geri bildirimlerini dinledik ve API'nin kullanımdan kaldırılması şimdilik ertelendi. Daha fazla ayrıntı 3. Ç2022'de bekleniyor. 3. Çeyrek 2022'de Microsoft Graph'ta Microsoft 365 Defender API'leri hakkında heyecan verici ayrıntıları paylaşmak için sabırsızlanıyoruz.

## <a name="january-2022"></a>Ocak 2022

- [Android ve iOS için güvenlik açığı yönetimi genel kullanıma sunuldu](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)<br>Bu yeni platformlar arası kapsam sayesinde Tehdit ve Güvenlik Açığı Yönetimi özellikleri artık iş istasyonları, sunucular ve mobil cihazlar gibi kuruluş genelindeki tüm büyük cihaz platformlarını desteklemektedir. 
- [Uç Nokta için Microsoft Defender Plan 1 Artık M365 E3/A3 Lisanslarına Dahil](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-for-endpoint-plan-1-now-included-in-m365-e3/ba-p/3060639)<br>14 Ocak'tan itibaren Uç Nokta için Microsoft Defender Plan 1 (P1) otomatik olarak Microsoft 365 E3/A3 lisanslarına dahil edilecek.
- [iOS'ta Uç Nokta için Microsoft Defender artık genel önizlemede sıfır dokunmayla ekleme](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/zero-touch-onboarding-of-microsoft-defender-for-endpoint-on-ios/ba-p/3038045)<br>Bu yeni özellik sayesinde kuruluşlar artık uygulamayla etkileşime geçmek için son kullanıcılara gerek kalmadan microsoft Endpoint Manager otomatik olarak kaydedilen iOS cihazlarına Uç Nokta için Microsoft Defender dağıtabilir. Bu, Uç Nokta için Microsoft Defender hedeflenen cihazlarda sessizce etkinleştirildiğinden ve iOS varlığınızı korumaya başladığından dağıtım uyuşmalarını kolaylaştırır ve uygulamayı tüm cihazlara dağıtmak için gereken süreyi önemli ölçüde azaltır.

## <a name="december-2021"></a>Aralık 2021

- [Microsoft Defender Güvenlik Açığı Yönetimi, uygulamalardaki ve bileşenlerdeki Log4j güvenlik açıklarını tanımlamaya yardımcı olabilir](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/#TVM)<br>Tehdit ve güvenlik açığı yönetimi, Log4j güvenlik açıklarından ve ortamdaki ilgili riskten etkilenen cihazları otomatik olarak ve sorunsuz bir şekilde tanımlar ve azaltma süresini önemli ölçüde azaltır. Microsoft, tehdit manzarasındaki en son bilgilere göre bu özellikleri yinelemeye devam eder.
- IoT cihazlarını bulma (önizleme): [Cihaz bulma](device-discovery.md) özelliği artık şirket ağınıza bağlı yönetilmeyen IoT cihazlarını bulmanıza yardımcı olabilir. Bu, ioT envanterinizin yanı sıra DIĞER BT cihazlarınızın (iş istasyonları, sunucular ve mobil) tek bir birleşik görünümünü sağlar.
- [IoT için Microsoft Defender tümleştirmesi (önizleme):](enable-microsoft-defender-for-iot-integration.md)Bu tümleştirme, IoT için Microsoft Defender tarafından sağlanan aracısız izleme özellikleriyle cihaz bulma özelliklerinizi geliştirir. Bu, ağınızdaki IoT cihazlarının bulunmasına, tanımlanmasına ve güvenliğinin sağlanmasına yardımcı olmak için daha fazla görünürlük sağlar.

## <a name="november-2021"></a>Kasım 2021

- [Güvenlik yapılandırma yönetimi](security-config-management.md) <br/> Microsoft Intune veya Microsoft Endpoint Configuration Manager microsoft Endpoint Manager tarafından yönetilmeyen cihazların microsoft defender güvenlik yapılandırmalarını doğrudan Endpoint Manager alma özelliği.
- [Değerlendirme Laboratuvarı: Atomik Kırmızı Takım simülasyonları & genişletilmiş işletim sistemi desteği](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/evaluation-lab-expanded-os-support-amp-atomic-red-team/ba-p/2993927)<br>Değerlendirme Laboratuvarı artık Windows 11, Windows Server 2016 ve Linux cihazları eklemeyi destekliyor. Ayrıca, Red Canary'nin açık kaynak simülasyon kitaplığı Atomik Kırmızı Takım ile yeni bir ortaklığı duyurmak istiyoruz!
- [Uç Nokta için Microsoft Defender Mobile - Kurcalama korumasının genel önizlemesini duyurma](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-the-public-preview-of-microsoft-defender-for-endpoint/ba-p/2971038)<br>Uç Nokta için Microsoft Defender mobil uygulamasında 7 günlük işlem yapılmadığında cihazı uyumsuz olarak işaretleyin.
- [Davranış izleme, genişletilmiş dağıtım kapsamı ve daha fazlası ile Linux varlığınızın korumasını artırın](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/boost-protection-of-your-linux-estate-with-behavior-monitoring/ba-p/2909320)<br>Linux'ta yeni nesil koruma, uç nokta algılama ve yanıt (EDR), Tehdit ve Güvenlik Açığı Yönetimi (TVM) Uç Nokta için Microsoft Defender hakkında en son haberleri paylaşmak için heyecanlıyız. Linux varlığınız için Microsoft koruması, güvenlik paketinin tüm yelpazesinde etkileyici bir destek alıyor. Linux'ın Azure Güvenlik Merkezi tümleştirmesine yönelik son Uç Nokta için Microsoft Defender, Linux EDR ve TVM'nin avantajları artık Azure Defender müşterilerine de genişlemektedir.

## <a name="october-2021"></a>Ekim 2021

- [Windows Server 2012 R2 ve Windows Server 2016 için ekleme ve özellik eşlikleri güncelleştirildi (önizleme)](configure-server-endpoints.md)<br/> Yeni birleşik çözüm paketi, bağımlılıkları ve yükleme adımlarını kaldırarak sunucuları eklemeyi kolaylaştırır. Ayrıca, bu birleşik çözüm paketi birçok yeni özellik geliştirmesi ile birlikte gelir.
- Uç Nokta için Microsoft Defender ve Microsoft 365 Defender Windows 11 desteği eklendi.

## <a name="september-2021"></a>Eylül 2021

- [Web içeriği filtreleme](web-content-filtering.md) <br/>Uç Nokta için Microsoft Defender'daki web koruma özelliklerinin bir parçası olarak, web içeriği filtreleme, kuruluşunuzun güvenlik ekibinin web sitelerine erişimi içerik kategorilerine göre izlemesine ve düzenlemesine olanak tanır. Kategoriler arasında yetişkin içeriği, yüksek bant genişliği, yasal sorumluluk, boş zaman ve kategorilere ayrılmamış yer alır. Bu kategorilerden birine veya daha fazlasına giren birçok web sitesi kötü amaçlı olmasa da uyumluluk düzenlemeleri, bant genişliği kullanımı veya diğer endişeler nedeniyle sorunlu olabilir. [Web içeriği filtreleme hakkında daha fazla bilgi edinin](web-content-filtering.md).

## <a name="august-2021"></a>Ağustos 2021

- (Önizleme) [Uç Nokta için Microsoft Defender Plan 1 ](defender-endpoint-plan-1.md) <br/>Uç Nokta Planı 1 için Defender (önizleme), yeni nesil koruma, saldırı yüzeyini azaltma, merkezi yönetim ve raporlama ve API'leri içeren bir uç nokta koruma çözümüdür. Uç Nokta Için Defender Plan 1 (önizleme), uç nokta koruma özelliklerimizi denemek, Microsoft 365 E3 sahip olmak ve henüz Microsoft 365 E5 sahip olmayan müşteriler için yeni bir tekliftir. 

   Daha fazla bilgi için bkz. [Plan 1 (önizleme) Uç Nokta için Microsoft Defender](defender-endpoint-plan-1.md). Mevcut [Uç Nokta için Defender özellikleri, Uç Nokta](microsoft-defender-endpoint.md) Için Defender Plan 2 olarak bilinir. 
- (Önizleme) [Web İçeriği Filtreleme](web-content-filtering.md)<br>  Web içeriği filtreleme, Uç Nokta için Microsoft Defender'daki web koruma özelliklerinin bir parçasıdır. Kuruluşunuzun web sitelerine erişimi içerik kategorilerine göre izlemesine ve düzenlemesine olanak tanır. Bu web sitelerinin çoğu kötü amaçlı olmasa da uyumluluk düzenlemeleri, bant genişliği kullanımı veya diğer endişeler nedeniyle sorunlu olabilir.

## <a name="july-2021"></a>Temmuz 2021

- (Önizleme) [Cihaz durumu ve uyumluluk raporu](machine-reports.md) <br>  Cihaz durumu ve uyumluluk raporu, kuruluşunuzdaki cihazlar hakkında üst düzey bilgiler sağlar.

## <a name="june-2021"></a>Haziran 2021

- [Delta dışarı aktarma yazılımı güvenlik açıkları değerlendirmesi](get-assessment-methods-properties.md#31-methods) Apı <br> [Güvenlik açıkları ve güvenli yapılandırmalar API'sinin dışarı aktarma değerlendirmelerine](get-assessment-methods-properties.md) ek olarak. <br> Kuruluşunuzun yazılım güvenlik açıkları değerlendirmesinin tüm anlık görüntüsünü cihaza göre almak için kullanılan tam yazılım güvenlik açıkları değerlendirmesinin (JSON yanıtı) aksine, delta dışarı aktarma API çağrısı yalnızca seçilen tarihle geçerli tarih ("delta" API çağrısı) arasında gerçekleşen değişiklikleri getirmek için kullanılır. Her seferinde büyük miktarda veriyle tam dışarı aktarma işlemi almak yerine yalnızca yeni, sabit ve güncelleştirilmiş güvenlik açıklarıyla ilgili belirli bilgileri alırsınız. Delta dışarı aktarma API'si çağrısı, "kaç güvenlik açığının düzeltildiği" veya "kuruluşa kaç yeni güvenlik açığı eklendiği" gibi farklı KPI'leri hesaplamak için de kullanılabilir.
- [Güvenlik açıklarının ve güvenli yapılandırmaların dışarı aktarma değerlendirmeleri](get-assessment-methods-properties.md) Apı <br> Defender Güvenlik Açığı Yönetimi verilerini cihaz başına çeken bir API koleksiyonu ekler. Farklı veri türlerini almak için farklı API çağrıları vardır: güvenli yapılandırma değerlendirmesi, yazılım envanteri değerlendirmesi ve yazılım güvenlik açıkları değerlendirmesi. Her API çağrısı, kuruluşunuzdaki cihazlar için gerekli verileri içerir.
- [Düzeltme etkinliği](get-remediation-methods-properties.md) Apı <br> Kiracınızda oluşturulan Defender Güvenlik Açığı Yönetimi düzeltme etkinliklerini içeren yanıtlara sahip bir API koleksiyonu ekler. Yanıt bilgi türleri kimliğe göre bir düzeltme etkinliği, tüm düzeltme etkinlikleri ve tek bir düzeltme etkinliğinin kullanıma sunulan cihazlarını içerir.
- [cihaz keşfi](device-discovery.md) <br> Ek gereçlere veya hantal işlem değişikliklerine gerek kalmadan kurumsal ağınıza bağlı yönetilmeyen cihazları bulmanıza yardımcı olur. Eklenen cihazları kullanarak ağınızda yönetilmeyen cihazları bulabilir, güvenlik açıklarını ve riskleri değerlendirebilirsiniz. Daha sonra ağınızda yönetilmeyen uç noktaların olmasıyla ilgili riskleri azaltmak için bulunan cihazları ekleyebilirsiniz.

   > [!IMPORTANT]
   > Standart bulma, 19 Temmuz 2021'den itibaren tüm müşteriler için varsayılan mod olacaktır. Ayarlar sayfasından temel modu korumayı seçebilirsiniz.

- [Cihaz grubu tanımları](/microsoft-365/security/defender-endpoint/machine-groups) artık her koşul için birden çok değer içerebilir. Tek bir cihaz grubunun tanımına birden çok etiket, cihaz adı ve etki alanı ayarlayabilirsiniz.
- [Mobil Uygulama yönetimi desteği](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> Bu geliştirme, mobil uygulamaları yönetmek için Intune kullanılırken bir kuruluşun yönetilen uygulama içindeki verilerinin Uç Nokta için Microsoft Defender korunmasını sağlar. Mobil uygulama yönetimi hakkında daha fazla bilgi için [bu belgelere bakın](/mem/intune/apps/mam-faq).
- [Microsoft Tunnel VPN tümleştirmesi](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> Microsoft Tunnel VPN özellikleri artık Android için Uç Nokta için Microsoft Defender uygulamasıyla tümleştirilmiştir. Bu birleştirme, kuruluşların tek bir güvenlik uygulamasıyla basitleştirilmiş bir son kullanıcı deneyimi sunabilmesini sağlar. Hem mobil tehdit savunması hem de mobil cihazlarından şirket içi kaynaklara erişim olanağı sunarken, güvenlik ve BT ekipleri de tanıdıkları yönetici deneyimlerini sürdürebiliyor.
- [iOS'ta jailbreak algılama](/microsoft-365/security/defender-endpoint/ios-configure-features#conditional-access-with-defender-for-endpoint-on-ios) <br> iOS'ta Uç Nokta için Microsoft Defender jailbreak algılama özelliği genel kullanıma sunuldu. Bu, zaten var olan kimlik avı korumasına eklenir.  Daha fazla bilgi için bkz. [Cihaz risk sinyallerine göre Koşullu Erişim İlkesi'ni ayarlama](/microsoft-365/security/defender-endpoint/ios-configure-features).


## <a name="march-2021"></a>Mart 2021
- [Microsoft 365 Defender portalını kullanarak kuruluşunuz için kurcalama korumasını yönetme](manage-tamper-protection-microsoft-365-defender.md) <br> *kiracı ekleme* adlı bir yöntemi kullanarak Windows 10, Windows Server 2016, Windows Server 2019 ve Windows Server 2022'de kurcalama koruma ayarlarını yönetebilirsiniz.


## <a name="january-2021"></a>Ocak 2021

- [Azure Sanal Masaüstü](https://azure.microsoft.com/services/virtual-desktop/) <br> Uç Nokta için Microsoft Defender artık Azure Sanal Masaüstü için destek ekliyor.
