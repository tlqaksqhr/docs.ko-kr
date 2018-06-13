---
title: Docker란?
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: c566c4104f21ff6a55646d96e141cde4c7722735
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569670"
---
# <a name="what-is-docker"></a>Docker란?

[Docker](https://www.docker.com/) 는 [오픈 소스 프로젝트](https://github.com/docker/docker) 클라우드 또는 온-프레미스에서 실행할 수 있는 휴대용, 스페이스인 컨테이너로 응용 프로그램의 배포를 자동화 하는 데 (참조 그림 1-2). Docker 이기도 한 [회사](https://www.docker.com/) 장려 하 고이 기술은 클라우드, Linux 및 Windows 공급 업체를 비롯 하 여 Microsoft와의 공동 작업에서 작업을 개발 하는 합니다.

![](./media/image2.png)

Docker 그림 1-2: 하이브리드 클라우드의 모든 계층에서 컨테이너를 배포

Linux와 Windows에서 docker 이미지 컨테이너 고유 하 게 실행할 수 있습니다. 그러나 Windows 이미지는 Windows 호스트에 대해서만 실행할 수 있습니다 및 Linux 이미지 Linux 호스트를 호스트 서버 또는 VM에 대해서만 실행할 수 있습니다.

개발자는 Windows, Linux 또는 macOS에서 개발 환경을 사용할 수 있습니다. 개발 컴퓨터에서 개발자는 docker 이미지 배포 응용 프로그램 및 해당 종속성을 포함 하 여 Docker 호스트를 실행 합니다. Linux 기반, Docker 호스트를 사용 하 여 linux 또는 Mac에서 작업 하는 개발자 및 Linux 컨테이너에 대 한 이미지를 만들 수 있습니다. (Mac에서 작업 하는 개발자 코드를 편집 하거나 Docker 명령줄 인터페이스를 실행할 수 \[CLI\] 컨테이너에서 macOS 등 했지만,이 문서의 작성일, macOS에서 직접 실행 되지 않습니다.) Windows에서 작업 하는 개발자는 Linux 또는 Windows 컨테이너에 대 한 이미지를 만들 수 있습니다.

Docker 컨테이너 개발 환경에서 호스팅하고 개발자를 위한 추가 도구를 제공, 제공 [Docker Community Edition (CE)](https://www.docker.com/community-edition) macOS 또는 Windows에 대 한 합니다. 이러한 제품에 필요한 VM (Docker 호스트)를 사용 하는 컨테이너 호스트 설치 합니다. Docker도 사용할 수 있도록 [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), 엔터프라이즈 개발을 위해 설계 하 고 작성 하는 IT 팀에서 사용 하는, 배송, 및 프로덕션 환경에서 큰 업무에 중요 한 응용 프로그램을 실행 합니다.

실행 하려면 [Windows 컨테이너](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview), 두 가지 방법으로 런타임:

-   **Windows Server 컨테이너** 이 런타임 프로세스 및 네임 스페이스 격리 기술을 통해 응용 프로그램 격리를 제공 합니다. Windows Server 컨테이너는 컨테이너 호스트와 호스트에서 실행 중인 모든 컨테이너와 커널을 공유합니다.

-   **Hyper-v 컨테이너** 이 각 컨테이너를 고도로 최적화 된 VM에서 실행 하 여 Windows Server 컨테이너에서 제공 하는 격리를 확장 합니다. 이 구성에서 컨테이너 호스트의 커널은 Hyper-V 컨테이너와 공유되지 않으므로 격리 기능이 향상됩니다.

이러한 컨테이너에 대 한 이미지에 동일한 방식으로 만들어지며 동일 하 게 작동 합니다. 차이점은 컨테이너 이미지에서 만들어지는 방법을-추가 매개 변수가 필요한 Hyper-v 컨테이너를 실행 합니다. 자세한 내용은 [Hyper-V 컨테이너](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview)를 참조하세요.

## <a name="comparing-docker-containers-with-vms"></a>Vm 사용 하 여 Docker 컨테이너 비교

그림 1-3 Vm 및 Docker 간의 비교를 보여 줍니다. 컨테이너입니다.

컨테이너에 훨씬 더 적은 리소스가 필요 하기 때문에 (예를 들어 필요 하지 않은 전체 OS)를 쉽게 배포 하 고 빠른 시작 합니다. 이렇게 하면 동일한 하드웨어 단위 줄여 비용에 더 많은 서비스를 실행할 수 있는지를 의미 하는 높은 밀도 받아 주세요.

동일한 커널을에서 실행의 부작용을으로 Vm 보다 적은 격리를 시킬 수 있습니다.

이미지의 주요 목표는 서로 다른 배포에서 환경(종속성)을 동일하게 만드는 것입니다. 즉, 컴퓨터에서 이를 디버그한 다음, 동일한 환경의 다른 컴퓨터에 배포할 수 있습니다.

컨테이너 이미지는 응용 프로그램 또는 서비스를 패키지 하는 신뢰할 수 있는 고 재현 가능한 방식으로 배포 하는 방법입니다. 이런 점에서 Docker가 아닙니다.만 하는 기술 이기도 한 철학 및 프로세스입니다.

Docker를 사용 하면 예를 들어 개발자를 들, "바로 가기 작동 제 컴퓨터에서 안 되는 이유 프로덕션 환경에서?" 수 단순히 이제, "Docker에서 실행" 때문에 모든 지원 되는 Docker 환경에서 패키지 Docker 응용 프로그램을 실행할 수 있으며 모든 배포 대상 (개발, QA, 스테이징 등 프로덕션.)에서 원래 방식으로 실행 됩니다.

![](./media/image3.png)

Docker 컨테이너에 기존 Vm의 그림 1-3: 비교


>[!div class="step-by-step"]
[이전] (index.md) [다음] (docker-terminology.md)
