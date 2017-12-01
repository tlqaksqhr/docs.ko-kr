---
title: "서비스 지향 아키텍처"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 서비스 지향 아키텍처"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 970ff86c77100077d4c7710c0a697d1745d35819
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="service-oriented-architecture"></a>서비스 지향 아키텍처 

서비스 지향 아키텍처 (SOA) 과도 한 용어 였으며 다른 사람에 게 서로 다른 것 이라고 했습니다. 하지만 공통 분모로 SOA (가장 일반적으로 HTTP 서비스)와 같은 하위 시스템 또는 계층의 서로 다른 형식으로 분류할 수 있는 여러 서비스에 분해 하 여 응용 프로그램을 구성 하는 의미 합니다.

이러한 서비스 이제으로 배포할 수 있습니다, Docker 컨테이너 배포 문제를 해결 하는 모든 종속 컨테이너 이미지에 포함 되어 있으므로 합니다. 그러나 SOA 응용 프로그램을 확장 해야 할 때 확장성을 할 수 있습니다 및 단일 Docker 호스트를 기반으로 배포 하는 경우 가용성 문제입니다. 이 여기서 Docker 소프트웨어나는 orchestrator를 클러스터링 할 out, microservices에 대 한 배포 방법에 설명 하는 이후 섹션에서 설명한 것입니다.

Docker 컨테이너 유용 (않음 필요 없음)는 기존 서비스 지향 아키텍처와 더 많은 고급 microservices 아키텍처에 대 한 합니다.

SOA에서 Microservices 파생 있지만 SOA microservices 아키텍처 다릅니다. 큰 중앙 브로커와 같은 기능으로, 조직 수준에서 중앙 orchestrators 및 [서비스 버스 ESB (Enterprise)](https://en.wikipedia.org/wiki/Enterprise_service_bus) SOA에 일반적입니다. 하지만 대부분의 경우 이러한 항목은 마이크로 서비스 커뮤니티의 패턴입니다. 실제로 어떤 사람들 주장 하 "마이크로 서비스 아키텍처는 제대로 수행 하는 SOA."

이 가이드는 SOA 접근 방식을 요구 사항 및 마이크로 서비스 아키텍처에서 사용 하는 기술 보다 덜 규범적입니다 하므로 microservices를 설명 합니다. 마이크로 서비스 기반 응용 프로그램을 빌드하는 방법을 알고 있는 경우 더 간단한 서비스 지향 응용 프로그램을 빌드하는 방법을 알아야 합니다.




>[!div class="step-by-step"]
[이전] (docker-응용 프로그램-상태-data.md) [다음] (microservices architecture.md)
