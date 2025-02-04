---
title: Bağlamsal dosya ve klasör dışlamaları
description: Windows'da Microsoft Defender Virüsten Koruma için bağlamsal dosya ve klasör dışlamaları özelliğini açıklar. Bu özellik, kısıtlama uygulayarak Virüsten Koruma Microsoft Defender hangi bağlam altında bir dosya veya klasörü taramaması gerektiğini tanımlarken daha belirgin olmanıza olanak tanır
keywords: Microsoft Defender Virüsten Koruma, işlem, dışlama, dosyalar, taramalar
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: jweston-1
ms.author: v-jweston
ms.localizationpriority: medium
ms.date: 08/25/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 95db55c5aaa785dd5898956c17c232e79ea622c4
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68641545"
---
# <a name="contextual-file-and-folder-exclusions"></a>Bağlamsal dosya ve klasör dışlamaları

Bu makalede/bölümde Windows'ta Microsoft Defender Virüsten Koruma için bağlamsal dosya ve klasör dışlamaları özelliği açıklanmaktadır. Bu özellik, kısıtlama uygulayarak Virüsten Koruma Microsoft Defender hangi bağlam altında bir dosyayı veya klasörü taramaması gerektiğini tanımlarken daha belirgin olmanıza olanak tanır.

## <a name="overview"></a>Genel bakış

