---
title: Cihazları İş için Microsoft Defender ekleme
description: Cihazlarınızı ilk günden korumak için İş için Defender'a cihazları ekleme hakkında bilgi edinin.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 10/24/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365solution-mdb-setup
- highpri
- tier1
ms.openlocfilehash: 674b48c5c558cb4d31df85e439c1eb216c09f00c
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687618"
---
# <a name="onboard-devices-to-microsoft-defender-for-business"></a>Cihazları İş için Microsoft Defender ekleme

İş için Defender ile, şirketinizin cihazlarını eklemek için aralarından seçim yapabileceğiniz çeşitli seçenekler vardır. Bu makalede bu seçeneklerde size yol gösterilir ve eklemenin nasıl çalıştığına ilişkin bir genel bakış sağlanır.

## <a name="what-to-do"></a>Yapılması gerekenler

1. Bir sekme seçin: 
   - **Windows 10 ve 11**
   - **Mac**
   - **Sunucular** (YENİ! Windows Server veya Linux Server)
   - **Mobil** (iOS/iPadOS veya Android cihazlar için)
2. Ekleme seçeneklerinizi görüntüleyin ve seçili sekmedeki yönergeleri izleyin.
3. Sonraki adımlarınıza geçin.

## <a name="windows-10-and-11"></a>[**Windows 10 ve 11**](#tab/Windows10and11)

## <a name="windows-10-and-11"></a>Windows 10 ve 11

Windows istemci cihazlarını İş için Defender'a eklemek için aşağıdaki seçeneklerden birini belirleyin:

