---
title: Uç Nokta için Microsoft Defender API için Merhaba Dünya
ms.reviewer: ''
description: Uç Nokta için Microsoft Defender API'sine 'Merhaba dünya' stili api çağrısı oluşturma.
keywords: api'ler, desteklenen api'ler, gelişmiş avcılık, sorgu, microsoft defender atp, uç nokta için microsoft defender
ms.prod: m365-security
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 2805736c3d612716f3b99ba0f97fc74a0070bc68
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328046"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a>Uç Nokta için Microsoft Defender API - Merhaba Dünya

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)


>Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a>Basit bir PowerShell betiği kullanarak Uyarılar alma

### <a name="how-long-it-takes-to-go-through-this-example"></a>Bu örnekten geçmek ne kadar sürer?

İki adımda yalnızca 5 dakika sürer:

- Uygulama kaydı
- Örnekleri kullanma: Yalnızca kısa bir PowerShell betiğinin kopyalanmasını/yapıştırılabilmesini gerektirir

### <a name="do-i-need-a-permission-to-connect"></a>Bağlanmak için izne ihtiyacım var mı?

Uygulama kayıt aşaması için Azure Active Directory (Azure AD) kiracınızda **Genel yönetici** rolüne sahip olmanız gerekir.

### <a name="step-1---create-an-app-in-azure-active-directory"></a>1. Adım - Azure Active Directory'de uygulama oluşturma

