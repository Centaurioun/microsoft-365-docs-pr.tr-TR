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
ms.openlocfilehash: b8833e7b737c5ab03fb57320bbdbad7513f33b47
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2022
ms.locfileid: "67797695"
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

MTA-STS, bir etki alanının TLS için destek bildirmesine ve MX kaydını ve hedef sertifikasını bekleyebileceğiniz şekilde iletmesine olanak tanır. Ayrıca, bir sorun olduğunda bir gönderen sunucunun ne yapması gerektiğini gösterir. Bu iletişim, BIR DNS TXT kaydı ile HTTPS web sayfası olarak yayımlanan bir ilke dosyasının birleşimiyle gerçekleştirilir. HTTPS korumalı ilke, saldırganların aşması gereken başka bir güvenlik koruması sunar.

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

Bu ilkeler, Exchange Online müşteriler adına barındırabilecek bir şey değildir, bu nedenle müşterilerin tercih ettikleri hizmetleri kullanarak etki alanı STS ilkesini yapılandırmaları gerekir. Azure hizmetleri, ilke barındırma için kolayca kullanılabilir ve bu makalenin devamında bir yapılandırma kılavuzu vardır. İlkenin, alt etki alanı `mta-sts.<domain name>`için bir sertifika ile HTTPS tarafından korunması gerekir.

