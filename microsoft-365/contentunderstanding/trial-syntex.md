---
title: Microsoft Syntex denemesi çalıştırma
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom:
- Adopt
- admindeeplinkMAC
search.appverid: ''
ms.localizationpriority: medium
description: Kuruluşunuzda Microsoft Syntex için bir deneme pilot programı planlamayı, kaydolmayı ve çalıştırmayı öğrenin.
ms.openlocfilehash: 27770aa818c25b5c18c07a3f8f67a2185964ad37
ms.sourcegitcommit: 04e517c7e00323b5c33d8ea937115725cf2cfd4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2022
ms.locfileid: "68564070"
---
# <a name="run-a-trial-of-microsoft-syntex"></a>Microsoft Syntex denemesi çalıştırma

Bu makalede, kuruluşunuzda Microsoft Syntex dağıtmak için bir deneme pilot programı ayarlama ve çalıştırma işlemleri açıklanmaktadır. Ayrıca deneme için en iyi yöntemleri de önerir.

## <a name="sign-up-for-a-trial"></a>Deneme sürümüne kaydolma

Syntex deneme sürümü 30 gün boyunca 300 kullanıcıya erişim sağlar.

> [!NOTE]
> 1 milyon AI Builder kredisinin otomatik olarak eklenmesini sağlamak için deneme sürümüne en fazla 300 kullanıcı dahil edilir. Deneme sürümünün başarılı olması için 300 kullanıcı eklemeniz gerekmez.

Deneme sürümünü aşağıdaki kaynaklardan birinden alabilirsiniz:

