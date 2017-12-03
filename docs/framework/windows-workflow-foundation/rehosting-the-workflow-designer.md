---
title: "워크플로 디자이너 재호스트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c01b39a8f21011bb45a1d73fcf44df76d5bf6fb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="789af-102">워크플로 디자이너 재호스트</span><span class="sxs-lookup"><span data-stu-id="789af-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="789af-103">워크플로 만들기, 수정, 모니터링을 위해 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 외부 환경에서 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]를 다시 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="789af-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] for the purposes of creating, modifying, and monitoring workflows.</span></span>  
  
 <span data-ttu-id="789af-104"><xref:System.Activities.Presentation.WorkflowDesigner> 형식은 캔버스, 속성표 및 기타 요소의 래퍼이며 기본 프로그래밍 모델을 노출하여 대부분의 디자이너 다시 호스팅 시나리오를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="789af-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="789af-105"><xref:System.Activities.Presentation.WorkflowDesigner> 응용 프로그램 내부에 [!INCLUDE[avalon1](../../../includes/avalon1-md.md)]를 호스트하는 것은 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]에 대한 일반적인 재호스팅 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="789af-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="789af-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="789af-106">In This Section</span></span>  
 [<span data-ttu-id="789af-107">작업 1: 새 Windows Presentation Foundation 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="789af-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
  
 [<span data-ttu-id="789af-108">작업 2: 워크플로 디자이너 호스트</span><span class="sxs-lookup"><span data-stu-id="789af-108">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)  
  
 [<span data-ttu-id="789af-109">작업 3: 도구 상자 및 PropertyGrid 창 만들기</span><span class="sxs-lookup"><span data-stu-id="789af-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)  
  
 [<span data-ttu-id="789af-110">재호스트된 워크플로 디자이너에서 새 Workflow Foundation 4.5 기능에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="789af-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md)  
  
## <a name="see-also"></a><span data-ttu-id="789af-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="789af-111">See Also</span></span>  
 [<span data-ttu-id="789af-112">워크플로 디자인 환경 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="789af-112">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
