---
title: Uç Nokta için Microsoft Defender ekleme sorunlarını giderme
description: Cihazların veya Uç Nokta için Microsoft Defender hizmetine ekleme sırasında ortaya çıkabilecek sorunları giderin.
keywords: ekleme, ekleme sorunları, olay görüntüleyicisi, veri toplama ve önizleme derlemeleri, algılayıcı verileri ve tanılama sorunlarını giderme
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.subservice: mde
ms.openlocfilehash: fc870058e371e9bea23def223379055fb8ad7570
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67586390"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-onboarding-issues"></a>Uç Nokta için Microsoft Defender ekleme sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Windows Server 2012 R2
- Windows Server 2016
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Sorunlarla karşılaşırsanız Uç Nokta için Microsoft Defender ekleme işleminin sorunlarını gidermeniz gerekebilir.
Bu sayfa, dağıtım araçlarından biriyle dağıtım yaparken oluşabilecek ekleme sorunlarını ve cihazlarda oluşabilecek yaygın hataları gidermeye yönelik ayrıntılı adımlar sağlar.

Ekleme araçlarıyla ilgili sorunları gidermeye başlamadan önce, cihazları hizmetlere eklemeye yönelik en düşük gereksinimlerin karşılandığını kontrol etmek önemlidir. [Cihazları hizmete eklemek için lisans, donanım ve yazılım gereksinimleri hakkında bilgi edinin](minimum-requirements.md).

## <a name="troubleshoot-issues-with-onboarding-tools"></a>Ekleme araçlarıyla ilgili sorunları giderme

Ekleme işlemini tamamladıysanız ve bir saat sonra [Cihazlar listesinde](investigate-machines.md) cihazları görmüyorsanız, bu bir ekleme veya bağlantı sorununa işaret edebilir.

### <a name="troubleshoot-onboarding-when-deploying-with-group-policy"></a>grup ilkesi ile dağıtım yaparken ekleme sorunlarını giderme

grup ilkesi ile dağıtım, cihazlarda ekleme betiği çalıştırılarak gerçekleştirilir. grup ilkesi konsolu, dağıtımın başarılı olup olmadığını göstermez.

