---
title: "Windows Forms에서 이벤트 처리기 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a18afd8ba06b5bcc70ca5a6febc10be8050891b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="bb041-102">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="bb041-102">Creating Event Handlers in Windows Forms</span></span>
<span data-ttu-id="bb041-103">이벤트 처리기는 사용자가 단추를 클릭하거나 메시지 큐에서 메시지를 수신하는 등의 이벤트 발생 시 수행되는 작업을 결정하는 코드 내의 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="bb041-104">이벤트가 발생하면 해당 이벤트를 수신하는 하나 이상의 이벤트 처리기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="bb041-105">이벤트는 여러 처리기에 할당될 수 있으며 특정 이벤트를 처리하는 메서드가 동적으로 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="bb041-106">Windows Forms 디자이너를 사용하여 이벤트 처리기를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-106">You can also use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb041-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bb041-107">In This Section</span></span>  
 [<span data-ttu-id="bb041-108">이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="bb041-108">Events Overview</span></span>](../../../docs/framework/winforms/events-overview-windows-forms.md)  
 <span data-ttu-id="bb041-109">이벤트 모델과 대리자 역할에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-109">Explains the event model and the role of delegates.</span></span>  
  
 [<span data-ttu-id="bb041-110">이벤트 처리기 개요</span><span class="sxs-lookup"><span data-stu-id="bb041-110">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 <span data-ttu-id="bb041-111">이벤트를 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-111">Describes how to handle events.</span></span>  
  
 [<span data-ttu-id="bb041-112">방법: 런타임에 Windows Forms의 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="bb041-112">How to: Create Event Handlers at Run Time for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)  
 <span data-ttu-id="bb041-113">시스템 또는 사용자 이벤트에 동적으로 응답하는 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-113">Gives directions for responding to system or user events dynamically.</span></span>  
  
 [<span data-ttu-id="bb041-114">방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결</span><span class="sxs-lookup"><span data-stu-id="bb041-114">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)  
 <span data-ttu-id="bb041-115">이벤트를 통해 여러 컨트롤에 같은 기능을 할당하도록 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>  
  
 [<span data-ttu-id="bb041-116">Windows Forms에서의 이벤트 순서</span><span class="sxs-lookup"><span data-stu-id="bb041-116">Order of Events in Windows Forms</span></span>](../../../docs/framework/winforms/order-of-events-in-windows-forms.md)  
 <span data-ttu-id="bb041-117">Windows Forms 컨트롤에서 이벤트가 발생하는 순서에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-117">Describes the order in which events are raised in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="bb041-118">방법: 디자이너를 사용하여 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="bb041-118">How to: Create Event Handlers Using the Designer</span></span>](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2)  
 <span data-ttu-id="bb041-119">Windows Forms 디자이너를 사용하여 이벤트 처리기를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-119">Describes how to use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bb041-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="bb041-120">Related Sections</span></span>  
 [<span data-ttu-id="bb041-121">이벤트</span><span class="sxs-lookup"><span data-stu-id="bb041-121">Events</span></span>](../../../docs/standard/events/index.md)  
 <span data-ttu-id="bb041-122">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]를 사용하여 이벤트를 처리하고 발생시키는 방법을 설명하는 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-122">Provides links to topics on handling and raising events using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [<span data-ttu-id="bb041-123">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bb041-123">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="bb041-124">상속된 구성 요소의 이벤트 처리기에서 발생하는 일반적인 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb041-124">Lists common issues that occur with event handlers in inherited components.</span></span>
