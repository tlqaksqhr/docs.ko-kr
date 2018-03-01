---
title: "Windows Forms 응용 프로그램의 사용자 입력"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 60135c09f63bd98f753e151c515938cbf13e70ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="user-input-in-a-windows-forms-application"></a><span data-ttu-id="a7555-102">Windows Forms 응용 프로그램의 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="a7555-102">User Input in a Windows Forms Application</span></span>
<span data-ttu-id="a7555-103">Windows Forms에서 사용자 입력 Windows 메시지 형식으로의 응용 프로그램에 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-103">In Windows Forms, user input is sent to applications in the form of Windows messages.</span></span> <span data-ttu-id="a7555-104">응용 프로그램 폼에서 이러한 메시지를 처리 하 고 수준을 제어 하는 일련의 재정의 가능한 메서드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-104">A series of overridable methods process these messages at the application, form, and control level.</span></span> <span data-ttu-id="a7555-105">이러한 메서드는 마우스 및 키보드 메시지를 수신 하는 경우 마우스에 대 한 정보를 얻거나 키보드 입력을 처리할 수 있는 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-105">When these methods receive mouse and keyboard messages, they raise events that can be handled to get information about the mouse or keyboard input.</span></span> <span data-ttu-id="a7555-106">대부분의 경우에서 Windows Forms 응용 프로그램은 이러한 이벤트를 처리 하 여 모든 사용자 입력을 처리 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-106">In many cases, Windows Forms applications will be able to process all user input simply by handling these events.</span></span> <span data-ttu-id="a7555-107">다른 경우에 응용 프로그램은 응용 프로그램, 폼 또는 컨트롤에서 수신 하기 전에 특정 메시지를 차단 하기 위해 메시지를 처리 하는 메서드 중 하나를 재정의 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-107">In other cases, an application may need to override one of the methods that process messages in order to intercept a particular message before it is received by the application, form, or control.</span></span>  
  
