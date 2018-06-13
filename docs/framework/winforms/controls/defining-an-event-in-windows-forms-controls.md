---
title: Windows Forms 컨트롤에서 이벤트 정의
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- events [Windows Forms], defining within Windows Forms custom controls
- custom controls [Windows Forms], events using code
ms.assetid: d89f1096-8061-42e2-a855-a1f053f1940a
ms.openlocfilehash: 552f2b8441ae5323f55f236fabb9f50f8f8b5ab0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524035"
---
# <a name="defining-an-event-in-windows-forms-controls"></a><span data-ttu-id="4e5f6-102">Windows Forms 컨트롤에서 이벤트 정의</span><span class="sxs-lookup"><span data-stu-id="4e5f6-102">Defining an Event in Windows Forms Controls</span></span>
<span data-ttu-id="4e5f6-103">사용자 지정 이벤트를 정의 하는 방법에 대 한 세부 정보를 참조 하십시오. [이벤트](../../../../docs/standard/events/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5f6-103">For details about defining custom events, see [Events](../../../../docs/standard/events/index.md).</span></span> <span data-ttu-id="4e5f6-104">연결된 데이터가 없는 이벤트를 정의하는 경우에는 이벤트 데이터의 기본 형식인 <xref:System.EventArgs>를 사용하고 이벤트 대리자로 <xref:System.EventHandler>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5f6-104">If you define an event that does not have any associated data, use the base type for event data, <xref:System.EventArgs>, and use <xref:System.EventHandler> as the event delegate.</span></span> <span data-ttu-id="4e5f6-105">이벤트 멤버 및 보호 된 정의를 작업을 수행 하는 남게 됩니다 `On` *EventName* 이벤트를 발생 시키는 메서드.</span><span class="sxs-lookup"><span data-stu-id="4e5f6-105">All that remains to do is to define an event member and a protected `On`*EventName* method that raises the event.</span></span>  
  
 <span data-ttu-id="4e5f6-106">다음 코드 조각은 `FlashTrackBar` 사용자 지정 컨트롤이 사용자 지정 이벤트 `ValueChanged`를 정의하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e5f6-106">The following code fragment shows how the `FlashTrackBar` custom control defines a custom event, `ValueChanged`.</span></span> <span data-ttu-id="4e5f6-107">에 대 한 전체 코드에 대 한는 `FlashTrackBar` 예제를 참조는 [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e5f6-107">For the complete code for the `FlashTrackBar` sample, see the [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class FlashTrackBar  
   Inherits Control  
  
   ' The event does not have any data, so EventHandler is adequate   
   ' as the event delegate.          
   ' Define the event member using the event keyword.  
   ' In this case, for efficiency, the event is defined   
   ' using the event property construct.  
   Public Event ValueChanged As EventHandler  
   ' The protected method that raises the ValueChanged   
   ' event when the value has actually   
   ' changed. Derived controls can override this method.    
   Protected Overridable Sub OnValueChanged(e As EventArgs)  
      RaiseEvent ValueChanged(Me, e)  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class FlashTrackBar : Control {  
   // The event does not have any data, so EventHandler is adequate   
   // as the event delegate.  
   private EventHandler onValueChanged;  
   // Define the event member using the event keyword.  
   // In this case, for efficiency, the event is defined   
   // using the event property construct.  
   public event EventHandler ValueChanged {  
            add {  
                onValueChanged += value;  
            }  
            remove {  
                onValueChanged -= value;  
            }  
        }  
   // The protected method that raises the ValueChanged  
   // event when the value has actually   
   // changed. Derived controls can override this method.    
   protected virtual void OnValueChanged(EventArgs e) {  
      if (ValueChanged != null) {  
         ValueChanged(this, e);  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e5f6-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e5f6-108">See Also</span></span>  
 [<span data-ttu-id="4e5f6-109">Windows Forms 컨트롤의 이벤트</span><span class="sxs-lookup"><span data-stu-id="4e5f6-109">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="4e5f6-110">이벤트</span><span class="sxs-lookup"><span data-stu-id="4e5f6-110">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="4e5f6-111">이벤트</span><span class="sxs-lookup"><span data-stu-id="4e5f6-111">Events</span></span>](../../../../docs/standard/events/index.md)
