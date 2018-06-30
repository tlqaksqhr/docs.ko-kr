---
title: Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택
description: 컨테이너화된 .NET 응용 프로그램에 대한 .NET 마이크로 서비스 아키텍처 | Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 0f6689468eda1dd1b12c24927e650b2b01381274
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104444"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="04c0b-103">Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택</span><span class="sxs-lookup"><span data-stu-id="04c0b-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="04c0b-104">.NET에서 서버 쪽 컨테이너화된 Docker 응용 프로그램을 구축하는 데 지원되는 두 가지 구현은 [.NET Framework](https://www.microsoft.com/net/download/framework) 및 [.NET Core](https://www.microsoft.com/net/download/core)입니다.</span><span class="sxs-lookup"><span data-stu-id="04c0b-104">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="04c0b-105">두 구현은 여러 .NET Standard 구성 요소를 공유하므로 둘 간에 코드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04c0b-105">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="04c0b-106">그러나 두 구현 간에는 기본적인 차이가 있으며, 사용하는 구현은 수행하려는 작업에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="04c0b-106">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="04c0b-107">이 섹션에서는 각 구현을 선택할 경우에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="04c0b-107">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="04c0b-108">[이전](../container-docker-introduction/docker-containers-images-registries.md)
[다음](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="04c0b-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
