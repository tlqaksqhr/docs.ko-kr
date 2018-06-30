---
title: Visual Studio Tools를 사용 하 여 Docker (Visual Studio Windows에서)에 대 한
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: facc295399a7471edfd3e59eb1cc0e90f01ef11b
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104894"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Visual Studio Tools를 사용 하 여 Docker (Visual Studio Windows에서)에 대 한

Visual Studio Code 및 Docker CLI를 사용 하는 경우 한 Docker는 워크플로와 비슷하지만 대 한 Visual Studio 도구를 사용 하는 경우 개발자 워크플로 (실제로 동일한 Docker CLI)를 기반 있지만 보다 쉽게 시작할 수, 프로세스를 간소화 하 고 큰 제공 생산성 빌드에 대해 실행 하 고 작업을 구성 합니다. 실행 하 고 f5 키 또는 Ctrl + f 5를 눌러 Visual Studio에서와 같은 간단한 작업을 통해 사용자 컨테이너를 디버깅할 수 이기도 합니다. 더욱, 실행 하 고 단일 컨테이너를 디버깅할 수 있을 뿐만 아니라 Visual Studio 2017 년으로 실행 하 고 디버그할 수 컨테이너 (전체 솔루션)의 그룹 동시에 솔루션 수준에서 동일한 docker compose.yml 파일에서 정의 하는 경우.

## <a name="configuring-your-local-environment"></a>로컬 환경 구성

Windows 용 Docker의 최신 버전으로 이전에 Docker 응용 프로그램을 개발 다음 참조에 설명 된 대로 설치가 간단 하기 때문에 보다 쉽습니다.

**추가 정보:** 로 Windows 용 Docker를 설치 하는 방법에 대 한 자세한 내용은 <https://docs.docker.com/docker-for-windows/>합니다.

Visual Studio 2015를 사용 하는 경우에 업데이트 3 또는 이후 버전와 Docker 용 Visual Studio Tools 해야 합니다.

**추가 정보:** 알아보려면 Visual Studio를 설치 하는 방법에 지침은 [ https://visualstudio.microsoft.com/\ 제품/vs-2015-제품-버전](https://visualstudio.microsoft.com/products/vs-2015-product-editions)합니다.

Visual Studio Tools for Docker 설치에 대 한 확인을 이동 <http://aka.ms/vstoolsfordocker> 및 <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>합니다.

Visual Studio 2017를 사용 하 여 Docker 지원 포함 되어 있습니다.

## <a name="using-docker-tools-in-visual-studio-2015"></a>Visual Studio 2015에서 Docker 도구를 사용 하 여

Docker 용 Visual Studio Tools 개발 하 고 로컬로 유효성을 검사 Docker 컨테이너 linux에서 Linux Docker 호스트 또는 VM 또는 Windows에서 직접 Windows 컨테이너를 사용 하 여 일관 된 방식으로 제공 합니다.

단일 컨테이너를 사용 하는 경우 가장 먼저 시작 해야.NET Core 프로젝트에 Docker 지원에 설정 하는 것입니다. 이렇게 하려면 그림 4-25에 나와 있는 것 처럼 프로젝트 파일을 오른쪽 단추로 클릭 합니다.

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/image/file/205468/1/add-docker-support.png](./media/image31.png)

그림 4-25: Visual Studio 프로젝트에 대 한 Docker 지원을 설정

## <a name="using-docker-tools-in-visual-studio-2017"></a>Visual Studio 2017에 Docker 도구를 사용 하 여

솔루션에서 서비스 프로젝트에 Docker 지원의 추가 하는 경우 (그림 4-26 참조) Visual Studio DockerFile 파일을 프로젝트에만 추가 되지 않습니다, 것도 추가 서비스 섹션 솔루션의 docker compose.yml 파일 (또는 이러한 하지 않은 경우 파일을 만드는 중 존재). Multicontainer 솔루션; 작성을 시작 하는 쉬운 방법 다음 docker compose.yml 파일을 열 있고 추가 기능으로 업데이트 합니다.

![](./media/image32.png)

그림 4-26: Visual Studio 2017 프로젝트에서 Docker 솔루션 지원을 설정

이 작업을 뿐만 아니라 DockerFile 프로젝트에 추가, 또한 솔루션 수준에서 설정 된 전역 docker compose.yml에 필요한 구성 코드 줄을 추가 합니다.

또한 켤 수 있습니다 Docker 지원 Visual Studio 2017 년에서 ASP.NET Core 프로젝트를 만들 때 그림 4-27에 나와 있는 것 처럼 합니다.

![](./media/image33.png)

프로젝트를 만들 때 Docker 지원을 그림 4-27: 설정

Visual Studio에서 솔루션에 Docker 지원을 추가 하면 또한 나타납니다 추가 된 docker compose.yml 파일을 솔루션 탐색기에서 새 노드 트리 그림 4-28 표시 된 것 처럼 합니다.

![](./media/image34.PNG)

그림 4-28: docker compose.yml 파일 이제 솔루션 탐색기에 표시.

multicontainer를 배포할 수 응용 프로그램을 실행할 때 단일 docker compose.yml 파일을 사용 하 여 docker-작성. 환경 (프로덕션 및 개발) 및 실행에 따라 값을 재정의할 수 있도록 Visual Studio, 그룹을 추가 하는 반면 유형 (디버그와 릴리스). 뒷부분에서이 기능을 더 잘 설명 되어 있습니다.

**추가 정보:** 서비스 구현 및 Docke에 대 한 Visual Studio Tools의 사용에 관한 자세한 내용은 다음 문서를 참조 하세요.

빌드, 디버그, 업데이트 및 새로 고침 로컬 Docker 컨테이너에는 앱: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

원격 Docker 호스트에는 ASP.NET 컨테이너를 배포 합니다. [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)


>[!div class="step-by-step"]
[이전](docker-apps-inner-loop-workflow.md)
[다음](set-up-windows-containers-with-powershell.md)
