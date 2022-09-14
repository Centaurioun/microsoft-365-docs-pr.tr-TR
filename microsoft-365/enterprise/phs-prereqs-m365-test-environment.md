---
title: Microsoft 365 test ortamınızda parola karması eşitlemesi için kimlik ve cihaz erişimi önkoşulları
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Parola karması eşitleme kimlik doğrulaması önkoşullarıyla kimlik ve cihaz erişimini test etmek için bir Microsoft 365 ortamı oluşturun.
ms.openlocfilehash: 81ce62843c36a1df61ca7f86e2b22257c2631b68
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67672677"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a>Microsoft 365 test ortamınızda parola karması eşitlemesi için kimlik ve cihaz erişimi önkoşulları

*Bu Test Laboratuvarı Kılavuzu yalnızca kurumsal test ortamları için Microsoft 365 için kullanılabilir.*

[Kimlik ve cihaz erişim yapılandırmaları](../security/office-365-security/microsoft-365-policies-configurations.md), Azure Active Directory (Azure AD) ile tümleştirilen kuruluş için Microsoft 365'teki tüm hizmetlere erişimi korumaya yönelik bir dizi yapılandırma ve koşullu erişim ilkesidir.

Bu makalede, kimlik ve cihaz erişimi için [parola karması eşitleme kimlik doğrulaması önkoşul yapılandırması ile karmanın](../security/office-365-security/identity-access-prerequisites.md#prerequisites) gereksinimlerini karşılayan bir Microsoft 365 test ortamının nasıl yapılandırıldığı açıklanır.

Bu test ortamını ayarlamak için on aşama vardır:

1. Parola karması eşitleme testi ortamı ile sanal kuruluş oluşturma
2. Sorunsuz Azure AD çoklu oturum açmayı yapılandırma
3. Adlandırılmış konumları yapılandırma
4. Parola geri yazmayı yapılandırma
5. Tüm kullanıcı hesapları için self servis parola sıfırlamayı yapılandırma
6. Tüm kullanıcı hesapları için çok faktörlü kimlik doğrulamasını yapılandırma
7. Etki alanına katılmış Windows bilgisayarlarının otomatik cihaz kaydını etkinleştirme
8. parola korumasını Azure AD yapılandırma 
9. Azure AD Kimlik Korumasını etkinleştirme
10. Exchange Online ve Skype Kurumsal Online için modern kimlik doğrulamasını etkinleştirme

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a>1. Aşama: Parola karması eşitleme microsoft 365 test ortamı ile sanal kuruluşunuzu oluşturma

[Parola karması eşitleme](password-hash-sync-m365-ent-test-environment.md) Test Laboratuvarı Kılavuzu'ndaki yönergeleri izleyin.
Sonuçta elde edilen yapılandırma aşağıdadır.

![Parola karması eşitleme testi ortamı ile sanal kuruluş.](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>2. Aşama: Sorunsuz Azure AD çoklu oturum açmayı yapılandırma

[Azure AD Sorunsuz Çoklu Oturum Açma Test Laboratuvarı Kılavuzu'nun 2. Aşamasındaki](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) yönergeleri izleyin.

## <a name="phase-3-configure-named-locations"></a>3. Aşama: Adlandırılmış konumları yapılandırma

İlk olarak, kuruluşunuz tarafından kullanılan genel IP adreslerini veya adres aralıklarını belirleyin.

Ardından, adresleri veya adres aralıklarını [adlandırılmış konumlar olarak eklemek için Azure Active Directory'de adlandırılmış konumları yapılandırma](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) başlığı altında verilen yönergeleri izleyin. 

## <a name="phase-4-configure-password-writeback"></a>4. Aşama: Parola geri yazmayı yapılandırma

[Parola geri yazma Test Laboratuvarı Kılavuzu'nun 2. Aşamasındaki](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) yönergeleri izleyin.

## <a name="phase-5-configure-self-service-password-reset"></a>5. Aşama: Self servis parola sıfırlamayı yapılandırma

[Parola sıfırlama Test Laboratuvarı Kılavuzu'nun 3. Aşamasındaki](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) yönergeleri izleyin. 

Belirli bir Azure AD grubundaki hesaplar için parola sıfırlamayı etkinleştirirken bu hesapları **Parola sıfırlama** grubuna ekleyin:

- Kullanıcı 2
- Kullanıcı 3
- Kullanıcı 4
- Kullanıcı 5

Parola sıfırlamayı yalnızca Kullanıcı 2 hesabı için test edin.

## <a name="phase-6-configure-multi-factor-authentication"></a>6. Aşama: Çok faktörlü kimlik doğrulamasını yapılandırma

Aşağıdaki kullanıcı hesapları için [çok faktörlü kimlik doğrulaması Test Laboratuvarı Kılavuzu'nun 2. Aşamasındaki](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) yönergeleri izleyin:

- Kullanıcı 2
- Kullanıcı 3
- Kullanıcı 4
- Kullanıcı 5

Çok faktörlü kimlik doğrulamasını yalnızca Kullanıcı 2 hesabı için test edin.

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>7. Aşama: Etki alanına katılmış Windows bilgisayarlarının otomatik cihaz kaydını etkinleştirme 

Etki alanına katılmış Windows bilgisayarlarının otomatik cihaz kaydını etkinleştirmek için [bu yönergeleri](/azure/active-directory/devices/hybrid-azuread-join-plan) izleyin.

## <a name="phase-8-configure-azure-ad-password-protection"></a>8. Aşama: parola korumasını Azure AD yapılandırma 

Bilinen zayıf parolaları ve bunların değişkenlerini engellemek için [bu yönergeleri](/azure/active-directory/authentication/concept-password-ban-bad) izleyin.

## <a name="phase-9-enable-azure-ad-identity-protection"></a>9. Aşama: Azure AD Kimlik Korumasını Etkinleştirme

[Azure AD Kimlik Koruması Test Laboratuvarı Kılavuzu'nun 2. Aşamasındaki](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection) yönergeleri izleyin. 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>10. Aşama: Exchange Online ve Skype Kurumsal Online için modern kimlik doğrulamasını etkinleştirme

Exchange Online için [bu yönergeleri](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) izleyin. 

Skype Kurumsal Online için:

1. [Skype Kurumsal Online'a](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) bağlanın.

2. Bu komutu çalıştırın.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Bu komutla değişikliğin başarılı olduğunu doğrulayın.

  ```powershell
  Get-CsOAuthConfiguration
  ```

Sonuç, kimlik ve cihaz erişimi için [parola karması eşitleme önkoşul yapılandırmasıyla Active Directory](../security/office-365-security/identity-access-prerequisites.md#prerequisites) gereksinimlerini karşılayan bir test ortamıdır. 

## <a name="next-step"></a>Sonraki adım

[Önkoşulları oluşturan ilkeleri yapılandırmak ve](../security/office-365-security/identity-access-policies.md) kimlikleri ve cihazları korumak için Ortak kimlik ve cihaz erişim ilkelerini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Ek kimlik Test Laboratuvarı Kılavuzları](m365-enterprise-test-lab-guides.md#identity)

[Kimliği dağıtma](deploy-identity-solution-overview.md)

[Kurumsal test laboratuvarı kılavuzları için Microsoft 365](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Kurumsal belgeler için Microsoft 365](/microsoft-365-enterprise/)
