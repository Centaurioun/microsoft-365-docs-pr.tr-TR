---
title: Microsoft Defender Virüsten Koruma için performans çözümleyicisi
description: Microsoft Defender Virüsten Koruma'nın performansını ayarlama yordamını açıklar.
keywords: tune, performance, uç nokta için microsoft defender, defender virüsten koruma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.date: 08/13/2022
manager: dansimp
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 6fbb5d6a3ef37b3dde4f453c4e1823e3030617ed
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67687669"
---
# <a name="performance-analyzer-for-microsoft-defender-antivirus"></a>Microsoft Defender Virüsten Koruma için performans çözümleyicisi

**Uygulandığı öğe**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**

- Windows

## <a name="what-is-microsoft-defender-antivirus-performance-analyzer"></a>Microsoft Defender Virüsten Koruma performans çözümleyicisi nedir?

Bazı durumlarda, belirli dosya ve klasörleri tararken Microsoft Defender Virüsten Koruma'nın performansını ayarlamanız gerekebilir. Performans çözümleyicisi, hangi dosyaların, dosya uzantılarının ve işlemlerin tek tek uç noktalarda performans sorunlarına neden olabileceğini saptamaya yardımcı olan bir PowerShell komut satırı aracıdır. Bu bilgiler, performans sorunlarını daha iyi değerlendirmek ve düzeltme eylemleri uygulamak için kullanılabilir.

Analiz etmek için bazı seçenekler şunlardır:

- Tarama süresini etkileyen en iyi yollar
- Tarama süresini etkileyen en önemli dosyalar
- Tarama süresini etkileyen en önemli işlemler
- Tarama süresini etkileyen en iyi dosya uzantıları
- Kombinasyonlar – örneğin:
  - uzantı başına en çok kullanılan dosyalar
  - uzantı başına en iyi yollar
  - yol başına en üstteki işlemler
  - dosya başına en çok tarama
  - işlem başına dosya başına en çok tarama
  
## <a name="running-performance-analyzer"></a>Performans çözümleyicisi çalıştırma

Performans çözümleyicisini çalıştırmaya yönelik üst düzey işlem aşağıdaki adımları içerir:

1. Uç noktadaki Microsoft Defender Virüsten Koruma olaylarının performans kaydını toplamak için performans çözümleyicisini çalıştırın.

   > [!NOTE]
   > **Microsoft-Antimalware-Engine** türündeki Microsoft Defender Virüsten Koruma olaylarının performansı performans çözümleyicisi aracılığıyla kaydedilir.

2. Farklı kayıt raporları kullanarak tarama sonuçlarını analiz edin.

## <a name="using-performance-analyzer"></a>Performans çözümleyicisi kullanma

Sistem olaylarını kaydetmeye başlamak için PowerShell'i yönetim modunda açın ve aşağıdaki adımları uygulayın:

