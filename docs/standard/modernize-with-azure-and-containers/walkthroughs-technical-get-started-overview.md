---
title: 연습 및 technical 시작된 개요 가져오기
description: 기존.NET 응용 프로그램을 Azure 클라우드 및 Windows 컨테이너를 최신식 | 연습 및 technical 시작된 개요 가져오기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 27de9d1c5475855a22f2d8a3518982605277f6d9
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34027391"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>연습 및 technical 시작된 개요 가져오기

이 전자책 (영문)의 크기를 제한 하려면 추가 기술 설명서 및 전체 연습 된 사용할 수는 GitHub 리포지토리에 있습니다. 온라인 일련의이 장에서 설명 하는 연습에서는 Windows 컨테이너와 Azure로 배포를 기반으로 하는 여러 환경 설치 하는 단계별 설명 합니다.

다음 섹션에서는 설명 각 연습에 대해 해당 목표 및 높은 수준의 비전 관련 된 작업에 대 한 다이어그램을 제공 합니다. 자체의 연습을 얻을 수에 *eShopModernizing* 앱 GitHub 리포지토리에 wiki에서 [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki)합니다.

## <a name="technical-walkthrough-list"></a>기술 연습 목록

다음 started 연습 리프트 하 및 컨테이너를 사용 하 여 이동 하 고 다음 Azure에서 배포의 여러 선택 항목을 사용 하 여 이동할 수 있는 샘플 응용 프로그램에 일관 되 고 포괄적인 기술 지침을 제공 합니다.

다음 연습 중 각각의 새 샘플 eShopLegacy 및 eShopModernizing 앱의 경우에 GitHub에서 사용할 수 있는 사용 하 여 [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing)합니다.

- **EShop 레거시 응용 프로그램 (초기 응용 프로그램을 현대화 할) 둘러보기**

- **Windows 컨테이너에서 기존 ASP.NET 웹 앱 (MVC & WebForms)을 컨테이너 화합니다**

- **Windows 컨테이너와 함께 기존 WCF 서비스 (N 계층 응용 프로그램)을 컨테이너 화합니다**

- **Azure Vm에 Windows 컨테이너 기반 앱 배포**

- **Azure 컨테이너 서비스에서 Kubernetes에 Windows 컨테이너 기반 앱 배포**

- **Azure 서비스 패브릭에 Windows 컨테이너 기반 앱 배포**


## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>EShop 레거시 응용 프로그램 연습 1: 둘러보기

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.

