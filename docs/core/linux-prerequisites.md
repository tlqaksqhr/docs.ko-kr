---
title: Linux에서 .NET Core의 필수 구성 요소
description: Linux 컴퓨터에서 .NET Core 응용 프로그램을 개발, 배포 및 실행하기 위해 지원되는 Linux 버전 및 .NET Core 종속성입니다.
author: jralexander
ms.author: johalex
ms.date: 05/08/2018
ms.openlocfilehash: 41656bf8f18c2b66c35f0a65e4af0949db4464f9
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a>Linux에서 .NET Core의 필수 구성 요소

이 문서에서는 Linux에서 .NET Core 응용 프로그램을 개발하는 데 필요한 종속성을 보여 줍니다. 다음에 나오는 지원되는 Linux 배포/버전 및 종속성은 Linux에서 .NET Core 앱을 개발하기 위한 두 가지 방법에 적용됩니다.

* [즐겨 찾는 편집기를 사용하는 명령줄](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

> [!NOTE]
> .NET Core SDK 패키지는 프로덕션 서버/환경에서 필요하지 않습니다. .NET Core 런타임 패키지만 프로덕션 환경에 배포된 앱에 필요합니다. NET Core 런타임은 자체 포함된 배포의 일부로 앱으로 배포되지만 프레임워크 종속 배포된 앱에 대해 별도로 배포되어야 합니다. 프레임워크 종속 및 자체 포함된 배포 형식에 대한 자세한 내용은 [.NET Core 응용 프로그램 배포](./deploying/index.md)를 참조하세요. 또한 특정 지침은 [자체 포함된 Linux 응용 프로그램](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.

## <a name="supported-linux-versions"></a>지원되는 Linux 버전

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x는 단일 운영 체제로 Linux를 처리합니다. 지원되는 Linux 배포에 대한 단일 Linux 빌드(칩 아키텍처당)가 있습니다.

.NET Core 2.x는 다음 Linux 64비트(`x86_64` 또는 `amd64`) 배포/버전에서 지원됩니다.

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 27, 26
* Debian 9, 8.7 이상 버전
* Ubuntu 18.04, 17.10, 16.04, 14.04
* Linux Mint 18, 17
* openSUSE 42.3 이상 버전
* SUSE Enterprise Linux(SLES) 12 서비스 팩 2 이상

지원 OS 버전 중 .NET Core 2.x가 지원되는 운영 체제, 배포 및 버전, 수명 주기 정책 링크의 전체 목록은 [.NET Core 2.x가 지원되는 OS 버전](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)을 참조하세요.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x는 다음 Linux 64비트(`x86_64` 또는 `amd64`) 배포/버전에서 지원됩니다.

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 26
* Debian 8.2 이상 버전
* Ubuntu 16.04, 14.04
* Linux Mint 18, 17
* openSUSE 42.3 이상 버전(.NET Core 1.1)

지원 OS 버전 중 .NET Core 1.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)(.NET Core 1.x가 지원되는 OS 버전)를 참조하세요.

---

## <a name="linux-distribution-dependencies"></a>Linux 배포 종속성

다음은 예제로 사용됩니다. 정확한 버전 및 이름은 선택한 Linux 배포에 따라 약간 다를 수 있습니다.

### <a name="ubuntu"></a>Ubuntu

Ubuntu 배포에는 다음과 같은 라이브러리 설치가 필요합니다.

* libunwind8
* liblttng-ust0
* libcurl3
* libssl1.0.0
* libuuid1
* libkrb5-3
* zlib1g
* libicu52(14.x용)
* libicu55(16.x용)
* libicu57(17.x용)

### <a name="centos"></a>CentOS

CentOS 배포에는 다음과 같은 라이브러리 설치가 필요합니다.

* libunwind
* lttng-ust
* libcurl
* openssl-libs
* libuuid
* krb5-libs
* libicu
* zlib

종속성에 대한 자세한 내용은 [자체 포함 Linux 응용 프로그램](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)을 참조하세요.

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>기본 설치 관리자를 사용하여 .NET Core 종속성 설치

.NET Core 기본 설치 관리자는 지원되는 Linux 배포/버전에서 사용할 수 있습니다. 기본 설치 관리자를 사용하려면 서버에 대한 관리자(sudo) 권한이 필요합니다. 기본 설치 관리자를 사용하는 장점은 모든 .NET Core 기본 종속성을 설치한다는 것입니다. 기본 설치 관리자는 .NET Core SDK 시스템 차원을 설치합니다.

Linux에는 두 가지 패키지 선택 항목이 있습니다.

* 피드 기반 패키지 관리자 사용(예: Ubuntu의 경우 apt-get, CentOS/RHEL의 경우 yum).
* 패키지 자체 사용(DEB 또는 RPM).

### <a name="scripting-installs-with-the-net-core-installer-script"></a>.NET Core 설치 관리자 스크립트를 사용하여 설치 스크립팅

[dotnet-install 스크립트](./tools/dotnet-install-script.md)는 CLI 도구 체인 및 공유 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다. [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh)에서 스크립트를 다운로드할 수 있습니다.

설치 관리자 bash 스크립트는 자동화 시나리오 및 비관리자 설치에 사용됩니다. 또한 이 스크립트는 PowerShell 스위치를 읽으므로 Linux/OS X 시스템에서 스크립트와 함께 사용할 수 있습니다.

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a>지원되는 RHEL(Red Hat Enterprise Linux) 버전에 대한 .NET Core 설치

지원되는 RHEL 버전에 .NET Core를 설치하려면:

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

최신 설치 정보를 포함하는지 확인하려면 지원되는 RHEL 버전에 대한 [.NET Core 2.x SDK 및 런타임 설치 관리자 지침](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current)을 따릅니다.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2.  Red Hat Enterprise Linux 설치 정보에서 최신 .NET Core 1.1은 [.NET Core 1.1 시작 가이드](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)를 참조하세요.
     
**.NET Core 1.0**

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2.  Red Hat Enterprise Linux 설치 정보에서 최신 .NET Core 1.0은 [.NET Core 1.0 시작 가이드](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)를 참조하세요.

Red Hat .NET 채널 액세스 등록 도움말은 Red Hat에서 [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)(.NET Core 1.1 1장 시작 가이드)를 참조하세요.

---

## <a name="install-net-core-for-supported-ubuntu-and-linux-mint-distributionsversions-64-bit"></a>지원되는 Ubuntu 및 Linux Mint 배포/버전(64비트)에 대한 .NET Core 설치

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. 지원되는 Ubuntu 및 Linux Mint 배포/버전(64비트)에 대한 .NET Core 2.x 설치:

**.NET Core 2.0**

|런타임/SDK          |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|-------------------------|----------------|----------------|----------------------------|----------------------------|
|.NET Core 런타임 2.0.7  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.7)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.7)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.7)          |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.7)            |
|.NET Core 런타임 2.0.6  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.6)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|.NET Core 런타임 2.0.5  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.5)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|.NET Core SDK 2.1.105    |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.105)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.105)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.105)            |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.105)            |
|.NET Core SDK 2.1.103    |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.103)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|.NET Core SDK 2.0.3      |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.3)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |
|.NET Core SDK 2.0.0      |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.0)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.0)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.0)          |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.0)            |

