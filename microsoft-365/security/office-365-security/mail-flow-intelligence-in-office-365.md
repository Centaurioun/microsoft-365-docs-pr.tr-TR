---
title: Posta akışı zekası
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.custom: ''
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Yöneticiler, bağlayıcıları (posta akışı zekası olarak da bilinir) kullanarak ileti teslimiyle ilişkili hata kodları hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.collection: M365-security-compliance
ms.openlocfilehash: b83b2011af516359d219061ee88f06c7ac170369
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67599010"
---
# <a name="mail-flow-intelligence-in-eop"></a>EOP'de posta akışı zekası

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online posta kutusu olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında, e-posta iletilerini EOP'den şirket içi e-posta ortamınıza yönlendirmek için genellikle bir bağlayıcı kullanırsınız. Microsoft 365'ten gelen iletileri bir iş ortağı kuruluşuna yönlendirmek için bağlayıcı da kullanabilirsiniz. Microsoft 365 bu iletileri bağlayıcı aracılığıyla teslim etmediğinde Microsoft 365'te kuyruğa alınır. Microsoft 365, 24 saat boyunca her ileti için teslimi yeniden denemeye devam edecektir. 24 saat sonra, kuyruğa alınan iletinin süresi dolar ve ileti teslim edilemeyen bir raporda (NDR veya geri dönen ileti olarak da bilinir) özgün gönderene döndürülür.

Microsoft 365, bağlayıcı kullanılarak ileti teslim edilemiyorsa bir hata oluşturur. En yaygın hatalar ve çözümleri bu makalede açıklanmıştır. Bağlayıcılar aracılığıyla gönderilen teslim edilemeyen iletiler için toplu olarak kuyruğa alma ve bildirim hataları _posta akışı zekası_ olarak bilinir.

## <a name="error-code-450-44312-dns-query-failed"></a>Hata kodu: 450 4.4.312 DNS sorgusu başarısız oldu

Bu hata genellikle Microsoft 365'in bağlayıcıda belirtilen akıllı ana bilgisayara bağlanmayı denediğini ancak akıllı ana bilgisayarın IP adreslerini bulmak için DNS sorgusunun başarısız olduğu anlamına gelir. Bu hatanın olası nedenleri şunlardır:

- Etki alanınızın DNS barındırma hizmetiyle (etki alanınız için yetkili ad sunucularını barındıran taraf) bir sorun var.

- Etki alanınızın süresi kısa süre önce doldu, bu nedenle MX kaydı alınamıyor.

- Etki alanınızın MX kaydı kısa süre önce değişti ve DNS sunucuları etki alanınız için daha önce önbelleğe alınmış DNS bilgilerine sahip.

### <a name="how-do-i-fix-error-code-450-44312"></a>Hata kodu 450 4.4.312 Nasıl yaparım? düzeltildi?

- Etki alanınızla ilgili sorunu belirlemek ve düzeltmek için DNS barındırma hizmetinizle çalışın.

- Hata iş ortağı kuruluşunuzdan geliyorsa (örneğin, üçüncü taraf bir bulut hizmeti sağlayıcısı), sorunu çözmek için iş ortağınıza başvurun.

## <a name="error-code-450-44315-connection-timed-out"></a>Hata kodu: 450 4.4.315 Bağlantı zaman aşımına uğradı

Bu durum genellikle Microsoft 365'in hedef e-posta sunucusuna bağlanamazsınız anlamına gelir. Hata ayrıntıları sorunu açıklar. Örneğin:

- Şirket içi e-posta sunucunuz çalışmıyor.

- Bağlayıcının akıllı ana bilgisayar ayarlarında bir hata olduğundan Microsoft 365 yanlış IP adresine bağlanmaya çalışıyor.

### <a name="how-do-i-fix-error-code-450-44315"></a>Hata kodu 450 4.4.315 Nasıl yaparım? düzeltildi?

