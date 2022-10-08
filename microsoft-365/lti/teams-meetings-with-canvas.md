---
title: Canvas ile Microsoft Teams toplantılarını kullanma
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft Teams toplantılarını Tuval ile tümleştirme
ms.openlocfilehash: c26d094740d75156cef10ac703f116106614616c
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68210360"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Canvas ile Microsoft Teams toplantılarını kullanma

Microsoft Teams toplantıları, eğitimcilerin ve öğrencilerin Öğrenme Yönetim Sistemi (LMS) ile Teams arasında kolayca gezinmelerine yardımcı olan bir Öğrenme Araçları Birlikte Çalışabilirliği (LTI) uygulamasıdır. Kullanıcılar, kendi kurslarıyla ilişkili sınıf ekiplerine doğrudan LMS'lerinin içinden erişebilir.

## <a name="prerequisites-before-deployment"></a>Dağıtım Öncesi Önkoşullar

> [!NOTE]
> Geçerli Teams Toplantıları LTI yalnızca Tuval kullanıcılarının sınırlı kapsamdaki Microsoft Azure Active Directory (AAD) ile eşitlenmesini destekler.
>
> - Kiracınızın bir Microsoft Education lisansı olmalıdır.
> - Tuval ve Microsoft arasında kullanıcıları eşlemek için yalnızca tek bir Microsoft kiracısı kullanılabilir.
> - Tuval'in Microsoft Teams Eşitleme özelliğini Microsoft'un School Data Sync (SDS) ile aynı anda kullanmayı planlıyorsanız, SDS eşitlemenize sınıf ve sınıf listesi verilerini eklemeyin. Kullanıcılar, kuruluşlar, üst kişiler ve demografik bilgiler de dahil olmak üzere diğer tüm verileri eşitlemek için SDS kullanmaya devam edebilirsiniz.
> - **Kurs Eşitleme'yi** etkinleştirmeden Teams Toplantıları LTI'sini kullanabilirsiniz. Ancak Tüm **sınıfı ekle** seçeneğini kullanamazsınız. Katılımcıların e-posta adreslerini yazabilir veya kopyalayıp yapıştırabilir ya da toplantılara mevcut ekiplerin kanallarını ekleyebilirsiniz.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 Yönetici

Instructure Canvas içinde Microsoft Teams tümleştirmesini yönetmeden önce, Canvas yöneticisi kurulumunu tamamlamadan önce Microsoft Azure kiracınızda Canvas'ın **Microsoft-Teams-Sync-for-Canvas** Azure uygulamasının kuruluşunuzun Microsoft Office 365 yöneticisi tarafından onaylanması önemlidir.

1. Tuval'de oturum açın.

2. Genel gezinti bölmesinde **Yönetici** bağlantısını ve ardından hesabınızı seçin.