**.NET Core 2.1**

>[!IMPORTANT]
> Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview)해야 합니다.

|런타임/SDK                  |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|---------------------------------|----------------|----------------|----------------------------|----------------------------|
|.NET Core 런타임 2.1.0-rc1      |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.0-rc1)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-rc1)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-rc1)            |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-rc1)            |
|.NET Core 런타임 2.1.0-미리 보기2 |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.0-preview2)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview2)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview2)            |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview2)            |
|.NET Core 런타임 2.1.0-미리 보기1 |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.0-preview1)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview1)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview1)            |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview1)            |
|.NET Core SDK 2.1.300-rc1  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.300-rc1)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-rc1)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-rc1)            |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-rc1)            |
|.NET Core SDK 2.1.300-미리 보기2   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.300-preview2)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview2)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview2)            |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview2)            |
|.NET Core SDK 2.1.300-미리 보기1   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.300-preview1)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview1)|[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview1)            |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview1)            |


# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. 지원되는 Ubuntu 및 Linux Mint 배포/버전(64비트)에 대한 .NET Core 1.x 설치:

| 런타임/SDK         |Ubuntu 16.04/Linux Mint 18|Ubuntu 14.04/Linux Mint 17|
|-------------------------|----------------------------|----------------------------|
|.NET Core 런타임 1.1.7  |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core 런타임 1.1.6  |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core 런타임 1.0.10 |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core 런타임 1.0.9  |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.8      |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.7      |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.0.4      |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.0.1      |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-16.04-x64-binaries)            |[설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-14.04-x64-binaries)            |

---

## <a name="install-net-core-for-supported-debian-versions-64-bit"></a>지원되는 Debian 버전(64비트)에 대한 .NET Core 설치

지원되는 Debian 버전(64비트)에 .NET Core를 설치하려면:

