---
title: Microsoft Endpoint Configuration Manager aracılığı ile katılım
description: Microsoft Endpoint Configuration Manager kullanarak Uç Nokta için Microsoft Defender eklemeyi öğrenin
keywords: ekleme, yapılandırma, dağıtma, dağıtım, uç nokta yapılandırma yöneticisi, Uç Nokta için Microsoft Defender, koleksiyon oluşturma, uç nokta algılama yanıtı, yeni nesil koruma, saldırı yüzeyi azaltma, microsoft uç nokta yapılandırma yöneticisi
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: bc950e1f850dab3a5d3474566145979be34b6ab9
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67688671"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager aracılığı ile katılım

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Bu makale Dağıtım kılavuzunun bir parçasıdır ve örnek ekleme yöntemi olarak görev yapar.

[Planlama](deployment-strategy.md) konusunda, cihazları hizmete eklemek için çeşitli yöntemler sağlanmıştır. Bu konu, ortak yönetim mimarisini kapsar.

:::image type="content" source="images/co-management-architecture.png" alt-text="Buluta özel mimari" lightbox="images/co-management-architecture.png":::
*Ortam mimarileri diyagramı*

Uç Nokta için Defender çeşitli uç noktaların ve araçların eklenip eklenmediğini desteklese de, bu makale bunları kapsamaz. Desteklenen diğer dağıtım araçlarını ve yöntemlerini kullanarak genel ekleme hakkında bilgi için bkz. [Eklemeye genel bakış](onboarding.md).

Bu konu, kullanıcılara şu konuda yol gösterir:

- 1. Adım: Windows cihazlarını hizmete ekleme
- 2. Adım: Uç Nokta için Defender özelliklerini yapılandırma

Bu ekleme kılavuzu, Microsoft Endpoint Configuration Manager kullanırken uygulamanız gereken aşağıdaki temel adımlarda size yol gösterecektir:

- **Microsoft Endpoint Configuration Manager'da koleksiyon oluşturma**
- **Microsoft Endpoint Configuration Manager kullanarak Uç Nokta için Microsoft Defender özelliklerini yapılandırma**

> [!NOTE]
> Bu örnek dağıtımda yalnızca Windows cihazları ele alınmıştır.

## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>1. Adım: Microsoft Endpoint Configuration Manager kullanarak Windows cihazlarını ekleme

### <a name="collection-creation"></a>Koleksiyon oluşturma

Windows cihazlarını Microsoft Endpoint Configuration Manager ile eklemek için dağıtım mevcut bir koleksiyonu hedefleyebilir veya test için yeni bir koleksiyon oluşturulabilir.

Grup ilkesi veya el ile yöntemi gibi araçları kullanarak ekleme işlemi sisteme herhangi bir aracı yüklemez.

Microsoft Endpoint Configuration Manager konsolunda, ekleme işlemi konsolundaki uyumluluk ayarlarının bir parçası olarak yapılandırılır.

Bu gerekli yapılandırmayı alan tüm sistem, Configuration Manager istemcisi bu ilkeyi yönetim noktasından almaya devam ettikçe bu yapılandırmayı korur.

Microsoft Endpoint Configuration Manager kullanarak uç noktaları eklemek için aşağıdaki adımları izleyin.

1. Microsoft Endpoint Configuration Manager konsolunda **Varlıklar ve Uyumluluğa \> Genel Bakış \> Cihaz Koleksiyonları'na** gidin.

    :::image type="content" source="images/configmgr-device-collections.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı1" lightbox="images/configmgr-device-collections.png":::

2. Cihaz **Koleksiyonu'nu** sağ seçin ve **Cihaz Koleksiyonu Oluştur'u** seçin.

    :::image type="content" source="images/configmgr-create-device-collection.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı2" lightbox="images/configmgr-create-device-collection.png":::

3. **Bir Ad** ve **Sınırlama Koleksiyonu** sağlayın ve **ardından İleri'yi** seçin.

    :::image type="content" source="images/configmgr-limiting-collection.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı3" lightbox="images/configmgr-limiting-collection.png":::

