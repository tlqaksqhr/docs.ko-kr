---
title: ".NET Framework 4.7, 4.6 및 4.5"
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.custom: updateeachrelease
f1_keywords: f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34402e74bb0cb560d213760c38ce4b936d712eb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="net-framework-guide"></a><span data-ttu-id="d1498-102">.NET Framework 가이드</span><span class="sxs-lookup"><span data-stu-id="d1498-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="d1498-103">이 .NET Framework 콘텐츠 집합에는 .NET Framework 버전 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7 및 4.7.1에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-103">This .NET Framework content set includes information for .NET Framework versions 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, and 4.7.1.</span></span> <span data-ttu-id="d1498-104">.NET Framework를 다운로드하려면 [.NET Framework 설치](../../docs/framework/install/guide-for-developers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1498-104">To download the .NET Framework, see [Installing the .NET Framework](../../docs/framework/install/guide-for-developers.md).</span></span> <span data-ttu-id="d1498-105">.NET Framework 4.5, [!INCLUDE[net_v46](../../includes/net-v46-md.md)], 해당 포인트 릴리스 및 .NET Framework 4.7 및 4.7.1의 새로운 기능과 변경 사항 목록은 [.NET Framework의 새로운 기능](../../docs/framework/whats-new/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1498-105">For a list of new features and changes in the NET Framework 4.5, the [!INCLUDE[net_v46](../../includes/net-v46-md.md)], their point releases, and the .NET Framework 4.7 and 4.7.1, see [What's New in the .NET Framework](../../docs/framework/whats-new/index.md).</span></span> <span data-ttu-id="d1498-106">지원되는 플랫폼 목록은 [.NET Framework 시스템 요구 사항](../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1498-106">For a list of supported platforms, see [.NET Framework System Requirements](../../docs/framework/get-started/system-requirements.md).</span></span> 

<span data-ttu-id="d1498-107">.NET Framework는 웹, Windows, Windows Phone, Windows Server 및 Microsoft Azure용 앱을 빌드하기 위한 개발 플랫폼으로,</span><span class="sxs-lookup"><span data-stu-id="d1498-107">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="d1498-108">많은 업계 표준에 대한 다양한 기능 및 지원을 포함하는 .NET Framework 클래스 라이브러리와 CLR(공용 언어 런타임)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-108">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="d1498-109">.NET Framework는 메모리 관리, 유형 및 메모리 안전성, 보안, 네트워킹 및 응용 프로그램 배포를 비롯하여 다양한 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-109">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="d1498-110">또한 하위 수준의 Windows 운영 체제를 추상화하는 사용하기 쉬운 데이터 구조 및 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-110">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="d1498-111">.NET Framework와 함께 C#, F#, Visual Basic등의 다양한 프로그래밍 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-111">You can use a variety of programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>  

<span data-ttu-id="d1498-112">사용자와 개발자 모두를 위한 .NET Framework에 대한 일반적인 소개는 [시작](../../docs/framework/get-started/index.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1498-112">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](../../docs/framework/get-started/index.md).</span></span> <span data-ttu-id="d1498-113">.NET Framework의 아키텍처 및 주요 기능에 대한 소개는 [개요](../../docs/framework/get-started/overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1498-113">For an introduction to the architecture and key features of the .NET Framework, see the [overview](../../docs/framework/get-started/overview.md).</span></span>  

<span data-ttu-id="d1498-114">[Windows 컨테이너](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview)를 통해 Docker와 함께 .NET Framework를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-114">The .NET Framework can be used with Docker and with [Windows Containers](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview).</span></span> <span data-ttu-id="d1498-115">[Docker를 통해 .NET Framework 응용 프로그램 배포](./docker/index.md)를 참조하여 Docker 컨테이너에서 응용 프로그램을 실행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-115">See [Deploying .NET Framework applications with Docker](./docker/index.md) to learn how to run your applications in Docker containers.</span></span>

## <a name="installation"></a><span data-ttu-id="d1498-116">설치</span><span class="sxs-lookup"><span data-stu-id="d1498-116">Installation</span></span>

<span data-ttu-id="d1498-117">Windows와 함께 .NET Framework를 사용하면 .NET Framework 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="d1498-118">Windows 버전과 함께 제공되는 버전보다 이후 버전의 .NET Framework가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-118">You may need a later version of the .NET Framework than comes with your Windows version.</span></span> <span data-ttu-id="d1498-119">자세한 내용은 [Windows에 .NET Framework 설치](./install/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1498-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="d1498-120">[.NET Framework 복구](./install/repair.md)를 참조하여 .NET Framework를 설치할 때 오류가 발생하는 경우 .NET Framework 설치를 복구하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you are experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="d1498-121">.NET Framework 다운로드에 대한 자세한 내용은 [개발자용 .NET Framework 설치](../../docs/framework/install/guide-for-developers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1498-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1498-122">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d1498-122">In This Section</span></span>

[<span data-ttu-id="d1498-123">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="d1498-123">What's New</span></span>](../../docs/framework/whats-new/index.md)  
<span data-ttu-id="d1498-124">최신 버전의 .NET Framework에 새로 추가된 주요 기능과 변경 내용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="d1498-125">사용되지 않는 형식 및 멤버의 목록을 제공하고 이전 .NET Framework 버전에서 응용 프로그램을 마이그레이션하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>  
  
[<span data-ttu-id="d1498-126">시작</span><span class="sxs-lookup"><span data-stu-id="d1498-126">Getting Started</span></span>](../../docs/framework/get-started/index.md)  
<span data-ttu-id="d1498-127">.NET Framework의 포괄적인 개요 및 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
<span data-ttu-id="d1498-128">[마이그레이션 가이드](../../docs/framework/migration-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d1498-128">[Migration Guide](../../docs/framework/migration-guide/index.md) </span></span>  
<span data-ttu-id="d1498-129">응용 프로그램을 새 버전의 .NET Framework로 마이그레이션하는 경우 고려해야 할 리소스 및 변경 내용 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-129">Provides resources and a list of changes you need to consider  if you're migrating your application to a new version of the .NET Framework.</span></span>  
  
[<span data-ttu-id="d1498-130">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="d1498-130">Development Guide</span></span>](../../docs/framework/development-guide.md)  
<span data-ttu-id="d1498-131">만들기, 구성, 디버깅, 보안, 응용 프로그램 배포, 동적 프로그래밍에 대한 정보, 상호 운용성, 확장성, 메모리 관리 및 스레딩을 포함하여 응용 프로그램 개발에 대한 모든 주요 기술 분야 및 작업에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-131">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
[<span data-ttu-id="d1498-132">도구</span><span class="sxs-lookup"><span data-stu-id="d1498-132">Tools</span></span>](../../docs/framework/tools/index.md)  
<span data-ttu-id="d1498-133">.NET Framework 기술을 사용하여 응용 프로그램을 개발, 구성 및 배포하는 데 도움이 되는 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-133">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>  
  
<span data-ttu-id="d1498-134">[.NET Framework 클래스 라이브러리](/dotnet/api/?view=netframework-4.7.1) </span><span class="sxs-lookup"><span data-stu-id="d1498-134">[.NET Framework Class Library](/dotnet/api/?view=netframework-4.7.1) </span></span>  
<span data-ttu-id="d1498-135">.NET Framework 네임스페이스에 포함된 각 클래스에 대해 구문, 코드 예제 및 관련 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-135">Supplies syntax, code examples, and related information for each class contained in the .NET Framework namespaces.</span></span>  
  
[<span data-ttu-id="d1498-136">추가 클래스 라이브러리 및 API</span><span class="sxs-lookup"><span data-stu-id="d1498-136">Additional Class Libraries and APIs</span></span>](../../docs/framework/additional-apis/index.md)  
<span data-ttu-id="d1498-137">.NET Framework의 특정 플랫폼 또는 구현을 대상으로 하는 클래스 뿐만 아니라 OOB(대역 외) 릴리스에 포함된 클래스에 대한 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d1498-137">Provides documentation for classes contained in out-of-band (OOB) releases, as well as for classes that target specific platforms or implementations of the .NET Framework.</span></span>
