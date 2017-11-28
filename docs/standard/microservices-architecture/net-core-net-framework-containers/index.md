---
title: "Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택"
description: "컨테이너화된 .NET 응용 프로그램에 대한 .NET 마이크로 서비스 아키텍처 | Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f7a5fee26f4d138ae22f3551a25a674b22a2f6d1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="7a9ee-104">Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택</span><span class="sxs-lookup"><span data-stu-id="7a9ee-104">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="7a9ee-105">.NET에서 서버 쪽 컨테이너화된 Docker 응용 프로그램을 구축하는 데 지원되는 두 가지 구현은 [.NET Framework](https://www.microsoft.com/net/download/framework) 및 [.NET Core](https://www.microsoft.com/net/download/core)입니다.</span><span class="sxs-lookup"><span data-stu-id="7a9ee-105">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="7a9ee-106">두 구현은 여러 .NET Standard 구성 요소를 공유하므로 둘 간에 코드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a9ee-106">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="7a9ee-107">그러나 두 구현 간에는 기본적인 차이가 있으며, 사용하는 구현은 수행하려는 작업에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="7a9ee-107">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="7a9ee-108">이 섹션에서는 각 구현을 선택할 경우에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7a9ee-108">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7a9ee-109">[이전](../container-docker-introduction/docker-containers-images-registries.md) [다음](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="7a9ee-109">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
