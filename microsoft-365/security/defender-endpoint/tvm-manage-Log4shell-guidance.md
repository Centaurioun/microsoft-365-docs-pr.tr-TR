---
title: Uç Nokta için Microsoft Defender - Tehdit ve Güvenlik Açığı Yönetimi'da Log4Shell güvenlik açığını azaltmayı öğrenin
description: Uç Nokta için Microsoft Defender'da Log4Shell güvenlik açığını azaltmayı öğrenin
keywords: tvm, lo4j
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365-initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6e265490eb5afee275debcdd1eb073f11bb845e3
ms.sourcegitcommit: 8101c12df67cfd9c15507b0133c23ce4cca1c6ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2022
ms.locfileid: "66862381"
---
# <a name="learn-how-to-manage-the-log4shell-vulnerability-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de Log4Shell güvenlik açığını yönetmeyi öğrenin

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Tehdit ve güvenlik açığı yönetimi](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Log4Shell güvenlik açığı, Apache Log4j 2 günlük kitaplığında bulunan bir uzaktan kod yürütme (RCE) güvenlik açığıdır. Apache Log4j 2 yaygın olarak birçok yazılım uygulaması ve çevrimiçi hizmetler tarafından kullanıldığından, dünya çapındaki şirketler için karmaşık ve yüksek riskli bir durumu temsil eder. "Log4Shell" ([CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=2021-44228), [CVE-2021-45046](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-45046) ) olarak adlandırılır. Saldırganların kuruluştaki verileri ayıklamak ve fidye yazılımı dağıtmak için yararlanabileceği yeni bir saldırı vektörünü kullanıma sunar.

> [!NOTE]
> Kuruluşunuzu korumaya yönelik güvenlik açığı ve ürüne özgü risk azaltma önerileri hakkında yönergeler ve teknik bilgiler [için Log4j 2 güvenlik açığının kötüye kullanılmasını önleme, algılama ve tehdit avcılığını önlemeye](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/) yönelik yönergeler ve [Microsoft Güvenlik Yanıt Merkezi](https://msrc-blog.microsoft.com/2021/12/11/microsofts-response-to-cve-2021-44228-apache-log4j2/) bloglarına bakın.

## <a name="overview-of-discovery-monitoring-and-mitigation-capabilities"></a>Bulma, izleme ve azaltma özelliklerine genel bakış

Tehdit ve güvenlik açığı yönetimi, kuruluşunuzun Log4Shell güvenlik açığına maruz kalmasını tanımlamanıza, izlemenize ve azaltmanıza yardımcı olacak aşağıdaki özellikleri sağlar:

- **Bulma**: Hem eklenen cihazlar Uç Nokta için Microsoft Defender hem de bulunan ancak henüz eklenmemiş olan kullanıma sunulan cihazların algılanması, güvenlik açığı bulunan yazılımları ve diskte algılanan güvenlik açığı olan dosyaları temel alır.
- **Tehdit farkındalığı:** Kuruluşunuzun açığa çıkarmasını değerlendirmek için birleştirilmiş bir görünüm. Bu görünüm, cihaz düzeyinde ve yazılım düzeyinde açığa çıkarmanızı gösterir ve açık bağlantı noktalarıyla en son ne zaman görüldüğü, en son yürütülürken olduğu gibi güvenlik açığı olan dosyalar hakkındaki ayrıntılara erişim sağlar. Düzeltme eylemlerinize öncelik vermek için bu bilgileri kullanabilirsiniz. Kullanıma sunulan cihazlarla ilgili verilerin panoda görünmesi 24 saate kadar sürebilir.
- **Azaltma seçenekleri:** Risk azaltma riskinizi azaltmaya yardımcı olmak için risk azaltma seçeneklerini uygulayın.
- **Gelişmiş avcılık:** Diskte tanımlanan güvenlik açığı olan log4j dosyalarının ayrıntılarını döndürmek için gelişmiş avcılığı kullanın.

> [!NOTE]
> Bu özellikler Windows 10 & Windows 11, Windows Server, Linux ve macOS'ta desteklenir.
>
> Linux'ta destek için Uç Nokta için Microsoft Defender Linux istemci sürümü 101.52.57 (30.121092.15257.0) veya üzeri gerekir.
>
> macOS'ta destek için macOS istemci sürümü 20.121111.15416.0 veya üzeri Uç Nokta için Microsoft Defender gerekir.
>
>Desteklenen sürümler hakkında daha fazla bilgi için bkz [. Desteklenen işletim sistemi platformları ve özellikleri](tvm-supported-os.md).

## <a name="exposed-devices-discovery"></a>Kullanıma sunulan cihaz bulma

Microsoft 365 Defender portalında Log4j algılamasını etkinleştirmenin yanı sıra tümleşik Tehdit ve Güvenlik Açığı Yönetimi özellikleri, Log4Shell güvenlik açığına maruz kalan cihazları keşfetmenize yardımcı olur.

Eklenen cihazlar, güvenlik açığı bulunan yazılımları ve dosyaları bulabilen mevcut ekli Tehdit ve Güvenlik Açığı Yönetimi özellikleri kullanılarak değerlendirilir.

Bulunan ancak henüz eklenmemiş cihazlarda algılama için Log4j algılama etkinleştirilmelidir. Bu, yoklamaları cihaz bulma işleminin ağınızı etkin bir şekilde yoklaması gibi başlatır. Bu, birden çok eklenen uç noktadan (Windows 10+ ve Windows Server 2019+ cihazları) yoklama ve yalnızca alt ağlarda yoklama ile CVE-2021-44228'e açık ve uzaktan kullanıma açık cihazları algılamayı içerir.

Log4 algılamasını etkinleştirmek için:

1. **Ayarlar** > **Cihaz bulma bulma** > **kurulumu'na** gidin
2. **Log4j2 algılamasını etkinleştir 'i seçin (CVE-2021-44228)**
3. **Kaydet'i** seçin

:::image type="content" source="images/enable_log4j.png" alt-text="log4j2 algılamasını etkinleştirme ayarı" lightbox="images/enable_log4j.png":::

Bu yoklamaların çalıştırılması, standart Log4j akışını, yoklanan cihaz veya yoklama cihazı üzerinde zararlı bir etkiye neden olmadan tetikler. Yoklama, bulunan cihazlara birden çok HTTP isteği göndererek, ortak web uygulaması bağlantı noktalarını (örneğin - 80.8000.8080.443.8443) ve URL'leri hedefleyerek gerçekleştirilir. İstek, yoklanan makineden bir DNS isteğini tetikleyen JNDI yüküne sahip HTTP üst bilgileri içerir.

Örneğin, Kullanıcı Aracısı: ${jndi:dns://192.168.1.3:5353/MDEDiscoveryUser-Agent} burada 192.168.1.3, yoklama makinesinin IP'sini oluşturur.

> [!NOTE]
> Log4j2 algılamasını etkinleştirmek, eklenen cihazların yerel güvenlik açıklarını algılamak için kendi kendini yoklama kullanacağı anlamına da gelir.

## <a name="vulnerable-software-and-files-detection"></a>Güvenlik açığı bulunan yazılım ve dosya algılama

Tehdit ve güvenlik açığı yönetimi, keşfetmenize yardımcı olmak için algılama katmanları sağlar:

- **Güvenlik açığı bulunan yazılım**: Bulma, Log4j uzaktan kod yürütmeye karşı savunmasız olduğu bilinen yüklü uygulama Ortak Platform Numaralandırmalarını (CPE) temel alır.
- **Güvenlik açığı olan dosyalar:** Hem bellekteki dosyalar hem de dosya sistemindeki dosyalar değerlendirilir. Bu dosyalar, bilinen güvenlik açığı olan sürüme sahip Log4j-core jar dosyaları veya güvenlik açığı olan bir jndi arama sınıfı veya güvenlik açığı olan log4j-core dosyası içeren bir Uber-JAR olabilir. Özellikle, şu şekildedir:

  - JAR dosyalarını inceleyip şu dosyayı arayarak jar dosyasının güvenlik açığı olan bir Log4j dosyası içerip içermediğini belirler: \\META-INF\\maven\\org.apache.logging.log4j log4j-core\\\\pom.properties - Bu dosya varsa Log4j sürümü okunur ve ayıklanır.
  - "/log4j/core/lookup/JndiLookup.class" dizesini içeren yolları arayarak JAR dosyasının içindeki JndiLookup.class dosyasını arar. JndiLookup.class dosyası varsa, Tehdit ve Güvenlik Açığı Yönetimi bu JAR dosyasının pom.properties içinde tanımlanan sürüme sahip bir Log4j dosyası içerip içermediğini belirler.
  - bu dizelerden herhangi birini içeren yolları arayarak iç içe bir JAR içine eklenmiş güvenlik açığı olan Log4j-core JAR dosyalarını arar:
    - lib/log4j-core-
    - WEB-INF/lib/log4j-core-
    - App-INF/lib/log4j-core-

Bu tabloda desteklenen platformlar ve sürümler için arama özellikleri açıklanmaktadır:

|Yeteneği|Dosya Türü|Windows10+,<br>server2019+|Server 2012R2,<br>server2016|Server 2008R2|Linux + macOS|
|:---|:---|:---|:---|:---|:---|
|Bellekte Arama  | Log4j-core | Evet |Evet<sup>[1]| - | Evet |
| |Uber-JARs | Evet |Evet<sup>[1]| - | Evet |
| Disk üzerindeki tüm dosyaları arama  |Log4j-core | Evet |Evet<sup>[1]| Evet | - |
| | Uber-JARs|Evet |Evet<sup>[1]| - | -|

(1) Windows Server 2012 [R2 ve 2016'da KB5005292](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-update-for-edr-sensor-f8f69773-f17f-420f-91f4-a8e5167284ac) yüklendiğinde özellikler kullanılabilir.

## <a name="learn-about-your-log4shell-exposure-and-mitigation-options"></a>Log4Shell'i açığa çıkarma ve azaltma seçenekleriniz hakkında bilgi edinin

### <a name="threat-and-vulnerability-management-dashboard"></a>Tehdit ve güvenlik açığı yönetimi panosu

Geçerli açığa çıkarmanızı görmek için Tehdit ve Güvenlik Açığı Yönetimi panosunu kullanın.

1. Microsoft 365 Defender portalında **Güvenlik açığı yönetimi****Panosu** > **Tehdit tanıma:**
:::image type="content" source="images/awareness_dashboard.png" alt-text="Güvenlik açığı yönetimi" lightbox="images/awareness_dashboard.png"::: >  panosundaki tehdit tanıma pencere öğesi bölümüne gidin
2. Kuruluşunuzun açığa çıkarma işleminin birleştirilmiş görünümünü görmek için **Güvenlik açığı ayrıntılarını görüntüle'yi** seçin.
:::image type="content" source="images/view_vulnerability_details.png" alt-text="CVE-2021-44228 (Log4j) için güvenlik açığı ayrıntıları sayfası" lightbox="images/view_vulnerability_details.png":::
3. Pozlamanızın aşağıdakilere göre bölünmesini görmek için ilgili sekmeyi seçin:
    - Kullanıma sunulan cihazlar – ekleme
    - Kullanıma sunulan cihazlar – eklenmemiş
    - Güvenlik açığı olan dosyalar
    - Güvenlik açığı bulunan yazılımlar

### <a name="log4shell-vulnerability-mitigation"></a>Log4Shell güvenlik açığı azaltma

Log4J sürüm 2.10 - 2.14.1'de varsayılan yapılandırmalarla JNDI aramaları engellenerek log4Shell güvenlik açığı giderilebilir. Bu risk azaltma eylemini oluşturmak için **Tehdit tanıma panosundan**:

1. **Güvenlik açığı ayrıntılarını görüntüle'yi** seçin
2. **Azaltma seçeneklerini belirleme**

Risk azaltmayı kullanıma sunulan tüm cihazlara uygulamayı veya eklenen belirli cihazları seçebilirsiniz. İşlemi tamamlamak ve azaltmayı cihazlara uygulamak için **Azaltma eylemi oluştur'u** seçin.

:::image type="content" source="images/mitigation_options.png" alt-text="CVE-2021-44228 için azaltma seçenekleri" lightbox="images/mitigation_options.png":::

### <a name="mitigation-status"></a>Azaltma durumu

Azaltma durumu, JDNI aramalarını devre dışı bırakmaya yönelik geçici çözüm azaltmasının cihaza uygulanıp uygulanmadığını gösterir. Etkilenen her cihazın risk azaltma durumunu Kullanıma sunulan cihazlar sekmelerinde görüntüleyebilirsiniz. Bu, cihazların risk azaltma durumlarına göre risk azaltma ve/veya düzeltme eki uygulama önceliklerini belirlemeye yardımcı olabilir.

:::image type="content" source="images/mitigation_status.png" alt-text="Olası risk azaltma durumları" lightbox="/mitigation_status.png":::

Aşağıdaki tabloda olası risk azaltma durumları listelenmiştir:

| Azaltma durumu | Açıklama |
|:---|:---|
| Geçici çözüm uygulandı | _Windows_: LOG4J_FORMAT_MSG_NO_LOOKUPS ortam değişkeni en son cihaz yeniden başlatmadan önce gözlemlendi. <br/><br/> _Linux + macOS_: Çalışan tüm işlemlerin ortam değişkenlerinde LOG4J_FORMAT_MSG_NO_LOOKUPS=true değeri vardır. |
| Geçici çözüm yeniden başlatma bekliyor | LOG4J_FORMAT_MSG_NO_LOOKUPS ortam değişkeni ayarlandı, ancak aşağıdaki yeniden başlatma algılanmadı. |
| Uygulanmadı | _Windows_: LOG4J_FORMAT_MSG_NO_LOOKUPS ortam değişkeni gözlemlenmedi. <br/><br/> _Linux + macOS_: Tüm çalışan işlemlerin ortam değişkenlerinde LOG4J_FORMAT_MSG_NO_LOOKUPS=true değeri yoktur ve cihaza azaltma eylemi uygulanmamıştır. |
| Kısmen azaltılmış | _Linux + macOS_: Cihazda azaltma eylemi uygulansa da, çalışan tüm işlemlerin ortam değişkenlerinde LOG4J_FORMAT_MSG_NO_LOOKUPS=true değeri yoktur. |
|Geçerli değil | Risk azaltmanın sürüm aralığında olmayan güvenlik açığı olan dosyalara sahip cihazlar. |
|Unknown | Azaltma durumu şu anda belirlenemedi. |

> [!NOTE]
> Bir cihazın güncelleştirilmiş risk azaltma durumunun yansıtılması birkaç saat sürebilir.

### <a name="revert-mitigations-applied-for-the-log4shell-vulnerability"></a>Log4Shell güvenlik açığı için uygulanan azaltmaları geri döndürme

Risk azaltmanın geri alınması gereken durumlarda şu adımları izleyin:

**_Windows için:_**

1. Yükseltilmiş bir PowerShell penceresi açma
2. Aşağıdaki komutu çalıştırın:

 ```Powershell
   [Environment]::SetEnvironmentVariable("LOG4J\_FORMAT\_MSG\_NO\_LOOKUPS", $null,[EnvironmentVariableTarget]::Machine)
```

Cihaz yeniden başlatıldıktan sonra değişiklik geçerli olur.

**_Linux için:_**

1. /etc/environment dosyasını açın ve LOG4J\_FORMAT\_MSG\_NO\_LOOKUPS=true satırını silin
2. /etc/systemd/system.conf.d/log4j\_dosyasını silin jndi\_lookups.conf dosyasını devre dışı bırakın\_
3. /etc/systemd/user.conf.d/log4j\_dosyasını silin jndi\_lookups.conf dosyasını devre dışı bırakın\_

Cihaz yeniden başlatıldıktan sonra değişiklik geçerli olur.

**_macOS için:_**

setenv dosyasını kaldırın. LOG4J\_FORMAT\_MSG\_NO\_LOOKUPS.plist aşağıdaki klasörlerden:

- */Library/LaunchDaemons/*
- */Library/LaunchAgents/*
- */Users/\[username\]/Library/LaunchAgents/ - tüm kullanıcılar için*

Cihaz yeniden başlatıldıktan sonra değişiklik geçerli olur.

### <a name="apache-log4j-security-recommendations"></a>Apache Log4j güvenlik önerileri

Apache log4j ile ilgili etkin güvenlik önerisini görmek için güvenlik açığı ayrıntıları sayfasından **Güvenlik önerileri** sekmesini seçin. Bu örnekte **Apache Log4j'yi Güncelleştir'i** seçerseniz daha fazla bilgi içeren başka bir açılır öğe görürsünüz:

:::image type="content" source="images/update_apache_log4j.png" alt-text="Apache log4j güvenlik önerisini güncelleştirme" lightbox="images/update_apache_log4j.png":::

Düzeltme isteği oluşturmak için Düzeltme **iste'yi** seçin.

## <a name="explore-the-vulnerability-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında güvenlik açığını keşfetme

Kullanıma sunulan cihazlar, dosyalar ve yazılımlar bulunduktan sonra, ilgili bilgiler Microsoft 365 Defender portalında aşağıdaki deneyimler aracılığıyla da iletilir:

### <a name="security-recommendations"></a>Güvenlik önerileri

Log4Shell güvenlik açığını ele alan güvenlik önerilerini görmek için **CVE-2021-44228** araması yapın:

:::image type="content" source="images/security_recommendations_log4j.png" alt-text="Güvenlik önerileri sayfasındaki log4j güvenlik açığı" lightbox="images/security_recommendations_log4j.png":::

### <a name="software-inventory"></a>Yazılım envanteri

 Log4j yazılım yüklemeleri ve açığa çıkarma hakkındaki ayrıntıları görmek için yazılım envanteri sayfasında **CVE-2021-44228** araması yapın:

:::image type="content" source="images/software_inventory_log4j.png" alt-text="Yazılım envanteri sayfasındaki log4j güvenlik açığı" lightbox="images/software_inventory_log4j.png":::

### <a name="weaknesses"></a>Zayıf

Zayıflıklar sayfasında, Log4Shell güvenlik açığı hakkındaki bilgileri görmek için **CVE-2021-44228** araması yapın:

:::image type="content" source="images/weaknesses_log4j.png" alt-text="Zayıflıklar sayfasındaki log4j güvenlik açığı" lightbox="images/weaknesses_log4j.png":::

## <a name="use-advanced-hunting"></a>Gelişmiş avcılığı kullanma

Cihazlarda yüklü yazılımlardaki güvenlik açıklarını belirlemek için aşağıdaki gelişmiş tehdit avcılığı sorgusunu kullanabilirsiniz:

 ```text
    DeviceTvmSoftwareVulnerabilities
    | where CveId in ("CVE-2021-44228", "CVE-2021-45046")
 ```

Diskteki dosya düzeyinde bulguları ortaya çıkarma amacıyla cihazlarda yüklü yazılımdaki güvenlik açıklarını belirlemek için aşağıdaki gelişmiş tehdit avcılığı sorgusunu kullanabilirsiniz:

 ```text
    DeviceTvmSoftwareEvidenceBeta
    | mv-expand DiskPaths
    | where DiskPaths contains "log4j"
    | project DeviceId, SoftwareName, SoftwareVendor, SoftwareVersion, DiskPaths
 ```

## <a name="related-articles"></a>İlgili makaleler

- [Tehdit ve güvenlik açığı yönetimine genel bakış](http://next-gen-threat-and-vuln-mgt.md)
- [Güvenlik önerileri](tvm-security-recommendation.md)