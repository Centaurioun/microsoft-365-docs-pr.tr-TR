---
title: Microsoft 365 Defender API'leri aracılığıyla iş ortağı erişimi
description: Kullanıcılarınız adına Microsoft 365 Defender program aracılığıyla erişim elde etmek için uygulama oluşturmayı öğrenin.
keywords: iş ortağı, erişim, api, çok kiracılı, onay, erişim belirteci, uygulama
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.custom: api
ms.openlocfilehash: 1ef373d3f3c406453d92b0a463a26ba9513bb6e3
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68049022"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Microsoft 365 Defender API'lerine iş ortağı erişimi olan bir uygulama oluşturma

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Bu sayfada, birden çok kiracıdaki kullanıcılar adına Microsoft 365 Defender program aracılığıyla erişimi olan bir Azure Active Directory uygulamasının nasıl oluşturulacağı açıklanır. Çok kiracılı uygulamalar, büyük kullanıcı gruplarına hizmet etmek için kullanışlıdır.

Tek bir kullanıcı adına Microsoft 365 Defender program aracılığıyla erişmeniz gerekiyorsa bkz. [Kullanıcı adına Microsoft 365 Defender API'lere erişmek için uygulama oluşturma](api-create-app-user-context.md). Kullanıcı açıkça tanımlanmamış bir erişime ihtiyacınız varsa (örneğin, bir arka plan uygulaması veya daemon yazıyorsanız), bkz. [Kullanıcı olmadan Microsoft 365 Defender erişmek için uygulama oluşturma](api-create-app-web.md). Hangi tür erişime ihtiyacınız olduğundan emin değilseniz bkz. [Kullanmaya başlama](api-access.md).

Microsoft 365 Defender, bir dizi programlı API aracılığıyla verilerinin ve eylemlerinin büyük bir kısmını kullanıma sunar. Bu API'ler iş akışlarını otomatikleştirmenize ve Microsoft 365 Defender özelliklerinden yararlanmanıza yardımcı olur. Bu API erişimi için OAuth2.0 kimlik doğrulaması gerekir. Daha fazla bilgi için bkz [. OAuth 2.0 Yetkilendirme Kodu Akışı](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Genel olarak, bu API'leri kullanmak için aşağıdaki adımları uygulamanız gerekir:

- Bir Azure Active Directory (Azure AD) uygulaması oluşturun.
- Bu uygulamayı kullanarak erişim belirteci alın.
- Microsoft 365 Defender API'sine erişmek için belirteci kullanın.

Bu uygulama çok kiracılı olduğundan, kullanıcıları adına her kiracıdan [yönetici onayı](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) almanız gerekir.

Bu makalede şunların nasıl yapılacağını açıklar:

- **Çok kiracılı** Azure AD uygulaması oluşturma
- Uygulamanızın ihtiyaç duyduğu kaynaklara Microsoft 365 Defender erişmek için kullanıcı yöneticinizden yetkili onay alın.
- Microsoft 365 Defender erişim belirteci alma
- Belirteci doğrulama

Microsoft 365 Defender, bir dizi programlı API aracılığıyla verilerinin ve eylemlerinin büyük bir kısmını kullanıma sunar. Bu API'ler, iş akışlarını otomatikleştirmenize ve Microsoft 365 Defender özelliklerine göre yenilik oluşturmanıza yardımcı olur. API erişimi için OAuth2.0 kimlik doğrulaması gerekir. Daha fazla bilgi için bkz [. OAuth 2.0 Yetkilendirme Kodu Akışı](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Genel olarak, API'leri kullanmak için aşağıdaki adımları uygulamanız gerekir:

- **Çok kiracılı** bir Azure AD uygulaması oluşturun.
- Uygulamanızın ihtiyaç duyduğu Microsoft 365 Defender kaynaklara erişmesi için kullanıcı yöneticiniz tarafından yetkilendirilin (onay).
- Bu uygulamayı kullanarak erişim belirteci alın.
- Microsoft 365 Defender API'sine erişmek için belirteci kullanın.

Çok kiracılı bir Azure AD uygulaması oluşturma, Microsoft 365 Defender için erişim belirteci alma ve belirteci doğrulama adımlarını içeren aşağıdaki adımlar.

## <a name="create-the-multi-tenant-app"></a>Çok kiracılı uygulamayı oluşturma

1. **Azure'da Genel Yönetici** rolüyle kullanıcı olarak oturum açın.[](https://portal.azure.com)

2. **Azure Active Directory** >  **Uygulama kayıtları** >  **Yeni kayıt'a** gidin.

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Microsoft 365 Defender portalında bir uygulamanın kayıt bölümü" lightbox="../../media/atp-azure-new-app2.png":::

3. Kayıt formunda:

   - Uygulamanız için bir ad seçin.
   - **Desteklenen hesap türlerinden** **Herhangi bir kuruluş dizinindeki hesaplar (Herhangi bir Azure AD dizini) - Çok Kiracılı'yı** seçin.
   - **Yeniden Yönlendirme URI'sini** doldurun. **Web** yazın'ı seçin ve yeniden yönlendirme URI'sini olarak **https://portal.azure.com** verin.

   Formu doldurmayı tamamladıktan sonra **Kaydet'i** seçin.

   :::image type="content" source="../..//media/atp-api-new-app-partner.png" alt-text="Microsoft 365 Defender portalında uygulamanın kayıt bölümleri" lightbox="../..//media/atp-api-new-app-partner.png":::

4. Uygulama sayfanızda **API İzinleri** Kuruluşumun > kullandığı izin  > **API'leri** >  **ekle'yi** seçin, **Microsoft Tehdit Koruması** yazın ve **Microsoft Tehdit Koruması'yı** seçin. Uygulamanız artık Microsoft 365 Defender erişebilir.

   > [!TIP]
   > *Microsoft Tehdit Koruması*, Microsoft 365 Defender için eski bir addır ve özgün listede görünmez. Görünmesini sağlamak için metin kutusuna adını yazmaya başlamanız gerekir.

   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="Microsoft 365 Defender portalındaki API kullanımı bölümü" lightbox="../../media/apis-in-my-org-tab.PNG":::

5. **Uygulama izinleri'ne tıklayın**. Senaryonuz için ilgili izinleri seçin (örneğin, **Incident.Read.All**) ve ardından **İzin ekle'yi** seçin.

   :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="Microsoft 365 Defender portalında uygulamanın izin bölmesi" lightbox="../../media/request-api-permissions.PNG":::

    > [!NOTE]
    > Senaryonuz için ilgili izinleri seçmeniz gerekir. *Tüm olayları okuma* yalnızca bir örnektir. Hangi izne ihtiyacınız olduğunu belirlemek için lütfen çağırmak istediğiniz API'nin **İzinler** bölümüne bakın.
    >
    > Örneğin, [gelişmiş sorgular çalıştırmak](api-advanced-hunting.md) için 'Gelişmiş sorguları çalıştırma' iznini seçin; [cihazı yalıtmak](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine) için 'Makineyi yalıt' iznini seçin.

6. **Yönetici onayı ver'i** seçin. Her izin eklediğinizde, geçerli olması için **Yönetici onayı ver'i** seçmeniz gerekir.

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="Microsoft 365 Defender portalında yönetici onayı verme bölümü" lightbox="../../media/grant-consent.PNG":::

7. Uygulamaya gizli dizi eklemek için **Sertifikalar & gizli dizileri** seçin, gizli diziye bir açıklama ekleyin ve **ardından Ekle'yi** seçin.

    > [!TIP]
    > **Ekle'yi** seçtikten sonra **oluşturulan gizli dizi değerini kopyala'yı** seçin. Ayrıldıktan sonra gizli dizi değerini alamazsınız.

      :::image type="content" source="../../media/webapp-create-key2.png" alt-text="Microsoft 365 Defender portalındaki Gizli dizi ekleme bölümü" lightbox="../../media/webapp-create-key2.png":::

8. Uygulama kimliğinizi ve kiracı kimliğinizi güvenli bir yere kaydedin. Bunlar uygulama sayfanızda **Genel Bakış** altında listelenir.

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender portalındaki Genel Bakış bölmesi" lightbox="../../media/app-and-tenant-ids.png":::

9. Uygulamayı kullanıcınızın kiracısına ekleyin.

   Uygulamanız kullanıcılarınız adına Microsoft 365 Defender ile etkileşime geçtiğinden, kullanmak istediğiniz her kiracı için onaylanması gerekir.

   Kullanıcınızın kiracısından bir **Genel Yöneticinin** onay bağlantısını görüntülemesi ve uygulamanızı onaylaması gerekir.

   Onay bağlantısı şu biçimdedir:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   Basamaklar `00000000-0000-0000-0000-000000000000` Uygulama Kimliğiniz ile değiştirilmelidir.

   Onay bağlantısına tıkladıktan sonra kullanıcının kiracısının Genel Yöneticisi ile oturum açın ve uygulamayı onaylayın.

   :::image type="content" source="../../media/app-consent-partner.png" alt-text="Microsoft 365 Defender portalındaki onay uygulaması sayfası" lightbox="../../media/app-consent-partner.png":::

   Ayrıca kullanıcınızdan kiracı kimliğini de istemeniz gerekir. Kiracı kimliği, erişim belirteçlerini almak için kullanılan tanımlayıcılardan biridir.

- **Bitti!** Bir uygulamayı başarıyla kaydettiniz!
- Belirteç alma ve doğrulama için aşağıdaki örneklere bakın.

## <a name="get-an-access-token"></a>Erişim belirteci alma

Azure AD belirteçleri hakkında daha fazla bilgi için [Azure AD öğreticisine](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds) bakın.

> [!IMPORTANT]
> Bu bölümdeki örnekler gizli dizi değerlerini test amacıyla yapıştırmanızı teşvik etse de, üretimde çalışan bir uygulamaya **gizli dizileri hiçbir zaman sabit kodlamamalısınız** . Üçüncü bir taraf, kaynaklara erişmek için gizli dizinizi kullanabilir. [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates) kullanarak uygulamanızın gizli dizilerini güvende tutmaya yardımcı olabilirsiniz. Uygulamanızı nasıl koruyabileceğinize ilişkin pratik bir örnek için bkz. [Azure Key Vault ile sunucu uygulamalarınızda gizli dizileri yönetme](/training/modules/manage-secrets-with-azure-key-vault/).

> [!TIP]
> Aşağıdaki örneklerde, betiğin çalışıp çalışmadığını test etmek için kullanıcının kiracı kimliğini kullanın.

### <a name="get-an-access-token-using-powershell"></a>PowerShell kullanarak erişim belirteci alma

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a>C kullanarak erişim belirteci alma\#

> [!NOTE]
> Aşağıdaki kod Nuget Microsoft.Identity.Client 3.19.8 ile test edilmiştir.

> [!IMPORTANT]
> [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) NuGet paketi ve Azure AD Kimlik Doğrulama Kitaplığı (ADAL) kullanım dışı bırakıldı. 30 Haziran 2020'den bu yana yeni özellik eklenmemiş.   Yükseltmenizi kesinlikle öneririz. Diğer ayrıntılar için [geçiş kılavuzuna](/azure/active-directory/develop/msal-migration) bakın.

1. Yeni bir konsol uygulaması oluşturun.
1. NuGet [Microsoft.Identity.Client'ı](https://www.nuget.org/packages/Microsoft.Identity.Client/) yükleyin.
1. Aşağıdaki satırı ekleyin:

    ```C#
    using Microsoft.Identity.Client;
    ```

1. Aşağıdaki kodu kopyalayıp uygulamanıza yapıştırın (üç değişkeni güncelleştirmeyi unutmayın: `tenantId`, `clientId`, `appSecret`):

    ```C#
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 
    const string authority = https://login.microsoftonline.com;
    const string audience = https://api.securitycenter.microsoft.com;

    IConfidentialClientApplication myApp = ConfidentialClientApplicationBuilder.Create(appId).WithClientSecret(appSecret).WithAuthority($"{authority}/{tenantId}").Build();

    List<string> scopes = new List<string>() { $"{audience}/.default" };

    AuthenticationResult authResult = myApp.AcquireTokenForClient(scopes).ExecuteAsync().GetAwaiter().GetResult();

    string token = authResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a>Python kullanarak erişim belirteci alma

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a>Curl kullanarak erişim belirteci alma

> [!NOTE]
> Curl, Windows 10, sürüm 1803 ve sonraki sürümlerde önceden yüklenmiştir. Windows'un diğer sürümleri için aracı doğrudan [resmi curl web sitesinden](https://curl.haxx.se/windows/) indirin ve yükleyin.

1. Bir komut istemi açın ve CLIENT_ID Azure uygulama kimliğiniz olarak ayarlayın.
1. CLIENT_SECRET Azure uygulama gizli dizinize ayarlayın.
1. Microsoft 365 Defender erişmek için uygulamanızı kullanmak isteyen kullanıcının Azure kiracı kimliğine TENANT_ID ayarlayın.
1. Aşağıdaki komutu çalıştırın:

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Başarılı bir yanıt şöyle görünür:

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Belirteci doğrulama

1. Kodu çözmek için belirteci kopyalayıp [JSON web belirteci doğrulayıcı web sitesine (JWT)](https://jwt.ms) yapıştırın.
1. Kodu çözülen belirteç içindeki *rol* talebi için istenen izinlerin bulunduğundan emin olun.

Aşağıdaki görüntüde, , ```Incidents.ReadWrite.All```ve ```AdvancedHunting.Read.All``` izinleriyle ```Incidents.Read.All```bir uygulamadan alınan kodu çözülen belirteci görebilirsiniz:

:::image type="content" source="../../media/webapp-decoded-token.png" alt-text="Microsoft 365 Defender portalında Kod Çözme Belirteci bölmesi" lightbox="../../media/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Microsoft 365 Defender API'sine erişmek için belirteci kullanma

1. Kullanmak istediğiniz API'yi (olaylar veya gelişmiş avcılık) seçin. Daha fazla bilgi için bkz[. Desteklenen Microsoft 365 Defender API'leri](api-supported.md).
2. Göndermek üzere olduğunuz http isteğinde yetkilendirme üst bilgisini `"Bearer" <token>`olarak ayarlayın, *taşıyıcı* yetkilendirme şeması ve *belirteç* doğrulanmış belirtecinizdir.
3. Belirtecin süresi bir saat içinde dolar. Bu süre boyunca aynı belirteçle birden fazla istek gönderebilirsiniz.

Aşağıdaki örnekte **, C# kullanarak** olayların listesini almak için istek gönderme işlemleri gösterilmektedir.

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>İlgili makaleler

- [Microsoft 365 Defender API'lere genel bakış](api-overview.md)
- [Microsoft 365 Defender API'lerine erişme](api-access.md)
- ['Hello world' uygulaması oluşturma](api-hello-world.md)
- [Kullanıcı olmadan Microsoft 365 Defender erişmek için uygulama oluşturma](api-create-app-web.md)
- [Kullanıcı adına Microsoft 365 Defender API'lere erişmek için uygulama oluşturma](api-create-app-user-context.md)
- [API sınırları ve lisanslama hakkında bilgi edinin](api-terms.md)
- [Hata kodlarını anlama](api-error-codes.md)
- [Azure Key Vault ile sunucu uygulamalarınızdaki gizli dizileri yönetme](/training/modules/manage-secrets-with-azure-key-vault/)
- [Kullanıcı oturum açma ve API erişimi için OAuth 2.0 yetkilendirmesi](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
