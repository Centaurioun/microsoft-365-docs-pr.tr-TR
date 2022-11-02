---
title: MS SQL Veritabanı verilerini arşivleye bağlayıcı ayarlama
description: Yöneticiler, MS SQL Veritabanı verilerini içeri aktarmak ve arşivlemek için bir bağlayıcı ayarlayabilir. Bu bağlayıcı, Microsoft 365'teki üçüncü taraf veri kaynaklarından verileri arşivlenizi sağlar. Bu verileri arşivledikten sonra, üçüncü taraf verilerini yönetmek için yasal tutma, içerik arama ve bekletme ilkeleri gibi uyumluluk özelliklerini kullanabilirsiniz.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 04/06/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.openlocfilehash: dbf45099dd936af3312be2c0be063fde122cc305
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68812283"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>MS SQL Veritabanı verilerini arşivleye bağlayıcı ayarlama

MS SQL Veritabanı'dan Microsoft 365 kuruluşunuzdaki kullanıcı posta kutularına veri içeri aktarmak ve arşiv etmek için Microsoft Purview uyumluluk portalı bir Veritas bağlayıcısı kullanın. Veritas, bir XML yapılandırma dosyası kullanarak veritabanındaki öğeleri yakalamak ve bu öğeleri Microsoft 365'e aktarmak için yapılandırılmış bir MS SQL Veritabanı İçeri Aktarıcı bağlayıcısı sağlar. Bağlayıcı, MS SQL Veritabanı içeriği e-posta iletisi biçimine dönüştürür ve ardından bu öğeleri Microsoft 365'teki kullanıcı posta kutularına aktarır.

MS SQL Veritabanı içeriği kullanıcı posta kutularında depolandıktan sonra, Dava Tutma, eBulma, bekletme ilkeleri ve bekletme etiketleri gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlerken MS SQL Veritabanı bağlayıcısı kullanmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-the-ms-sql-data"></a>MS SQL verilerini arşivleme genel bakış

Aşağıdaki genel bakış, Microsoft 365'te MS SQL verilerini arşivlerken bağlayıcı kullanma işlemini açıklar.

![MS SQL verileri için iş akışı arşivleme.](../media/MSSQLDatabaseConnectorWorkflow.png)

1. Kuruluşunuz bir MS SQL Veritabanı sitesi ayarlamak ve yapılandırmak için bir MS SQL Veritabanı sağlayıcısıyla çalışır.

2. 24 saatte bir, MS SQL Veritabanı öğeleri Veritas Merge1 sitesine kopyalanır. Bağlayıcı ayrıca bu içeriği e-posta iletisi biçimine dönüştürür.

3. Uyumluluk portalında oluşturduğunuz MS SQL Veritabanı Importer bağlayıcısı her gün Veritas Merge1 sitesine bağlanır ve iletileri Microsoft bulutunda güvenli bir Azure Depolama konumuna aktarır.

