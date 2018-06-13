---
title: Windows 컨테이너도 기존.NET 응용 프로그램 배포
description: Azure 클라우드 및 Windows 컨테이너와 기존.NET 응용 프로그램을 최신식 | Windows 컨테이너도 기존.NET 응용 프로그램 배포
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 829f33aba14d79d7d9003d1ac7472a19060d401a
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958003"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>Windows 컨테이너도 기존.NET 응용 프로그램 배포

Windows 컨테이너를 기반으로 하는 배포 클라우드 액세스에 최적화 된 응용 프로그램과 클라우드 네이티브 응용 프로그램에 적용 됩니다.

그러나이 가이드에서는 다음 섹션에서는 특히에서 대부분을 중점적으로 대 한 Windows 컨테이너를 사용 하 여 *클라우드 액세스에 최적화 된* 응용 프로그램에 응용 프로그램 아키텍처 변경 필요가 없습니다.

## <a name="what-are-containers-linux-or-windows"></a>컨테이너 란? (Linux 또는 Windows)

컨테이너는 응용 프로그램을 격리 된 패키지 자체를 마무리 하는 방법입니다. 해당 컨테이너에서 응용 프로그램 컨테이너의 외부에 존재 하는 프로세스 또는 응용 프로그램에 의해 영향을 받지 않습니다. 모든 응용 프로그램 하기 위해 종속 실행 성공적으로 프로세스를 컨테이너 내에서 있는 그대로 있습니다. 컨테이너가 있습니다 이동 하는 아무 곳에 나 응용 프로그램의 요구 사항을 항상 충족 되 면 직접 종속성에서 (라이브러리 종속성, 런타임, 및 등)를 실행 하는 데 필요한 모든 항목으로 번들로 묶여 있으므로 합니다.

컨테이너의 주요 특징 수행 하는 환경의 동일한 서로 다른 배포에서 필요한 모든 종속성을 컨테이너 자체 제공 하므로입니다. 컴퓨터에 응용 프로그램을 디버깅할 수 있으며 보장 환경으로 다른 컴퓨터에 배포 합니다.

컨테이너는 컨테이너 이미지의 인스턴스입니다. 컨테이너 이미지는 응용 프로그램 또는 서비스 (예: 스냅숏), 패키지 하 고 다음 신뢰할 수 있고 재현 가능한 방식으로 배포 하는 방법입니다. Docker는 프로세스 기술 it만도 하지 않음을 이라고 할 수 있습니다.

업계 전반 "배포 단위입니다." 강조 되은 매일 컨테이너 일반적인 되 면,

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>컨테이너 (Linux 또는 Windows에서 Docker 엔진)의 이점

또한 컨테이너를 사용 하 여 응용 프로그램을 빌드할 수 있습니다에 정의 된 간단한 구성 요소 제품으로 크게 증가 민첩성, 구축 하기 위한 제공 되는 경우 모든 인프라를 통해 모든 응용 프로그램을 실행 합니다.

컨테이너를 모든 앱 개발에서 프로덕션 환경에 Microsoft 개발자 도구, 운영 체제 및 클라우드 전체에서 Docker 통합할 덕분에 거의 없거나 전혀 없이 코드 변경으로 인해 취할 수 있습니다.

일반 Vm에 배포할 때 Vm에는 ASP.NET 앱을 배포 하기 위한 준비 메서드 이미 있는 합니다. 호스팅되고, 하지만 방법을 과정이 포함 되어 있음을 여러 수동 단계 또는 복잡 한 자동화 된 프로세스 Puppet, 같은 배포 도구 또는 유사한 도구를 사용 하 여입니다. 구성 항목 수정 서버 간, 응용 프로그램 콘텐츠를 복사 하 고 테스트 하 여 뒤에 한.msi 설정에 따라 대화형 설치 프로그램을 실행 하는 등의 작업을 수행 해야 할 수 있습니다. 배포에서 모든 단계 시간 및 위험 배포에 추가합니다. 대상 환경에서 종속성 없을 때마다 오류가 발생 합니다.

