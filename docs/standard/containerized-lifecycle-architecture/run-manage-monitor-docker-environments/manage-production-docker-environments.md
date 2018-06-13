---
title: 프로덕션 Docker 환경 관리
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 5ecf1fbc164ff4170951894abc071908f45178d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573883"
---
# <a name="manage-production-docker-environments"></a>프로덕션 Docker 환경 관리

클러스터 관리 및 오케스트레이션은 호스트 그룹을 제어 하는 과정입니다. 호스트 추가 및 제거 호스트 및 컨테이너의 현재 상태에 대 한 정보 가져오기 및 시작 하 고, 프로세스를 중지 하는 클러스터에서이 포함 될 수 있습니다. 클러스터 관리 및 오케스트레이션은와 밀접 하 게 해야 하기 때문에 스케줄러 각 호스트에 대 한 액세스 클러스터의 서비스를 예약 하려면 예약 합니다. 이러한 이유로 동일한 도구가 주로 두 가지 용도로 사용 됩니다.

## <a name="container-service-and-management-tools"></a>컨테이너 서비스 및 관리 도구

컨테이너 서비스는 인기 있는 오픈 소스 컨테이너 클러스터링 및 오케스트레이션 솔루션의 신속한 배포를 제공합니다. Docker 이미지를 사용 하 여 응용 프로그램 컨테이너가 완전히 이식 가능 하도록 합니다. 컨테이너 서비스를 사용 하 여 DC/OS (Mesosphere 및 Apache Mesos에 의해 제공)를 배포할 수 있습니다 및 수천에 이러한 응용 프로그램을 확장할 수 있는지 확인 하기 위해 Azure 포털 또는 Azure 리소스 관리자 템플릿을 클러스터 docker는 Docker Swarm-수만 포함 하 여-의 다시 설정 합니다.

Azure 가상 컴퓨터 크기 집합을 사용 하 여 이러한 클러스터를 배포 하 고 클러스터 네트워킹 및 저장소에 대 한 Azure 기능 활용 합니다. 컨테이너 서비스에 액세스 하려면 Azure 구독이 필요 합니다. 컨테이너 서비스를 사용 하면 오케스트레이션 계층에 포함 하 여 응용 프로그램 이식성을 유지 하면서 Azure의 엔터프라이즈급 기능을 걸릴 수 있습니다.

표 6-1의 orchestrators, 스케줄러, 및 클러스터링 플랫폼 관련 된 일반 관리 도구를 나열 합니다.

표 6-1: Docker 관리 도구


