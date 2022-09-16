---
title: projeleri Microsoft Defender Tehdit Analizi (MDTI) ile kullanma
description: Microsoft Defender Tehdit Analizi (MDTI) kullanarak projeleri yönetmeyi öğrenin.
author: alexroland24
ms.author: aroland
manager: dolmont
ms.service: threat-intelligence
ms.topic: how-to
ms.date: 08/02/2022
ms.custom: template-how-to
ms.openlocfilehash: 02a279f97db0d72ddb978601fb2b693c9995ac4a
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67739234"
---
# <a name="using-projects"></a>Projeleri kullanma

Microsoft Defender Tehdit Analizi (Defender TI) platformu, kullanıcıların ilgi göstergelerini ve bir soruşturmadan ödün verme göstergelerini düzenlemek için özel kişisel veya takım proje türleri geliştirmesine olanak tanır. Projeler, tüm ilişkili yapıtların listesini ve adları, açıklamaları, ortak çalışanları ve izleme profillerini koruyan ayrıntılı bir geçmiş içerir.

Kullanıcı Defender TI'da bir IP adresini, etki alanını veya konağı ararken, bu gösterge kullanıcının erişimi olan bir projede listeleniyorsa, kullanıcı Zeka bölümündeki Projeler dikey penceresini seçebilir ve daha fazla bilgi için diğer veri kümelerini gözden geçirmeden önce gösterge hakkında daha fazla bağlam için projenin ayrıntılarına gidebilir. Alternatif olarak, kullanıcılar sol taraftaki menü bölmesinde projeler simgesini seçerek özel ekip projelerini görüntüleyebilir.

Bir projenin ayrıntılarını ziyaret etmeniz, tüm ilişkili yapıtların listesini ve yukarıda açıklanan tüm bağlamı koruyan ayrıntılı bir geçmişi gösterir. Aynı kuruluştaki kullanıcıların artık iletişim kurmak için zaman harcaması gerekmez. Tehdit aktörü profilleri Defender TI içinde oluşturulabilir ve "canlı" bir gösterge kümesi görevi görebilir. Yeni bilgiler bulunduğunda veya bulunduğunda bu projeye eklenebilir.

Defender TI platformu, kullanıcıların ilgi çekici göstergeleri ve bir araştırmadan ödün verme göstergelerini düzenlemek için birden çok proje türü geliştirmesine olanak tanır.

Bir projenin sahibi, ortak çalışanları (Defender TI Premium lisansıyla Azure kiracısında listelenen kullanıcılar) ekleyebilir. Bu, ortak çalışanların projede herhangi bir değişiklik yapma iznini, projenin sahibiymiş gibi verir. Ortak çalışanların projeleri silemez olması özel durum. ortak çalışanlar, projelerle paylaşılan projeleri Projeler Giriş Sayfasının Paylaşılan Projeler bölümünde görüntüler.

Kullanıcılar ayrıca indirme simgesini seçerek proje içindeki yapıtları da indirebilir. Bu, tehdit avcılığı ekiplerinin bir araştırmadan elde ettikleri bulguları kullanarak risk göstergelerini engellemeleri veya SIEM'leri içinde ek algılama kuralları oluşturmaları için harika bir yoldur.

**Projelerin Yanıtlamaya Yardımcı Olabileceği Sorular:**

- Ekip üyelerimden biri bu göstergeyi içeren bir Ekip projesi oluşturdu mu?

   - Öyleyse, bu ekip üyesinin başka hangi ilgili risk göstergelerini yakaladığını ve araştırma türünü tanımlamak için hangi açıklamayı ve etiketleri içerdiğini?

- Bu ekip üyesi projeyi en son ne zaman düzenledi?

    ![Projeler Ayrıntılı Proje Chrome Ekran Görüntüsü](media/projectsDetailedProjectChromeScreenshot.png)

## <a name="prerequisites"></a>Önkoşullar

