---
title: Cihaz keşif ayarlarını yapılandırın
description: Temel veya standart bulma kullanarak Microsoft 365 Defender'de cihaz bulmayı yapılandırmayı öğrenin
keywords: temel, standart, uç nokta bulmayı yapılandırma, cihaz bulma
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 9fbff594d65ef51d351f9810764821914206be53
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67702434"
---
# <a name="configure-device-discovery"></a>Cihaz keşif ayarlarını yapılandırın

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Bulma, standart veya temel modda olacak şekilde yapılandırılabilir. Ağınızdaki cihazları etkin bir şekilde bulmak için standart seçeneği kullanın. Bu seçenek uç noktaların bulunmasını daha iyi garanti eder ve daha zengin cihaz sınıflandırması sağlar.

Standart bulma gerçekleştirmek için kullanılan cihazların listesini özelleştirebilirsiniz. Bu özelliği de destekleyen tüm eklenen cihazlarda standart bulmayı etkinleştirebilirsiniz (şu anda - Windows 10 veya üzeri ve yalnızca Windows Server 2019 veya üzeri cihazlar) ya da cihaz etiketlerini belirterek cihazlarınızın alt kümesini veya alt kümelerini seçebilirsiniz.

## <a name="set-up-device-discovery"></a>Cihaz bulmayı ayarlama

Cihaz bulmayı ayarlamak için <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalında</a> aşağıdaki yapılandırma adımlarını uygulayın:

**Ayarlar** > **Cihaz bulma'ya** gidin

1. Temel'i eklenen cihazlarınızda kullanılacak bulma modu olarak yapılandırmak istiyorsanız **Temel'i** ve ardından **Kaydet'i** seçin
2. Standart bulma'yı kullanmayı seçtiyseniz, etkin yoklama için hangi cihazların kullanılacağını seçin: tüm cihazlar veya cihaz etiketlerini belirterek bir alt kümede ve ardından **Kaydet'i** seçin

