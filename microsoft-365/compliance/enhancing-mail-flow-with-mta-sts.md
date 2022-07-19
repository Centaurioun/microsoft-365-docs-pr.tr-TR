---
title: 'MTA-STS ile posta akışını iyileştirme '
f1.keywords:
- NOCSH
ms.author: v-bshilpa
author: Benny-54
manager: serdars
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: MTA-STS ile posta akışını geliştirmeyi öğrenin.
ms.openlocfilehash: 735cce96c61a2083b8f0785ace49a5b199790989
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2022
ms.locfileid: "66861610"
---
# <a name="enhancing-mail-flow-with-mta-sts"></a>MTA-STS ile posta akışını iyileştirme

[Exchange Online SMTP MTA Strict Transport Security](https://datatracker.ietf.org/doc/html/rfc8461) (MTA-STS) standardı desteği eklenir. Standart, TLS'nin her zaman e-posta sunucuları arasındaki bağlantılar için kullanıldığından emin olmak için geliştirilmiştir. Ayrıca, alıcı sunucunun güvenilir bir sertifikaya sahip olduğunu doğrulamak için sunucu göndermek için bir yol sağlar. TLS sunulmazsa veya sertifika geçerli değilse, gönderen iletileri teslim etmeyi reddeder. Bu yeni denetimler SMTP'nin genel güvenliğini artırır ve ortadaki adam saldırılarına karşı koruma sağlar.

MTA-STS iki senaryoya ayrılabilir: Gelen ve Giden Koruma. Gelen, MTA-STS ile Exchange Online barındırılan etki alanlarının korumasını kapsar ve Giden, MTA-STS korumalı etki alanlarına e-posta gönderirken Exchange Online tarafından gerçekleştirilen MTA-STS doğrulamalarını kapsar.

## <a name="outbound-protection"></a>Giden Koruma

Exchange Online'den MTA-STS korumalı alıcılara gönderilen tüm iletiler, MTA-STS standardı tarafından belirlenen bu ek güvenlik denetimleriyle doğrulanır. Yöneticilerin uygulamayı uygulamak için yapması gereken bir şey yoktur. Giden uygulamamız, MTA-STS ilkesi aracılığıyla alıcı etki alanı sahiplerinin isteklerine saygı gösterir. MTA-STS, Exchange Online güvenlik altyapısının bir parçasını oluşturur ve bu nedenle her zaman açık olur (diğer temel SMTP özellikleri gibi).

## <a name="inbound-protection"></a>Gelen Koruma

Etki alanı sahipleri, MX kayıtları Exchange Online işaret ederse MTA-STS ile etki alanlarına gönderilen e-postaları korumak için eylem gerçekleştirebilir. MX kaydınız aracı bir üçüncü taraf hizmetine işaret ederse, MTA-STS gereksinimlerini karşılayıp karşılamadığını denetlemeniz ve yönergelerini izlemeniz gerekir.

Etki alanınız için MTA-STS ayarlandıktan sonra, MTA-STS'yi destekleyen gönderenlerden gönderilen tüm iletiler, güvenli bir bağlantı sağlamak için standart tarafından belirlenen doğrulamaları gerçekleştirir. MTA-STS'yi desteklemeyen bir gönderenden e-posta alıyorsanız, e-posta ek koruma olmadan teslim edilmeye devam eder. Benzer şekilde, henüz MTA-STS kullanmıyorsanız ancak gönderen destekliyorsa iletilerde herhangi bir kesinti olmaz. İletilerin teslim edilmemiş olduğu tek senaryo, her iki tarafın da MTA-STS kullandığı ve MTA-STS doğrulamasının başarısız olduğu senaryodur.

## <a name="how-to-adopt-mta-sts"></a>MTA-STS'yi benimseme

MTA-STS, bir etki alanının TLS için destek bildirmesine ve MX kaydını ve hedef sertifikasını bekleyebileceğiniz şekilde iletmesine olanak tanır. Ayrıca, bir sorun olduğunda bir gönderen sunucunun ne yapması gerektiğini gösterir. Bu işlem, BIR DNS TXT kaydı ile HTTPS web sayfası olarak yayımlanan bir ilke dosyasının birleşimiyle gerçekleştirilir. HTTPS korumalı ilke, saldırganların aşması gereken başka bir güvenlik koruması sunar.

Bir etki alanının MTA-STS TXT kaydı, gönderene MTA-STS desteği olduğunu belirtir ve bundan sonra etki alanının HTTPS tabanlı MTA-STS ilkesi gönderen tarafından alınır. Aşağıdaki TXT kaydı, MTA-STS desteğini bildiren bir örnektir:

`_mta-sts.contoso.com. 3600 IN TXT v=STSv1; id=20220101000000Z;`

Bir etki alanının MTA-STS ilkesinin, etki alanının web altyapısı tarafından barındırılan önceden tanımlanmış bir URL'de bulunması gerekir. URL söz dizimi şeklindedir `https://mta-sts.<domain name>/.well-known/mta-sts.txt`. Örneğin, Microsoft.com'un ilkesi şu konumda bulunur: <https://mta-sts.microsoft.com/.well-known/mta-sts.txt>.

```text
version: STSv1
mode: enforce
mx: *.mail.protection.outlook.com
max_age: 604800
```

MX kayıtları doğrudan Exchange Online işaret eden tüm müşteriler, microsoft.com ilkesinde yukarıda gösterilen değerlerle kendi ilkelerinde belirtebilir. İlkedeki benzersiz gerekli bilgiler, Exchange Online (`*`.mail.protection.outlook.com) işaret eden MX kaydıdır ve aynı sertifika tüm Exchange Online müşteriler tarafından paylaşılır. İlkenizi *zorlama* moduna geçirmeden önce geçerli olduğundan emin olmak için *test* modunda yayımlamak mümkündür. Orada yapılandırmanızı denetleyebilen üçüncü taraf doğrulama araçları vardır.

Bu ilkeler, Exchange Online müşteriler adına barındırabileceği bir şey değildir ve müşterilerin kullandıkları web barındırma hizmetinden yararlanması gerekir. İlkenin, alt etki alanı `mta-sts.<domain name>`için bir sertifika ile HTTPS tarafından korunması gerekir. Bir ilkeyi barındırmanın alternatifleri vardır ve bunu barındırmak için GitHub Pages kullanan [bu çözüm](https://github.com/jpawlowski/mta-sts.template) de buna dahildir.

DNS TXT etki alanı kaydı oluşturulduktan ve ilke dosyası gerekli HTTPS URL'sinde kullanılabilir olduğunda, etki alanı MTA-STS tarafından korunur. MTA-STS hakkındaki ayrıntıları [RFC 8461'de](https://datatracker.ietf.org/doc/html/rfc8461) bulabilirsiniz.
