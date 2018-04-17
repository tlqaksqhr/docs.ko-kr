---
title: Docker 컨테이너, 이미지 및 레지스트리
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9de37f9ee3a8fe7ce4a337fc548030b2aeadba55
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="docker-containers-images-and-registries"></a>Docker 컨테이너, 이미지 및 레지스트리

Docker를 사용 하는 경우는 응용 프로그램 또는 만들고 서비스 패키지 하 고 여기에 종속 컨테이너 이미지에 합니다. 이미지는 앱 또는 서비스와 그 구성 및 종속성을 정적으로 표현합니다.

응용 프로그램 또는 서비스를 실행 하려면 응용 프로그램의 이미지가 Docker 호스트에서 실행 중인 컨테이너를 만들려면 인스턴스화됩니다. 컨테이너는 개발 환경 또는 PC에서 초기에 테스트됩니다.

이미지의 라이브러리 역할을 레지스트리에 이미지를 저장 합니다. 프로덕션 orchestrators에 배포할 때 레지스트리를 해야 합니다. Docker는 [Docker 허브](https://hub.docker.com/)를 통해 공용 레지스트리를 관리합니다. 다른 공급업체는 다른 이미지 컬렉션을 위한 레지스트리를 제공합니다. 또는 기업에서는 자체 Docker 이미지를 위해 개인 레지스트리 온-프레미스를 가질 수 있습니다.

그림 1-4 이미지와 레지스트리의 Docker에서 관계를 다른 구성 요소를 보여 줍니다. 그것은 또한 공급업체로부터 제공되는 여러 레지스트리를 보여줍니다.

![](./media/image4.png)

Docker 용어 및 개념의 그림 1-4: 분류

레지스트리 ()에 이미지를 배치 하 여 모든 프레임 워크 수준 종속성을 포함 하 여 정적 및 변경할 수 없는 응용 프로그램 비트를 저장할 수 있습니다. 하면 버전을 관리할 수 및 여러 환경에서 이미지를 배포 하 고 따라서 일관 된 배포 단위를 제공 합니다.

개인 이미지 레지스트리, 온-프레미스 호스트 또는 클라우드에 다음과 같은 상황에서 권장 됩니다.

-   기밀로 인해 이미지를 공개적으로 공유해서는 안됩니다.

-   이미지와 선택한 배포 환경 사이에는 최소 네트워크 대기 시간이 요구됩니다. 예를 들어 프로덕션 환경의 Azure 이면를 싶을 네트워크 대기 시간이 최소화 됩니다 되도록 이미지를 Azure 컨테이너 레지스트리에 저장 합니다. 프로덕션 환경이 동일한 로컬 네트워크 내에서 사용 가능한 온-프레미스 Docker Trusted Registry인 경우에도 마찬가지입니다.

>[!div class="step-by-step"]
[이전] (docker-terminology.md) [다음] (Docker-응용 프로그램-수명 주기/index.md)
