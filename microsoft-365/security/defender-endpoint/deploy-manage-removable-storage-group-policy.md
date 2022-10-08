---
title: Grup ilkesini kullanarak Çıkarılabilir Depolama Access Control dağıtma ve yönetme
description: Çıkarılabilir depolama erişim denetimini dağıtmak ve yönetmek için grup ilkesini kullanın.
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.date: 09/09/2022
ms.reviewer: tewchen
search.appverid: met150
ms.openlocfilehash: 947388cd2840c94e7faeb956d3fcaac309303307
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68174940"
---
# <a name="deploy-and-manage-removable-storage-access-control-using-group-policy"></a>Grup ilkesini kullanarak Çıkarılabilir Depolama Access Control dağıtma ve yönetme

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> Bu ürünün grup ilkesi yönetimi ve Intune OMA-URI/Özel İlke yönetimi genel kullanıma sunuldu (4.18.2106): [Teknik Topluluk blogu: Çıkarılabilir depolama alanınızı ve yazıcınızı Uç Nokta için Microsoft Defender ile koruma](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806).

Çıkarılabilir Depolama Birimi Access Control özelliği, kullanıcı veya cihaza ya da her ikisine grup ilkesi kullanarak bir ilke uygulamanıza olanak tanır.

## <a name="device-control-removable-storage-access-control-policies"></a>Cihaz Denetimi Çıkarılabilir Depolama birimi Access Control ilkeleri

Çıkarılabilir bir depolama grubu oluşturmak için aşağıdaki özellikleri kullanabilirsiniz.

> [!NOTE]
> XML açıklama gösterimini `<!-- COMMENT -->` kullanan açıklamalar Kural ve Grup XML dosyalarında kullanılabilir, ancak XML dosyasının ilk satırının değil ilk XML etiketinin içinde olmalıdır.

## <a name="licensing-requirements"></a>Lisans gereksinimleri

Çıkarılabilir Depolama birimi Access Control kullanmaya başlamadan önce [Microsoft 365 aboneliğinizi](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) onaylamanız gerekir. Çıkarılabilir Depolama birimi Access Control grup ilkesi aracılığıyla erişmek ve kullanmak için Microsoft 365 E5 sahip olmanız gerekir.

## <a name="deploy-using-group-policy"></a>Grup ilkesini kullanarak dağıtma

1. Çıkarılabilir Depolama birimi Access Control etkinleştirme veya devre dışı bırakma:

   Cihaz denetimini aşağıdaki gibi etkinleştirebilir veya devre dışı bırakabilirsiniz:

   - **Bilgisayar Yapılandırması** > **Yönetim Şablonları** > **Windows Bileşenleri** >  **Microsoft Defender Virüsten Koruma** >  Özellikleri **Cihaz Denetimi'ne** >  gidin.
   - **Cihaz Denetimi** penceresinde **Etkin'i** seçin.

   :::image type="content" source="images/enable-rsac-gp.png" alt-text="grup ilkesi kullanarak RSAC'yi etkinleştirme işleminin ekran görüntüsü " lightbox="images/enable-rsac-gp.png":::

> [!NOTE]
> Bu grup ilkesi nesnelerini görmüyorsanız, grup ilkesi yönetim şablonunu eklemeniz gerekir. yönetim şablonunu (WindowsDefender.adml ve WindowsDefender.admx) adresinden https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samplesindirebilirsiniz.

2. Varsayılan Zorlamayı Ayarla:

   Tüm Cihaz Denetimi özellikleri (RemovableMediaDevices, CdRomDevices, WpdDevices, PrinterDevices) için varsayılan erişimi (Reddet veya İzin Ver) ayarlayabilirsiniz.

   Örneğin, Bir Deny veya Allow policy for RemovableMediaDevices olabilir, ancak CdRomDevices veya WpdDevices için sahip olmayabilirsiniz. Bu ilke aracılığıyla Varsayılan Reddetme'yi ayarlarsınız, ardından CdRomDevices veya WpdDevices'e Okuma/Yazma/Yürütme erişimi engellenir. Yalnızca depolama alanını yönetmek istiyorsanız Yazıcı için İzin Ver ilkesi oluşturduğunuzdan emin olun. Aksi takdirde, bu Varsayılan Zorlama Yazıcıya da uygulanır.

   - **Bilgisayar Yapılandırması** > **Yönetim Şablonları** > **Windows Bileşenleri** >  **Microsoft Defender Virüsten Koruma** > **Özellikleri** > **Cihaz Denetimi** > **Seç Cihaz Denetimi Varsayılan Zorlama'ya** gidin

   - **Cihaz Denetimi Varsayılan Zorlamasını Seç** bölmesinde **Varsayılan Reddetme'yi** seçin:

   :::image type="content" source="images/set-default-enforcement-deny-gp.png" alt-text="Varsayılan Zorlama = grup ilkesi kullanarak reddet ayarının ekran görüntüsü" lightbox="images/set-default-enforcement-deny-gp.png":::