3. Yönetici gezintisinde **Ayarlar** bağlantısını ve ardından **Tümleştirmeler** sekmesini seçin.

   ![Tuval Ekipleri Eşitleme Güncelleştirildi png.](https://user-images.githubusercontent.com/87142492/128552407-78cb28e9-47cf-4026-954d-12dc3553af6f.png)

4. Microsoft kiracı adınızı, oturum açma özniteliğinizi, etki alanı sonekini ve AAD arama özniteliğinizi girin. Bu alanlar, Tuval'deki kullanıcıları Microsoft Azure Active Directory'daki kullanıcılarla eşleştirmek için kullanılır.
   - Login Özniteliği, eşleştirme için kullanılan Canvas kullanıcı özniteliğidir.
   - Sonek alanı isteğe bağlıdır ve Canvas öznitelikleri ile Microsoft AAD alanları arasında tam eşleme olmadığında bir etki alanı belirtmenize olanak tanır. Örneğin, Tuval e-postanız 'name@example.edu' ise, Microsoft AAD'deki UPN 'ad' ise, sonek alanına 'example.edu' girerek kullanıcıları eşleştirebilirsiniz.
   - Active Directory Arama Özniteliği, Microsoft tarafında Canvas özniteliklerinin eşleştirildiği alandır. UPN, birincil e-posta adresi veya e-posta diğer adı arasında seçim yapın.

5. İşlem tamamlandıktan sonra **Ayarları Güncelleştir'i** seçin.

6. Canvas'ın **Microsoft-Teams-Sync-for-Canvas Azure uygulamasına** erişimi onaylamak için **Kiracı erişimi ver** bağlantısını seçin. Microsoft Kimlik Platformu Yönetici Onay Uç Noktası'na yönlendirilirsiniz.

   ![Izin.](media/permissions.png)

7. **Kabul Et'i** seçin.

   > [!NOTE]
   > Eşitleme, LMS iş ortağı tarafından yönetilen ve Microsoft graph API'lerini kullanarak kurs düzeyinde üyeliği Teams ekibiyle eşitlemek için kullanılan bir işlevdir. Bu öncelikle eğitimcinin kurs düzeyinde doğru olarak geçiş yaptığı bir işlevdir. Daha sonra, üyelerin eklenmesi veya silinmesi için LMS tarafında yapılan tüm üyelik değişiklikleri, LMS iş ortağı tarafından uygulanan Eşitleme kullanılarak yansıtılır. Bu işlem bir Eğitimci için etkinleştirilmeden önce bile M365 eğitim enstitüsü yöneticisi, eğitimcilerinin aşağıda bulunan Eşitleme izin modalitesini kullanarak eşitlemeye erişmesine izin verir. Bu izinler, eğitimcilerin LMS kursuyla Teams Sınıf ekipleri arasında üyeliği eşitlemesini sağlamak için LMS iş ortağına verilir.

8. İki durumlu düğmeyi açarak Microsoft Teams eşitlemesini etkinleştirin.

   ![teams-sync.](media/teams-sync.png)

## <a name="canvas-admin"></a>Tuval Yönetici

Microsoft Teams LTI 1.3 Tümleştirmesi'ni ayarlayın.

Tuval Yönetici olarak ortamınıza Microsoft Teams toplantıları LTI uygulamasını eklemeniz gerekir. Uygulamanın LTI İstemci Kimliğini not edin.

- Microsoft Teams toplantıları - 170000000000703

1. Erişim **Yönetici ayarları** > **Uygulamalar**.

2. Teams LTI uygulamalarını eklemek için **+ Uygulama'ya** tıklayın.

   ![dış uygulamalar.](media/external-apps.png)

3. Yapılandırma türü için **İstemci Kimliğine Göre'yi** seçin.

   ![uygulama ekleyin.](media/add-app.png)

4. Sağlanan İstemci Kimliğini girin ve **Gönder'i** seçin.

   Onay için İstemci Kimliği için Microsoft Teams toplantıları LTI uygulama adını fark edeceksiniz.

5. **Yükle**’yi seçin.

   Microsoft Teams toplantıları LTI uygulaması dış uygulamalar listesine eklenir.

6. Tuval yönetici hesabındaki geliştirici anahtarlarına giderek, devralınmış'ı seçerek ve Microsoft Teams Toplantıları için iki durumlu düğmeyi "açarak" uygulamayı etkinleştirin.

## <a name="enable-for-canvas-courses"></a>Tuval Kursları için Etkinleştirme

LTI'yi bir kurs içinde kullanabilmek için Canvas kursunun eğitmeninin tümleştirme eşitlemesini etkinleştirmesi gerekir. İlgili Teams'in oluşturulması için her kursun bir eğitmen tarafından etkinleştirilmesi gerekir; Teams oluşturma için genel bir mekanizma yoktur. Bu, istenmeyen Teams'in oluşturulmasını önlemek için dikkatli bir şekilde tasarlanmıştır.

Her kurs için LTI'yi etkinleştirme ve tümleştirme kurulumunu tamamlama konusunda eğitmen [belgelerine](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) lütfen eğitmenlerinize başvurun.
