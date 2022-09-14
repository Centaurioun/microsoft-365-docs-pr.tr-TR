---
title: Hassas bilgi türü REGEX doğrulayıcıları ve ek denetimler
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Duyarlı bilgi türlerinizde REGEX doğrulayıcılarını ve ek denetimleri kullanmayı öğrenin.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 615d4757be16b3171005105aea8148536e6f3015
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67679273"
---
# <a name="sensitive-information-type-regex-validators-and-additional-check"></a>Hassas bilgi türü REGEX doğrulayıcıları ve ek denetim

> [!IMPORTANT]
> Microsoft Müşteri Hizmetleri & Desteği, özel sınıflandırmalar veya normal ifade desenleri oluşturmaya yardımcı olamaz. Destek mühendisleri, test amacıyla örnek normal ifade desenleri sağlama veya beklendiği gibi tetiklenmeyen mevcut normal ifade deseninde sorun gidermeye yardımcı olma gibi özellikler için sınırlı destek sağlayabilir, ancak herhangi bir özel içerik eşleştirme geliştirmesinin gereksinimlerinizi veya yükümlülüklerinizi yerine getireceği konusunda güvence sağlayamaz.

## <a name="sensitive-information-type-regular-expression-validators"></a>Hassas Bilgi Türü normal ifade doğrulayıcıları

### <a name="checksum-validator"></a>Sağlama toplamı doğrulayıcısı

Normal ifadedeki bir basamak üzerinde sağlama toplamı çalıştırmanız gerekiyorsa sağlama *toplamı doğrulayıcısını* kullanabilirsiniz. Örneğin, son rakamın mod 9 hesaplaması kullanılarak doğrulanan bir sağlama toplamı basamak olduğu sekiz basamaklı bir lisans numarası için sit oluşturmanız gerektiğini varsayalım. Sağlama toplamı algoritmasını şu şekilde ayarladınız:

```console
Sum = digit 1 * Weight 1 + digit 2 * weight 2 + digit 3 * weight 3 + digit 4 * weight 4 + digit 5 * weight 5 + digit 6 * weight 6 + digit 7 * weight 7 + digit 8 * weight 8
Mod value = Sum % 9
If Mod value == digit 8
    Account number is valid
If Mod value != digit 8
    Account number is invalid
```

1. Birincil öğeyi şu normal ifadeyle tanımlayın:

   ```console
   \d{8}
   ```

2. Ardından sağlama toplamı doğrulayıcısını ekleyin.