4. Bağlayıcı, [3. Adımda](#step-3-map-users-and-complete-the-connector-setup) açıklandığı gibi otomatik kullanıcı eşlemesinin Email özelliğinin değerini kullanarak dönüştürülen MS *SQL Veritabanı* öğelerini belirli kullanıcıların posta kutularına aktarır. Kullanıcı posta kutularında **MS SQL Veritabanı İçeri Aktarıcı** adlı Gelen Kutusu klasöründe bir alt klasör oluşturulur ve öğeler bu klasöre aktarılır. Bağlayıcı, *Email* özelliğinin değerini kullanarak öğelerin hangi posta kutusuna aktarılacağını belirler. MS SQL Veritabanı her öğe, öğenin her katılımcısının e-posta adresiyle doldurulan bu özelliği içerir.

## <a name="before-you-begin"></a>Başlamadan önce

- Microsoft bağlayıcıları için bir Veritas Merge1 hesabı oluşturun. Hesap oluşturmak için [Veritas Müşteri Desteği'ne](https://www.veritas.com/content/support/) başvurun. 1. Adımda bağlayıcıyı oluştururken bu hesapta oturum açmanız gerekir.

- 1. Adımda MS SQL Veritabanı İçeri Aktarıcı bağlayıcısını oluşturan (ve 3. Adımda tamamlayan) kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Microsoft 365 Defender ve [Microsoft Purview uyumluluk portallarındaki Roller ve rol grupları bölümündeki "Defender ve uyumluluk portallarındaki roller](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu Veritas veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında genel önizleme aşamasındadır. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>1. Adım: MS SQL Veritabanı İçeri Aktarıcı bağlayıcısını ayarlama

İlk adım, uyumluluk portalındaki **Veri Bağlayıcıları** sayfasına erişmek ve MS SQL Veritabanı için bir bağlayıcı oluşturmaktır.

1. **Veri bağlayıcıları** > **MS SQL Veritabanı İçeri Aktarıcı'ya**[https://compliance.microsoft.com](https://compliance.microsoft.com) gidin ve bunu seçin.

2. **MS SQL Veritabanı Importer** ürün açıklaması sayfasında **Yeni bağlayıcı ekle'yi** seçin.

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. Bağlayıcıyı tanımlayan benzersiz bir ad girin ve **İleri'yi** seçin.

5. Bağlayıcıyı yapılandırmak için Merge1 hesabınızda oturum açın.

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>2. Adım: Veritas Merge1 sitesinde MS SQL Veritabanı Importer bağlayıcısını yapılandırma

İkinci adım, Merge1 sitesinde MS SQL Veritabanı Importer bağlayıcısını yapılandırmaktır. MS SQL Veritabanı İçeri Aktarıcısını yapılandırma hakkında bilgi için bkz. [Birleştirme1 Üçüncü Taraf Bağlayıcıları Kullanıcı Kılavuzu](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).

**Kaydet & Son'u** seçtikten sonra, uyumluluk portalındaki bağlayıcı sihirbazındaki **Kullanıcı eşleme** sayfası görüntülenir.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3. Adım: Kullanıcıları eşleme ve bağlayıcı kurulumunu tamamlama

Kullanıcıları eşlemek ve bağlayıcı kurulumunu tamamlamak için şu adımları izleyin:

1. **MS SQL Veritabanı Importer kullanıcılarını Microsoft 365 kullanıcıları ile eşle** sayfasında otomatik kullanıcı eşlemesini etkinleştirin. MS SQL Veritabanı öğeleri, kuruluşunuzdaki kullanıcıların e-posta adreslerini içeren *Email* adlı bir özellik içerir. Bağlayıcı bu adresi bir Microsoft 365 kullanıcısı ile ilişkilendirebiliyorsa, öğeler söz konusu kullanıcının posta kutusuna aktarılır.

2. **İleri'yi** seçin, ayarlarınızı gözden geçirin ve yeni bağlayıcının içeri aktarma işleminin ilerleme durumunu görmek için **Veri bağlayıcıları** sayfasına gidin.

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>4. Adım: MS SQL Veritabanı İçeri Aktarıcı bağlayıcısını izleme

MS SQL Veritabanı Importer bağlayıcısını oluşturduktan sonra bağlayıcının durumunu uyumluluk portalında görüntüleyebilirsiniz.

1. Sol gezinti **bölmesinden Veri bağlayıcıları'na** <https://compliance.microsoft.com/> gidin ve bunu seçin.

2. **Bağlayıcılar** sekmesini seçin ve ardından BAĞLAYıCının özelliklerini ve bilgilerini içeren açılır sayfayı görüntülemek için **MS SQL Veritabanı** **İçeri Aktarıcı** bağlayıcısını seçin.

3. Bağlayıcının durum günlüğünü açmak (veya kaydetmek) için **Kaynakla bağlayıcı durumu** altında **Günlüğü indir** bağlantısını seçin. Bu günlük, Microsoft buluta aktarılan veriler hakkında bilgi içerir. Daha fazla bilgi için bkz. [Veri bağlayıcıları için yönetici günlüklerini görüntüleme](data-connector-admin-logs.md).

## <a name="known-issues"></a>Bilinen sorunlar

- Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.