- [Yerel betik](#local-script-for-windows-10-and-11) (cihazları Microsoft 365 Defender portalında el ile ekleme için)
- [grup ilkesi](#group-policy-for-windows-10-and-11) (kuruluşunuzda zaten grup ilkesi kullanıyorsanız)
- [Microsoft Intune](#intune-for-windows-10-and-11) (zaten Intune kullanıyorsanız)

### <a name="local-script-for-windows-10-and-11"></a>Windows 10 ve 11 için yerel betik

Windows istemci cihazlarını eklemek için yerel bir betik kullanabilirsiniz. Bir cihazda ekleme betiğini çalıştırdığınızda: 

- Bu güven henüz yoksa Azure Active Directory ile bir güven oluşturur.
- Henüz kaydedilmemişse cihazı Microsoft Intune kaydeder ve ardından cihazı İş için Defender'a ekler. 
- Yerel betik yöntemi şu anda Intune sahip olmasanız bile çalışır ve bu, İş için Defender müşterileri için önerilen yöntemdir.

> [!TIP]
> Yerel betik yöntemini kullanırken bir kerede en fazla 10 cihaz eklemenizi öneririz.

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın.

2. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları'nı** seçin ve ardından **Cihaz yönetimi'nin** altında **Ekleme'yi** seçin.

3. **Windows 10 ve 11'i** seçin ve ardından **Dağıtım yöntemi** bölümünde **Yerel betik'i** seçin. 

4. **Ekleme paketini indir'i** seçin. Ekleme paketini çıkarılabilir bir sürücüye kaydetmenizi öneririz.

5. Bir Windows cihazında, yapılandırma paketinin içeriğini Masaüstü klasörü gibi bir konuma ayıklayın. adlı `WindowsDefenderATPLocalOnboardingScript.cmd`bir dosyanız olmalıdır. 

6. Bir komut istemini yönetici olarak açın.

7. Betik dosyasının konumunu yazın. Örneğin, dosyayı Desktop klasörüne kopyaladıysanız `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`yazın ve Enter tuşuna basın (veya **Tamam'ı** seçin).

8. Betik çalıştırıldıktan sonra [bir algılama testi çalıştırın](#run-a-detection-test-on-a-windows-10-or-11-device).

### <a name="group-policy-for-windows-10-and-11"></a>Windows 10 ve 11 için grup ilkesi

Windows istemcilerini eklemek için grup ilkesi kullanmayı tercih ediyorsanız grup ilkesi [kullanarak Windows cihazlarını ekleme](../defender-endpoint/configure-endpoints-gp.md) yönergelerini izleyin. Bu makalede, Uç Nokta için Microsoft Defender ekleme adımları açıklanmaktadır. İş için Defender'a ekleme adımları benzerdir.

### <a name="intune-for-windows-10-and-11"></a>Windows 10 ve 11 için Intune

Microsoft Endpoint Manager yönetim merkezini ([https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) kullanarak Windows istemcilerini ve diğer cihazları Intune'a ekleyebilirsiniz. Cihazları Intune kaydetmek için kullanılabilecek çeşitli yöntemler vardır. Aşağıdaki yöntemlerden birini kullanmanızı öneririz:

- [Şirkete ait veya şirket tarafından yönetilen cihazlar için Windows otomatik kaydını etkinleştirme](#enable-automatic-enrollment-for-windows-10-and-11)
- [Kullanıcılardan kendi Windows 10/11 cihazlarını Intune kaydetmelerini isteyin](#ask-users-enroll-their-own-windows-10-and-11-devices)

#### <a name="enable-automatic-enrollment-for-windows-10-and-11"></a>Windows 10 ve 11 için otomatik kaydı etkinleştirme

Otomatik kaydı ayarladığınızda, kullanıcılar iş hesabını cihaza ekler. Arka planda cihaz Azure Active Directory'ye (Azure AD) kaydolup katılır ve Intune kaydedilir.

1. Azure portal ([https://portal.azure.com/](https://portal.azure.com/)) gidin ve oturum açın.

2. **Azure Active Directory** > **Mobility (MDM ve MAM)** > **Microsoft Intune'ı** seçin.

3. **MDM Kullanıcı kapsamını** ve **MAM kullanıcı kapsamını** yapılandırın.

   :::image type="content" source="media/mem-mam-scope-azure-ad.png" alt-text="Intune'da MDM kullanıcı kapsamını ve MAM kullanıcı kapsamını ayarlamanın ekran görüntüsü.":::

   - MDM Kullanıcı kapsamı için, tüm kullanıcıların Windows cihazlarını otomatik olarak kaydedebilmesi için **Tümü** seçeneğini belirlemenizi öneririz.
   - MAM kullanıcı kapsamı bölümünde URL'ler için aşağıdaki varsayılan değerleri öneririz:

       - **MDM Kullanım Koşulları URL’si**
       - **MDM Bulma URL’si**
       - **MAM uyumluluk URL’si**

4. **Kaydet**'i seçin.

5. Bir cihaz Intune kaydedildikten sonra, bunu İş için Defender'daki bir cihaz grubuna ekleyebilirsiniz. [İş için Defender'da cihaz grupları hakkında daha fazla bilgi edinin](mdb-create-edit-device-groups.md).

> [!TIP]
> Daha fazla bilgi için bkz. [Windows otomatik kaydını etkinleştirme](/mem/intune/enrollment/windows-enroll).

#### <a name="ask-users-enroll-their-own-windows-10-and-11-devices"></a>Kullanıcılardan kendi Windows 10 ve 11 cihazlarını kaydetmelerini isteyin

1. Kaydın nasıl çalıştığını görmek için aşağıdaki videoyu izleyin:<br/><br/>

   > [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]  

2. Bu makaleyi kuruluşunuzdaki kullanıcılarla paylaşın: [Windows 10/11 cihazlarını Intune'a kaydedin](/mem/intune/user-help/enroll-windows-10-device).

3. Bir cihaz Intune kaydedildikten sonra, bunu İş için Defender'daki bir cihaz grubuna ekleyebilirsiniz. [İş için Defender'da cihaz grupları hakkında daha fazla bilgi edinin](mdb-create-edit-device-groups.md).

### <a name="run-a-detection-test-on-a-windows-10-or-11-device"></a>Windows 10 veya 11 cihazda algılama testi çalıştırma

Windows cihazlarını İş için Defender'a ekledikten sonra, her şeyin düzgün çalıştığından emin olmak için cihazda bir algılama testi çalıştırabilirsiniz.

1. Windows cihazında bir klasör oluşturun: `C:\test-MDATP-test`.

2. Yönetici olarak Komut İstemi'ni açın.

3. Komut İstemi penceresinde aşağıdaki PowerShell komutunu çalıştırın:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Komut çalıştırıldıktan sonra Komut İstemi penceresi otomatik olarak kapatılır. Başarılı olursa algılama testi tamamlandı olarak işaretlenir ve yeni eklenen cihaz için Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)) yaklaşık 10 dakika içinde yeni bir uyarı görünür.

## <a name="view-a-list-of-onboarded-devices"></a>Eklenen cihazların listesini görüntüleme

İş için Defender'a eklenen cihazların listesini görüntülemek için Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com) ) gidin. Gezinti bölmesinde **Varlık** > **Cihazları'na** gidin.

## <a name="next-steps"></a>Sonraki adımlar

- Eklenecek başka cihazlarınız varsa, bu cihazların sekmesini seçin ([Windows 10 ve 11, Mac, Sunucular veya Mobil cihazlar](#what-to-do)) ve bu sekmedeki yönergeleri izleyin.
- Cihazları eklemeyi bitirdiyseniz [5. Adım: İş için Defender'da güvenlik ayarlarınızı ve ilkelerinizi yapılandırma](mdb-configure-security-settings.md) bölümüne gidin
- Bkz. [İş için Defender'ı kullanmaya başlama](mdb-get-started.md).

## <a name="mac"></a>[**Mac**](#tab/mac)

## <a name="mac"></a>Mac

> [!NOTE]
> [Mac'i eklemek için yerel bir betik](#local-script-for-mac) kullanmanızı öneririz. [mac için kaydı Intune kullanarak ayarlayabilmenize](/mem/intune/enrollment/macos-enroll) rağmen, yerel betik Mac'i İş için Defender'a eklemek için en basit yöntemdir. 

Mac'i eklemek için aşağıdaki seçeneklerden birini belirleyin:

- [Mac için yerel betik](#local-script-for-mac) (*önerilir*)
- [Mac için Intune](#intune-for-mac) (zaten Intune kullanıyorsanız)

### <a name="local-script-for-mac"></a>Mac için yerel betik

Mac'te yerel betiği çalıştırdığınızda: 

- Bu güven henüz yoksa Azure Active Directory ile bir güven oluşturur.
- Henüz kaydedilmemişse Mac'i Microsoft Intune kaydeder ve ardından Mac'i İş için Defender'a ekler. 
- Bu yöntemi kullanarak bir kerede en fazla 10 cihaz eklemenizi öneririz.

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın.

2. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları'nı** seçin ve ardından **Cihaz yönetimi'nin** altında **Ekleme'yi** seçin.

3. **macOS'ı** seçin. **Dağıtım yöntemi** bölümünde **Yerel betik'i** seçin. 

4. **Ekleme paketini indir'i** seçin ve çıkarılabilir bir sürücüye kaydedin. Ayrıca **Yükleme paketini indir'i** seçin ve çıkarılabilir cihazınıza kaydedin.

5. Mac'te yükleme paketini yerel bir dizine olarak `wdav.pkg` kaydedin.

6. Ekleme paketini, yükleme paketi için kullandığınız dizine kaydedin `WindowsDefenderATPOnboardingPackage.zip` .

7. Kaydettiğinize gitmek için Bulucu'ya `wdav.pkg` gidin ve açın.

8. **Devam'ı** seçin, lisans koşullarını kabul edin ve istendiğinde parolanızı girin.

9. Microsoft'tan bir sürücünün yüklenmesine izin vermeniz istenir ("Sistem Uzantısı Engellendi" veya "Yükleme beklemede" veya her ikisi). Sürücü yüklemesine izin vermelisiniz: **Güvenlik Tercihlerini Aç'ı** veya **Sistem Tercihlerini** > **Aç Güvenlik & Gizlilik'i** ve ardından **İzin Ver'i** seçin.

10. Ekleme paketini çalıştırmak için Bash'te aşağıdaki Python komutunu kullanın: `/usr/bin/python MicrosoftDefenderATPOnboardingMacOs.sh`

Mac Intune kaydedildikten sonra bir cihaz grubuna ekleyebilirsiniz. [İş için Defender'da cihaz grupları hakkında daha fazla bilgi edinin](mdb-create-edit-device-groups.md).

### <a name="intune-for-mac"></a>Mac için Intune

Zaten Intune varsa, Microsoft Endpoint Manager yönetim merkezini ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) kullanarak Mac bilgisayarları kaydedebilirsiniz. Mac'i Intune'a kaydetmek için kullanılabilecek çeşitli yöntemler vardır. Aşağıdaki yöntemlerden birini öneririz:

- [Şirkete ait Mac için bir seçenek belirleyin](#options-for-company-owned-mac)
- [Kullanıcılardan kendi Mac'lerini Intune kaydetmelerini isteyin](#ask-users-to-enroll-their-own-mac-in-intune)

#### <a name="options-for-company-owned-mac"></a>Şirkete ait Mac için seçenekler

Şirket tarafından yönetilen Mac cihazlarını Intune kaydetmek için aşağıdaki seçeneklerden birini belirleyin:

| Seçeneği  | Açıklama  |
|---------|---------|
| Apple Otomatik Cihaz Kaydı |  Apple Business Manager veya Apple School Manager aracılığıyla satın alınan cihazlarda kaydı otomatikleştirmek için bu yöntemi kullanın. Otomatik cihaz kaydı kayıt profilini "havadan" dağıtır, böylece cihazlara fiziksel erişiminiz olması gerekmez. <br/><br/>Bkz. [Mac'i Apple Business Manager veya Apple School Manager ile otomatik olarak kaydetme](/mem/intune/enrollment/device-enrollment-program-enroll-macos). |
| Cihaz kayıt yöneticisi (DEM)  |  Büyük ölçekli dağıtımlar ve kuruluşunuzda kayıt kurulumuna yardımcı olabilecek birden çok kişi olduğunda bu yöntemi kullanın. Cihaz kayıt yöneticisi (DEM) izinleri olan biri, tek bir Azure Active Directory hesabıyla en fazla 1.000 cihazı kaydedebilir. Bu yöntem, cihazları kaydetmek için Şirket Portalı uygulamasını veya Microsoft Intune uygulamasını kullanır. Otomatik Cihaz Kaydı aracılığıyla cihazları kaydetmek için BIR DEM hesabı kullanamazsınız.<br/><br/> Bkz[. Cihaz kayıt yöneticisi hesabı kullanarak cihazları Intune kaydetme](/mem/intune/enrollment/device-enrollment-manager-enroll).  |
| Doğrudan kayıt  | Doğrudan kayıt, kullanıcı benzitesi olmayan cihazları kaydeder, bu nedenle bu yöntem tek bir kullanıcıyla ilişkilendirilmeyen cihazlar için en iyisidir. Bu yöntem, kaydettiğiniz Mac'lere fiziksel erişiminiz olmasını gerektirir. <br/><br/>Bkz [. Mac için Doğrudan Kayıt'ı kullanma](/mem/intune/enrollment/device-enrollment-direct-enroll-macos).      |

#### <a name="ask-users-to-enroll-their-own-mac-in-intune"></a>Kullanıcılardan kendi Mac'lerini Intune kaydetmelerini isteyin

İşletmeniz kişilerin kendi cihazlarını Intune kaydetmesini tercih ederse, kullanıcıları şu adımları izlemeye yönlendirin:

1. Şirket Portalı web sitesine ([https://portal.manage.microsoft.com/](https://portal.manage.microsoft.com/)) gidin ve oturum açın.

2. Cihazlarını eklemek için Şirket Portalı web sitesindeki yönergeleri izleyin.

3. konumundaki Şirket Portalı uygulamasını [https://aka.ms/EnrollMyMac](https://aka.ms/EnrollMyMac)yükleyin ve uygulamadaki yönergeleri izleyin.

### <a name="confirm-that-a-mac-is-onboarded"></a>Mac'in eklendiğini onaylayın

1. Cihazın şirketinizle ilişkili olduğunu onaylamak için Bash'te aşağıdaki Python komutunu kullanın:

   `mdatp health --field org_id`.

2. macOS 10.15 (Catalina) veya sonraki bir sürümü kullanıyorsanız cihazınızı korumak için İş için Defender'a onay verin. **Sistem Tercihleri** > **Güvenliği & Gizlilik** > **Gizliliği** > **Tam Disk Erişimi'ne** gidin. Değişiklik yapmak için iletişim kutusunun alt kısmındaki kilit simgesini seçin ve ardından **İş için Microsoft Defender** (veya gördüğünüz buysa **Uç Nokta için Defender**) öğesini seçin.

3. Cihazın eklendiğini doğrulamak için Bash'te aşağıdaki komutu kullanın:

   `mdatp health --field real_time_protection_enabled`

Bir cihaz Intune kaydedildikten sonra cihaz grubuna ekleyebilirsiniz. [İş için Defender'da cihaz grupları hakkında daha fazla bilgi edinin](mdb-create-edit-device-groups.md).

## <a name="view-a-list-of-onboarded-devices"></a>Eklenen cihazların listesini görüntüleme

İş için Defender'a eklenen cihazların listesini görüntülemek için Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com) ) gidin. Gezinti bölmesinde **Varlık** > **Cihazları'na** gidin.

## <a name="next-steps"></a>Sonraki adımlar

- Eklenecek başka cihazlarınız varsa, bu cihazların sekmesini seçin ([Windows 10 ve 11, Mac, Sunucular veya Mobil cihazlar](#what-to-do)) ve bu sekmedeki yönergeleri izleyin.
- Cihazları eklemeyi bitirdiyseniz [, 5. Adım: İş için Defender'da güvenlik ayarlarınızı ve ilkelerinizi yapılandırma](mdb-configure-security-settings.md) bölümüne gidin.
- Bkz. [İş için Defender'ı kullanmaya başlama](mdb-get-started.md).

## <a name="servers"></a>[**Sunucular**](#tab/Servers)

## <a name="servers"></a>Sunucular

> [!IMPORTANT]
> Windows Server veya Linux Server örneğini eklemeyi planlıyorsanız, İş için Microsoft Defender sunucuları (önizleme) gibi ek bir lisansa ihtiyacınız olacaktır. Alternatif olarak [Sunucular için Microsoft Defender](/azure/defender-for-cloud/defender-for-servers-introduction) kullanabilirsiniz; ancak Sunucular için Defender Plan 1 veya Plan 2 gibi bir kurumsal plan eklediğinizde İş için Defender deneyiminiz değişebilir. Daha fazla bilgi edinmek için bkz. [Microsoft uç nokta güvenlik aboneliklerinin bir karışımına sahipsem ne olur?](mdb-faq.yml#what-happens-if-i-have-a-mix-of-microsoft-endpoint-security-subscriptions).

Sunucunuz için işletim sistemini seçin:

- [Windows Server:](#windows-server)
- [Linux Server](#linux-server)

## <a name="windows-server"></a>Windows Server

> [!IMPORTANT]
> **Windows Server uç noktalarını ekleme özelliği şu anda önizleme aşamasındadır**. Genel kullanılabilirlik duyurulduğunda, eklenen her sunucu için bir İş için Microsoft Defender sunucuları lisansı satın alınmalıdır; aksi durumda bu sunucular kullanıma alınabilir.
> Windows Server uç noktasını eklemeden önce aşağıdaki gereksinimleri karşıladığınızdan emin olun:
> - **Önizleme özellikleri** ayarı açıktır. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ), **Ayarlar** > **Uç Noktaları** > **Genel** > **Gelişmiş özellikler****Önizleme özellikleri'ne** >  gidin.
> - Windows Server için zorlama kapsamı açık. **Ayarlar** > **Uç Noktaları** > **Yapılandırma yönetimi** > **Zorlama kapsamı'na** gidin. **MEM'den güvenlik yapılandırma ayarlarını zorunlu kılmak için MDE kullan'ı** seçin, **Windows Server'ı** ve ardından **Kaydet'i** seçin.

Yerel bir betik kullanarak bir Windows Server örneğini İş için Defender'a ekleyebilirsiniz.

### <a name="local-script-for-windows-server"></a>Windows Server için yerel betik

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın.

2. Gezinti bölmesinde **Ayarlar** > **Uç Noktaları'nı** seçin ve ardından **Cihaz yönetimi'nin** altında **Ekleme'yi** seçin.

3. **Windows Server 1803, 2019 ve 2022** gibi bir işletim sistemi seçin ve ardından **Dağıtım yöntemi** bölümünde **Yerel betik'i** seçin. 

   **R2 ve 2016 Windows Server 2012** seçerseniz, indirilip çalıştırılacak iki paketiniz olur: yükleme paketi ve ekleme paketi. Yükleme paketi, İş için Defender aracısını yükleyen bir MSI dosyası içerir. Ekleme paketi, Windows Server uç noktanızı İş için Defender'a ekleme betiğini içerir.

4. **Ekleme paketini indir'i** seçin. Ekleme paketini çıkarılabilir bir sürücüye kaydetmenizi öneririz.

   **R2 ve 2016 Windows Server 2012** seçtiyseniz **Yükleme paketini indir'i** de seçin ve paketi çıkarılabilir bir sürücüye kaydedin

5. Windows Server uç noktanızda, yükleme/ekleme paketinin içeriğini Masaüstü klasörü gibi bir konuma ayıklayın. adlı `WindowsDefenderATPLocalOnboardingScript.cmd`bir dosyanız olmalıdır. 

   R2 veya Windows Server 2016 Windows Server 2012 ekliıyorsanız, önce yükleme paketini ayıklayın.

6. Bir komut istemini yönetici olarak açın.

7. Windows Server 2012R2 veya Windows Server 2016 ekliyseniz aşağıdaki komutu çalıştırın:

   `Msiexec /i md4ws.msi /quiet` 

   Windows Server 1803, 2019 veya 2022'yi ekliıyorsanız, bu adımı atlayın ve 8. adıma geçin.

8. Betik dosyasının konumunu yazın. Örneğin, dosyayı Masaüstü klasörüne kopyaladıysanız `%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd`yazın ve Enter tuşuna basın (veya **Tamam'ı** seçin).

9. [Windows Server'da algılama testi çalıştırma bölümüne](#run-a-detection-test-on-windows-server) gidin.

### <a name="run-a-detection-test-on-windows-server"></a>Windows Server'da algılama testi çalıştırma

Windows Server uç noktanızı İş için Defender'a ekledikten sonra, her şeyin düzgün çalıştığından emin olmak için bir algılama testi çalıştırabilirsiniz:

1. Windows Server cihazında bir klasör oluşturun: `C:\test-MDATP-test`.

2. Yönetici olarak Komut İstemi'ni açın.

3. Komut İstemi penceresinde aşağıdaki PowerShell komutunu çalıştırın:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Komut çalıştırıldıktan sonra Komut İstemi penceresi otomatik olarak kapatılır. Başarılı olursa algılama testi tamamlandı olarak işaretlenir ve yeni eklenen cihaz için Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)) yaklaşık 10 dakika içinde yeni bir uyarı görünür.

## <a name="linux-server"></a>Linux Server

> [!IMPORTANT]
> **Linux Server uç noktalarını ekleme özelliği şu anda önizleme aşamasındadır**. Genel kullanılabilirlik duyurulduğunda, eklenen her sunucu için bir İş için Microsoft Defender sunucuları lisansı satın alınmalıdır; aksi durumda bu sunucular kullanıma alınabilir.
> Linux Server uç noktasını eklemeden önce aşağıdaki gereksinimleri karşıladığınızdan emin olun:
> - **Önizleme özellikleri** ayarı açıktır. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ), **Ayarlar** > **Uç Noktaları** > **Genel** > **Gelişmiş özellikler****Önizleme özellikleri'ne** >  gidin.
> - [Linux'ta Uç Nokta için Microsoft Defender önkoşullarını](../defender-endpoint/microsoft-defender-endpoint-linux.md#prerequisites) karşılarsınız.

### <a name="onboard-linux-server-endpoints"></a>Linux Server uç noktalarını ekleme

Bir Linux Server örneğini İş için Defender'a eklemek için aşağıdaki yöntemleri kullanabilirsiniz:

- **Yerel betik:** Bkz [. Linux'ta Uç Nokta için Microsoft Defender el ile dağıtma](../defender-endpoint/linux-install-manually.md).
- **Ansible:** Bkz [. Ansible ile Linux'ta Uç Nokta için Microsoft Defender dağıtma](../defender-endpoint/linux-install-with-ansible.md).
- **Şef:** Bkz. [Chef ile Linux'ta Uç Nokta için Defender'ı dağıtma](../defender-endpoint/linux-deploy-defender-for-endpoint-with-chef.md).
- **Kukla:** Bkz [. Puppet ile Linux'ta Uç Nokta için Microsoft Defender dağıtma](../defender-endpoint/linux-install-with-puppet.md).

> [!NOTE]
> Linux Server örneğini İş için Defender'a eklemek, [Linux'ta Uç Nokta için Microsoft Defender](../defender-endpoint/microsoft-defender-endpoint-linux.md) ekleme işlemiyle aynıdır.

## <a name="view-a-list-of-onboarded-devices"></a>Eklenen cihazların listesini görüntüleme

İş için Defender'a eklenen cihazların listesini görüntülemek için Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com) ) gidin. Gezinti bölmesinde **Varlık** > **Cihazları'na** gidin.

## <a name="next-steps"></a>Sonraki adımlar

- Eklenecek başka cihazlarınız varsa, bu cihazların sekmesini seçin ([Windows 10 ve 11, Mac, Sunucular veya Mobil cihazlar](#what-to-do)) ve bu sekmedeki yönergeleri izleyin.
- Cihazları eklemeyi bitirdiyseniz [, 5. Adım: İş için Defender'da güvenlik ayarlarınızı ve ilkelerinizi yapılandırma](mdb-configure-security-settings.md) bölümüne gidin.
- Bkz. [İş için Defender'ı kullanmaya başlama](mdb-get-started.md).

## <a name="mobile-devices"></a>[**Mobil cihazlar**](#tab/mobiles)

## <a name="mobile-devices"></a>Mobil cihazlar

Android ve iOS/iPadOS cihazları gibi mobil cihazları eklemek için Microsoft Intune kullanın. Bu cihazları Intune kaydetme konusunda yardım almak için aşağıdaki kaynaklara bakın:

- [Android cihazları kaydetme](/mem/intune/enrollment/android-enroll)
- [iOS veya iPadOS cihazlarını kaydetme](/mem/intune/enrollment/ios-enroll)

Bir cihaz Intune kaydedildikten sonra cihaz grubuna ekleyebilirsiniz. [İş için Defender'da cihaz grupları hakkında daha fazla bilgi edinin](mdb-create-edit-device-groups.md).

> [!NOTE]
> İş için Defender'ın tek başına sürümü, iOS ve Android cihazlarını eklemek için gereken Intune lisansını içermez. mobil cihazları eklemek için İş için Defender aboneliğinize Intune ekleyebilirsiniz. Intune Microsoft 365 İş Ekstra dahildir.

## <a name="view-a-list-of-onboarded-devices"></a>Eklenen cihazların listesini görüntüleme

İş için Defender'a eklenen cihazların listesini görüntülemek için Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com) ) gidin. Gezinti bölmesinde **Varlık** > **Cihazları'na** gidin.

## <a name="next-steps"></a>Sonraki adımlar

- Eklenecek başka cihazlarınız varsa, bu cihazların sekmesini seçin ([Windows 10 ve 11, Mac, Sunucular veya Mobil cihazlar](#what-to-do)) ve bu sekmedeki yönergeleri izleyin.
- Cihazları eklemeyi bitirdiyseniz [, 5. Adım: İş için Defender'da güvenlik ayarlarınızı ve ilkelerinizi yapılandırma](mdb-configure-security-settings.md) bölümüne gidin.
- Bkz. [İş için Defender'ı kullanmaya başlama](mdb-get-started.md).
