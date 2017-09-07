---
title: "Linux에서 .NET Core의 필수 구성 요소"
description: "Linux 컴퓨터에서 .NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 Linux 버전 및 .NET Core 종속성입니다."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 7bbb8405f39a52d2798fd1dbc78f3116cb3bedbb
ms.openlocfilehash: 9864ffa31caa007cb649a9e6e8913863d9cb2c35
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a>Linux에서 .NET Core의 필수 구성 요소

이 문서에서는 Linux에서 .NET Core 응용 프로그램을 개발하는 데 필요한 종속성을 보여 줍니다. 다음에 나오는 지원되는 Linux 배포/버전 및 종속성은 Linux에서 .NET Core 앱을 개발하기 위한 두 가지 방법에 적용됩니다.

* [즐겨 찾는 편집기를 사용하는 명령줄](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a>지원되는 Linux 버전

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.0은 단일 운영 체제로 Linux를 처리합니다. 지원되는 Linux 배포판에 대한 단일 Linux 빌드(칩 아키텍처 당)가 있습니다.

.NET Core 2.x는 다음 Linux x64 배포/버전에서 지원됩니다.

 * Red Hat Enterprise Linux 7
 * CentOS 7
 * Oracle Linux 7
 * Fedora 25, Fedora 26
 * Debian 8.7 이상 버전 
 * Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04
 * Linux Mint 18, Linux Mint 17
 * openSUSE 42.2 이상 버전
 * SLES(SUSE Enterprise Linux) 12 SP2 이상 버전

지원 OS 버전 중 .NET Core 2.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x가 지원되는 OS 버전)를 참조하세요.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x는 다음 Linux x64 배포/버전에서 지원됩니다.

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 24
* Debian 8.2 이상 버전
* Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*
 * Ubuntu 16.10은 .NET Core 1.1의 최신 패치 릴리스에서 지원됩니다.
* Linux Mint 17
* openSUSE 42.1 이상 버전(.NET Core 1.1)

지원 OS 버전 중 .NET Core 1.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)(.NET Core 1.x가 지원되는 OS 버전)를 참조하세요.

---

## <a name="linux-distribution-dependencies"></a>Linux 배포 종속성

### <a name="ubuntu"></a>Ubuntu

Ubuntu 배포에는 다음과 같은 라이브러리 설치가 필요합니다.

* libunwind8
* libunwind8-dev
* gettext
* libicu-dev
* liblttng-ust-dev
* libcurl4-openssl-dev
* libssl-dev
* uuid-dev
* unzip

### <a name="centos"></a>CentOS

CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.

* deltarpm
* epel-release
* unzip
* libunwind
* gettext
* libcurl-devel
* openssl-devel
* zlib
* libicu-devel

