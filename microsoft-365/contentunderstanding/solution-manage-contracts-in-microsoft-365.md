---
title: Microsoft 365 çözümü kullanarak sözleşmeleri yönetme
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.service: microsoft-365-enterprise
ms.collection:
- m365solution-managecontracts
- m365solution-overview
- highpri
- m365initiative-syntex
search.appverid: ''
ms.localizationpriority: medium
ROBOTS: ''
description: SharePoint Syntex, SharePoint Listeleri, Microsoft Teams ve Power Automate'in Microsoft 365 çözümünü kullanarak sözleşmeleri yönetmeyi öğrenin.
ms.openlocfilehash: edb05502ff9f4a84f194e4f991307886ce85bd46
ms.sourcegitcommit: 674dfa2cb2f20546d2f7822e09bacf0e12e2718b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68041183"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Microsoft 365 çözümü kullanarak sözleşmeleri yönetme

Bu makalede, Microsoft 365'in SharePoint Syntex ve bileşenlerini kullanarak kuruluşunuz için sözleşme yönetimi çözümünün nasıl oluşturulacağı açıklanır. Benzersiz iş gereksinimlerinize uygun bir çözüm planlamanıza ve oluşturmanıza yardımcı olacak bir çerçeve sağlar. Bu çözüm sözleşme yönetiminden bahsetse de, iş veya fatura deyimleri gibi başka belge yönetimi çözümleri oluşturmak için uyarlayabilirsiniz.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWJUR0]

</br>

## <a name="identify-the-business-problem"></a>İş sorununu tanımlama

Sözleşme yönetim sisteminizi planlamanın ilk adımı çözmeye çalıştığınız sorunu anlamaktır. Bu çözüm için dört önemli sorunun çözülmesi gerekir:

- **Sözleşmeleri tanımlama**. Kuruluşunuz faturalar, sözleşmeler, iş ekstreleri gibi birçok belgeyle çalışır.  Bazıları e-posta yoluyla gönderilen dijital varlıklar, bazıları ise geleneksel postalar aracılığıyla gönderilen kağıt varlıklardır. Diğer tüm belgelerden tüm müşteri sözleşmelerini tanımlamanın ve sonra bunları bu şekilde sınıflandırmanın bir yolunu kullanmanız gerekir.

- **Sözleşme onaylarının geçmişini izleyin**. Kuruluşunuzun, sözleşmelerin onaylanıp onaylanmamış olup olmadığını ve ödemenin işlenip işlenmediğini bulmak için güvenilir bir yönteme ihtiyacı vardır. 

- **Sözleşme onaylarını yönetmek için site**. Kuruluşunuzun tüm gerekli paydaşların sözleşmeleri kolayca gözden geçirebileceği işbirliğine dayalı bir site ayarlaması gerekir. Paydaşlar gerekirse sözleşmenin tamamını gözden geçirebilmelidir, ancak çoğunlukla her sözleşmeden birkaç önemli alan (örneğin, müşteri adı, PO numarası ve toplam maliyet) görmeyi önemser. Paydaşlar gelen sözleşmeleri kolayca onaylayabilmeli veya reddedebilmelidir.

- **Gözden geçirilmiş sözleşmeleri yönlendirme**. Onaylanan ve reddedilen sözleşmelerin belirli bir iş akışı üzerinden yönlendirilmesi gerekir. Onaylanan sözleşmelerin ödeme işleme için üçüncü taraf bir uygulamaya yönlendirilmesi gerekir. Reddedilen sözleşmelerin ek gözden geçirme için yönlendirilmesi gerekir.

