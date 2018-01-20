---
title: "컨트롤 형식 권장 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- user controls [Windows Forms], when to use
- custom controls [Windows Forms], types
- controls [Windows Forms], creating
ms.assetid: 5235fe9d-c36a-4c08-ae76-6cb90b50085e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a126d3b21ddd4bd31e168726c3538de21fb7d956
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="control-type-recommendations"></a><span data-ttu-id="6176a-102">컨트롤 형식 권장 사항</span><span class="sxs-lookup"><span data-stu-id="6176a-102">Control Type Recommendations</span></span>
<span data-ttu-id="6176a-103">.NET Framework는 새 컨트롤을 개발 및 구현하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-103">The .NET Framework gives you power to develop and implement new controls.</span></span> <span data-ttu-id="6176a-104">익숙한 사용자 정의 컨트롤뿐 아니라 이제 고유한 그리기를 수행하는 사용자 지정 컨트롤을 작성할 수 있으며 상속을 통해 기존 컨트롤의 기능을 확장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-104">In addition to the familiar user control, you will now find that you are able to write custom controls that perform their own painting, and are even able to extend the functionality of existing controls through inheritance.</span></span> <span data-ttu-id="6176a-105">만들 컨트롤 형식을 결정하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-105">Deciding which type of control to create can be confusing.</span></span> <span data-ttu-id="6176a-106">이 섹션에서는 상속할 수 있는 다양한 컨트롤 형식 간의 차이점을 요약하고 프로젝트에 대해 선택할 형식과 관련된 고려 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-106">This section highlights the differences between the various types of controls from which you can inherit, and gives considerations regarding the type to choose for your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6176a-107">Web Forms에서 사용할 컨트롤을 작성하려는 경우 [사용자 지정 ASP.NET 서버 컨트롤 개발](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6176a-107">If you want to author a control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
  
## <a name="inheriting-from-a-windows-forms-control"></a><span data-ttu-id="6176a-108">Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="6176a-108">Inheriting from a Windows Forms Control</span></span>  
 <span data-ttu-id="6176a-109">기존 Windows Forms 컨트롤에서 상속된 컨트롤을 파생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-109">You can derive an inherited control from any existing Windows Forms control.</span></span> <span data-ttu-id="6176a-110">이 접근 방식을 통해 Windows Forms 컨트롤의 고유 기능을 모두 유지하는 동시에 사용자 지정 속성, 메서드 또는 다른 기능을 추가하여 해당 기능을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-110">This approach allows you to retain all of the inherent functionality of a Windows Forms control, and to then extend that functionality by adding custom properties, methods, or other functionality.</span></span> <span data-ttu-id="6176a-111">예를 들어 숫자만 입력할 수 있고 자동으로 입력을 값으로 변환하는 <xref:System.Windows.Forms.TextBox>에서 파생된 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-111">For example, you might create a control derived from <xref:System.Windows.Forms.TextBox> that can accept only numbers and automatically converts input into a value.</span></span> <span data-ttu-id="6176a-112">이러한 컨트롤에는 텍스트 상자의 텍스트가 변경될 때마다 호출된 유효성 검사 코드가 포함될 수 있으며 추가 속성인 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-112">Such a control might contain validation code that was called whenever the text in the text box changed, and could have an additional property, Value.</span></span> <span data-ttu-id="6176a-113">일부 컨트롤에서는 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하여 컨트롤의 그래픽 인터페이스에 사용자 지정 모양을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-113">In some controls, you can also add a custom appearance to the graphical interface of your control by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>  
  
 <span data-ttu-id="6176a-114">다음과 같은 경우 Windows Forms 컨트롤에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-114">Inherit from a Windows Forms control if:</span></span>  
  
-   <span data-ttu-id="6176a-115">필요한 기능이 대부분 기존 Windows Forms 컨트롤에 이미 있는 것과 동일한 경우</span><span class="sxs-lookup"><span data-stu-id="6176a-115">Most of the functionality you need is already identical to an existing Windows Forms control.</span></span>  
  