종속성에 대한 자세한 내용은 [자체 포함 Linux 응용 프로그램](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>기본 설치 관리자를 사용하여 .NET Core 종속성 설치

.NET Core 기본 설치 관리자는 지원되는 Linux 배포/버전에서 사용할 수 있습니다. 기본 설치 관리자를 사용하려면 서버에 대한 관리자(sudo) 권한이 필요합니다. 기본 설치 관리자를 사용하는 장점은 모든 .NET Core 기본 종속성을 설치한다는 것입니다. 기본 설치 관리자는 .NET Core SDK 시스템 차원을 설치합니다.

Linux에는 두 가지 패키지 선택 항목이 있습니다.

* 피드 기반 패키지 관리자 사용(예: Ubuntu의 경우 apt-get, CentOS/RHEL의 경우 yum).
* 패키지 자체 사용(DEB 또는 RPM).

### <a name="scripting-installs-with-the-net-core-installer-script"></a>.NET Core 설치 관리자 스크립트를 사용하여 설치 스크립팅

`dotnet-install` 스크립트는 CLI 도구 체인 및 공유 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. [CLI GitHub 리포지토리](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain)에서 스크립트를 다운로드할 수 있습니다.

설치 관리자 bash 스크립트는 자동화 시나리오 및 비관리자 설치에 사용됩니다. 또한 이 스크립트는 PowerShell 스위치를 읽으므로 Linux/OS X 시스템에서 스크립트와 함께 사용할 수 있습니다.

> [!IMPORTANT]
> 스크립트를 실행하기 전에 필요한 모든 [종속성](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)을 설치하세요.

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a>RHEL(Red Hat Enterprise Linux) 7에 대한 .NET Core 설치

RHEL 7에 .NET Core를 설치하려면 다음과 같이 합니다.

1. RHEL 7 구독에 따라 사용할 수 있는 Red Hat .NET 채널을 사용하도록 설정합니다.
    * Red Hat Enterprise 7 Server의 경우 다음을 사용합니다.
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * Red Hat Enterprise 7 Workstation의 경우 다음을 사용합니다.
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * Red Hat Enterprise 7 HPC Compute Node의 경우 다음을 사용합니다.
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. scl 도구를 설치합니다.

    ```bash
    yum install scl-utils
    ```
    
3. .NET Core 설치

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.0 SDK 및 런타임 설치:

   ```bash
   yum install rh-dotnet20
   ```

사용자 환경에 대해 .NET Core 2.0 SDK/런타임을 사용하도록 설정:

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

.NET Core 1.1 SDK 및 런타임 설치:

   ```bash
   yum install rh-dotnetcore11
   ```

사용자 환경에 대해 .NET Core 1.1 SDK 및 런타임을 사용하도록 설정:

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

**.NET Core 1.0**

.NET Core 1.0 SDK 및 런타임 설치:

   ```bash
   yum install rh-dotnetcore10
   ```

사용자 환경에 대해 .NET Core 1.0 SDK 및 런타임을 사용하도록 설정:

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. `dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.

     ```bash
     dotnet --version
     ```

Red Hat .NET 채널 액세스 등록 도움말은 Red Hat에서 [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)(.NET Core 1.1 1장 시작 가이드)를 참조하세요.

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a>Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18(64 비트)에 대한 .NET Core 설치

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. 신뢰할 수 있는 것으로 Microsoft 제품 키를 등록합니다.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. 원하는 버전의 호스트 패키지 피드를 설정합니다.

   **Ubuntu 17.04**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 16.04/Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 14.04/Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. .NET Core를 설치합니다.

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. `dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. 원하는 버전의 호스트 패키지 피드를 설정합니다.

   **Ubuntu 16.10**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  **Ubuntu 16.04/Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   **Ubuntu 14.04/Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. Ubuntu 또는 Linux Mint에 .NET Core 1.x를 설치합니다.

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. `dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a>Debian 8 또는 Debian 9(64비트)에 대한 .NET Core를 설치합니다.

Debian 8 또는 Debian 9(64비트)에 .NET Core를 설치하려면:

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

> [!NOTE]
> tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. 시스템 구성 요소를 설치합니다.

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. 신뢰할 수 있는 Microsoft 제품 키를 등록합니다.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. Microsoft 제품 피드를 등록합니다.

   **Debian 9(Stretch)**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   **Debian 8(Jessie)**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. .NET Core SDK 이전 파일을 추출합니다.

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. PATH에 dotnet을 추가합니다.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. 필수 구성 요소를 확인합니다.

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. .NET Core SDK 이진 파일(tarball)을 다운로드합니다.

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. .NET Core SDK 이전 파일을 추출합니다.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. PATH에 dotnet을 추가합니다.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. `dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a>Fedora 24, Fedora 25 또는 Fedora 26(64비트)에 대한 .NET Core 설치

Fedora 26, Fedora 25(.NET Core 2.x) 또는 Fedora 24(.NET Core 1.x)에 대한 .NET Core를 설치하려면:

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

> [!NOTE]
> tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Fedora 26 또는 Fedora 25**

2. Microsoft 서명 키를 등록합니다.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. dotnet 제품 피드를 추가합니다.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. .NET Core SDK를 설치합니다.

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. PATH에 dotnet을 추가합니다.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Fedora 24**

2. 필수 구성 요소를 확인합니다.

   ```bash
   sudo dnf install libunwind libicu
   ```

3. .NET Core SDK 이진 파일(tarball)을 다운로드합니다.

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. .NET Core SDK 이전 파일을 추출합니다.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. PATH에 dotnet을 추가합니다.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. `dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a>CentOS 7.1(64비트) 및 Oracle Linux 7.1(64비트)에 대한 .NET Core 설치

CentOS 7.1(64비트) 및 Oracle Linux 7.1(64비트)에 대한 .NET Core를 설치하려면:

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

> [!NOTE]
> tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Microsoft 서명 키를 등록합니다.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Microsoft 제품 피드를 추가합니다.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. .NET Core SDK를 설치합니다.

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. PATH에 dotnet 추가

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. 필수 구성 요소를 확인합니다.

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. .NET Core SDK 이진 파일(tarball)을 다운로드합니다.

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. .NET Core SDK 이전 파일을 추출합니다.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. PATH에 dotnet을 추가합니다.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. `dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a>SUSE Linux Enterprise Server(64비트)에 대한 .NET Core 설치

SLES(SUSE Linux Enterprise Server) 12 SP2(64비트)에 대한 .NET Core 2.x을 설치하려면:

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. dotnet 제품 피드를 추가합니다.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. .NET Core SDK를 설치합니다.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. PATH에 dotnet을 추가합니다.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. `dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a>openSUSE(64비트)용 .NET Core 설치

openSUSE용 .NET Core 2.x 또는 openSUSE(64비트)용 .NET Core 1.x를 설치하려면:

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

> [!NOTE]
> tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Microsoft 서명 키를 등록합니다.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. dotnet 제품 피드를 추가합니다.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. .NET Core SDK를 설치합니다.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. PATH에 dotnet을 추가합니다.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. 필수 구성 요소를 확인합니다.

   ```bash
   sudo zypper install libunwind libicu
   ```

3. .NET Core SDK 이진 파일(tarball)을 다운로드합니다.

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. .NET Core SDK 이전 파일을 추출합니다.
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. PATH에 dotnet을 추가합니다.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. `dotnet --version` 명령을 실행하여 설치 성공을 증명합니다.

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> 지원되는 Linux 배포/버전의 .NET Core 2.x 설치에 문제가 있는 경우 설치된 배포/버전은 [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0)(2.0 알려진 문제) 항목을 참조하세요. 
>
> 지원되는 Linux 배포/버전의 .NET Core 1.x 설치에 문제가 있는 경우 설치된 배포/버전은 [1.0.0 Known issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md)(1.0.0 알려진 문제) 및 [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md)(1.0.1 알려진 문제) 항목을 참조하세요.