## <a name="mouse-and-keyboard-events"></a><span data-ttu-id="a7555-108">마우스 및 키보드 이벤트</span><span class="sxs-lookup"><span data-stu-id="a7555-108">Mouse and Keyboard Events</span></span>  
 <span data-ttu-id="a7555-109">모든 Windows Forms 컨트롤의 마우스 및 키보드 입력와 관련 된 이벤트 집합을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-109">All Windows Forms controls inherit a set of events related to mouse and keyboard input.</span></span> <span data-ttu-id="a7555-110">예를 들어 한 컨트롤에서 처리할 수는 <xref:System.Windows.Forms.Control.KeyPress> 는 눌린 키의 문자 코드를 확인 하는 이벤트 또는 컨트롤을 처리할 수는 <xref:System.Windows.Forms.Control.MouseClick> 클릭 마우스의 위치를 결정 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-110">For example, a control can handle the <xref:System.Windows.Forms.Control.KeyPress> event to determine the character code of a key that was pressed, or a control can handle the <xref:System.Windows.Forms.Control.MouseClick> event to determine the location of a mouse click.</span></span> <span data-ttu-id="a7555-111">마우스 및 키보드 이벤트에 대 한 자세한 내용은 참조 하십시오. [키보드 이벤트를 사용 하 여](../../../docs/framework/winforms/using-keyboard-events.md) 및 [Windows Forms의 마우스 이벤트](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-111">For more information on the mouse and keyboard events, see [Using Keyboard Events](../../../docs/framework/winforms/using-keyboard-events.md) and [Mouse Events in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).</span></span>  
  
## <a name="methods-that-process-user-input-messages"></a><span data-ttu-id="a7555-112">사용자 입력된 메시지를 처리 하는 메서드</span><span class="sxs-lookup"><span data-stu-id="a7555-112">Methods that Process User Input Messages</span></span>  
 <span data-ttu-id="a7555-113">폼 및 컨트롤에 대 한 액세스 권한이 <xref:System.Windows.Forms.IMessageFilter> 인터페이스 및 메시지 큐의 여러 지점에서 Windows 메시지를 처리 하는 재정의 가능한 메서드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-113">Forms and controls have access to the <xref:System.Windows.Forms.IMessageFilter> interface and a set of overridable methods that process Windows messages at different points in the message queue.</span></span> <span data-ttu-id="a7555-114">모든는 이러한 메서드는 <xref:System.Windows.Forms.Message> Windows 메시지의 하위 수준 세부 정보를 캡슐화 하는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-114">These methods all have a <xref:System.Windows.Forms.Message> parameter, which encapsulates the low-level details of Windows messages.</span></span> <span data-ttu-id="a7555-115">구현 하거나 메시지에서 확인 된 메시지를 사용 하거나 메시지 큐에서 다음 소비자에 전달 하도록 이러한 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-115">You can implement or override these methods to examine the message and then either consume the message or pass it on to the next consumer in the message queue.</span></span> <span data-ttu-id="a7555-116">다음 표에서 Windows Forms에서 모든 Windows 메시지를 처리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-116">The following table presents the methods that process all Windows messages in Windows Forms.</span></span>  
  
|<span data-ttu-id="a7555-117">메서드</span><span class="sxs-lookup"><span data-stu-id="a7555-117">Method</span></span>|<span data-ttu-id="a7555-118">노트</span><span class="sxs-lookup"><span data-stu-id="a7555-118">Notes</span></span>|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|<span data-ttu-id="a7555-119">이 메서드는 응용 프로그램 수준에서 대기 중인된 (게시 라고도 함) Windows 메시지를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-119">This method intercepts queued (also known as posted) Windows messages at the application level.</span></span>|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|<span data-ttu-id="a7555-120">이 메서드는 처리 전에 폼과 컨트롤 수준에서 Windows 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-120">This method intercepts Windows messages at the form and control level before they have been processed.</span></span>|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|<span data-ttu-id="a7555-121">이 메서드는 폼과 컨트롤 수준에서 Windows 메시지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-121">This method processes Windows messages at the form and control level.</span></span>|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|<span data-ttu-id="a7555-122">이 메서드는 폼과 컨트롤 수준에서 Windows 메시지의 기본 처리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-122">This method performs the default processing of Windows messages at the form and control level.</span></span> <span data-ttu-id="a7555-123">창의 최소 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-123">This provides the minimal functionality of a window.</span></span>|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|<span data-ttu-id="a7555-124">처리 된 후이 메서드는 폼과 컨트롤 수준에서 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-124">This method intercepts messages at the form and control level, after they have been processed.</span></span> <span data-ttu-id="a7555-125"><xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> 이 메서드를 호출할 수에 대 한 스타일 비트를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-125">The <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> style bit must be set for this method to be called.</span></span>|  
  
 <span data-ttu-id="a7555-126">키보드 및 마우스 메시지의 해당 유형의 메시지에만 적용 되는 재정의 가능한 메서드가 추가 집합으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-126">Keyboard and mouse messages are also processed by an additional set of overridable methods that are specific to those types of messages.</span></span> <span data-ttu-id="a7555-127">자세한 내용은 참조 [키보드 입력 작동 방식](../../../docs/framework/winforms/how-keyboard-input-works.md) 및 [Windows Forms의 마우스 입력 방법](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7555-127">For more information, see [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md) and [How Mouse Input Works in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7555-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7555-128">See Also</span></span>  
 [<span data-ttu-id="a7555-129">Windows Forms에 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="a7555-129">User Input in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 [<span data-ttu-id="a7555-130">Windows Forms 응용 프로그램의 키보드 입력</span><span class="sxs-lookup"><span data-stu-id="a7555-130">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="a7555-131">Windows Forms 응용 프로그램의 마우스 입력</span><span class="sxs-lookup"><span data-stu-id="a7555-131">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
