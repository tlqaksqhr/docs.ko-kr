---
title: "Windows Forms 컨트롤의 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e568dd7fadea8af399a63aa95347f368b4e13a54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="0fa1b-102">Windows Forms 컨트롤의 이벤트</span><span class="sxs-lookup"><span data-stu-id="0fa1b-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="0fa1b-103">Windows Forms 컨트롤의 60 개 이상의 이벤트 상속 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa1b-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0fa1b-104">여기에 <xref:System.Windows.Forms.Control.Paint> 이벤트는 컨트롤을 그릴 수 있도록,와 같은 창에 표시와 관련 된 이벤트는 <xref:System.Windows.Forms.Control.Resize> 및 <xref:System.Windows.Forms.Control.Layout> 이벤트 및 하위 수준 마우스 및 키보드 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0fa1b-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="0fa1b-105">일부 하위 수준 이벤트에서 합성 됩니다 <xref:System.Windows.Forms.Control> 와 같은 의미 이벤트로 <xref:System.Windows.Forms.Control.Click> 및 <xref:System.Windows.Forms.Control.DoubleClick>합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa1b-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="0fa1b-106">상속 된 이벤트에 대 한 세부 정보를 참조 하십시오. <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa1b-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="0fa1b-107">사용자 지정 컨트롤이 상속된 이벤트 기능을 재정의해야 하는 경우 대리자를 연결하는 대신 상속된 `On`*EventName* 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0fa1b-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="0fa1b-108">.NET Framework에서 이벤트 모델에 익숙하지 않다면 [구성 요소에서 이벤트 발생 시키기](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fa1b-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa1b-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fa1b-109">See Also</span></span>  
 [<span data-ttu-id="0fa1b-110">OnPaint 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="0fa1b-110">Overriding the OnPaint Method</span></span>](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [<span data-ttu-id="0fa1b-111">사용자 입력 처리</span><span class="sxs-lookup"><span data-stu-id="0fa1b-111">Handling User Input</span></span>](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [<span data-ttu-id="0fa1b-112">이벤트 정의</span><span class="sxs-lookup"><span data-stu-id="0fa1b-112">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [<span data-ttu-id="0fa1b-113">이벤트</span><span class="sxs-lookup"><span data-stu-id="0fa1b-113">Events</span></span>](../../../../docs/standard/events/index.md)
