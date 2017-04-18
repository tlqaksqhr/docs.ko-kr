---
title: "WF의 상태 시스템 활동 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# WF의 상태 시스템 활동
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 상태 시스템 워크플로를 만들기 위한 여러 시스템 제공 활동 및 활동 디자이너를 제공합니다.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|익숙한 상태 시스템 패러다임을 사용하여 포함된 활동을 실행합니다.|  
|<xref:System.Activities.Statements.State>|상태 시스템의 상태를 나타냅니다.|  
|<xref:System.Activities.Core.Presentation.FinalState>|상태 시스템의 종료 상태를 나타냅니다.<xref:System.Activities.Core.Presentation.FinalState>는 사용될 경우 종료 상태로 미리 구성되는 <xref:System.Activities.Statements.State>를 만드는 활동 디자이너입니다.자세한 내용은 [FinalState 활동 디자이너](../Topic/FinalState%20Activity%20Designer.md)를 참조하십시오.|  
|<xref:System.Activities.Statements.Transition>|두 상태 간 전환을 나타냅니다.<xref:System.Activities.Statements.Transition>에 대한 **도구 상자** 항목이 없습니다. 전환은 Workflow Designer에서 두 상태 사이의 선을 끌어 놓거나, 한 상태가 다른 상태 위에 있을 때 표시되는 삼각형에 상태를 놓아 만듭니다.자세한 내용은 [전환 활동 디자이너](../Topic/Transition%20Activity%20Designer.md)를 참조하십시오.|  
  
## 참고 항목  
 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)