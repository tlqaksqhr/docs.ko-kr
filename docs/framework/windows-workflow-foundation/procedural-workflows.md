---
title: "절차적 워크플로"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd879d138a95c003ca0ffb12b3ce010534c3e158
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="procedural-workflows"></a><span data-ttu-id="2efd5-102">절차적 워크플로</span><span class="sxs-lookup"><span data-stu-id="2efd5-102">Procedural Workflows</span></span>
<span data-ttu-id="2efd5-103">절차적 워크플로에서는 절차적 언어에서 사용되는 것과 비슷한 흐름 제어 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="2efd5-104">이러한 구조에는 `While` 및 `If`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="2efd5-105"><xref:System.Activities.Statements.Flowchart> 및 <xref:System.Activities.Statements.Sequence>와 같은 다른 흐름 제어 활동을 사용하여 이러한 워크플로를 자유롭게 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="2efd5-106">실행 흐름 제어</span><span class="sxs-lookup"><span data-stu-id="2efd5-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="2efd5-107">워크플로 활동 라이브러리에는 절차적 언어에서 사용되는 대부분의 흐름 제어 메서드를 모델링하기 위한 활동이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="2efd5-108">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-108">These include:</span></span>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="2efd5-109">흐름 제어 활동을 사용 하려면 끌어서 놓으십시오에서 **활동** 도구 상자 내에서 디자이너 창의 복합 활동으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2efd5-110">웹 팜에서 워크플로를 호스트하는 [!INCLUDE[dublin](../../../includes/dublin-md.md)]을 사용하면 AppFabric은 다른 AppFabric 서버 간 인스턴스를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="2efd5-111">이 경우 모든 노드 간에 리소스가 공유될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="2efd5-112">기본 NET 4 워크플로 활동 중 어떤 활동도 로컬 리소스에 액세스하는 작업을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="2efd5-113">AppFabric은 워크플로를 이동 불가능으로 표시하는 어떠한 메커니즘도 제공하지 않으므로 개발자는 워크플로가 이동할 때 실패할 수 있는 사용자 지정 활동을 만들지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efd5-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2efd5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2efd5-114">See Also</span></span>  
 [<span data-ttu-id="2efd5-115">순서도 워크플로</span><span class="sxs-lookup"><span data-stu-id="2efd5-115">Flowchart Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
