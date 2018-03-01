---
title: "방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bfd955b4153c7a2bc54d8b52ff1801541c3a7559
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="5e02a-102">방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결</span><span class="sxs-lookup"><span data-stu-id="5e02a-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="5e02a-103">응용 프로그램 디자인에서 있습니다 경우가 여러 이벤트에 대 한 단일 이벤트 처리기를 사용 하거나 동일한 절차를 수행 하는 여러 개의 이벤트가 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="5e02a-104">예를 들어 것이 강력한 시간을 절약할에 메뉴 명령을 폼의 단추를 구현 하는 경우 동일한 기능으로 같은 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="5e02a-105">사용 하거나 속성 창에 C#의 이벤트 보기를 사용 하 여이 작업을 수행할 수는 `Handles` 키워드 및 **클래스 이름** 및 **메서드 이름** Visual Basic 코드 편집기에서 드롭다운 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="5e02a-106">Visual Basic에서 단일 이벤트 처리기에 여러 이벤트 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="5e02a-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1.  <span data-ttu-id="5e02a-107">폼을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-107">Right-click the form and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="5e02a-108">**클래스 이름** 드롭다운 목록 상자에서 처리할 이벤트 처리기를 컨트롤 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3.  <span data-ttu-id="5e02a-109">**메서드 이름** 드롭다운 목록 상자에서 이벤트를 처리할 이벤트 처리기를 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4.  <span data-ttu-id="5e02a-110">코드 편집기는 적절 한 이벤트 처리기를 삽입 하 고 메서드 내에서 삽입 포인터를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="5e02a-111">아래 예제에서는 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트는 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  <span data-ttu-id="5e02a-112">다른 처리 하는 이벤트 선택에 추가 하는 `Handles` 절.</span><span class="sxs-lookup"><span data-stu-id="5e02a-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  <span data-ttu-id="5e02a-113">이벤트 처리기에 적절 한 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="5e02a-114">C#에서 단일 이벤트 처리기에 여러 이벤트 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="5e02a-114">To connect multiple events to a single event handler in C#</span></span>  
  
1.  <span data-ttu-id="5e02a-115">이벤트 처리기를 연결 하려면 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-115">Select the control to which you want to connect an event handler.</span></span>  
  
2.  <span data-ttu-id="5e02a-116">속성 창에서 클릭 된 **이벤트** 단추 (![이벤트 단추](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="5e02a-116">In the Properties window, click the **Events** button (![Events Button](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3.  <span data-ttu-id="5e02a-117">처리할 이벤트의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-117">Click the name of the event that you want to handle.</span></span>  
  
4.  <span data-ttu-id="5e02a-118">이벤트 이름 옆에 있는 값 섹션을 처리 하려면 이벤트의 메서드 시그니처를 일치 하는 기존 이벤트 처리기의 목록을 표시 하려면 드롭다운 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5.  <span data-ttu-id="5e02a-119">목록에서 적절 한 이벤트 처리기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="5e02a-120">코드에서 기존 이벤트 처리기에 이벤트를 바인딩할 폼에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e02a-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e02a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e02a-121">See Also</span></span>  
 [<span data-ttu-id="5e02a-122">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="5e02a-122">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="5e02a-123">이벤트 처리기 개요</span><span class="sxs-lookup"><span data-stu-id="5e02a-123">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