## <a name="overview-of-the-solution"></a>Çözüme genel bakış

  ![SharePoint Syntex, SharePoint listeleri, Teams ve Power Automate kullanan çözümün diyagramı.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

Bu sözleşme yönetimi çözümü kılavuzu, Microsoft 365'in dört bileşenini içerir:

- **Microsoft SharePoint Syntex**: Sözleşme dosyalarınızı tanımlamak ve sınıflandırmak ve ardından bunlardan uygun verileri ayıklamak için modeller oluşturun.

- **Microsoft SharePoint listeleri**: Sözleşmeleri iş dostu bir biçimde sunmak için modern SharePoint listelerinde sağlanan biçimlendirmeyi kullanın.

- **Microsoft Teams**: Proje katılımcılarınızın sözleşmeleri gözden geçirmesine ve yönetmesine olanak sağlamak için Teams kanalının ve ilişkili sekmelerin işlevselliğini kullanın.

- **Power Automate**: Sözleşmeleri onay süreci boyunca ve ardından ödeme için üçüncü taraf bir uygulamaya yönlendirmek için akışları kullanın.

### <a name="how-it-all-works"></a>Her şey nasıl çalışır?

  ![Belgeleri karşıya yüklemek, verileri ayıklamak, proje katılımcılarını bilgilendirmek ve sözleşmeyi onaylamak veya reddetmek için iş akışını gösteren çözümün diyagramı.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. Belgeler bir SharePoint belge kitaplığına yüklenir. Belge kitaplığına SharePoint Syntex belge anlama modeli uygulandı. Aranacak şekilde eğitilen bir "sözleşme" içerik türüyle eşleşip eşleşmediğini görmek için her dosyayı denetler. Eşleşme bulursa, dosyayı "sözleşme" olarak sınıflandırır ve belgenin içerik türünü güncelleştirir.

2. Model ayrıca paydaşların görmekle ilgilendiği her sözleşme dosyasından *Müşteri*, *Yüklenici* ve *Ücret tutarı* gibi belirli verileri çeker.

    Aşağıdaki sayfada modelin tanımlamak üzere eğitilmiş olduğu bir sözleşme örneği verilmiştir.

      ![Sözleşme örneği.](../media/content-understanding/contract.png)

3. Microsoft Teams'de tüm paydaşlar, belge kitaplığındaki tüm sözleşmelerin onay veya reddedilmek üzere görünür olduğu güvenli bir Teams kanalının üyeleridir. Teams işlevselliği kullanılarak, yeni sözleşmelerin gözden geçirilmesi gerektiğinde tüm paydaşlara bildirim gönderilir.

4. Power Automate kullanılarak sözleşmeler Teams kanalındaki onay sürecine taşınır. Bir üye bir sözleşmeyi onayladığında, sözleşme durumu onaylandı olarak değiştirilir, tüm üyelere bir Teams gönderisi aracılığıyla bildirim gönderilir ve sözleşmenin ödemeye hazır olduğunu göstermek için bir satır öğesi oluşturulur. Bu işlem, ödeme için doğrudan üçüncü taraf bir finansal uygulamaya yazılacak şekilde uzatılabilir.

5. Bir üye bir sözleşmeyi reddettiği zaman, durum reddedildi olarak değiştirilir ve tüm üyeler bir Teams gönderisi aracılığıyla bildirilir.

6. Bu çözümün sonucu, kuruluşunuz için otomatik bir iş sürecidir. Çalışanlar, belgelerinizin onay iş akışını başlatmak ve izlemek için Teams'deki özel kutucuk görünümünü kolayca kullanabilir. 

     ![Sözleşmeler sekmesi.](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a>Lisans gereksinimleri

Bu çözüm, tümü Microsoft 365 Kurumsal (E1, E3, E5, F3) veya İş (Temel, Standart veya Premium) lisansının parçası olarak kullanılabilen aşağıdaki işlevlere dayanır:

- Microsoft SharePoint Syntex
- Microsoft Teams
- Power Automate

### <a name="learn-how-to-use-sharepoint-syntex"></a>SharePoint Syntex kullanmayı öğrenin

SharePoint Syntex'da yeni misiniz? yapay zeka kullanarak içeriği yönetmek için SharePoint Syntex kullanmayı öğrenin.

[SharePoint Syntex kullanmaya başlama](/training/paths/syntex-get-started) öğrenme yolu, belgeleri sınıflandırmak, metin ayıklamak ve hızlı ve kolay bilgi yönetimi için belgelerinizi etiketlemek için belge anlama ve form işleme modellerini nasıl kullanabileceğinizi öğretir.

## <a name="create-the-solution"></a>Çözümü oluşturma

Sonraki bölümlerde sözleşme yönetimi çözümünüzü yapılandırma hakkında ayrıntılı bilgi verilecektir. Üç adıma ayrılmıştır:

- [1. Adım. Sözleşme dosyalarını tanımlamak ve verileri ayıklamak için SharePoint Syntex kullanma](solution-manage-contracts-step1.md)
- [2. Adım. Sözleşme yönetim kanalınızı oluşturmak için Microsoft Teams'i kullanma](solution-manage-contracts-step2.md)
- [3. Adım. Anlaşmalarınızı işlemek üzere akış oluşturmak için Power Automate'i kullanma](solution-manage-contracts-step3.md)
