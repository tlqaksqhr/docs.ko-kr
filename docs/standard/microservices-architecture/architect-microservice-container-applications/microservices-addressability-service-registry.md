---
title: "Microservices 주소 지정 기능 및 서비스 레지스트리"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Microservices 주소 지정 기능 및 서비스 레지스트리"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 19a0200dadfb90a455de690d880f4eeae4772ed7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="microservices-addressability-and-the-service-registry"></a>Microservices 주소 지정 기능 및 서비스 레지스트리

각 마이크로 서비스에는 해당 위치를 확인 하는 데 사용 되는 고유한 이름이 (URL). 마이크로 서비스 프로그램 실행 중인 경우 항상 주소 지정 가능한 수 있어야 합니다. 어떤 컴퓨터에 대 한 특정 마이크로 서비스를 실행 중인 생각해 야 하는 경우 발생할 수 있는 잘못 된 신속 하 게 합니다. DNS 특정 컴퓨터에 한 URL을 확인 하는 동일한 방법으로 사용자 마이크로 서비스를 현재 위치를 검색할 수 있도록 고유한 이름을 가져야 해야 합니다. Microservices는 인프라에서 실행 되는 별개는 주소 지정 가능 이름이 필요 합니다. 이 있어야 하기 때문에 서비스의 배포 방법을 검색 방법을 사이의 상호 작용 임을 의미는 [서비스 레지스트리](http://microservices.io/patterns/service-registry.html)합니다. 동일한 맥락에서 한 컴퓨터에서 오류가 발생 하는 경우 레지스트리 서비스가 있어야 서비스 실행 이제 중임을 나타내는 합니다.

[서비스 레지스트리 패턴](http://microservices.io/patterns/service-registry.html) 서비스 검색의 핵심 부분입니다. 레지스트리는 서비스 인스턴스의 네트워크 위치를 포함 하는 데이터베이스입니다. 서비스 레지스트리 항상 사용 가능 하 고 최신 상태로 있어야 합니다. 클라이언트는 서비스 레지스트리에에서 가져온 네트워크 위치를 캐시할 수 있습니다. 그러나 해당 정보 결국 만료 들어가고 클라이언트 서비스 인스턴스를 더 이상 검색할 수 없습니다. 따라서 서비스 레지스트리 복제 프로토콜을 사용 하 여 일관성을 유지 하는 서버 클러스터로 구성 됩니다.

일부 마이크로 서비스 배포 환경 (이후 섹션에서 다루기 엔 클러스터 라고 함)에서 서비스 검색은 기본 제공 합니다. 예를 들어 Azure 컨테이너 서비스 환경 내에서 Kubernetes 및 DC/OS 마라톤와 처리 서비스 인스턴스를 등록 하 고 수 등록을 취소 합니다. 프록시 서버 쪽 검색 라우터의 역할을 수행 하는 각 클러스터 호스트에서 실행 됩니다. 또 다른 예로 또한 해당 기본-명명 서비스를 통해 서비스 레지스트리를 제공 하는 Azure 서비스 패브릭 합니다.

Note 서비스 레지스트리 및 사용도이 문제를 해결 하는 API 게이트웨이 패턴 특정 겹치지 있다는 것입니다. 예를 들어는 [서비스 패브릭 역방향 프록시](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) 유형 서비스 Fabrice 명명 서비스를 기반으로 하 고 주소 확인 내부 서비스에 해결에 도움이 되는 API 게이트웨이의 구현입니다.

## <a name="additional-resources"></a>추가 리소스

-   **Chris Richardson 합니다. 패턴: 서비스 레지스트리**
    *http://microservices.io/patterns/service-registry.html*

-   **Auth0 합니다. 서비스 레지스트리**
    [*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)

-   **Gabriel Schenker 합니다. 서비스 검색**
    [*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)


>[!div class="step-by-step"]
[이전] (유지 관리-마이크로 서비스-apis.md) [다음] (microservice-based-composite-ui-shape-layout.md)