Windows 컨테이너에서 응용 프로그램 패키징 프로세스 자동 완벽 하 게 됩니다. Windows 컨테이너는 자동 업데이트와 롤백은 배포의 컨테이너를 제공 하는 Docker 플랫폼을 기반으로 합니다. Docker 엔진 사용에서 얻는 주요 개선 모든 종속성과 함께 응용 프로그램의 스냅숏을 같은 이미지를 만드는입니다. 이미지는 Docker 이미지 (이 경우: Windows 컨테이너 이미지)입니다. 소스 코드를 다시 살펴보자면 없이 컨테이너에 ASP.NET 응용 프로그램을 실행 하는 이미지입니다. 컨테이너 스냅샷이 배포 단위입니다.

대부분의 조직에서는 다음과 같은 이유로 모놀리식 기존 응용 프로그램 containerizing 됩니다.

-   **향상 된 배포를 통해 민첩성 릴리스**합니다. 컨테이너는 개발 및 운영 간의 일관 된 배포 계약을 제공합니다. 컨테이너를 사용 하면 예를 들어 개발자 들은지 않습니다를 "작동 제 컴퓨터에서 안 되는 이유 프로덕션 환경에서?" "실행 컨테이너로 사용할 경우 프로덕션 환경에서 실행 됩니다.", 이제 수 있습니다. 지원 되는 컨테이너 기반 환경에서 모든 종속성과 함께 패키지 된 응용 프로그램을 실행할 수 있습니다. 모든 배포 대상 (개발, QA, 준비, 프로덕션)에서 실행 되도록 원래 방식으로 실행 됩니다. 다음 배포를 크게 향상 시키거나, 한 단계에서 이동할 때 컨테이너 대부분 frictions를 제거 하 고 더 빨리 제공할 수 키를 누릅니다.

-   **비용 절감**합니다. 컨테이너를 통합 하 고 하드웨어 단위당 높은 밀도에서 실행 중인 응용 프로그램 또는 기존 하드웨어를 제거 하 여 비용 절감 될 있습니다.

-   **이식성**합니다. 컨테이너는 모듈식 및 노트북 됩니다. Docker 컨테이너는 모든 서버 운영 체제 (Linux 및 Windows) (Microsoft Azure, AWS Amazon, Google, IBM) 모든 주요 공용 클라우드 및 온-프레미스 및에 개인 또는 하이브리드 클라우드 환경에서 지원 됩니다.

-   **컨트롤**합니다. 컨테이너는 컨테이너 수준에서 제어 하는 유연 하 고 보안 환경을 제공 합니다. 컨테이너 보안 처리 isolated, 되며도 컨테이너에서 실행 한 제약 조건 정책 설정에 의해 제한 될 수 있습니다. Windows 컨테이너에 대 한 섹션에서 설명, Windows Server 2016 및 Hyper-v 컨테이너 추가 엔터프라이즈 지원 옵션을 제공합니다.

민첩성, 이식성을 및 제어에 크게 향상 된 기능 궁극적으로 많은 비용을 줄이는 경우 발생할 컨테이너를 사용 하 여 개발 하 고 응용 프로그램을 관리 합니다.

## <a name="what-is-docker"></a>Docker란?

