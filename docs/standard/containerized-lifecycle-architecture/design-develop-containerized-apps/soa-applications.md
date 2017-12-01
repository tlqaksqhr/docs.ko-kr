---
title: "SOA 응용 프로그램"
description: "Microsoft 플랫폼 및 도구와 Docker 컨테이너 화 된 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 92a69ccd18759be3b319395d8609d65bb6d3e1b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="soa-applications"></a>SOA 응용 프로그램

SOA 과도 한 용어 되었으며 다른 사람에 게 많은 다른 것을 의미 합니다. 하지만 (가장 일반적으로 HTTP 서비스)와 다른 형식으로 분류할 수 있는 여러 서비스에서 분해 하 여 응용 프로그램의 아키텍처 구조 하는 하위 시스템에는 최소한와 공통 분모, SOA, 또는 서비스 방향, 평균 등의 또는 계층으로 다른 경우에 합니다.

오늘으로 배포할 수 있습니다 이러한 서비스를, Docker 컨테이너 종속성의 모든 컨테이너 이미지 내에 포함 되어 있으므로 배포 관련 문제를 해결 하 합니다. 그러나 확장 Soa 해야 할 경우에 따라 단일 인스턴스를 배포 하는 경우 문제가 발생할 수 있습니다. 여기서 클러스터링 소프트웨어 또는 orchestrator Docker를 통해 수입니다. 살펴보게이 다음 섹션에서 자세히 microservices 접근 방식을 살펴볼 때는 합니다.

일의 끝 컨테이너 클러스터링 솔루션은 각 마이크로 서비스는 해당 데이터 모델을 소유 하는 고급 microservices 아키텍처 또는 기존의 SOA 아키텍처에 유용 합니다. 및, 여러 데이터베이스를 통해 있습니다도 수 확장 SOA 서비스에서 공유 되는 모놀리식 데이터베이스와 함께 작업 하지 않고 데이터 계층입니다. 그러나 데이터를 분할 하는 방법에 대 한 토론 순수 하 게에 대 한 아키텍처 및 디자인 됩니다.


>[!div class="step-by-step"]
[이전] [다음] (오케스트레이션-높은-확장성-availability.md) (state-and-data-in-docker-applications.md)
