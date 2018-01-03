---
title: "컨테이너화된 앱을 위한 Microsoft 플랫폼 및 도구 소개"
description: "Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a24f57216130a42eb11ef44abe462d4955601fdb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="introduction-to-the-microsoft-platform-and-tools-for-containerized-apps"></a>컨테이너화된 앱을 위한 Microsoft 플랫폼 및 도구 소개


그림 3-1 (응용 프로그램 개발, DevOps 인프라 프로세스 및 IT 관리 및 작업) 여러 팀에서 제공 하는 작업의 유형에 따라 분류 Docker 앱의 수명 주기에서 주요 사항 보여 줍니다. 일반적으로 기업에서 각 영역을 담당하는 "가상 사용자"의 프로필은 다릅니다. 기술도 마찬가지입니다.

![](./media/image1.png)

그림 3-1: Microsoft 플랫폼 및 도구를 사용하는 컨테이너화된 Docker 응용 프로그램의 수명 주기 주요 사항

컨테이너화된 Docker 수명 주기 워크플로는 처음에 개발자가 더 빠르게 시작하기 용이하도록 "기본적인 제품 옵션"에 따라 규정할 수 있지만 각 조직이나 기업의 다양한 상황에 맞게 조정할 수 있는 유연한 워크플로가 되도록 중심부에 개방적인 프레임워크가 있어야 한다는 것이 핵심적입니다. 워크플로 인프라(구성 요소와 제품)는 각 회사에서 나중에 보유하게 될 환경에 맞출 수 있을 만큼 충분히 유연해야 합니다. 개발 또는 DevOps 제품을 다른 사람과 맞바꿀 수 있을 정도여야 합니다. 플랫폼 및 인프라의 이러한 유연성, 개방성 및 광범위한 기술 옵션은 다음에 나오는 챕터에 설명된 것처럼 컨테이너화된 Docker 응용 프로그램에 대한 Microsoft의 우선 순위입니다.

표 3-1에서는 컨테이너화된 Docker 응용 프로그램에 대한 Microsoft DevOps의 의도는 사용자가 각 단계에 사용할 제품(Microsoft 또는 타사 제품)을 선택할 수 있도록 개방적인 DevOps 워크플로를 제공하는 한편, 이미 연결된 "기본 제품"을 제공하는 간소화된 워크플로를 제공함으로써 Docker 앱을 위한 기업 차원의 DevOps 워크플로를 빠르게 시작할 수 있게 하는 것임을 보여줍니다.

표 3-1: 모든 기술에 개방적인 DevOps 워크플로

| 호스트 | Microsoft 기술 | 타사-Azure 플러그형 |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Docker 앱용 플랫폼   | • Microsoft Visual Studio 및 Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Container Service<br /> • Azure Service Fabric<br /> • Azure Container Registry<br /> | • 모든 코드 편집기(예: Sublime)<br /> • 모든 언어(Node.js, Java, Go 등)<br /> • 모든 오케스트레이터 및 스케줄러<br /> • 모든 Docker 레지스트리<br /> |
| Docker 앱용 DevOps     | • Visual Studio Team Services<br /> • Microsoft Team Foundation Server<br /> • Azure Container Service<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion 등<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI 등<br /> • 온-프레미스 Docker Datacenter, Docker Swarm, Mesos DC/OS, Kubernetes 등<br /> |
| 관리 및 모니터링  | • Operations Management Suite<br /> • Applications Insights<br /> | • Marathon, Chronos 등<br />

표 3-1에 정의된 컨테이너화된 Docker 앱을 위한 Microsoft 플랫폼 및 도구는 다음과 같은 구성 요소로 이루어집니다.

-   **Docker 앱 개발용 플랫폼** "앱"을 구성하는 서비스나 서비스 컬렉션의 개발을 말합니다. 이 개발 플랫폼은 개발자가 공유 코드 리포지토리에 코드를 게시하기 전에 필요한 모든 작업을 제공합니다. 컨테이너로 배포된 서비스를 배포하는 것은 Docker 없이 동일한 앱이나 서비스를 개발하는 것과 매우 유사합니다. 원하는 언어(.NET, Node.js, Go 등)와 원하는 편집기 또는 IDE(예: Visual Studio 또는 Visual Studio Code)를 계속 사용할 수 있습니다. 그러나 Docker를 배포 대상으로 고려하기보다는 Docker 환경에서 서비스를 개발하세요. 컨테이너에서 로컬로 코드를 빌드, 실행, 테스트 및 디버그하여 개발 시 대상 환경을 제공할 수 있습니다. 대상 환경을 로컬로 제공하면 Docker 컨테이너에서 DevOps 수명 주기를 개선하는 데 큰 도움이 될 수 있는 요소를 설정합니다. Visual Studio 및 Visual Studio Code에는 개발 프로세스 내에서 Docker 컨테이너를 통합하는 확장 기능이 있습니다.