[Docker](https://www.docker.com/) 는 [오픈 소스 프로젝트](https://github.com/docker/docker) 클라우드 또는 온-프레미스에서 실행할 수 있는 휴대용, 스페이스인 컨테이너로 응용 프로그램의 배포를 자동화 하는 합니다. Docker는 이 기술을 장려하고 발전시키는 [회사](https://www.docker.com/)이기도 합니다. 회사는 클라우드, Linux 및 Windows 공급 업체를 비롯 하 여 Microsoft와의 공동 작업에서 작동합니다.

![](./media/image6.png)

> **그림 4-6입니다.** Docker는 하이브리드 클라우드의 모든 계층에서 컨테이너를 배포

다른 사람에 게 가상 컴퓨터에 잘 알고 컨테이너 나타날 수 있습니다 매우 유사 합니다. 컨테이너는 운영 체제를 실행 파일 시스템에 있으며 물리적 또는 가상 컴퓨터 시스템과 마찬가지로 네트워크를 통해 액세스할 수 있습니다. 그러나 기술 및 컨테이너 개념은 가상 컴퓨터와 크게 다릅니다. 개발자의 관점에서 단일 프로세스와 같은 컨테이너를 더 처리 해야 합니다. 사실, 컨테이너는 하나의 프로세스에 대 한 단일 진입점입니다.

Docker 컨테이너 (편의상 *컨테이너*) Linux와 Windows에서 기본적으로 실행할 수 있습니다. Windows 컨테이너 (호스트 서버 또는 VM) Windows 호스트에서 실행 가능 일반 컨테이너를 실행 하는 경우 및 Linux 컨테이너 Linux 호스트에만 실행할 수 있습니다. 그러나 Windows Server 및 Hyper-v 컨테이너의 최신 버전의 Linux 컨테이너도에서 실행할 수 기본적으로 Windows Server는 현재 Windows Server 컨테이너 에서만 사용할 수 있는 Hyper-v 격리 기술을 사용 하 여.

가까운 장래에 Linux 및 Windows 컨테이너에 있는 혼합 된 환경을 가능 하 고 일반적인 됩니다.

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>기존.NET 응용 프로그램에 대 한 Windows 컨테이너의 이점

Windows 컨테이너를 사용 하는 이점을 기본적 일반적 컨테이너에서 얻을 수 있는 동일한 이점입니다. Windows 컨테이너를 사용 하는 것은 크게 개선 민첩성, 이식성을 제어 하는 방법에 대 한입니다.

기존.NET 응용 프로그램은.NET Framework를 사용 하 여 만든 응용 프로그램을 가리킵니다. 예를 들어 기존의 ASP.NET 웹 응용 프로그램이 아닐-최신일 하 고 플랫폼을 실행 하는.NET Core를 사용 하지 않는 Linux, Windows 및 MacOS에서 합니다.

.NET Framework의 주요 종속성은 Windows입니다. 기존 ASP.NET에서 IIS 및 System.Web 같은 보조 종속성을 갖도록 합니다.

.NET Framework 응용 프로그램 기간 windows에서 실행 해야 합니다. 기존.NET Framework 응용 프로그램을 컨테이너 화할 하려는 고 처리할 수 없거나.NET Core로 마이그레이션하는 데 투자 하지 않으려는 ("제대로 작동 하지 않는 마이그레이션할"), Windows 컨테이너를 사용 하는 컨테이너에 대 한 유일한 선택 합니다.

따라서 Windows 컨테이너의 주요 장점 중 하나를 제공 하면 컨테이너 화 통해 Windows에서 실행 되는 기존.NET Framework 응용 프로그램을 최신식 하는 방법입니다. 궁극적으로, Windows 컨테이너가 하면 이점을 활용할 수 컨테이너 민첩성, 이식성을 효율적으로 제어를 사용 하 여 찾고 있는 합니다.

## <a name="choose-an-os-to-target-with-net-based-containers"></a>대상으로 하는 운영 체제를 선택 합니다. NET 기반 컨테이너

.NET Core와.NET Framework 간의 차이점 뿐만 아니라 Docker에서 지원 되는 운영 체제의 다양성을 고려할 때, 특정 OS 및 특정 버전을 사용 하는 프레임 워크에 따라 대상 해야 있습니다.

Windows의 경우 Windows Server Core 또는 Windows Nano Server를 사용할 수 있습니다. 이러한 Windows 버전 (예: Kestrel 처럼 자체 호스트 된 웹 서버와 IIS).NET Framework 또는.NET Core 응용 프로그램에서 필요할 수 있는 다른 특성을 제공 합니다.

Linux의 경우 공식 .NET Docker 이미지(예: Debian)에서 여러 배포판을 제공합니다.

그림 4-7에는.NET Framework의 응용 프로그램의 버전에 따라 표시할 수 있는 운영 체제 버전이 나와 있습니다.

![](./media/image7.png)

> **그림 4-7입니다.** 대상.NET Framework 버전에 따라 운영 체제

.NET Framework 응용 프로그램을 기반으로 하는 기존 또는 레거시 응용 프로그램에 대 한 마이그레이션 시나리오에서는 주요 종속성 Windows 및 IIS에 있습니다. 수정할 수 있는 유일한 방법은 Windows Server Core와.NET Framework를 기반으로 하는 Docker 이미지를 사용 하는 것입니다.

Dockerfile 파일을 이미지 이름을 추가 하면.NET Framework 기반 Windows 컨테이너 이미지에 대 한 다음 예제와 같이 태그를 사용 하 여 운영 체제 및 버전을 선택할 수 있습니다.

> | **태그** | **시스템 및 버전** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET framework 4.x Windows Server Core에서 |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET framework 4.x를 Windows Server Core에서 추가 ASP.NET 사용자 지정 |

.NET Core (플랫폼 간 Linux 및 Windows 용)에 대 한 태그는 다음과 같은 형태가 됩니다.

> | **태그** | **시스템 및 버전**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET core 2.0 Linux에서 런타임 전용 |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .NET core 2.0 Windows Nano Server에서 런타임 전용 |

### <a name="multi-arch-images"></a>다중 아치 이미지

2017 중순 부터는 사용할 수도 있습니다는 새로운 기능 호출 Docker에서 [다중 arch](https://github.com/moby/moby/issues/15866) 이미지입니다. .NET core Docker images 다중 아치 태그를 사용할 수 있습니다. Dockerfile 파일을 대상으로 하는 운영 체제를 정의할 필요가 더 이상 사용 되지 않습니다. 다중 아치 기능으로 단일 태그를를 다중 컴퓨터 구성에 걸쳐 사용할 수 있습니다. 예를 들어, 다중 arch 사용 하면 하나의 공통 된 태그: **microsoft/dotnet:2.0.0-runtime**합니다. Linux 컨테이너 환경에서 이러한 태그를 끌면 Debian 기반 이미지를 가져옵니다. Windows 컨테이너 환경에서 이러한 태그를 끌면 Nano 서버 기반 이미지를 가져옵니다.

기존.NET Framework만 Windows를 지원 하기 때문에.NET Framework 이미지에 대 한 다중 아치 기능을 사용할 수 없습니다.

## <a name="windows-container-types"></a>Windows 컨테이너 형식

Linux 컨테이너와 같은 Windows Server 컨테이너는 Docker 엔진을 사용 하 여 관리 됩니다. Linux 컨테이너와 달리 Windows 컨테이너 두 개의 서로 다른 컨테이너 형식에 포함 하거나 실행 시간은 Windows Server 컨테이너와 Hyper-v 격리 합니다.

**Windows Server 컨테이너**: 프로세스 및 네임 스페이스 격리 기술을 통해 응용 프로그램 격리를 제공 합니다. Windows Server 컨테이너는 컨테이너 호스트와 호스트에서 실행 되는 모든 컨테이너와 커널을 공유 합니다. 이러한 컨테이너는 유해 보안 경계를 제공 하지 않는 하 고 신뢰할 수 없는 코드를 격리 하려면 쓰일 수 없습니다. 공유 커널 공간 때문에 이러한 컨테이너는 동일한 커널 버전 및 구성 해야합니다.

**Hyper-v 격리**: 각 컨테이너를 고도로 최적화 된 VM에서 실행 하 여 Windows Server 컨테이너에서 제공 하는 격리를 확장 합니다. 이 구성에서는 컨테이너 호스트의 커널은 동일한 호스트에 다른 컨테이너와 공유 되지 됩니다. 이러한 컨테이너는 유해 다중 테 넌 트, 사용 하 여 호스팅하는 VM의 동일한 보안 보장 하도록 디자인 되었습니다. 이러한 컨테이너 호스트 또는 호스트에 다른 컨테이너와 커널을 공유 하지 않습니다, 때문에 서로 다른 버전 및 지원 되는 버전) (함께 구성 하는 커널에서 실행할 수 있습니다. 예를 들어 Windows 10에서 모든 Windows 컨테이너 Windows Server 커널 버전 및 구성을 활용 하 여 Hyper-v 격리를 사용 합니다.

또는 Hyper-v 격리 하지 않고도 windows 컨테이너를 실행 하는 것은 런타임에 결정 합니다. 처음에 Hyper-v 격리 컨테이너를 만들도록 선택할 수도 있으며 런타임 시 Windows Server 컨테이너로 대신 실행 하도록 선택할 수 있습니다.

### <a name="additional-resources"></a>추가 자료

-   **Windows 컨테이너 설명서**

    [https://docs.microsoft.com/virtualization/windowscontainers/](https://docs.microsoft.com/virtualization/windowscontainers/)

-   **Windows 컨테이너 기본 사항**

    [https://docs.microsoft.com/virtualization/windowscontainers/about/](https://docs.microsoft.com/virtualization/windowscontainers/about/)

-   **인포 그래픽: Microsoft 및 컨테이너**

    [https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf](https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf)


## <a name="the-container-ecosystem-in-azure"></a>Azure에서 컨테이너 생태계는

이전 섹션에서 것에 설명 했습니다.NET 응용 프로그램에 대 한 특정 컨테이너 이미지에 대 한 세부 정보 뿐만 아니라 이란 Docker 컨테이너의 이점입니다. 일반 정보를 개발 하거나 응용 프로그램을 컨테이너 화할 기반이 됩니다.
그러나 프로덕션 배포 환경 또는 심지어 QA 및 개발/테스트 환경에 대 한를 고려할 때에 Microsoft Azure는 열려 있고 광범위 한의 다양 한 선택 항목 (아래 다이어그램에 표시 됨) 클라우드에서 전체 컨테이너 생태계를 제공 합니다. 특정 응용 프로그램의 필요에 따라 하나 또는 다른 Azure 제품을 선택 해야 합니다.

![](./media/image7.5.png)

> **그림 4-7.5입니다.** Azure에서 컨테이너 생태계는

이러한 컨테이너 생태계는 azure에서 컨테이너 간주 되는 인프라를 지 원하는 다음 제품:
-   **Azure 컨테이너 인스턴스 (ACI)**
-   **Azure 가상 컴퓨터** (으로 컨테이너의 지원)
-   **Azure 가상 컴퓨터 크기 집합** (으로 컨테이너의 지원)

이러한 세에서 ACI 기본 운영 체제를 업그레이드/패치 등을 필요가 없습니다 유지 하기 위해 필요는 없지만 여전히 ACI 더 잘이 설명서의 이후 단원에서 설명한 것 처럼는 인프라 수준에서 배치 되는 사실 많은 도움이 될을 제공 합니다.

Azure 지원 된 컨테이너를 PaaS (Platform 서비스)에 더 배치 하는 동시에 수준에서 제품은 다음과 같습니다.

-   **Azure App Service**
-   **Azure Kubernetes 서비스 (AKS 및 ACS)**
-   **Azure 서비스 패브릭** 
-   **Azure 일괄 처리** 

그런 다음 Azure 컨테이너 레지스트리는 모든 이전 제품 등록 하 고 사용자 지정 컨테이너 이미지를 배포 하는 경우에서 사용할 수 있는 Azure에서 호스팅되는 높은 확장 가능한 컨테이너 레지스트리입니다.

또한 사용자 컨테이너에서 사용할 수 있습니다 다른 관리 서비스 등의 Azure SQL 데이터베이스, Azure Redis 캐시 Azure Cosmos DB와 같은 Azure에서. 또한 클라우드 대장간 및 Azure 내에서 컨테이너를도 사용할 수 있는 OpenShift와 같은 Azure Marketplace에서 공급 업체 솔루션/플랫폼 됩니다. 

다음 섹션에서는 Windows 컨테이너를 대상으로 하는 경우에 특히 각 해당 Azure 제품과 솔루션을 사용 하는 경우에 Microsoft의 권장 사항을 탐색할 수 있습니다.


>[!div class="step-by-step"]
[이전](what-about-cloud-native-applications.md)
[다음](when-not-to-deploy-to-windows-containers.md)
