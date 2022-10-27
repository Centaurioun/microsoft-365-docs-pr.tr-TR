---
title: Özel etki alanımdan Microsoft 365'i pilot
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier2
- scotvorg
- Adm_O365
- Adm_TOC
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
description: Yalnızca iki test hesabı kullanarak özel etki alanımdan Microsoft 365 posta kutusuna e-posta işlevselliğini denemeyi öğrenin.
ms.openlocfilehash: 210ff211efc32267180ed95b021ec1d5d4f86c95
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68728565"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>Özel etki alanımdan Microsoft 365'i pilot

Microsoft 365'i şu gereksinimler ve sınırlamalarla pilot olarak kullanabilirsiniz:

- Geçerli e-posta sağlayıcınız e-posta iletme sağlamalıdır.

- Microsoft 365 DNS kayıtlarınızı sizin yerinize Microsoft 365'in yönetmesi yerine DNS barındırma sağlayıcınızda yönetmeniz gerekir.

    Daha fazla bilgi edinmek için bkz. [Etki alanınıza bağlanmak için DNS kayıtları ekleme](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

- Diğer e-posta sunucusundaki kullanıcılar için serbest/meşgul bilgileri kullanılamaz.

- Yöneticiler tüm kullanıcı hesaplarını tek bir konumdan yönetemez.

- Kullanıcılar Microsoft 365 istenmeyen posta filtrelemesini kullanamayabilir.

- Bu, çok az sayıda kullanıcı için önerilir ve yalnızca pilot için e-posta kullanımı için geçerlidir.

## <a name="set-up-a-microsoft-365-pilot"></a>Microsoft 365 pilotu ayarlama

Microsoft 365 pilotu ayarlamak için şu adımları izleyin:

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>1. Adım: Microsoft 365 yönetim merkezi oturum açma

1. İş veya okul hesabınızla [Microsoft 365 yönetim merkezi](https://admin.microsoft.com) oturum açın.

2. Sol gezinti bölmesinde **Ayarlar** > **Etki Alanları'nı** seçin.

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>2. Adım: Kullanmak istediğiniz etki alanının sahibi olduğunuzu doğrulayın

1. **Etki alanları** sayfasında **Etki alanı ekle'yi** seçin.

2. Kutuya etki alanı adını yazın, **Bu etki alanını kullan'ı** ve ardından **Devam'ı** seçin.

3. E-posta ve anlık ileti gibi etki alanınızla test etmek istediğiniz hizmetleri seçin.

4. Etki alanını **doğrula** sayfasında adım adım yönergeleri izleyin ve ardından **Doğrula'yı** seçin.

    DNS değişikliklerinin geçerlilik kazanması birkaç dakika ile 72 saat arasında sürer.

    Doğrulama başarılı olduğunda DNS kayıtlarınızı değiştirmeniz istenir.

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>3. Adım: Etki alanını Exchange Online'da paylaşılan olarak işaretleme

1. Exchange yönetim merkezindeki **Posta akışı** bölümünde **Kabul edilen etki alanları'nı** ve ardından değiştirmek istediğiniz etki alanını seçin.

2. Pencereyi açmak için çift tıklayın ve İç **Geçiş'i** seçin.

3. **Kaydet**'i seçin.

    Bu ayarın geçerlilik kazanması birkaç dakika sürebilir.

### <a name="step-4-unblock-the-existing-email-server-optional"></a>4. Adım: Mevcut e-posta sunucusunun engellemesini kaldırma (isteğe bağlı)

Microsoft 365, istenmeyen posta koruması için Exchange Online Protection (EOP) kullanır. EOP, geçerli posta sunucunuz tarafından iletilen yüksek miktarda istenmeyen posta algılarsa mevcut posta sunucunuzu engelleyebilir. Diğer e-posta sağlayıcınızın istenmeyen posta korumasına güveniyorsanız Microsoft 365'te sunucunun engellemesini kaldırabilirsiniz.

> [!NOTE]
> Mevcut e-posta sunucunuzun engelini kaldırmak, özgün sunucunuzdan gelen istenmeyen postaların Microsoft 365 posta kutularına gelmesini sağlar ve Microsoft 365'in istenmeyen postaları ne kadar iyi önlediğini değerlendiremezsiniz.

1. Exchange yönetim merkezi gezinti bölmesinde **Koruma'yı** ve ardından **Bağlantı filtresi'ni** seçin.

2. **IP İzin Ver listesinde** öğesini seçin **+** ve geçerli e-posta sağlayıcınızın posta sunucusu IP adresini ekleyin.

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>5. Adım: Kullanıcı hesapları oluşturma ve birincil yanıt adresini ayarlama

1. Sol Microsoft 365 yönetim merkezi gezinti bölmesinde **Kullanıcılar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Etkin kullanıcılar'ı**</a> seçin.

2. mevcut iki kullanıcı ekleyerek iki test hesabı oluşturun.

    Her hesap için **+ Kullanıcı ekle'yi** seçin ve test etmek istediğiniz parola yöntemi de dahil olmak üzere gerekli bilgileri doldurun.

    Kullanıcının e-postasının aynı kalmasını sağlamak için **Kullanıcı adı** alanının kullanıcının geçerli e-posta adresiyle eşleşmesi gerekir.

3. Uygun lisansı seçin, **İleri'ye** ve ardından **Eklemeyi bitir'e** tıklayın.

4. **Kullanıcı adı'nın** yanında, açılan listeden özel etki alanı adınızı seçin.

5. **Kapat Oluştur'u** >  seçin.

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a>6. Adım: **Postayı Microsoft 365'ten veya Office 365 Email sunucusuna akacak şekilde yapılandırma

Bunun iki adımı vardır:

1. Microsoft 365 veya Office 365 ortamınızı yapılandırın.

2. Microsoft 365'ten veya e-posta sunucunuza Office 365 bir bağlayıcı ayarlayın.

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a>1. Microsoft 365 veya Office 365 ortamınızı yapılandırma

Microsoft 365 veya Office 365'da aşağıdakileri tamamladığınızdan emin olun:

1. Bağlayıcıları ayarlamak için başlamadan önce izinlerin atanmış olması gerekir. Hangi izinlere ihtiyacınız olduğunu denetlemek için, Exchange Online özellik izinleri konusunun Microsoft 365 ve [Office 365 bağlayıcıları](/exchange/permissions-exo/feature-permissions) girişine bakın.

2. EOP'nin veya Exchange Online e-posta sunucularınızdan İnternet'e e-posta geçirmesini istiyorsanız:

   - Microsoft 365 veya Office 365 kabul edilen etki alanıyla eşleşen bir konu adıyla yapılandırılmış bir sertifika kullanın. Sertifikanızın ortak adı veya konu alternatif adının kuruluşunuzun birincil SMTP etki alanıyla eşleşmesini öneririz. Ayrıntılar için bkz. [Şirket içi e-posta ortamınız için önkoşullar](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).

   -VEYA-

   - Tüm kuruluş gönderen etki alanlarının ve alt etki alanlarının Microsoft 365 veya Office 365'da kabul edilen etki alanları olarak yapılandırıldığından emin olun.

   Kabul edilen etki alanlarını tanımlama hakkında daha fazla bilgi için bkz. [Exchange Online'de kabul edilen etki alanlarını yönetme](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) ve [Exchange Online'da alt etki alanları için posta akışını etkinleştirme](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

3. Postayı Microsoft 365'ten veya Office 365 e-posta sunucularınıza teslim etmek için posta akışı kurallarını (taşıma kuralları olarak da bilinir) veya etki alanı adlarını kullanmak isteyip istemediğinize karar verin. Çoğu işletme, kabul edilen tüm etki alanları için posta teslim etmeyi seçer. Daha fazla bilgi için bkz[. Senaryo: Exchange Online koşullu posta yönlendirme](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).

> [!NOTE]
> posta akışı kurallarını[, Exchange Online'daki Posta akışı kuralı eylemleri bölümünde](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) açıklandığı gibi ayarlayabilirsiniz. Örneğin, postanız şu anda dağıtım listeleri aracılığıyla birden çok siteye yönlendiriliyorsa, posta akışı kurallarını bağlayıcılarla birlikte kullanmak isteyebilirsiniz.

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a>2. Microsoft 365'ten veya e-posta sunucunuza Office 365 bağlayıcı ayarlama

Microsoft 365 veya Office 365'da bağlayıcı oluşturmak için **Yönetici** >  **Exchange'i** seçerek Exchange yönetim merkezine gidin. Ardından **posta akışı**<a href="https://go.microsoft.com/fwlink/?linkid=2183136" target="_blank">**Bağlayıcıları'nı**</a> >  seçin.

Sihirbazı kullanarak bağlayıcıları ayarlayın.

Sihirbazı başlatmak için artı simgesine **+** tıklayın. İlk ekranda, **Office 365'den** ve **Kuruluşunuza** Posta sunucusundan'ı seçin.

**İleri'ye** tıklayın ve sihirbazdaki yönergeleri izleyin. Daha fazla bilgiye ihtiyacınız varsa **Yardım** veya **Daha Fazla Bilgi bağlantısına** tıklayın. Sihirbaz kurulumda size yol gösterir. Sonunda bağlayıcınızın doğrulandığından emin olun. Bağlayıcı doğrulamazsa, daha fazla bilgi almak için görüntülenen iletiye çift tıklayın ve sorunları çözme konusunda yardım için [bağlayıcıları doğrulama](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) konusuna bakın.



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a>7. Adım: DNS barındırma sağlayıcınızda DNS kayıtlarını güncelleştirme

DNS barındırma sağlayıcınızın web sitesinde oturum açın ve [etki alanınıza bağlanmak için DNS kayıtları ekleme](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) başlığı altında verilen yönergeleri izleyin.

**Aşağıdaki iki özel durumu yapın:**

- Yeni bir MX kaydı oluşturmayın veya mevcut MX kaydınızı değiştirmeyin.

- Önceki e-posta sağlayıcınız için zaten bir Sender Policy Framework (SPF) kaydınız varsa, Exchange Online için yeni bir SPF (TXT) kaydı oluşturmak yerine geçerli TXT kaydına "include:spf.protection.outlook.com" ekleyin.

    Örneğin, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".

    SPF kaydınız yoksa, Microsoft 365 tarafından önerilen kaydı geçerli e-posta sağlayıcınızın etki alanını içerecek şekilde değiştirin ve spf.protection.outlook.com ekleyin. Bu, her iki e-posta sisteminden giden iletileri yetkiler.

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a>8. Adım: Geçerli sağlayıcınızda e-posta iletmeyi ayarlama

Geçerli e-posta sağlayıcınızda, kullanıcı e-posta hesaplarınız için onmicrosoft.com etki alanınıza iletmeyi ayarlayın:

- Kullanıcı A posta kutusunu usera@yourcompany.onmicrosoft.com iletme

- Kullanıcı B posta kutusunu userb@yourcompany.onmicrosoft.com ilet

Bu adımı tamamladığınızda, usera@yourcompany.com ve userb@yourcompany.com gönderilen tüm e-postalar Microsoft 365'te kullanılabilir.

> [!NOTE]
> E-posta iletmeyi ayarlamaya yönelik tam adımlar için geçerli e-posta sağlayıcınıza başvurun.<br/>
> İletilerin bir kopyasını geçerli e-posta sağlayıcısında tutmanız gerekmez.<br/>
> Çoğu sağlayıcı, yanıtların özgün gönderene gitmesi için gönderenin Yanıtla adresini olduğu gibi bırakarak e-postayı iletir.

### <a name="step-9-test-mail-flow"></a>9. Adım: Posta akışını test edin

1. A Kullanıcısı kimlik bilgilerini kullanarak Outlook Web App oturum açın.

2. Şu testleri gerçekleştirin:

    - Yerel Microsoft e-postasını, örneğin Kullanıcı B'ye bir e-posta göndererek test edin. E-posta hemen teslim edilir. Bu senaryoda, Microsoft 365 posta kutusu yerel olduğundan, ileti özgün sunucunuzdaki Kullanıcı B'nin posta kutusuna yönlendirilmemiştir.

    - Mevcut e-posta sistemindeki bir kullanıcıya e-posta göndermek için örneğin Kullanıcı C'ye e-posta gönderin. E-posta, özgün posta sunucunuzdaki Kullanıcı C'nin posta kutusuna teslim edilir.

    - İletme işleminin dış hesaptan veya mevcut e-posta sistemindeki bir çalışan e-posta hesabından düzgün ayarlandığını doğrulayın. Örneğin, C kullanıcısı veya Hotmail hesabı için özgün sunucu hesabından A Kullanıcı'ya bir e-posta gönderin ve A Kullanıcısı için Microsoft 365 posta kutusuna ulaştığını doğrulayın.

### <a name="step-10-move-mailbox-contents"></a>10. Adım: Posta kutusu içeriğini taşıma

Yalnızca iki test kullanıcısını taşıdığınız ve A Kullanıcısı ile B Kullanıcısı'nın her ikisi de Outlook kullandığından, eski öğesini açarak e-postayı taşıyabilirsiniz. Yeni Outlook profilinde PST dosyası ve iletileri, takvim öğelerini, kişileri vb. kopyalama. Daha fazla bilgi için bkz. [Outlook .pst dosyasından e-postayı, kişileri ve takvimi içeri aktarma](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).

Microsoft 365 posta kutusunda uygun konumlara aktarıldıktan sonra öğelere herhangi bir cihazdan ve her yerden erişilebilir.
