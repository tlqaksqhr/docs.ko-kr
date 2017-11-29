---
title: "구성 요소 컨트롤"
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
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 932b90d972aaa2305743b6fdaae546b0e2542cd5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="constituent-controls"></a><span data-ttu-id="2fef0-102">구성 요소 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2fef0-102">Constituent Controls</span></span>
<span data-ttu-id="2fef0-103">사용자 정의 컨트롤을 구성하는 컨트롤, 즉 *구성 요소컨트롤*은 사용자 지정 그래픽 렌더링을 수행할 때 사용 범위가 상대적으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-103">The controls that make up a user control, or *constituent controls* as they are termed, are relatively inflexible when it comes to custom graphics rendering.</span></span> <span data-ttu-id="2fef0-104">모든 Windows Forms 컨트롤을 통해 자신의 고유한 렌더링을 처리할 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2fef0-104">All Windows Forms controls handle their own rendering through their own <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="2fef0-105">이 메서드는 protected로 선언되므로 개발자가 액세스할 수 없으며, 이에 따라 컨트롤을 그릴 때 실행되는 것을 막을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-105">Because this method is protected, it is not accessible to the developer, and thus cannot be prevented from executing when the control is painted.</span></span> <span data-ttu-id="2fef0-106">그러나 이러한 이유로 구성 요소 컨트롤의 모양에 적용되는 코드를 추가할 수 없는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-106">This does not mean, however, that you cannot add code to affect the appearance of constituent controls.</span></span> <span data-ttu-id="2fef0-107">이벤트 처리기를 추가하면 추가적 렌더링을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-107">Additional rendering can be accomplished by adding an event handler.</span></span> <span data-ttu-id="2fef0-108">예를 들어, 제작 하는 <xref:System.Windows.Forms.UserControl> 이라는 단추와 `MyButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-108">For example, suppose you were authoring a <xref:System.Windows.Forms.UserControl> with a button named `MyButton`.</span></span> <span data-ttu-id="2fef0-109">추가적인 렌더링 하 여 제공 된 것 외에 <xref:System.Web.UI.WebControls.Button>, 코드는 다음과 같은 사용자 정의 컨트롤에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-109">If you wished to have additional rendering beyond what was provided by the <xref:System.Web.UI.WebControls.Button>, you would add code to your user control similar to the following:</span></span>  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="2fef0-110">와 같은 일부 Windows Forms 컨트롤 <xref:System.Windows.Forms.TextBox>, Windows에서 직접 칠해집니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-110">Some Windows Forms controls, such as <xref:System.Windows.Forms.TextBox>, are painted directly by Windows.</span></span> <span data-ttu-id="2fef0-111">이러한 경우에는 <xref:System.Windows.Forms.Control.OnPaint%2A> 따라서 위의 예제에서는 호출 되지 않는 및 메서드 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-111">In these instances, the <xref:System.Windows.Forms.Control.OnPaint%2A> method is never called, and thus the above example will never be called.</span></span>  
  
 <span data-ttu-id="2fef0-112">이 경우 `MyButton.Paint` 이벤트가 실행될 때마다 실행되는 메서드를 만들어 사용자 정의 컨트롤에 추가적인 그래픽 표현을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-112">This creates a method that executes every time the `MyButton.Paint` event executes, thereby adding additional graphical representation to your control.</span></span> <span data-ttu-id="2fef0-113">여기서는 `MyButton.OnPaint`가 실행되는 것을 막을 수 없으므로 사용자 지정 그리기뿐만 아니라 일반적으로 단추를 통해 수행되는 모든 그리기도 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-113">Note that this does not prevent the execution of `MyButton.OnPaint`, and thus all of the painting usually performed by a button will still be performed in addition to your custom painting.</span></span> <span data-ttu-id="2fef0-114">GDI + 기술 및 사용자 지정 렌더링에 대한 자세한 내용은 [GDI+를 사용하여 그래픽 이미지 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2fef0-114">For details about GDI+ technology and custom rendering, see the [Creating Graphical Images with GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="2fef0-115">고유한 컨트롤 표현을 제공하려면 상속된 컨트롤을 만들고 이 컨트롤에 필요한 사용자 지정 렌더링 코드를 작성하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2fef0-115">If you wish to have a unique representation of your control, your best course of action is to create an inherited control, and to write custom rendering code for it.</span></span> <span data-ttu-id="2fef0-116">자세한 내용은 [사용자가 그린 컨트롤](../../../../docs/framework/winforms/controls/user-drawn-controls.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2fef0-116">For details, see [User-Drawn Controls](../../../../docs/framework/winforms/controls/user-drawn-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fef0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fef0-117">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="2fef0-118">사용자가 그린 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2fef0-118">User-Drawn Controls</span></span>](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 [<span data-ttu-id="2fef0-119">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="2fef0-119">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="2fef0-120">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="2fef0-120">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
