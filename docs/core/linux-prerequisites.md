---
title: "Linux에서 .NET Core의 필수 구성 요소"
description: "Linux 컴퓨터에서 .NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 Linux 버전 및 .NET Core 종속성입니다."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: johalex
ms.author: johalex
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: c30888895275ce18628ea341fee2d5a77080b8f6
ms.openlocfilehash: ff2b85372208e76c6c3becb551c41cdfb275d272
ms.contentlocale: ko-kr
ms.lasthandoff: 08/28/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a>Linux에서 .NET Core의 필수 구성 요소

이 문서에서는 Linux에서 .NET Core 응용 프로그램을 개발하는 데 필요한 종속성을 보여 줍니다. 다음에 나오는 지원되는 Linux 배포/버전 및 종속성은 Linux에서 .NET Core 앱을 개발하기 위한 두 가지 방법에 적용됩니다.

* [명령줄](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a>지원되는 Linux 버전

.NET Core 2.x는 다음 Linux 배포/버전에서 지원됩니다.

 * Red Hat Enterprise Linux 7 x64
 * CentOS 7 x64
 * Oracle Linux 7 x64
 * Fedora 25, 26 x64
 * Debian 9, 8.7+ x64 
 * Ubuntu 17.04, 16.04, 14.04  x64
 * Linux Mint 18, 17 x64
 * openSUSE 42.2+ x64
 * SLES(SUSE Enterprise Linux) 12 SP2+ x64

.NET Core 1.x는 다음 Linux 배포/버전에서 지원됩니다.

* Red Hat Enterprise Linux/CentOS/Oracle Linux 7 x64
* Fedora 24 x64
* Debian 8.2+ x64
* Ubuntu/Linux Mint 14.04, 16.04, 16.10*, 17 x64
* openSUSE 42.1(1.1) x64
> [!NOTE]
> Ubuntu/Linux 16.10은 .NET Core 1.1의 최신 패치 릴리스에서 지원됩니다.

지원 OS 버전 중 .NET Core 2.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x가 지원되는 OS 버전)를 참조하세요.

지원 OS 버전 중 .NET Core 1.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)(.NET Core 1.x가 지원되는 OS 버전)를 참조하세요.
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

## <a name="installing-net-core-prerequisites-with-the-native-installers"></a>기본 설치 관리자를 사용하여 .NET Core 필수 구성 요소 설치

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
4. `dotnet --help` 명령을 실행하여 설치 성공을 증명합니다.

     ```bash
     dotnet --help
     ```
> [!NOTE]
> Red Hat .NET 채널 액세스 등록 도움말은 Red Hat에서 [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)(.NET Core 1.1 1장 시작 가이드)를 참조하세요.


## <a name="install-net-core-for-ubuntu-1404-1604-1610--linux-mint-17-18-64-bit"></a>Ubuntu 14.04, 16.04, 16.10 및 Linux Mint 17, 18(64비트)에 대한 .NET Core 설치

> [!Warning]
> 시작하기 전에 시스템에서 .NET Core의 이전 버전을 제거하세요.

### <a name="add-the-dotnet-apt-get-feed"></a>dotnet apt-get 피드 추가

1. 원하는 버전의 호스트 패키지 피드를 설정합니다.

   **Ubuntu 14.04/Linux Mint 17**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
    **Ubuntu 16.04/Linux Mint 18**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
    **Ubuntu 16.10**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
2. .NET Core를 설치합니다.
# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

호스트 패키지 피드 설정 이후 Ubuntu 또는 Linux Mint에 .NET Core 2.0을 설치합니다.
```bash
sudo apt-get install dotnet-sdk-2.0.0
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

호스트 패키지 피드 설정 이후 Ubuntu 또는 Linux Mint에 .NET Core 1.x를 설치합니다.
```bash
sudo apt-get install dotnet-dev-1.0.4
```
---
3. `dotnet --help` 명령을 실행하여 설치 성공을 증명합니다.

 ```bash
     dotnet --help
 ```
## <a name="install-net-core-for-debian-8-or-9-64-bit"></a>Debian 8 또는 9(64비트)에 대한 .NET Core를 설치합니다.

> [!Warning]
> 시작하기 전에 시스템에서 .NET Core의 이전 버전을 제거하세요.

Debian 8 또는 9(64비트)에 .NET Core를 설치하려면:
1. 필수 구성 요소를 확인합니다. 
    ```bash
    sudo apt-get install curl libunwind8 gettext
    ```
2. .NET Core SDK 이진 파일(tarball)을 다운로드합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)   

```bash
     curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)   

