---
title: "OnPaint 메서드 재정의"
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
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41205f7f0ec21e27b97d0b12415fca89ae526552
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="38d88-102">OnPaint 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="38d88-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="38d88-103">에 정의 된 이벤트를 재정의 하는 기본 단계는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 동일 하며 다음 목록에 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-103">The basic steps for overriding any event defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="38d88-104">상속된 된 이벤트를 재정의 하려면</span><span class="sxs-lookup"><span data-stu-id="38d88-104">To override an inherited event</span></span>  
  
1.  <span data-ttu-id="38d88-105">보호 된 재정의 `On` *EventName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="38d88-105">Override the protected `On`*EventName* method.</span></span>  
  
2.  <span data-ttu-id="38d88-106">호출 된 `On` *EventName* 에서 재정의 된 기본 클래스의 메서드 `On` *EventName* 메서드를 등록 된 대리자가 이벤트를 받도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="38d88-107"><xref:System.Windows.Forms.Control.Paint> 이벤트는 모든 Windows Forms 컨트롤 재정의 해야 하기 때문에 여기에서 자세히 설명 되어는 <xref:System.Windows.Forms.Control.Paint> 에서 상속 된 이벤트 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="38d88-108">기본 <xref:System.Windows.Forms.Control> 클래스 파생된 된 컨트롤을 그릴 수 있도록 요구 하는 방법을 알지 못합니다 및 모든 그리기 논리를 제공 하지 않습니다는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="38d88-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="38d88-109"><xref:System.Windows.Forms.Control.OnPaint%2A> 메서드 <xref:System.Windows.Forms.Control> 디스패치 하기만 <xref:System.Windows.Forms.Control.Paint> 등록 된 이벤트 수신기에는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="38d88-110">이 샘플에서 작업 한 경우 [하는 방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), 재정의 하는 예제에 알아보았습니다는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="38d88-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="38d88-111">다음 코드에서는 샘플에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-111">The following code fragment is taken from that sample.</span></span>  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class   
```  
  
```csharp  
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 <span data-ttu-id="38d88-112"><xref:System.Windows.Forms.PaintEventArgs> 클래스에 대 한 데이터가 포함 된 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="38d88-113">이것은 다음 코드에 표시 된 두 개의 속성.</span><span class="sxs-lookup"><span data-stu-id="38d88-113">It has two properties, as shown in the following code.</span></span>  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property   
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <span data-ttu-id="38d88-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>그리려는 사각형 및 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 속성은 참조는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="38d88-115">클래스는 <xref:System.Drawing?displayProperty=nameWithType> 네임 스페이스는 관리의 기능에 대 한 액세스를 제공 하는 클래스 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 새 Windows 그래픽 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], the new Windows graphics library.</span></span> <span data-ttu-id="38d88-116"><xref:System.Drawing.Graphics> 개체의 포인트, 문자열, 선, 타원, 타원, 및 기타 많은 도형을 그릴 수 있는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="38d88-117">컨트롤 호출 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 자신의 시각적 표시를 변경 해야 할 때마다 메서드.</span><span class="sxs-lookup"><span data-stu-id="38d88-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="38d88-118">이 메서드는 메서드가 다시에 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="38d88-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d88-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38d88-119">See Also</span></span>  
 [<span data-ttu-id="38d88-120">이벤트</span><span class="sxs-lookup"><span data-stu-id="38d88-120">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="38d88-121">Windows Forms 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="38d88-121">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [<span data-ttu-id="38d88-122">이벤트 정의</span><span class="sxs-lookup"><span data-stu-id="38d88-122">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
