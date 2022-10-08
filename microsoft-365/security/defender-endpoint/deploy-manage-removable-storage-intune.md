---
title: Intune kullanarak Çıkarılabilir Depolama Access Control dağıtma ve yönetme
description: Çıkarılabilir depolama erişim denetimini dağıtmak ve yönetmek için Intune OMA-URI ve Intune kullanıcı arabirimini kullanın.
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
ms.openlocfilehash: 05cf5bd278f5ca88c5802891dd6f4d584b7e4d27
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68207610"
---
# <a name="deploy-and-manage-removable-storage-access-control-using-intune"></a>Intune kullanarak Çıkarılabilir Depolama Access Control dağıtma ve yönetme

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!NOTE]
> Bu ürünün grup ilkesi yönetimi ve Intune OMA-URI/Özel İlke yönetimi genel kullanıma sunuldu (4.18.2106): [Teknik Topluluk blogu: Çıkarılabilir depolama alanınızı ve yazıcınızı Uç Nokta için Microsoft Defender ile koruma](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protect-your-removable-storage-and-printers-with-microsoft/ba-p/2324806).

Çıkarılabilir Depolama Birimi Access Control özelliği, kullanıcıya veya cihaza ya da her ikisine de OMA-URI kullanarak ilke uygulamanızı sağlar.

## <a name="licensing-requirements"></a>Lisans gereksinimleri

Çıkarılabilir Depolama birimi Access Control kullanmaya başlamadan önce [Microsoft 365 aboneliğinizi](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2) onaylamanız gerekir. Çıkarılabilir Depolama birimi Access Control erişmek ve kullanmak için Microsoft 365 E3 sahip olmanız gerekir.

### <a name="permission"></a>Izni

Intune'da ilke dağıtımı için hesabın cihaz yapılandırma profillerini oluşturma, düzenleme, güncelleştirme veya silme izinleri olmalıdır. Bu izinlerle özel roller oluşturabilir veya yerleşik rollerden herhangi birini kullanabilirsiniz.

- İlke ve profil Yöneticisi rolü
- Cihaz Yapılandırma profilleri için Raporları Oluşturma/Düzenleme/Güncelleştirme/Okuma/Silme/Görüntüleme izinlerinin açık olduğu özel rol
- Genel yönetici

## <a name="deploy-removable-storage-access-control-by-using-intune-oma-uri"></a>Intune OMA-URI kullanarak Çıkarılabilir Depolama Birimi Access Control dağıtma