```bash
     curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
```
---
3. .NET Core SDK 이전 파일을 추출합니다.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. PATH에 dotnet을 추가합니다.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. `dotnet --help` 명령을 실행하여 설치 성공을 증명합니다.

     ```bash
     dotnet --help
     ```

## <a name="install-net-core-for-fedora-24-25-or-26-64-bit"></a>Fedora 24, 25 또는 26(64비트)에 대한 .NET Core 설치

> [!Warning]
> 시작하기 전에 시스템에서 .NET Core의 이전 버전을 제거하세요.

Fedora 26,25(.NET Core 2.x) 또는 24(.NET Core 1.x)에 대한 .NET Core를 설치하려면: 
1. 필수 구성 요소를 확인합니다. 
    ```bash
    sudo dnf install libunwind libicu
    ```
2. .NET Core SDK 이진 파일(tarball)을 다운로드합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Fedora 26 또는 25**

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Fedora 24**

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
```

---
3. .NET Core SDK 이전 파일을 추출합니다.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. PATH에 dotnet을 추가합니다.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. `dotnet --help` 명령을 실행하여 설치 성공을 증명합니다.

     ```bash
     dotnet --help
     ```
## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a>CentOS 7.1(64비트) 및 Oracle Linux 7.1(64비트)에 대한 .NET Core 설치

> [!Warning]
> 시작하기 전에 시스템에서 .NET Core의 이전 버전을 제거하세요.

CentOS 7.1(64비트) 및 Oracle Linux 7.1(64비트)에 대한 .NET Core를 설치하려면:

1. 필수 구성 요소를 확인합니다.
    ```bash
    sudo dnf install libunwind libicu
    ```
2. .NET Core SDK 이진 파일(tarball)을 다운로드합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
```

---
3. .NET Core SDK 이전 파일을 추출합니다.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. PATH에 dotnet을 추가합니다.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. `dotnet --help` 명령을 실행하여 설치 성공을 증명합니다.

     ```bash
     dotnet --help
     ```
## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit-net-core-2x-and-opensuse-64-bit"></a>SUSE Linux Enterprise Server(64비트)(.NET Core 2.x) 및 openSUSE(64비트)에 대한 .NET Core 설치

> [!Warning]
> 시작하기 전에 시스템에서 .NET Core의 이전 버전을 제거하세요.

NET Core 2.x에 SLES(SUSE Linux Enterprise Server) 12 SP2(64비트) 및 openSUSE 42.2에 대한 .NET Core를 설치하거나 .NET Core 1.x에 openSUSE 42.1(64비트)을 설치하려면:

1. 필수 구성 요소를 확인합니다.
    ```bash
    sudo zypper install libunwind libicu
    ```
2. .NET Core SDK 이진 파일(tarball)을 다운로드합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**SLES 12 SP2, openSUSE 42.2**

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**openSUSE 42.1**

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
```

---
3. .NET Core SDK 이전 파일을 추출합니다.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. PATH에 dotnet을 추가합니다.
    ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. `dotnet --help` 명령을 실행하여 설치 성공을 증명합니다.

     ```bash
     dotnet --help
     ```

> [!IMPORTANT]
> 지원되는 Linux 배포/버전의 .NET Core 2.x 설치에 문제가 있는 경우 설치된 배포/버전은 [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0)(2.0 알려진 문제) 항목을 참조하세요.
> [!IMPORTANT]
> 지원되는 Linux 배포/버전의 .NET Core 1.x 설치에 문제가 있는 경우 설치된 배포/버전은 [1.0.0 Known issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md)(1.0.0 알려진 문제) 및 [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md)(1.0.1 알려진 문제) 항목을 참조하세요.
