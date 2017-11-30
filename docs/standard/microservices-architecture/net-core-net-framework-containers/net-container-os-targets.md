---
title: ".NET 컨테이너와 대상에 어느 운영 체제"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | .NET 컨테이너와 대상에 어느 운영 체제"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="967cb-104">.NET 컨테이너와 대상에 어느 운영 체제</span><span class="sxs-lookup"><span data-stu-id="967cb-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="967cb-105">Docker 및.NET Core와.NET Framework의 차이점을 지 원하는 운영 체제의 다양성을 고려할 때, 특정 OS 및 사용 하는 프레임 워크에 따라 특정 버전 대상 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="967cb-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="967cb-106">Windows, Windows Server Core 또는 Windows Nano Server를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="967cb-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="967cb-107">이러한 Windows 버전 필요할 수 있는.NET Framework 또는.NET Core에서 각각 다른 특성 (Windows Server Core와 Nano Server에서 Kestrel와 같은 자체 호스트 된 웹 서버에서에서 IIS)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="967cb-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="967cb-108">Linux 용 여러 배포판은 사용할 수 있으며 (예: Debian).NET Docker 이미지를 공식 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="967cb-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="967cb-109">그림 3-1에서 사용 되는.NET framework에 따라 가능한 운영 체제 버전을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="967cb-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="967cb-110">**그림 3-1입니다.**</span><span class="sxs-lookup"><span data-stu-id="967cb-110">**Figure 3-1.**</span></span> <span data-ttu-id="967cb-111">.NET framework의 버전에 따라 대상으로 운영 체제</span><span class="sxs-lookup"><span data-stu-id="967cb-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="967cb-112">또한 다른 Linux 배포판을 사용 하려면 또는 Microsoft에서 제공 하지 않는 버전 이미지를 원하는 경우에서 사용자 고유의 Docker 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="967cb-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="967cb-113">예를 들어 기존.NET Framework 및 Docke에 대 한 not 하므로 일반적인 시나리오는 Windows Server Core에서 실행 되는 ASP.NET Core와 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="967cb-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="967cb-114">Dockerfile 파일을 이미지 이름을 추가 하면 운영 체제 및 버전을 사용 하면 다음 예와 같이 태그에 따라 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="967cb-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="967cb-115">microsoft /**dotnet:2.0.0-런타임-제시**</span><span class="sxs-lookup"><span data-stu-id="967cb-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="967cb-116">microsoft /**dotnet:2.0.0-런타임-nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="967cb-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="967cb-117">microsoft /**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="967cb-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="967cb-118">[이전] (컨테이너-프레임 워크-선택-factors.md) [다음] (공식-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="967cb-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