Ekleme işlemini tamamladıysanız ve cihazları bir saat sonra [Cihazlar listesinde](investigate-machines.md) görmüyorsanız, cihazlarda betiğin çıkışını de kontrol edebilirsiniz. Daha fazla bilgi için bkz. [Betikle dağıtım yaparken ekleme sorunlarını giderme](#troubleshoot-onboarding-when-deploying-with-a-script).

Betik başarıyla tamamlanırsa, oluşabilecek ek hatalar için [bkz. Cihazlarda ekleme sorunlarını giderme](#troubleshoot-onboarding-issues-on-the-device) .

### <a name="troubleshoot-onboarding-issues-when-deploying-with-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager ile dağıtım yaparken karşılaşılan ekleme sorunlarını giderme

Cihazları aşağıdaki Configuration Manager sürümlerini kullanarak ekleme yaparken:

- Microsoft Uç Noktası Yapılandırma Yöneticisi
- System Center 2012 Configuration Manager
- System Center 2012 R2 Configuration Manager

Configuration Manager'ın yukarıda bahsedilen sürümleriyle dağıtım, cihazlarda ekleme betiği çalıştırılarak gerçekleştirilir. Dağıtımı Configuration Manager Konsolu'nda izleyebilirsiniz.

Dağıtım başarısız olursa, cihazlarda betiğin çıkışını de kontrol edebilirsiniz.

Ekleme başarıyla tamamlandıysa ancak cihazlar bir saat sonra **Cihazlar listesinde** görünmüyorsa, oluşabilecek ek hatalar için [bkz. Cihazda ekleme sorunlarını giderme](#troubleshoot-onboarding-issues-on-the-device) .

### <a name="troubleshoot-onboarding-when-deploying-with-a-script"></a>Betikle dağıtım yaparken ekleme sorunlarını giderme

**Cihazdaki betiğin sonucunu denetleyin:**

1. **Başlat'a** tıklayın, **Olay Görüntüleyicisi** yazın ve **Enter tuşuna** basın.

2. **Windows Günlükleri** \> **Uygulaması'na** gidin.

3. **WDATPOnboarding** olay kaynağından bir olay arayın.

Betik başarısız olursa ve olay bir hataysa, sorunu gidermenize yardımcı olması için aşağıdaki tabloda olay kimliğini de kontrol edebilirsiniz.

> [!NOTE]
> Aşağıdaki olay kimlikleri yalnızca ekleme betiğine özeldir.

<br>

****

|Olay Kimliği|Hata Türü|Çözüm adımları|
|:---:|---|---|
|`5`|Çıkarma verileri bulundu ancak silinemedi|Özellikle kayıt defterindeki izinleri denetleyin <p> `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.|
|`10`|Ekleme verileri kayıt defterine yazılamıyor|Özellikle kayıt defterindeki izinleri denetleyin <p> `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`. <p> Betiğin yönetici olarak çalıştırıldığını doğrulayın.|
|`15`|SENSE hizmeti başlatılamadı|Hizmet durumunu denetleyin (`sc query sense` komut). Ara durumda olmadığından emin olun (*'Pending_Stopped'*, *'Pending_Running'*) ve betiği yeniden çalıştırmayı deneyin (yönetici haklarıyla). <p> Cihaz Windows 10, sürüm 1607 çalıştırıyorsa ve komutunu `sc query sense` `START_PENDING`çalıştırıyorsa, cihazı yeniden başlatın. Cihazı yeniden başlatmak sorunu çözmezse KB4015217'ye yükseltin ve yeniden eklemeyi deneyin.|
|`15`|SENSE hizmeti başlatılamadı|Hata iletisi şuysa: Sistem hatası 577 veya hata 1058 oluştu, Microsoft Defender Virüsten Koruma ELAM sürücüsünü etkinleştirmeniz gerekir. Yönergeler için microsoft [Defender Virüsten Koruma'nın bir ilke tarafından devre dışı bırakılmadığından emin olun](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) konusuna bakın.|
|`30`|Betik hizmetin çalışmaya başlamasını bekleyemedi|Hizmetin başlatılması daha fazla zaman alabilir veya başlatılmaya çalışılırken hatalarla karşılaşmış olabilir. SENSE ile ilgili olaylar ve hatalar hakkında daha fazla bilgi için bkz. [Olay görüntüleyicisini kullanarak olayları ve hataları gözden geçirme](event-error-codes.md).|
|`35`|Betik gerekli ekleme durumu kayıt defteri değerini bulamadı|SENSE hizmeti ilk kez başlatıldığında kayıt defteri konumuna ekleme durumu yazar <p> `HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`. <p> Betik birkaç saniye sonra bulamıyor. El ile test edebilir ve orada olup olmadığını kontrol edebilirsiniz. SENSE ile ilgili olaylar ve hatalar hakkında daha fazla bilgi için bkz. [Olay görüntüleyicisini kullanarak olayları ve hataları gözden geçirme](event-error-codes.md).|
|`40`|SENSE hizmeti ekleme durumu **1** olarak ayarlanmadı|SENSE hizmeti düzgün şekilde eklenmedi. SENSE ile ilgili olaylar ve hatalar hakkında daha fazla bilgi için bkz. [Olay görüntüleyicisini kullanarak olayları ve hataları gözden geçirme](event-error-codes.md).|
|`65`|Yetersiz ayrıcalıklar|Betiği yönetici ayrıcalıklarıyla yeniden çalıştırın.|
|

### <a name="troubleshoot-onboarding-issues-using-microsoft-intune"></a>Microsoft Intune kullanarak ekleme sorunlarını giderme

Hata kodlarını denetlemek ve sorunun nedenini gidermeye çalışmak için Microsoft Intune kullanabilirsiniz.

Intune'de ilkeler yapılandırdıysanız ve bunlar cihazlara yayılmadıysa, otomatik MDM kaydını yapılandırmanız gerekebilir.

Ekleme sırasında sorunların olası nedenlerini anlamak için aşağıdaki tabloları kullanın:

- Microsoft Intune hata kodları ve OMA-URIs tablosu
- Uyumsuzluk tablosuyla ilgili bilinen sorunlar
- Mobil Cihaz Yönetimi (MDM) olay günlükleri tablosu

Olay günlükleri ve sorun giderme adımlarından hiçbiri işe yaramazsa portalın **Cihaz yönetimi** bölümünden Yerel betiği indirin ve yükseltilmiş bir komut isteminde çalıştırın.

#### <a name="microsoft-intune-error-codes-and-oma-uris"></a>Hata kodlarını ve OMA-URIs Microsoft Intune

<br>

****

|Hata Kodu Onaltılık|Hata Kodu Ara|Hata Açıklaması|OMA-URI|Olası neden ve sorun giderme adımları|
|:---:|---|---|---|---|
|0x87D1FDE8|-2016281112|Düzeltme başarısız oldu|Ekleme <p> Çıkarma|**Olası neden:** Yanlış bir blobda ekleme veya çıkarma başarısız oldu: yanlış imza veya PreviousOrgIds alanları eksik. <p> **Sorun giderme adımları:** <p> [Cihaz olay günlüğü bölümündeki Aracı ekleme hatalarını görüntüleme bölümündeki olay](#view-agent-onboarding-errors-in-the-device-event-log) kimliklerini denetleyin. <p> Aşağıdaki tabloda yer alan MDM olay günlüklerini denetleyin veya [Windows'da MDM hatalarını tanılama](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) başlığındaki yönergeleri izleyin.|
||||Ekleme <p> Çıkarma <p> SampleSharing|**Olası neden:** Uç Nokta için Microsoft Defender İlke kayıt defteri anahtarı yok veya OMA DM istemcisinin bu anahtara yazma izni yok. <p> **Sorun giderme adımları:** Aşağıdaki kayıt defteri anahtarının mevcut olduğundan emin olun: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` <p> Yoksa, yükseltilmiş bir komut açın ve anahtarı ekleyin.|
||||SenseIsRunning <p> OnboardingState <p> Kuruluş Kimliği|**Olası neden:** Salt okunur özellik tarafından düzeltilmeye çalışılıyor. Ekleme başarısız oldu. <p> **Sorun giderme adımları:** [Cihazda ekleme sorunlarını giderme](#troubleshoot-onboarding-issues-on-the-device) sayfasındaki sorun giderme adımlarını gözden geçirin. <p> Aşağıdaki tabloda yer alan MDM olay günlüklerini denetleyin veya [Windows'da MDM hatalarını tanılama](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) başlığındaki yönergeleri izleyin.|
||||Tümü|**Olası neden:** Uç Nokta için Microsoft Defender, özellikle Holographic SKU'su olmak üzere desteklenmeyen SKU'ya/Platforma dağıtmayı deneme. <p> Şu anda desteklenen platformlar: <p> Enterprise, Education ve Professional.<p> Sunucu desteklenmiyor.|
|0x87D101A9|-2016345687|SyncML(425): gönderenin alıcı üzerinde yeterli erişim denetimi izinleri (ACL) olmadığından istenen komut başarısız oldu.|Tümü|**Olası neden:** Uç Nokta için Microsoft Defender, özellikle Holographic SKU'su olmak üzere desteklenmeyen SKU'ya/Platforma dağıtmayı deneme.<p> Şu anda desteklenen platformlar: <p> Enterprise, Education ve Professional.|
|

#### <a name="known-issues-with-non-compliance"></a>Uyumsuzlukla ilgili bilinen sorunlar

Aşağıdaki tabloda uyumsuzlukla ilgili sorunlar ve sorunları nasıl giderebileceğiniz hakkında bilgi sağlanmaktadır.

<br>

****

|Durumda|Belirtiler|Olası neden ve sorun giderme adımları|
|:---:|---|---|
|`1`|Cihaz, SenseIsRunning OMA-URI ile uyumludur. Ancak OrgId, Onboarding ve OnboardingState OMA-URI'leri ile uyumlu değildir.|**Olası neden:** Windows yükleme veya yükseltme işleminden sonra kullanıcının OOBE'i geçirerek geçirmediğini denetleyin. OOBE ekleme işlemi tamamlanamadı ancak SENSE zaten çalışıyor. <p> **Sorun giderme adımları:** OOBE'nin tamamlanmasını bekleyin.|
|`2`|Cihaz OrgId, Onboarding ve OnboardingState OMA-URI'leri ile uyumludur, ancak SenseIsRunning OMA-URI'leri tarafından uyumlu değildir.|**Olası neden:** Sense hizmetinin başlangıç türü "Gecikmeli Başlangıç" olarak ayarlanır. Bazen bu durum, sistem başlangıcında DM oturumu gerçekleştiğinde Microsoft Intune sunucusunun cihazı SenseIsRunning tarafından uyumsuz olarak bildirmesine neden olur. <p> **Sorun giderme adımları:** Sorun 24 saat içinde otomatik olarak düzeltilmelidir.|
|`3`|Cihaz uyumlu değil|**Sorun giderme adımları:** Ekleme ve Çıkarma ilkelerinin aynı cihazda aynı anda dağıtılmadığından emin olun.|
|

#### <a name="mobile-device-management-mdm-event-logs"></a>Mobil Cihaz Yönetimi (MDM) olay günlükleri

Ekleme sırasında ortaya çıkabilecek sorunları gidermek için MDM olay günlüklerini görüntüleyin:

Günlük adı: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider

Kanal adı: Yönetici

<br>

****

|Kimlik|Önem derecesi|Olay açıklaması|Sorun giderme adımları|
|---|---|---|---|
|1819|Error|Uç Nokta için Microsoft Defender CSP: Düğümün Değeri Ayarlanamadı. NodeId: (%1), TokenName: (%2), Sonuç: (%3).|[Windows 10 1607 toplu güncelleştirmesini](https://go.microsoft.com/fwlink/?linkid=829760) indirin.|
|

## <a name="troubleshoot-onboarding-issues-on-the-device"></a>Cihazda ekleme sorunlarını giderme

Kullanılan dağıtım araçları ekleme işlemindeki bir hatayı göstermiyorsa ancak cihazlar bir saat içinde cihaz listesinde görünmemeye devam ediyorsa, Uç Nokta için Microsoft Defender aracısında bir hata oluşup oluşmadığını denetlemek için aşağıdaki doğrulama konularını inceleyin.

- [Cihaz olay günlüğünde aracı ekleme hatalarını görüntüleme](#view-agent-onboarding-errors-in-the-device-event-log)
- [Tanılama veri hizmetinin etkinleştirildiğinden emin olun](#ensure-the-diagnostics-service-is-enabled)
- [Hizmetin başlatacak şekilde ayarlandığından emin olun](#ensure-the-service-is-set-to-start)
- [Cihazın İnternet bağlantısı olduğundan emin olun](#ensure-the-device-has-an-internet-connection)
- [Microsoft Defender Virüsten Koruma'nın bir ilke tarafından devre dışı bırakılmadığından emin olun](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

### <a name="view-agent-onboarding-errors-in-the-device-event-log"></a>Cihaz olay günlüğünde aracı ekleme hatalarını görüntüleme

1. **Başlat'a** tıklayın, **Olay Görüntüleyicisi** yazın ve **Enter tuşuna** basın.

2. **Olay Görüntüleyicisi (Yerel)** bölmesinde, **Microsoft** \> **Windows** \> **SENSE** **Uygulama ve Hizmet Günlükleri'ni** \> genişletin.

   > [!NOTE]
   > SENSE, Uç Nokta için Microsoft Defender destekleyen davranış algılayıcısına başvurmak için kullanılan iç addır.

3. Günlüğü yüklemek için **İşletimsel'i** seçin.

4. **Eylem** bölmesinde **Geçerli Günlüğü Filtrele'ye** tıklayın.

5. **Filtre** sekmesinde, **Olay düzeyi:** altında **Kritik**, **Uyarı** ve **Hata'yı** seçin ve **Tamam'a** tıklayın.

   :::image type="content" source="images/filter-log.png" alt-text="Olay Görüntüleyicisi günlük filtresi" lightbox="images/filter-log.png":::

6. Sorunları gösterebilen olaylar **İşletim** bölmesinde görünür. Aşağıdaki tabloda yer alan çözümleri temel alarak sorun gidermeye çalışabilirsiniz:

   <br>

   ****

   |Olay Kimliği|İleti|Çözüm adımları|
   |:---:|---|---|
   |`5`|Uç Nokta için Microsoft Defender hizmeti _değişkende_ sunucuya bağlanamadı|[Cihazın İnternet erişimi olduğundan emin olun](#ensure-the-device-has-an-internet-connection).|
   |`6`|Uç Nokta için Microsoft Defender hizmeti eklenmedi ve ekleme parametresi bulunamadı. Hata kodu: _değişken_|[Ekleme betiğini yeniden çalıştırın](configure-endpoints-script.md).|
   |`7`|Uç Nokta için Microsoft Defender hizmeti ekleme parametrelerini okuyamadı. Hata kodu: _değişken_|[Cihazın İnternet erişimi olduğundan emin olun](#ensure-the-device-has-an-internet-connection), ardından ekleme işleminin tamamını yeniden çalıştırın.|
   |`9`|Uç Nokta için Microsoft Defender hizmeti başlangıç türünü değiştiremedi. Hata kodu: değişken|Olay ekleme sırasında gerçekleştiyse, yeniden başlatın ve ekleme betiğini çalıştırmayı yeniden deneme. Daha fazla bilgi için bkz. [Ekleme betiğini yeniden çalıştırma](configure-endpoints-script.md). <br><br>Olay çıkarma sırasında gerçekleştiyse desteğe başvurun.|
   |`10`|Uç Nokta için Microsoft Defender hizmeti ekleme bilgilerini kalıcı hale alamadı. Hata kodu: değişken|Olay ekleme sırasında gerçekleştiyse, ekleme betiğini çalıştırmayı yeniden deneme. Daha fazla bilgi için bkz. [Ekleme betiğini yeniden çalıştırma](configure-endpoints-script.md). <br><br>Sorun devam ederse desteğe başvurun.|
   |`15`|Uç Nokta için Microsoft Defender URL ile komut kanalı başlatılamıyor: _değişken_|[Cihazın İnternet erişimi olduğundan emin olun](#ensure-the-device-has-an-internet-connection).|
   |`17`|Uç Nokta için Microsoft Defender hizmeti Bağlı Kullanıcı Deneyimleri ve Telemetri hizmeti konumunu değiştiremedi. Hata kodu: değişken|[Ekleme betiğini yeniden çalıştırın](configure-endpoints-script.md). Sorun devam ederse desteğe başvurun.|
   |`25`|Uç Nokta için Microsoft Defender hizmeti kayıt defterinde sistem durumunu sıfırlayamadı. Hata kodu: _değişken_|Desteğe başvurun.|
   |`27`|Windows Defender'da Uç Nokta için Microsoft Defender modu etkinleştiremedi. Ekleme işlemi başarısız oldu. Hata kodu: değişken|Desteğe başvurun.|
   |`29`|Çıkarma parametreleri okunamadı. Hata türü: %1, Hata kodu: %2, Açıklama: %3|Cihazın İnternet erişimi olduğundan emin olun, ardından tüm çıkarma işlemini yeniden çalıştırın.|
   |`30`|$(build.sense.productDisplayName) modu Uç Nokta için Microsoft Defender devre dışı bırakılamadı. Hata kodu: %1|Desteğe başvurun.|
   |`32`|$(build.sense.productDisplayName) hizmeti, çıkarma işleminden sonra kendisini durdurma isteğinde bulunamadı. Hata kodu: %1|Hizmet başlangıç türünün el ile olduğunu doğrulayın ve cihazı yeniden başlatın.|
   |`55`|Güvenli ETW otomatik günlükçü oluşturulamadı. Hata kodu: %1|Cihazı yeniden başlatın.|
   |`63`|Dış hizmetin başlangıç türü güncelleştiriliyor. Ad: %1, gerçek başlangıç türü: %2, beklenen başlangıç türü: %3, çıkış kodu: %4|Belirtilen hizmetin başlangıç türündeki değişikliklere neyin neden olduğunu belirleyin. Çıkış kodu 0 değilse, başlangıç türünü el ile beklenen başlangıç türüne düzeltin.|
   |`64`|Dış hizmeti başlatma durduruldu. Ad: %1, çıkış kodu: %2|Olay yeniden görüntülenmeye devam ederse desteğe başvurun.|
   |`68`|Hizmetin başlangıç türü beklenmeyen bir durumdur. Hizmet adı: %1, gerçek başlangıç türü: %2, beklenen başlangıç türü: %3|Başlangıç türündeki değişikliklere neyin neden olduğunu belirleyin. Bahsedilen hizmet başlangıç türü düzeltildi.|
   |`69`|Hizmet durduruldu. Hizmet adı: %1|Belirtilen hizmeti başlatın. Devam ederse desteğe başvurun.|
   |

Cihazda, Uç Nokta için Microsoft Defender aracısının düzgün çalışması için bağımlı olduğu ek bileşenler vardır. Uç Nokta için Microsoft Defender aracısı olay günlüğünde eklemeyle ilgili hata yoksa, ek bileşenlerin doğru yapılandırıldığından emin olmak için aşağıdaki adımlarla devam edin.

<span id="ensure-the-diagnostics-service-is-enabled" />

### <a name="ensure-the-diagnostic-data-service-is-enabled"></a>Tanılama veri hizmetinin etkinleştirildiğinden emin olun

Cihazlar doğru bildirmiyorsa, Windows tanılama veri hizmetinin otomatik olarak başlatacak şekilde ayarlanıp ayarlanmadığını ve cihazda çalıştığını denetlemeniz gerekebilir. Hizmet, diğer programlar veya kullanıcı yapılandırması değişiklikleri tarafından devre dışı bırakılmış olabilir.

İlk olarak, Windows başlatıldığında hizmetin otomatik olarak başlayacak şekilde ayarlanıp ayarlanmadığını denetlemeli, ardından hizmetin şu anda çalıştığını denetlemeli (ve çalışmıyorsa başlatmalısınız).

### <a name="ensure-the-service-is-set-to-start"></a>Hizmetin başlatacak şekilde ayarlandığından emin olun

**Windows tanılama veri hizmeti başlangıç türünü denetlemek için komut satırını kullanın**:

1. Cihazda yükseltilmiş bir komut satırı istemi açın:

   a. **Başlat'a** tıklayın, **cmd** yazın ve **Enter tuşuna** basın.

   b. **Komut istemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.

2. Aşağıdaki komutu girin ve **Enter tuşuna** basın:

   ```console
   sc qc diagtrack
   ```

   Hizmet etkinse sonuç aşağıdaki ekran görüntüsüne benzer olmalıdır:

   :::image type="content" source="images/windefatp-sc-qc-diagtrack.png" alt-text="Diagtrack için sc query komutunun sonucu" lightbox="images/windefatp-sc-qc-diagtrack.png":::

   `START_TYPE` olarak ayarlanmadıysa`AUTO_START`, hizmeti otomatik olarak başlatacak şekilde ayarlamanız gerekir.

**Windows tanılama veri hizmetini otomatik olarak başlatacak şekilde ayarlamak için komut satırını kullanın:**

1. Cihazda yükseltilmiş bir komut satırı istemi açın:

   a. **Başlat'a** tıklayın, **cmd** yazın ve **Enter tuşuna** basın.

   b. **Komut istemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.

2. Aşağıdaki komutu girin ve **Enter tuşuna** basın:

   ```console
   sc config diagtrack start=auto
   ```

3. Başarılı iletisi görüntülenir. Aşağıdaki komutu girerek değişikliği doğrulayın ve **Enter tuşuna** basın:

   ```console
   sc qc diagtrack
   ```

4. Hizmeti başlatın. Komut isteminde aşağıdaki komutu yazın ve **Enter tuşuna** basın:

   ```console
   sc start diagtrack
   ```

### <a name="ensure-the-device-has-an-internet-connection"></a>Cihazın İnternet bağlantısı olduğundan emin olun

Uç Nokta için Microsoft Defender algılayıcısı, algılayıcı verilerini raporlamak ve Uç Nokta için Microsoft Defender hizmetiyle iletişim kurmak için Microsoft Windows HTTP (WinHTTP) gerektirir.

WinHTTP, İnternet'e göz atma proxy ayarlarından ve diğer kullanıcı bağlamı uygulamalarından bağımsızdır ve kendi ortamınızda bulunan proxy sunucularını algılayabilmelidir.

Algılayıcının hizmet bağlantısı olduğundan emin olmak için Uç Nokta için Microsoft Defender [hizmet URL'lerine istemci bağlantısını doğrulama](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls) konusunda açıklanan adımları izleyin.

Doğrulama başarısız olursa ve ortamınız İnternet'e bağlanmak için ara sunucu kullanıyorsa Ara [sunucu ve İnternet bağlantı ayarlarını yapılandırma](configure-proxy-internet.md) konusunda açıklanan adımları izleyin.

### <a name="ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy"></a>Microsoft Defender Virüsten Koruma'nın bir ilke tarafından devre dışı bırakılmadığından emin olun

> [!IMPORTANT]
> Aşağıdakiler yalnızca Microsoft Defender Virüsten Koruma için Ağustos 2020 (sürüm 4.18.2007.8) güncelleştirmesini henüz **almamış** cihazlar için geçerlidir.
>
> Güncelleştirme, Microsoft Defender Virüsten Koruma'nın sistem ilkesi aracılığıyla istemci cihazlarda kapatılmamasını sağlar.

**Sorun**: Uç Nokta için Microsoft Defender hizmeti eklendikten sonra başlatılmıyor.

**Belirti**: Ekleme başarıyla tamamlanır, ancak hizmeti başlatmaya çalışırken hata 577 veya hata 1058'i görürsünüz.

**Çözüm**: Cihazlarınız üçüncü taraf kötü amaçlı yazılımdan koruma istemcisi çalıştırıyorsa, Uç Nokta için Microsoft Defender aracısının Erken Başlatma Kötü Amaçlı Yazılımdan Koruma (ELAM) sürücüsünün etkinleştirilmesi gerekir. Bir sistem ilkesi tarafından kapatılmadığından emin olmanız gerekir.

- İlkeleri uygulamak için kullandığınız ara çubuğuna bağlı olarak, aşağıdaki Windows Defender ilkelerinin temizlendiğini doğrulamanız gerekir:

  - DisableAntiSpyware
  - DisableAntiVirus

  Örneğin, grup ilkesi aşağıdaki değerler gibi girdiler olmamalıdır:

  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiSpyware"/></Key>`
  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiVirus"/></Key>`

> [!IMPORTANT]
> Ayar `disableAntiSpyware` sonlandırılır ve Ağustos 2020 (sürüm 4.18.2007.8) Microsoft Defender Virüsten Koruma güncelleştirmesi itibarıyla tüm Windows 10 cihazlarda yoksayılır.

- İlkeyi temizledikten sonra ekleme adımlarını yeniden çalıştırın.

- Ayrıca, kayıt defteri anahtarını açarak ilkenin devre dışı bırakıldığını doğrulamak için önceki kayıt defteri anahtarı `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`değerlerini de de de kontrol edebilirsiniz.

  :::image type="content" source="images/atp-disableantispyware-regkey.png" alt-text="Microsoft Defender Virüsten Koruma için kayıt defteri anahtarı" lightbox="images/atp-disableantispyware-regkey.png":::

   > [!NOTE]
   > Tüm Windows Defender hizmetleri (wdboot, wdfilter, wdnisdrv, wdnissvc ve windefend) varsayılan durumunda olmalıdır. Bu hizmetlerin başlatılmasını değiştirmek desteklenmez ve sisteminizi yeniden kullanmaya zorlayabilir.
   >
   > WdBoot ve WdFilter için örnek varsayılan yapılandırmalar:
   >
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdBoot"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdFilter"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`

## <a name="troubleshoot-onboarding-issues"></a>Katılım sorunlarını giderin 

> [!NOTE]
> Aşağıdaki sorun giderme kılavuzu yalnızca Windows Server 2016 ve daha düşük sürümler için geçerlidir.

Sunucu eklerken sorunlarla karşılaşırsanız olası sorunları çözmek için aşağıdaki doğrulama adımlarını izleyin.


- [Microsoft Monitoring Agent'ın (MMA) yüklü olduğundan ve algılayıcı verilerini hizmete bildirecek şekilde yapılandırıldığından emin olun](configure-server-endpoints.md)
- [Sunucu ara sunucusu ve İnternet bağlantı ayarlarının düzgün yapılandırıldığından emin olun](configure-server-endpoints.md)

Aşağıdakileri de denetlemeniz gerekebilir:

- **Görev Yöneticisi'nin** **İşlemler** sekmesinde çalışan bir Uç Nokta için Microsoft Defender Hizmeti olup olmadığını denetleyin. Örneğin:

  :::image type="content" source="images/atp-task-manager.png" alt-text="Uç Nokta için Microsoft Defender Hizmeti'nin çalıştığı işlem görünümü" lightbox="images/atp-task-manager.png":::

- Herhangi **bir** \> hata olup olmadığını görmek için **Uygulama ve Hizmet Günlükleri** \> **İşlem Yöneticisi'Olay Görüntüleyicisi** denetleyin.

- **Hizmetler'de** **Microsoft Monitoring Agent'ın** sunucuda çalıştırılıp çalıştırılamadığını denetleyin. Örneğin,

  :::image type="content" source="images/atp-services.png" alt-text="Hizmetler" lightbox="images/atp-services.png":::

- **Microsoft Monitoring Agent** \> **Azure Log Analytics'te (OMS)** Çalışma Alanları'nı denetleyin ve durumun çalıştığını doğrulayın.

  :::image type="content" source="images/atp-mma-properties.png" alt-text="Microsoft Monitoring Agent Özellikleri" lightbox="images/atp-mma-properties.png":::

- Cihazların portaldaki **Cihazlar listesine** yansıtıldığını denetleyin.

## <a name="confirming-onboarding-of-newly-built-devices"></a>Yeni oluşturulan cihazların eklenmesini onaylama

Ekleme yeni oluşturulan bir cihaza dağıtıldığında ancak tamamlanmadığında örnekler olabilir.

Aşağıdaki adımlar aşağıdaki senaryo için rehberlik sağlar:

- Ekleme paketi yeni oluşturulan cihazlara dağıtılır
- İlk çalıştırma deneyimi (OOBE) veya ilk kullanıcı oturum açma işlemi tamamlanmadığından algılayıcı başlatılamıyor
- Son kullanıcı ilk oturum açma işlemini gerçekleştirmeden önce cihaz kapatılır veya yeniden başlatılır
- Bu senaryoda, ekleme paketi dağıtılsa bile SENSE hizmeti otomatik olarak başlatılmaz

> [!NOTE]
> SENSE hizmetinin şu veya daha yeni Windows sürümlerinde başlaması için OOBE'den sonra Kullanıcı Oturumu Açma artık gerekli değildir: Windows 10, sürüm 1809 veya Windows Server 2019 ya da [22 Nisan 2021 güncelleştirme paketiyle Windows Server 2022](https://support.microsoft.com/kb/5001384). Windows 10, [Nisan 2021 güncelleştirme paketi ile sürüm 1909](https://support.microsoft.com/kb/5001396). Windows 10, sürüm 2004/20H2 ile [28 Nisan 2021 güncelleştirme paketi](https://support.microsoft.com/kb/5001391). 


> [!NOTE]
> Aşağıdaki adımlar yalnızca Microsoft Endpoint Configuration Manager kullanılırken geçerlidir. Microsoft Endpoint Configuration Manager kullanarak ekleme hakkında daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection).

1. Microsoft Endpoint Configuration Manager'de bir uygulama oluşturun.

   :::image type="content" source="images/mecm-1.png" alt-text="Microsoft Endpoint Configuration Manager configuration-1" lightbox="images/mecm-1.png":::

2. **Uygulama bilgilerini el ile belirtin'i** seçin.

   :::image type="content" source="images/mecm-2.png" alt-text="Microsoft Endpoint Configuration Manager configuration-2" lightbox="images/mecm-2.png":::

3. Uygulama hakkında bilgi belirtin ve **İleri'yi** seçin.

   :::image type="content" source="images/mecm-3.png" alt-text="Microsoft Endpoint Configuration Manager configuration-3" lightbox="images/mecm-3.png":::

4. Yazılım merkezi hakkında bilgi belirtin ve **İleri'yi** seçin.

   :::image type="content" source="images/mecm-4.png" alt-text="Microsoft Endpoint Configuration Manager configuration-4" lightbox="images/mecm-4.png":::

5. **Dağıtım türleri'nde** **Ekle'yi** seçin.

   :::image type="content" source="images/mecm-5.png" alt-text="Microsoft Endpoint Configuration Manager yapılandırması-5" lightbox="images/mecm-5.png":::

6. **Dağıtım türü bilgilerini el ile belirtin'i** ve ardından **İleri'yi** seçin.

   :::image type="content" source="images/mecm-6.png" alt-text="Microsoft Endpoint Configuration Manager configuration-6" lightbox="images/mecm-6.png":::

7. Dağıtım türü hakkında bilgi belirtin ve **İleri'yi** seçin.

   :::image type="content" source="images/mecm-7.png" alt-text="Microsoft Endpoint Configuration Manager configuration-7" lightbox="images/mecm-7.png":::

8. **İçerik** \> **Yükleme programında** şu komutu belirtin: `net start sense`.

   :::image type="content" source="images/mecm-8.png" alt-text="Microsoft Endpoint Configuration Manager configuration-8" lightbox="images/mecm-8.png":::

9. **Algılama yöntemi'nde** **Bu dağıtım türünün varlığını algılamak için Kuralları yapılandır'ı** ve ardından **Yan Tümce Ekle'yi** seçin.

   :::image type="content" source="images/mecm-9.png" alt-text="Microsoft Endpoint Configuration Manager configuration-9" lightbox="images/mecm-9.png":::

10. Aşağıdaki algılama kuralı ayrıntılarını belirtin ve **tamam'ı** seçin:

    :::image type="content" source="images/mecm-10.png" alt-text="Microsoft Endpoint Configuration Manager configuration-10" lightbox="images/mecm-10.png":::

11. **Algılama yöntemi'nde** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-11.png" alt-text="Microsoft Endpoint Configuration Manager configuration-11" lightbox="images/mecm-11.png":::

12. **Kullanıcı Deneyimi'nde** aşağıdaki bilgileri belirtin ve **İleri'yi** seçin:

    :::image type="content" source="images/mecm-12.png" alt-text="Microsoft Endpoint Configuration Manager configuration-12" lightbox="images/mecm-12.png":::

13. **Gereksinimler'de** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-13.png" alt-text="Microsoft Endpoint Configuration Manager yapılandırması-13" lightbox="images/mecm-13.png":::

14. **Bağımlılıklar'da** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-14.png" alt-text="Microsoft Endpoint Configuration Manager configuration-14" lightbox="images/mecm-14.png":::

15. **Özet'te** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-15.png" alt-text="Microsoft Endpoint Configuration Manager yapılandırması-15" lightbox="images/mecm-15.png":::

16. **Tamamlama** bölümünde **Kapat'ı** seçin.

    :::image type="content" source="images/mecm-16.png" alt-text="Microsoft Endpoint Configuration Manager configuration-16" lightbox="images/mecm-16.png":::

17. **Dağıtım türleri'nde** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-17.png" alt-text="Microsoft Endpoint Configuration Manager configuration-17" lightbox="images/mecm-17.png":::

18. **Özet'te** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-18.png" alt-text="Microsoft Endpoint Configuration Manager yapılandırması-18" lightbox="images/mecm-18.png":::

    Durum daha sonra görüntülenir: :::image type="content" source="images/mecm-19.png" alt-text="Microsoft Endpoint Configuration Manager configuration-19" lightbox="images/mecm-19.png":::

19. **Tamamlama** bölümünde **Kapat'ı** seçin.

    :::image type="content" source="images/mecm-20.png" alt-text="Microsoft Endpoint Configuration Manager configuration-20" lightbox="images/mecm-20.png":::

20. Artık uygulamaya sağ tıklayıp Dağıt'ı seçerek uygulamayı **dağıtabilirsiniz**.

    :::image type="content" source="images/mecm-21.png" alt-text="Microsoft Endpoint Configuration Manager configuration-21" lightbox="images/mecm-21.png":::

21. **Genel'de** **Bağımlılıklar için içeriği otomatik olarak dağıt'ı** ve **Gözat'ı** seçin.

    :::image type="content" source="images/mecm-22.png" alt-text="Microsoft Endpoint Configuration Manager configuration-22" lightbox="images/mecm-22.png":::

22. **İçerik'te** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-23.png" alt-text="Microsoft Endpoint Configuration Manager yapılandırması-23" lightbox="images/mecm-23.png":::

23. **Dağıtım ayarları'nda** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-24.png" alt-text="Microsoft Endpoint Configuration Manager configuration-24" lightbox="images/mecm-24.png":::

24. **Zamanlama'da****, kullanılabilir süreden sonra mümkün olan en kısa sürede** seçeneğini belirleyin ve ardından **İleri'yi** seçin.

    :::image type="content" source="images/mecm-25.png" alt-text="Microsoft Endpoint Configuration Manager configuration-25" lightbox="images/mecm-25.png":::

25. **Kullanıcı deneyimi** bölümünde **Değişiklikleri son tarihe veya bakım penceresi sırasında işle (yeniden başlatma gerektirir)** seçeneğini belirleyin ve **ardından İleri'yi** seçin.

    :::image type="content" source="images/mecm-26.png" alt-text="Microsoft Endpoint Configuration Manager configuration-26" lightbox="images/mecm-26.png":::

26. **Uyarılar'da** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-27.png" alt-text="Microsoft Endpoint Configuration Manager configuration-27" lightbox="images/mecm-27.png":::

27. **Özet'te** **İleri'yi** seçin.

    :::image type="content" source="images/mecm-28.png" alt-text="Microsoft Endpoint Configuration Manager configuration-28" lightbox="images/mecm-28.png":::
      

    Durum daha sonra Görüntülenir :::image type="content" source="images/mecm-29.png" alt-text="Microsoft Endpoint Configuration Manager configuration-29" lightbox="images/mecm-29.png":::

28. **Tamamlama** bölümünde **Kapat'ı** seçin.

    :::image type="content" source="images/mecm-30.png" alt-text="Microsoft Endpoint Configuration Manager configuration-30" lightbox="images/mecm-30.png":::

## <a name="related-topics"></a>İlgili konular

- [sorun giderme Uç Nokta için Microsoft Defender](troubleshoot-mdatp.md)
- [Cihazları ekleme](onboard-configure.md)
- [Cihaz ara sunucusu ve İnternet bağlantısı ayarlarını yapılandırma](configure-proxy-internet.md)
