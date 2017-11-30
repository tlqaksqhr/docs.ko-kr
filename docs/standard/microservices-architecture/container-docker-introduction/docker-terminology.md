---
title: "Docker 용어"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Docker 용어"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 885b1fbd3369dec54ebde21a5378630c764f852d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="docker-terminology"></a>Docker 용어

이 섹션에는 용어 및 정의 하면 익숙해야 Docker 깊은 들어가기 전에 나열 됩니다. 추가로 정의 대 한 참조는 광범위 한 [용어집](https://docs.docker.com/v1.11/engine/reference/glossary/) Docker에서 제공 합니다.

**컨테이너 이미지**: 모든 종속성 및 컨테이너를 만드는 데 필요한 정보를 가진 패키지입니다. 이미지는 컨테이너 런타임에서 사용할 배포 및 실행 구성 및 모든 종속성 (예: 프레임 워크)를 포함 합니다. 일반적으로 이미지는 컨테이너의 파일 시스템을 구성 하기 위해 서로 위에 쌓입니다 계층이 여러 기본 이미지에서 파생 됩니다. 이미지는 만든 후 변경할 수 없습니다.

**컨테이너**:는 Docker 이미지의 인스턴스. 컨테이너는 단일 응용 프로그램, 프로세스 또는 서비스의 실행을 나타냅니다. Docker 이미지를, 실행 환경 및 명령의 표준 집합의 내용을 구성 됩니다. 서비스를 크기 조정 하는 경우에 동일한 이미지에서 컨테이너의 여러 인스턴스를 만듭니다. 또는 일괄 작업 각 인스턴스에 다른 매개 변수를 전달 하는 동일한 이미지에서 여러 컨테이너를 만들 수 있습니다.

**태그**: 표시 또는 레이블 서로 다른 이미지 또는 (버전 번호 또는 대상 환경)에 따라 동일한 이미지의 버전을 식별할 수 있도록 이미지에 적용할 수 있습니다.

**Dockerfile**: Docker 이미지를 작성 하는 방법에 대 한 지침을 포함 하는 텍스트 파일입니다.

**빌드**: 정보 및 해당 Dockerfile files 추가 이미지 빌드되는 폴더에 제공 된 컨텍스트를 기준으로 작업의 컨테이너 이미지를 작성 합니다. Docker docker 빌드 명령 사용 하 여 이미지를 작성할 수 있습니다.

**리포지토리 (리 포)**: 이미지 버전을 나타내는 태그를 붙이지 관련된 Docker 이미지의 컬렉션입니다. 일부 리포지토리 등만 런타임 (밝은) 포함 된 이미지 (많은) Sdk에 포함 된 이미지와 같은 특정 이미지의 여러 변형이 포함 되어 있습니다. 이러한 변형 태그로 표시할 수 있습니다. 단일 리포지토리 플랫폼 변형 Linux 이미지 등 Windows 이미지를 포함할 수 있습니다.

**레지스트리**: 저장소에 대 한 액세스를 제공 하는 서비스입니다. 대부분의 공용 이미지에 대 한 기본 레지스트리는 [Docker 허브](https://hub.docker.com/) (조직으로 Docker가 소유). 레지스트리는 일반적으로 여러 팀에서 저장소를 포함합니다. 회사에 저장 하 고 이미지를 작성 한 관리 사설 레지스트리 있는 경우가 많습니다. Azure 컨테이너 레지스트리는 또 다른 예입니다.

**Docker 허브**: 이미지를 업로드 하 고 작업을 하려면 공개 레지스트리 합니다. Docker 허브는 Docker 이미지 호스팅, 공개 또는 개인 레지스트리, 빌드 트리거 및 웹 후크 및 GitHub 및 Bitbucket와의 통합을 제공합니다.

**Azure 컨테이너 레지스트리**: Docker 이미지와 Azure에서 구성 요소를 사용 하기 위한 공용 리소스입니다. 이 Azure에서 배포를 가까운 이며 수 있도록 액세스에 대 한 제어를 제공 하는 레지스트리를 통해 Azure Active Directory 그룹 및 권한을 사용 합니다.

**Docker 신뢰 레지스트리 DTR ()**: A Docker 레지스트리 (Docker)에서 수 있는 서비스 조직 데이터 센터와 네트워크 내에서 유지 되므로 온-프레미스를 설치 합니다. 기업 내 관리 해야 하는 개인 이미지에는 것이 유용 합니다. Docker Trusted Registry Docker 데이터 센터 제품의 일부분으로 포함 됩니다. 자세한 내용은 참조 [Docker 신뢰 레지스트리 DTR ()](https://docs.docker.com/docker-trusted-registry/overview/)합니다.

**Docker Community Edition (CE)**: 개발 도구 창과 macOS 빌드, 실행 및 테스트 로컬로 컨테이너입니다. Windows 용 docker CE Linux와 Windows 컨테이너에 대 한 개발 환경을 제공합니다. Windows의 Linux Docker 호스트를 기반으로 한 [Hyper-v](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) 가상 컴퓨터. Windows 컨테이너에 대 한 호스트를 직접 Windows 기반 합니다. Apple 하이퍼바이저 프레임 워크를 기반으로 하는 Mac 용 docker CE 및 [xhyve 하이퍼바이저](https://github.com/mist64/xhyve), Mac OS X. CE Windows 용 Docker와 Mac에 대 한 Linux Docker 호스트 가상 컴퓨터를 제공 하는 Oracle을 기반으로 하는 Docker 도구 상자를 대체 VirtualBox 합니다.

**Docker Enterprise Edition (EE)**:는 엔터프라이즈급 버전의 Linux 및 Windows 개발을 위한 Docker 도구입니다.

**작성**: YAML 및 명령줄 도구에 대 한 파일 형식을 정의 하 고 실행 중인 다중 컨테이너 응용 프로그램에 대 한 메타 데이터를 사용 합니다. 환경에 따라 값을 재정의할 수 있는 하나 이상의.yml 파일과 함께 여러 이미지를 기반으로 하는 단일 응용 프로그램을 정의 합니다. 정의 만든 후에 단일 명령으로 여러 컨테이너 전체 응용 프로그램을 배포할 수 있습니다 (docker-를 작성) 이미지당 컨테이너 Docker 호스트에 만들어지는 합니다.

**클러스터**: 컬렉션의 단일 가상 Docker 호스트 된 응용 프로그램 서비스의 여러 인스턴스를 확장할 수 있도록 노출 Docker 호스트 클러스터 내의 여러 호스트에 걸쳐 분산 합니다. Docker는 Docker Swarm, Mesosphere DC/운영 체제, Kubernetes, 및 Azure 서비스 패브릭와 docker 클러스터를 만들 수 있습니다. (으로 클러스터를 일반적으로 참조 하는 클러스터를 관리 하기 위한 docker는 Docker Swarm을 사용 하는 경우는 *swarm* 클러스터 대신.)

**Orchestrator**: 클러스터와 Docker 호스트의 관리를 단순화 하는 도구입니다. 해당 이미지, 컨테이너 및 명령줄 인터페이스 (CLI)를 통해 호스트를 관리할 수 있게 orchestrators 또는 그래픽 UI입니다. 컨테이너 네트워킹, 구성, 부하 분산, 서비스 검색, 고가용성, Docker 호스트 구성 및 더를 관리할 수 있습니다. orchestrator는 실행, 배포, 배율 및 노드 컬렉션 간에 작업 부하를 복구 하는 일을 담당 합니다. 일반적으로, orchestrator 제품은 같은 Mesosphere DC/OS, Kubernetes, docker는 Docker Swarm 및 Azure 서비스 패브릭 클러스터 인프라를 제공 하는 동일한 제품입니다.


>[!div class="step-by-step"]
[이전] (docker-defined.md) [다음] (docker-컨테이너-이미지-registries.md)
