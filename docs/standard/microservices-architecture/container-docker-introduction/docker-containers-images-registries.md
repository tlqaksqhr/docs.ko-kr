---
title: Docker 컨테이너, 이미지 및 레지스트리
description: 컨테이너화된 .NET 용용 프로그램용 .NET 마이크로 서비스 아키텍쳐 | Docker 컨테이너, 이미지 및 레지스트리
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 4716159d052fd8e229ac42e5d17c72717ac86d9f
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106462"
---
# <a name="docker-containers-images-and-registries"></a>Docker 컨테이너, 이미지 및 레지스트리

Docker를 사용할 때, 개발자는 앱 또는 서비스를 만들고 컨테이너 및 해당 종속성을 컨테이너 이미지에 패키지합니다.  이미지는 앱 또는 서비스와 그 구성 및 종속성을 정적으로 표현합니다.

앱 또는 서비스를 실행하려면 앱의 이미지가 인스턴스화되어 Docker 호스트에서 실행되는 컨테이너를 만듭니다. 컨테이너는 개발 환경 또는 PC에서 초기에 테스트됩니다.

개발자는 이미지 라이브러리로 작동하는 레지스트리에 이미지를 저장해야 하며 프로덕션 오케스트레이터에 배포할 때 필요합니다.  Docker는 [Docker 허브](https://hub.docker.com/)를 통해 공용 레지스트리를 관리합니다. 다른 공급업체는 다른 이미지 컬렉션을 위한 레지스트리를 제공합니다. 또는 기업에서는 자체 Docker 이미지를 위해 개인 레지스트리 온-프레미스를 가질 수 있습니다.

그림 2-4는 Docker의 이미지와 레지스트리가 다른 구성 요소와 어떤 관계가 있는지 보여줍니다.  그것은 또한 공급업체로부터 제공되는 여러 레지스트리를 보여줍니다.

![](./media/image5.PNG)

**그림 2-4**. Docker 용어 및 개념의 분류

레지스티리에 이미지를 저장하면 프레임워크 수준에서 모든 종속성을 포함하여 정적 및 변경할 수 없는 응용 프로그램 비트를 저장할 수 있습니다. 이러한 이미지는 여러 환경에서 버전을 지정하고 배포할 수 있으므로 일관된 배포 단위를 제공합니다. 

온-프레미스 또는 클라우드에서 호스팅되는 개인 이미지 레지스티리는 다음과 같은 경우에 권장됩니다.

-   기밀로 인해 이미지를 공개적으로 공유해서는 안됩니다.

-   이미지와 선택한 배포 환경 사이에는 최소 네트워크 대기 시간이 요구됩니다. 예를 들어, 프로덕션 환경이 Azure 클라우드인 경우 Azure Container Registry에 이미지를 저장하여 네트워크 대기 시간을 최소화할 수 있습니다. 프로덕션 환경이 동일한 로컬 네트워크 내에서 사용 가능한 온-프레미스 Docker Trusted Registry인 경우에도 마찬가지입니다.

>[!div class="step-by-step"]
[이전](docker-terminology.md)
[다음](../net-core-net-framework-containers/index.md)
