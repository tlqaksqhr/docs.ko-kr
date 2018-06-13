---
title: 서비스 지향 아키텍처
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 서비스 지향 아키텍처
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ce4addefc7b6b1cf82551bf8304b7f06f1614796
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573817"
---
# <a name="service-oriented-architecture"></a>서비스 지향 아키텍처 

SOA(서비스 지향 아키텍처)라는 용어는 남용되었으며 사람들 사이에서 여러 의미로 사용됩니다. 하지만 한 가지 공통 분모가 있으니, SOA는 응용 프로그램을 하위 시스템 또는 계층 같은 다양한 유형으로 분류할 수 있는 여러 서비스로 구성 해제하여(가장 일반적으로 HTTP 서비스) 응용 프로그램을 만든다는 의미입니다.

이제 이러한 서비스는 모든 종속성이 컨테이너 이미지에 포함되므로 배포 문제를 해결하는 Docker 컨테이너로 배포할 수 있습니다. 그러나 SOA 응용 프로그램을 강화해야 하는데, 단일 Docker 호스트를 기반으로 배포하는 경우 확장성 및 가용성 문제에 직면할 수 있습니다. 이때 Docker 클러스터링 소프트웨어 또는 오케스트레이터가 도움이 되며, 이에 대한 내용은 뒷부분에 나오는 마이크로 서비스에 대한 배포 접근 방식을 설명하는 섹션에서 다루겠습니다.

Docker 컨테이너는 기존의 서비스 지향 아키텍처와 보다 발전된 마이크로 서비스 아키텍처 모두에 유용합니다(하지만 필수는 아님).

마이크로 서비스가 SOA에서 파생되지만, SOA는 마이크로 서비스 아키텍처와 다릅니다. 대형 중앙 브로커, 조직 수준의 중앙 오케스트레이터, [ESB(Enterprise Service Bus)](https://en.wikipedia.org/wiki/Enterprise_service_bus) 같은 기능은 SOA에서 일반적입니다. 하지만 대부분의 경우 이러한 기능은 마이크로 서비스 커뮤니티의 안티패턴입니다. 사실, 일부 사람들은 "마이크로 서비스 아키텍처는 SOA를 제대로 만든 것"이라고 주장합니다.

SOA 접근 방식은 마이크로 서비스 아키텍처에 사용되는 요구 사항 및 기술보다 덜 규범적이므로 이 가이드에서는 마이크로 서비스를 집중적으로 다룹니다. 마이크로 서비스 기반 응용 프로그램을 빌드하는 방법을 알고 있는 분들은 그보다 더 간단한 서비스 지향 응용 프로그램을 빌드하는 방법도 알고 있는 것입니다.




>[!div class="step-by-step"]
[이전] (docker-application-state-data.md) [다음] (microservices-architecture.md)
