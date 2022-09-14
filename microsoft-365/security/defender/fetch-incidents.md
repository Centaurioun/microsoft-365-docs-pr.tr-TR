---
title: Defender Microsoft 365 getirin
description: Müşteri kiracısından Microsoft 365 Defender olayları getirmeyi öğrenin
keywords: yönetilen güvenlik hizmeti sağlayıcısı, mssp, yapılandırma, tümleştirme
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: api
ms.openlocfilehash: 707041bb9c1a7692086f696e3ae7f648ed484de6
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67679767"
---
# <a name="fetch-microsoft-365-defender-incidents"></a>Defender Microsoft 365 getirin 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!NOTE]
> Bu eylem MSSP tarafından gerçekleştirilen.

Uyarıları getirmenin iki yolu vardır:

- SIEM yöntemini kullanma
- API'leri kullanma

## <a name="fetch-incidents-into-your-siem"></a>Olayları SIEM'inize getirme

Olayları SIEM sisteminize getirmek için aşağıdaki adımları uygulamanız gerekir:

- 1. Adım: Üçüncü taraf uygulama oluşturma
- 2. Adım: Müşterinizin kiracısından erişim ve yenileme belirteçleri alma
- 3. Adım: uygulamanızın Microsoft 365 Defender

### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>1. Adım: Azure Active Directory'de uygulama oluşturma (Azure AD)

Bir uygulama oluşturmanız ve müşterinizin Microsoft 365 Defender kiracısından uyarı getirme izni vermeniz gerekir.

1. [Azure AD portalında](https://aad.portal.azure.com/) oturum açın.

2. **Azure Active Directory** \> **Uygulama kayıtları'ı** seçin.

3. **Yeni kayıt'a** tıklayın.

4. Aşağıdaki değerleri belirtin:

    - Ad: \<Tenant_name\> SIEM MSSP Bağlayıcısı (Tenant_name kiracı görünen adıyla değiştirin)

    - Desteklenen hesap türleri: Yalnızca bu kuruluş dizinindeki hesap
    - Yeniden yönlendirme URI'si: Web'i seçin ve yazın `https://<domain_name>/SiemMsspConnector`(<domain_name> kiracı adıyla değiştirin)

5. **Kaydet'e** tıklayın. Uygulama, sahip olduğunuz uygulamalar listesinde görüntülenir.

6. Uygulamayı seçin ve genel **bakış'a** tıklayın.

7. **Uygulama (istemci) Kimliği** alanındaki değeri güvenli bir yere kopyalayın; sonraki adımda buna ihtiyacınız olacaktır.

8. Yeni uygulama panelinde **Sertifika & gizli dizileri'ni** seçin.

9. **Yeni istemci gizli dizisi'ne** tıklayın.

    - Açıklama: Anahtar için bir açıklama girin.
    - Süre sonu: **1 yıl içinde** seçin

10. **Ekle'ye** tıklayın, istemci gizli dizisinin değerini güvenli bir yere kopyalayın, sonraki adımda buna ihtiyacınız olacaktır.

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>2. Adım: Müşterinizin kiracısından erişim ve yenileme belirteçleri alma

Bu bölüm, müşterinizin kiracısından belirteçleri almak için PowerShell betiğini kullanma konusunda size yol gösterir. Bu betik, OAuth Yetkilendirme Kodu Akışı'nı kullanarak erişim ve yenileme belirteçlerini almak için önceki adımdaki uygulamayı kullanır.

Kimlik bilgilerinizi sağladıktan sonra, uygulamanın müşterinin kiracısında sağlanması için uygulamaya onay vermeniz gerekir.

1. Yeni bir klasör oluşturun ve şu adı verin: `MsspTokensAcquisition`.

2. [LoginBrowser.psm1 modülünü](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) indirin ve klasöre `MsspTokensAcquisition` kaydedin.

    > [!NOTE]
    > 30. satırda değerini ile `authorizationUrl`değiştirin`authorzationUrl`.

3. Aşağıdaki içeriğe sahip bir dosya oluşturun ve klasöre adıyla `MsspTokensAcquisition.ps1` kaydedin:

    ```powershell
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " ----------------------------------- TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " ----------------------------------- REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken
    ```
4. Klasörde yükseltilmiş bir PowerShell komut istemi `MsspTokensAcquisition` açın.

5. Aşağıdaki konumu çalıştırın: `Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. Aşağıdaki komutları girin: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`

    - değerini önceki adımda aldığınız **Uygulama (istemci) kimliğiyle** değiştirin\<client_id\>.
    - değerini önceki adımda oluşturduğunuz **İstemci Gizli Anahtarı** ile değiştirin\<app_key\>.
    - değerini müşterinizin **Kiracı Kimliği** ile değiştirin\<customer_tenant_id\>.

7. Kimlik bilgilerinizi ve onayınızı sağlamanız istenir. Sayfa yeniden yönlendirmesini yoksayın.

8. PowerShell penceresinde bir erişim belirteci ve yenileme belirteci alırsınız. SIEM bağlayıcınızı yapılandırmak için yenileme belirtecini kaydedin.

### <a name="step-3-allow-your-application-on-microsoft-365-defender"></a>3. Adım: Uygulamanızın Microsoft 365 Defender'de izin verme

Microsoft 365 Defender'de oluşturduğunuz uygulamaya izin vermeniz gerekir.

Uygulamaya izin vermek için **Portal sistem ayarlarını yönet** iznine sahip olmanız gerekir. Aksi takdirde müşterinizden uygulamaya sizin için izin vermelerini istemeniz gerekir.

1. adresine `https://security.microsoft.com?tid=<customer_tenant_id>` gidin (değerini müşterinin kiracı kimliğiyle değiştirin \<customer_tenant_id\> .

2. **Ayarlar** \> **Uç Noktaları API'leri** \>  \> **SIEM'i** tıklatın.

3. **MSSP** sekmesini seçin.

4. İlk adımdaki **Uygulama Kimliğini** ve **Kiracı Kimliğinizi** girin.

5. **Uygulamayı yetkile'ye** tıklayın.

Artık SIEM'iniz için ilgili yapılandırma dosyasını indirebilir ve Microsoft 365 Defender API'sine bağlanabilirsiniz. Daha fazla bilgi için bkz. [SIEM araçlarınıza uyarılar çekme](../defender-endpoint/configure-siem.md).

- ArcSight yapılandırma dosyası / Splunk Kimlik Doğrulama Özellikleri dosyasında gizli dizi değerini ayarlayarak uygulama anahtarınızı el ile yazın.
- Portalda yenileme belirteci almak yerine bir yenileme belirteci almak (veya başka bir yolla almak) için önceki adımdaki betiği kullanın.

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>API'leri kullanarak MSSP müşteri kiracısından uyarıları getirme

REST API kullanarak uyarıları getirme hakkında bilgi için bkz. [REST API kullanarak uyarıları çekme](../defender-endpoint/pull-alerts-using-rest-api.md).