[eShopModernizing wiki 연습](https://github.com/dotnet-architecture/eShopModernizing/wiki)


### <a name="overview"></a>개요

이 연습에서는 세 개의 샘플 레거시 응용 프로그램의 초기 구현을 탐색할 수 있습니다. 처음 두 개의 샘플 웹 응용 프로그램은 모놀리식 아키텍처 및 기존 ASP.NET을 사용 하 여 만든 합니다. ASP.NET을 기반으로 한 응용 프로그램은 4.x MVC; 두 번째 응용 프로그램은 ASP.NET 4.x Web Forms를 기반으로 합니다. 세 번째 응용 프로그램은 클라이언트 WinForms 응용 프로그램 및 서버 쪽에서 구성 하는 3 계층 응용 프로그램 [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) 서비스입니다.

이러한 모든 응용이 프로그램에서 사용할 수 있는 [eShopModernizing GitHub 리포지토리](https://github.com/dotnet-architecture/eShopModernizing)합니다.

### <a name="goals"></a>목표

이 연습에서는 주요 목표는 단순히 코드 및 구성 하 고 이러한 앱을 친숙 해지기 합니다. 생성 하 고 모의 데이터를 사용 하 여 테스트 목적으로 SQL 데이터베이스를 사용 하지 않고 있음을 앱을 구성할 수 있습니다. 이 선택적 구성은 분리 된 방식으로 종속성 주입을 기반으로 합니다.

### <a name="scenario-1-aspnet-web-apps"></a>시나리오 1: ASP.NET 웹 응용 프로그램

아래 그림에서는 원래 레거시 ASP.NET 웹 응용 프로그램의 간단한 시나리오를 보여 줍니다.

> ![원래 레거시 ASP.NET 웹 응용 프로그램의 간단한 아키텍처 시나리오](./media/image5-1.png)
>

비즈니스 도메인 관점에서 두 앱 모두 동일한 카탈로그 관리 기능을 제공합니다. EShop 엔터프라이즈 팀의 멤버를 보고 편집할 제품 카탈로그 응용 프로그램을 사용 합니다. 

다음 그림에는 초기 앱 스크린 샷을 보여 줍니다.

![ASP.NET MVC와 ASP.NET Web Forms 응용 프로그램 (기존/레거시 technologies)](./media/image5-2.png)

종속성에 ASP.NET 4.x 또는 이전 버전 (또는 MVC에 대 한 Web Forms에 대 한) 의미 이러한 응용 프로그램 코드는 ASP.NET Core MVC를 사용 하 여 완전히 다시 작성 하지 않으면.NET Core에서 실행 되지 않습니다. 

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>시나리오 2: WCF 서비스 및 WinForms 클라이언트 응용 프로그램 (3 계층 응용 프로그램)

아래 그림에서는 원래 3 계층 레거시 응용 프로그램의 간단한 시나리오를 보여 줍니다.

> ![WCF 서비스와 원래 레거시 3 계층 응용 프로그램 및 WinForms 클라이언트 응용 프로그램의 간단한 아키텍처 시나리오](./media/image5-1.5.png)
>

### <a name="benefits"></a>이점

이 연습에서는 이점은 간단한: 방금 익숙해질 목적으로 코드와 초기 응용 프로그램입니다.

### <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.

  - [ASP.NET MVC 기준선에 둘러보기 및 Web Forms "레거시" 앱](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
  - [기본 WCF 서비스와 WinForms (3 계층) "레거시" 응용 프로그램에서 둘러보기](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)


## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>연습 2: Windows 컨테이너를 기존.NET 응용 프로그램을 컨테이너 화합니다

### <a name="overview"></a>개요

Windows 컨테이너를 사용 하 여 MVC, Web Forms, WCF, 프로덕션, 개발 및 테스트 환경에 기반 하는 것과 같은 기존.NET 응용 프로그램의 배포를 향상 시킵니다.

### <a name="goals"></a>목표

이 연습의 목표 containerizing 기존.NET Framework 응용 프로그램에 대 한 몇 가지 옵션을 표시 하는입니다. 다음과 같은 작업을 수행할 수 있습니다.

- 사용 하 여 응용 프로그램을 컨테이너 화할 [Docker 용 Visual Studio 2017 도구](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 또는 이후 버전).

- 수동으로 추가 하 여 응용 프로그램을 컨테이너 화할는 [Dockerfile](https://docs.docker.com/engine/reference/builder/)를 사용 하 여는 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)합니다.

- 사용 하 여 응용 프로그램을 컨테이너 화할는 [Img2Docker](https://github.com/docker/communitytools-image2docker-win) 도구 (Docker에서 오픈 소스 도구).

이 연습에서는 Visual Studio 2017 Tools for Docker 접근 방식에 중점을 두고 있지만 Dockerfile을 사용 하 여 관련 하 여 다른 두 가지 방법으로 매우 비슷합니다.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>시나리오 1: 컨테이너 화 된 ASP.NET 웹 앱

아래 그림에서는 컨테이너 화 된 eShop 레거시 웹 응용 프로그램 응용 프로그램에 대 한 시나리오를 보여 줍니다.

> ![개발 환경에서 ASP.NET 응용 프로그램을 컨테이너 화 된 간소화 된 아키텍처 다이어그램](./media/image5-3.png)
>


### <a name="scenario-2-containerized-wcf-service"></a>시나리오 2: 컨테이너 화 된 WCF 서비스

아래 그림에서는 컨테이너 화 된 WCF 서비스와 3 계층 응용 프로그램에 대 한 시나리오를 보여 줍니다. 

> ![개발 환경에서 컨테이너 화 된 WCF 서비스의 아키텍처 다이어그램을 간소화](./media/image5-3.5.png)
>

### <a name="benefits"></a>이점

컨테이너에서 단일 응용 프로그램을 실행 하는 이점이 있습니다. 먼저, 응용 프로그램에 대 한 이미지를 만듭니다. 해당 시점부터 모든 배포가 동일한 환경에서 실행 됩니다. 모든 컨테이너 동일한 운영 체제 버전을 사용 하 여, 설치 하는 종속성의 버전은, 동일한.NET framework 버전을 사용 하 여 및 동일한 프로세스를 사용 하 여 작성 됩니다. 기본적으로, Docker 이미지를 사용 하 여 응용 프로그램의 종속성을 제어 합니다. 종속성의 컨테이너를 배포할 때 응용 프로그램으로 이동 합니다.

또 다른 이점은 개발자가 Windows 컨테이너에서 제공 되는 일관 된 환경에서 응용 프로그램을 실행할 수입니다. 특정 버전으로 표시 하는 문제 스테이징 또는 프로덕션 환경에는 대신 즉시 발견 될 수 있습니다. 개발 팀의 멤버에서 사용 하는 개발 환경의 차이점 중요 응용 프로그램 컨테이너에서 실행 하는 경우 작습니다.

컨테이너 화 된 응용 프로그램에 볼록한 확장 곡선을 갖게 됩니다. 컨테이너 화 된 응용 프로그램 VM 또는 물리적 컴퓨터 컴퓨터당 일반 응용 프로그램 배포에 비해 더 많은 응용 프로그램 및 서비스 인스턴스 (컨테이너에 기반)를 사용할 수 있습니다를 사용 합니다. 이 명령은 더 높은 밀도 필요한 적은으로 해석 orchestrators Kubernetes 서비스 패브릭 등을 사용 하는 경우에 특히 리소스입니다.

컨테이너 화 이상적인 상황에서 응용 프로그램 코드를 변경한 필요 하지 않습니다 (C\#). 대부분의 시나리오에서 하기만 하면 Docker 배포 메타 데이터 파일 (Dockerfiles 및 Docker Compose 파일).

### <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.

  - [Windows 컨테이너 및 Docker를 사용 하 여.NET Framework 웹 앱을 컨테이너 화할 하는 방법](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
  - [WCF 서비스에 Docker 지원 추가](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)



## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Azure Vm에 Windows 컨테이너 기반 앱을 배포 하는 연습 3:

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다. [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>개요

Docker 호스트에 Windows Server 2016 가상 컴퓨터 (VM) Azure에서 배포 개발/테스트/스테이징 환경을 신속 하 게 설정할 수 있습니다. 또한, 테스터 또는 비즈니스 사용자가 유효성을 검사할 앱에 대 한 공통 위치를 제공 합니다. 또한 Vm 서비스 (IaaS) 프로덕션 환경으로 유효한 하 부 구조를 수 있습니다.

### <a name="goals"></a>목표

이 연습의 목표는 Windows Server 2016 또는 이상 버전을 기반으로 하는 Azure Vm에 Windows 컨테이너를 배포할 때 사용할 수 있는 여러 대체 방법을 설명 합니다.

### <a name="scenarios"></a>시나리오

몇 가지 시나리오는이 연습에 포함 됩니다.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Docker 엔진 연결을 통해 dev PC에서에서 Azure VM 배포 시나리오 a:

![Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포](./media/image5-4.png)

> **그림 5-4.** Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Docker 레지스트리를 통해 Azure VM에 배포 시나리오 b:

![Docker 레지스트리를 통해 Azure VM에 배포](./media/image5-5.png)

> **그림 5-5.** Docker 레지스트리를 통해 Azure VM에 배포

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a>Visual Studio Team Services에서 CI/CD 파이프라인에서 Azure VM에 시나리오 c: 배포

![Visual Studio Team Services에서 CI/CD 파이프라인에서 Azure VM에 배포](./media/image5-6.png)

> **그림 5-6.** Visual Studio Team Services에서 CI/CD 파이프라인에서 Azure VM에 배포

### <a name="azure-vms-for-windows-containers"></a>Windows 컨테이너에 대 한 azure Vm

Windows 컨테이너에 대 한 azure Vm은 Windows Server 2016, Windows 10 또는 이후 버전에 따라 Vm, 모두 Docker 엔진으로 설정 합니다. 대부분의 경우에서 Windows Server 2016은 Azure Vm에서 사용 됩니다.

Azure에서 현재 V 제공 **컨테이너와 Windows Server 2016**합니다. Windows Server Core 또는 Windows Nano Server과 함께 새로운 Windows Server 컨테이너 기능을 사용 하려면이 VM을 사용할 수 있습니다. 컨테이너 OS 이미지 설치 되 고 VM은 Docker에서 사용할 수 있습니다.

### <a name="benefits"></a>이점

Azure에 배포할 Windows 컨테이너를 온-프레미스 Windows Server 2016 Vm으로 배포할 수 있지만 Windows Server 컨테이너 Vm이 즉시 사용을 시작 하는 쉬운 방법이 가져옵니다. 테스터 및 Azure 가상 컴퓨터 크기 집합을 통해 자동 확장성에 액세스할 수 있는 공통 온라인 위치를 가져올 수도 있습니다.

### <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Azure 컨테이너 인스턴스 (ACI)에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 연습 4:

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.

[ACI (Azure 컨테이너 인스턴스)에 앱 배포](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>개요

[Azure 컨테이너 인스턴스 (ACI)](https://docs.microsoft.com/en-us/azure/container-instances/) 는 가장 빠른 방법은 컨테이너 개발/테스트/준비 환경을 컨테이너의 단일 인스턴스를 배포할 수 있습니다.

### <a name="goals"></a>목표

이 연습에서는 Azure 컨테이너 인스턴스 (ACI) 및 ACI에 eShopModernizing 앱을 배포 하는 방법을에 Windows 컨테이너를 배포할 때 주요 시나리오를 보여줍니다.

### <a name="scenarios"></a>시나리오

하나 또는 모든 (MVC 응용 프로그램, WebForms 응용 프로그램 또는 WCF 서비스) 앱을 배포 하는 등 ACI에 eShopModernizing 앱을 배포 하는 방법에 대 한 변형이 있을 수 있습니다. 아래에 표시 된 다음과 같은 시나리오에서 ACI (Azure 컨테이너 인스턴스)으로 ASP.NET MVC 응용 프로그램 및 배포 둘 다 SQL Server 컨테이너 컨테이너로 볼 수 있습니다.

![개발 환경에서 ACI를 배포](./media/image5-3.5.6.png)

### <a name="benefits"></a>이점

Azure 컨테이너 인스턴스를 쉽게 만들고 가상 컴퓨터를 프로 비전 하거나 더 높은 수준의 서비스를 채택 필요 없이 azure에서 Docker 컨테이너를 관리할 수 있습니다. ACI, 직접 Azure에서 Windows 컨테이너를 배포 하 고 사용할 수에 노출할 정규화 된 도메인 이름 (FQDN)를 사용 하 여 인터넷 몇 초 내에에서 (있는 경우 준비 Windows 컨테이너 이미지 Docker 레지스트리 (Docker 허브 또는 Azure 컨테이너 등)에 레지스트리)입니다.

### <a name="considerations"></a>고려 사항

어느 전체.NET Framework를 사용 하 여 Windows 컨테이너 배포 / ASP.NET 또는 SQL Server Azure 컨테이너 인스턴스 (ACI)에 매우 빠르게 Docker 이미지 될 해야 하므로 (예: Windows 컨테이너와 Windows Server 2016) 일반 Docker 호스트에 배포 하지만 될 때마다 (Docker 레지스트리에서 가져온) 다운로드 하 고 (영구적으로 온라인 상태이 고 고유한 docker 호스트를 유지 관리 보다 훨씬 저렴 SQL 컨테이너 이미지 (15.1 GB) 및 ASP.NET 컨테이너 이미지 (13.9 GB)의 크기는 훨씬 큰 Azure에서 Windows 컨테이너 VM으로 Windows Server 2016) 인 반면에 프로덕션 배포에 유리한입니다 (AKS/ACS) Azure 또는 Azure 서비스 패브릭에서 Kubernetes 같은 전체 orchestrator 언급 하기 위해이 없습니다.

주 결론 Azure 컨테이너 인스턴스를 사용 하는 매우 매력적인 사용할 개발/테스트 시나리오에 대 한 및 CI/CD 파이프라인에 대 한 합니다.

## <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다. 

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)


## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Azure 컨테이너 서비스에서 Kubernetes에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 연습 5:

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>개요

Windows 컨테이너를 기반으로 하는 응용 프로그램 더욱 해소 IaaS Vm에서 다른 페이지로 이동 하는 플랫폼에서 사용 하 여 신속 하 게 할 수 있습니다. 이 쉽게 높은 확장성을 달성 하는 데 필요한 및 더 잘 자동화 확장성, 고 크게 향상에 대 한 배포 및 버전 관리를 자동화 합니다. Orchestrator를 사용 하 여 이러한 목표를 달성할 수 [Kubernetes](https://kubernetes.io/)에서 사용할 수 있는, [Azure 컨테이너 서비스](https://azure.microsoft.com/services/container-service/)합니다.

### <a name="goals"></a>목표

Windows 컨테이너 기반 응용 프로그램 Kubernetes 배포 하는 방법에 알아보려면이 연습의 목표는 (호출 또한 *K8s*) Azure 컨테이너 서비스의 합니다. 처음부터 Kubernetes에 배포은 두 단계로 이루어집니다.

1.  Azure 컨테이너 서비스를 Kubernetes 클러스터를 배포 합니다.

2.  Kubernetes 클러스터에 응용 프로그램 및 관련된 리소스를 배포 합니다.

### <a name="scenarios"></a>시나리오

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>시나리오 a: Kubernetes 클러스터에 직접 배포 하는 개발 환경에서

![개발 환경에서 Kubernetes 클러스터에 직접 배포 합니다.](./media/image5-7.png)

> **그림 5-7.** 개발 환경에서 Kubernetes 클러스터에 직접 배포 합니다.

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a>Team Services에서 파이프라인 CI/CD에서 Kubernetes 클러스터 시나리오 b: 배포

![Team Services에서 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포 합니다.](./media/image5-8.png)

> **그림 5-8.** Team Services에서 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포 합니다.

### <a name="benefits"></a>이점

Kubernetes에 있는 클러스터를 배포 하는 다음과 같은 많은 이점이 있습니다. 가장 큰 장점은 적용 되는 응용 프로그램 (내부 확장성의 기존 노드에서에서)를 사용 하 고 클러스터 (에서 노드 또는 Vm의 수에 따라 컨테이너 인스턴스 수에 따라를 확장할 수 있는 프로덕션에 사용 가능한 환경 가져올 전역 확장성 클러스터의)입니다.

Azure 컨테이너 서비스 인기 있는 오픈 소스 도구와 기술을 Azure에 맞게 최적화합니다. 사용자 컨테이너 및 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션 가져오기 크기, 호스트의 수를 선택 하 고 다른 모든 항목을 처리 하는 orchestrator 도구-컨테이너 서비스 키를 누릅니다.

Kubernetes와 개발자가 수에서 진행 상황 실제 및 가상 컴퓨터에 대 한 다음과 같은 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라 계획:

- 여러 컨테이너를 기반으로 응용 프로그램

- 컨테이너 인스턴스를 복제 하는 가로 자동 크기 조정

- 이름 지정 및 검색 (예를 들어 내부 DNS)

- 로드 균형 조정

- 롤링 업데이트

- 암호를 배포합니다.

- 응용 프로그램 상태 확인

## <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다. [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Azure 서비스 패브릭에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 연습 6:

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>개요

Windows 컨테이너를 신속 하 게 기반 응용 프로그램 플랫폼에서 더욱 해소 IaaS Vm에서 다른 페이지로 이동 사용 해야 합니다. 이 쉽게 높은 확장성을 달성 하는 데 필요한 및 더 잘 자동화 확장성, 고 크게 향상에 대 한 배포 및 버전 관리를 자동화 합니다. 다른 공용 클라우드 또는 Azure 클라우드에서 사용할 수 있지만 가능 온-프레미스를 사용 하는 Azure 서비스 패브릭 orchestrator를 사용 하 여 이러한 목표를 달성할 수 있습니다.

### <a name="goals"></a>목표

이 연습의 목표는 azure에서 서비스 패브릭 클러스터에 Windows 컨테이너-> 기반 응용 프로그램을 배포 하는 방법에 알아보려면입니다. 서비스 패브릭을 처음부터 새로 배포은 두 단계로 이루어집니다.

1.  Azure로 (또는 다른 환경에) 서비스 패브릭 클러스터를 배포 합니다.

2.  서비스 패브릭 클러스터에 응용 프로그램 및 관련된 리소스를 배포 합니다.

### <a name="scenarios"></a>시나리오

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>개발 환경에서 서비스 패브릭 클러스터에 직접 시나리오 a: 배포

![개발 환경에서 서비스 패브릭 클러스터에 직접 배포 합니다.](./media/image5-9.png)

> **그림 5-9.** 개발 환경에서 서비스 패브릭 클러스터에 직접 배포 합니다.

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a>Team Services에서 파이프라인 CI/CD에서 서비스 패브릭 클러스터를 시나리오 b: 배포

![Visual Studio Team Services에서 CI/CD 파이프라인에서 서비스 패브릭 클러스터를 배포](./media/image5-10.png)

> **그림 5-10.** Visual Studio Team Services에서 CI/CD 파이프라인에서 서비스 패브릭 클러스터를 배포

## <a name="benefits"></a>이점

서비스 패브릭 클러스터에 배포의 이점을 Kubernetes 사용의 이점와 비슷합니다. 한 가지 차이점 하지만 서비스 패브릭 Windows 응용 프로그램의 버전 1.9 Kubernetes에서 Windows 컨테이너에 대 한 베타 기간 내에 있는 Kubernetes에 비해 더 성숙한 프로덕션 환경 된다는 점입니다 (2017 년 12 월). Kubernetes는 Linux 용 더 성숙한 환경입니다.

Azure Service Fabric을 사용 하 여의 주요 장점은 적용 되는 응용 프로그램 (내부 확장성의 기존 노드에서에서)를 사용 하 고의 수에 따라 컨테이너 인스턴스 수에 따라를 확장할 수 있는 프로덕션에 사용 가능한 환경 가져올 노드 또는 클러스터 (클러스터의 전역 확장성)에서 Vm입니다.

Azure 서비스 패브릭 응용 프로그램 구성에 대 한 및 사용자 컨테이너에 대 한 이식성을 제공합니다. 서비스 패브릭 클러스터에 Azure에서 또는 자체 데이터 센터에서 온-프레미스 설치를 할 수 있습니다. 다른 클라우드에서 서비스 패브릭 클러스터 같은 설치도 [AWS Amazon](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/)합니다.

서비스 패브릭 개발자 수에서 진행 상황 실제 및 가상 컴퓨터에 대 한 다음과 같은 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라 계획:

- 여러 컨테이너를 기반으로 응용 프로그램입니다.

- 가로 크기 자동 조정 및 컨테이너 인스턴스를 복제합니다.

- 이름 지정 및 (예를 들어 내부 DNS)를 검색 합니다.

- 로드 균형 조정 합니다.

- 롤링 업데이트 합니다.

- 비밀을 배포합니다.

- 응용 프로그램 상태를 확인합니다.

다음과 같은 기능 (다른 orchestrators 비교) 서비스 패브릭에서 배타적 있습니다.

- 신뢰할 수 있는 서비스 응용 프로그램 모델을 통해 상태 저장 서비스 기능입니다.

- Reliable Actors 응용 프로그램 모델을 통해 actor 패턴입니다.

- Windows 또는 Linux 컨테이너 외에도 본 운영 체제 미 설치 프로세스를 배포 합니다.

- 고급 롤링 업데이트 및 상태 검사 합니다.

### <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
[이전](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[다음](conclusions.md)
