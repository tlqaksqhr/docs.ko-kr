---
title: "이벤트 처리기 개요(Windows Forms)"
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
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7353f3ab4513d8331b1d38cb01ad16c7d3cde165
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="ed5fc-102">이벤트 처리기 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ed5fc-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="ed5fc-103">이벤트 처리기는 이벤트에 바인딩된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="ed5fc-104">이벤트가 발생 하면 이벤트 처리기 내에서 코드가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="ed5fc-105">각 이벤트 처리기는 이벤트를 올바르게 처리할 수 있도록 하는 두 개의 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="ed5fc-106">다음 예제에 대 한 이벤트 처리기는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 <span data-ttu-id="ed5fc-107">첫 번째 매개 변수`sender`, 이벤트를 발생 시킨 개체에 대 한 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="ed5fc-108">두 번째 매개 변수 `e`, 위의 예제에는 개체를 전달 처리 되는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="ed5fc-109">개체의 속성 (및 경우에 따라 해당 메서드)를 참조 하 여 마우스 이벤트 또는 끌어서 놓기 이벤트에서 전송 되는 데이터에 대 한 마우스의 위치와 같은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="ed5fc-110">일반적으로 각 이벤트와 두 번째 매개 변수에 대 한 다른 이벤트 개체 유형 이벤트 처리기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="ed5fc-111">같은 일부 이벤트 처리기는 <xref:System.Windows.Forms.Control.MouseDown> 및 <xref:System.Windows.Forms.Control.MouseUp> 이벤트의 두 번째 매개 변수에 대 한 동일한 object 형식이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="ed5fc-112">이러한 종류의 이벤트에 대 한 두 이벤트를 처리 하는 동일한 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="ed5fc-113">또한 다른 컨트롤에 대해 동일한 이벤트를 처리 하는 동일한 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="ed5fc-114">예를 들어, 그룹이 있는 경우 <xref:System.Windows.Forms.RadioButton> 폼에 컨트롤에 대 한 단일 이벤트 처리기를 만들 수 있습니다는 <xref:System.Windows.Forms.Control.Click> 이벤트 각 컨트롤 <xref:System.Windows.Forms.Control.Click> 이벤트를 단일 이벤트 처리기에 바인딩된 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="ed5fc-115">자세한 내용은 참조 [하는 방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5fc-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed5fc-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed5fc-116">See Also</span></span>  
 [<span data-ttu-id="ed5fc-117">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="ed5fc-117">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="ed5fc-118">이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="ed5fc-118">Events Overview</span></span>](../../../docs/framework/winforms/events-overview-windows-forms.md)