-   <span data-ttu-id="6176a-116">사용자 지정 그래픽 인터페이스가 필요하지 않거나 기존 컨트롤에 대한 새 그래픽 프런트 엔드를 디자인하려는 경우</span><span class="sxs-lookup"><span data-stu-id="6176a-116">You do not need a custom graphical interface, or you want to design a new graphical front end for an existing control.</span></span>  
  
## <a name="inheriting-from-the-usercontrol-class"></a><span data-ttu-id="6176a-117">UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="6176a-117">Inheriting from the UserControl Class</span></span>  
 <span data-ttu-id="6176a-118">사용자 정의 컨트롤은 공용 컨테이너로 캡슐화된 Windows Forms 컨트롤 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-118">A user control is a collection of Windows Forms controls encapsulated into a common container.</span></span> <span data-ttu-id="6176a-119">컨테이너는 각 Windows Forms 컨트롤과 연결된 고유 기능을 모두 포함하며 해당 속성을 선택적으로 노출하고 바인딩할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-119">The container holds all of the inherent functionality associated with each of the Windows Forms controls and allows you to selectively expose and bind their properties.</span></span> <span data-ttu-id="6176a-120">사용자 정의 컨트롤의 예로 데이터베이스의 고객 주소 데이터를 표시하기 위해 빌드된 컨트롤을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-120">An example of a user control might be a control built to display customer address data from a database.</span></span> <span data-ttu-id="6176a-121">이 컨트롤은 각 필드를 표시할 여러 개의 텍스트 상자와 레코드를 탐색하는 단추 컨트롤을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-121">This control would include several textboxes to display each field, and button controls to navigate through the records.</span></span> <span data-ttu-id="6176a-122">데이터 바인딩 속성을 선택적으로 노출할 수 있으며, 전체 컨트롤을 패키징하고 응용 프로그램 간에 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-122">Data-binding properties could be selectively exposed, and the entire control could be packaged and reused from application to application.</span></span>  
  
 <span data-ttu-id="6176a-123">다음과 같은 경우 <xref:System.Windows.Forms.UserControl> 클래스에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-123">Inherit from the <xref:System.Windows.Forms.UserControl> class if:</span></span>  
  
-   <span data-ttu-id="6176a-124">여러 Windows Forms 컨트롤의 기능을 다시 사용 가능한 단일 단위로 결합하려는 경우</span><span class="sxs-lookup"><span data-stu-id="6176a-124">You want to combine the functionality of several Windows Forms controls into a single reusable unit.</span></span>  
  
## <a name="inheriting-from-the-control-class"></a><span data-ttu-id="6176a-125">Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="6176a-125">Inheriting from the Control Class</span></span>  
 <span data-ttu-id="6176a-126">컨트롤을 만드는 또 다른 방법은 <xref:System.Windows.Forms.Control>에서 상속하여 처음부터 새로 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-126">Another way to create a control is to create one substantially from scratch by inheriting from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="6176a-127"><xref:System.Windows.Forms.Control> 클래스는 컨트롤에 필요한 기본 기능(예: 이벤트)을 모두 제공하지만 컨트롤별 기능이나 그래픽 인터페이스는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-127">The <xref:System.Windows.Forms.Control> class provides all of the basic functionality required by controls (for example, events), but no control-specific functionality or graphical interface.</span></span> <span data-ttu-id="6176a-128"><xref:System.Windows.Forms.Control> 클래스에서 상속하여 컨트롤을 만들려면 사용자 정의 컨트롤 또는 기존 Windows Forms 컨트롤에서 상속하는 것보다 훨씬 더 많은 노력과 사고가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-128">Creating a control by inheriting from the <xref:System.Windows.Forms.Control> class requires a lot more thought and effort than inheriting from user control or an existing Windows Forms control.</span></span> <span data-ttu-id="6176a-129">작성자는 컨트롤의 <xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트에 대한 코드 및 필요한 기능별 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-129">The author must write code for the <xref:System.Windows.Forms.Control.OnPaint%2A> event of the control, as well as any functionality specific code that is needed.</span></span> <span data-ttu-id="6176a-130">그러나 허용되는 유연성이 더 크며, 정확한 요구에 맞게 컨트롤을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-130">Greater flexibility is allowed, however, and you can custom tailor a control to suit your exact needs.</span></span> <span data-ttu-id="6176a-131">사용자 지정 컨트롤의 예로 아날로그 시계의 모양과 동작을 복제하는 시계 컨트롤이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-131">An example of a custom control is a clock control that duplicates the look and action of an analog clock.</span></span> <span data-ttu-id="6176a-132">사용자 지정 그리기를 호출하면 시계 바늘이 내부 타이머 구성 요소의 <xref:System.Windows.Forms.Timer.Tick> 이벤트에 대한 응답으로 움직입니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-132">Custom painting would be invoked to cause the hands of the clock to move in response to <xref:System.Windows.Forms.Timer.Tick> events from an internal timer component.</span></span>  
  
 <span data-ttu-id="6176a-133">다음과 같은 경우 <xref:System.Windows.Forms.Control> 클래스에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="6176a-133">Inherit from the <xref:System.Windows.Forms.Control> class if:</span></span>  
  
