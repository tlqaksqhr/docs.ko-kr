---
title: COM Interop(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, COM interop
- COM interop [Visual Basic], in Visual Basic
ms.assetid: 3ffd1bdf-1b8d-47f5-87eb-75b659f64294
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a2c418855cd2e79c31301705706ff1b98f119a97
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="com-interop-visual-basic"></a><span data-ttu-id="bc7c8-102">COM Interop(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc7c8-102">COM Interop (Visual Basic)</span></span>
<span data-ttu-id="bc7c8-103">COM(구성 요소 개체 모델)을 통해 개체는 기능을 다른 구성 요소에 노출하고 응용 프로그램을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-103">The Component Object Model (COM) allows an object to expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="bc7c8-104">오늘날 대부분의 소프트웨어에는 COM 개체가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-104">Most of today's software includes COM objects.</span></span> <span data-ttu-id="bc7c8-105">새 응용 프로그램에는 .NET 어셈블리가 제일 나은 선택이지만 때로는 COM 개체를 채택해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-105">Although .NET assemblies are the best choice for new applications, you may at times need to employ COM objects.</span></span> <span data-ttu-id="bc7c8-106">이 섹션에서는 작성 및 Visual Basic을 사용한 COM 개체를 사용 하 여 관련 된 문제 중 일부에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-106">This section covers some of the issues associated with creating and using COM objects with Visual Basic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc7c8-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bc7c8-107">In This Section</span></span>  
 [<span data-ttu-id="bc7c8-108">COM Interop 소개</span><span class="sxs-lookup"><span data-stu-id="bc7c8-108">Introduction to COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)  
 <span data-ttu-id="bc7c8-109">COM 상호 운용성의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-109">Provides an overview of COM interoperability.</span></span>  
  
 [<span data-ttu-id="bc7c8-110">방법: Visual Basic에서 COM 개체 참조</span><span class="sxs-lookup"><span data-stu-id="bc7c8-110">How to: Reference COM Objects from Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-reference-com-objects.md)  
 <span data-ttu-id="bc7c8-111">형식 라이브러리가 포함된 COM 개체에 참조를 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-111">Covers how to add references to COM objects that have type libraries.</span></span>  
  
 [<span data-ttu-id="bc7c8-112">방법: ActiveX 컨트롤을 사용하여 작업</span><span class="sxs-lookup"><span data-stu-id="bc7c8-112">How to: Work with ActiveX Controls</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-work-with-activex-controls.md)  
 <span data-ttu-id="bc7c8-113">Visual Studio 도구 상자에 기능을 추가할 기존 ActiveX 컨트롤을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-113">Demonstrates how to use existing ActiveX controls to add features to the Visual Studio Toolbox.</span></span>  
  
 [<span data-ttu-id="bc7c8-114">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="bc7c8-114">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 <span data-ttu-id="bc7c8-115">Windows 운영 체제에 포함된 API를 호출하는 프로세스를 단계별로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-115">Steps you through the process of calling the APIs that are part of the Windows operating system.</span></span>  
  
 [<span data-ttu-id="bc7c8-116">방법: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="bc7c8-116">How to: Call Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-windows-apis.md)  
 <span data-ttu-id="bc7c8-117">User32.dll에서 `MessageBox` 함수를 정의 및 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-117">Demonstrates how to define and call the `MessageBox` function in User32.dll.</span></span>  
  
 [<span data-ttu-id="bc7c8-118">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="bc7c8-118">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 <span data-ttu-id="bc7c8-119">서명되지 않은 형식의 매개 변수가 있는 Windows 함수를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-119">Demonstrates how to call a Windows function that has a parameter of an unsigned type.</span></span>  
  
 [<span data-ttu-id="bc7c8-120">연습: Visual Basic을 사용하여 COM 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="bc7c8-120">Walkthrough: Creating COM Objects with Visual Basic</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-creating-com-objects.md)  
 <span data-ttu-id="bc7c8-121">COM 클래스 템플릿을 사용하거나 사용하지 않고 COM 개체를 만드는 프로세스를 단계별로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-121">Steps you through the process of creating COM objects with and without the COM class template.</span></span>  
  
 [<span data-ttu-id="bc7c8-122">상호 운용성 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bc7c8-122">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 <span data-ttu-id="bc7c8-123">COM을 사용할 경우 발생할 수 있는 일부 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-123">Covers some of the problems you may encounter when using COM.</span></span>  
  
 [<span data-ttu-id="bc7c8-124">.NET Framework 응용 프로그램의 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="bc7c8-124">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 <span data-ttu-id="bc7c8-125">같은 응용 프로그램에서 COM 개체 및 .NET Framework 개체를 사용하는 방법의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-125">Provides an overview of how to use COM objects and .NET Framework objects in the same application.</span></span>  
  
 [<span data-ttu-id="bc7c8-126">연습: COM 개체를 사용한 상속 구현</span><span class="sxs-lookup"><span data-stu-id="bc7c8-126">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 <span data-ttu-id="bc7c8-127">기존 COM 개체를 새 개체의 기반으로 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-127">Describes using existing COM objects as the basis for new objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bc7c8-128">관련 단원</span><span class="sxs-lookup"><span data-stu-id="bc7c8-128">Related Sections</span></span>  
 [<span data-ttu-id="bc7c8-129">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="bc7c8-129">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)  
 <span data-ttu-id="bc7c8-130">공용 언어 런타임에서 제공하는 상호 운용성 서비스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-130">Describes interoperability services provided by the common language runtime.</span></span>  
  
 [<span data-ttu-id="bc7c8-131">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="bc7c8-131">Exposing COM Components to the .NET Framework</span></span>](http://msdn.microsoft.com/library/e78b14f1-e487-43cd-9c6d-1a07483f1730)  
 <span data-ttu-id="bc7c8-132">COM interop를 통해 COM 형식을 호출하는 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-132">Describes the process of calling COM types through COM interop.</span></span>  
  
 [<span data-ttu-id="bc7c8-133">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="bc7c8-133">Exposing .NET Framework Components to COM</span></span>](http://msdn.microsoft.com/library/e42a65f7-1e61-411f-b09a-aca1bbce24c6)  
 <span data-ttu-id="bc7c8-134">COM에서 관리되는 형식의 준비 및 사용을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-134">Describes the preparation and use of managed types from COM.</span></span>  
  
 [<span data-ttu-id="bc7c8-135">Interop 특성 적용</span><span class="sxs-lookup"><span data-stu-id="bc7c8-135">Applying Interop Attributes</span></span>](../../../framework/interop/applying-interop-attributes.md)  
 <span data-ttu-id="bc7c8-136">비관리 코드를 사용할 때 사용할 수 있는 특성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc7c8-136">Covers attributes you can use when working with unmanaged code.</span></span>
