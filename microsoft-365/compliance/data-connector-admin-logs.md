---
title: Verileri içeri aktarmayla ilgili durumu görüntülemek için veri bağlayıcıları için yönetici günlüğünü kullanma
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Bağlayıcı tarafından içeri aktarılan verilere ilişkin durum bilgilerini almak için veri bağlayıcılarının yönetici günlüklerine erişmeyi ve bu günlükleri görüntülemeyi öğrenin.
ms.openlocfilehash: de8b1de56b5e44ad199db942c3d385dcc05e1160
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2022
ms.locfileid: "66861591"
---
# <a name="view-admin-logs-for-data-connectors"></a>Veri bağlayıcıları için yönetici günlüklerini görüntüleme

Microsoft dışı verileri Microsoft Purview'a aktarmak için bir veri bağlayıcısı oluşturduktan sonra, veri bağlayıcısının yönetici günlüklerini indirerek bağlayıcının günlük içeri aktarma durumunu izleyebilirsiniz.

> [!IMPORTANT]
> Kuruluşunuzun yönetici günlüğünü görüntüleyebilmesi için denetim günlüğünün etkinleştirilmesi gerekir. Microsoft 365 ve Office 365 kuruluşları için varsayılan olarak etkindir, ancak kuruluşunuzun denetim durumunu doğrulamanızı kesinlikle öneririz. Denetim durumunu denetleme yönergeleri için lütfen buraya tıklayın. Denetimi el ile açma yönergeleri için lütfen buraya tıklayın. Denetim açıldıktan sonra içeri aktarma olaylarının günlüğe kaydedilmesi 48 saat kadar sürebilir. Bağlayıcı yapılandırılmadan önce denetimi etkinleştirmenizi kesinlikle öneririz. Bağlayıcı yapılandırıldıktan sonra, içeri aktarma durumu özetini içeren günlüklerin oluşturulması 72 saat kadar sürebilir.

## <a name="before-you-view-admin-logs"></a>Yönetici günlüklerini görüntülemeden önce

- Kuruluşunuzun kuruluşunuz için yönetici günlüğü oluşturması ve görüntülemesi için denetimin etkinleştirilmesi gerekir. Denetim, Microsoft Purview'da varsayılan olarak etkindir. Ancak kuruluşunuzun denetim durumunu doğrulamanızı öneririz. Yönergeler için bkz. [Kuruluşunuzun denetim durumunu doğrulama](turn-audit-log-search-on-or-off.md#verify-the-auditing-status-for-your-organization). Kuruluşunuzda denetimi etkinleştirmeniz gerekiyorsa bkz. [Denetimi açma](turn-audit-log-search-on-or-off.md#turn-on-auditing).

- Denetim açıldıktan sonra veri bağlayıcıları için yönetici günlüklerinin oluşturulması 48 saat kadar sürebilir. Veri bağlayıcıları oluşturmadan önce denetimi etkinleştirmenizi öneririz.

- Veri bağlayıcısı oluşturulduktan sonra, içeri aktarma durumu özetini içeren yönetici günlüklerinin oluşturulması 72 saat kadar sürebilir.

- Yönetici günlükleri önceki yedi gün için kullanılabilir.

## <a name="download-admin-logs-for-data-connectors"></a>Veri bağlayıcıları için yönetici günlüklerini indirme

1. **Veri bağlayıcıları'na**<https://compliance.microsoft.com/> gidin ve tıklayın.

2. **Bağlayıcılarım** sekmesine tıklayın ve veri bağlayıcısı hakkındaki bilgileri ve özellikleri içeren açılır sayfayı görüntülemek için bir veri bağlayıcısı seçin.

3. **Yönetici günlükler'in** altında **Günlüğü indir** bağlantısına tıklayarak bir yönetici günlüğü açın.

   ![Veri bağlayıcısı açılır sayfasında görüntülenen yönetici günlükleri.](..\media\Data-connector-admin-logs1.png)

4. Yönetici günlüğünde aşağıdaki içeri aktarma durumu bilgilerini görüntüleyin:

    - **İçeri aktarma tamamlanma süresi**: Bağlayıcı veri kaynağından içeri aktarmayı tamamladığında ve aşağıdaki olayların tümü içeri aktarma işlemine göre hesaplandığında/güncelleştirildiğinde zaman damgası (UTC olarak).
    - **Kaynaktan edinilebilen öğeler**: Bağlayıcı tarafından veri kaynağından indirilen öğelerin sayısı.
    - **İçeri aktarma için kullanılabilen öğeler**: Bağlayıcı tarafından dışarı aktarma işleminden sonra içeri aktarılabilmesi için kullanılabilecek öğelerin sayısı. Fanout, tüm ilişkili katılımcılara (gönderen, alıcı vb.) ileti yazma eylemini temsil eder.
    - **Başarıyla içeri aktarılan öğeler**: Bağlayıcı tarafından kullanıcı posta kutularına başarıyla içeri aktarılan öğelerin sayısı.
    - **Kısmen içeri aktarılan öğeler**: Bağlayıcı tarafından kullanıcı posta kutularına başarıyla aktarılmış ancak ekleri bırakılan öğelerin sayısı.
    - **Atlanan öğeler**: Yinelenen öğeler olması nedeniyle fanout sonrasında kullanıcı posta kutularına aktarılmaktan atlanan öğelerin sayısı.
    - **Öğeler başarısız oldu**: Hatalardan (kullanıcı eşlemesi, öğe boyutu aşıldı vb.) dolayı kullanıcı posta kutularına aktarılamayan öğelerin sayısı. Olay, kullanıcı eşleme hataları için kullanıcı başına bir kez günlüğe kaydedilir.

    > [!NOTE]
    > İçeri aktarma için kullanılabilen öğeler, başarıyla içeri aktarılan, kısmen içeri aktarılan, atlanan ve başarısız olan öğelerin toplamı olmalıdır.

    - Başarısız öğe ayrıntılarının özeti:
      - **Öğe kimliği** – öğenin benzersiz tanımlayıcısı
      - **Kaynak Kullanıcı Kimliği** – kaynak uygulamada kullanıcı kimliği
      - **M365 Kullanıcı Kimliği** – M365'te Kullanıcı Asıl Adı
      - **Hata Nedeni** – bağlayıcının öğeyi içeri aktaramamasının nedenini gösterir

      Belirli bir günde alınan öğe yoksa, aşağıdaki ileti günlük dosyasında bulunur:

      *Aa/gg/yyyy* tarihinde hiçbir öğe alınmadı.

> [!NOTE]
> Belirli bir günde içeri aktarılan öğe yoksa, yönetici günlüğü aşağıdaki iletiyi içerir: `No items ingested on mm/dd/yyyy.`