-   <span data-ttu-id="6176a-134">컨트롤의 사용자 지정 그래픽 표현을 제공하려는 경우</span><span class="sxs-lookup"><span data-stu-id="6176a-134">You want to provide a custom graphical representation of your control.</span></span>  
  
-   <span data-ttu-id="6176a-135">표준 컨트롤을 통해 사용할 수 없는 사용자 지정 기능을 구현해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="6176a-135">You need to implement custom functionality that is not available through standard controls.</span></span>  
  
-   <span data-ttu-id="6176a-136">[방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-136">[How to: Display a Control in the Choose Toolbox Items Dialog Box](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-137">[연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 serialize](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-137">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-138">[연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속](http://msdn.microsoft.com/library/5h0k2e6x\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-138">[Walkthrough: Inheriting from a Windows Forms Control with Visual C#](http://msdn.microsoft.com/library/5h0k2e6x\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-139">[방법: 컨트롤에 대한 도구 상자 비트맵 제공](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-139">[How to: Provide a Toolbox Bitmap for a Control](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-140">[방법: 기존 Windows Forms 컨트롤에서 상속](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-140">[How to: Inherit from Existing Windows Forms Controls](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-141">[연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-141">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-142">[방법: Control 클래스에서 상속](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-142">[How to: Inherit from the Control Class](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-143">[방법: UserControl의 런타임 동작 테스트](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-143">[How to: Test the Run-Time Behavior of a UserControl](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-144">[방법: 디자인 타임에 컨트롤을 양식의 가장자리에 맞춤](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-144">[How to: Align a Control to the Edges of Forms at Design Time](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-145">[방법: UserControl 클래스에서 상속](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-145">[How to: Inherit from the UserControl Class](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-146">[방법: Windows Forms 컨트롤 작성](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-146">[How to: Author Controls for Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-147">[방법: 복합 컨트롤 작성](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-147">[How to: Author Composite Controls](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-148">[연습: Visual Basic에서 합성 컨트롤 작성](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-148">[Walkthrough: Authoring a Composite Control with Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-149">[연습: Visual C#에서 합성 컨트롤 작성](http://msdn.microsoft.com/library/a6h7e207\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-149">[Walkthrough: Authoring a Composite Control with Visual C#](http://msdn.microsoft.com/library/a6h7e207\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-150">[연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-150">[Walkthrough: Inheriting from a Windows Forms Control with Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-151">[방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="6176a-151">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="6176a-152">[방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="6176a-152">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6176a-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6176a-153">See Also</span></span>  
 [<span data-ttu-id="6176a-154">방법: 간단한 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="6176a-154">How to: Develop a Simple Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [<span data-ttu-id="6176a-155">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="6176a-155">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
