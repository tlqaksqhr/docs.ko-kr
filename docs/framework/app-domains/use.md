---
title: 응용 프로그램 도메인 사용
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ebd1de46eb2757098a369b58dd9a6c0009e5b95
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="using-application-domains"></a><span data-ttu-id="1f513-102">응용 프로그램 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="1f513-102">Using Application Domains</span></span>
<span data-ttu-id="1f513-103">응용 프로그램 도메인은 공용 언어 런타임에 대한 격리 단위를 제공하고</span><span class="sxs-lookup"><span data-stu-id="1f513-103">Application domains provide a unit of isolation for the common language runtime.</span></span> <span data-ttu-id="1f513-104">프로세스 내에서 생성되고 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-104">They are created and run inside a process.</span></span> <span data-ttu-id="1f513-105">응용 프로그램 도메인은 대개 런타임을 프로세스로 로드하고 응용 프로그램 도메인 내에서 사용자 코드를 실행하는 응용 프로그램인 런타임 호스트에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-105">Application domains are usually created by a runtime host, which is an application responsible for loading the runtime into a process and executing user code within an application domain.</span></span> <span data-ttu-id="1f513-106">런타임 호스트는 프로세스와 기본 응용 프로그램 도메인을 만들고 그 내부에서 관리 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-106">The runtime host creates a process and a default application domain, and runs managed code inside it.</span></span> <span data-ttu-id="1f513-107">런타임 호스트에는 ASP.NET, Microsoft Internet Explorer 및 Windows 셸이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-107">Runtime hosts include ASP.NET, Microsoft Internet Explorer, and the Windows shell.</span></span>  
  
 <span data-ttu-id="1f513-108">대부분 응용 프로그램의 경우 자체적인 응용 프로그램 도메인을 만들 필요가 없습니다. 런타임 호스트에서 필요한 응용 프로그램 도메인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-108">For most applications, you do not need to create your own application domain; the runtime host creates any necessary application domains for you.</span></span> <span data-ttu-id="1f513-109">그러나 응용 프로그램이 코드를 분리하거나 DLL을 사용하고 언로드해야 할 경우 직접 추가적인 응용 프로그램 도메인을 만들고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-109">However, you can create and configure additional application domains if your application needs to isolate code or to use and unload DLLs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f513-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1f513-110">In This Section</span></span>  
 [<span data-ttu-id="1f513-111">방법: 응용 프로그램 도메인 만들기</span><span class="sxs-lookup"><span data-stu-id="1f513-111">How to: Create an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 <span data-ttu-id="1f513-112">응용 프로그램 도메인을 프로그래밍 방식으로 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-112">Describes how to programmatically create an application domain.</span></span>  
  
 [<span data-ttu-id="1f513-113">방법: 응용 프로그램 도메인 언로드</span><span class="sxs-lookup"><span data-stu-id="1f513-113">How to: Unload an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 <span data-ttu-id="1f513-114">응용 프로그램 도메인을 프로그래밍 방식으로 언로드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-114">Describes how to programmatically unload an application domain.</span></span>  
  
 [<span data-ttu-id="1f513-115">방법: 응용 프로그램 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="1f513-115">How to: Configure an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 <span data-ttu-id="1f513-116">응용 프로그램 도메인을 구성하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-116">Provides an introduction to configuring an application domain.</span></span>  
  
 [<span data-ttu-id="1f513-117">응용 프로그램 도메인에서 설치 정보 검색</span><span class="sxs-lookup"><span data-stu-id="1f513-117">Retrieving Setup Information from an Application Domain</span></span>](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 <span data-ttu-id="1f513-118">응용 프로그램 도메인에서 설정 정보를 검색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-118">Describes how to retrieve setup information from an application domain.</span></span>  
  
 [<span data-ttu-id="1f513-119">방법: 응용 프로그램 도메인에 어셈블리 로드</span><span class="sxs-lookup"><span data-stu-id="1f513-119">How to: Load Assemblies into an Application Domain</span></span>](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 <span data-ttu-id="1f513-120">어셈블리를 응용 프로그램 도메인으로 로드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-120">Describes how to load an assembly into an application domain.</span></span>  
  
 [<span data-ttu-id="1f513-121">방법: 어셈블리에서 형식 및 멤버 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="1f513-121">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="1f513-122">어셈블리에 대한 정보를 검색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-122">Describes how to retrieve information about an assembly.</span></span>  
  
 [<span data-ttu-id="1f513-123">어셈블리 섀도 복사</span><span class="sxs-lookup"><span data-stu-id="1f513-123">Shadow Copying Assemblies</span></span>](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 <span data-ttu-id="1f513-124">어셈블리가 사용되는 동안 섀도 복사를 통해 어셈블리 업데이트를 허용하는 방법과 섀도 복사를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-124">Describes how shadow copying allows updates to assemblies while they are in use, and how to configure shadow copying.</span></span>  
  
 [<span data-ttu-id="1f513-125">방법: 첫째 예외 알림 받기</span><span class="sxs-lookup"><span data-stu-id="1f513-125">How to: Receive First-Chance Exception Notifications</span></span>](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 <span data-ttu-id="1f513-126">공용 언어 런타임이 예외 처리기 검색을 시작하기 전에 예외가 throw되었다는 알림을 받을 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-126">Explains how you can receive a notification that an exception has been thrown, before the common language runtime has begun searching for exception handlers.</span></span>  
  
 [<span data-ttu-id="1f513-127">어셈블리 로드 해결</span><span class="sxs-lookup"><span data-stu-id="1f513-127">Resolving Assembly Loads</span></span>](../../../docs/framework/app-domains/resolve-assembly-loads.md)  
 <span data-ttu-id="1f513-128"><xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> 이벤트를 사용하여 어셈블리 로드 실패를 해결하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-128">Provides guidance on using the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event to resolve assembly load failures.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1f513-129">참조</span><span class="sxs-lookup"><span data-stu-id="1f513-129">Reference</span></span>  
 <xref:System.AppDomain>  
 <span data-ttu-id="1f513-130">응용 프로그램 도메인을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-130">Represents an application domain.</span></span> <span data-ttu-id="1f513-131">응용 프로그램 도메인을 만들고 제어하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-131">Provides methods for creating and controlling application domains.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1f513-132">관련 단원</span><span class="sxs-lookup"><span data-stu-id="1f513-132">Related Sections</span></span>  
 [<span data-ttu-id="1f513-133">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="1f513-133">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="1f513-134">어셈블리가 실행하는 함수의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-134">Provides an overview of the functions performed by assemblies.</span></span>  
  
 [<span data-ttu-id="1f513-135">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1f513-135">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 <span data-ttu-id="1f513-136">어셈블리를 만들고, 서명하고, 특성을 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-136">Describes how to create, sign, and set attributes on assemblies.</span></span>  
  
 [<span data-ttu-id="1f513-137">동적 메서드 및 어셈블리 내보내기</span><span class="sxs-lookup"><span data-stu-id="1f513-137">Emitting Dynamic Methods and Assemblies</span></span>](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 <span data-ttu-id="1f513-138">동적 어셈블리를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-138">Describes how to create dynamic assemblies.</span></span>  
  
 [<span data-ttu-id="1f513-139">응용 프로그램 도메인</span><span class="sxs-lookup"><span data-stu-id="1f513-139">Application Domains</span></span>](../../../docs/framework/app-domains/application-domains.md)  
 <span data-ttu-id="1f513-140">응용 프로그램 도메인에 대해 개념적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-140">Provides a conceptual overview of application domains.</span></span>  
  
 [<span data-ttu-id="1f513-141">리플렉션 개요</span><span class="sxs-lookup"><span data-stu-id="1f513-141">Reflection Overview</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="1f513-142">**Reflection** 클래스를 사용하여 어셈블리에 대한 정보를 얻는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1f513-142">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
