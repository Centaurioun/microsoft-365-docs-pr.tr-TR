---
title: macOS Catalina için yeni yapılandırma profilleri ve macOS'un daha yeni sürümleri
description: Bu konuda, macOS Catalina'daki çekirdek uzantılarının ve macOS'un daha yeni sürümlerinin yerini alan sistem uzantılarından yararlanmak için yapılması gereken değişiklikler açıklanmaktadır.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, çekirdek, sistem, uzantılar, catalina, big sur, monterey, ventura, mac için mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.subservice: mde
ms.openlocfilehash: 3ecd935bfbbd6f37d6803409e7ee8336ca25381f
ms.sourcegitcommit: a20d30f4e5027f90d8ea4cde95d1d5bacfdd2b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68770073"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a>macOS Catalina için yeni yapılandırma profilleri ve macOS'un daha yeni sürümleri

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

macOS'ta yönetilen bir ortamda (JAMF, Intune veya başka bir MDM çözümü aracılığıyla) Uç Nokta için Microsoft Defender dağıttıysanız, yeni yapılandırma profilleri dağıtmanız gerekir. Bu adımların yapılmaması, kullanıcıların bu yeni bileşenleri çalıştırmak için onay istemleri almasına neden olur.

## <a name="jamf"></a>JAMF

### <a name="jamf-system-extensions-policy"></a>JAMF Sistem Uzantıları İlkesi

Sistem uzantılarını onaylamak için aşağıdaki yükü oluşturun:

1. **Bilgisayarlar > Yapılandırma Profilleri'nde** **Seçenekler > Sistem Uzantıları'nı** seçin.
2. **Sistem Uzantısı Türleri** açılan **listesinden İzin Verilen Sistem Uzantıları'nı** seçin.
3. Takım Kimliği için **UBF8T346G9** kullanın.
4. **İzin Verilen Sistem Uzantıları** listesine aşağıdaki paket tanımlayıcılarını ekleyin:

    - **com.microsoft.wdav.epsext**
    - **com.microsoft.wdav.netext**

    :::image type="content" source="images/mac-approved-system-extensions.png" alt-text=" Onaylı sistem uzantıları sayfası" lightbox="images/mac-approved-system-extensions.png":::

### <a name="privacy-preferences-policy-control"></a>Gizlilik Tercihleri İlke Denetimi

Uç Nokta için Microsoft Defender Endpoint Security Uzantısına Tam Disk Erişimi vermek için aşağıdaki JAMF yükünü ekleyin. Bu ilke, uzantıyı cihazınızda çalıştırmak için bir önkoşuldur.

