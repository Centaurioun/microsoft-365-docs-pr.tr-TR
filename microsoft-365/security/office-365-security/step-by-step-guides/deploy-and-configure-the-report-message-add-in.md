---
title: Rapor iletisi eklentisini dağıtma ve yapılandırma
description: Microsoft'un güvenlik yöneticilerine yönelik kimlik avı raporlama eklentilerini dağıtma ve yapılandırma adımları.
search.product: ''
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
search.appverid: met150
ms.openlocfilehash: fd494b27654ba137409b3e29e21d81229ff5fddb
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67690673"
---
# <a name="deploy-and-configure-the-report-message-add-in-to-users"></a>Rapor iletisi eklentisini dağıtın ve kullanıcılara yapılandırın.

Outlook için Rapor iletisi ve rapor kimlik avı eklentisi, kimlik avının analiz için Microsoft'a ve bağlı kuruluşlarına bildirilmesine ve [gönderim portalındaki](https://security.microsoft.com/reportsubmission?viewid=user) yöneticiler için kolay önceliklendirmeye olanak sağlar. 

Office 365 için Defender lisansınız olup olmadığına bağlı olarak, güvenlik operasyonları personelinizin yükünü ortadan kaldıracak uyarı & otomatik araştırma ve yanıt (AIR) gibi işlevler de eklenir. Bu kılavuz, Office 365 için Microsoft Defender ekibi tarafından önerilen eklenti dağıtımını yapılandırma konusunda size yol gösterir.

## <a name="choose-between-which-add-in-to-deploy"></a>Hangi eklentinin dağıtılacağı arasında seçim yapma

- Kimlik Avı Bildir eklentisi yalnızca kimlik avı iletilerini raporlama seçeneği sağlar
- Rapor İletisi eklentisi gereksiz (hatalı pozitif) ve kimlik avı iletilerini değil gereksiz postaları raporlama seçeneği sağlar


## <a name="what-youll-need"></a>İhtiyacınız olan şey

-   Exchange Online Protection (bazı özellikler plan 2 Office 365 için Defender gerektirir)
-   Yeterli izinler (Eklenti dağıtımı için genel yönetici, özelleştirme için güvenlik yöneticisi)
- Aşağıdaki adımları gerçekleştirmek için 5-10 dakika

## <a name="deploy-the-add-in-for-users"></a>Kullanıcılar için eklentiyi dağıtma

1.  Microsoft 365 yönetim merkezi **oturum açın**.  https://admin.microsoft.com.
1.  Sol gezinti bölmesinde **Tümünü Göster'e** basın, ardından **Ayarlar'ı** genişletin ve **Tümleşik Uygulamalar'ı** seçin.
1.  Yüklenen sayfada **Uygulama Al'a** basın.
1.  Görüntülenen sayfada, sağ üstteki Arama kutusuna **Rapor İletisi** veya **Rapor Kimlik Avı** yazın ve Ara'yı **seçin**.
1.  Arama sonuçları içinde seçtiğiniz uygulamada **Şimdi al'a** basın (yayımcı **Microsoft Corporation'dır**).
1.  Açılan açılır öğede eklentinin dağıtılacağı kişiyi seçin. Test etmek istiyorsanız belirli bir grubu kullanmak isteyebilirsiniz, aksi takdirde seçimi yaptığınızda tüm **kuruluş** için yapılandırın **İleri tuşuna** basın.
1.  İzinleri, bilgileri ve özellikleri gözden geçirin ve **İleri'ye** basın.
1.  **Dağıtımı bitir'e** basın (eklentinin Outlook istemcilerinde otomatik olarak görünmesi 12-24 saat sürebilir).

## <a name="configure-the-add-in-for-users"></a>Eklentiyi kullanıcılar için yapılandırma
1.  adresinden Microsoft Güvenlik portalında https://security.microsoft.com**oturum açın**.
2.  Sol gezinti bölmesinde, **işbirliği Email &** altında **İlkeler & kuralları'nı** seçin.
3.  **Tehdit ilkeleri'ne tıklayın**.
4.  **Diğerleri** başlığının altında **Kullanıcı tarafından bildirilen ileti ayarları'nı** seçin.
5.  **Microsoft Outlook Rapor İletisi düğmesinin** **Açık** olarak ayarlandığından emin olun.
6.  **Bildirilen iletileri gönder'in** altında **Microsoft'u** seçin (Önerilir).
7.  **Kullanıcıların raporlamak isteyip istemediklerini seçmesine izin ver** seçeneğinin işaretli olmadığını ve **İletiyi her zaman bildir'in** seçili olduğundan emin olun.
8.  **Kaydet'e** basın.

## <a name="optional-steps--configure-notifications"></a>İsteğe bağlı adımlar – bildirimleri yapılandırma

1.  Önceki adımlarda yer alan yapılandırma sayfasında, **Kullanıcı raporlama deneyiminin** altında, isterseniz pop-up'ların önce ve sonra bildirimi başlığını ve gövdesini yapılandırın. Raporlamadan önce sor seçeneği de etkinse son kullanıcılar **raporlamadan önce** açılan penceresini görür.
2.  Bildirimlerin kuruluş içindeki bir posta kutusundan gelmesini istiyorsanız, **gönderen olarak kullanılacak Office 365 e-posta adresini belirtin'i** seçin ve bildirimleri göndermek için kuruluşunuzda geçerli bir posta kutusu arayın.
3.  Yönetici Bildirim **İşaretle** & Bildir'i kullanarak bildirilen bir iletiyi gözden geçirdikten sonra raporlama kullanıcılarına gönderilen metni ayarlamak için Bildirimleri özelleştir'e basın, **Kimlik Avı**, **Önemsiz** & **Tehdit bulunamadı** seçeneklerini yapılandırın.
4.  **Alt Bilgi** sekmesinde, bildirimler için gönderilecek genel alt bilgiyi ve uygunsa kuruluşunuzun logosunu seçin.


### <a name="further-reading"></a>Daha fazla okuma
Kullanıcı tarafından bildirilen ileti ayarları hakkında daha fazla bilgi edinin [Kullanıcı tarafından bildirilen ileti ayarları - Office 365 | Microsoft Docs](../user-submission.md)

Rapor iletisini veya rapor kimlik avı eklentisini [etkinleştirme Rapor İletisini veya Rapor Kimlik Avı eklentilerini etkinleştirme - Office 365 | Microsoft Docs](../enable-the-report-message-add-in.md)
