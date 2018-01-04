---
title: "활동 클래스를 사용하여 워크플로 활동 제작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b7b1c66-f093-43c3-b4d1-7173b46516da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52d29f9cbed65932b3f9e97f0e9275861953b5d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-activity-authoring-using-the-activity-class"></a><span data-ttu-id="9b710-102">활동 클래스를 사용하여 워크플로 활동 제작</span><span class="sxs-lookup"><span data-stu-id="9b710-102">Workflow Activity Authoring Using the Activity Class</span></span>
<span data-ttu-id="9b710-103">사용 하 여 활동을 만드는 가장 기본적인 방법은 [!INCLUDE[wf](../../../includes/wf-md.md)] 에 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] 에서 상속 되는 클래스를 만드는 <xref:System.Activities.Activity> 만들어지는 기능 어셈블하는 방법으로 사용자 지정 활동 또는 활동에서는 [기본 제공 활동 라이브러리 ](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span><span class="sxs-lookup"><span data-stu-id="9b710-103">The most basic way to create an activity using [!INCLUDE[wf](../../../includes/wf-md.md)] in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] is to create a class that inherits from <xref:System.Activities.Activity> that creates functionality by assembling custom activities or activities from the [Built-In Activity Library](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).</span></span> <span data-ttu-id="9b710-104">이 항목에서는 콘솔에 두 개의 메시지를 쓰는 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-104">This topic demonstrates how to create an activity that writes two messages to the console.</span></span>  
  
### <a name="to-create-a-custom-activity-using-the-activity-designer"></a><span data-ttu-id="9b710-105">활동 디자이너를 사용하여 사용자 지정 활동을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9b710-105">To create a custom Activity using the activity designer</span></span>  
  
1.  <span data-ttu-id="9b710-106">[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-106">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b710-107">파일, 새로 만들기, 프로젝트를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-107">Select File, New, Project.</span></span> <span data-ttu-id="9b710-108">선택 **Workflow 4.0** 아래 **Visual C#** 에 **프로젝트 형식** 창과 선택은 **v2010** 노드.</span><span class="sxs-lookup"><span data-stu-id="9b710-108">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="9b710-109">선택 **활동 라이브러리** 에 **템플릿** 창.</span><span class="sxs-lookup"><span data-stu-id="9b710-109">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="9b710-110">새 프로젝트의 이름을 HelloActivity로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-110">Name the new project HelloActivity.</span></span>  
  
3.  <span data-ttu-id="9b710-111">새 활동을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-111">Open the new activity.</span></span>  <span data-ttu-id="9b710-112">도구 상자의 <xref:System.Activities.Statements.Sequence> 활동을 디자이너 화면으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-112">Drag a <xref:System.Activities.Statements.Sequence> activity from the toolbox onto the designer surface.</span></span>  
  
4.  <span data-ttu-id="9b710-113"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-113">Drag a <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="9b710-114">입력 `"Hello World"` (따옴표 포함)와는 **텍스트** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-114">Enter `"Hello World"` (with quotes) into the **Text** field.</span></span>  
  
5.  <span data-ttu-id="9b710-115">두 번째 <xref:System.Activities.Statements.WriteLine> 활동을 첫 번째 활동 아래의 <xref:System.Activities.Statements.Sequence> 활동으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-115">Drag a second <xref:System.Activities.Statements.WriteLine> activity into the <xref:System.Activities.Statements.Sequence> activity, below the first one.</span></span> <span data-ttu-id="9b710-116">입력 `"Goodbye"` (따옴표 포함)와는 **텍스트** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="9b710-116">Enter `"Goodbye"` (with quotes) into the **Text** field.</span></span>