4. **Kural Ekle'yi** ve **ardından Sorgu Kuralı'nı** seçin.

    :::image type="content" source="images/configmgr-query-rule.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı4" lightbox="images/configmgr-query-rule.png":::

5. **Doğrudan Üyelik Sihirbazı'nda** **İleri'yi** ve **ardından Sorgu Deyimini Düzenle'yi** seçin.

    :::image type="content" source="images/configmgr-direct-membership.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı5" lightbox="images/configmgr-direct-membership.png":::

6. **Ölçütler'i** ve ardından yıldız simgesini seçin.

    :::image type="content" source="images/configmgr-criteria.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı6" lightbox="images/configmgr-criteria.png":::

7. Ölçüt türünü **basit bir değer** olarak tutun, **İşletim Sistemi - derleme numarası**, işleç olarak **14393** **değerinden büyük veya buna eşit olan** işleci seçin ve **Tamam'ı** seçin.

    :::image type="content" source="images/configmgr-simple-value.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı7" lightbox="images/configmgr-simple-value.png":::

8. **İleri** ve **Kapat'ı** seçin.

    :::image type="content" source="images/configmgr-membership-rules.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı8" lightbox="images/configmgr-membership-rules.png":::

9. **İleri**'yi seçin.

    :::image type="content" source="images/configmgr-confirm.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı9" lightbox="images/configmgr-confirm.png":::

Bu görevi tamamladıktan sonra, artık ortamdaki tüm Windows uç noktalarını içeren bir cihaz koleksiyonunuz olur.

## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>2. Adım: Uç Nokta için Microsoft Defender özelliklerini yapılandırma

Bu bölüm, Windows cihazlarda Microsoft Endpoint Configuration Manager kullanarak aşağıdaki özellikleri yapılandırma konusunda size yol gösterir:

- [**Uç nokta algılama ve yanıt**](#endpoint-detection-and-response)
- [**Yeni nesil koruma**](#next-generation-protection)
- [**Saldırı yüzeyini azaltma**](#attack-surface-reduction)

### <a name="endpoint-detection-and-response"></a>Uç nokta algılama ve yanıt

#### <a name="windows-10-and-windows-11"></a>Windows 10 ve Windows 11

Microsoft 365 Defender portalından, ilkeyi `.onboarding` System Center Configuration Manager oluşturmak ve bu ilkeyi Windows 10 ve Windows 11 cihazlara dağıtmak için kullanılabilecek ilkeyi indirmek mümkündür.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalından</a> [Ayarlar'ı ve ardından Ekleme'yi](https://security.microsoft.com/preferences2/onboarding) seçin.

2. Dağıtım yöntemi'nin altında **Microsoft Endpoint Configuration Manager'nin** desteklenen sürümünü seçin.

    :::image type="content" source="images/mdatp-onboarding-wizard.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı10" lightbox="images/mdatp-onboarding-wizard.png":::

3. **Paketi indir'i** seçin.

   :::image type="content" source="images/mdatp-download-package.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı11" lightbox="images/mdatp-download-package.png":::

4. Paketi erişilebilir bir konuma kaydedin.
5. Microsoft Endpoint Configuration Manager'da: **Varlıklar ve Uyumluluk > Genel Bakış > Endpoint Protection > Microsoft Defender ATP İlkeleri'ne** gidin.

6. **Microsoft Defender ATP İlkeleri'ne** sağ tıklayın ve **Microsoft Defender ATP İlkesi Oluştur'u** seçin.

    :::image type="content" source="images/configmgr-create-policy.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı12" lightbox="images/configmgr-create-policy.png":::

7. Adı ve açıklamayı girin, **Ekleme'nin** seçili olduğunu doğrulayın ve **ardından İleri'yi** seçin.

    :::image type="content" source="images/configmgr-policy-name.png" alt-text="Microsoft Endpoint Configuration Manager sihirbazı13" lightbox="images/configmgr-policy-name.png":::

8. **Gözat'ı** seçin.

9. Yukarıdaki 4. adımda indirilen dosyanın konumuna gidin.

10. **İleri**'yi seçin.
11. Aracıyı uygun örneklerle yapılandırın (**Hiçbiri** veya **Tümü dosya türleri**).

    :::image type="content" source="images/configmgr-config-settings.png" alt-text="Yapılandırma ayarları1" lightbox="images/configmgr-config-settings.png":::

12. Uygun telemetriyi (**Normal** veya **Hızlandırılmış**) ve ardından **İleri'yi** seçin.

    :::image type="content" source="images/configmgr-telemetry.png" alt-text="Yapılandırma ayarları2" lightbox="images/configmgr-telemetry.png":::

13. Yapılandırmayı doğrulayın ve **İleri'yi** seçin.

    :::image type="content" source="images/configmgr-verify-configuration.png" alt-text="Yapılandırma ayarları3" lightbox="images/configmgr-verify-configuration.png":::

14. Sihirbaz tamamlandığında **Kapat'ı** seçin.

15. Microsoft Endpoint Configuration Manager konsolunda, yeni oluşturduğunuz Uç Nokta için Defender ilkesine sağ tıklayın ve **Dağıt'ı** seçin.

    :::image type="content" source="images/configmgr-deploy.png" alt-text="Yapılandırma ayarları4" lightbox="images/configmgr-deploy.png":::

16. Sağ panelde, daha önce oluşturulan koleksiyonu seçin ve **Tamam'ı** seçin.

    :::image type="content" source="images/configmgr-select-collection.png" alt-text="Yapılandırma ayarları5" lightbox="images/configmgr-select-collection.png":::

#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Windows İstemcisi'nin önceki sürümleri (Windows 7 ve Windows 8.1)

Önceki Windows sürümlerinin eklenmesi için gerekli olan Uç Nokta için Defender Çalışma Alanı Kimliği ve Çalışma Alanı Anahtarı'nı belirlemek için aşağıdaki adımları izleyin.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalından</a> **Ayarlar** \> **Uç Noktaları** \> **Ekleme'yi** seçin (**Cihaz Yönetimi** altında).

2. İşletim sistemi bölümünde **Windows 7 SP1 ve 8.1'i** seçin.

3. **Çalışma Alanı Kimliği** ve **Çalışma Alanı Anahtarı'nı** kopyalayıp kaydedin. Bunlar işlemin ilerleyen bölümlerinde kullanılacaktır.

   :::image type="content" source="images/91b738e4b97c4272fd6d438d8c2d5269.png" alt-text="Ekleme işlemi" lightbox="images/91b738e4b97c4272fd6d438d8c2d5269.png":::

4. Microsoft Monitoring Agent'ı (MMA) yükleyin.

   MMA şu anda (Ocak 2019 itibariyle) aşağıdaki Windows İşletim Sistemlerinde desteklenmektedir:

   - Sunucu SKU'ları: Windows Server 2008 SP1 veya Daha Yeni
   - İstemci SKU'ları: Windows 7 SP1 ve üzeri

   MMA aracısının Windows cihazlarına yüklenmesi gerekir. Aracıyı yüklemek için bazı sistemlerin MMA ile veri toplamak [için Müşteri deneyimi ve tanılama telemetrisi için Güncelleştirme'yi](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) indirmesi gerekir. Bu sistem sürümleri şunları içerir ancak bunlarla sınırlı olmayabilir:

   - Windows 8.1
   - Windows 7
   - Windows Server 2016
   - Windows Server 2012 R2
   - Windows Server 2008 R2

   Özellikle, Windows 7 SP1 için aşağıdaki düzeltme eklerinin yüklenmesi gerekir:

   - [KB4074598'i](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598) yükleme
   - [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (veya üzeri) **veya** [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework) yükleyin. Her ikisini de aynı sisteme yüklemeyin.

5. İnternet'e bağlanmak için ara sunucu kullanıyorsanız Ara sunucu ayarlarını yapılandırma bölümüne bakın.

Tamamlandıktan sonra, bir saat içinde portalda eklenen uç noktaları görmeniz gerekir.

### <a name="next-generation-protection"></a>Yeni nesil koruma

Microsoft Defender Virüsten Koruma, masaüstleri, taşınabilir bilgisayarlar ve sunucular için yeni nesil koruma sağlayan yerleşik bir kötü amaçlı yazılımdan koruma çözümüdür.

1. Microsoft Endpoint Configuration Manager konsolunda **Varlıklar ve Uyumluluğa \> Genel Bakış \> Endpoint Protection \> Kötü Amaçlı Yazılımdan Koruma İlkeleri'ne** gidin ve **Kötü Amaçlı Yazılımdan Koruma İlkesi Oluştur'u** seçin.

   :::image type="content" source="images/9736e0358e86bc778ce1bd4c516adb8b.png" alt-text="Kötü amaçlı yazılımdan koruma ilkesi" lightbox="images/9736e0358e86bc778ce1bd4c516adb8b.png":::

2. **Zamanlanmış taramalar**, **Tarama ayarları**, **Varsayılan eylemler**, **Gerçek zamanlı koruma**, **Dışlama ayarları**, **Gelişmiş**, **Tehdit geçersiz kılmaları**, **Bulut Koruma Hizmeti** ve **Güvenlik bilgileri güncelleştirmeleri'ni** seçin ve **Tamam'ı** seçin.

   :::image type="content" source="images/1566ad81bae3d714cc9e0d47575a8cbd.png" alt-text="Yeni nesil koruma bölmesi1" lightbox="images/1566ad81bae3d714cc9e0d47575a8cbd.png":::

    Bazı sektörlerde veya bazı belirli kurumsal müşterilerin Virüsten Koruma'nın nasıl yapılandırıldığı konusunda belirli gereksinimleri olabilir.

    [Hızlı tarama ile tam tarama ve özel tarama karşılaştırması](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Daha fazla bilgi için bkz. [yapılandırma çerçevesi Windows Güvenliği](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework).
  
    :::image type="content" source="images/cd7daeb392ad5a36f2d3a15d650f1e96.png" alt-text="Yeni nesil koruma bölmesi2" lightbox="images/cd7daeb392ad5a36f2d3a15d650f1e96.png":::

    :::image type="content" source="images/36c7c2ed737f2f4b54918a4f20791d4b.png" alt-text="Yeni nesil koruma bölmesi3" lightbox="images/36c7c2ed737f2f4b54918a4f20791d4b.png":::

    :::image type="content" source="images/a28afc02c1940d5220b233640364970c.png" alt-text="Yeni nesil koruma bölmesi4" lightbox="images/a28afc02c1940d5220b233640364970c.png":::

    :::image type="content" source="images/5420a8790c550f39f189830775a6d4c9.png" alt-text="Yeni nesil koruma bölmesi5" lightbox="images/5420a8790c550f39f189830775a6d4c9.png":::

    :::image type="content" source="images/33f08a38f2f4dd12a364f8eac95e8c6b.png" alt-text="Yeni nesil koruma bölmesi6" lightbox="images/33f08a38f2f4dd12a364f8eac95e8c6b.png":::

    :::image type="content" source="images/41b9a023bc96364062c2041a8f5c344e.png" alt-text="Yeni nesil koruma bölmesi7" lightbox="images/41b9a023bc96364062c2041a8f5c344e.png":::

    :::image type="content" source="images/945c9c5d66797037c3caeaa5c19f135c.png" alt-text="Yeni nesil koruma bölmesi8" lightbox="images/945c9c5d66797037c3caeaa5c19f135c.png":::

    :::image type="content" source="images/3876ca687391bfc0ce215d221c683970.png" alt-text="Yeni nesil koruma bölmesi9" lightbox="images/3876ca687391bfc0ce215d221c683970.png":::

3. Yeni oluşturulan kötü amaçlı yazılımdan koruma ilkesine sağ tıklayın ve **Dağıt'ı** seçin.

    :::image type="content" source="images/f5508317cd8c7870627cb4726acd5f3d.png" alt-text="Yeni nesil koruma bölmesi10" lightbox="images/f5508317cd8c7870627cb4726acd5f3d.png":::

4. Yeni kötü amaçlı yazılımdan koruma ilkesini Windows koleksiyonunuzla hedefleyin ve **Tamam'ı** seçin.

    :::image type="content" source="images/configmgr-select-collection.png" alt-text="Yeni nesil koruma bölmesi11" lightbox="images/configmgr-select-collection.png":::

Bu görevi tamamladıktan sonra Microsoft Defender Virüsten Koruma'yı başarıyla yapılandırmış oldunuz.

### <a name="attack-surface-reduction"></a>Saldırı yüzeyini azaltma

Uç Nokta için Defender'ın saldırı yüzeyi azaltma sütunu Exploit Guard altında kullanılabilen özellik kümesini içerir. Saldırı yüzeyi azaltma (ASR) kuralları, Denetimli Klasör Erişimi, Ağ Koruması ve Exploit Protection.

Tüm bu özellikler bir test modu ve bir blok modu sağlar. Test modunda son kullanıcı etkisi yoktur. Tek yaptığı ek telemetri toplamak ve Microsoft 365 Defender portalında kullanılabilir hale getirmektir. Dağıtımın amacı, güvenlik denetimlerini adım adım blok moduna taşımaktır.

ASR kurallarını test modunda ayarlamak için:

1. Microsoft Endpoint Configuration Manager konsolunda **Varlıklar ve Uyumluluğa \> Genel Bakış \> Endpoint Protection \> Windows Defender Exploit Guard'a** gidin ve **Exploit Guard İlkesi Oluştur'u** seçin.

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="Microsoft Endpoint Configuration Manager console0" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. **Saldırı Yüzeyi Azaltma'ya** tıklayın.

3. Kuralları **Denetim** olarak ayarlayın ve **İleri'yi** seçin.

   :::image type="content" source="images/d18e40c9e60aecf1f9a93065cb7567bd.png" alt-text="Microsoft Endpoint Configuration Manager konsolu1" lightbox="images/d18e40c9e60aecf1f9a93065cb7567bd.png":::

4. **İleri'yi** seçerek yeni Exploit Guard ilkesini onaylayın.

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="Microsoft Endpoint Configuration Manager konsolu2" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. İlke oluşturulduktan sonra **Kapat'ı** seçin.

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="Microsoft Endpoint Configuration Manager konsolu3" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. Yeni oluşturulan ilkeye sağ tıklayın ve **Dağıt'ı** seçin.

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="Microsoft Endpoint Configuration Manager konsolu4" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::

7. İlkeyi yeni oluşturulan Windows koleksiyonuna hedefleyin ve **Tamam'ı** seçin.

   :::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="Microsoft Endpoint Configuration Manager konsolu5" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

Bu görevi tamamladıktan sonra asr kurallarını test modunda başarıyla yapılandırmış oldunuz.

AsR kurallarının uç noktalara doğru uygulanıp uygulanmadığını doğrulamaya yönelik ek adımlar aşağıdadır. (Bu işlem birkaç dakika sürebilir)

1. Web tarayıcısından <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> gidin.

2. Sol taraftaki menüden **Yapılandırma yönetimi'ne** tıklayın.

3. Saldırı **yüzeyi yönetimi panelinde Saldırı yüzeyi yönetimine git'i** seçin.

   :::image type="content" source="images/security-center-attack-surface-mgnt-tile.png" alt-text="Saldırı yüzeyi yönetimi" lightbox="images/security-center-attack-surface-mgnt-tile.png":::

4. Saldırı yüzeyi azaltma kuralları raporlarında **Yapılandırma** sekmesini seçin. Her cihazda ASR kuralları yapılandırmasına genel bakış ve ASR kuralları durumunu gösterir.

   :::image type="content" source="images/f91f406e6e0aae197a947d3b0e8b2d0d.png" alt-text="Saldırı yüzeyi azaltma kuralları raporları1" lightbox="images/f91f406e6e0aae197a947d3b0e8b2d0d.png":::

5. AsR kurallarının yapılandırma ayrıntılarını gösteren her cihazı seçin.

   :::image type="content" source="images/24bfb16ed561cbb468bd8ce51130ca9d.png" alt-text="Saldırı yüzeyi azaltma kuralları raporları2" lightbox="images/24bfb16ed561cbb468bd8ce51130ca9d.png":::

Daha fazla ayrıntı için bkz. [ASR kuralı dağıtım ve algılamalarını iyileştirme](/microsoft-365/security/defender-endpoint/configure-machines-asr) .

#### <a name="set-network-protection-rules-in-test-mode"></a>Test modunda Ağ Koruması kurallarını ayarlama

1. Microsoft Endpoint Configuration Manager konsolunda **Varlıklar ve Uyumluluğa \> Genel Bakış \> Endpoint Protection \> Windows Defender Exploit Guard'a** gidin ve **Exploit Guard İlkesi Oluştur'u** seçin.

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="The System Center Configuration Manager1" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. **Ağ koruması'ı** seçin.

3. Ayarı **Denetim** olarak ayarlayın ve **İleri'yi** seçin.

   :::image type="content" source="images/c039b2e05dba1ade6fb4512456380c9f.png" alt-text="The System Center Configuration Manager2" lightbox="images/c039b2e05dba1ade6fb4512456380c9f.png":::

4. **İleri'yi** seçerek yeni Exploit Guard İlkesi'ni onaylayın.

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="Exploit Guard ilkesi1" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. İlke oluşturulduktan sonra **Kapat'ı** seçin.

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="Exploit Guard ilkesi2" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. Yeni oluşturulan ilkeye sağ tıklayın ve **Dağıt'ı** seçin.

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="Microsoft Endpoint Configuration Manager-1" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::

7. Yeni oluşturulan Windows koleksiyonuna ilişkin ilkeyi seçin ve **Tamam'ı** seçin.

   :::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="Microsoft Endpoint Configuration Manager-2" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

Bu görevi tamamladıktan sonra ağ korumasını test modunda başarıyla yapılandırmış oldunuz.

#### <a name="to-set-controlled-folder-access-rules-in-test-mode"></a>Denetimli Klasör Erişimi kurallarını test modunda ayarlamak için

1. Microsoft Endpoint Configuration Manager konsolunda **Varlıklar ve Uyumluluğa** > **Genel Bakış** > **Endpoint Protection** >  **Windows Defender Exploit Guard'a** gidin ve **Exploit Guard İlkesi Oluştur'u** seçin.

   :::image type="content" source="images/728c10ef26042bbdbcd270b6343f1a8a.png" alt-text="Microsoft Endpoint Configuration Manager-3" lightbox="images/728c10ef26042bbdbcd270b6343f1a8a.png":::

2. **Denetimli klasör erişimi'ni** seçin.

3. Yapılandırmayı **Denetim** olarak ayarlayın ve **İleri'yi** seçin.

   :::image type="content" source="images/a8b934dab2dbba289cf64fe30e0e8aa4.png" alt-text="Microsoft Endpoint Configuration Manager-4" lightbox="images/a8b934dab2dbba289cf64fe30e0e8aa4.png":::

4. **İleri'yi** seçerek yeni Exploit Guard İlkesi'ni onaylayın.

   :::image type="content" source="images/0a6536f2c4024c08709cac8fcf800060.png" alt-text="Microsoft Endpoint Configuration Manager-5" lightbox="images/0a6536f2c4024c08709cac8fcf800060.png":::

5. İlke oluşturulduktan sonra **Kapat'ı** seçin.

   :::image type="content" source="images/95d23a07c2c8bc79176788f28cef7557.png" alt-text="Microsoft Endpoint Configuration Manager-6" lightbox="images/95d23a07c2c8bc79176788f28cef7557.png":::

6. Yeni oluşturulan ilkeye sağ tıklayın ve **Dağıt'ı** seçin.

   :::image type="content" source="images/8999dd697e3b495c04eb911f8b68a1ef.png" alt-text="Microsoft Endpoint Configuration Manager-7" lightbox="images/8999dd697e3b495c04eb911f8b68a1ef.png":::

7. İlkeyi yeni oluşturulan Windows koleksiyonuna hedefleyin ve **Tamam'ı** seçin.

:::image type="content" source="images/0ccfe3e803be4b56c668b220b51da7f7.png" alt-text="Microsoft Endpoint Configuration Manager-8" lightbox="images/0ccfe3e803be4b56c668b220b51da7f7.png":::

Denetimli klasör erişimini test modunda başarıyla yapılandırmış oldunuz.

## <a name="related-topic"></a>İlgili konu

- [Microsoft Endpoint Manager aracılığı ile katılım](onboarding-endpoint-manager.md)