Dışlamalar öncelikli olarak performans üzerindeki etkileri azaltmaya yöneliktir. Daha düşük koruma değeri cezasıyla gelirler. Bu kısıtlamalar, dışlamanın uygulanacağı koşulları belirterek bu koruma azaltmasını sınırlamanıza olanak sağlar. Bağlamsal dışlamalar, hatalı pozitif sonuçları güvenilir bir şekilde ele almak için uygun değildir. Hatalı bir pozitif sonuçla karşılaşırsanız, dosyaları [analiz için Microsoft 365 Defender](https://security.microsoft.com/) portalı (abonelik gereklidir) veya [Microsoft Güvenlik Zekası](https://www.microsoft.com/wdsi/filesubmission) web sitesi aracılığıyla gönderebilirsiniz. Geçici bir gizleme yöntemi için [Uç Nokta için Microsoft Defender'de](/microsoft-365/security/defender-endpoint/indicator-file) özel _bir izin verme_ göstergesi oluşturmayı göz önünde bulundurun.

Bir dışlamanın uygulanabilirliğini sınırlamak için uygulayabileceğiniz dört kısıtlama vardır:

- **Dosya/klasör yolu türü kısıtlaması**. Dışlamaları yalnızca hedef bir dosya veya bir klasörse geçerli olacak şekilde kısıtlayabilir ve amacı belirli hale getirebilirsiniz. Hedef bir dosyaysa ancak dışlama bir klasör olarak belirtilmişse, geçerli olmaz. Buna karşılık, hedef klasörse ancak dışlama bir dosya olarak belirtilmişse, dışlama uygulanır.
- **Tarama türü kısıtlaması**. Bir dışlamanın uygulanması için gerekli tarama türünü tanımlamanızı sağlar. Örneğin, belirli bir klasörü yalnızca Tam taramalar'ın dışında tutmak istersiniz, ancak "kaynak" taramasından (hedefli tarama) hariç tutmak istemezsiniz.
- **Tarama tetikleyici türü kısıtlaması**. Dışlamanın yalnızca tarama belirli bir olay tarafından başlatıldığında uygulanacağını belirtmek için bu kısıtlamayı kullanabilirsiniz:
  - isteğe bağlı
  - erişimde
  - veya davranışsal izlemeden kaynaklanır
- **İşlem kısıtlaması**. Dışlamanın yalnızca belirli bir işlem tarafından bir dosya veya klasöre erişildiğinde geçerli olması gerektiğini tanımlamanızı sağlar.

## <a name="configuring-restrictions"></a>Kısıtlamaları yapılandırma

Kısıtlamalar genellikle dosya veya klasör dışlama yoluna kısıtlama türü eklenerek uygulanır.  

| Kısıtlama | Typename | Değer |
|:---|:---|:---|
| Dosya/klasör  | PathType  | Dosya <br> Klasör |
| Tarama türü | ScanType | Hızlı <br> Tam |
| Tarama tetikleyicisi | ScanTrigger | Ondemand <br> OnAccess <br> BM |
| Işlem | Işlem | "<image_path>" |

### <a name="requirements"></a>Gereksinimler

Bu özellik Microsoft Defender Virüsten Koruma gerektirir:

- Platform: **4.18.2205.7** veya üzeri
- Motor: **1.1.19300.2** veya üzeri

### <a name="syntax"></a>Sözdizimi

Başlangıç noktası olarak, daha belirgin hale getirmek istediğiniz dışlamalar zaten mevcut olabilir. Dışlama dizesini oluşturmak için, önce dışlanacak dosya veya klasörün yolunu tanımlayın, ardından aşağıdaki örnekte gösterildiği gibi tür adını ve ilişkili değeri ekleyin.

`<PATH>\:{TypeName:value,TypeName:value}`

_Tüm_ **türlerin** ve değerlerin büyük/küçük **harfe** duyarlı olduğunu unutmayın.

> [!NOTE]  
> Kısıtlamanın eşleşmesi için içindeki `{}` koşullar DOĞRU OLMALIDIR. Örneğin, iki tarama tetikleyicisi belirtirseniz bu doğru olamaz ve dışlama uygulanmaz. Aynı türde iki kısıtlama belirtmek için iki ayrı dışlama oluşturun.


### <a name="examples"></a>Örnekler

Aşağıdaki dize yalnızca bir dosyaysa ve yalnızca erişim içi taramalarda "c:\documents\design.doc" hariç tutar:

`c:\documents\design.doc\:{PathType:file,ScanTrigger:OnAccess}`

Aşağıdaki dize, yalnızca "winword.exe" görüntü adına sahip bir işlem tarafından erişildiği için taranmışsa (erişimde) "c:\documents\design.doc" öğesini dışlar:

`c:\documents\design.doc\:{Process:"winword.exe"}`

İşlem görüntüsü yolu, aşağıdaki örnekte olduğu gibi joker karakterler içerebilir:

`c:\documents\design.doc\:{Process:"C:\Program Files*\Microsoft Office\root\Office??\winword.exe"}`

### <a name="filefolder-restriction"></a>Dosya/klasör kısıtlaması

Dışlamaları yalnızca hedef bir dosya veya klasörse geçerli olacak şekilde kısıtlayabilir ve amacı belirli hale getirebilirsiniz. Hedef bir dosyaysa ancak dışlama bir klasör olarak belirtilmişse, dışlama uygulanmaz. Buna karşılık, hedef klasörse ancak dışlama bir dosya olarak belirtilmişse, dışlama uygulanır.

#### <a name="filefolder-exclusions-default-behavior"></a>Dosya/klasör dışlamaları varsayılan davranışı

Başka bir seçenek belirtmezseniz, dosya/klasör tüm tarama türlerinin dışında tutulur _ve_ hedef bir dosya veya klasör olmasına bakılmaksızın dışlama uygulanır. Dışlamaları yalnızca belirli bir tarama türüne uygulanacak şekilde özelleştirme hakkında daha fazla bilgi için bkz [. Tarama türü kısıtlaması](#scan-type-restriction).

#### <a name="folders"></a>Klasörler

Dışlamanın yalnızca hedef bir dosya değil bir klasörse geçerli olduğundan emin olmak için **PathType:folder** kısıtlamasını kullanabilirsiniz. Örneğin:

`C:\documents\:{PathType:folder}`

#### <a name="files"></a>Dosyalar

Dışlamanın yalnızca hedef bir dosyaysa geçerli olduğundan emin olmak için PathType: dosya kısıtlamasını kullanabilirsiniz.

Örneğin:

`C:\documents\database.mdb\:{PathType:file}`

### <a name="scan-type-restriction"></a>Tarama türü kısıtlaması

Varsayılan olarak, dışlamalar tüm tarama türleri için geçerlidir:  

- **kaynak**: Tek bir dosya veya klasör hedefli bir şekilde taranır (örneğin, sağ tıklama, Tarama)
- **hızlı**: kötü amaçlı yazılım, bellek ve belirli kayıt defteri anahtarları tarafından kullanılan yaygın başlangıç konumları
- **full**: Hızlı tarama konumlarını ve tam dosya sistemini (tüm dosya ve klasörler) içerir

Performans sorunlarını azaltmak için, belirli bir tarama türü tarafından taranan bir klasörü veya dosya kümesini dışlayabilirsiniz. Bir dışlamanın uygulanması için gerekli tarama türünü de tanımlayabilirsiniz.  

Bir klasörü yalnızca tam tarama sırasında taranmasının dışında tutmak için, aşağıdaki örnekte olduğu gibi dosya veya klasör dışlaması ile birlikte bir kısıtlama türü belirtin:

`C:\documents\:{ScanType:full}`

Bir klasörün yalnızca hızlı tarama sırasında taranmasını dışlamak için, dosya veya klasör dışlaması ile birlikte bir kısıtlama türü belirtin:

`C:\program.exe\:{ScanType:quick}`

Bu dışlamanın bir klasör için değil yalnızca belirli bir dosya için geçerli olduğundan emin olmak istiyorsanız (c:\foo.exe bir klasör olabilir), PathType kısıtlamasını da uygulayın:

`C:\program.exe\:{ScanType:quick,PathType:file}`

### <a name="scan-trigger-restriction"></a>Tarama tetikleyicisi kısıtlaması

Varsayılan olarak, temel dışlamalar tüm tarama tetikleyicileri için geçerlidir. ScanTrigger kısıtlaması, dışlamanın yalnızca tarama belirli bir olay tarafından başlatıldığında uygulanacağını belirtmenize olanak tanır; isteğe bağlı (hızlı, tam ve hedefli taramalar dahil), erişimde veya davranışsal izlemeden (bellek taramaları dahil) kaynaklanır.

- **OnDemand**: Bir komut veya yönetici eylemi tarafından bir tarama tetiklendi. Zamanlanmış hızlı ve tam taramaların da bu kategoriye girildiğini unutmayın.
- **OnAccess**: Bir dosya veya klasör açılır/yazılır/okunur/değiştirilir (genellikle gerçek zamanlı koruma olarak kabul edilir)
- **BM**: Davranış tetikleyicisi, davranışsal izlemenin belirli bir dosyayı taramasına neden olur

Bir dosya veya klasörü ve içeriğini yalnızca dosyaya erişildikten sonra taranırken taranmasını dışlamak için, aşağıdaki örnek gibi bir tarama tetikleyicisi kısıtlaması tanımlayın:

`c:\documents\:{ScanTrigger:OnAccess}`

### <a name="process-restriction"></a>İşlem kısıtlaması

Bu kısıtlama, dışlamanın yalnızca belirli bir işlem tarafından bir dosya veya klasöre erişilirken geçerli olması gerektiğini tanımlamanızı sağlar. Yaygın bir senaryo, bu önlemenin Defender Virüsten Koruma'nın bu işlemdeki diğer işlemleri yoksaymasına neden olacağından, işlemi dışlamaktan kaçınmak istemenizdir.

> [!NOTE]  
>
> Makinede büyük miktarda işlem dışlama kısıtlaması kullanılması performansı olumsuz etkileyebilir.  
> Ayrıca, dışlama işlemini belirli bir işlem veya işlemle kısıtladığınızdan, diğer etkin işlemler (dizin oluşturma, yedekleme, güncelleştirmeler gibi) dosya taramalarını tetikleyebilir.

Bir dosya veya klasörü yalnızca belirli bir işlem tarafından erişildiğinde dışlamak için normal bir dosya veya klasör dışlaması oluşturun ve dışlama işlemini şu şekilde kısıtlayın:  

`c:\documents\design.doc\:{Process:"winword.exe", Process:"msaccess.exe"}`

### <a name="how-to-configure"></a>Yapılandırma

İstediğiniz bağlamsal dışlamaları oluşturduktan sonra, oluşturduğunuz dizeyi kullanarak dosya ve klasör dışlamalarını yapılandırmak için mevcut yönetim aracınızı kullanabilirsiniz.

Bkz. [Microsoft Defender Virüsten Koruma taramaları için dışlamaları yapılandırma ve doğrulama](configure-exclusions-microsoft-defender-antivirus.md)
