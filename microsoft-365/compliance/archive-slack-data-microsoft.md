---
title: Microsoft tarafından sağlanan veri bağlayıcısını kullanarak Slack eKeşif verilerini Microsoft 365'e arşivle
description: Microsoft tarafından sağlanan Slack eKeşif veri bağlayıcısını ayarlamayı ve kullanarak anlık ileti verilerini içeri aktarmayı ve arşivlemeyi öğrenin.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 07/15/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.openlocfilehash: 8c117a8410af9774adf992f3559b10cf02158c28
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68811821"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data-preview"></a>Slack eKeşif verilerini arşivleme (önizleme) için bağlayıcı ayarlama

Microsoft tarafından sağlanan Slack eKeşif veri bağlayıcısı, kuruluşunuzun Slack çalışma alanlarından Microsoft 365'e anlık ileti verilerini (iletiler, ekler, bağlantılar ve düzeltmeler gibi) içeri aktarmanıza ve arşivlenize yardımcı olur. Veri bağlayıcısı Slack API'sinden verileri çeker, e-posta iletisi biçimine dönüştürür ve ardından bu öğeleri Microsoft 365'teki kullanıcı posta kutularına aktarır. Slack verileri içeri aktarıldıktan sonra, Slack içeriğine Dava tutma, Microsoft Purview eKeşif (Premium), İletişim uyumluluğu ve bekletme ayarları gibi uyumluluk çözümleri uygulayabilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlerken Slack eKeşif veri bağlayıcısı kullanmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

Önizlemeye katılmak isterseniz lütfen dcfeedback@microsoft.com ekibine ulaşın.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Slack eKeşif verilerini arşivleme işlemine genel bakış

Aşağıdaki genel bakış, Microsoft 365'te Slack verilerini arşivleyemek için Bir Microsoft veri bağlayıcısı kullanma işlemini açıklar.

![Slack eBulma arşivleme iş akışı.](../media/SlackMSFTConnectorWorkflow.png)

1. Kuruluşunuz Slack çalışma alanını ayarlamak ve yapılandırmak için Slack ile birlikte çalışır.

2. Veri bağlayıcısı ayarlandıktan sonra, kuruluşunuzun Slack çalışma alanlarından gelen iletiler Microsoft 365'teki kullanıcı posta kutularına kopyalanır. Veri bağlayıcısı ayrıca bir sohbet iletisinin içeriğini e-posta iletisi biçimine dönüştürür.

3. Bağlayıcı, dönüştürülen sohbet iletilerini belirli kullanıcıların posta kutularına aktarır. Kullanıcı posta kutularında Gelen Kutusu klasöründe **Slack eKeşif** adlı bir alt klasör oluşturulur ve sohbet iletisi öğeleri bu klasöre aktarılır.

## <a name="before-you-set-up-a-connector"></a>Bağlayıcıyı ayarlamadan önce

