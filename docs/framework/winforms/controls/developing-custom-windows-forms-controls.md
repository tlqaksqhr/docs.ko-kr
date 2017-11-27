---
title: ".NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89be7e347556c8ec34296044f17fbfd4450bc127
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="3cd1c-102">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="3cd1c-102">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="3cd1c-103">Windows Forms 컨트롤은 사용자 인터페이스 기능을 캡슐화하고 클라이언트 측 Windows 기반 응용 프로그램에서 사용되는 재사용 가능한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-103">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="3cd1c-104">Windows Forms은 바로 사용할 수 있는 많은 컨트롤을 제공할 뿐만 아니라 고유한 컨트롤을 개발하기 위한 인프라도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-104">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="3cd1c-105">기존 컨트롤을 결합 또는 확장하거나 고유한 사용자 지정 컨트롤을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-105">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="3cd1c-106">이 섹션에서는 Windows Forms 컨트롤을 개발하는 데 도움이 되는 배경 정보 및 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-106">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3cd1c-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="3cd1c-107">In This Section</span></span>  
 [<span data-ttu-id="3cd1c-108">Windows Forms에서 컨트롤 사용 개요</span><span class="sxs-lookup"><span data-stu-id="3cd1c-108">Overview of Using Controls in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="3cd1c-109">Windows Forms 응용 프로그램에 있는 컨트롤 사용의 필수 요소를 요약해서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-109">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="3cd1c-110">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="3cd1c-110">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="3cd1c-111"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스로 작성할 수 있는 다양한 종류의 사용자 지정 컨트롤을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-111">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="3cd1c-112">Windows Forms 컨트롤 개발 기본 사항</span><span class="sxs-lookup"><span data-stu-id="3cd1c-112">Windows Forms Control Development Basics</span></span>](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)  
 <span data-ttu-id="3cd1c-113">Windows Forms 컨트롤 개발의 첫 번째 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-113">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="3cd1c-114">Windows Forms 컨트롤의 속성</span><span class="sxs-lookup"><span data-stu-id="3cd1c-114">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 <span data-ttu-id="3cd1c-115">Windows Forms 컨트롤에 속성을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-115">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="3cd1c-116">Windows Forms 컨트롤의 이벤트</span><span class="sxs-lookup"><span data-stu-id="3cd1c-116">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 <span data-ttu-id="3cd1c-117">Windows Forms 컨트롤에서 이벤트를 처리 및 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-117">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="3cd1c-118">Windows Forms 컨트롤의 특성</span><span class="sxs-lookup"><span data-stu-id="3cd1c-118">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="3cd1c-119">사용자 지정 컨트롤 및 구성 요소의 속성이나 다른 멤버에 적용할 수 있는 특성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-119">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="3cd1c-120">사용자 지정 컨트롤 그리기 및 렌더링</span><span class="sxs-lookup"><span data-stu-id="3cd1c-120">Custom Control Painting and Rendering</span></span>](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="3cd1c-121">컨트롤의 모양을 사용자 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-121">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="3cd1c-122">Windows Forms 컨트롤의 레이아웃</span><span class="sxs-lookup"><span data-stu-id="3cd1c-122">Layout in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/layout-in-windows-forms-controls.md)  
 <span data-ttu-id="3cd1c-123">컨트롤 및 폼에 사용할 정교한 레이아웃을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-123">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="3cd1c-124">Windows Forms 컨트롤의 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="3cd1c-124">Multithreading in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="3cd1c-125">다중 스레드 컨트롤을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-125">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3cd1c-126">참조</span><span class="sxs-lookup"><span data-stu-id="3cd1c-126">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="3cd1c-127">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="3cd1c-128">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-128">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3cd1c-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="3cd1c-129">Related Sections</span></span>  
 [<span data-ttu-id="3cd1c-130">구성 요소의 디자인 타임 특성</span><span class="sxs-lookup"><span data-stu-id="3cd1c-130">Design-Time Attributes for Components</span></span>](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 <span data-ttu-id="3cd1c-131">비주얼 디자이너에서 디자인 타임에 올바르게 표시되도록 구성 요소 및 컨트롤에 적용할 메타데이터 특성을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-131">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 [<span data-ttu-id="3cd1c-132">디자인 타임 지원 확장</span><span class="sxs-lookup"><span data-stu-id="3cd1c-132">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 <span data-ttu-id="3cd1c-133">디자인 타임 지원을 제공하는 편집기 및 디자이너와 같은 클래스를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-133">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 [<span data-ttu-id="3cd1c-134">방법: 구성 요소 및 컨트롤 라이선스</span><span class="sxs-lookup"><span data-stu-id="3cd1c-134">How to: License Components and Controls</span></span>](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)  
 <span data-ttu-id="3cd1c-135">컨트롤이나 구성 요소에서 라이선스를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-135">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="3cd1c-136">또한 [디자인 타임에서 Windows Forms 컨트롤 개발](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-136">Also see [Developing Windows Forms Controls at Design Time](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\)).</span></span>