- Hangi senaryonun sizin için geçerli olduğunu öğrenin ve gerekli düzeltmeleri yapın. Örneğin, posta akışı düzgün çalışıyorsa ve bağlayıcı ayarlarını değiştirmediyseniz, sunucunun devre dışı olup olmadığını veya ağ altyapınızda herhangi bir değişiklik olup olmadığını görmek için şirket içi e-posta ortamınızı denetlemeniz gerekir (örneğin, İnternet servis sağlayıcılarını değiştirdiyseniz, dolayısıyla artık farklı IP adresleriniz vardır).

- Hata iş ortağı kuruluşunuzdan geliyorsa (örneğin, üçüncü taraf bir bulut hizmeti sağlayıcısı), sorunu çözmek için iş ortağınıza başvurun.

## <a name="error-code-450-44316-connection-refused"></a>Hata kodu: 450 4.4.316 Bağlantı reddedildi

Bu hata genellikle Microsoft 365'in hedef e-posta sunucusuna bağlanmaya çalışırken bir bağlantı hatasıyla karşılaştığı anlamına gelir. Bu hatanın olası bir nedeni, güvenlik duvarınızın Microsoft 365 IP adreslerinden gelen bağlantıları engellemesidir. Ya da şirket içi e-posta sisteminizi Tamamen Microsoft 365'e geçirdiyseniz ve şirket içi e-posta ortamınızı kapattıysanız bu hata tasarım gereği olabilir.

### <a name="how-do-i-fix-error-code-450-44316"></a>Hata kodu 450 4.4.316 Nasıl yaparım? düzeltildi?