1. Genel yönetici kullanıcınızla [](https://portal.azure.com) **Azure'da** oturum açın.

2. **Azure Active Directory** \> **Uygulama kayıtları** \> **Yeni kayıt'a** gidin.

   :::image type="content" source="images/atp-azure-new-app2.png" alt-text="Azure Active Directory portalındaki Yönet bölmesinin altındaki Uygulama kayıtları seçeneği"  lightbox="images/atp-azure-new-app2.png":::

3. Kayıt formunda, uygulamanız için bir ad seçin ve **Kaydet'e** tıklayın.

4. Uygulamanızın Uç Nokta için Defender'a erişmesine ve **'Tüm uyarıları okuma'** izni atamasına izin verin:

   - Uygulama sayfanızda **API İzinleri** **Kuruluşumun kullandığı** **izin** \> API'leri \> ekle'ye tıklayın > **WindowsDefenderATP** yazın ve **WindowsDefenderATP'ye** tıklayın.

     > [!NOTE]
     > WindowsDefenderATP özgün listede görünmez. Görünmesini sağlamak için metin kutusuna adını yazmaya başlamanız gerekir.

     :::image type="content" source="images/add-permission.png" alt-text="Azure Active Directory portalındaki Yönet bölmesinin altındaki API izinleri seçeneği" lightbox="images/add-permission.png":::

   - **Uygulama izinleri** \> **Alert.Read.All** > **İzin ekle'ye** tıklayın.

     :::image type="content" source="images/application-permissions.png" alt-text="API izinleri isteme sayfasındaki izin türü ve ayarlar bölmeleri" lightbox="images/application-permissions.png":::

     > [!IMPORTANT]
     > İlgili izinleri seçmeniz gerekir. 'Tüm Uyarıları Oku' yalnızca bir örnektir!

     Örneğin:

     - [Gelişmiş sorgular çalıştırmak](run-advanced-query-api.md) için 'Gelişmiş sorgu çalıştır' iznini seçin.
     - [Bir makineyi yalıtmak](isolate-machine.md) için 'Makineyi yalıtma' iznini seçin.
     - Hangi izne ihtiyacınız olduğunu belirlemek için lütfen çağırmak istediğiniz API'nin **İzinler** bölümüne bakın.

5. **İzin ver'e** tıklayın.

   > [!NOTE]
   > her izin eklediğinizde, yeni iznin geçerli olması için **Onay ver'e** tıklamanız gerekir.

   :::image type="content" source="images/grant-consent.png" alt-text="Azure Active Directory portalında izin izni verme seçeneği" lightbox="images/grant-consent.png":::

6. Uygulamaya gizli dizi ekleyin.

    **Sertifikalar & gizli diziler'e** tıklayın, gizli diziye açıklama ekleyin ve **Ekle'ye** tıklayın.

    > [!IMPORTANT]
    > Ekle'ye tıkladıktan sonra **oluşturulan gizli dizi değerini kopyalayın**. Gittikten sonra geri alamazsınız!

    :::image type="content" source="images/webapp-create-key2.png" alt-text="Azure Active Directory portalındaki Yönet bölmesindeki Sertifikalar & gizli dizileri menü öğesi" lightbox="images/webapp-create-key2.png":::

7. Uygulama kimliğinizi ve kiracı kimliğinizi not edin.

   Uygulama sayfanızda **Genel Bakış'a** gidin ve aşağıdakileri kopyalayın:

   :::image type="content" source="images/app-and-tenant-ids.png" alt-text="Azure Active Directory portalındaki Genel Bakış menü öğesinin altındaki uygulama ayrıntıları bölmesi" lightbox="images/app-and-tenant-ids.png":::

Bitti! Bir uygulamayı başarıyla kaydettiniz!

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>2. Adım: Uygulamayı kullanarak bir belirteç alın ve API'ye erişmek için bu belirteci kullanın.

- Aşağıdaki betiği PowerShell ISE'ye veya bir metin düzenleyicisine kopyalayın ve **Get-Token.ps1** olarak kaydedin.
- Bu betiği çalıştırmak bir belirteç oluşturur ve **Latest-token.txt** adı altında çalışma klasörüne kaydeder.

   ```powershell
   # That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
   # Paste below your Tenant ID, App ID and App Secret (App key).

   $tenantId = '' ### Paste your tenant ID here
   $appId = '' ### Paste your Application ID here
   $appSecret = '' ### Paste your Application secret here

   $resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
   $oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
   $authBody = [Ordered] @{
       resource = "$resourceAppIdUri"
       client_id = "$appId"
       client_secret = "$appSecret"
       grant_type = 'client_credentials'
   }
   $authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
   $token = $authResponse.access_token
   Out-File -FilePath "./Latest-token.txt" -InputObject $token
   return $token
   ```

- Sanity Denetimi:
  - Betiği çalıştırın.
  - Tarayıcınızda adresine gidin: <https://jwt.ms/>.
  - Belirteci kopyalayın (Latest-token.txt dosyasının içeriği).
  - Üstteki kutuya yapıştırın.
  - "Roller" bölümünü arayın. _Alert.Read.All_ rolünü bulun.

  :::image type="content" source="images/api-jwt-ms.png" alt-text="jwt.ms için Kod Çözme Belirteci bölmesi" lightbox="images/api-jwt-ms.png":::

### <a name="lets-get-the-alerts"></a>Uyarıları alalım!

- Aşağıdaki betik, API'ye erişmek için **Get-Token.ps1** kullanır ve son 48 saatlik Uyarıları alır.
- Bu betiği, **Get-Token.ps1** önceki betiği kaydettiğiniz klasöre kaydedin.
- Betik, betiklerle aynı klasörde yer alan verileri içeren iki dosya (json ve csv) oluşturur.

  ```powershell
  # Returns Alerts created in the past 48 hours.

  $token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

  # Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
  $dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

  # The URL contains the type of query and the time filter we create above
  # Read more about other query options and filters at   Https://TBD- add the documentation link
  $url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

  # Set the WebRequest headers
  $headers = @{
      'Content-Type' = 'application/json'
      Accept = 'application/json'
      Authorization = "Bearer $token"
  }

  # Send the webrequest and get the results.
  $response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

  # Extract the alerts from the results.
  $alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

  # Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
  $dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

  # Save the result as json and as csv
  $outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"
  $outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

  Out-File -FilePath $outputJsonPath -InputObject $alerts
  ($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation
  ```

Hepsi bu kadar! Başarılı bir şekilde:

- Oluşturulan ve kaydedilen ve uygulama
- Bu uygulamaya uyarıları okuma izni verildi
- API'yi bağlama
- Son 48 saat içinde oluşturulan uyarıları döndürmek için PowerShell betiği kullanıldı

## <a name="related-topic"></a>İlgili konu

- [api'leri Uç Nokta için Microsoft Defender](exposed-apis-list.md)
- [Uygulama bağlamı ile Uç Nokta için Microsoft Defender erişme](exposed-apis-create-app-webapp.md)
- [Kullanıcı bağlamıyla Uç Nokta için Microsoft Defender erişme](exposed-apis-create-app-nativeapp.md)