3. Ağırlık değerlerini virgülle ayırarak, kontrol rakamının konumunu ve Mod değerini ekleyin. Modulo işlemi hakkında daha fazla bilgi için bkz [. Modulo işlemi](https://en.wikipedia.org/wiki/Modulo_operation).

   > [!NOTE]
   > Denetim basamakları sağlama toplamı hesaplamasının bir parçası değilse, denetim basamasının ağırlığı olarak 0 kullanın. Örneğin, yukarıdaki örnekte denetim basamasının hesaplanması için kullanılmaması durumunda 8 olan ağırlık 0'a eşit olacaktır.

   :::image type="content" alt-text="yapılandırılmış sağlama toplamı doğrulayıcının ekran görüntüsü." source="../media/checksum-validator.png" lightbox="../media/checksum-validator.png":::

### <a name="date-validator"></a>Tarih doğrulayıcı

Normal ifadeye eklenmiş bir tarih değeri, oluşturduğunuz yeni bir desenin parçasıysa, *tarih doğrulayıcısını* kullanarak ölçütlerinize uygun olup olmadığını test edebilirsiniz. Örneğin, dokuz basamaklı bir çalışan kimlik numarası için bir SIT oluşturmak istediğinizi varsayalım. İlk altı basamak, DDMMYY biçiminde işe alma tarihi ve son üçü rastgele oluşturulan sayılardır. İlk altı basamağın doğru biçimde olduğunu doğrulamak için.

1. Birincil öğeyi şu normal ifadeyle tanımlayın:

   ```console
   \d{9}
   ```

2. Ardından tarih doğrulayıcısını ekleyin.

3. Tarih biçimini ve başlangıç uzaklığını seçin. Tarih dizesi ilk altı basamak olduğundan, uzaklık olur `0`.

   :::image type="content" alt-text="yapılandırılan tarih doğrulayıcının ekran görüntüsü." source="../media/date-validator.png" lightbox="../media/date-validator.png":::

### <a name="functional-processors-as-validators"></a>Doğrulayıcı olarak işlevsel işlemciler

Doğrulayıcı olarak en yaygın kullanılan SID'lerden bazıları için işlev işlemcilerini kullanabilirsiniz. Bu, sit için gereken ek denetimleri geçirmelerini sağlarken kendi normal ifadenizi tanımlamanızı sağlar. Örneğin, Func_India_Aadhar tarafından tanımlanan özel normal ifadenin Hint Aadhar kartı için gereken doğrulama mantığını geçirmesini sağlar. Doğrulayıcı olarak kullanılabilecek DLP işlevleri hakkında daha fazla bilgi için bkz [. Hassas bilgi türü işlevleri](sit-functions.md). 

### <a name="luhn-check-validator"></a>Luhn check validator

Luhn algoritmasını geçirmesi gereken normal bir ifade içeren özel bir Hassas bilgi türünüz varsa [Luhn](https://en.wikipedia.org/wiki/Luhn_algorithm) denetim doğrulayıcısını kullanabilirsiniz.

## <a name="sensitive-information-type-additional-checks"></a>Hassas bilgi türü ek denetimler

Kullanılabilir ek denetimler için tanımlar ve bazı örnekler aşağıda verilmiştir.

**Belirli eşleşmeleri hariç tut**: Bu denetim, düzenlediğiniz desen için eşleşmeleri algılarken hariç tutulacak anahtar sözcükleri tanımlamanıza olanak tanır. Örneğin, geçerli bir sayı olarak eşleşmemeleri için '4111111111111111' gibi test kredi kartı numaralarını hariç tutabilirsiniz.

**Karakterlerle başlar veya başlamaz**: Bu denetim, eşleşen öğelerin başlaması veya başlamaması gereken karakterleri tanımlamanızı sağlar. Örneğin, desenin yalnızca 41, 42 veya 43 ile başlayan kredi kartı numaralarını algılamasını istiyorsanız, **Şununla başlar'ı seçin ve virgülle** ayırarak listeye 41, 42 ve 43 ekleyin. 

**Biter veya karakterle bitmez**: Bu denetim, eşleşen öğelerin bitmesi veya bitmemesi gereken karakterleri tanımlamanızı sağlar. Örneğin, Çalışan Kimliği numaranız 0 veya 1 ile bitemiyorsa, **Şununla bitmiyor'ı seçin ve virgülle** ayrılmış olarak listeye 0 ve 1 ekleyin.

**Yinelenen karakterleri hariç tut**: Bu denetim, tüm basamakların aynı olduğu eşleşmeleri yoksaymanıza olanak tanır. Örneğin, altı basamaklı çalışan kimliği numarasının tüm basamakları aynı olamazsa, çalışan kimliği için geçerli eşleşmeler listesinden 111111, 222222, 333333, 444444, 555555, 666666, 777777, 888888, 999999 ve 000000'i dışlamak için **Yinelenen karakterleri dışla'yı** seçebilirsiniz.

**Ön ekleri dahil etme veya hariç tutma**: Bu denetim, eşleşen varlıktan hemen önce bulunması veya bulunmaması gereken anahtar sözcükleri tanımlamanızı sağlar. Seçiminize bağlı olarak, varlıklar buraya eklediğiniz ön eklerin önündeyse eşleştirilir veya eşleşmez. Örneğin, **GUID**: ön ekini **Dışlarsanız**, **GUID'** nin önündeki herhangi bir varlık eşleşme olarak kabul edilmez.

**Sonekleri ekleme veya dışlama** Bu denetim, eşleşen varlığın hemen ardından bulunması veya bulunmaması gereken anahtar sözcükleri tanımlamanızı sağlar. Seçiminize bağlı olarak, varlıklar eşleştirilir veya buraya eklediğiniz sonekler tarafından izlenirse eşleşmez. Örneğin, **:GUID** sonekini **dışlarsanız**, **ardından :GUID** gelen metinler eşleşmez.
