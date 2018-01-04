---
title: "Windows Forms에서의 이벤트 순서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03d2661752e5c0acb36fe76a8fa72b0638b4ad54
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="order-of-events-in-windows-forms"></a><span data-ttu-id="78548-102">Windows Forms에서의 이벤트 순서</span><span class="sxs-lookup"><span data-stu-id="78548-102">Order of Events in Windows Forms</span></span>
<span data-ttu-id="78548-103">Windows Forms 응용 프로그램에서 이벤트가 발생하는 순서는 반대로 이러한 각 이벤트의 처리와 관련된 개발자에게 특히 관심 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="78548-103">The order in which events are raised in Windows Forms applications is of particular interest to developers concerned with handling each of these events in turn.</span></span> <span data-ttu-id="78548-104">폼 부분을 다시 그려야 하는 경우와 같이 이벤트를 세심하게 처리해야 하는 상황에서는 런타임에 이벤트가 발생한 정확한 순서를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-104">When a situation calls for meticulous handling of events, such as when you are redrawing parts of the form, an awareness of the precise order in which events are raised at run time is necessary.</span></span> <span data-ttu-id="78548-105">이 항목에서는 응용 프로그램 및 컨트롤 수명에서 여러 중요한 단계 중에 발생하는 이벤트 순서에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-105">This topic provides some details on the order of events during several important stages in the lifetime of applications and controls.</span></span> <span data-ttu-id="78548-106">마우스 입력된 이벤트의 순서에 대 한 특정 세부 정보를 참조 하십시오. [Windows Forms의 마우스 이벤트](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-106">For specific details about the order of mouse input events, see [Mouse Events in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).</span></span> <span data-ttu-id="78548-107">Windows Forms의 이벤트의 개요를 참조 하십시오. [이벤트 개요](../../../docs/framework/winforms/events-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-107">For an overview of events in Windows Forms, see [Events Overview](../../../docs/framework/winforms/events-overview-windows-forms.md).</span></span> <span data-ttu-id="78548-108">이벤트 처리기 구성에 대 한 세부 정보를 참조 하십시오. [이벤트 처리기 개요](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-108">For details about the makeup of event handlers, see [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
## <a name="application-startup-and-shutdown-events"></a><span data-ttu-id="78548-109">응용 프로그램 시작 및 종료 이벤트</span><span class="sxs-lookup"><span data-stu-id="78548-109">Application Startup and Shutdown Events</span></span>  
 <span data-ttu-id="78548-110"><xref:System.Windows.Forms.Form> 및 <xref:System.Windows.Forms.Control> 클래스는 응용 프로그램 시작 및 종료와 관련된 이벤트 집합을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-110">The <xref:System.Windows.Forms.Form> and <xref:System.Windows.Forms.Control> classes expose a set of events related to application startup and shutdown.</span></span> <span data-ttu-id="78548-111">Windows Forms 응용 프로그램이 시작되면 주 폼의 시작 이벤트가 다음 순서대로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-111">When a Windows Forms application starts, the startup events of the main form are raised in the following order:</span></span>  
  
-   <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 <span data-ttu-id="78548-112">응용 프로그램이 닫히면 주 폼의 종료 이벤트가 다음 순서대로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-112">When an application closes, the shutdown events of the main form are raised in the following order:</span></span>  
  
-   <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 <span data-ttu-id="78548-113"><xref:System.Windows.Forms.Application> 클래스의 <xref:System.Windows.Forms.Application.ApplicationExit> 이벤트는 주 폼의 종료 이벤트 뒤에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-113">The <xref:System.Windows.Forms.Application.ApplicationExit> event of the <xref:System.Windows.Forms.Application> class is raised after the shutdown events of the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78548-114">Visual Basic 2005에는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> 및 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>과 같은 추가 응용 프로그램 이벤트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="78548-114">Visual Basic 2005 includes additional application events, such as <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> and <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span></span>  
  
## <a name="focus-and-validation-events"></a><span data-ttu-id="78548-115">포커스 및 유효성 검사 이벤트</span><span class="sxs-lookup"><span data-stu-id="78548-115">Focus and Validation Events</span></span>  
 <span data-ttu-id="78548-116">키보드(TAB, SHIFT+TAB 등)를 사용하거나, <xref:System.Windows.Forms.Control.Select%2A> 또는 <xref:System.Windows.Forms.Control.SelectNextControl%2A> 메서드를 호출하거나, <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 속성을 현재 폼으로 설정하여 포커스를 변경하면 <xref:System.Windows.Forms.Control> 클래스의 포커스 이벤트가 다음 순서대로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-116">When you change the focus by using the keyboard (TAB, SHIFT+TAB, and so on), by calling the <xref:System.Windows.Forms.Control.Select%2A> or <xref:System.Windows.Forms.Control.SelectNextControl%2A> methods, or by setting the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property to the current form, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
 <span data-ttu-id="78548-117">마우스를 사용하거나 <xref:System.Windows.Forms.Control.Focus%2A> 메서드를 호출하여 포커스를 변경하면 <xref:System.Windows.Forms.Control> 클래스의 포커스 이벤트가 다음 순서대로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="78548-117">When you change the focus by using the mouse or by calling the <xref:System.Windows.Forms.Control.Focus%2A> method, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a><span data-ttu-id="78548-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78548-118">See Also</span></span>  
 [<span data-ttu-id="78548-119">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="78548-119">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
