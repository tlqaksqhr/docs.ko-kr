---
title: "WF의 트랜잭션 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb33378e-82c6-4ea0-870f-76dc77e7f0fe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6c72a54d596468e1ae6948ff9f177e026458628
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="transaction-activities-in-wf"></a><span data-ttu-id="6766a-102">WF의 트랜잭션 활동</span><span class="sxs-lookup"><span data-stu-id="6766a-102">Transaction Activities in WF</span></span>
<span data-ttu-id="6766a-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에는 모델링 트랜잭션, 보정 및 취소에 대한 여러 가지 시스템 제공 활동이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-103">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] has several system-provided activities for modeling transactions, compensation, and cancellation.</span></span> <span data-ttu-id="6766a-104">이러한 프로그래밍 모델을 사용하면 워크플로가 비즈니스 논리 및 오류 처리에 변경이 있는 경우 프로세스를 계속 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-104">These programming models allow the workflow to continue forward progress in the event of changes in business logic and error handling.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="6766a-105">트랜잭션, 보정 및 취소, 참조 [트랜잭션을](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [보정](../../../docs/framework/windows-workflow-foundation/compensation.md), 및 [취소](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-105"> transactions, compensation, and cancellation, see [Transactions](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [Compensation](../../../docs/framework/windows-workflow-foundation/compensation.md), and [Cancellation](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md).</span></span>  
  
## <a name="transaction-activities"></a><span data-ttu-id="6766a-106">트랜잭션 활동</span><span class="sxs-lookup"><span data-stu-id="6766a-106">Transaction Activities</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|<span data-ttu-id="6766a-107">활동 형식의 취소 논리를 역시 활동으로 표현되는 주 실행 경로와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-107">Associates cancellation logic, in the form of an activity, with a main path of execution, also expressed as an activity.</span></span>|  
|<xref:System.Activities.Statements.CompensableActivity>|<span data-ttu-id="6766a-108">자식 활동의 보정을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-108">Supports compensation of its child activities.</span></span>|  
|<xref:System.Activities.Statements.Compensate>|<span data-ttu-id="6766a-109"><xref:System.Activities.Statements.CompensableActivity>의 보정 처리기를 명시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-109">Explicitly invokes the compensation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.Confirm>|<span data-ttu-id="6766a-110"><xref:System.Activities.Statements.CompensableActivity>의 확인 처리기를 명시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-110">Explicitly invokes the confirmation handler of a <xref:System.Activities.Statements.CompensableActivity>.</span></span>|  
|<xref:System.Activities.Statements.TransactionScope>|<span data-ttu-id="6766a-111">트랜잭션 경계를 정합니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-111">Demarcates a transaction boundary.</span></span>|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|<span data-ttu-id="6766a-112">수신한 메시지로 시작되는 트랜잭션 수명의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-112">Scopes the lifetime of a transaction that is initiated by a received message.</span></span> <span data-ttu-id="6766a-113">트랜잭션은 시작 메시지의 워크플로로 이동하거나 메시지를 수신했을 때 디스패처로 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-113">The transaction may be flowed into the workflow on the initiating message, or created by the dispatcher when the message is received.</span></span> <span data-ttu-id="6766a-114">**참고:** 는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 에 위치한는 **메시징** 의 섹션은 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="6766a-114">**Note:**  The <xref:System.ServiceModel.Activities.TransactedReceiveScope> is located in the **Messaging** section of the **Toolbox**.</span></span>|
