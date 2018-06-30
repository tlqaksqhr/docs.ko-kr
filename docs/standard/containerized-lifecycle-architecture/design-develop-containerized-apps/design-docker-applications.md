---
title: Docker 응용 프로그램 디자인
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 2f4a3b7675365aa4d1e33328f756439398f3a4de
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105239"
---
# <a name="design-docker-applications"></a><span data-ttu-id="bfa8d-103">Docker 응용 프로그램 디자인</span><span class="sxs-lookup"><span data-stu-id="bfa8d-103">Design Docker applications</span></span>

<span data-ttu-id="bfa8d-104">1 장 컨테이너 및 Docker에 대 한 기본 개념을 도입 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa8d-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="bfa8d-105">해당 정보는 기본 수준 시작 하는 데 필요한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="bfa8d-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="bfa8d-106">하지만 엔터프라이즈 응용 프로그램은 복잡 하 고 단일 서비스 또는 컨테이너 대신 여러 서비스 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa8d-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="bfa8d-107">이러한 선택적으로 사용 사례에 대 한 알아야 추가 방법은 디자인 같은 서비스 지향 아키텍처 SOA () 및 더 많은 고급 microservices 개념 및 컨테이너에 오케스트레이션 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="bfa8d-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="bfa8d-108">이 문서의 범위 microservices 제한 되지 않습니다. 하지만 모든 Docker 응용 프로그램 수명 주기를 따라서 것 않습니다 탐색 하지는 심층에서 microservices 아키텍처 있습니다도 하거나 하기 때문에 컨테이너 및 Docker를 사용 하 여 작업, 백그라운드 작업 또는 일반 쌍으로 포함 하 여 단일 응용 프로그램 배포 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bfa8d-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SAO, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="bfa8d-109">그러나 응용 프로그램 수명 주기 및 DevOps에 들어가기 전에 되기 미리 알고 어떻게 디자인 및 응용 프로그램 란 무엇 이며 디자인 선택 사항 구성 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa8d-109">However, before we get into the application life cycle and DevOps, it is important to know how you are going to design and construct your application and what are your design choices.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="bfa8d-110">[이전](index.md)
[다음](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="bfa8d-110">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
