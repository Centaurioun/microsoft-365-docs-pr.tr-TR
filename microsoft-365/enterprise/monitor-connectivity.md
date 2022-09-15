---
title: Microsoft 365 bağlantısını izleyin
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: Bu makalede, Microsoft 365 bağlantısını izlemek ve sürdürmek için kullanabileceğiniz araçlar ve teknikler hakkında bilgi edineceksiniz.
ms.openlocfilehash: db2997db354e1650882a63c7198ea248e4e90c1c
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67702038"
---
# <a name="monitor-microsoft-365-connectivity"></a>Microsoft 365 bağlantısını izleyin

Microsoft 365'i dağıttıktan sonra, aşağıdaki araç ve tekniklerden bazılarını kullanarak Microsoft 365 bağlantısını koruyabilirsiniz. Resmi [Hizmet Durumu ve Süreklilik](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) yönergelerinin yanı sıra [Microsoft 365'i yavaş bir ağda kullanmaya yönelik en iyi yöntemlerimizi](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) anlamak isteyeceksiniz. Ayrıca [Microsoft 365 yönetici uygulamasını](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) almak ve [İş için Microsoft 365 - yardım Yönetici](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791) yer işareti eklemek isteyeceksiniz.
  
## <a name="monitoring-microsoft-365-connectivity"></a>Microsoft 365 Bağlantısını İzleme

|İzleme türü |Açıklama |
|:-----|:-----|
|**Yeni Microsoft 365 uç noktalarıyla ilgili bildirim alma** <br/> |[Microsoft 365 uç noktalarını yönetiyorsanız, yeni uç noktaları](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) yayımladığımızda bildirim almak istersiniz. Sık kullandığınız RSS okuyucusunu kullanarak RSS akışımıza abone olabilirsiniz. [Outlook aracılığıyla abone](https://go.microsoft.com/fwlink/p/?LinkId=532416) olma veya [RSS akışı güncelleştirmelerinin size e-posta ile göndermesini sağlamak için aşağıdaki yöntemleri kullanabilirsiniz](https://go.microsoft.com/fwlink/p/?LinkId=532417).  <br/> |
|**Microsoft 365'i izlemek için System Center'ı kullanma** <br/> |Microsoft System Center kullanıyorsanız, [Microsoft 365'i izlemeye hemen başlamak için Microsoft 365 için Microsoft System Center Operations Manager Yönetim Paketi'ni](https://www.microsoft.com/download/details.aspx?id=103379) indirebilirsiniz. Daha ayrıntılı yönergeler için lütfen yönetim paketi işlemleri kılavuzuna bakın. <br/> |
|**Azure ExpressRoute'un durumunu izleme** <br/> |Microsoft 365 için Azure ExpressRoute'u kullanarak Microsoft 365'e bağlanıyorsanız hem Microsoft 365 Hizmet Durumu Panosu'nu hem de Azure [Kaynak durumu ile sorun giderme süresini azaltmayı](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) kullandığınızdan emin olmak istersiniz <br/> |
|**AD FS ile Azure AD Connect Health kullanma** <br/> |Microsoft 365 ile Tek Sign-On için AD FS kullanıyorsanız, [AD FS altyapınızı izlemek için Azure AD Connect Health kullanmaya](/azure/active-directory/hybrid/how-to-connect-health-adfs) başlamak istersiniz.  <br/> |
|**Microsoft 365'i program aracılığıyla izleme** <br/> |[Microsoft 365 Yönetim API'siyle ilgili kılavuzumuza](/office/office-365-management-api/office-365-management-apis-overview) bakın.  <br/> |

İşte geri dönmek için kullanabileceğiniz kısa bir bağlantı: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>İlgili konular

[Microsoft 365 Kurumsal hizmetlerini ve uygulamalarını yapılandırma](configure-services-and-applications.md)
  
[Kuruluşunuzu Microsoft 365 Kurumsal için hazırlama](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365 için ağ planlama ve performans ayarlama](network-planning-and-performance.md)
  
[Şirket içi ortamlarla Microsoft 365 tümleştirmesi](microsoft-365-integration.md)
  
[Microsoft 365 uç noktalarını yönetme](managing-office-365-endpoints.md)