1. Kaydı başlatmak için aşağıdaki komutu çalıştırın:

   `New-MpPerformanceRecording -RecordTo <recording.etl>`

    where `-RecordTo` parametresi, izleme dosyasının kaydedildiği tam yol konumunu belirtir. Daha fazla cmdlet bilgisi için bkz. [Microsoft Defender Virüsten Koruma cmdlet'leri](/powershell/module/defender).

2. Performansı etkilediği düşünülen süreçler veya hizmetler varsa, ilgili görevleri gerçekleştirerek durumu yeniden oluşturun.

3. Kaydı durdurmak ve kaydetmek için **ENTER** tuşuna veya kaydı iptal etmek için **Ctrl+C** tuşlarına basın.

4. Performans çözümleyicisinin `Get-MpPerformanceReport`parametresini kullanarak sonuçları analiz edin. Örneğin, komutunu `Get-MpPerformanceReport -Path <recording.etl> -TopFiles 3 -TopScansPerFile 10`yürütürken kullanıcıya performansı etkileyen ilk 3 dosya için ilk on taramanın listesi sağlanır.

Komut satırı parametreleri ve seçenekleri hakkında daha fazla bilgi için bkz. [New-MpPerformanceRecording](#new-mpperformancerecording) ve [Get-MpPerformanceReport](#get-mpperformancereport).

> [!NOTE]
> Kayıt çalıştırırken "Windows Performans Kaydedicisi zaten kayıtta olduğundan performans kaydı başlatılamıyor" hatasını alırsanız, yeni komutla var olan izlemeyi durdurmak için aşağıdaki komutu çalıştırın: **wpr -cancel -instancename MSFT_MpPerformanceRecording**

## <a name="performance-tuning-data-and-information"></a>Performans ayarlama verileri ve bilgileri

Sorguya bağlı olarak, kullanıcı tarama sayıları, süre (toplam/min/ortalama/maksimum/ortanca), yol, işlem ve **tarama nedeni verilerini** görüntüleyebilir. Aşağıdaki resimde tarama etkisi için ilk 10 dosyanın basit bir sorgusu için örnek çıktı gösterilmektedir.

:::image type="content" source="images/example-output.png" alt-text="Temel topfiles sorgusu için örnek çıktı" lightbox="images/example-output.png":::

## <a name="additional-functionality-exporting-and-converting-to-csv-and-json"></a>Ek işlevsellik: CSV ve JSON'a dışarı aktarma ve dönüştürme

Performans çözümleyicisinin sonuçları da dışarı aktarılabilir ve csv veya JSON dosyasına dönüştürülebilir.
Örnek kodlar aracılığıyla "dışarı aktarma" ve "dönüştürme" işlemini açıklayan örnekler için aşağıya bakın.

Defender sürüm 4.18.2206.X'den başlayarak, kullanıcılar "SkipReason" sütunu altında tarama atlama nedeni bilgilerini görüntüleyebilir. Olası değerler:

1. Atlanmamış
1. İyileştirme (genellikle performans nedenlerinden dolayı)
1. Kullanıcı atlandı (genellikle kullanıcı kümesi dışlamaları nedeniyle)

### <a name="for-csv"></a>CSV için

- **Dışarı aktarmak için**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | Export-CSV -Path:.\Repro-Install-Scans.csv -Encoding:UTF8 -NoTypeInformation`

- **Dönüştürmek için**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:100). TopScans | ConvertTo-Csv -NoTypeInformation`

### <a name="for-json"></a>JSON için

- **Dönüştürmek için**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | ConvertTo-Json -Depth:1`

Diğer veri işleme sistemleriyle dışarı aktarma için makine tarafından okunabilir bir çıkış sağlamak için Get-MpPerformanceReport için -Raw parametresinin kullanılması önerilir. Ayrıntılar için aşağıya bakın

## <a name="requirements"></a>Gereksinimler

Microsoft Defender Virüsten Koruma performans çözümleyicisi aşağıdaki önkoşullara sahiptir:

- Desteklenen Windows sürümleri: Windows 10, Windows 11 ve Windows Server 2016 ve üzeri
- Platform Sürümü: 4.18.2108.7+
- PowerShell Sürümü: PowerShell Sürüm 5.1, PowerShell ISE, uzak PowerShell (4.18.2201.10+), PowerShell 7.x (4.18.2201.10+)

## <a name="powershell-reference"></a>PowerShell başvurusu

Microsoft Defender Virüsten Koruma'nın performansını ayarlamak için kullanılan iki yeni PowerShell cmdlet'i vardır:

- [New-MpPerformanceRecording](#new-mpperformancerecording)
- [Get-MpPerformanceReport](#get-mpperformancereport)

### <a name="new-mpperformancerecording"></a>New-MpPerformanceRecording

Aşağıdaki bölümde New-MpPerformanceRecording yeni PowerShell cmdlet'inin başvurusu açıklanmaktadır. Bu cmdlet, Microsoft Defender Virüsten Koruma taramalarının performans kaydını toplar.

#### <a name="syntax-new-mpperformancerecording"></a>Söz dizimi: New-MpPerformanceRecording

```powershell
New-MpPerformanceRecording -RecordTo <String >
```

#### <a name="description-new-mpperformancerecording"></a>Açıklama: New-MpPerformanceRecording

Cmdlet, `New-MpPerformanceRecording` Microsoft Defender Virüsten Koruma taramalarının performans kaydını toplar. Bu performans kayıtları Microsoft-Antimalware-Engine ve NT çekirdek işlemi olaylarını içerir ve [Get-MpPerformanceReport](#get-mpperformancereport) cmdlet'i kullanılarak koleksiyondan sonra analiz edilebilir.

Bu `New-MpPerformanceRecording` cmdlet, Microsoft Defender Virüsten Koruma'nın performansında düşüşe neden olabilecek sorunlu dosyalar hakkında içgörü sağlar. Bu araç "OLDUĞU GIBI" sağlanır ve dışlamalarla ilgili öneriler sağlamak üzere tasarlanmamıştır. Dışlamalar uç noktalarınızdaki koruma düzeyini azaltabilir. Varsa dışlamalar dikkatle tanımlanmalıdır.

Performans çözümleyicisi hakkında daha fazla bilgi için bkz. [Performans Analizi](/windows-hardware/test/wpt/windows-performance-analyzer) belgeleri.

> [!IMPORTANT]
> Bu cmdlet yükseltilmiş yönetici ayrıcalıkları gerektirir.

**Desteklenen işletim sistemi sürümleri**:

Windows Sürüm 10 ve üzeri.

> [!NOTE]
> Bu özellik, 4.18.2108.X ve sonraki platform sürümlerinden itibaren kullanılabilir.

#### <a name="examples-new-mpperformancerecording"></a>Örnekler: New-MpPerformanceRecording

##### <a name="example-1-collect-a-performance-recording-and-save-it"></a>Örnek 1: Performans kaydı toplama ve kaydetme

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

Yukarıdaki komut bir performans kaydı toplar ve bunu belirtilen yola kaydeder: **.\Defender-scans.etl**.

##### <a name="example-2-collect-a-performance-recording-for-remote-powershell-session"></a>Örnek 2: Uzak PowerShell oturumu için performans kaydı toplama

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
New-MpPerformanceRecording -RecordTo C:\LocalPathOnServer02\trace.etl -Session $s
```

Yukarıdaki komut Server02'de bir performans kaydı toplar (Session parametresinin bağımsız değişkeni $s belirtildiği gibi) ve bunu belirtilen yola kaydeder: **Server02'de C:\LocalPathOnServer02\trace.etl** .

##### <a name="example-3-collect-a-performance-recording-in-non-interactive-mode"></a>Örnek 3: Etkileşimli olmayan modda performans kaydı toplama

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl -Seconds 60
```

Yukarıdaki komut, -Seconds parametresi tarafından belirtilen saniye cinsinden süre için bir performans kaydı toplar. Bu, etkileşim veya istem gerektirmeyen toplu koleksiyonlar yürüten kullanıcılar için önerilir.

#### <a name="parameters-new-mpperformancerecording"></a>Parametreler: New-MpPerformanceRecording

##### <a name="-recordto"></a>-RecordTo

Microsoft Defender Kötü Amaçlı Yazılımdan Koruma performans kaydının kaydedildiği konumu belirtir.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-session"></a>-Oturum

Microsoft Defender Virüsten Koruma performans kaydının oluşturulup kaydedildiği PSSession nesnesini belirtir. Bu parametreyi kullandığınızda, RecordTo parametresi uzak makinedeki yerel yola başvurur. Defender platformu sürüm 4.18.2201.10 ile kullanılabilir.

```yaml
Type: PSSession[]
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-seconds"></a>-Saniye

Performans kaydının süresini saniye cinsinden belirtir. Bu, etkileşim veya istem gerektirmeyen toplu koleksiyonlar yürüten kullanıcılar için önerilir.

```yaml
Type: Int32
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="get-mpperformancereport"></a>Get-MpPerformanceReport

Aşağıdaki bölümde Get-MpPerformanceReport PowerShell cmdlet'i açıklanmaktadır. Microsoft Defender Virüsten Koruma performans kaydını analiz eder ve raporlar.

#### <a name="syntax-get-mpperformancereport"></a>Söz dizimi: Get-MpPerformanceReport

```powershell
Get-MpPerformanceReport    [-Path] <String>
    [-TopScans [<Int32>]]
    [-TopPaths [<Int32>] [-TopPathsDepth [<Int32>]]]
            [-TopScansPerPath [<Int32>]]
            [-TopFilesPerPath [<Int32>]
                    [-TopScansPerFilePerPath [<Int32>]]
                    ]
            [-TopExtensionsPerPath [<Int32>]
                    [-TopScansPerExtensionPerPath [<Int32>]]
                    ]
            [-TopProcessesPerPath [<Int32>]
                    [-TopScansPerProcessPerPath [<Int32>]]
                    ]
            ]
    [-TopFiles [<Int32>]
            [-TopScansPerFile [<Int32>]]
            [-TopProcessesPerFile [<Int32>]
                    [-TopScansPerProcessPerFile [<Int32>]]
                    ]
            ]
    [-TopExtensions [<Int32>]
            [-TopScansPerExtension [<Int32>]
            [-TopPathsPerExtension [<Int32>] [-TopPathsDepth [<Int32>]]
                    [-TopScansPerPathPerExtension [<Int32>]]
                    ]
            [-TopProcessesPerExtension [<Int32>]
                    [-TopScansPerProcessPerExtension [<Int32>]]
                    ]
            [-TopFilesPerExtension [<Int32>]
                    [-TopScansPerFilePerExtension [<Int32>]]
                    ]
            ]
    [-TopProcesses [<Int32>]
            [-TopScansPerProcess [<Int32>]]
            [-TopExtensionsPerProcess [<Int32>]
                    [-TopScansPerExtensionPerProcess [<Int32>]]
                    ]
            [-TopPathsPerProcess [<Int32>] [-TopPathsDepth [<Int32>]]
                    [-TopScansPerPathPerProcess [<Int32>]]
                    ]
            [-TopFilesPerProcess [<Int32>]
                    [-TopScansPerFilePerProcess [<Int32>]]
                    ]
            ]
    [-MinDuration <String>]
    [-Raw]

```

#### <a name="description-get-mpperformancereport"></a>Açıklama: Get-MpPerformanceReport

Cmdlet, `Get-MpPerformanceReport` daha önce toplanan bir Microsoft Defender Virüsten Koruma performans kaydını ([New-MpPerformanceRecording](#new-mpperformancerecording)) analiz eder ve Microsoft Defender Virüsten Koruma taramaları üzerinde en yüksek etkiye neden olan dosya yollarını, dosya uzantılarını ve işlemleri bildirir.

Performans çözümleyicisi, Microsoft Defender Virüsten Koruma'nın performansında düşüşe neden olabilecek sorunlu dosyalar hakkında içgörü sağlar. Bu araç "OLDUĞU GIBI" sağlanır ve dışlamalarla ilgili öneriler sağlamak üzere tasarlanmamıştır. Dışlamalar uç noktalarınızdaki koruma düzeyini azaltabilir. Varsa dışlamalar dikkatle tanımlanmalıdır.

Performans çözümleyicisi hakkında daha fazla bilgi için bkz. [Performans Analizi](/windows-hardware/test/wpt/windows-performance-analyzer) belgeleri.

**Desteklenen işletim sistemi sürümleri**:

Windows Sürüm 10 ve üzeri.

> [!NOTE]
> Bu özellik, 4.18.2108.X ve sonraki platform sürümlerinden itibaren kullanılabilir.

#### <a name="examples-get-mpperformancereport"></a>Örnekler: Get-MpPerformanceReport

##### <a name="example-1-single-query"></a>Örnek 1: Tek sorgu

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:20
```

##### <a name="example-2-multiple-queries"></a>Örnek 2: Birden çok sorgu

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10
```

##### <a name="example-3-nested-queries"></a>Örnek 3: İç içe sorgular

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopExtensionsPerProcess:3 -TopScansPerExtensionPerProcess:3
```

##### <a name="example-4-using--minduration-parameter"></a>Örnek 4: -MinDuration parametresini kullanma

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:100 -MinDuration:100ms
```

##### <a name="example-5-using--raw-parameter"></a>Örnek 5: -Raw parametresini kullanma

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10 -Raw | ConvertTo-Json
```

\-Yukarıdaki komutta Raw kullanılması, çıkışın makine tarafından okunabilir ve JSON gibi serileştirme biçimlerine dönüştürülebilir olması gerektiğini belirtir

#### <a name="parameters-get-mpperformancereport"></a>Parametreler: Get-MpPerformanceReport

##### <a name="-toppaths"></a>-TopPath'ler

Bir üst yol raporu isteğinde bulunur ve çıkış için "Süre" ölçütüne göre sıralanmış en iyi yol sayısını belirtir. Taramaları yollarına ve dizinlerine göre toplar. Kullanıcı, her düzeyde kaç dizin görüntülenmesi gerektiğini ve seçimin derinliğini belirtebilir.

- Tür: Int32
- Konum: Adlandırılmış
- Varsayılan değer: Yok
- İşlem hattı girişini kabul et: False
- Joker karakterleri kabul et: False

##### <a name="-toppathsdepth"></a>-TopPathsDepth

Toplanan yol sonuçlarını gruplandırmak ve görüntülemek için kullanılacak özyinelemeli derinliği belirtir. Örneğin, "C:\" 1 derinliğine karşılık gelir, "C:\Users\Foo" 3 derinliğe karşılık gelir.

Bu bayrak, diğer tüm Üst Yol seçeneklerine eşlik edebilir. Eksikse varsayılan değer olan 3 varsayılır. Değer 0 olamaz.

- Tür: Int32
- Konum: Adlandırılmış
- Varsayılan değer: 3
- İşlem hattı girişini kabul et: False
- Joker karakterleri kabul et: False

| Bayrak | Tanımı |
|:---|:---|  
|  -**TopScansPerPath** | Her üst yol için en iyi taramaların nasıl belirtileceğini belirtir. |
|  -**TopFilesPerPath** | Her üst yol için en çok kullanılan dosyaların nasıl belirtileceğini belirtir. |
|  -**TopScansPerFilePerPath** | "Süre" ölçütüne göre sıralanmış her bir üst yol için her bir üst dosya için kaç tane en çok taramanın çıkışını yapılacağını belirtir |
|  -**TopExtensionsPerPath** | Her üst yol için kaç tane üst uzantının çıkışını yapılacağını belirtir |
|  -**TopScansPerExtensionPerPath** | Her üst yol için her üst uzantı için kaç tane ilk taramanın çıkışını yapılacağını belirtir |
|  -**TopProcessesPerPath** | Her üst yol için kaç tane üst işlem çıkışı yapılacağını belirtir |
|  -**TopScansPerProcessPerPath** | Her üst yol için her bir üst işlem için kaç tane ilk taramanın çıkışını yapılacağını belirtir |
|  -**TopPathsPerExtension** | Her üst uzantı için çıkış için en çok kaç yol olduğunu belirtir |
|  -**TopScansPerPathPerExtension** | Her üst uzantı için her üst yol için kaç tane ilk taramanın çıkışını yapılacağını belirtir |
|  -**TopPathsPerProcess** | Her bir üst işlem için çıkış için kaç üst yol olduğunu belirtir |
|  -**TopScansPerPathPerProcess** | Her üst işlem için her üst yol için kaç tane ilk taramanın çıkışını yapılacağını belirtir |

##### <a name="-minduration"></a>-MinDuration

Rapora dahil edilen dosyaların, uzantıların ve işlemlerin tarama sürelerinin veya toplam tarama sürelerinin en düşük süresini belirtir;  **0,1234567sec**, **0,1234 ms**, **0,1us** veya geçerli bir TimeSpan gibi değerleri kabul eder.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-path"></a>-Yol

Bir veya daha fazla konumun yollarını belirtir.

```yaml
Type: String
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

##### <a name="-raw"></a>-Ham

Performans kaydının çıktısının makine tarafından okunabilir ve JSON gibi serileştirme biçimlerine (örneğin, JSON'a Dönüştür komutu aracılığıyla) dönüştürülebilir olması gerektiğini belirtir. Bu, diğer veri işleme sistemleriyle toplu işlemeyle ilgilenen kullanıcılar için önerilir.

```yaml
Type: <SwitchParameter>
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topextensions"></a>-TopExtensions

Çıkış için "Süre" ölçütüne göre sıralanmış en çok kaç uzantı olduğunu belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topextensionsperprocess"></a>-TopExtensionsPerProcess

"Süre" ölçütüne göre sıralanmış her bir üst işlem için kaç tane üst uzantının çıkışını yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topfiles"></a>-TopFiles

Bir en çok kullanılan dosyalar raporu istemektedir ve "Süre" ölçütüne göre sıralanmış en çok kaç dosyanın çıkışını oluşturacaklarını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topfilesperextension"></a>-TopFilesPerExtension

"Süre" ölçütüne göre sıralanmış her bir üst uzantı için en çok kaç dosyanın çıkışını yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topfilesperprocess"></a>-TopFilesPerProcess

"Süre" ölçütüne göre sıralanmış her bir üst işlem için en çok kaç dosyanın çıkışını yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topprocesses"></a>-TopProcesses

Bir üst işlemler raporu istemektedir ve "Süre" ölçütüne göre sıralanmış en çok kullanılan işlem sayısını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topprocessesperextension"></a>-TopProcessesPerExtension

"Süre" ölçütüne göre sıralanmış her bir üst uzantı için en çok kaç işlemin çıkışlanacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topprocessesperfile"></a>-TopProcessesPerFile

"Süre" ölçütüne göre sıralanmış, her bir üst dosya için kaç tane en çok işlem çıkışı yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscans"></a>-TopScans

Bir üst tarama raporu isteğinde bulunur ve "Süre" ölçütüne göre sıralanmış olarak kaç tane en çok tarama yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperextension"></a>-TopScansPerExtension

"Süre" ölçütüne göre sıralanmış her bir üst uzantı için kaç tane ilk taramanın çıkışını yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperextensionperprocess"></a>-TopScansPerExtensionPerProcess

"Süre" ölçütüne göre sıralanmış her üst işlem için her üst uzantı için kaç tane en çok tarama yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperfile"></a>-TopScansPerFile

"Süre" ölçütüne göre sıralanmış her bir üst dosya için en çok kaç taramanın çıkışını yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperfileperextension"></a>-TopScansPerFilePerExtension

"Süre" ölçütüne göre sıralanmış her üst uzantı için her bir üst dosya için çıkış olarak kaç tane en çok tarama yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperfileperprocess"></a>-TopScansPerFilePerProcess

"Süre" ölçütüne göre sıralanmış her üst işlem için her bir üst dosya için çıkış için en çok kaç tarama yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperprocess"></a>-TopScansPerProcess

"Süre" ölçütüne göre sıralanmış, En İyi İşlemler raporundaki her bir üst işlem için kaç tane en çok tarama yapılacağını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperprocessperextension"></a>-TopScansPerProcessPerExtension

"Süre" ölçütüne göre sıralanmış her üst uzantı için her bir üst işlem için en çok kaç tarama yapıldığını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperprocessperfile"></a>-TopScansPerProcessPerFile

"Süre" ölçütüne göre sıralanmış her bir üst dosya için her bir üst işlem için çıkış için en çok kaç tarama yapıldığını belirtir.

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## <a name="additional-resources"></a>Ek kaynaklar

Diğer platformlar için Virüsten Koruma ile ilgili bilgileri arıyorsanız bkz:

- [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
- [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
- [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
- [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
- [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
- [Android'de Uç Nokta için Defender özelliklerini](android-configure.md)-  yapılandırma [iOS özelliklerinde Uç Nokta için Microsoft Defender yapılandırma](ios-configure-features.md)