DNS TXT kaydı oluşturulduktan ve ilke dosyası gerekli HTTPS URL'sinde kullanılabilir olduğunda, etki alanı MTA-STS tarafından korunur. MTA-STS hakkındaki ayrıntıları [RFC 8461'de](https://datatracker.ietf.org/doc/html/rfc8461) bulabilirsiniz.

### <a name="configuring-inbound-mta-sts-with-azure-services"></a>Azure Hizmetleri ile Gelen MTA-STS'yi yapılandırma

> [!NOTE]
> Bu yapılandırma akışları, Microsoft Exchange Online müşterilerin MTA-STS ilkelerini Azure kaynaklarını kullanarak barındırmasına yardımcı olmak için geliştirilmiştir. Bu yapılandırma akışı, MTA-STS'nin nasıl çalıştığını ve gereksinimlerini bilen bir Exchange Online müşterisi olduğunuzu varsayar. Bu konunun ötesindeki protokol hakkında daha fazla bilgi için bkz. [RFC8461](https://www.rfc-editor.org/rfc/rfc8461.html).

MTA-STS ilkesini barındırmak için kullanılabilecek iki Azure kaynağı vardır: [Azure Statik Web Uygulaması](https://azure.microsoft.com/services/app-service/static/) ve [Azure İşlevleri](/azure/azure-functions/functions-overview). Bu makalede ilkenin her iki kaynak kullanılarak nasıl dağıtılacağı açıklanmaktadır ancak önerilen yöntem, STS ilkesi gibi statik sayfaları barındırmak için tasarlanmış olan [Azure Static Web App'tir](https://azure.microsoft.com/services/app-service/static/) ve Azure, daha fazla yapılandırma gerektirmeden MTA-STS web sayfası için kullanıma hazır bir TLS sertifikası sağlayarak yapılandırmayı basitleştirir. [Azure Static Web App'i](https://azure.microsoft.com/services/app-service/static/) kullanamıyorsanız, [Azure İşlevleri](/azure/azure-functions/functions-overview) kullanarak ilkenizi sunucusuz kod olarak da barındırabilirsiniz. Azure İşlevi diğer senaryolar için tasarlanmış bir özellik olduğundan ve Azure Static Web Apps aksine otomatik olarak tls sertifikası vermediğinden bu yaklaşım tercih edilen yöntem değildir. Bu nedenle MTA-STS için [Azure İşlevleri](/azure/azure-functions/functions-overview) kullanmak için kendi "mta-sts.[ etki alanınız]" sertifikasını seçin ve işlevine bağlayın.

Hangi yaklaşımı benimsediğinize bakılmaksızın, ilkenizin düzgün yapılandırıldığını ve yanıt süresinin kabul edilebilir olduğunu doğrulamanızı öneririz; RFC kılavuzu başına zaman aşımı 60 saniyedir.

Bu yapılandırma akışları yalnızca MTA-STS ilkesini barındırmak için kullanılabilecek Ve Azure özelliklerinin ücretlendirmesi veya maliyetleri hakkında herhangi bir bilgi sağlamayan Azure özellikleri hakkında teknik bilgiler sağlamayı amaçlar. Azure özellik maliyetlerini öğrenmek istiyorsanız Azure [Fiyatlandırma Hesaplayıcısı'nı](https://azure.microsoft.com/pricing/calculator/) kullanın.

#### <a name="option-1-recommended-azure-static-web-app"></a>Seçenek 1 (ÖNERİLEN): Azure Statik Web Uygulaması

1. Bir Azure DevOps kuruluşu oluşturun veya zaten var olan bir kuruluşu kullanın. Bu örnekte, MTA-STS ilkesini barındırmak için "ContosoCorporation" adlı bir kuruluş kullanılacaktır.

   :::image type="content" source="../media/projects-tab.png" alt-text="Projeler sekmesini gösteren ekran görüntüsü." lightbox="../media/projects-tab.png":::

2. **Depolar > Dosyalar** bölümünde deponuzu tercih ettiğiniz herhangi bir IDE'ye kopyalayın. Bu örnekte depo Visual Studio'da kopyalanacaktır.

   :::image type="content" source="../media/clone-to-vs-code.png" alt-text="Visual Studio Code'a kopyalama örneğini gösteren ekran görüntüsü." lightbox="../media/clone-to-vs-code.png":::

3. Depo kopyalandıktan sonra aşağıdaki klasör yolunu oluşturun: `home\.well-known\`. Ardından aşağıdaki dosyaları oluşturun: 

    - Dosya 1: giriş\.well-known\mta-sts.txt

   > [!NOTE]
   > Bu yapılandırma yalnızca Exchange Online etki alanınız adına ileti almasına olanak tanır. Birden çok e-posta sağlayıcısı kullanıyorsanız, bu diğer sağlayıcıların etki alanları için de MX konaklarına başvurmanız gerekir. Joker karakterler veya '*' tüm MTA-STS senaryolarında MX öneki olarak kullanılmamalıdır; aşağıdaki ayarlar yalnızca Exchange Online özgüdür ve MTA-STS'yi yapılandırmak için genel kılavuz olarak KULLANıLMAMALIDIR. 

    1. mta-sts.txt dosyasına aşağıdaki metni girin:
        ```powershell
           version: STSv1
           mode: testing
           mx: *.mail.protection.outlook.com
           max_age: 604800
        ```
       > [!NOTE]
       > İlke modunun başlangıçta 'test' olarak ayarlanması önerilir. Ardından, yapılandırmanın sonunda ve ilkenin beklendiği gibi çalıştığını doğruladıktan sonra, mta-sts.txt dosyasını modu 'zorlama' olacak şekilde güncelleştirin.
 
       Dosya yalnızca aşağıdaki ekran görüntüsünde gösterildiği gibi içeriği içermelidir:

       :::image type="content" source="../media/contents-of-file1.png" alt-text="Dosya1'in içeriğini görüntüleyen ekran görüntüsü." lightbox="../media/contents-of-file1.png":::

    - Dosya 2: home\index.html
    
    1. bir index.html dosyası oluşturun ve içine aşağıdaki kodu girin:
    
       ```powershell
           <!DOCTYPE html>
           <html lang="en">

           <head>
           <meta charset="UTF-8">
           <title>MTA-STS</title>
           </head>

           <body>
           <h1>MTA-STS Static Website index</h1>
           </body>

           </html>
       ```
           
      Dosya yalnızca aşağıdaki ekran görüntüsünde gösterildiği gibi içeriği içermelidir:
   
      :::image type="content" source="../media/contents-of-file2.png" alt-text="Dosya2'nin içeriğini görüntüleyen ekran görüntüsü." lightbox="../media/contents-of-file2.png":::

      Klasör yolu ve dosyalar oluşturulduktan sonra, değişiklikleri işlemeyi ve bunları ana dalınıza göndermeyi unutmayın.

4. Aşağıdaki yapılandırmayla yeni bir Azure Statik Web Uygulaması oluşturun:

    - **Ad**: MTA-STS-StaticWebApp
    - **Plan türü**: Standart
    - **Dağıtım Ayrıntıları**: Azure DevOps
    - **Kuruluş**: ContosoCorporation
    - **Proje**: MTA-STS_Project
    - **Depo**: MTA-STS_Project
    - **Dal**: ana
    - **Derleme Ön Ayarları**: Angular
    - **Uygulama Konumu**: /home
   
    :::image type="content" source="../media/new-app-with-details.png" alt-text="Bilgileriyle birlikte yeni oluşturulan bir Azure Statik Web Uygulamasını gösteren ekran görüntüsü." lightbox="../media/new-app-with-details.png":::

5. Statik Web Uygulaması oluşturma işlemi tamamlandıktan ve kaynak sağlandıktan sonra **Dağıtım belirtecini yönetme > Genel Bakış'a** gidin; ardından belirteci bir sonraki adımda kullanılacağı şekilde kopyalayın.

6. **Git > MTA-STS_Project > Azure Repos İşlem Hattı Oluşturma > İşlem Hatları'na** gidin ve aşağıdaki alt görevleri gerçekleştirin:
    1. **Değişkenler > Yeni Değişken'e** gidin ve aşağıdakileri yazın:
        1. **Ad**: belirteç
        1. **Değer**: (daha önce kopyaladığınız belirteci yapıştırın)
    1. Değişken kaydedildikten sonra **İşlem hattı YAML'nizi gözden geçirin'e** dönün ve aşağıdaki yml'yi yapıştırın, kaydedin ve çalıştırın.
           
       ```powershell
           trigger:
           - main

           pool:
           vmImage: ubuntu-latest

           steps:
           - checkout: self
           submodules: true
           - task: AzureStaticWebApp@0
           inputs:
            app_location: '/home'
            azure_static_web_apps_api_token: $(token)
       ```

       Azure DevOps'ta dağıtım sırasında **Barındırılan paralellik satın alınmadı veya verildi** hatasıyla karşılaşırsanız, bu [form](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR63mUWPlq7NEsFZhkyH8jChUMlM3QzdDMFZOMkVBWU5BWFM3SDI2QlRBSC4u) aracılığıyla istekte bulun veya **Microsoft Barındırılan > Değişiklik > Ücretli Paralel işler > "Ücretli paralel işlere" izin verilir gibi Kuruluş Ayarları > Paralel işler** aracılığıyla bir yapılandırma uygulayın.

7. İş başarıyla tamamlandıktan sonra **Azure Static Web App > Environment > Browser'a giderek Azure portal** aracılığıyla dağıtımı doğrulayabilirsiniz. index.html dosyasının içeriğini görmeniz gerekir.

8. **Azure Static Web App > Özel etki alanları > Ekle'de kibir etki alanınızı ekleyin**. Bölgenin size ait olduğunu doğrulamak için DNS sağlayıcınız (örneğin GoDaddy) aracılığıyla bir **CNAME** kaydı oluşturmanız gerekir. Doğrulama tamamlandıktan sonra Azure bir sertifika verir ve bunu otomatik olarak Statik Web Uygulamanıza bağlar.

9. MTA-STS ilkenizin yayımlandığını doğrulayın: https://mta-sts.[ etki alanınız]/.well-known/mta-sts.txt.

10. DNS sağlayıcınız aracılığıyla MTA-STS TXT DNS kaydını oluşturun. Biçim aşağıdaki gibidir:
     
    ```powershell
        Hostname: _mta-sts.<domain name>
        TTL: 3600 (recommended)
        Type: TXT
        Text: v=STSv1; id=<ID unique for your domain’s STS policy>Z;
    ```

    > [!NOTE]
    > Örnek bir MTA-STS TXT kaydı, [MTA-STS'yi Benimseme](#how-to-adopt-mta-sts) bölümünde bulunabilir.

11. TXT kaydı DNS'de kullanılabilir olduğunda, MTA-STS yapılandırmanızı doğrulayın. Yapılandırma başarıyla doğrulandıktan sonra, mta-sts.txt dosyasını ilke modunun 'zorlama' olacak şekilde güncelleştirin; ardından TXT kaydında ilke kimliğinizi güncelleştirin.

#### <a name="option-2-azure-function"></a>Seçenek 2: Azure İşlevi

1. Aşağıdaki yapılandırmayla yeni bir Azure İşlev Uygulaması oluşturun:

    - **İşlev Uygulaması adı**: [Tercihiniz olarak]
    - **Yayımla**: Kod
    - **Çalışma zamanı yığını**: .NET
    - **Sürüm**: 6
    - **İşletim Sistemi**: Windows
    - **Plan Türü**: [Tercihiniz olarak]

    :::image type="content" source="../media/new-azure-function-app.png" alt-text="Yeni bir Azure İşlevi uygulamasının yapılandırmalarını gösteren ekran görüntüsü." lightbox="../media/new-azure-function-app.png":::

2. Özel etki alanınızı İşlev Uygulamasına ekleyin. Etki alanının size ait olduğunu doğrulamak için bir **CNAME** kaydı oluşturmanız gerekir.

   :::image type="content" source="../media/custom-domain-to-add.png" alt-text="İşlev Uygulamasına eklenecek özel etki alanını gösteren ekran görüntüsü." lightbox="../media/custom-domain-to-add.png":::

3. Mta-sts'nizi bağlayın. [etki alanınız] ile İşlev Uygulaması'na gidin.

   :::image type="content" source="../media/binding-to-function-app.png" alt-text="Etki alanını İşlev Uygulamasına bağlama işlemini gösteren ekran görüntüsü." lightbox="../media/binding-to-function-app.png":::

4. **Uygulama Dosyası'nda** aşağıdaki uzantıyı İşlev Uygulamanızın host.json dosyasına ekleyerek RoutePrefix yolunu ortadan kaldırın. Bu ekleme, /api'yi işlev URL'sinden kaldırmak için gereklidir.
   
    ```powershell
        "extensions": {
    "http": {
      "routePrefix&quot;: &quot;"
      }
    }
    ```

   :::image type="content" source="../media/extension-added-to-app-file.png" alt-text="Uygulama dosyasına eklenen uzantıyı gösteren ekran görüntüsü." lightbox="../media/extension-added-to-app-file.png":::

5. İşlev Uygulamanızda **İşlevler > Oluştur'a** gidin ve aşağıdaki parametreleri yapılandırın: 

   > [!NOTE]
   > Bu örnekte portal aracılığıyla işlev geliştirme açıklanmaktadır ancak VS Code veya tercih ettiğiniz başka bir aracı kullanabilirsiniz.

    - **Geliştirme ortamı**: [Tercihinize göre, bu örnekte "Portalda Geliştirme" kullanılır]
    - **Şablon seçin**: HTTP tetikleyicisi
    - **Yeni İşlev**: [Tercihiniz olarak]
    - **Yetkilendirme düzeyi**: Anonim

    :::image type="content" source="../media/create-function-screen.png" alt-text="İşlev oluştur sayfasını gösteren ekran görüntüsü." lightbox="../media/create-function-screen.png":::

6. İşlev oluşturulduktan sonra **Kod + Test'i** açın ve C# dilinde MTA-STS ilkeniz olacak basit bir zaman uyumsuz HTTP yanıtı geliştirin. Aşağıdaki örnek, Exchange Online e-posta almasının beklendiğini gösterir:

   > [!NOTE]
   > İlke modunun başlangıçta 'test' olarak ayarlanması önerilir. Ardından, yapılandırmanın sonunda ve ilkenin beklendiği gibi çalıştığını doğruladıktan sonra, mta-sts.txt dosyasını modu 'zorlama' olacak şekilde güncelleştirin.

   :::image type="content" source="../media/mta-sts-policy.png" alt-text="Geliştirilen mta-sts ilkesini gösteren ekran görüntüsü." lightbox="../media/mta-sts-policy.png":::

7. **HTTP (req) > Tümleştirme'de** tetikleyiciyi aşağıdaki değerlerle düzenleyin:

    - **Yol Şablonu**: .well-known/mta-sts.txt
    - **Seçilen HTTP yöntemleri**: GET

    :::image type="content" source="../media/edit-trigger-screen.png" alt-text="Tetikleyiciyi düzenle sayfasını gösteren ekran görüntüsü." lightbox="../media/edit-trigger-screen.png":::

8. MTA-STS ilkenizin yayımlandığını doğrulayın: https://mta-sts.[ etki alanınız]/.well-known/mta-sts.txt.

9. DNS sağlayıcınız aracılığıyla MTA-STS TXT DNS kaydını aşağıdaki biçimde oluşturun:

     ```powershell
        Hostname: _mta-sts.<domain name>
        TTL: 3600 (recommended)
        Type: TXT
        Text: v=STSv1; id=<ID unique for your domain’s STS policy>Z;
     ```

   > [!NOTE]
   > Örnek bir MTA-STS TXT kaydı, [MTA-STS'yi Benimseme](#how-to-adopt-mta-sts) bölümünde bulunabilir.

10. TXT kaydı DNS'de kullanılabilir olduğunda, MTA-STS yapılandırmanızı doğrulayın. Yapılandırma başarıyla doğrulandıktan sonra, mta-sts.txt dosyasını ilke modu 'zorlama' olacak şekilde güncelleştirin; ardından TXT kaydında ilke kimliğinizi güncelleştirin.