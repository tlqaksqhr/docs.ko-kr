---
title: "연습 및 technical 시작된 개요 가져오기"
description: "기존.NET 응용 프로그램을 Azure 클라우드 및 Windows 컨테이너를 최신식 | 연습 및 technical 시작된 개요 가져오기"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ead28fe1ffe1e002af73642a1c3b2e72479520f4
ms.sourcegitcommit: bf8a3ba647252010bdce86dd914ac6c61b5ba89d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>연습 및 technical 시작된 개요 가져오기 

이 전자책 (영문)의 크기를 제한 하려면 만들었고 추가 기술 설명서 및 전체 연습 GitHub 리포지토리에서 사용할 수 있습니다. 온라인 일련의이 장에서 설명 하는 연습에서는 Windows 컨테이너와 Azure로 배포를 기반으로 하는 여러 환경 설치 하는 단계별 설명 합니다.

다음 섹션에서는 각 연습 란에 대 한 해당 목표, 상위 수준 비전-하 고 관련 된 작업에 대 한 다이어그램을 제공 합니다. 자체의 연습을 얻을 수에 *eShopModernizing* 앱 GitHub 리포지토리에 wiki에서 [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki)합니다.

# <a name="technical-walkthrough-list"></a>기술 연습 목록

다음 started 연습 리프트 하 및 컨테이너를 사용 하 여 이동 하 고 다음 Azure에서 배포의 여러 선택 항목을 사용 하 여 이동할 수 있는 샘플 응용 프로그램에 일관 되 고 포괄적인 기술 지침을 제공 합니다.

다음 연습 중 각각의 새 샘플 eShopLegacy 및 eShopModernizing 앱의 경우에 GitHub에서 사용할 수 있는 사용 하 여 [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)합니다.

-   **둘러보기의 eShop 레거시 응용 프로그램**

-   **Windows 컨테이너를 기존.NET 응용 프로그램을 컨테이너 화합니다**

-   **Azure Vm에 Windows 컨테이너 기반 앱 배포**

-   **Azure 컨테이너 서비스에서 Kubernetes에 Windows 컨테이너 기반 앱 배포**

-   **Azure 서비스 패브릭에 Windows 컨테이너 기반 앱 배포**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>EShop 레거시 응용 프로그램 연습 1: 둘러보기

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a>개요