- [Syntex ürün sayfası](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- [Microsoft 365 yönetim merkezi](https://admin.microsoft.com)
    1. [Microsoft 365 yönetici merkezi](https://admin.microsoft.com)'nde oturum açın.
    2. **Faturalama** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**Satın Alma Hizmetleri'ne**</a> gidin.
    3. Aşağı kaydırarak **Eklentiler** bölümüne gelin.
    4. Syntex kutucuğunda **Ayrıntılar'ı** seçin.
    5. **Ücretsiz denemeyi başlat'ı** seçin.
    6. Deneme sürümünü onaylamak için kalan sihirbaz adımlarını izleyin.

Deneme sürümünü etkinleştirmek için Microsoft 365 genel yöneticisi veya faturalama yöneticisi olmanız gerekir.

### <a name="who-should-be-involved-in-a-trial"></a>Bir denemede kimlerin yer alması gerekir?

|Rol|Etkinlik|
|---|---|
|Microsoft 365 genel yöneticisi veya faturalama yöneticisi|Deneme sürümünü etkinleştirme ve lisans atama|
|Microsoft 365 genel yöneticisi veya SharePoint yöneticisi|Syntex'i yapılandırma ve içerik merkezleri oluşturma|
|İş kullanıcıları|Model oluşturma ve test etme|

### <a name="before-you-activate-a-trial"></a>Deneme sürümünü etkinleştirmeden önce

Syntex denemesini başarıyla planlamak için aşağıdaki faktörleri göz önünde bulundurun:

- En anlamlı test , "gerçek dünya" senaryolarında ve verilerinde tamamlanır.
- Syntex deneme sürümünü kiracı başına yalnızca bir kez etkinleştirebilirsiniz.

Bir test veya tanıtım kiracısı, etkinleştirme adımlarını ve yönetim denetimlerini gözden geçirmek için "kuru çalıştırma" olarak kullanılabilir. Ancak büyük olasılıkla bir üretim kiracısı üzerinde model oluşturmayı değerlendirmek en iyisidir.

Üretim kiracısının deneme sürümünün değerini en üst düzeye çıkarmak için planlama ve iş etkileşimi gereklidir. Syntex tarafından ele alınabilecek üç veya altı kullanım örneğini belirlemek için bir veya daha fazla iş alanıyla etkileşime geçmeniz gerekir. Bu kullanım örnekleri şunları yapmalıdır:

- Form işleme veya belge anlama modeli tarafından çözülebilecek senaryolar ekleyin.
- Ayıklanan meta verilerin amacını net bir şekilde anlayın; örneğin, Power Automate'i kullanarak biçimlendirmeyi veya otomasyonu görüntüleyin. Syntex, belgeleri sınıflandırmaya ve meta verileri ayıklamaya odaklanmış olsa da, bu meta verilerin sağladığı miktar değeridir.
- Tanımlı bir veri kümesini temel alın; örneğin, belirli SharePoint siteleri veya kitaplıkları. Syntex'in yaygın bir yanılgısı, genel amaçlı modellerin tüm kuruluş içeriğine uygulanabilmesidir. Daha doğru bir görünüm, modellerin hedeflenen konumlardaki belirli iş sorunlarını çözmeye yardımcı olmak için oluşturulduğudur.

Bu kullanım örneklerinin tümü Syntex için uygun olmayabilir. Kaliteli denemenin amacı Syntex'in tüm senaryolara uygun olduğunu kanıtlamak değildir. Bunun yerine, deneme sürümü ürünün değerini daha iyi anlamanıza yardımcı olmalıdır.

Planlanan kullanım örneklerinin her biri için, ilgili içerik veya süreçte konu uzmanı olan kullanıcıları belirleyin. Syntex modellerinin oluşturulması, BT uzmanlarına veya geliştirici kaynaklarına değil içerikteki etki alanı uzmanlarına odaklanır.

## <a name="activate-a-trial"></a>Deneme sürümünü etkinleştirme

Deneme sürümünü başlattığınızda şunları yapmanız gerekir:

- İlgili kullanıcılara lisans atayın.
- [Syntex'in ek kurulumunu gerçekleştirin](set-up-content-understanding.md).
  - Daha [fazla içerik merkezi oluşturmak](create-a-content-center.md) isteyebilirsiniz.

Deneme sürümü etkinleştirildikten sonra modeller oluşturabilir ve dosyaları işleyebilirsiniz. [Model oluşturma yönergelerine](create-a-content-center.md) bakın.

## <a name="during-a-trial"></a>Deneme sırasında

Deneme süreleri sınırlıdır, bu nedenle başlangıçta Syntex modellerinin belgeleri sınıflandırıp sınıflandıramayacağına ve tanımlı kullanım örnekleri için meta verileri ayıklayıp ayıklayamayacağına odaklanmak en iyisidir. Deneme süresi sona erdikten sonra meta verilerin nasıl kullanılabileceğini değerlendirebilirsiniz.

## <a name="after-a-trial"></a>Denemeden sonra

Denemenin sonucuna bağlı olarak Syntex'in üretim kullanımına devam edip etmeyeceğinize karar vekleyebilirsiniz.

### <a name="proceed-to-production-use"></a>Üretim kullanımına geçin

Hizmetin sürekliliğini sağlamak için gerekli lisans sayısını satın almanız ve bu [lisansları](syntex-licensing.md) kullanıcılara atamanız gerekir. Deneme süresinin sonunda tam lisansı olmayan deneme kullanıcıları Syntex'i tam olarak kullanamaz.

Beklenen sayıda AI Builder kredisi için öngörülen form işleme ve plan kullanımınızı tahmin etmek zorunda olabilirsiniz. Yardım için bkz. [Size uygun AI Builder kapasitesini tahmin](https://powerapps.microsoft.com/ai-builder-calculator/) etme.

### <a name="dont-proceed-to-production-use"></a>Üretim kullanımına devam etmeyin

Deneme sürümünden sonra lisans satın almıyorsanız:

- Yeni modeller oluşturamazsınız.
- Modelleri çalıştıran kitaplıklar artık dosyaları otomatik olarak sınıflandırmaz veya modelleri ayıklamaz.
- Daha önce sınıflandırılmış dosyalar veya ayıklanan meta veriler etkilenmez.
- İçerik merkezleri ve belge anlama modelleri otomatik olarak silinmez. Gelecekte lisans satın alma kararı alırsanız bunlar kullanılabilir durumda kalır.
- Form işleme modelleri, varsayılan Power Platform ortamının Dataverse (eski adı Common Data Service (CDS)) örneğinde depolanır. Bunlar Syntex için gelecekteki lisanslama ile veya Power Platform'daki AI Builder özellikleriyle kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Syntex'i benimsemeye başlama](adoption-getstarted.md)

[Microsoft Syntex için senaryolar ve kullanım örnekleri](adoption-scenarios.md)