1. **Seçenekler** \> **Gizlilik Tercihleri İlke Denetimi'ni** seçin.
2. **Tanımlayıcı** olarak ve `Bundle ID` **Paket türü** olarak kullanın`com.microsoft.wdav.epsext`.
3. Kod Gereksinimini olarak ayarlayın `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
4. **Uygulama veya hizmeti** **SystemPolicyAllFiles** ve erişimi **İzin Ver** olarak ayarlayın.

   :::image type="content" source="images/mac-system-extension-privacy.png" alt-text=" Gizlilik Tercihleri İlkesi Denetimi menü öğesi" lightbox="images/mac-system-extension-privacy.png":::

### <a name="network-extension-policy"></a>Ağ Uzantısı İlkesi

Uç Nokta Algılama ve Yanıt özelliklerinin bir parçası olarak macOS'ta Uç Nokta için Microsoft Defender yuva trafiğini inceler ve bu bilgileri Microsoft 365 Defender portalına bildirir. Aşağıdaki ilke, ağ uzantısının bu işlevi gerçekleştirmesine izin verir.

> [!NOTE]
> JAMF,macOS üzerinde Uç Nokta için Microsoft Defender ağ uzantılarının cihaza yüklenmesini sağlamak için bir önkoşul olan içerik filtreleme ilkeleri için yerleşik desteğe sahip değildir. Ayrıca, JAMF bazen dağıtılmakta olan ilkelerin içeriğini değiştirir.
> Bu nedenle, aşağıdaki adımlar yapılandırma profilini imzalamayı içeren bir geçici çözüm sağlar.

1. Aşağıdaki içeriği cihazınıza `com.microsoft.network-extension.mobileconfig` metin düzenleyicisi kullanarak kaydedin:

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. Terminalde yardımcı programını çalıştırarak `plutil` yukarıdaki dosyanın doğru kopyalandığını doğrulayın:

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    Örneğin, dosya Belgeler'de depolanmışsa:

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```

    Komutun çıkışını `OK`olduğunu doğrulayın.

    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```

3. JAMF'nin yerleşik sertifika yetkilisini kullanarak imzalama sertifikası oluşturmak için [bu sayfadaki](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) yönergeleri izleyin.

4. Sertifika oluşturulduktan ve cihazınıza yüklendikten sonra, dosyayı imzalamak için Terminal'den aşağıdaki komutu çalıştırın:

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```

    Örneğin, sertifika adı **SigningCertificate** ise ve imzalı dosya Belgeler'de depolanacaksa:

    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```

5. JAMF portalından **Yapılandırma Profilleri'ne** gidin ve **Karşıya Yükle** düğmesine tıklayın. Dosya istendiğinde öğesini seçin `com.microsoft.network-extension.signed.mobileconfig` .

## <a name="intune"></a>Intune

### <a name="intune-system-extensions-policy"></a>Intune Sistem Uzantıları İlkesi

Sistem uzantılarını onaylamak için:

1. Intune'da **Cihaz yapılandırmasını** **yönet'i** \> açın. Profilleri **Yönet** \> **Profil Oluştur'u** \> seçin.
2. Profil için bir ad seçin. **Platform=macOS** **değerini Profil türü=Uzantılar** olarak değiştirin. **Oluştur**’u seçin.
3. `Basics` Sekmesinde, bu yeni profile bir ad verin.
4. `Configuration settings` sekmesinde, bölümüne aşağıdaki girdileri `Allowed system extensions` ekleyin:

   <br>

   ****

   |Paket tanımlayıcısı|Ekip tanımlayıcısı|
   |---|---|
   |com.microsoft.wdav.epsext|UBF8T346G9|
   |com.microsoft.wdav.netext|UBF8T346G9|
   |||

   :::image type="content" source="images/mac-system-extension-intune2.png" alt-text=" Sistem yapılandırma profilleri sayfası" lightbox="images/mac-system-extension-intune2.png":::

5. `Assignments` sekmesinde, bu profili **Tüm Kullanıcılar & Tüm cihazlar'a atayın**.
6. Bu yapılandırma profilini gözden geçirin ve oluşturun.

### <a name="create-and-deploy-the-custom-configuration-profile"></a>Özel Yapılandırma Profili oluşturma ve dağıtma

Aşağıdaki yapılandırma profili ağ uzantısını etkinleştirir ve Endpoint Security sistem uzantısına Tam Disk Erişimi verir.

Aşağıdaki içeriği **sysext.xml** adlı bir dosyaya kaydedin:

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

Yukarıdaki dosyanın doğru kopyalandığını doğrulayın. Terminal'den aşağıdaki komutu çalıştırın ve çıktısını `OK`alın:

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

Bu özel yapılandırma profilini dağıtmak için:

1. Intune'da **Cihaz yapılandırmasını** **yönet'i** \> açın. Profilleri **Yönet** \> **Profil** \> **oluştur'u** seçin.
2. Profil için bir ad seçin. **Platform=macOS** ve **Profil türü=Özel'i** değiştirin. **Yapılandır'ı** seçin.
3. Yapılandırma profilini açın ve **sysext.xml** karşıya yükleyin. Bu dosya önceki adımda oluşturulmuştur.
4. **Tamam**'ı seçin.

   :::image type="content" source="images/mac-system-extension-intune.png" alt-text="Intune sayfasındaki Sistem uzantısı" lightbox="images/mac-system-extension-intune.png":::

5. `Assignments` sekmesinde, bu profili **Tüm Kullanıcılar & Tüm cihazlar'a atayın**.
6. Bu yapılandırma profilini gözden geçirin ve oluşturun.