| 관리 도구      | 설명           | 관련된 orchestrators |
|-----------------------|-----------------------|-----------------------|
| 컨테이너 서비스\(Azure 포털에서 관리 UI) | [컨테이너 서비스](https://azure.microsoft.com/en-us/services/container-service/) 쉽게 이용할 수를 제공 하는 방식으로 시작 [Azure에서 컨테이너-클러스터 배포](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment) Mesosphere DC/OS, Kubernetes 및 docker는 Docker Swarm와 같은 인기 있는 orchestrators에 따라 합니다. <br /><br /> 컨테이너 서비스는 해당 플랫폼의 구성을 최적화합니다. 크기, 호스트, 수 및 다양 한 orchestrator 도구를 선택 해야 하 고 다른 모든 항목을 처리 하는 컨테이너 서비스 키를 누릅니다. | Mesosphere DC/OS <br /><br /> Kubernetes <br /><br /> Docker Swarm |
| Docker 유니버설 제어 평면\(온-프레미스 또는 클라우드) | [Docker 유니버설 제어 평면](https://docs.docker.com/v1.11/ucp/overview/) Docker에서 엔터프라이즈급 클러스터 관리 솔루션입니다. 그 한 곳에서 전체 클러스터를 관리할 수 있습니다. <br /><br /> Docker 유니버설 제어 평면 docker는 Docker Swarm, 유니버설 제어 평면 Docker 및 Docker Trusted Registry 제공 하는 Docker 데이터 센터 라는 상용 제품의 일부분으로 포함 됩니다. <br /><br /> Docker 데이터 센터 설치 된 온-프레미스 이거나 Azure와 같은 공용 클라우드를 프로 비전 합니다. | Docker는 docker Swarm\(컨테이너 서비스에서 지원) |
| Docker 클라우드\(Tutum; 클라우드 SaaS 라고도 함) | [Docker 클라우드](https://docs.docker.com/docker-cloud/) 는 빌드 및 테스트 기능을 Dockerized 응용 프로그램 이미지를 설정 하 고 호스트 인프라를 관리 하는 데 유용한 도구를 사용 하 여 오케스트레이션 기능 및 Docker 레지스트리를 제공 하는 호스팅된 관리 서비스 (SaaS) 및 구체적 인프라에 이미지 배포를 자동화할 수 있도록 배포 기능을 추가 합니다. Docker는 Docker Swarm 클러스터를 실행 하는 컨테이너 서비스에서 인프라를 SaaS Docker 클라우드 계정과 연결할 수 있습니다. | Docker는 docker Swarm\(컨테이너 서비스에서 지원) |
| Mesosphere 마라톤\(온-프레미스 또는 클라우드) | [풀 마라톤](https://mesosphere.github.io/marathon/docs/marathon-ui.html) Mesosphere의 DC/OS 및 Apache Mesos는 프로덕션 수준의 컨테이너 오케스트레이션 및 스케줄러 플랫폼입니다. <br /><br /> Mesos와 함께 작동 (DC/OS가 기반 Apache Mesos) 장기 실행 제어에 서비스를 제공 하며 제공는 [프로세스 및 컨테이너 관리에 대 한 웹 UI](https://mesosphere.github.io/marathon/docs/marathon-ui.html)합니다. 웹 UI 관리 도구를 제공 | DC/OS mesosphere\(Apache Mesos 기반; 컨테이너 서비스에서 지원) |
| Google Kubernetes | [Kubernetes](http://kubernetes.io/docs/user-guide/ui/#dashboard-access) 조정, 일정 및 클러스터 인프라에 걸쳐 있습니다. 사용 되는 오픈 소스 플랫폼 컨테이너 중심 인프라를 제공 하는 호스트의 클러스터를 배포, 배율 및 응용 프로그램 컨테이너의 작업 자동화입니다. | Google Kubernetes\(컨테이너 서비스에서 지원) |

## <a name="azure-service-fabric"></a>Azure Service Fabric

클러스터 배포 및 관리에 대 한 다른 선택에는 Azure 서비스 패브릭 됩니다. [서비스 패브릭](https://azure.microsoft.com/en-us/services/service-fabric/) 컨테이너 오케스트레이션 개발자를 포함 하는 Microsoft microservices 플랫폼은 확장성이 뛰어난 microservices 응용 프로그램을 빌드하는 모델 프로그래밍 합니다. 서비스 패브릭에서는 Docker 현재 Linux 미리 보기 버전에서와 같이 [linux 미리 보기 서비스 패브릭](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere), 및 Windows 컨테이너에 대 한 [다음 릴리스에서](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview)합니다.

다음은 서비스 패브릭 관리 도구:

-   [서비스 패브릭 용 azure 포털](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-creation-via-portal) 클러스터 관련 작업 (만들기/업데이트/삭제)는 클러스터 또는 인프라 (Vm, 부하 분산 장치, 네트워킹 등)를 구성 합니다.

-   [Azure 서비스 패브릭 탐색기](https://docs.microsoft.com/azure/service-fabric/service-fabric-visualizing-your-cluster) insights 및 응용 프로그램 및 서비스의 관점 및 노드/Vm의 관점에서 서비스 패브릭 클러스터에 대해 특정 작업을 제공 하는 특수 한 웹 UI 도구입니다.


>[!div class="step-by-step"]
[이전] [다음] (모니터-컨테이너 화 된-응용 프로그램-services.md) (run-microservices-based-applications-in-production.md)
