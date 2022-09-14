---
title: Linux'ta Uç Nokta için Microsoft Defender için dışlamaları yapılandırma ve doğrulama
description: Linux'ta Uç Nokta için Microsoft Defender için dışlamalar sağlayın ve doğrulayın. Dosyalar, klasörler ve işlemler için dışlamalar ayarlanabilir.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, dışlamalar, taramalar, virüsten koruma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 19d21a465bd4cd663dee2c1e26f9b5598fb345ed
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67683439"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>Linux'ta Uç Nokta için Microsoft Defender için dışlamaları yapılandırma ve doğrulama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Bu makalede, isteğe bağlı taramalar ve gerçek zamanlı koruma ve izleme için geçerli olan dışlamaların nasıl tanımlanacağı hakkında bilgi sağlanır.

> [!IMPORTANT]
> Bu makalede açıklanan dışlamalar, uç nokta algılama ve yanıt (EDR) dahil olmak üzere Linux üzerinde Uç Nokta için Defender özellikleri için geçerli değildir. Bu makalede açıklanan yöntemleri kullanarak dışladığınız dosyalar yine de EDR uyarılarını ve diğer algılamaları tetikleyebilir.

Linux taramalarında uç nokta için Defender'ın belirli dosyaları, klasörleri, işlemleri ve işlem tarafından açılan dosyaları hariç tutabilirsiniz.

Dışlamalar, kuruluşunuz için benzersiz veya özelleştirilmiş dosya veya yazılımlarda yanlış algılamalardan kaçınmak için yararlı olabilir. Bunlar, Linux'ta Uç Nokta için Defender'ın neden olduğu performans sorunlarını azaltmak için de yararlı olabilir.

> [!WARNING]
> Dışlamaların tanımlanması, Linux'ta Uç Nokta için Defender tarafından sunulan korumayı düşürür. Dışlamaları uygulamayla ilişkili riskleri her zaman değerlendirmeli ve yalnızca kötü amaçlı olmadığından emin olduğunuz dosyaları hariç tutmalısınız.

## <a name="supported-exclusion-types"></a>Desteklenen dışlama türleri

Aşağıdaki tabloda, Linux üzerinde Uç Nokta için Defender tarafından desteklenen dışlama türleri gösterilmektedir.

Dışlama|Tanım|Örnekler
---|---|---
Dosya uzantısı|Uzantılı tüm dosyalar, cihazın herhangi bir yerinde|`.test`
Dosya|Tam yol tarafından tanımlanan belirli bir dosya|`/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Klasör|Belirtilen klasör altındaki tüm dosyalar (özyinelemeli olarak)|`/var/log/`<br/>`/var/*/`
Işlem|Belirli bir işlem (tam yol veya dosya adıyla belirtilir) ve tarafından açılan tüm dosyalar|`/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> Yukarıdaki yolların başarıyla dışlanması için sembolik bağlantılar değil sabit bağlantılar olması gerekir. komutunu çalıştırarak `file <path-name>`yolun sembolik bir bağlantı olup olmadığını de kontrol edebilirsiniz.

Dosya, klasör ve işlem dışlamaları aşağıdaki joker karakterleri destekler:

Joker|Açıklama|Örnek|Eşleşen|Eşleşmiyor
---|---|---|---|---
\*|Hiçbiri dahil olmak üzere herhangi bir sayıda karakterle eşleşir (bu joker karakter bir yolun içinde kullanıldığında yalnızca bir klasörü değiştireceğini unutmayın)|`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`
?|Herhangi bir tek karakterle eşleşir|`file?.log`|`file1.log`<br/>`file2.log`|`file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>Dışlama listesini yapılandırma

### <a name="from-the-management-console"></a>Yönetim konsolundan

Puppet, Ansible veya başka bir yönetim konsolundan dışlamaları yapılandırma hakkında daha fazla bilgi için bkz. [Linux'ta Uç Nokta için Defender tercihlerini ayarlama](linux-preferences.md).

### <a name="from-the-command-line"></a>Komut satırından

Dışlamaları yönetmek için kullanılabilir anahtarları görmek için aşağıdaki komutu çalıştırın:

```bash
mdatp exclusion
```

> [!TIP]
> Dışlamaları joker karakterlerle yapılandırırken, globbing'i önlemek için parametresini çift tırnak içine alın.

Örnekler:

- Dosya uzantısı için dışlama ekleyin:

    ```bash
    mdatp exclusion extension add --name .txt
    ```

    ```Output
    Extension exclusion configured successfully
    ```

- Dosya için dışlama ekleyin:

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```

    ```Output
    File exclusion configured successfully
    ```

- Klasör için dışlama ekleyin:

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```

    ```Output
    Folder exclusion configured successfully
    ```

- İkinci klasör için dışlama ekleyin:

    ```bash
    mdatp exclusion folder add --path /var/log/
    mdatp exclusion folder add --path /other/folder
    ```

    ```Output
    Folder exclusion configured successfully
    ```

- Içinde joker karakter bulunan bir klasör için dışlama ekleyin:

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > Bu, */var/* altındaki yolları yalnızca bir düzey hariç tutar, ancak daha derin iç içe yerleştirilmiş klasörleri dışlamaz; örneğin, */var/this-subfolder/but-not-this-subfolder*.

    ```bash
    mdatp exclusion folder add --path "/var/"
    ```

    > [!NOTE]
    > Bu, üst öğesi */var/*; olan tüm yolları dışlar; örneğin, */var/this-subfolder/and-this-subfolder-as-well*.

    ```Output
    Folder exclusion configured successfully
    ```

