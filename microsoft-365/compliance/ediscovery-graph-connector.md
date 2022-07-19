---
title: Microsoft Purview eKeşif Graph bağlayıcıları
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 07/15/2022
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365solution-ediscovery
- m365initiative-compliance
- m365solution-overview
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
description: Microsoft 365 müşterileri, kurumsal arama için alınan içerikte eBulma aramaları gerçekleştirebilir.
ms.openlocfilehash: df6f948f60b74da6868f4f3877ee3a39e97c2a46
ms.sourcegitcommit: 180da7b39cfda7263a89bda0c3b93d9d6e55f3c2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66843825"
---
# <a name="use-graph-connectors-with-ediscovery-premium"></a>Graph bağlayıcılarını eBulma ile kullanma (Premium)

Microsoft 365 müşterileri, kurumsal arama için alınan içerikte eBulma aramaları gerçekleştirebilir. Bu, kuruluşların dış içerik kaynaklarına uyumluluk duruşunu geliştirmelerine yardımcı olmak için bunları Microsoft uyumluluk çözümlerinin kapsamına getirir.

Graph bağlayıcılarıyla, dış veri kaynaklarından gelen içeriğin Microsoft Purview eKeşif premium çözümde kullanılabilir olmasını sağlayabilirsiniz. Kuruluşunuz için Graph Bağlayıcıları oluşturma hakkında daha fazla bilgiyi burada bulabilirsiniz: [Microsoft Search için Microsoft Graph bağlayıcılarına genel bakış](/microsoftsearch/connectors-overview).

## <a name="add-graph-connector-as-a-data-source-within-a-case"></a>Graph Bağlayıcısı'nı bir servis talebi içinde veri kaynağı olarak ekleme

Bir kuruluş için Graph Bağlayıcıları oluşturulduktan ve eBulma etkinleştirildikten sonra, Servis Talebine Graph Bağlayıcısı veri kaynağını ekleme seçeneği Microsoft 365 olmayan konumlar altında kullanılabilir. Yalnızca oluşturulmuş ve etkinleştirilmiş bağlayıcılar, bir duruma dahil edilmesi için eBulma yöneticisi tarafından kullanılabilir.

:::image type="content" source="../media/ediscovery-graph-new.png" alt-text="Graf'ı veri kaynağı olarak seçebilirsiniz.":::

## <a name="collect-graph-connectors-content"></a>Graph Bağlayıcıları içeriğini toplama

Graph Bağlayıcıları içeriğini veri kaynağı olarak ekledikten sonra bu içerik arama ve toplama için kullanılabilir. Koleksiyon sihirbazında, Graph Bağlayıcısı içeriğini gözetimsiz bir veri kaynağı olarak seçin, yalnızca ilgilendiğiniz içeriği toplamak üzere bağlı içerikte arama yapmak için tarih aralığı, anahtar sözcükler ve daha fazlası gibi koşulları kullanın. Sihirbazın tamamlanmasının ardından arama ölçütlerinize isabet içeren içerik miktarına ilişkin tahminler alın ve koleksiyonu gözden geçirme kümesine işleyin.  

## <a name="review-content"></a>İçeriği gözden geçirme

Bir gözden geçirme kümesine toplandıktan sonra, eBulma yöneticileri içerik hakkında daha fazla bilgi edinmek için Graph Bağlayıcıları'ndan içeriği gözden geçirebilir ve bilgilerin kritik ve servis talebiyle ilgili olup olmadığını değerlendirmek için çalışabilir.  

## <a name="export-content"></a>İçeriği dışarı aktarma

Gözden geçirilirken toplanan içeriğin doğru içerik olduğu doğrulandıktan sonra, bu içerik doğrudan gözden geçirme kümesinden dışarı aktarılabilir. Dışarı aktarma seçeneklerini belirleyin ve bağlayıcı içeriğinin gözden geçirme kümesinden dışarı aktarılacağı dışarı aktarma işini gönderin.