> [!NOTE]
> tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. 지원되는 Debian 버전(64비트)에 .NET Core 2.x를 설치하려면:

**.NET Core 2.0**

|런타임/SDK          |Debian 9       |Debian 8       |
|-------------------------|---------------|---------------|
|.NET Core 런타임 2.0.7  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.7)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.7)   |
|.NET Core 런타임 2.0.6  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|.NET Core 런타임 2.0.5  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|.NET Core SDK 2.1.105    |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.105)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.105)   |
|.NET Core SDK 2.1.103    |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|.NET Core SDK 2.0.3      |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |
|.NET Core SDK 2.0.0      |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.0)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.0)   |

**.NET Core 2.1**

>[!IMPORTANT]
> Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview)해야 합니다.

|런타임/SDK                  |Debian 9       |Debian 8       |
|---------------------------------|---------------|---------------|
|.NET Core 런타임 2.1.0-rc1      |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-rc1)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-rc1)   |
|.NET Core 런타임 2.1.0-미리 보기2 |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview2)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview2)   |
|.NET Core 런타임 2.1.0-미리 보기1 |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview1)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview1)   |
|.NET Core SDK 2.1.300-rc1        |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-rc1)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-rc1)        |
|.NET Core SDK 2.1.300-미리 보기2   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview2)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview2)   |
|.NET Core SDK 2.1.300-미리 보기1   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview1)   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview1)   |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. Debian 9 또는 Debian 8에 .NET Core 1.x 설치:

* .NET Core 런타임 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)
* .NET Core 런타임 1.1.6 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)
* .NET Core 런타임 1.0.10 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)
* .NET Core 런타임 1.0.9 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)
* .NET Core SDK 1.1.8 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)
* .NET Core SDK 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)
* .NET Core SDK 1.0.4 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)
* .NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

---

## <a name="install-net-core-for-supported-fedora-versions-64-bit"></a>지원되는 Fedora 버전(64비트)에 대한 .NET Core 설치

지원되는 Fedora 버전에 .NET Core를 설치하려면:

> [!NOTE]
> tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. 지원되는 Fedora 버전(64비트)에 대한 .NET Core 2.x 설치:

**.NET Core 2.0**

|런타임/SDK          |Fedora 26 이상 |Fedora 25 이전 |
|-------------------------|-------------------|----------------------|
|.NET Core 런타임 2.0.7  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.7)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.7)           |
|.NET Core 런타임 2.0.6  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|.NET Core 런타임 2.0.5  |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|.NET Core SDK 2.1.105    |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.105)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.105)           |
|.NET Core SDK 2.1.103    |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|.NET Core SDK 2.0.3      |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

**.NET Core 2.1**

>[!IMPORTANT]
> Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview)해야 합니다.

|런타임/SDK                  |Fedora 27          |Fedora 26             |
|---------------------------------|-------------------|----------------------|
|.NET Core 런타임 2.1.0-rc1      |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0-rc1)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-rc1)           |
|.NET Core 런타임 2.1.0-미리 보기2 |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0-preview2)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview2)           |
|.NET Core 런타임 2.1.0-미리 보기1 |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0-preview1)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview1)           |
|.NET Core SDK 2.1.300-rc1        |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.300-rc1)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-rc1)           |
|.NET Core SDK 2.1.300-미리 보기2   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.300-preview2)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview2))           |
|.NET Core SDK 2.1.300-미리 보기1   |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0-preview1)       |[설치 링크](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview1)           |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. 지원되는 Fedora 버전(64비트)에 .NET Core 1.x 설치:

**Fedora 24**

* .NET Core 런타임 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)
* .NET Core 런타임 1.1.6 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.8 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

**Fedora 23**

* .NET Core 런타임 1.0.9 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)
* .NET Core SDK 1.0.4 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)
* .NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)

---

## <a name="install-net-core-for-supported-centos-and-oracle-linux-distributionsversions-64-bit"></a>지원되는 CentOS 및 Oracle Linux 배포/버전(64비트)에 대한 .NET Core 설치

지원되는 CentOS 및 Oracle Linux 배포/버전(64비트)에 .NET Core를 설치하려면:

> [!NOTE]
> tar.gz에서 Linux 시스템을 설치하는 데 사용자 제어 디렉터리가 필요합니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. 지원되는 CentOS 및 Oracle Linux 배포/버전(64비트)에 .NET Core 2.x 설치:

**.NET Core 2.0**

