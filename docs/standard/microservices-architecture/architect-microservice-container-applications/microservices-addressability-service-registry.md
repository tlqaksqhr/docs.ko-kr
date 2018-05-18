---
title: 마이크로 서비스 주소 지정 기능 및 서비스 레지스트리
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 마이크로 서비스 주소 지정 기능 및 서비스 레지스트리
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: cce0b11ca8cb4fe4d97e2f575888254f92543fc3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="microservices-addressability-and-the-service-registry"></a>마이크로 서비스 주소 지정 기능 및 서비스 레지스트리

각 마이크로 서비스에는 해당 위치를 확인하는 데 사용되는 고유한 이름(URL)이 있습니다. 마이크로 서비스는 어디서 실행되든지 주소 지정 가능해야 합니다. 특정 마이크로 서비스를 실행 중인 컴퓨터에 대해 고려해야 하는 경우 오류가 발생할 수 있습니다. 현재 위치를 검색할 수 있도록 DNS가 특정 컴퓨터에 대한 URL을 확인하는 것과 동일한 방법으로 마이크로 서비스에 고유한 이름을 사용해야 합니다. 마이크로 서비스에는 실행되는 인프라와 독립적인 주소 지정 가능 이름이 필요합니다. [서비스 레지스트리](https://microservices.io/patterns/service-registry.html)가 있어야 하기 때문에 서비스 배포 방법과 검색 방법 간에 상호 작용이 필요합니다. 동일한 맥락에서 한 컴퓨터가 실패하는 경우 레지스트리 서비스는 서비스가 지금 실행 중인 위치를 나타내야 합니다.

[서비스 레지스트리 패턴](https://microservices.io/patterns/service-registry.html)은 서비스 검색의 핵심 부분입니다. 레지스트리는 서비스 인스턴스의 네트워크 위치를 포함하는 데이터베이스입니다. 서비스 레지스트리는 항상 사용 가능하고 최신 상태를 유지해야 합니다. 클라이언트는 서비스 레지스트리에서 가져온 네트워크 위치를 캐시할 수 있습니다. 그러나 해당 정보가 결국 만료되고 클라이언트는 서비스 인스턴스를 더 이상 검색할 수 없습니다. 따라서 서비스 레지스트리는 복제 프로토콜을 사용하여 일관성을 유지하는 서버 클러스터로 구성됩니다.

일부 마이크로 서비스 배포 환경(이후 섹션에서 다루는 클러스터라고 함)에서 서비스 검색은 기본 제공됩니다. 예를 들어 Azure Container Service 환경 내에서 Kubernetes 및 Marathon을 사용하는 DC/OS는 서비스 인스턴스 등록 및 등록 취소를 처리할 수 있습니다. 또한 서버 쪽 검색 라우터의 역할을 수행하는 각 클러스터 호스트에서 프록시를 실행합니다. 또 다른 예로 Azure Service Fabric이 있습니다. 여기서는 해당 기본 명명 서비스를 통해 서비스 레지스트리를 제공합니다.

서비스 레지스트리와 API 게이트웨이 패턴 간에 특정 겹치기가 없습니다. 따라서 이 문제도 해결할 수 있습니다. 예를 들어는 [Service Fabric 역방향 프록시](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy)는 Service Fabrice 명명 서비스를 기반으로 하고 내부 서비스에 대한 주소를 확인할 수 있는 API 게이트웨이의 구현 형식입니다.

## <a name="additional-resources"></a>추가 자료

-   **Chris Richardson. 패턴: 서비스 레지스트리**
    *https://microservices.io/patterns/service-registry.html*

-   **Auth0 서비스 레지스트리**
    [*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)

-   **Gabriel Schenker 서비스 검색**
    [*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)


>[!div class="step-by-step"]
[이전] (maintain-microservice-apis.md) [다음] (microservice-based-composite-ui-shape-layout.md)
