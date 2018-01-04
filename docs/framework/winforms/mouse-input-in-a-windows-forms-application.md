---
title: "Windows Forms 응용 프로그램의 마우스 입력"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Windows Forms, mouse input
ms.assetid: 743c2f3c-219e-4a52-b6b8-2657096a2da6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56b267222f8e22d9d411d744f67d93cde6ba17a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="mouse-input-in-a-windows-forms-application"></a><span data-ttu-id="9d0e7-102">Windows Forms 응용 프로그램의 마우스 입력</span><span class="sxs-lookup"><span data-stu-id="9d0e7-102">Mouse Input in a Windows Forms Application</span></span>
<span data-ttu-id="9d0e7-103">Windows Forms에는 다양한 마우스 이벤트 및 사용자 지정된 마우스 커서, 마우스 캡처 및 끌어서 놓기 동작에 대한 추가 지원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d0e7-103">Windows Forms includes a variety of mouse events and additional support for customized mouse cursors, mouse capture, and drag-and-drop behavior.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d0e7-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="9d0e7-104">In This Section</span></span>  
 [<span data-ttu-id="9d0e7-105">Windows Forms에서 마우스 입력이 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="9d0e7-105">How Mouse Input Works in Windows Forms</span></span>](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md)  
 <span data-ttu-id="9d0e7-106">마우스 이벤트에 대한 정보 및 마우스에 대한 현재 정보와 시스템 설정을 가져오는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0e7-106">Provides information about the mouse events and how to get current information and system settings for the mouse.</span></span>  
  
 [<span data-ttu-id="9d0e7-107">Windows Forms의 마우스 이벤트</span><span class="sxs-lookup"><span data-stu-id="9d0e7-107">Mouse Events in Windows Forms</span></span>](../../../docs/framework/winforms/mouse-events-in-windows-forms.md)  
 <span data-ttu-id="9d0e7-108">마우스 이벤트가 발생하는 순서 및 특정 컨트롤 내에서 마우스 이벤트가 발생되는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0e7-108">Provides information about the order in which the mouse events occur and how the mouse events are raised within specific controls.</span></span>  
  
 [<span data-ttu-id="9d0e7-109">방법: 클릭과 두 번 클릭 간 구별</span><span class="sxs-lookup"><span data-stu-id="9d0e7-109">How to: Distinguish Between Clicks and Double-Clicks</span></span>](../../../docs/framework/winforms/how-to-distinguish-between-clicks-and-double-clicks.md)  
 <span data-ttu-id="9d0e7-110">한 번 클릭과 두 번 클릭을 사용하여 호환되지 않는 작업을 시작하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d0e7-110">Demonstrates how to use single and double clicks to initiate incompatible actions.</span></span>  
  
 [<span data-ttu-id="9d0e7-111">Windows Forms의 마우스 포인터</span><span class="sxs-lookup"><span data-stu-id="9d0e7-111">Mouse Pointers in Windows Forms</span></span>](../../../docs/framework/winforms/mouse-pointers-in-windows-forms.md)  
 <span data-ttu-id="9d0e7-112">마우스 커서를 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0e7-112">Describes how to change the mouse cursor.</span></span>  
  
 [<span data-ttu-id="9d0e7-113">Windows Forms의 마우스 캡처</span><span class="sxs-lookup"><span data-stu-id="9d0e7-113">Mouse Capture in Windows Forms</span></span>](../../../docs/framework/winforms/mouse-capture-in-windows-forms.md)  
 <span data-ttu-id="9d0e7-114">컨트롤이 마우스를 캡처할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0e7-114">Describes how a control can capture the mouse.</span></span>  
  
 [<span data-ttu-id="9d0e7-115">Windows Forms에서의 끌어서 놓기 기능</span><span class="sxs-lookup"><span data-stu-id="9d0e7-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="9d0e7-116">끌어서 놓기 동작을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0e7-116">Describes how to implement drag-and-drop behavior.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9d0e7-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="9d0e7-117">Related Sections</span></span>  
 [<span data-ttu-id="9d0e7-118">마우스에 액세스</span><span class="sxs-lookup"><span data-stu-id="9d0e7-118">Accessing the Mouse</span></span>](~/docs/visual-basic/developing-apps/programming/computer-resources/accessing-the-mouse.md)  
 <span data-ttu-id="9d0e7-119">Visual Basic을 사용하여 마우스에 액세스에 대한 항목을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9d0e7-119">Lists topics for accessing the mouse using Visual Basic.</span></span>