- Kuruluşunuzun Slack için Enterprise Grid aboneliğine ihtiyacı vardır. Daha fazla bilgi için bkz [. Slack abonelikleri ve özellikleri](https://slack.com/intl/en-gb/help/articles/115003205446-Slack-subscriptions-and-features-).

- Veri bağlayıcısını oluşturan kullanıcıya Slack kuruluşunda **Kuruluş sahipleri** uygulama rolü atanmalıdır. Daha fazla bilgi için bkz. [Slack'teki rol türleri](https://slack.com/intl/en-gb/help/articles/360018112273-Types-of-roles-in-Slack).

- Kuruluşunuzun Slack kurumsal hesabının kullanıcı adını ve parolasını alın. Veri bağlayıcısını oluştururken bu hesapta oturum açmak için bu kimlik bilgilerini kullanırsınız. Slack kuruluşunuzda otomatik kullanıcı sağlama özelliğinin çoklu oturum açma (SSO) kullanacak şekilde yapılandırılmış olması da önerilir. [Güvenlik & Uyumluluk Merkezi'ndeki roller](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)

- Slack eKeşif bağlayıcısını oluşturan kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, Microsoft Purview uyumluluk portalı **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Microsoft 365 Defender ve [Microsoft Purview uyumluluk portallarındaki Roller ve rol grupları bölümündeki "Defender ve uyumluluk portallarındaki roller](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

## <a name="step-1-create-a-slack-ediscovery-connector"></a>1. Adım: Slack eKeşif bağlayıcısı oluşturma

1. Sol gezinti bölmesinde **Veri bağlayıcıları'na** <https://compliance.microsoft.com> gidin ve bunu seçin.

2. **Genel Bakış** sekmesinde **Filtre'yi** seçin ve **Microsoft'a göre'yi** seçin ve ardından filtreyi uygulayın.

3. **Slack eKeşif (önizleme) öğesini** seçin.

4. **Slack eKeşif (önizleme)** ürün açıklaması sayfasında **Bağlayıcı ekle'yi** seçin.

5. **Hizmet koşulları** sihirbazı sayfasında **Kabul Et'i** seçin.

6. Bağlayıcıyı tanımlayan benzersiz bir ad girin ve **İleri'yi** seçin. Girdiğiniz ad, bağlayıcıyı oluşturduktan sonra **Veri bağlayıcıları** sayfasında tanımlar.

## <a name="step-2-sign-into-your-slack-organization"></a>2. Adım: Slack kuruluşunuzda oturum açın

1. **Kuruluşunuzun Slack** çalışma alanında oturum açmak için Slack'te oturum açma sihirbazı sayfasında **Slack'te oturum açın'ı** seçin.

2. Slack **Çalışma alanınızda oturum açın** sayfasında, verileri arşivlemesini istediğiniz çalışma alanının adını yazın ve **Devam'ı** seçin.

   Slack çalışma alanınızın adını ve oturum açma istemini içeren bir sayfa görüntülenir.

3. **Kuruluş Sahiplerinin de burada oturum açabileceği dizesindeki** bağlantıyı seçin.

4. Çalışma alanı oturum açma sayfasında, kuruluşunuzun Slack kurumsal hesabının e-posta adresini ve parolasını girin ve oturum **aç'ı** seçin.

   Başarıyla oturum açtığınızda, bağlayıcı uygulaması tarafından Slack kuruluşunuza erişim izni isteyen bir sayfa görüntülenir.

5. Uygulamanın kuruluşunuzu yönetmesine izin vermek için **İzin Ver'i** seçin.

   **İzin Ver'i** seçtikten sonra Slack sayfası kapatılır ve bağlayıcı sihirbazındaki **Slack eKeşif kullanıcılarını Microsoft 365 kullanıcıları ile eşle** sayfası görüntülenir.

## <a name="step-3-specify-the-users-to-import-data-for"></a>3. Adım: Verileri içeri aktaracak kullanıcıları belirtin

Slack eBulma verilerini içeri aktarmak istediğiniz kullanıcıları belirtmek için aşağıdaki seçeneklerden birini belirleyin.

- **Kuruluşunuzdaki tüm kullanıcılar**. Tüm kullanıcılar için verileri içeri aktarmak için bu seçeneği belirleyin.

- **Yalnızca Dava tutan kullanıcılar**. Yalnızca posta kutuları Dava tutmada yer alan kullanıcılar için verileri içeri aktarmak için bu seçeneği belirleyin. Bu seçenek, LitigationHoldEnabled özelliği True olarak ayarlanmış kullanıcı posta kutularına veri aktarır. Daha fazla bilgi için bkz. [Dava tutma oluşturma](create-a-litigation-hold.md).

## <a name="step-4-map-users-and-select-data-types-to-import"></a>4. Adım: Kullanıcıları eşleme ve içeri aktaracak veri türlerini seçme

1. Slack kullanıcılarını Microsoft 365 posta kutularına eşlemek için aşağıdaki seçeneklerden birini veya her ikisini yapılandırın.

   - **Otomatik kullanıcı eşlemesi**. Slack kullanıcı adlarını Microsoft 365 posta kutularına otomatik olarak eşlemek için bu seçeneği belirleyin. Bağlayıcı, her Slack iletisinin veya öğesinin içerdiği *Email* özelliğinin değerini kullanarak yapar. Bu özellik, iletinin her katılımcısının e-posta adresiyle doldurulur. Bağlayıcı e-posta adreslerini ilgili Microsoft 365 kullanıcılarıyla ilişkilendirebiliyorsa, öğe bu kullanıcıların Microsoft 365 posta kutusuna aktarılır. Bu seçeneği kullanmak için Slack kuruluşunuz için SSO'nun yapılandırılmış olması gerekir.

   - **Özel kullanıcı eşlemesi**. Ayrıca, otomatik kullanıcı eşlemesi yerine (veya buna ek olarak) özel kullanıcı eşlemesi kullanma seçeneğiniz de vardır. Bu seçenekle, kullanıcıların Slack üye kimliğini Microsoft 365 e-posta adreslerine eşleyen bir CSV dosyası oluşturup karşıya yüklemeniz gerekir. Bunu yapmak için **CSV eşleme şablonunu indir'i** seçin, CSV dosyasını kuruluşunuzdaki tüm kullanıcılar için Slack üye kimliği ve Microsoft 365 e-posta adresiyle doldurun, ardından CSV dosyasını seçip sihirbaza yükleyin. CSV dosyasındaki sütun başlıklarını değiştirmediğinizden emin olun. AŞAĞıDA CSV eşleme dosyasının bir örneği verilmişti:

     |**ExternalUserId**  | **O365UserMailbox**   |
     |:-------------------|:-----------------------|
     | U01MDTF0QV6        | alexjones@contoso.onmicrosoft.com |
     | U02MDTF1RW7| pilarp@contoso.onmicrosoft.com|
     | U03MDTF2SX8 | sarad@contoso.onmicrosoft.com|
     |||

   > [!TIP]
   > Kullanıcılar için üye kimlikleri,... Kullanıcının profilindeki Diğer düğmesi ve ardından **Üye kimliğini kopyala'yı** seçin. Alternatif olarak, Slack ekibinin tüm üyelerine ait kimlikleri almak için Slack [users.list API yöntemini](https://api.slack.com/methods/users.list) kullanabilirsiniz.

   Otomatik kullanıcı eşlemesini etkinleştirir ve özel bir eşleme dosyası sağlarsanız, bağlayıcı önce Slack kullanıcısını bir Microsoft 365 posta kutusuna eşlemek için özel eşleme dosyasına bakar. Bağlayıcı Slack kullanıcısına karşılık gelen geçerli bir Microsoft 365 kullanıcısı bulamazsa, bağlayıcı Slack öğesinin *Email* özelliğini kullanır. Bağlayıcı, özel eşleme dosyasında veya ileti öğesinin *Email* özelliğinde geçerli bir Microsoft 365 kullanıcısı bulamazsa, öğe içeri aktarılamaz.

2. **İçeri aktaracak veri türlerini seçin** sihirbazı sayfasında, içeri aktarmak istediğiniz Slack veri türlerini seçin. Tüm kanallardan iletileri içeri aktarmak istiyorsanız tüm seçenekleri belirleyin. Aksi takdirde, yalnızca içeri aktarmak istediğiniz veri türlerini seçin.

     Slack iletilerine ek olarak, Microsoft 365'e aktarılacak diğer Slack içeriği türlerini de belirtebilirsiniz. 

3. İçeri aktaracak veri türlerini yapılandırdıktan sonra **İleri'yi** seçin, bağlayıcı ayarlarını gözden geçirin ve **son'u** seçerek bağlayıcıyı oluşturun.

## <a name="step-5-monitor-the-slack-ediscovery-connector"></a>5. Adım: Slack eKeşif bağlayıcısını izleme

Slack eKeşif bağlayıcısını oluşturduktan sonra bağlayıcının durumunu uyumluluk portalında görüntüleyebilirsiniz.

1. Sol gezinti **bölmesinden Veri bağlayıcıları'na** [https://compliance.microsoft.com](https://compliance.microsoft.com/) gidin ve bunu seçin.

2. **Bağlayıcılar** sekmesini seçin ve ardından **Slack eKeşif** bağlayıcısını seçerek bağlayıcının özelliklerini ve bilgilerini içeren açılır sayfayı görüntüleyin.

3. Bağlayıcının durum günlüğünü açmak (veya kaydetmek) için **Kaynakla bağlayıcı durumu** altında **Günlüğü indir** bağlantısını seçin. Bu günlük, Microsoft buluta aktarılan veriler hakkında bilgi içerir. Daha fazla bilgi için bkz. [Veri bağlayıcıları için yönetici günlüklerini görüntüleme](data-connector-admin-logs.md).

## <a name="known-issues"></a>Bilinen sorunlar

- Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.