-   **Docker 앱을 위한 DevOps** Docker 응용 프로그램을 만드는 개발자는 VSTS(Visual Studio Team Services) 또는 다른 타사 제품(예: Jenkins)을 사용하여 포괄적인 자동 ALM(응용 프로그램 수명 주기 관리)을 구축할 수 있습니다.

VSTS를 통해 개발자는 VSTS-Git, GitHub, 모든 원격 Git 리포지토리 또는 Subversion 등 어디서나 소스 코드 제어를 처리하는 빠르고 직관적인 프로세스, CI(지속적인 통합), 내부 단위 세트스, 컨테이너/서비스 간 통합 테스트, CD(지속적인 업데이트) 및 RM(릴리스 관리)을 위한 컨테이너 중심의 DevOps를 만들 수 있습니다. 또한 개발자는 개발 환경에서 준비 및 프로덕션 환경까지 Azure Container Service로의 Docker 응용 프로그램 릴리스를 자동화할 수 있습니다.

-   IT 프로덕션 관리 및 모니터링.

**관리** IT는 여러 가지 방법으로 프로덕션 응용 프로그램 및 서비스를 관리할 수 있습니다.

-   **Azure Portal** 오픈 소스 오케스트레이터를 사용 중인 경우 Docker Datacenter 및 Mesosphere Marathon 같은 클러스터 관리 도구와 ACS(Azure Container Service)를 사용하면 Docker 환경을 설정하고 유지 관리하는 데 도움이 됩니다. Azure Service Fabric을 사용 중인 경우 Service Fabric Explorer를 통해 클러스터를 시각화하고 구성할 수 있습니다.

-   **Docker 도구** 익숙한 도구를 사용하여 컨테이너 응용 프로그램을 관리할 수 있습니다. 컨테이너 작업을 클라우드로 이동하기 위해 기존 Docker 관리 방법을 변경할 필요가 없습니다. 이미 익숙한 응용 프로그램 관리 도구를 사용하고 원하는 오케스트레이터를 위한 표준 API 끝점을 통해 연결하세요. 또한 다른 타사 도구를 사용하여 Docker Datacenter 또는 CLI Docker 도구와 같은 Docker 응용 프로그램을 관리할 수도 있습니다.

-   **오픈 소스 도구** ACS는 오케스트레이션 엔진에 대한 표준 API 끝점을 노출하므로 시각화 도우미, 모니터링, 명령줄 도구 및 향후 제공 예정인 도구와 같은 가장 인기 있는 도구가 ACS와 호환되고, 대부분의 경우 바로 작동합니다.

**모니터링** 프로덕션 환경을 실행하는 동안 다음을 사용하여 다각도로 모니터링할 수 있습니다.

-   **OMS(Operations Management Suite)** "OMS 컨테이너 솔루션"은 컨테이너 및 컨테이너 호스트가 있는 위치에 대한 정보를 표시하여 Docker 호스트 및 컨테이너를 관리하고 모니터링할 수 있습니다. 또한 CPU, 메모리, 네트워크 및 저장소 등 컨테이너 및 호스트에 대한 성능 메트릭을 표시하여 문제를 해결하고, 노이지 네이버(noisy neighbor) 컨테이너를 찾을 수 있게 해줍니다.

-   **Application Insights** 서비스에 SDK를 설치하기만 하면 프로덕션 Docker 응용 프로그램을 모니터링하여 응용 프로그램의 원격 분석 데이터를 얻을 수 있습니다.

따라서 Microsoft는 컨테이너화된 Docker 응용 프로그램의 전체 수명 주기에 대한 완벽한 기반을 제공합니다. 그러나 *원하는 대로 선택하고 기존 도구 및 프로세스와 통합할 수 있게 해주는 제품과 기술의 모음*입니다. 광범위한 접근법의 유연성과 심층적인 기능의 강력함은 컨테이너화된 Docker 응용 프로그램 개발 분야에서 Microsoft가 유리한 위치를 점할 수 있게 해줍니다.

>[!div class="step-by-step"]
[이전] (../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md) [다음] (../design-develop-containerized-apps/index.md)
