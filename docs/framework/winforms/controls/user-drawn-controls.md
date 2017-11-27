---
title: "사용자가 그린 컨트롤"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42f208d10b1c111f98af3c803148590466baddf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="user-drawn-controls"></a><span data-ttu-id="42cd8-102">사용자가 그린 컨트롤</span><span class="sxs-lookup"><span data-stu-id="42cd8-102">User-Drawn Controls</span></span>
<span data-ttu-id="42cd8-103">.NET Framework 사용자 지정 컨트롤을 쉽게 개발 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="42cd8-104">코드에서 함께 바인딩된 표준 컨트롤 집합을 사용자 정의 컨트롤을 만들거나 위로 기초부터 사용자 고유의 컨트롤을 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="42cd8-105">기존 컨트롤에서 상속 되는 컨트롤을 만들고의 고유 기능에 추가 상속을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="42cd8-106">어떤 방법을 사용 하는.NET Framework를 그릴 만드는 모든 컨트롤에 대 한 사용자 지정 그래픽 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="42cd8-107">컨트롤의 그리기 컨트롤의 코드를 실행 하 여 수행 됩니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="42cd8-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="42cd8-108">단일 인수는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 한 <xref:System.Windows.Forms.PaintEventArgs> 모든 정보 및 컨트롤을 렌더링 하는 데 필요한 기능을 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="42cd8-109"><xref:System.Windows.Forms.PaintEventArgs> 속성으로 컨트롤의 렌더링에 사용할 두 개의 기본 개체를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
-   <span data-ttu-id="42cd8-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>개체-에 그릴 컨트롤의 부분을 나타내는 사각형입니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="42cd8-111">이 수는 전체 컨트롤 또는 컨트롤을 그리는 방법에 따라 제어의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
-   <span data-ttu-id="42cd8-112"><xref:System.Drawing.Graphics>개체-여러 그래픽 지향 개체와 컨트롤을 그리는 데 필요한 기능을 제공 하는 메서드를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="42cd8-113">대 한 자세한 내용은 <xref:System.Drawing.Graphics> 개체와 사용을 참조 하는 방법 [하는 방법: 그리기에 대 한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="42cd8-114"><xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트는 컨트롤을 그리거나 화면에서 새로 고칠 때마다 발생 하며 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 개체를 그리기 열리는 사각형을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="42cd8-115">전체 컨트롤 고쳐야 하는 경우는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 는 전체 컨트롤의 크기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="42cd8-116">그러나 컨트롤의 부분 새로 고칠 필요가,만 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 개체는 다시 그려야 하는 영역만 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="42cd8-117">이러한 경우의 예는 컨트롤이 다른 컨트롤이 나 폼의 사용자 인터페이스에 의해 부분적으로 가려져 때 것입니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="42cd8-118">상속 된 경우는 <xref:System.Windows.Forms.Control> 재정의 해야 클래스는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드 내에서 그래픽 렌더링 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="42cd8-119">사용자 정의 컨트롤 또는 상속된 된 컨트롤에 사용자 지정 그래픽 인터페이스를 제공 하려는 경우 수 또한 이렇게 하면 재정의 하 여는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="42cd8-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="42cd8-120">예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-120">An example is shown below:</span></span>  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
         this.Size));  
   }
}  
```  
  
 <span data-ttu-id="42cd8-121">앞의 예제에는 매우 간단한 그래픽 방식으로 컨트롤을 렌더링 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="42cd8-122">호출 된 <xref:System.Windows.Forms.Control.OnPaint%2A> 기본 클래스의 메서드를 만듭니다는 <xref:System.Drawing.Pen> , 그리는 데 사용할 개체 및 사각형에 타원을 그립니다에 의해 결정 되는 마지막으로 <xref:System.Windows.Forms.Control.Location%2A> 및 <xref:System.Windows.Forms.Control.Size%2A> 컨트롤의 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="42cd8-123">이 예제에서는 사용 하는 대부분의 렌더링 코드 보다 좀 더 복잡 하지만 <xref:System.Drawing.Graphics> 내에 포함 된 개체는 <xref:System.Windows.Forms.PaintEventArgs> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="42cd8-124">와 같은 그래픽으로 이미가지고 있는 클래스에서 상속 하는 경우에 <xref:System.Windows.Forms.UserControl> 또는 <xref:System.Windows.Forms.Button>, 표현을 렌더링에 통합 하려면, 기본 클래스를 호출 하지 않아야 하 고 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="42cd8-125">코드는 <xref:System.Windows.Forms.Control.OnPaint%2A> 컨트롤의 메서드를 먼저 컨트롤을 그리면 및 새로 고칠 때마다 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="42cd8-126">크기를 조정할 때마다 컨트롤을 다시 그리면 되도록 컨트롤의 생성자에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  <span data-ttu-id="42cd8-127">사용 하 여 <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> 사각형이 아닌 컨트롤을 구현 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="42cd8-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42cd8-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42cd8-128">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Region%2A>  
 <xref:System.Windows.Forms.ControlStyles>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Windows.Forms.PaintEventArgs>  
 [<span data-ttu-id="42cd8-129">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="42cd8-129">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="42cd8-130">구성 요소 컨트롤</span><span class="sxs-lookup"><span data-stu-id="42cd8-130">Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 [<span data-ttu-id="42cd8-131">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="42cd8-131">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
