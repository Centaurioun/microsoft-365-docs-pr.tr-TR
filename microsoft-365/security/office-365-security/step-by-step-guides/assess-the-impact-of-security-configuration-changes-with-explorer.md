---
title: Explorer ile güvenlik yapılandırması değişikliklerinin etkisini değerlendirme
description: Office 365 için Microsoft Defender'de bir güvenlik denetimi (yapılandırma) değişikliğinin etkisini belirlemek için Explorer'ı kullanma örnekleri ve izlenecek yol
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 35ab846810c4cef2fdd87563bda3f69a7a5f73f9
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2022
ms.locfileid: "67107205"
---
# <a name="assess-the-impact-of-security-configuration-changes-with-explorer"></a>Explorer ile güvenlik yapılandırması değişikliklerinin etkisini değerlendirme

İlkeler veya aktarım kuralları gibi güvenlik yapılandırmanızda değişiklik yapmadan önce, kuruluşunuzda *en az* kesintiyi planlayabilmek ve sağlamak için değişikliklerin etkisini anlamanız önemlidir.

Bu adım adım kılavuz, bir değişikliği değerlendirme ve değerlendirme için etkilenen e-postaları dışarı aktarma konusunda size yol gösterir. Yordam, gezginde kullandığınız ölçütler (filtreler) değiştirilerek birçok farklı değişikliğe uygulanabilir.

## <a name="what-youll-need"></a>İhtiyacınız olan şey

- Office 365 için Microsoft Defender Plan 2 (E5'in bir parçası olarak dahildir).
- Yeterli izinler (Tehdit Gezgini aracılığıyla değerlendirmek için en düşük güvenlik okuyucu gereklidir).
- Aşağıdaki adımları gerçekleştirmek için 5-10 dakika.

## <a name="assess-changing-normal-confidence-phish-delivery-location-to-quarantine-from-the-junk-email-folder"></a>Normal güvenilirlik kimlik avı teslim konumunu karantinaya almak için değiştirme değerlendirme (Gereksiz e-posta klasöründen)

1. Güvenlik portalında **oturum açın** ve Gezgin'e gidin (sol gezinti *bölmesindeki İşbirliği Email &* altında). <https://security.microsoft.com/threatexplorer>
1. Üst sekme seçiminden **Kimlik Avı'nı** seçin (*Tüm e-postalar* varsayılan görünümdür).
1. **Filtre** düğmesine (varsayılan olarak *Gönderen* olarak ayarlanır) basın ve **Kimlik avı güvenilirlik düzeyi'ni** seçin.
1. **Normal** kimlik **avı güvenilirlik düzeyini** seçin.
1. **Gereksiz klasör** olarak ayarlanan **Özgün teslim konumuna** ek bir **filtre** ekleyin.
1. **Yenile'ye** basın. Explorer artık *yüksek güvenilirlikli kimlik avı* olarak algılanan tüm postaları gösterecek şekilde filtrelenmiştir ve istenmeyen posta önleme ilkesindeki ayarlar nedeniyle Gereksiz klasörüne teslim edilir.
1. Grafikte görüntülenen verileri özetleme yapmak isterseniz, eğilimleri ve en çok etkilenen gönderenleri saptamak **için grafiğin sol üst kısmındaki veri dilimleyicisini ( *varsayılan olarak Teslim eylemi* olarak adlandırılır)** kullanarak, **Gönderen IP'si** veya **Gönderen etki alanı** gibi yararlı verileri seçerek yapabilirsiniz.
1. Etkilenen e-postaların görüntülendiği grafik bölümünün altında **E-posta listesini dışarı aktar'ı** seçin; bu liste çevrimdışı analiz için bir CSV oluşturur. **Bu, kimlik avı eylemi karantinaya alındıysa karantinaya alınabilecek e-postaların listesidir (hem standart hem de katı ön ayarlar için önerilen değişiklik).**

## <a name="assess-removing-a-sender--domain-override-removal"></a>Gönderenin / etki alanı geçersiz kılmanın kaldırılmasını değerlendirme

1. Güvenlik portalında **oturum açın** ve **Gezgin'e** gidin (sol gezinti bölmesindeki İşbirliği Email & altında) <https://security.microsoft.com/threatexplorer>.
1. Henüz seçili değilse **Tüm e-postalar'ı** seçin.
1. **Filtre** düğmesine basın (varsayılan olarak *Gönderen* olarak ayarlanır) ve bir gönderen veya gönderen etki alanı filtresi ekleyin, ardından kaldırmanın etkisini değerlendirmek istediğiniz girdiyi ekleyin.
1. Tarih aralığını üst sınıra kadar genişletin & **Yenile'ye** basın Artık gönderen/gönderen etki alanı kuruluşunuza ileti göndermede hala etkinse postanın listelendiğini görmelisiniz. *Aksi takdirde* filtreyi değiştirmeniz gerekebilir veya alternatif olarak artık bu etki alanından / gönderenden posta almazsınız ve girişi güvenli bir şekilde kaldırabilirsiniz.
1. Posta listeleniyorsa bu, girdinin hala etkin bir gönderen olduğu anlamına gelir. Veri dilimleyicisini kullanarak grafikteki verileri ( *Varsayılan olarak Teslim eylemi* olarak ayarlanır) **Algılama teknolojisi** olarak özetleyin.
1. Grafiğin yenilenmesi gerekir ve artık veri görüntülenmiyorsa, daha önce gösterilen postaların hiçbirinde herhangi bir tehdit algılamadığımız anlamına gelir; bu da geçersiz kılma algılaması olmadığından geçersiz kılmaya gerek olmadığını gösterir.
1. Veriler **Algılama teknolojisine** göre dilimlendiğinde görüntülenen veriler varsa, koruma yığınının işlem gerçekleştirmesi *nedeniyle geçersiz* kılmanın kaldırılmasının bu göndereni / etki alanını etkilediği anlamına gelir.
1. Postanın gerçekten kötü amaçlı olup olmadığını ve girişin kaldırılıp kaldırılmadığını veya *hatalı pozitif* olup olmadığını değerlendirmek için postayı daha fazla araştırmanız ve artık yanlış bir tehdit olarak algılanmaması için düzeltilmesi gerekir (hatalı pozitif sonuçların en büyük nedeni kimlik doğrulamasıdır).

### <a name="further-reading"></a>Daha fazla okuma

Önceden ayarlanmış [güvenlik ilkeleriyle her zaman en uygun güvenlik denetimlerine sahip olduğunuzdan emin olmak için güvenli ön ayarları](/microsoft-365/security/office-365-security/step-by-step-guides/ensuring-you-always-have-the-optimal-security-controls-with-preset-security-policies) kullanmayı göz önünde bulundurun

Ayrıca kimlik sahtekarlık zekası kimlik bilgileri [içgörüleri](/microsoft-365/security/office-365-security/learn-about-spoof-intelligence) ile e-posta kimlik doğrulaması sorunlarını yönetebilirsiniz

Exchange Online Protection'da e-posta kimlik doğrulaması [Email Kimlik Doğrulaması](/microsoft-365/security/office-365-security/email-validation-and-authentication) hakkında daha fazla bilgi edinin
