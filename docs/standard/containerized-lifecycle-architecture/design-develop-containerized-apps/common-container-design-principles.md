---
title: 공용 컨테이너 디자인 원칙
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d3ae0c05a7e94d739a3442ecdb11564a70567963
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37071177"
---
# <a name="common-container-design-principles"></a>공용 컨테이너 디자인 원칙

앞의 개발 프로세스에 있는 경우 관련 하 여 컨테이너를 사용 하는 방법을 알면 몇 가지 기본 개념

## <a name="container-equals-a-process"></a>컨테이너는 프로세스를 같음

컨테이너 모델의 컨테이너는 단일 프로세스를 나타냅니다. 컨테이너 프로세스 경계를 정의 하면 눈금 또는 일괄 처리 오프, 프로세스에 사용 되는 기본 형식을 만드는 데 시작 합니다. Docker 컨테이너를 실행 하면 표시 됩니다는 [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) 정의 합니다. 프로세스 및 컨테이너의 수명을 정의합니다. 프로세스가 완료 되 면 컨테이너 수명 주기에 종료 됩니다. 웹 서버 및 Microsoft Azure로 구현 했을 수 있는 일괄 처리 작업, 수명이 짧은 프로세스와 같은 장기 실행 프로세스는 [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/)합니다. 프로세스에 실패할 경우 컨테이너가 종료되며 조정자가 이어서 프로세스를 진행합니다. Orchestrator를 실행 하는 5 개의 인스턴스를 유지 하도록 지정 된 하나에 오류가 발생 하는 경우 orchestrator 오류가 발생 한 프로세스를 바꾸려면 다른 컨테이너로 만들어집니다. 일괄 작업에서 프로세스는 매개 변수와 함께 시작됩니다. 프로세스가 완료되면 작업이 완료됩니다.

여러 프로세스를 단일 컨테이너에서 실행 하려는 시나리오를 확인할 수 있습니다. 아키텍처 문서의 되지 않습니다는 "사용 안 함," 없고 항상는 "항상"입니다. 사용 하는 일반적인 패턴은 여러 프로세스를 요구 하는 시나리오에 대 한 [감독자](http://supervisord.org/)합니다.


>[!div class="step-by-step"]
[이전](design-docker-applications.md)
[다음](monolithic-applications.md)