> [!NOTE]
>Standart bulma, ağdaki cihazları etkin bir şekilde araştırmak için çeşitli PowerShell betikleri kullanır. Bu PowerShell betikleri Microsoft tarafından imzalanmıştır ve şu konumdan yürütülür: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`. Örneğin, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>Cihazları standart bulmada etkin bir şekilde yoklamanın dışında tutma

Ağınızda etkin olarak taranmaması gereken cihazlar varsa (örneğin, başka bir güvenlik aracı için bal arısı olarak kullanılan cihazlar), taranmalarını önlemek için bir dışlama listesi de tanımlayabilirsiniz. Cihazların hala Temel bulma modu kullanılarak bulunabileceğini ve çok noktaya yayın bulma denemeleri aracılığıyla da bulunabileceğini unutmayın. Bu cihazlar pasif olarak bulunacaktır ancak etkin bir şekilde yoklamayacaktır.

**Dışlamalar** sayfasında cihazları dışlamak üzere yapılandırabilirsiniz.

## <a name="select-networks-to-monitor"></a>İzlenecek ağları seçin

Uç Nokta için Microsoft Defender bir ağı analiz eder ve bunun izlenmesi gereken bir şirket ağı mı yoksa yoksa yoksayılabilir kurumsal olmayan bir ağ mı olduğunu belirler. Bir ağı şirket olarak tanımlamak için, ağ tanımlayıcılarını tüm kiracının istemcileri arasında ilişkilendiriyoruz ve kuruluştaki cihazların çoğu aynı ağ adına bağlı olduklarını bildiriyorsa, aynı varsayılan ağ geçidi ve DHCP sunucusu adresiyle bunun bir kurumsal ağ olduğunu varsayarız. Şirket ağları genellikle izlenmesi için seçilir. Ancak, eklenen cihazların bulunduğu şirket dışı ağları izlemeyi seçerek bu kararı geçersiz kılabilirsiniz.

Hangi ağların izleneceğini belirterek cihaz bulmanın nerede gerçekleştirilebileceğini yapılandırabilirsiniz. Bir ağ izlendiğinde, üzerinde cihaz bulma işlemi gerçekleştirilebilir.

cihaz bulma işleminin gerçekleştirilebileceği ağların listesi **, İzlenen ağlar** sayfasında gösterilir.

> [!NOTE]
> Listede, şirket ağları olarak tanımlanan ağlar gösterilir. 50'den az ağ kurumsal ağ olarak tanımlanırsa, liste en çok eklenen cihazlara sahip en fazla 50 ağ gösterir.

İzlenen ağların listesi, ağda son 7 gün içinde görülen toplam cihaz sayısına göre sıralanır.

Aşağıdaki ağ bulma durumlarından herhangi birini görüntülemek için bir filtre uygulayabilirsiniz:

- **İzlenen ağlar** - Cihaz bulma işleminin gerçekleştirildiği ağlar.
- **Yoksayılan ağlar** - Bu ağ yoksayılır ve cihaz bulma işlemi gerçekleştirilmez.
- **Tümü** - Hem izlenen hem de yoksayılan ağlar görüntülenir.

### <a name="configure-the-network-monitor-state"></a>Ağ izleyici durumunu yapılandırma

Cihaz bulmanın nerede gerçekleşeceği sizin denetiminizdir. İzlenen ağlar, cihaz bulma işleminin gerçekleştirileceği yerdir ve genellikle kurumsal ağlardır. Ayrıca, bir durumu değiştirdikten sonra ağları yoksaymayı veya ilk bulma sınıflandırmasını seçebilirsiniz.

İlk bulma sınıflandırmasını seçmek, varsayılan sistem tarafından yapılmış ağ izleyici durumunun uygulanması anlamına gelir. Sistem tarafından yapılan varsayılan ağ izleme durumunun seçilmesi, şirket olduğu belirlenen ağların izleneceği ve şirket dışı olarak tanımlanan ağların otomatik olarak yoksayılacağı anlamına gelir.

1. **Cihaz bulma > Ayarlar'ı** seçin.
2. **İzlenen ağlar'ı** seçin.
3. Ağ listesini görüntüleyin.
4. Ağ adının yanındaki üç noktayı seçin.
5. İlk bulma sınıflandırmasını izlemek, yoksaymak veya kullanmak isteyip istemediğinizi seçin.

    > [!WARNING]
    >
    > - Uç Nokta için Microsoft Defender tarafından şirket ağı olarak tanımlanmayan bir ağı izlemeyi seçmek, şirket ağınızın dışında cihaz bulma işlemine neden olabilir ve bu nedenle ev veya şirket dışı cihazları algılayabilir.
    > - Bir ağı yoksaymayı seçmek, o ağdaki cihazları izlemeyi ve bulmayı durdurur. Önceden bulunan cihazlar envanterden kaldırılmaz, ancak artık güncelleştirilmez ve Uç Nokta için Defender'ın veri saklama süresi dolana kadar ayrıntılar korunur.
    > - Şirket dışı ağları izlemeyi seçmeden önce, bunu yapmak için izniniz olduğundan emin olmanız gerekir. <br>

6. Değişikliği yapmak istediğinizi onaylayın.

## <a name="explore-devices-in-the-network"></a>Ağdaki cihazları keşfetme

Ağ listesinde açıklanan her ağ adı hakkında daha fazla bağlam elde etmek için aşağıdaki gelişmiş tehdit avcılığı sorgusunu kullanabilirsiniz. Sorgu, son 7 gün içinde belirli bir ağa bağlı olan tüm eklenen cihazları listeler.

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="get-information-on-device"></a>Cihazla ilgili bilgi alma

Belirli bir cihazda en son eksiksiz bilgileri almak için aşağıdaki gelişmiş tehdit avcılığı sorgusunu kullanabilirsiniz.

```kusto
DeviceInfo
| where DeviceName == "<device name here>" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="see-also"></a>Ayrıca bkz.

- [Cihaz keşfine genel bakış](device-discovery.md)
- [Cihaz bulma hakkında SSS](device-discovery-faq.md)
