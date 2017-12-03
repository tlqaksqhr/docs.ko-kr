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
# <a name="transaction-activities-in-wf"></a>WF의 트랜잭션 활동
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에는 모델링 트랜잭션, 보정 및 취소에 대한 여러 가지 시스템 제공 활동이 있습니다. 이러한 프로그래밍 모델을 사용하면 워크플로가 비즈니스 논리 및 오류 처리에 변경이 있는 경우 프로세스를 계속 전달할 수 있습니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]트랜잭션, 보정 및 취소, 참조 [트랜잭션을](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md), [보정](../../../docs/framework/windows-workflow-foundation/compensation.md), 및 [취소](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)합니다.  
  
## <a name="transaction-activities"></a>트랜잭션 활동  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.CancellationScope>|활동 형식의 취소 논리를 역시 활동으로 표현되는 주 실행 경로와 연결합니다.|  
|<xref:System.Activities.Statements.CompensableActivity>|자식 활동의 보정을 지원합니다.|  
|<xref:System.Activities.Statements.Compensate>|<xref:System.Activities.Statements.CompensableActivity>의 보정 처리기를 명시적으로 호출합니다.|  
|<xref:System.Activities.Statements.Confirm>|<xref:System.Activities.Statements.CompensableActivity>의 확인 처리기를 명시적으로 호출합니다.|  
|<xref:System.Activities.Statements.TransactionScope>|트랜잭션 경계를 정합니다.|  
|<xref:System.ServiceModel.Activities.TransactedReceiveScope>|수신한 메시지로 시작되는 트랜잭션 수명의 범위입니다. 트랜잭션은 시작 메시지의 워크플로로 이동하거나 메시지를 수신했을 때 디스패처로 생성될 수 있습니다. **참고:** 는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 에 위치한는 **메시징** 의 섹션은 **도구 상자**합니다.|