* .NET Core 런타임 2.0.7 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)
* .NET Core 런타임 2.0.6 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)
* .NET Core 런타임 2.0.5 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)
* .NET Core SDK 2.1.105 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.105)
* .NET Core SDK 2.1.103 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)
* .NET Core SDK 2.0.3 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)
* .NET Core SDK 2.0.0 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.0)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview/)해야 합니다.

* .NET Core 런타임 2.1.0-rc1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-rc1)
* .NET Core 런타임 2.1.0-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2)
* .NET Core 런타임 2.1.0-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1)
* .NET Core SDK 2.1.300-rc1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-rc1)
* .NET Core SDK 2.1.300-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2)
* .NET Core SDK 2.1.300-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. 지원되는 CentOS 및 Oracle Linux 배포/버전(64비트)에 .NET Core 1.x 설치:

* .NET Core 런타임 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)
* .NET Core 런타임 1.1.6 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)
* .NET Core 런타임 1.0.10 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)
* .NET Core 런타임 1.0.9 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)
* .NET Core SDK 1.1.8 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)
* .NET Core SDK 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)
* .NET Core SDK 1.0.4 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)
* .NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a>지원되는 SUSE Linux Enterprise Server 및 OpenSUSE 배포/버전(64비트)에 .NET Core 설치

지원되는 SUSE Linux Enterprise Server 및 OpenSUSE 배포/버전(64비트)에 .NET Core 2.x를 설치하려면:

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. 지원되는 SUSE Linux Enterprise Server 및 OpenSUSE 배포/버전(64비트)에 .NET Core 2.x 설치:

**.NET Core 2.0**

**SUSE Linux Enterprise Server**

* .NET Core 런타임 2.0.7 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.7)
* .NET Core 런타임 2.0.6 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.6)
* .NET Core 런타임 2.0.5 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.5)
* .NET Core SDK 2.1.105 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.105)
* .NET Core SDK 2.1.103 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.103)
* .NET Core SDK 2.0.3 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.3)
* .NET Core SDK 2.0.0 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.0)

**openSUSE**

* .NET Core 런타임 2.0.7 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.7)
* .NET Core 런타임 2.0.6 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)
* .NET Core 런타임 2.0.5 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)
* .NET Core SDK 2.1.105 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.105)
* .NET Core SDK 2.1.103 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)
* .NET Core SDK 2.0.3 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)
* .NET Core SDK 2.0.0 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.0)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Visual Studio와 함께 .NET Core 2.1을 사용하려면 [Visual Studio 2017 15.7 미리 보기 1 이상을 설치](https://www.visualstudio.com/vs/preview)해야 합니다.

**SUSE Linux Enterprise Server**

* .NET Core 런타임 2.1.0-rc1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.0-rc1)
* .NET Core 런타임 2.1.0-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.0-preview2)
* .NET Core 런타임 2.1.0-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.0-preview1)
* .NET Core SDK 2.1.300-rc1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.300-rc1)
* .NET Core SDK 2.1.300-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.300-preview2)
* .NET Core SDK 2.1.300-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.300-preview1)

**openSUSE**

* .NET Core 런타임 2.1.0-rc1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-rc1)
* .NET Core 런타임 2.1.0-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2)
* .NET Core 런타임 2.1.0-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1)
* .NET Core SDK 2.1.300-rc1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-rc1)
* .NET Core SDK 2.1.300-미리 보기2 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2)
* .NET Core SDK 2.1.300-미리 보기1 [설치 링크](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 시스템에서 .NET Core의 **이전 미리 보기** 버전을 제거하세요.

2. 지원되는 SUSE Linux Enterprise Server 및 OpenSUSE 배포/버전(64비트)에 .NET Core 1.x 설치:

**SUSE Linux Enterprise Server 13.2**

* .NET Core 런타임 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)
* .NET Core 런타임 1.1.6 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)
* .NET Core SDK 1.1.7 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)

**openSUSE 24**

* .NET Core SDK 1.0.4 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries)
* .NET Core SDK 1.0.1 [설치 링크](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries)

---

> [!IMPORTANT]
> 지원되는 Linux 배포/버전에 .NET Core 설치에 문제가 있는 경우 설치된 배포/버전에 대한 다음 항목을 참조하세요.
> * [.NET Core 2.1 알려진 문제](https://github.com/dotnet/core/tree/master/release-notes/2.1)
> * [.NET Core 2.0 알려진 문제](https://github.com/dotnet/core/tree/master/release-notes/2.0)
> * [.NET Core 1.1 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.1)
> * [.NET Core 1.0 알려진 문제](https://github.com/dotnet/core/blob/master/release-notes/1.0)