이 연습에서는 두 개의 샘플 레거시 응용 프로그램의 초기 구현을 탐색할 수 있습니다. 두 샘플 앱은 모놀리식 아키텍처 및 기존 ASP.NET을 사용 하 여 만든 합니다. ASP.NET을 기반으로 한 응용 프로그램은 4.x MVC; 두 번째 응용 프로그램은 ASP.NET 4.x Web Forms를 기반으로 합니다. 응용 프로그램은 모두에 [eShopModernizing GitHub 리포지토리](https://github.com/dotnet-architecture/eShopModernizing)합니다.

두 샘플 앱을 컨테이너 화할 수, 하는 방식과 비슷하게 수 컨테이너 화할 때는 기존 [Windows Communication Foundation](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) (WCF) 응용 프로그램을 데스크톱 응용 프로그램으로 사용할 수 있도록 합니다. 예를 들어 참조 [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms)합니다.

### <a name="goals"></a>목표

이 연습에서는 주요 목표는 단순히 코드 및 구성 하 고 이러한 앱을 친숙 해지기 합니다. 생성 하 고 모의 데이터를 사용 하 여 테스트 목적으로 SQL 데이터베이스를 사용 하지 않고 있음을 앱을 구성할 수 있습니다. 이 선택적 구성은 분리 된 방식으로 종속성 주입을 기반으로 합니다.

### <a name="scenario"></a>시나리오

그림 5-1 원래 레거시 응용 프로그램의 간단한 시나리오를 보여 줍니다.

> ![원래 레거시 응용 프로그램의 간단한 아키텍처 시나리오](./media/image5-1.png)
>
> **그림 5-1입니다.** 원래 레거시 응용 프로그램의 간단한 아키텍처 시나리오

비즈니스 도메인 관점에서 두 앱 모두 동일한 카탈로그 관리 기능을 제공합니다. EShop 엔터프라이즈 팀의 멤버를 보고 편집할 제품 카탈로그 응용 프로그램을 사용 합니다. 그림 5-2에는 초기 앱 스크린 샷을 보여 줍니다.

![ASP.NET MVC와 ASP.NET Web Forms 응용 프로그램 (기존/레거시 technologies)](./media/image5-2.png)

> **그림 5-2입니다.** ASP.NET MVC와 ASP.NET Web Forms 응용 프로그램 (기존/레거시 technologies)

이들은 탐색 및 카탈로그 항목을 수정 하는 데 사용 되는 웹 응용 프로그램입니다. 두 앱 모두 동일한 비즈니스 기능/기능을 제공 하는 팩트는 단순히 비교 목적으로 합니다. ASP.NET Web Forms 및 ASP.NET MVC 프레임 워크를 사용 하 여 만든 앱에 대 한 비슷한 현대화 프로세스를 볼 수 있습니다.

종속성에 ASP.NET 4.x 또는 이전 버전 (또는 MVC에 대 한 Web Forms에 대 한) 의미 이러한 응용 프로그램 코드는 ASP.NET Core MVC를 사용 하 여 완전히 다시 작성 하지 않으면.NET Core에서 실행 되지 않습니다. 이 코드를 다시 작성 하거나 다시 설계 않으려면 고 수 있는 기존 응용 프로그램을 컨테이너 화할 계속 동일한.NET 기술 및 동일한 코드를 사용 하 여 지점을 보여 줍니다. 레거시 코드를 변경 하지 않고 컨테이너에서 이러한 응용 프로그램을 실행 하는 방법을 확인할 수 있습니다.

### <a name="benefits"></a>이점

이 연습에서는 이점은 간단한: 종속성 주입에 따라 코드 및 응용 프로그램 구성에 잘 알고 가져옵니다. 그런 다음 컨테이너 화할 나중에 여러 환경에 배포할 때는이 접근 방식으로 테스트할 수 있습니다.

### <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>연습 2: Windows 컨테이너를 기존.NET 응용 프로그램을 컨테이너 화합니다

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

### <a name="overview"></a>개요

Windows 컨테이너를 사용 하 여 MVC, Web Forms, WCF, 프로덕션, 개발 및 테스트 환경에 기반 하는 것과 같은 기존.NET 응용 프로그램의 배포를 향상 시킵니다.

### <a name="goals"></a>목표

이 연습의 목표 containerizing 기존.NET Framework 응용 프로그램에 대 한 몇 가지 옵션을 표시 하는입니다. 다음과 같은 작업을 수행할 수 있습니다.

-   사용 하 여 응용 프로그램을 컨테이너 화할 [Docker 용 Visual Studio 2017 도구](https://docs.microsoft.com/dotnet/core/docker/visual-studio-tools-for-docker) (Visual Studio 2017 또는 이후 버전).

-   수동으로 추가 하 여 응용 프로그램을 컨테이너 화할는 [Dockerfile](https://docs.docker.com/engine/reference/builder/)를 사용 하 여는 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)합니다.

-   사용 하 여 응용 프로그램을 컨테이너 화할는 [Img2Docker](https://github.com/docker/communitytools-image2docker-win) 도구 (Docker에서 오픈 소스 도구).

이 연습에서는 Visual Studio 2017 Tools for Docker 접근 방식에 중점을 두고 있지만 Dockerfile을 사용 하 여 시에서 다른 두 가지 방법으로 매우 비슷합니다.

### <a name="scenario"></a>시나리오

그림 5-3 색인화 eShop 레거시 응용 프로그램에 대 한 시나리오를 보여 줍니다.

> ![개발 환경에서 화 된 응용 프로그램의 간소화 된 아키텍처 다이어그램](./media/image5-3.png)
>
> **그림 5-3입니다.** 개발 환경에서 화 된 응용 프로그램의 간소화 된 아키텍처 다이어그램

### <a name="benefits"></a>이점

컨테이너에서 단일 응용 프로그램을 실행 하는 이점이 있습니다. 먼저, 응용 프로그램에 대 한 이미지를 만듭니다. 해당 시점부터 모든 배포가 동일한 환경에서 실행 됩니다. 모든 컨테이너 동일한 운영 체제 버전을 사용 하 여, 설치 하는 종속성의 버전은, 동일한.NET framework 버전을 사용 하 여 및 동일한 프로세스를 사용 하 여 작성 됩니다. 기본적으로, Docker 이미지를 사용 하 여 응용 프로그램의 종속성을 제어 합니다. 종속성의 컨테이너를 배포할 때 응용 프로그램으로 이동 합니다.

또 다른 이점은 개발자가 Windows 컨테이너에서 제공 되는 일관 된 환경에서 응용 프로그램을 실행할 수입니다. 특정 버전으로 표시 하는 문제 스테이징 또는 프로덕션 환경에는 대신 즉시 발견 될 수 있습니다. 개발 팀의 멤버에서 사용 하는 개발 환경의 차이점 중요 응용 프로그램 컨테이너에서 실행 하는 경우 작습니다.

컨테이너 화 된 응용 프로그램에 볼록한 확장 곡선을 갖게 됩니다. 컨테이너 화 된 응용 프로그램 VM 또는 물리적 컴퓨터 컴퓨터당 일반 응용 프로그램 배포에 비해 더 많은 응용 프로그램 및 서비스 인스턴스 (컨테이너에 기반)를 사용할 수 있습니다를 사용 합니다. 이 명령은 더 높은 밀도 필요한 적은으로 해석 orchestrators Kubernetes 서비스 패브릭 등을 사용 하는 경우에 특히 리소스입니다.

컨테이너 화 이상적인 상황에서 응용 프로그램 코드를 변경한 필요 하지 않습니다 (C\#). 대부분의 시나리오에서 하기만 하면 Docker 배포 메타 데이터 파일 (Dockerfiles 및 Docker Compose 파일).

### <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세하게 탐색할: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Azure Vm에 Windows 컨테이너 기반 앱을 배포 하는 연습 3:

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>개요

Azure에서 Windows Server 2016 VM에서 Docker 호스트에 배포 하는 개발/테스트/스테이징 환경을 신속 하 게 설정할 수 있습니다. 또한, 테스터 또는 비즈니스 사용자가 유효성을 검사할 앱에 대 한 공통 위치를 제공 합니다. Vm 유효한 IaaS 프로덕션 환경 수도 있습니다.

### <a name="goals"></a>목표

이 연습의 목표는 Windows Server 2016 또는 이상 버전을 기반으로 하는 Azure Vm에 Windows 컨테이너를 배포할 때 사용할 수 있는 여러 대체 방법을 설명 합니다.

### <a name="scenarios"></a>시나리오

몇 가지 시나리오는이 연습에 포함 됩니다.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Docker 엔진 연결을 통해 dev PC에서에서 Azure VM 배포 시나리오 a:

![Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포](./media/image5-4.png)

> **그림 5-4입니다.** Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Docker 레지스트리를 통해 Azure VM에 배포 시나리오 b:

![Docker 레지스트리를 통해 Azure VM에 배포](./media/image5-5.png)

> **그림 5-5입니다.** Docker 레지스트리를 통해 Azure VM에 배포

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a>Visual Studio Team Services에서 CI/CD 파이프라인에서 Azure VM에 시나리오 c: 배포

![Visual Studio Team Services에서 CI/CD 파이프라인에서 Azure VM에 배포](./media/image5-6.png)

> **그림 5-6입니다.** Visual Studio Team Services에서 CI/CD 파이프라인에서 Azure VM에 배포

### <a name="azure-vms-for-windows-containers"></a>Windows 컨테이너에 대 한 azure Vm

Windows 컨테이너에 대 한 azure Vm은 Windows Server 2016, Windows 10을 기반으로 하는 Vm 하기만 하면 또는 이상 버전에서 모두 Docker 엔진으로 설정 합니다. 대부분의 경우에서 Azure Vm에서 Windows Server 2016을 사용 합니다.

Azure에서 현재 V 제공 **컨테이너와 Windows Server 2016**합니다. Windows Server Core 또는 Windows Nano Server과 함께 새로운 Windows Server 컨테이너 기능을 사용 하려면이 VM을 사용할 수 있습니다. 컨테이너 OS 이미지 설치 되 고 VM은 Docker에서 사용할 수 있습니다.

### <a name="benefits"></a>이점

Azure에 배포할 Windows 컨테이너를 온-프레미스 Windows Server 2016 Vm으로 배포할 수 있지만 Windows Server 컨테이너 Vm이 즉시 사용을 시작 하는 쉬운 방법이 가져옵니다. 테스터 및 Azure VM 크기 집합을 통해 자동 확장성에 액세스할 수 있는 공통 온라인 위치를 가져올 수도 있습니다.

### <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Azure 컨테이너 서비스에서 Kubernetes에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 연습 4:

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

> **그림 5-7입니다.** 개발 환경에서 Kubernetes 클러스터에 직접 배포 합니다.

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a>Team Services에서 파이프라인 CI/CD에서 Kubernetes 클러스터 시나리오 b: 배포

![Team Services에서 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포 합니다.](./media/image5-8.png)

> **그림 5-8입니다.** Team Services에서 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포 합니다.

### <a name="benefits"></a>이점

Kubernetes에 있는 클러스터를 배포 하는 다음과 같은 많은 이점이 있습니다. 가장 큰 장점은 적용 되는 즉시 환경 있는 있습니다 수 확장 (내부 확장성의 기존 노드에서에서)를 사용 하 고 클러스터 (에서 노드 또는 Vm의 수에 따라 컨테이너 인스턴스 수에 따라 응용 프로그램을 가져올 전역 확장성 클러스터의)입니다.

Azure 컨테이너 서비스 인기 있는 오픈 소스 도구와 기술을 Azure에 맞게 최적화합니다. 사용자 컨테이너 및 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션 가져오기 크기, 호스트의 수를 선택 하 고 다른 모든 항목을 처리 하는 orchestrator 도구-컨테이너 서비스 키를 누릅니다.

Kubernetes와 개발자가 수에서 진행 상황 실제 및 가상 컴퓨터에 대 한 다음과 같은 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라 계획:

-   여러 컨테이너를 기반으로 응용 프로그램

-   컨테이너 인스턴스를 복제 하는 가로 자동 크기 조정

-   이름 지정 및 검색 (예를 들어 내부 DNS)

-   로드 균형 조정

-   롤링 업데이트

-   암호를 배포합니다.

-   응용 프로그램 상태 확인

## <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세하게 탐색할: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-드 ( Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Azure 서비스 패브릭에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 연습 5:

### <a name="technical-walkthrough-availability"></a>기술 연습 가용성

전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>개요

Windows 컨테이너를 기반으로 하는 응용 프로그램 더욱 해소 IaaS Vm에서 다른 페이지로 이동 하는 플랫폼에서 사용 하 여 신속 하 게 할 수 있습니다. 이 쉽게 높은 확장성을 달성 하는 데 필요한 및 더 잘 자동화 확장성, 고 크게 향상에 대 한 배포 및 버전 관리를 자동화 합니다. 다른 공용 클라우드 또는 Azure 클라우드에서 사용할 수 있지만 가능 온-프레미스를 사용 하는 Azure 서비스 패브릭 orchestrator를 사용 하 여 이러한 목표를 달성할 수 있습니다.

### <a name="goals"></a>목표

이 연습의 목표는 azure에서 서비스 패브릭 클러스터에 Windows 컨테이너-> 기반 응용 프로그램을 배포 하는 방법에 알아보려면입니다. 서비스 패브릭을 처음부터 새로 배포은 두 단계로 이루어집니다.

1.  Azure로 (또는 다른 환경에) 서비스 패브릭 클러스터를 배포 합니다.

2.  서비스 패브릭 클러스터에 응용 프로그램 및 관련된 리소스를 배포 합니다.

### <a name="scenarios"></a>시나리오

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>개발 환경에서 서비스 패브릭 클러스터에 직접 시나리오 a: 배포

![개발 환경에서 서비스 패브릭 클러스터에 직접 배포 합니다.](./media/image5-9.png)

> **그림 5-9입니다.** 개발 환경에서 서비스 패브릭 클러스터에 직접 배포 합니다.

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a>Team Services에서 파이프라인 CI/CD에서 서비스 패브릭 클러스터를 시나리오 b: 배포

![Visual Studio Team Services에서 CI/CD 파이프라인에서 서비스 패브릭 클러스터를 배포](./media/image5-10.png)

> **그림 5-10입니다.** Visual Studio Team Services에서 CI/CD 파이프라인에서 서비스 패브릭 클러스터를 배포

## <a name="benefits"></a>이점

서비스 패브릭 클러스터에 배포의 이점을 Kubernetes 사용의 이점와 비슷합니다. 그러나 한 가지 차이점 서비스 패브릭 Windows 응용 프로그램의 Windows 컨테이너에 대 한 미리 보기 초기까지 2017의 대체 된 있는 Kubernetes에 비해 매우 성숙한 프로덕션 환경 된다는 점입니다. (Kubernetes는 Linux 용 더 성숙한 환경)입니다. 

Azure Service Fabric을 사용 하 여의 주요 장점은 적용 되는 즉시 환경 있는 있습니다 수 확장 (내부 확장성의 기존 노드에서에서)를 사용 하 고의 수에 따라 컨테이너 인스턴스 수에 따라 응용 프로그램을 가져올 노드 또는 클러스터 (클러스터의 전역 확장성)에서 Vm입니다.

Azure 서비스 패브릭 응용 프로그램 구성에 대 한 및 사용자 컨테이너에 대 한 이식성을 제공합니다. 서비스 패브릭 클러스터에 Azure에서 또는 자체 데이터 센터에서 온-프레미스 설치를 할 수 있습니다. 다른 클라우드에서 서비스 패브릭 클러스터 같은 설치도 [AWS Amazon](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/)합니다.

서비스 패브릭 개발자 수에서 진행 상황 실제 및 가상 컴퓨터에 대 한 다음과 같은 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라 계획:

-   여러 컨테이너를 기반으로 응용 프로그램입니다.

-   가로 크기 자동 조정 및 컨테이너 인스턴스를 복제합니다.

-   이름 지정 및 (예를 들어 내부 DNS)를 검색 합니다.

-   로드 균형 조정 합니다.

-   롤링 업데이트 합니다.

-   비밀을 배포합니다.

-   응용 프로그램 상태를 확인합니다.

다음과 같은 기능 (다른 orchestrators 비교) 서비스 패브릭에서 배타적 있습니다.

-   신뢰할 수 있는 서비스 응용 프로그램 모델을 통해 상태 저장 서비스 기능입니다.

-   Reliable Actors 응용 프로그램 모델을 통해 actor 패턴입니다.

-   Windows 또는 Linux 컨테이너 외에도 본 운영 체제 미 설치 프로세스를 배포 합니다.

-   고급 롤링 업데이트 및 상태 검사 합니다.

### <a name="next-steps"></a>다음 단계

GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
[이전](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[다음](conclusions.md)
