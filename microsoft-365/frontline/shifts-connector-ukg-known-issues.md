---
title: UKG Boyutları için Team Shifts bağlayıcısı bilinen sorunlar
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Vardiyaları UKG Boyutları ile tümleştirmek için UKG Boyutları için Team Shifts bağlayıcısını kullanırken karşılaşılan bilinen sorunları listeler.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 10c1f0aff03fb302cc12cae78cf003d2f337a01a
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68234565"
---
# <a name="known-issues-team-shifts-connector-for-ukg-dimensions"></a>Bilinen sorunlar: UKG Boyutları için Ekip Vardiyaları bağlayıcısı

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Bu makalede [UKG Boyutları için Microsoft Teams Vardiyaları bağlayıcısı ile](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions) ilgili bilinen sorunlar listelenmiştir.

## <a name="you-can-map-an-instance-to-more-than-one-team-using-powershell-or-microsoft-graph"></a>PowerShell veya Microsoft Graph kullanarak bir örneği birden fazla ekiple eşleyebilirsiniz

UkG Dimensions örneği, bir bağlantıda herhangi bir zamanda yalnızca bir takımla eşlenmelidir.

Bununla birlikte, bağlantı kurmak için PowerShell veya Microsoft Graph kullandığınızda, bir örneği birden fazla ekiple eşlemek mümkündür. Eşitleme sorunlarına ve beklenmeyen davranışlara neden olabileceğinden bir örneği birden çok ekiple eşlemekten kaçınmanızı öneririz.

## <a name="frontline-managers-can-select-a-time-zone-for-a-schedule-in-shifts-thats-different-from-the-time-zone-thats-set-in-ukg-dimensions"></a>Ön cephe yöneticileri, Vardiyalar'da UKG Dimensions'ta ayarlanan saat diliminden farklı bir zamanlama için saat dilimi seçebilir

Vardiyalardaki zamanlamaların saat dilimi ayarı UKG Boyutlarından eşitlenir. Ancak ön cephe yöneticilerinin Vardiyalar'daki bir zamanlamanın saat dilimini UKG Dimensions'ta yapılandırılandan farklı bir saat dilimine değiştirmesi mümkündür. Bunun yapılması eşitleme sorunlarına ve beklenmeyen davranışlara neden olabilir.

Bu sorunu geçici olarak çözmek için saat dilimi ayarını olduğu gibi tutun.

## <a name="nothing-happens-when-users-select-the-start-a-break-and-end-break-buttons-in-shifts-to-start-or-end-a-break"></a>Kullanıcılar bir kesmeyi başlatmak veya sonlandırmak için Vardiyalar'daki "Kesmeyi başlat" ve "Kesmeyi sonlandır" düğmelerini seçtiğinde hiçbir şey olmaz

UkG Dimensions ile tümleştirmede zaman saati özelliğinin başlangıç ve bitiş sonu özelliği desteklenmez. Düğmeler Vardiyalar'da görüntülense bile kullanıcılar çıkış yapamaz veya molaya giriş yapamaz.

## <a name="a-user-cant-perform-some-actions-in-shifts-in-the-teams-web-app-after-signing-in-with-a-different-account"></a>Kullanıcı, farklı bir hesapla oturum açtıktan sonra Teams web uygulamasındaKi Vardiyalar'da bazı eylemleri gerçekleştiremez

Teams'de birden çok hesabı olan bir kullanıcı, UkG Boyutları'nda çoklu oturum açma (SSO) gerektiren ve aynı tarayıcıdaki Teams web uygulamasındaki hesapları değiştiren eylemleri Vardiyalar'da gerçekleştirirse bu sorun oluşabilir.

Örneğin, bir kullanıcı Teams'de oturum açar, bir izin isteğini onaylar ve ardından oturumu kapatır. Kullanıcı daha sonra farklı bir hesap kullanarak Teams'de oturum açar ve Vardiyalar'da UKG Boyutlarında SSO gerektiren başka bir eylem gerçekleştirmeye çalışır.

Bu senaryoda, kullanıcının bir hesapta Teams ve Vardiyalar'da oturum açtığı, diğer hesaptaki UKG Dimensions'ta oturum açtığı bir önbelleğe alma sorunu oluşur.

Bu sorunu geçici olarak çözmek için aşağıdakilerden birini yapın:

- Tarayıcıdaki mykronos.com sitesi için tanımlama bilgilerini ve site verilerini temizleyin. Daha fazla bilgi için bkz. [Microsoft Edge'de tanımlama bilgilerini silme](https://support.microsoft.com/microsoft-edge/delete-cookies-in-microsoft-edge-63947406-40ac-c3b8-57b9-2a946a29ae09) veya [Chrome'da tanımlama bilgilerini temizleme, etkinleştirme ve yönetme](https://support.google.com/chrome/answer/95647).
- Teams web uygulamasını Microsoft Edge'deki bir InPrivate penceresinde veya Google Chrome'da Gizli modda kullanın.

## <a name="related-articles"></a>İlgili makaleler

- [Vardiya bağlayıcıları](shifts-connectors.md)
- [Shifts bağlayıcı sihirbazını kullanarak Shifts'i UKG Boyutlarına bağlama](shifts-connector-wizard-ukg.md)
- [Vardiyaları UKG Boyutlarına bağlamak için PowerShell kullanma](shifts-connector-ukg-powershell-setup.md)
- [UKG Boyutlarına Vardiyalar bağlantınızı yönetmek için Microsoft 365 yönetim merkezi kullanın](shifts-connector-ukg-admin-center-manage.md)
- [PowerShell kullanarak UkG Boyutlarına Vardiyalar bağlantınızı yönetme](shifts-connector-ukg-powershell-manage.md)
- [Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)