---
title: "예외, 트랜잭션 및 보정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e83661ba66ca6a71f26c11172902d5bc602a2f6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="6881e-102">예외, 트랜잭션 및 보정</span><span class="sxs-lookup"><span data-stu-id="6881e-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="6881e-103">에서는 워크플로에서 런타임 오류 조건을 처리하는 다양한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6881e-103"> provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="6881e-104">워크플로에서는 예외 처리기, 트랜잭션, 취소 및 보정을 함께 사용하여 오류 조건을 정상적으로 처리 및 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6881e-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6881e-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6881e-105">In This Section</span></span>  
 [<span data-ttu-id="6881e-106">예외</span><span class="sxs-lookup"><span data-stu-id="6881e-106">Exceptions</span></span>](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 <span data-ttu-id="6881e-107"><xref:System.Activities.Statements.TryCatch> 활동을 사용하여 워크플로에서 예외를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6881e-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="6881e-108">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="6881e-108">Transactions</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 <span data-ttu-id="6881e-109"><xref:System.Activities.Statements.TransactionScope> 활동을 사용하여 워크플로에서 트랜잭션을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6881e-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="6881e-110">보정</span><span class="sxs-lookup"><span data-stu-id="6881e-110">Compensation</span></span>](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 <span data-ttu-id="6881e-111">워크플로의 보정에 대해 설명하고 <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, <xref:System.Activities.Statements.Confirm> 등과 같은 보정 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6881e-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="6881e-112">취소</span><span class="sxs-lookup"><span data-stu-id="6881e-112">Cancellation</span></span>](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="6881e-113">기본 제공 활동과 사용자 지정 활동을 사용하여 워크플로에서 취소를 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6881e-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="6881e-114">워크플로 디버깅</span><span class="sxs-lookup"><span data-stu-id="6881e-114">Debugging Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 <span data-ttu-id="6881e-115">워크플로를 디버깅하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6881e-115">Describes how to debug workflows.</span></span>
