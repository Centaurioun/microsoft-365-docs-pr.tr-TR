---
title: Microsoft 365 Defender REST API için Merhaba Dünya
description: Microsoft 365 Defender API'lerine erişmek için uygulama oluşturmayı ve belirteç kullanmayı öğrenin
keywords: uygulama, belirteç, erişim, aad, uygulama, uygulama kaydı, powershell, betik, genel yönetici, izin, microsoft 365 defender
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
ms.openlocfilehash: d94bd5353aecbf93ca59651878af7b6261e00d1d
ms.sourcegitcommit: 0380a7cd5adb710b80a0ed6fcd349199f1571080
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2022
ms.locfileid: "68332172"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Microsoft 365 Defender REST API için Merhaba Dünya

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Basit bir PowerShell betiği kullanarak olayları alma

Bu projenin tamamlanması 5-10 dakika sürmelidir. Bu zaman tahmini, uygulamayı kaydetmeyi ve PowerShell örnek betiğinden kodu uygulamayı içerir.

### <a name="register-an-app-in-azure-active-directory"></a>Azure Active Directory'de uygulama kaydetme

1. [Genel yönetici](https://portal.azure.com) rolüyle **Azure'da** kullanıcı olarak oturum açın.

2. **Azure Active Directory** >  **Uygulama kayıtları** >  **Yeni kayıt'a** gidin.

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Microsoft 365 Defender portalındaki Yeni kayıt bölümü" lightbox="../../media/atp-azure-new-app2.png":::

3. Kayıt formunda, uygulamanız için bir ad seçin ve ardından **Kaydet'i** seçin. Yeniden yönlendirme URI'sini seçmek isteğe bağlıdır. Bu örneği tamamlamak için ihtiyacınız olmayacaktır.

4. Uygulama sayfanızda **API İzinleri** Kuruluşumun > kullandığı izin  > **API'leri** >  **ekle'yi** seçin, **Microsoft Tehdit Koruması** yazın ve **Microsoft Tehdit Koruması'yı** seçin. Uygulamanız artık Microsoft 365 Defender erişebilir.

   > [!TIP]
   > *Microsoft Tehdit Koruması*, Microsoft 365 Defender için eski bir addır ve özgün listede görünmez. Görünmesini sağlamak için metin kutusuna adını yazmaya başlamanız gerekir.
   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="Microsoft 365 Defender portalında API kullanımı bölümü" lightbox="../../media/apis-in-my-org-tab.PNG":::

   - **Uygulama izinleri** > **Incident.Read.All** öğesini seçin ve **İzin ekle'yi** seçin.

     :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="Microsoft 365 Defender portalında bir uygulamanın izinler bölmesi" lightbox="../../media/request-api-permissions.PNG":::

5. **Yönetici onayı ver'i** seçin. Her izin eklediğinizde, geçerli olması için **Yönetici onayı ver'i** seçmeniz gerekir.

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="Microsoft 365 Defender portalında Yönetici onayı verme bölümü" lightbox="../../media/grant-consent.PNG":::

6. Uygulamaya gizli dizi ekleyin. **Sertifikalar & gizli dizileri** seçin, gizli diziye bir açıklama ekleyin ve **ardından Ekle'yi** seçin.

    > [!TIP]
    > **Ekle'yi** seçtikten sonra **oluşturulan gizli dizi değerini kopyala'yı** seçin. Ayrıldıktan sonra gizli dizi değerini alamazsınız.

    :::image type="content" source="../../media/webapp-create-key2.png" alt-text="Microsoft 365 Defender portalındaki gizli dizi ekleme bölümü" lightbox="../../media/webapp-create-key2.png":::
    

7. Uygulama kimliğinizi ve kiracı kimliğinizi güvenli bir yere kaydedin. Bunlar uygulama sayfanızda **Genel Bakış** altında listelenir.

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender portalındaki Genel Bakış bölümü" lightbox="../../media/app-and-tenant-ids.png":::

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Uygulamayı kullanarak belirteç alma ve belirteci kullanarak API'ye erişme

Azure Active Directory belirteçleri hakkında daha fazla bilgi [için Azure AD öğreticisine](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds) bakın.

> [!IMPORTANT]
> Bu tanıtım uygulamasındaki örnek, test amacıyla gizli dizi değerinizi yapıştırmanızı teşvik etse de, **gizli dizileri üretimde çalışan bir uygulamaya asla sabit kodlamamalısınız** . Üçüncü bir taraf, kaynaklara erişmek için gizli dizinizi kullanabilir. [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates) kullanarak uygulamanızın gizli dizilerini güvende tutmaya yardımcı olabilirsiniz. Uygulamanızı nasıl koruyabileceğinize ilişkin pratik bir örnek için bkz. [Azure Key Vault ile sunucu uygulamalarınızda gizli dizileri yönetme](/training/modules/manage-secrets-with-azure-key-vault/).

1. Aşağıdaki betiği kopyalayın ve sık kullandığınız metin düzenleyiciye yapıştırın. **Get-Token.ps1** olarak kaydedin. Kodu PowerShell ISE'de olduğu gibi de çalıştırabilirsiniz, ancak bunu kaydetmeniz gerekir çünkü sonraki bölümde olay getirme betiğini kullandığımızda yeniden çalıştırmamız gerekir.

    Bu betik bir belirteç oluşturur ve *Latest-token.txt* adlı çalışma klasörüne kaydeder.

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a>Belirteci doğrulama

1. Aldığınız belirteci kopyalayıp [JWT'ye](https://jwt.ms) yapıştırarak kodunu çözebilirsiniz.
1. *JWT* , *JSON Web Belirteci'nin* kısaltmasıdır. Kodu çözülen belirteç bir dizi JSON biçimli öğe veya talep içerir. Kodu çözülen belirteç içindeki *rol* talebi için istenen izinlerin bulunduğundan emin olun.

    Aşağıdaki görüntüde, , ```Incidents.ReadWrite.All```ve ```AdvancedHunting.Read.All``` izinleriyle ```Incidents.Read.All```bir uygulamadan alınan kodu çözülen belirteci görebilirsiniz:

    :::image type="content" source="../../media/api-jwt-ms.png" alt-text="Microsoft 365 Defender portalındaki Kod Çözme Belirteci bölümü" lightbox="../../media/api-jwt-ms.png":::

### <a name="get-a-list-of-recent-incidents"></a>Son olayların listesini alma

Aşağıdaki betik, API'ye erişmek için **Get-Token.ps1** kullanır. Ardından son 48 saat içinde güncelleştirilen olayların listesini alır ve listeyi JSON dosyası olarak kaydeder.

> [!IMPORTANT]
> Bu betiği **Get-Token.ps1** kaydettiğiniz klasöre kaydedin.

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents`?`$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

Hepsi bu kadar! Başarılı bir şekilde:

- Uygulama oluşturuldu ve kaydedildi.
- Bu uygulamaya uyarıları okuma izni verildi.
- API'ye bağlı.
- Son 48 saat içinde güncelleştirilen olayları döndürmek için bir PowerShell betiği kullandı.

## <a name="related-articles"></a>İlgili makaleler

- [Microsoft 365 Defender API'lere genel bakış](api-overview.md)
- [Microsoft 365 Defender API'lerine erişme](api-access.md)
- [Kullanıcı olmadan Microsoft 365 Defender erişmek için uygulama oluşturma](api-create-app-web.md)
- [Kullanıcı adına Microsoft 365 Defender API'lere erişmek için uygulama oluşturma](api-create-app-user-context.md)
- [Microsoft 365 Defender API'lere çok kiracılı iş ortağı erişimine sahip bir uygulama oluşturma](api-partner-access.md)
- [Azure Key Vault ile sunucu uygulamalarınızdaki gizli dizileri yönetme](/training/modules/manage-secrets-with-azure-key-vault/)
- [Kullanıcı oturum açma ve API erişimi için OAuth 2.0 Yetkilendirmesi](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