- Bir işlem için dışlama ekleyin:

    ```bash
    mdatp exclusion process add --name cat
    ```

    ```Output
    Process exclusion configured successfully
    ```

- İkinci bir işlem için dışlama ekleyin:

    ```bash
    mdatp exclusion process add --name cat
    mdatp exclusion process add --name dog
    ```

    ```Output
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>EICAR test dosyasıyla dışlama listelerini doğrulama

Bir test dosyasını indirmek için kullanarak `curl` dışlama listelerinizin çalıştığını doğrulayabilirsiniz.

Aşağıdaki Bash kod parçacığında öğesini dışlama kurallarınıza uygun bir dosyayla değiştirin `test.txt` . Örneğin, uzantıyı `.testing` dışladıysanız değerini ile `test.testing`değiştirin`test.txt`. Bir yolu test ediyorsanız, komutu bu yol içinde çalıştırdığınızdan emin olun.

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Linux'ta Uç Nokta için Defender kötü amaçlı yazılım bildiriyorsa kural çalışmıyor demektir. Kötü amaçlı yazılım raporu yoksa ve indirilen dosya varsa, dışlama çalışıyor demektir. İçeriğin [EICAR test dosyası web sitesinde](http://2016.eicar.org/86-0-Intended-use.html) açıklananla aynı olduğunu onaylamak için dosyayı açabilirsiniz.

İnternet erişiminiz yoksa kendi EICAR test dosyanızı oluşturabilirsiniz. Aşağıdaki Bash komutuyla EICAR dizesini yeni bir metin dosyasına yazın:

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

Ayrıca, dizeyi boş bir metin dosyasına kopyalayabilir ve dosya adıyla veya dışlamaya çalıştığınız klasöre kaydetmeye çalışabilirsiniz.

## <a name="allow-threats"></a>Tehditlere izin ver

Belirli içeriklerin taranmasını dışlamanın yanı sıra, ürünü bazı tehdit sınıflarını (tehdit adıyla tanımlanır) algılamayacak şekilde de yapılandırabilirsiniz. Bu işlevi kullanırken dikkatli olmanız gerekir, bu nedenle cihazınız korumasız bırakılabilir.

İzin verilenler listesine bir tehdit adı eklemek için aşağıdaki komutu yürütür:

```bash
mdatp threat allowed add --name [threat-name]
```

Cihazınızdaki bir algılamayla ilişkili tehdit adı aşağıdaki komut kullanılarak alınabilir:

```bash
mdatp threat list
```

Örneğin, izin verilenler listesine (EICAR algılamasıyla ilişkili tehdit adı) eklemek `EICAR-Test-File (not a virus)` için aşağıdaki komutu yürütür:

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
