---
title: Kurcalama koruması hakkında sık sorulan sorular
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Kurcalama korumasını yapılandırma hakkında sık sorulan sorular.
keywords: kötü amaçlı yazılım, defender, virüsten koruma, kurcalama koruması
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.technology: mde
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: 39e295d165ff0130536c62e195a6b3a13bb47317
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67389462"
---
# <a name="frequently-asked-questions-on-tamper-protection"></a>Kurcalama koruması hakkında sık sorulan sorular

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

## <a name="on-which-versions-of-windows-can-i-configure-tamper-protection"></a>Windows'un hangi sürümlerinde 'kurcalama koruması' yapılandırabilirim?

- Windows 11
- Çoklu oturum Windows 11 Enterprise
- Uç Nokta için Microsoft Defender ile birlikte işletim sistemi [1709](/lifecycle/announcements/revised-end-of-service-windows-10-1709), [1803](/lifecycle/announcements/windows-server-1803-end-of-servicing), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) veya [üzerini Windows 10](/microsoft-365/security/defender-endpoint).
- Çoklu oturum Windows 10 Enterprise
  
Kiracı eklemeli Configuration Manager, sürüm 2006 kullanıyorsanız, kurcalama koruması R2, Windows Server 2016, Windows Server 2019 ve Windows Server 2022 Windows Server 2012 genişletilebilir. Bkz [. Kiracı ekleme: Yönetim merkezinden uç nokta güvenliği Virüsten koruma ilkesi oluşturma ve dağıtma (önizleme)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).

## <a name="will-tamper-protection-affect-non-microsoft-antivirus-registration-in-the-windows-security-app"></a>Kurcalama koruması, Windows Güvenliği uygulamasında Microsoft dışı virüsten koruma kaydını etkiler mi?

Hayır. Microsoft dışı virüsten koruma teklifleri Windows Güvenliği uygulamasına kaydolmaya devam eder.

## <a name="what-happens-if-microsoft-defender-antivirus-isnt-active-on-a-device"></a>Microsoft Defender Virüsten Koruma bir cihazda etkin değilse ne olur?

Uç Nokta için Microsoft Defender eklenen cihazlarda Microsoft Defender Virüsten Koruma pasif modda çalışır. Bu durumlarda, kurcalama koruması hizmeti ve özelliklerini korumaya devam eder.

## <a name="how-do-i-turn-tamper-protection-on-or-off"></a>Kurcalama korumasını açmak veya kapatmak Nasıl yaparım??

Ev kullanıcısıysanız bkz. [Tek bir cihazda kurcalama korumasını yönetme](manage-tamper-protection-individual-device.md).

[Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint) kullanan bir kuruluşsanız, diğer uç nokta koruma özelliklerini yönetme yönteminize benzer şekilde Intune 'kurcalama korumasını' yönetebiliyor olmanız gerekir. Bu makalenin aşağıdaki bölümlerine bakın:

- [Microsoft Endpoint Manager kullanarak kurcalama korumasını yönetme](manage-tamper-protection-microsoft-endpoint-manager.md)
- [Microsoft 365 Defender kullanarak kurcalama korumasını yönetme](manage-tamper-protection-microsoft-365-defender.md)

## <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-with-group-policy"></a>Intune'de kurcalama korumasını yapılandırmak, microsoft defender virüsten korumayı grup ilkesi ile yönetme şeklimi nasıl etkiler?

Şu anda 'kurcalama koruması' yapılandırmak ve yönetmek için Intune kullanıyorsanız, Intune kullanmaya devam etmelisiniz. 

Grup ilkesi kurcalama koruması için geçerli değildir. grup ilkesi kullanılarak Microsoft Defender Virüsten Koruma ayarlarında yapılan değişiklikler, kurcalama koruması açık olduğunda veya Intune ile kurcalama koruması yapılandırıldığında yoksayılır.

## <a name="if-we-use-microsoft-intune-to-configure-tamper-protection-does-it-apply-only-to-the-entire-organization"></a>'Kurcalama korumasını' yapılandırmak için Microsoft Intune kullanırsak, bu yalnızca kuruluşun tamamı için geçerli mi?

Intune ile kurcalama korumasını yapılandırma esnekliğine sahipsiniz. Kuruluşunuzun tamamını hedefleyebilir veya belirli cihazları ve kullanıcı gruplarını seçebilirsiniz.

## <a name="can-i-configure-tamper-protection-with-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager ile kurcalama korumasını yapılandırabilir miyim?

Kiracı ekleme kullanıyorsanız Microsoft Endpoint Configuration Manager kullanabilirsiniz. Aşağıdaki kaynaklara bakın:

- [Configuration Manager, sürüm 2006 ile kiracı ekleme kullanarak kurcalama korumasını yönetme](manage-tamper-protection-configuration-manager.md)
- [Teknoloji Topluluğu blogu: Configuration Manager Kiracı Ekleme istemcileri için Kurcalama Koruması Duyuruları](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Windows E3 kaydım var. Intune'de kurcalama korumasını yapılandırmayı kullanabilir miyim?

Şu anda, Intune'de kurcalama korumasını yapılandırmak yalnızca [Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint) sahip müşteriler tarafından kullanılabilir.

## <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>Kurumsal bir müşteriyim. Yerel yöneticiler cihazlarında kurcalama korumasını değiştirebilir mi?

Hayır. Yerel yöneticiler 'kurcalama koruması' ayarlarını değiştiremez veya değiştiremez.

## <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>Cihazım Uç Nokta için Microsoft Defender eklendiğinde ve ardından kapalı duruma geçerse ne olur?

Bir cihaz Uç Nokta için Microsoft Defender kapalıysa, yönetilmeyen cihazlar için varsayılan durum olan kurcalama koruması açılır.

## <a name="if-the-status-of-tamper-protection-changes-are-alerts-shown-in-the-microsoft-365-defender-portal"></a>Kurcalama korumasının durumu değişirse uyarılar Microsoft 365 Defender portalında gösteriliyor mu?

Evet. Uyarı, **Uyarılar** altında gösterilir [https://security.microsoft.com](https://security.microsoft.com).

Güvenlik operasyonları ekibiniz, aşağıdaki örnek gibi avcılık sorgularını da kullanabilir:

`AlertInfo|where Title == "Tamper Protection bypass"`

> [!TIP]
> Diğer platformlar için Antivirüs ile ilgili bilgi arıyorsanız bkz:
> - [MacOS'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](mac-preferences.md)
> - [Mac'te Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-mac.md)
> - [Intune için Microsoft Defender için macOS Virüsten Koruma ilke ayarları](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux'ta Uç Nokta için Microsoft Defender tercihlerini ayarlayın](linux-preferences.md)
> - [Linux'ta Uç Nokta için Microsoft Defender](microsoft-defender-endpoint-linux.md)
> - [Android özelliklerinde Uç Nokta için Defender’ı yapılandırın](android-configure.md)
> - [iOS özelliklerinde Uç Nokta için Microsoft Defender’ı yapılandırın](ios-configure-features.md)
