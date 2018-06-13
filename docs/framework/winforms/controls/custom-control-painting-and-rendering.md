---
title: 사용자 지정 컨트롤 그리기 및 렌더링
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 18a05a739f42d41a650e66723f44aae69c1707c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526053"
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="7f9f9-102">사용자 지정 컨트롤 그리기 및 렌더링</span><span class="sxs-lookup"><span data-stu-id="7f9f9-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="7f9f9-103">사용자 지정 그리기 컨트롤의.NET Framework로 쉽게 수행할 수 있는 여러 복잡 한 작업 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="7f9f9-104">사용자 지정 컨트롤을 작성할 때 컨트롤의 그래픽 모양에 대 한 많은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="7f9f9-105">상속 되는 컨트롤을 작성 하는 경우는 `Control`, 컨트롤의 그래픽 표현을 렌더링할 수 있는 코드를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="7f9f9-106">상속 하 여 사용자 정의 컨트롤을 만드는 경우는 `UserControl`, 상속 되는지 또는 Windows Forms 컨트롤 중 하나에서 있습니다는 표준 그래픽 표시를 재정의 그래픽 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="7f9f9-107">구성 요소 컨트롤에 대 한 사용자 지정 렌더링을 제공 하려는 경우는 `UserControl` 제작 하는, 옵션은 더욱 제한 되지만 광범위 한 컨트롤 및 응용 프로그램에 대 한 그래픽 기능을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f9f9-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7f9f9-108">In This Section</span></span>  
 [<span data-ttu-id="7f9f9-109">Windows Forms 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="7f9f9-109">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 <span data-ttu-id="7f9f9-110">컨트롤을 표시 하는 논리를 프로그래밍 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="7f9f9-111">사용자가 그린 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7f9f9-111">User-Drawn Controls</span></span>](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 <span data-ttu-id="7f9f9-112">작성 하 고 컨트롤 렌더링 코드를 재정의 하는 단계에 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="7f9f9-113">구성 요소 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7f9f9-113">Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 <span data-ttu-id="7f9f9-114">사용자 컨트롤 및 폼의 구성 요소 컨트롤에 대 한 사용자 지정 렌더링 코드를 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="7f9f9-115">방법: 런타임에 컨트롤 숨기기</span><span class="sxs-lookup"><span data-stu-id="7f9f9-115">How to: Make Your Control Invisible at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="7f9f9-116">사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 숨기 거 나 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="7f9f9-117">방법: 컨트롤에 투명한 배경 적용</span><span class="sxs-lookup"><span data-stu-id="7f9f9-117">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="7f9f9-118">사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Control.SetStyle%2A> 방법을 불투명, 투명 하 게 또는 반투명 하는 배경색을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="7f9f9-119">비주얼 스타일을 사용하여 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="7f9f9-119">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="7f9f9-120">비주얼 스타일을 지 원하는 운영 체제에서 사용 하 여 컨트롤을 렌더링 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7f9f9-121">참조</span><span class="sxs-lookup"><span data-stu-id="7f9f9-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="7f9f9-122">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="7f9f9-123">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="7f9f9-124">이 메서드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7f9f9-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="7f9f9-125">Related Sections</span></span>  
 [<span data-ttu-id="7f9f9-126">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="7f9f9-126">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="7f9f9-127">소개 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Visual Studio의 관점 및 제공 링크에서 자세한 정보를 그래픽 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-127">Introduces [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="7f9f9-128">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="7f9f9-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="7f9f9-129">사용자 지정 컨트롤을 제작할 수의 종류를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9f9-129">Describes the kinds of custom controls you can author.</span></span>
