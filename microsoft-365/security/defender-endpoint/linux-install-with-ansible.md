---
title: Ansible ile Linux'ta Uç Nokta için Microsoft Defender dağıtma
ms.reviewer: ''
description: Ansible kullanarak Linux'ta Uç Nokta için Microsoft Defender dağıtmayı açıklar.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos, fedora, amazon linux 2
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: a35c50a941c7398c2c0722233627fe76f36f6afe
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522091"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Ansible ile Linux'ta Uç Nokta için Microsoft Defender dağıtma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Bu makalede Ansible kullanarak Linux'ta Uç Nokta için Defender'ın nasıl dağıtılacağı açıklanmaktadır. Başarılı bir dağıtım için aşağıdaki görevlerin tümünün tamamlanması gerekir:

- [Ekleme paketini indirme](#download-the-onboarding-package)
- [Ansible YAML dosyaları oluşturma](#create-ansible-yaml-files)
- [Dağıtım](#deployment)
- [Başvurular](#references)

## <a name="prerequisites-and-system-requirements"></a>Önkoşullar ve sistem gereksinimleri

Başlamadan önce, geçerli yazılım sürümü için önkoşulların ve sistem gereksinimlerinin açıklaması [için Linux'ta Uç Nokta için Ana Defender sayfasına](microsoft-defender-endpoint-linux.md) bakın.

Ayrıca Ansible dağıtımı için Ansible yönetim görevleri hakkında bilgi sahibi olmanız, Ansible'ı yapılandırmanız ve playbook'ları ve görevleri dağıtmayı bilmeniz gerekir. Ansible'ın aynı görevi tamamlamak için birçok yolu vardır. Bu yönergelerde, paketin dağıtılmasına yardımcı olmak için *apt* ve *unarchive* gibi desteklenen Ansible modüllerinin kullanılabilir olduğu varsayılır. Kuruluşunuz farklı bir iş akışı kullanabilir. Ayrıntılar için [Ansible belgelerine](https://docs.ansible.com/) bakın.

- Ansible'ın en az bir bilgisayara yüklenmesi gerekir (Ansible bunu denetim düğümü olarak çağırır).
- SSH, denetim düğümü ile tüm yönetilen düğümler (uç nokta için Defender'ın yüklü olacağı cihazlar) arasında bir yönetici hesabı için yapılandırılmalıdır ve ortak anahtar kimlik doğrulaması ile yapılandırılması önerilir.
- Aşağıdaki yazılım tüm yönetilen düğümlere yüklenmelidir:
  - Curl
  - python-apt

- Tüm yönetilen düğümler veya ilgili dosyada `/etc/ansible/hosts` aşağıdaki biçimde listelenmelidir:

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Ping testi:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>Ekleme paketini indirme

Ekleme paketini Microsoft 365 Defender portalından indirin:

1. Microsoft 365 Defender portalında **Ayarlar > Uç Noktalar > Cihaz yönetimi > Ekleme'ye** gidin.
2. İlk açılan menüde işletim sistemi olarak **Linux Server'ı** seçin. İkinci açılan menüde dağıtım yöntemi olarak **Tercih ettiğiniz Linux yapılandırma yönetim aracını** seçin.
3. **Ekleme paketini indir'i** seçin. Dosyayı WindowsDefenderATPOnboardingPackage.zip olarak kaydedin.

   :::image type="content" source="images/portal-onboarding-linux-2.png" alt-text="Ekleme paketini indir seçeneği" lightbox="images/portal-onboarding-linux-2.png":::

4. Komut isteminden, dosyanın size ait olduğunu doğrulayın. Arşivin içeriğini ayıklayın:

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a>Ansible YAML dosyaları oluşturma

Bir playbook'a veya göreve katkıda bulunabilecek bir alt görev veya rol dosyaları oluşturun.

- Ekleme görevini oluşturun: `onboarding_setup.yml`

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- Uç Nokta için Defender deposunu ve anahtarını ekleyin: `add_apt_repo.yml`

    Linux'ta Uç Nokta için Defender aşağıdaki kanallardan birinden dağıtılabilir (aşağıda *[channel]* olarak belirtilir): *insider-fast*, *insider-slow* veya *prod*. Bu kanalların her biri bir Linux yazılım deposuna karşılık gelir.

    Kanal seçimi, cihazınıza sunulan güncelleştirmelerin türünü ve sıklığını belirler. *Insider'ların hızlı* olduğu cihazlar, güncelleştirmeleri ve yeni özellikleri ilk alan cihazlardır ve daha sonra *insider'ların yavaş* ve son olarak *prod* tarafından takip edilir.

    Yeni özellikleri önizlemek ve erken geri bildirim sağlamak için kuruluşunuzdaki bazı cihazları *insider hızlı veya insider yavaş* kullanacak şekilde yapılandırmanız önerilir.

    > [!WARNING]
    > İlk yüklemeden sonra kanalın değiştirilmesi için ürünün yeniden yüklenmesi gerekir. Ürün kanalını değiştirmek için: Mevcut paketi kaldırın, cihazınızı yeni kanalı kullanacak şekilde yeniden yapılandırın ve paketi yeni konumdan yüklemek için bu belgedeki adımları izleyin.

    Dağıtımınızı ve sürümünüzü not edin ve altında `https://packages.microsoft.com/config/[distro]/`onun için en yakın girdiyi belirleyin.

    Aşağıdaki komutlarda *[distro]* ve *[version]* sözcüklerini tanımladığınız bilgilerle değiştirin.

    > [!NOTE]
    > Oracle Linux ve Amazon Linux 2 olması durumunda *[distro]* yerine "rhel" yazın. Amazon Linux 2 için *[version]* yerine "7" yazın. Oracle kullanmak için *[version]* yerine Oracle Linux sürümünü yazın.

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      url: https://packages.microsoft.com/keys/microsoft.asc
      state: present
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [codename] main
      update_cache: yes
      state: present
      filename: microsoft-[channel]
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/ 
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Ansible yüklemesini oluşturun ve YAML dosyalarını kaldırın.

    - Apt tabanlı dağıtımlar için aşağıdaki YAML dosyasını kullanın:

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - dnf tabanlı dağıtımlar için aşağıdaki YAML dosyasını kullanın:

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a>Dağıtım

Şimdi görev dosyalarını veya ilgili dizin altında `/etc/ansible/playbooks/` çalıştırın.

- Yükleme:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> Ürün ilk kez başlatıldığında en son kötü amaçlı yazılımdan koruma tanımlarını indirir. İnternet bağlantınıza bağlı olarak bu işlem birkaç dakika kadar sürebilir.

- Doğrulama/yapılandırma:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- Kaldırma:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>Günlük yükleme sorunları

Bir hata oluştuğunda yükleyici tarafından oluşturulan otomatik olarak oluşturulan günlüğü bulma hakkında daha fazla bilgi için bkz. [Günlük yükleme sorunları](linux-resources.md#log-installation-issues) .

## <a name="operating-system-upgrades"></a>İşletim sistemi yükseltmeleri

İşletim sisteminizi yeni bir ana sürüme yükseltirken, önce Linux'ta Uç Nokta için Defender'ı kaldırmanız, yükseltmeyi yüklemeniz ve son olarak cihazınızda Linux'ta Uç Nokta için Defender'ı yeniden yapılandırmanız gerekir.

## <a name="references"></a>Başvurular

- [YUM depoları ekleme veya kaldırma](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [dnf paket yöneticisi ile paketleri yönetme](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [APT depoları ekleme ve kaldırma](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [apt paketlerini yönetme](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>Ayrıca bkz.
- [Sistem durumu sorunlarını araştırın](health-status.md)