Microsoft Endpoint Manager yönetim merkezine (<https://endpoint.microsoft.com/>) > **Cihazlar** > **Profil Platformu Oluştur****: Windows 10 ve üzeri, Profil türü: Özel > Şablonlar**** bölümüne gidin. > 

1. Cihaz denetimini aşağıdaki gibi etkinleştirin veya devre dışı bırakın:

   - **Özel** > **Yapılandırma ayarları'nın** altında **Ekle'yi** seçin.
   - **Satır Ekle** bölmesinde aşağıdaki ayarları belirtin:
     - **Cihaz Denetimini Etkinleştir** olarak **adlandır**
     - **OMA-URI** olarak `./Vendor/MSFT/Defender/Configuration/DeviceControlEnabled`
     - **Tamsayı** Olarak **Veri Türü**
     - **1** olarak **değer**

       `Disable: 0`
       `Enable: 1`

     - **Kaydet**'i seçin.

   :::image type="content" source="images/enable-rsac.png" alt-text="Çıkarılabilir Depolama Birimi Access Control ilkesini etkinleştirme işleminin ekran görüntüsü" lightbox="images/enable-rsac.png":::

2. Varsayılan Zorlamayı Ayarla:

   Tüm Cihaz Denetimi özellikleri (, `CdRomDevices`, , `PrinterDevices``WpdDevices`) için varsayılan erişimi (`RemovableMediaDevices`Reddet veya İzin Ver) ayarlayabilirsiniz.

   Belirli bir çıkarılabilir depolama sınıfını engellemek ancak belirli bir medyaya izin vermek için '`IncludedIdList` aracılığıyla bir grup `PrimaryId` ve `ExcludedIDList` /etc aracılığıyla `DeviceId`/`HardwareId`bir grup' kullanabilirsiniz.  Ek ayrıntılar için bkz. [Uç Nokta için Microsoft Defender Cihaz Denetimi Çıkarılabilir Depolama Access Control](device-control-removable-storage-access-control.md).

   Örneğin, için `RemovableMediaDevices`**bir Reddet** veya **İzin Ver** ilkesine sahip olabilirsiniz, ancak veya `WpdDevices`için `CdRomDevices` sahip olmayabilirsiniz. Bu ilke aracılığıyla **Varsayılan Reddetme'yi** ayarlayabilirsiniz, ardından Okuma/Yazma/Yürütme erişimi `CdRomDevices` engellenir veya `WpdDevices` engellenir. Yalnızca depolama alanını yönetmek istiyorsanız yazıcınız için **bir İzin Ver** ilkesi oluşturduğunuzdan emin olun; aksi takdirde, bu varsayılan zorlama yazıcılara da uygulanır.

   - **Satır Ekle** bölmesinde aşağıdaki ayarları belirtin:
     - **Varsayılan Reddetme** Olarak **Adlandır**
     - **OMA-URI** olarak `./Vendor/MSFT/Defender/Configuration/DefaultEnforcement`
     - **Tamsayı** Olarak **Veri Türü**
     - **1** veya **2** olarak **değer**

       `DefaultEnforcementAllow = 1`
       `DefaultEnforcementDeny = 2`

     - **Kaydet**'i seçin.

   :::image type="content" source="images/default-deny.png" alt-text="Varsayılan Zorlama'nın Reddet olarak ayarlanmasının ekran görüntüsü" lightbox="images/default-deny.png":::

3. Her grup için bir XML dosyası oluşturun:

   Her grup için aşağıdaki gibi bir çıkarılabilir depolama grubu oluşturabilirsiniz:

   - **Satır Ekle** bölmesine şunu girin:
     - **Herhangi Bir Çıkarılabilir Depolama Grubu** Olarak **Adlandır**
     - **OMA-URI** olarak `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b**[GroupId]**%7d/GroupData`
     - **Dize Olarak Veri Türü** **(XML dosyası)**
       - Seçili XML dosyası olarak **özel** XML

         Çıkarılabilir depolama birimleri, CDROM ve Windows taşınabilir cihazları için bir grup örneği XML dosyası aşağıda verilmiştir: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Any%20Removable%20Storage%20and%20CD-DVD%20and%20WPD%20Group.xml>

       :::image type="content" source="images/any-removable-storage-group.png" alt-text="Çıkarılabilir Depolama Grubu oluşturma işleminin ekran görüntüsü." lightbox="images/any-removable-storage-group.png":::

> [!NOTE]
> XML açıklama gösterimini `<!-- COMMENT -->` kullanan açıklamalar Kural ve Grup XML dosyalarında kullanılabilir, ancak XML dosyasının ilk satırının değil ilk XML etiketinin içinde olmalıdır.

4. Her erişim denetimi veya ilke kuralı için bir XML dosyası oluşturun:

   Bir ilke oluşturabilir ve bunu ilgili çıkarılabilir depolama grubuna aşağıdaki gibi uygulayabilirsiniz:

   - **Satır Ekle** bölmesine şunu girin:
     - **Okuma Etkinliğine İzin Ver** Olarak **Adlandır**
     - **OMA-URI** olarak `./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7b**[PolicyRule Id]**%7d/RuleData`
     - **Dize Olarak Veri Türü** **(XML dosyası)**
     - **Read.xmldosyasına İzin Ver** olarak **Özel XML**

       Her çıkarılabilir depolama birimi için Okuma erişimine izin ver için bir grup örneği XML dosyası aşağıda verilmiştir: <https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Allow%20Read.xml>

       :::image type="content" source="images/allow-read-activity.png" alt-text="Okuma Etkinliğine İzin Ver ilkesinin ekran görüntüsü" lightbox= "images/allow-read-activity.png":::

> [!NOTE]
> XML açıklama gösterimini `<!-- COMMENT -->` kullanan açıklamalar Kural ve Grup XML dosyalarında kullanılabilir, ancak XML dosyasının ilk satırının değil ilk XML etiketinin içinde olmalıdır.

5. Dosyanın bir kopyası için konum ayarlayın (kanıt):
   
   Yazma erişimi gerçekleştiğinde dosyanın bir kopyasına (kanıt) sahip olmak istiyorsanız, XML dosyasında çıkarılabilir depolama birimi erişim ilkesi kuralınızda sağ **Seçenekler'i** ayarlayın ve ardından sistemin kopyayı kaydedebileceği konumu belirtin.

   - **Satır Ekle** bölmesine şunu girin:
     - **Kanıt klasörü konumu** olarak **adlandır**
     - **OMA-URI** olarak `./Vendor/MSFT/Defender/Configuration/DataDuplicationRemoteLocation`
     - **Dize** Olarak **Veri Türü**

       :::image type="content" source="../../media/device-control-oma-uri-edit-row.png" alt-text="Dosya kanıtı için konum ayarlama":::

## <a name="scenarios"></a>Senaryo

Çıkarılabilir Depolama birimi Access Control Uç Nokta için Microsoft Defender hakkında bilgi sahibi olmanıza yardımcı olacak bazı yaygın senaryolar aşağıdadır.

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a>Senaryo 1: Belirli onaylı USB'lere izin vermek dışında tümüne Yazma ve Yürütme erişimini engelleme

Bu senaryo için iki grup oluşturmanız gerekir: bir grup çıkarılabilir depolama birimi için bir grup ve onaylanan USB'ler için başka bir grup. Ayrıca iki ilke oluşturmanız gerekir: biri çıkarılabilir depolama birimi grupları için Yazma ve Yürütme erişimini reddetmek için bir ilke, onaylanan USB grubunu denetlemek için diğer ilke.

1. Grup oluşturma

    1. Grup 1: Tüm çıkarılabilir depolama birimleri, CD/DVD ve Windows taşınabilir cihazları.

       :::image type="content" source="media/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png" alt-text="Çıkarılabilir depolama birimini gösteren ekran görüntüsü" lightbox= "media/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png":::

    [Örnek dosya](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Any%20Removable%20Storage%20and%20CD-DVD%20and%20WPD%20Group.xml) aşağıda verilmiştir. Yapılandırmayı dağıtmak için [Çıkarılabilir Depolama Birimi Dağıtma Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) bölümündeki 3. adıma bakın.

    2. Grup 2: Cihaz özelliklerine göre onaylı USB'ler.

        :::image type="content" source="media/188234372-526d20b3-cfea-4f1d-8d63-b513497ada52.png" alt-text="Onaylanan USB'lerin ekran görüntüsü" lightbox= "media/188234372-526d20b3-cfea-4f1d-8d63-b513497ada52.png":::

    [Örnek dosya](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Approved%20USBs%20Group.xml) aşağıda verilmiştir. Yapılandırmayı dağıtmak için [Çıkarılabilir Depolama Birimi Dağıtma Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) bölümündeki 3. adıma bakın.

    > [!TIP]
    > değerini XML dosyasındaki değeriyle `&amp;` değiştirin`&`.

2. İlke oluşturma

    1. İlke 1: Herhangi bir çıkarılabilir depolama grubu için Yazma ve Yürütme erişimini engelleyin, ancak onaylı USB'lere izin verin.

        :::image type="content" source="media/188243425-c0772ed4-6537-4c6a-9a1d-1dbb48018578.png" alt-text="İlke 1'in ekran görüntüsü" lightbox= "media/188243425-c0772ed4-6537-4c6a-9a1d-1dbb48018578.png":::

    [Örnek dosya](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Scenario%201%20Block%20Write%20and%20Execute%20Access%20but%20allow%20approved%20USBs.xml) aşağıda verilmiştir. Yapılandırmayı dağıtmak için [Çıkarılabilir Depolama Birimi Dağıtma Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) bölümündeki 4. adıma bakın.

    2. İlke 2: İzin verilen USB'ler için Yazma ve Yürütme erişimini denetleme.

        :::image type="content" source="media/188243552-5d2a90ab-dba6-450f-ad8f-86a862f6e739.png" alt-text="İlke 2'nin ekran görüntüsü" lightbox= "media/188243552-5d2a90ab-dba6-450f-ad8f-86a862f6e739.png":::

    İlkedeki '54' ne anlama geliyor? Bu değer 18 + 36 = 54'tir:

    - Yazma erişimi: disk düzeyi 2 + dosya sistemi düzeyi 16 = 18.
    - Yürütme: disk düzeyi 4 + dosya sistemi düzeyi 32 = 36.

    [Örnek dosya](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Scenario%201%20Audit%20Write%20and%20Execute%20access%20to%20aproved%20USBs.xml) aşağıda verilmiştir. Yapılandırmayı dağıtmak için [Çıkarılabilir Depolama Birimi Dağıtma Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) bölümündeki 4. adıma bakın.

### <a name="scenario-2-audit-write-and-execute-access-for-all-but-block-specific-blocked-usbs"></a>Senaryo 2: Belirli engellenen USB'ler için yazma ve yürütme erişimini denetleme

Bu senaryo için iki grup oluşturmanız gerekir: bir grup çıkarılabilir depolama birimi için bir grup ve engellenen USB'ler için başka bir grup. Ayrıca iki ilke oluşturmanız gerekir: biri çıkarılabilir depolama birimi grupları için Yazma ve Yürütme erişimini denetlemek için bir ilke ve engellenen USB grubunu reddetmek için diğer ilke.

1. Grup oluşturma

    1. Grup 1: Tüm çıkarılabilir depolama birimleri, CD/DVD ve Windows taşınabilir cihazları.

        :::image type="content" source="media/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png" alt-text="Grup 1'in ekran görüntüsü" lightbox="media/188234308-4db09787-b14e-446a-b9e0-93c99b08748f.png":::
    
    [Örnek dosya](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Any%20Removable%20Storage%20and%20CD-DVD%20and%20WPD%20Group.xml) aşağıda verilmiştir. Yapılandırmayı dağıtmak için [Çıkarılabilir Depolama Birimi Dağıtma Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) bölümündeki 3. adıma bakın.

    2. Grup 2: Cihaz özelliklerine göre onaylanmamış USB'ler.

        :::image type="content" source="media/188243875-0693ebcf-00c3-45bd-afd3-57a79df9dce6.png" alt-text="Grup 2'nin ekran görüntüsü" lightbox= "media/188243875-0693ebcf-00c3-45bd-afd3-57a79df9dce6.png":::
     
    [Örnek dosya](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Unapproved%20USBs%20Group.xml) aşağıda verilmiştir. Yapılandırmayı dağıtmak için [Çıkarılabilir Depolama Birimi Dağıtma Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) bölümündeki 3. adıma bakın.


    > [!TIP]
    > değerini XML dosyasındaki değeriyle `&amp;` değiştirin`&`.

2. İlke oluşturma

    1. İlke 1: Onaylanmamış belirli USB'ler için yazma ve yürütme erişimini engelle.

        :::image type="content" source="media/188244024-62355ded-353c-4d3a-ba61-4520d48f5a18.png" alt-text="Onaylanmamış USB'leri engelleme ilkesinin ekran görüntüsü" lightbox= "media/188244024-62355ded-353c-4d3a-ba61-4520d48f5a18.png":::
    
    [Örnek dosya](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Scenario%202%20Audit%20Write%20and%20Execute%20access%20to%20all%20but%20block%20specific%20unapproved%20USBs.xml) aşağıda verilmiştir. Yapılandırmayı dağıtmak için [Çıkarılabilir Depolama Birimi Dağıtma Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) bölümündeki 4. adıma bakın.

    2. İlke 2: Başkaları için Yazma ve Yürütme erişimini denetleme.

        :::image type="content" source="media/188244203-36c869b6-9330-4e2a-854b-494c342bb77d.png" alt-text="Denetim yazma ve yürütme erişiminin ekran görüntüsü" lightbox= "media/188244203-36c869b6-9330-4e2a-854b-494c342bb77d.png":::
    
    İlkedeki '54' ne anlama geliyor? Bu değer 18 + 36 = 54'tir:

    - Yazma erişimi: disk düzeyi 2 + dosya sistemi düzeyi 16 = 18.
    - Yürütme: disk düzeyi 4 + dosya sistemi düzeyi 32 = 36.
    
    [Örnek dosya](https://github.com/microsoft/mdatp-devicecontrol/blob/main/Removable%20Storage%20Access%20Control%20Samples/Intune%20OMA-URI/Scenario%202%20Audit%20Write%20and%20Execute%20access%20to%20others.xml) aşağıda verilmiştir. Yapılandırmayı dağıtmak için [Çıkarılabilir Depolama Birimi Dağıtma Access Control](deploy-manage-removable-storage-intune.md#deploy-removable-storage-access-control-by-using-intune-oma-uri) bölümündeki 4. adıma bakın.

## <a name="use-intune-user-interface"></a>Intune kullanıcı arabirimini kullanma

Bu özellik Microsoft Endpoint Manager yönetim merkezinde (<https://endpoint.microsoft.com/>) kullanılabilir. 

**Endpoint Security** > **Attack Surface Azaltma** > **Oluşturma İlkesi'ne** gidin. **Profil: Cihaz Denetimi** ile **Platform: Windows 10 ve üzerini** seçin.