- Şirket içi ortamınızda posta kutularınız varsa, güvenlik duvarı ayarlarınızı, 25 numaralı TCP bağlantı noktasındaki Microsoft 365 IP adreslerinden şirket içi e-posta sunucularınıza bağlantılara izin verecek şekilde değiştirmeniz gerekir. Microsoft 365 IP adreslerinin listesi için bkz. [Microsoft 365 URL'leri ve IP adresi aralıkları](../../enterprise/urls-and-ip-address-ranges.md).

- Şirket içi ortamınıza başka ileti teslim edilmemesi gerekiyorsa, Microsoft 365'in geçersiz alıcıları olan iletileri hemen reddedebilmesi için uyarıda **Şimdi düzelt'e** tıklayın. Bu, kuruluşunuzun geçersiz alıcılar için kotasını aşma riskini azaltır ve bu da normal ileti teslimini etkileyebilir. Ya da sorunu el ile düzeltmek için aşağıdaki yönergeleri kullanabilirsiniz:

  - Exchange yönetim merkezinde, Microsoft 365'ten şirket içi e-posta ortamınıza e-posta teslim eden bağlayıcıyı devre dışı bırakın veya silin:

    1. konumundaki EAC'de <https://admin.exchange.microsoft.com>**Posta akışı** \> **Bağlayıcıları'na** gidin. Doğrudan **Bağlayıcılar** sayfasına gitmek için kullanın <https://admin.exchange.microsoft.com/#/connectors>.

    2. **Kimden** değeri **Office 365** ve **To** değeri **Kuruluşunuzun e-posta sunucusuna** sahip bağlayıcıyı seçin ve aşağıdaki adımlardan birini yapın:
       - **Kaldır** simgesine tıklayarak ![bağlayıcıyı silin.](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)
       - **Düzenle** ![simgesine tıklayarak bağlayıcıyı devre dışı bırakın.](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ve **Aç'ı** temizleyin.

  - Microsoft 365'te şirket içi e-posta ortamınızla ilişkili kabul edilen etki alanını **İç Geçişten** **Yetkili** olarak değiştirin. Yönergeler için bkz. [Exchange Online'da kabul edilen etki alanlarını yönetme](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

  **Not**: Bu değişikliklerin geçerlilik kazanması genellikle 30 dakika ile bir saat arasında sürer. Bir saat sonra artık hata almadığınızdan emin olun.

- Hata iş ortağı kuruluşunuzdan geliyorsa (örneğin, üçüncü taraf bir bulut hizmeti sağlayıcısı), sorunu çözmek için iş ortağınıza başvurmanız gerekir.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Hata kodu: 450 4.4.317 Uzak sunucuya bağlanılamıyor

Bu hata genellikle hedef e-posta sunucusuna bağlı Microsoft 365 anlamına gelir, ancak sunucu hemen bir hatayla yanıt verir veya bağlantı gereksinimlerini karşılamaz. Hata ayrıntıları sorunu açıklar. Örneğin:

- Hedef e-posta sunucusu, sunucunun Microsoft 365 ile iletişimi sürdüremediğini belirten "Hizmet kullanılamıyor" hatasıyla yanıt verdi.
- Bağlayıcı TLS gerektirecek şekilde yapılandırılmıştır, ancak hedef e-posta sunucusu TLS'yi desteklemez.

### <a name="how-do-i-fix-error-code-450-44317"></a>Hata kodu 450 4.4.317 Nasıl yaparım? düzeltildi?

- Şirket içi e-posta sunucularınızdaki TLS ayarlarını ve sertifikalarını ve bağlayıcıdaki TLS ayarlarını doğrulayın.
- Hata iş ortağı kuruluşunuzdan geliyorsa (örneğin, üçüncü taraf bir bulut hizmeti sağlayıcısı), sorunu çözmek için iş ortağınıza başvurmanız gerekir.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Hata kodu: 450 4.4.318 Bağlantı aniden kapatıldı

Bu hata genellikle Microsoft 365'in şirket içi e-posta ortamınızla iletişim kurmakta zorlandığı ve dolayısıyla bağlantının kesildiği anlamına gelir. Bu hatanın olası nedenleri şunlardır:

- Güvenlik duvarınız SMTP paket inceleme kurallarını kullanıyor ve bu kurallar düzgün çalışmıyor.
- Şirket içi e-posta sunucunuz düzgün çalışmıyor (örneğin, hizmet kilitleniyor, kilitleniyor veya düşük sistem kaynakları), bu da sunucunun zaman aşımına uğrmasına ve Microsoft 365 bağlantısını kapatmasına neden oluyor.
- Şirket içi ortamınız ile Microsoft 365 arasında ağ sorunları vardır.

### <a name="how-do-i-fix-error-code-450-44318"></a>Hata kodu 450 4.4.318 Nasıl yaparım? düzeltildi?

- Hangi senaryonun sizin için geçerli olduğunu öğrenin ve gerekli düzeltmeleri yapın.
- Soruna şirket içi ortamınız ile Microsoft 365 arasındaki ağ sorunları neden oluyorsa, sorunu gidermek için ağ ekibinize başvurun.
- Hata iş ortağı kuruluşunuzdan geliyorsa (örneğin, üçüncü taraf bir bulut hizmeti sağlayıcısı), sorunu çözmek için iş ortağınıza başvurmanız gerekir.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Hata kodu: 450 4.7.320 Sertifika doğrulaması başarısız oldu

Genellikle bu hata, Microsoft 365'in hedef e-posta sunucusunun sertifikasını doğrulamaya çalışırken bir hatayla karşılaştığı anlamına gelir. Hata ayrıntıları hatayı açıklar. Örneğin:

- Sertifikanın süresi doldu
- Sertifika konusu uyuşmazlığı
- Sertifika artık geçerli değil

### <a name="how-do-i-fix-error-code-450-47320"></a>Hata kodu 450 4.7.320 Nasıl yaparım? düzeltildi?

- Microsoft 365'te kuyruğa alınmış iletilerin teslim edilebilmesi için sertifikayı veya bağlayıcıdaki ayarları düzeltin.
- Hata iş ortağı kuruluşunuzdan geliyorsa (örneğin, üçüncü taraf bir bulut hizmeti sağlayıcısı), sorunu çözmek için iş ortağınıza başvurmanız gerekir.

## <a name="other-error-codes"></a>Diğer hata kodları

Microsoft 365, şirket içi veya iş ortağı e-posta sunucunuza ileti göndermekte zorlanıyor. Ortamınızdaki sorunu incelemek için hatadaki **Hedef sunucu** bilgilerini kullanın veya yapılandırma hatası varsa bağlayıcıyı değiştirin.

Hata iş ortağı kuruluşunuzdan geliyorsa (örneğin, üçüncü taraf bir bulut hizmeti sağlayıcısı), sorunu çözmek için iş ortağınıza başvurmanız gerekir.
