---
title: "Docker 컨테이너, 이미지 및 레지스트리"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Docker 컨테이너, 이미지 및 레지스트리"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 224fed34f06d10760b14aa9ecbae6c0e912915cf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="docker-containers-images-and-registries"></a>Docker 컨테이너, 이미지 및 레지스트리

Docker를 사용 하면 개발자가 만듭니다 패키지 및 응용 프로그램 또는 서비스 하 고 여기에 종속 컨테이너 이미지에 있습니다. 이미지는 응용 프로그램 또는 서비스와 해당 구성 및 종속성의 정적 표현 합니다.

응용 프로그램 또는 서비스를 실행 하려면 응용 프로그램의 이미지가 Docker 호스트에서 실행 중인 컨테이너를 만들려면 인스턴스화됩니다. 컨테이너는 개발 환경 또는 PC에서 처음 테스트 됩니다.

개발자는 이미지의 라이브러리 역할을 하 고 프로덕션 orchestrators에 배포할 때 필요 레지스트리에 이미지를 저장 해야 합니다. Docker가 관리를 통해 공개 레지스트리 [Docker 허브](https://hub.docker.com/); 다른 공급 업체 이미지의 다양 한 컬렉션에 대 한 레지스트리를 제공 합니다. 기업에서는 사설 레지스트리를 가질 수 있습니다 또는 온-프레미스 자신의 Docker 이미지에 대 한 합니다.

그림 2-4 이미지와 레지스트리의 Docker에서 관계를 보여 줍니다 다른 구성 요소입니다. 또한 공급 업체의 여러 레지스트리 제공 보여 줍니다.

![](./media/image5.PNG)

**그림 2-4**합니다. Docker 용어 및 개념의 분류

레지스트리 ()에 이미지를 배치 비트 정적 및 변경할 수 없는 응용 프로그램 프레임 워크 수준의 모든 종속 요소를 포함 하 여 저장할 수 있습니다. 이러한 이미지 버전 및 여러 환경에서 배포 된 다음 수 있으며 따라서 일관 된 배포 단위를 제공 됩니다.

개인 이미지 레지스트리, 호스트 하거나 온-프레미스 또는 클라우드에서 경우에 권장:

-   기밀성 인해 공개적으로 이미지를 공유 되어야 합니다.

-   사용자 이미지와 선택한 배포 환경 간의 최소 네트워크 대기 시간이 하려고 합니다. 예를 들어 프로덕션 환경의 Azure 클라우드 이면를 싶을 네트워크 대기 시간이 최소화 됩니다 되도록 이미지를 Azure 컨테이너 레지스트리에 저장 합니다. 유사한 방식 프로덕션 환경에는 온-프레미스에는 경우는 온-프레미스 Docker Trusted Registry 동일한 로컬 네트워크 내에서 사용할 수 있어야 합니다.

>[!div class="step-by-step"]
[이전] (docker-terminology.md) [다음] (... /net-core-net-framework-containers/index.md)