3. Çıkarılabilir depolama grupları için bir XML dosyası oluşturun:

   Çıkarılabilir depolama grubundaki özellikleri kullanarak Çıkarılabilir depolama grupları için bir XML dosyası oluşturun, XML dosyasını ağ paylaşımına kaydedin ve ayarı aşağıdaki gibi tanımlayın:

   - **Bilgisayar Yapılandırması** \> **Yönetim Şablonları** \> **Windows Bileşenleri** \> **Microsoft Defender Virüsten Koruma** \> **Cihaz Denetimi** \> **Cihaz denetimi ilke gruplarını tanımla'ya** gidin.

    :::image type="content" source="images/define-device-control-policy-grps-gp.png" alt-text="Cihaz denetimi ilke gruplarını tanımlama ekran görüntüsü" lightbox="images/define-device-control-policy-grps-gp.png":::

   - **Cihaz denetimi ilkesi gruplarını tanımla** penceresinde, XML grupları verilerini içeren ağ paylaşımı dosya yolunu belirtin.

> [!NOTE]
> XML açıklama gösterimini `<!-- COMMENT -->` kullanan açıklamalar Kural ve Grup XML dosyalarında kullanılabilir, ancak XML dosyasının ilk satırının değil ilk XML etiketinin içinde olmalıdır.

4. Erişim ilkesi kuralları için bir XML dosyası oluşturun:

   Her grubun çıkarılabilir depolama erişim ilkesi kuralı için bir XML oluşturmak, XML dosyasını ağ paylaşımına kaydetmek ve ayar ayarını aşağıdaki gibi geliştirmek için çıkarılabilir depolama erişim ilkesi kurallarındaki özellikleri kullanın:

   - **Bilgisayar Yapılandırması** > **Yönetim Şablonları** > **Windows Bileşenleri** >  **Microsoft Defender Virüsten Koruma** > **Cihaz Denetimi** > **Cihaz denetimi ilkesi kurallarını tanımla'ya** gidin.

     :::image type="content" source="images/define-device-cntrl-policy-rules-gp.png" alt-text="Cihaz denetimi ilkesi kurallarını tanımlama ekran görüntüsü" lightbox="images/define-device-cntrl-policy-rules-gp.png":::

   - **Cihaz denetimi ilkesi kurallarını tanımla** penceresinde **Etkin'i** seçin ve XML kuralları verilerini içeren ağ paylaşımı dosya yolunu girin.

> [!NOTE]
> XML açıklama gösterimini `<!-- COMMENT -->` kullanan açıklamalar Kural ve Grup XML dosyalarında kullanılabilir, ancak XML dosyasının ilk satırının değil ilk XML etiketinin içinde olmalıdır.

5. Dosyanın bir kopyası için konum ayarlayın (kanıt):

    Yazma erişimi gerçekleştiğinde dosyanın bir kopyasına (kanıt) sahip olmak istiyorsanız, XML dosyasında çıkarılabilir depolama birimi erişim ilkesi kuralınızda sağ **Seçenekler'i** ayarlayın ve ardından sistemin kopyayı kaydedebileceği konumu belirtin.

    - **Bilgisayar Yapılandırması** > **Yönetim Şablonları** > **Windows Bileşenleri** >  **Microsoft Defender Virüsten Koruma** > **Cihaz Denetimi****Cihaz Denetimi** >  kanıt verilerini uzak konumu tanımla'ya gidin.

    - **Cihaz Denetimi kanıt verilerini uzak konum tanımla** bölmesinde **Etkin'i** seçin ve ardından yerel veya ağ paylaşımı klasör yolunu belirtin.

      :::image type="content" source="images/evidence-data-remote-location-gp.png" alt-text="Cihaz Denetimi kanıt verilerini uzak konumu tanımla'nın ekran görüntüsü." lightbox="images/evidence-data-remote-location-gp.png":::

## <a name="scenarios"></a>Senaryo

Çıkarılabilir Depolama birimi Access Control Uç Nokta için Microsoft Defender hakkında bilgi sahibi olmanıza yardımcı olacak bazı yaygın senaryolar aşağıdadır. 'Varsayılan Zorlama' hem çıkarılabilir depolama birimine hem de yazıcıya uygulanacağından, aşağıdaki örneklerde 'Varsayılan Zorlama' kullanılmamıştır.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Senaryo 1: Belirli onaylı USB'lere izin vermek dışında tümüne Yazma ve Yürütme erişimini engelleme

Bu senaryo için iki grup oluşturmanız gerekir: bir grup çıkarılabilir depolama birimi için bir grup ve onaylanan USB'ler için başka bir grup. Ayrıca iki ilke oluşturmanız gerekir: biri çıkarılabilir depolama birimi grupları için Yazma ve Yürütme erişimini reddetmek için bir ilke, onaylanan USB grubunu denetlemek için diğer ilke.

