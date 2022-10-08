---
title: Tüm LMS'ler için Microsoft LMS Ağ Geçidi'ni yönetme
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Görüntüleme, silme, düzenleme ve sorun giderme gibi önemli Microsoft LMS Ağ Geçidi yönetim görevlerini yürütmeyi öğrenin.
ms.openlocfilehash: ccf05bb497546bae153f2132e27440713661845b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68187569"
---
# <a name="manage-microsoft-lms-gateway-for-any-lms"></a>Tüm LMS'ler için Microsoft LMS Ağ Geçidi'ni yönetme

Microsoft LMS Gateway, Canvas, Blackboard, Moodle ve Brightspace gibi çeşitli LMS'lerle tümleşir.

Bu makalede, BT yöneticileri önemli Microsoft LMS Ağ Geçidi yönetim görevleriyle ilgili yönergeleri bulur.

- [LTI kaydını görüntüleyin](#view-an-lti-registration).
- [LTI kaydını silin](#delete-an-lti-registration).
- [LTI kaydını düzenleyin](#edit-an-lti-registration).
- [Microsoft LMS Ağ Geçidi ile ilgili sorunları giderin](#troubleshoot-issues-with-microsoft-lms-gateway).
- [Microsoft LMS Ağ Geçidi ile ilgili sorunları bildirin](#report-problems-with-lti-registration-portal).

## <a name="view-an-lti-registration"></a>LTI kaydını görüntüleme

Bir LTI kaydının ayrıntılarını görüntülemek istiyorsanız aşağıdaki adımları izleyin.

1. [Microsoft LMS Ağ Geçidi'ni ziyaret edin](https://lti.microsoft.com/).
2. Microsoft 365 yönetici hesabıyla oturum açın.
3. Kayıt listesinde, görüntülemek istediğiniz LTI kaydını bulun.
4. Listenin yanındaki **göz simgesini** seçin.
5. Kayıt ayrıntıları paneli açılır.

## <a name="delete-an-lti-registration"></a>LTI kaydını silme

Bir LTI kaydını silmek istiyorsanız aşağıdaki adımları izleyin.

1. [Microsoft LMS Ağ Geçidi'ni ziyaret edin](https://lti.microsoft.com/).
2. Microsoft 365 yönetici hesabıyla oturum açın.
3. Kayıt listesinde silmek istediğiniz LTI kaydını bulun.
4. Dökümün yanındaki **çöp kutusu simgesini** seçin.
5. Silme işlemini onaylamak için onay iletişim kutusunda **Sil'i** seçin.
6. Silindikten sonra bir başarı iletisi görürsünüz.

## <a name="edit-an-lti-registration"></a>LTI kaydını düzenleme

Şu anda, eklendikten sonra mevcut bir LTI kaydını düzenlemeyi desteklemiyoruz.

LTI kaydını değiştirmek için şunları yapmanız gerekir:

1. [Mevcut kaydı silin](#delete-an-lti-registration).
2. Yeni bir kayıt ekleyin.

## <a name="troubleshoot-issues-with-microsoft-lms-gateway"></a>Microsoft LMS Ağ Geçidi ile ilgili sorunları giderme

Siz veya eğitimcileriniz Microsoft LMS Ağ Geçidi ile ilgili sorunlar yaşıyorsanız, sorun gidermek için yapabileceğiniz bazı işlemler şunlardır.

### <a name="issues-while-launching-an-lti-app-from-the-lms"></a>LMS'den LTI uygulaması başlatırken karşılaşılan sorunlar

Eğitimciler LMS'lerinde bir Microsoft LTI uygulaması başlatırken sorunlarla karşılaşabilir.

Öyleyse, bazı yaygın sorunlar ve bunların nasıl çözüleceğini burada bulabilirsiniz.

- **Tanımlama bilgileri bulunamıyor**
  - Tarayıcı ayarlarında **LMS URL'si** için üçüncü taraf tanımlama bilgilerine izin verilmelidir.
  - Bu tanımlama bilgileri, IMS belirtimlerine göre LTI 1.3 el sıkışmasını tamamlamak için gereklidir.
  - Tarayıcınızın tanımlama bilgisi ayarlarını nasıl güncelleştireceğinizi öğrenmek için bkz. [Tarayıcınızda LMS URL'leri için tanımlama bilgilerine izin verme](browser-cookies.md).

- **Kayıt ayrıntıları bulunamadı**
  - Bu sorun, LTI uygulamasının kaydı tamamlanmadığında veya kayıt Microsoft LMS Ağ Geçidi'nde silindiğinde ortaya çıkar.
  - BT yöneticisinin LTI uygulamasının kaydını tamamlaması gerekir.

- **LMS'den bazı ayrıntılar geçerli değil**
  - Bu sorun, uygulama başlatma isteğindeki LMS'den gönderilen ayrıntılar IMS LTI 1.3 belirtimiyle uyumlu olmadığında ortaya çıkar.
  - Sorun devam ederse BT yöneticisinin [Microsoft'un eğitim destek ekibine](https://edusupport.microsoft.com/support?product_id=lti_apps&platform_id=web) ulaşması gerekir.

### <a name="issues-with-signing-in-to-the-microsoft-lms-gateway"></a>Microsoft LMS Ağ Geçidi'nde oturum açma sorunları

Microsoft LMS Ağ Geçidi'nde oturum açarken kayıt sayfasına erişirken sorunlarla karşılaşabilir veya oturum açma hatası alabilirsiniz.

Bazı yaygın oturum açma sorunları ve bunların nasıl çözüleceğini burada bulabilirsiniz.

- **Yetkilendirme hatası**
  - "Hesabınızın bu sayfaya erişim izni yok" hata iletisini görürseniz, iki durumda da:
    - Hesap kayıtlı bir kiracıya ait değil veya
    - Hesap bir eğitimciye veya yöneticiye ait değildir.

  - Her iki durumda da **Bir Oturumu Kapat & hesap değiştir** düğmesini görürsünüz.
    - Bu düğmeyi seçin veya kullanıcı profili menüsünün altındaki **Oturumu kapat** düğmesini seçin.
    - Kiracıya, eğitimciye veya yöneticiye ait bir hesapla oturum açın.

  - Kiracı kayıtlı değilse, BT yöneticisinin LTI tümleştirmelerini kaydetmeye çalışmadan önce kiracıyı kaydetmesi gerekir.

  - Bu adımları denedikten sonra bu hatayı görmeye devam ederseniz oturumu kapatın ve yeniden oturum açın.
    - Ayrıca, Microsoft LMS Ağ Geçidi ve için tanımlama bilgilerini ve `https://login.microsoftonline.com/`yerel depolama alanını temizleyebilirsiniz.
    - Yeniden oturum açmayı deneyin.
    - Sorun devam ederse, sağ üst kısımdaki **Sorun bildir** bağlantısını seçerek sorunu bildirin.

- **Kimlik doğrulama hatası**
  - "Kimlik doğrulaması başarısız oldu. Yeniden deneyin", oturum açma oturumunun süresi dolmuş olabilir.
    - Oturumu kapatın ve yeniden oturum açın.
    - Ayrıca, Microsoft LMS Ağ Geçidi ve için tanımlama bilgilerini ve `https://login.microsoftonline.com/`yerel depolama alanını temizleyebilirsiniz.
    - Yeniden oturum açmayı deneyin.
    - Sorun devam ederse, sağ üst kısımdaki **Sorun bildir** bağlantısını seçerek sorunu bildirin.

- **Diğer hatalar**
  - Diğer tüm hatalar için şu hata iletisini görürsünüz: "Bir sorun oluştu. Daha sonra yeniden deneyin.
    - Bu bir iç işlem hatası olabilir.
    - Birkaç saat sonra yeniden oturum açmayı deneyin.
      - **Giriş sayfasına git** düğmesini seçin. Bu işlem giriş sayfasına geri döner.
      - Microsoft LMS Ağ **Geçidi'ne dönmek için Kayıt portalına git** düğmesini seçin.

### <a name="report-problems-with-lti-registration-portal"></a>LTI kayıt portalıyla ilgili sorunları bildirme

Sorunları bildirmek veya LTI kayıt portalı için geri bildirim göndermek için aşağıdaki adımları izleyin.

1. LTI kayıt portalında, sayfa üst bilgisindeki **soru işareti simgesini** seçin.
2. Açılan listede **Sorun bildir'i** seçin.
3. Microsoft Eğitim Desteği sayfası açılır. Microsoft 365 kimlik bilgilerinizle oturum açın.
4. Formu doldurun ve gönderin.