- Bir Azure Active Directory veya kişisel Microsoft hesabı. [Oturum açma veya hesap oluşturma](https://signup.microsoft.com/)
- Microsoft Defender Tehdit Analizi (Defender TI) Premium lisansı.
    > [!NOTE]
    > Defender TI Premium lisansı olmayan kullanıcılar Defender Tehdit Bilgileri Portalı'na giriş yapmaya ve ücretsiz Defender TI teklifimize erişmeye devam edebilir.

## <a name="open-defender-tis-threat-intelligence-home-page"></a>Defender TI'nin Tehdit Bilgileri Giriş Sayfasını açın

1. [Defender Tehdit Bilgileri Portalı'na](https://ti.defender.microsoft.com/) erişin.
2. Portala erişmek için Microsoft kimlik doğrulamasını tamamlayın.

## <a name="creating-a-project"></a>Proje Oluşturma

Kullanıcılar, Projeler Giriş Sayfası aracılığıyla veya sonuçları araştırırken iki farklı yolla proje oluşturabilir.

Defender TI Projeleri Giriş Sayfasında oturum açarken, kullanıcılara sahip oldukları veya kiracılarındaki diğer Defender TI kullanıcılarıyla paylaşılmış projeleri gösteren bir pano sunulur. Doğrudan bu görünümden, kullanıcılar yalnızca "+" simgesini seçerek yeni bir proje oluşturmaya karar verebilir veya sol taraftaki çekmece menüsünü kullanarak proje sayfasını ziyaret edebilir.

1. Proje Giriş Sayfasından proje oluşturmak için 'Projeler' simgesine gidin ve Projeler Giriş Sayfası'ndan 'Yeni Proje Ekle' simgesini seçin.

    ![Project'e ekle](media/projectsAddProject.png)

    Defender TI içinde arama yaparken, kullanıcılar var olan bir projeye yapıtı (risk göstergesi) eklemek veya yapıtı eklemek için yeni bir proje oluşturmak için 'Projeye Ekle'yi seçebilir.

2. Araştırma yoluyla proje oluşturmak için Tehdit Bilgileri arama çubuğundan bir gösterge araması yapın ve 'Projeye Ekle' simgesine tıklayın.

3. Yeni proje oluşturuyorsanız , 'Yeni Proje Ekle' bağlantısını seçin, gerekli alanları doldurun ve yeni projenizi 'Kaydedin'. Yapıtı eklemek istediğiniz mevcut bir projeniz varsa lütfen seçin veya aşağı kaydırın ve istediğiniz projeyi seçin.

    ![Yeni Proje Ekle](media/projectsAddNewProjectDetails.png)

## <a name="managing-projects"></a>Projeleri Yönetme

Bir kullanıcı proje oluşturduktan sonra bunları platformun Projeler bölümünden yönetebilir. İlk Proje Giriş sayfası, kullanıcının görebileceği tüm projeleri vurgular ve proje özelliklerine göre filtreleme yöntemleri sağlar. Proje Giriş sayfası varsayılan olarak kiracılarındaki Defender TI kullanıcılarıyla ilişkilendirilmiş Takım projeleridir. Kendi oluşturdukları kişisel projelerin yanı sıra katkıda bulunmak üzere kendileriyle paylaşılmış projeleri seçme seçeneğine sahiptir.

![Projeleri Yönetme](media/projectsHomePage.png)

1. Kullanıcılar proje adına tıklayarak projenin ayrıntılarını görüntüleyebilir.
2. Erişim düzeyine bağlı olarak, kullanıcılar sağ üst köşedeki düzenle düğmesine tıklayarak projede doğrudan değişiklik yapabilir.
3. Kullanıcılar ayrıca projenin sahibiyse projeyi silebilir. Ayrıca sağ üst köşedeki "Yapıt Ekle" düğmesini kullanarak yapıtları el ile eklemeyi de seçebilirler.

## <a name="best-practices"></a>En İyi Yöntemler

Olası tehditleri araştırmak için Defender TI'yi kullanmak söz konusu olduğunda, bu adımlar taktiksel zekaya geçmeden önce stratejik ve operasyonel zeka toplamanıza olanak sağlayacağından aşağıdaki iş akışlarını yürütmenizi öneririz.

Kullanıcılar Defender TI içinde çeşitli arama türleri gerçekleştirebilir. Bu nedenle, belirli göstergeleri araştırmadan önce size geniş sonuçlar sunacak şekilde zeka toplama yönteminize yaklaşmak önemlidir. Örneğin, Bir IP adresini Defender TI Giriş Sayfası'na göre ararsanız, hangi makalelerin bu IP adresiyle bir ilişkisi vardır? Bu makalelerde IP adresi hakkında hangi bilgiler bulunur? Aksi takdirde veri kümesi zenginleştirmesi için doğrudan IP adresinin Veri sekmesine giderken bulamazsınız. Örneğin, bu IP adresi olası bir C2 olarak tanımlandı mı, tehdit aktörü kim, makalede başka hangi ilgili risk göstergeleri listeleniyor, tehdit aktörü hangi TTP'leri kullanıyor ve kimi hedefleniyor?

Kullanıcılar, Defender TI ile çeşitli arama türleri gerçekleştirmenin yanı sıra araştırmalarda birlikte işbirliği yapabilir. Bu nedenle kullanıcıların proje oluşturması, bir projeye araştırmayla ilgili göstergeler eklemesi ve aynı araştırma üzerinde birden fazla kişi çalışıyorsa projeye ortak çalışanlar eklemesi teşvik edilir. Bu, aynı GÇ'leri analiz etmek için harcanan süreyi azaltmaya yardımcı olur ve daha hızlı bir iş akışı gözlemlenmesine neden olur.