1. Grup oluşturma

    1. Grup 1: Tüm çıkarılabilir depolama birimleri, CD/DVD ve Windows taşınabilir cihazları.

    ![Çıkarılabilir depolama biriminin ekran görüntüsü](https://user-images.githubusercontent.com/81826151/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png)

    2. Grup 2: Cihaz özelliklerine göre onaylı USB'ler.

    ![Onaylanan USB'lerin ekran görüntüsü](https://user-images.githubusercontent.com/81826151/188234372-526d20b3-cfea-4f1d-8d63-b513497ada52.png)
    
    Bu iki grubu [tek bir XML dosyasında birleştirin](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Demo_Groups.xml). Bu yapılandırmayı dağıtmak için [Grup ilkesi kullanarak dağıtma](deploy-manage-removable-storage-group-policy.md#deploy-using-group-policy) bölümündeki 3. adıma bakın.

    > [!TIP]
    > değerini ile `&amp;` değiştirin`&`.

2. İlke oluşturma

    1. İlke 1: Herhangi bir çıkarılabilir depolama grubu için Yazma ve Yürütme erişimini engelleyin, ancak onaylı USB'lere izin verin.

    ![Blok yazma ve yürütme erişiminin ekran görüntüsü](https://user-images.githubusercontent.com/81826151/188237490-d736ace1-4912-4788-9e94-3fc506692a41.png)


    2. İlke 2: İzin verilen USB'ler için Yazma ve Yürütme erişimini denetleme.

    ![Denetim yazma ve yürütme erişiminin ekran görüntüsü](https://user-images.githubusercontent.com/81826151/188237598-b28dd534-9ea4-4cdd-832b-afff50f9897b.png)

    İlkedeki '54' ne anlama geliyor? Bu değer 18 + 36 = 54'tir:

    - Yazma erişimi: disk düzeyi 2 + dosya sistemi düzeyi 16 = 18.
    - Yürütme: disk düzeyi 4 + dosya sistemi düzeyi 32 = 36.

    Bu iki ilke kuralını [tek bir XML dosyasında birleştirin](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Scenario%201%20GPO%20Policy%20-%20Prevent%20Write%20and%20Execute%20access%20to%20all%20but%20allow%20specific%20approved%20USBs.xml). Bu yapılandırmayı dağıtmak için [Grup ilkesi kullanarak dağıtma](deploy-manage-removable-storage-group-policy.md#deploy-using-group-policy) bölümündeki 4. adıma bakın.

### <a name="scenario-2-audit-write-and-execute-access-for-all-but-block-specific-blocked-usbs"></a>Senaryo 2: Belirli engellenen USB'ler için yazma ve yürütme erişimini denetleme

Bu senaryo için iki grup oluşturmanız gerekir: bir grup çıkarılabilir depolama birimi için bir grup ve engellenen USB'ler için başka bir grup. Ayrıca iki ilke oluşturmanız gerekir: biri çıkarılabilir depolama birimi grupları için Yazma ve Yürütme erişimini denetlemek için bir ilke ve engellenen USB grubunu reddetmek için diğer ilke.

1. Grup oluşturma

    1. Grup 1: Tüm çıkarılabilir depolama birimleri, CD/DVD ve windows taşınabilir cihazları.

    ![Gruplardaki çıkarılabilir depolama biriminin ekran görüntüsü](https://user-images.githubusercontent.com/81826151/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png)

    2. Grup 2: Cihaz özelliklerine göre engellenen USB'ler.

    ![Engellenen USB'lerin ekran görüntüsü](https://user-images.githubusercontent.com/81826151/188234372-526d20b3-cfea-4f1d-8d63-b513497ada52.png)
    
    Bu iki grubu [tek bir XML dosyasında birleştirin](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Demo_Groups.xml). Bu yapılandırmayı dağıtmak için [Grup ilkesi kullanarak dağıtma](deploy-manage-removable-storage-group-policy.md#deploy-using-group-policy) bölümündeki 3. adıma bakın.

    > [!TIP]
    > değerini ile `&amp;` değiştirin`&`.

2. İlke oluşturma

    1. İlke 1: Onaylanmamış belirli USB'ler için yazma ve yürütme erişimini engelle.

    ![Onaylanmamış belirli USB'lerin ekran görüntüsü](https://user-images.githubusercontent.com/81826151/188239025-218a1985-b198-4f7e-b323-b4b6fb7e274e.png)

    2. İlke 2: Başkaları için Yazma ve Yürütme erişimini denetleme. 

    ![Grup ilkesinde denetim yazma ve yürütme erişiminin ekran görüntüsü](https://user-images.githubusercontent.com/81826151/188239144-3e6a2781-6927-487a-aa01-498a0904ad98.png)

    İlkedeki '54' ne anlama geliyor? Bu değer 18 + 36 = 54'tir:

    - Yazma erişimi: disk düzeyi 2 + dosya sistemi düzeyi 16 = 18.
    - Yürütme: disk düzeyi 4 + dosya sistemi düzeyi 32 = 36.

    Bu iki ilke kuralını [tek bir XML dosyasında birleştirin](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Group%20Policy/Scenario%202%20GPO%20Policy%20-%20Audit%20Write%20and%20Execute%20access%20to%20all%20but%20block%20specific%20unapproved%20USBs.xml). Bu yapılandırmayı dağıtmak için [Grup ilkesi kullanarak dağıtma](deploy-manage-removable-storage-group-policy.md#deploy-using-group-policy) bölümündeki 4. adıma bakın.

