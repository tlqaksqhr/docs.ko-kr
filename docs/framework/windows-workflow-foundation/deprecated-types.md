---
title: "Deprecated types in Windows Workflow Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Deprecated types in Windows Workflow Foundation
.NET 4에서 워크플로 팀은 <xref:System.Activities> 네임스페이스에 완전히 새로운 워크플로 엔진을 제공했습니다.  .NET 4.5 베타 릴리스에서 "WF 3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel> 및 <xref:System.Workflow.Runtime> 네임스페이스에 있는 대부분의 형식은 더 이상 사용되지 않는 것으로 표시됩니다.  
  
## 사용되지 않는 네임스페이스 및 도구  
 다음 어셈블리에는 더 이상 사용되지 않는 하나 이상의 공용 형식이 있습니다.  
  
-   System.Workflow.Activities.dll  
  
-   System.Workflow.ComponentModel.dll  
  
-   System.Workflow.Runtime.dll  
  
-   System.WorkflowServices.dll  
  
-   Microsoft.Workflow.DebugController.dll  
  
-   Microsoft.Workflow.Compiler.exe  
  
-   Wfc.exe  
  
 따라서 고객이 더 이상 사용되지 않는 WF 3 API를 사용 중인 경우 다음과 유사한 메시지가 있는 빌드 경고가 표시됩니다.  
  
  **경고 BC40000: X는 사용되지 않습니다. WF 3 형식은 사용되지 않습니다.  대신 WF 4를 사용하세요.**  이후에 릴리스되는 .NET Framework에서는 이러한 형식을 제거하겠지만, 아직 정확한 시간은 결정되지 않았습니다\(4.5에서는 아님\).  현재 단계에서는 고객에게 이러한 방침을 전달하여 새로운 WF4 모델로 이동할 수 있는 충분한 시간을 주어야 합니다.  [Microsoft 지원 기간 정책](http://aka.ms/MicrosoftSupportLifecycle)에 따라 이러한 WF 3 형식을 계속 지원할 것입니다.  기존 WF3 응용 프로그램은 .NET 4.5에서 문제 없이 실행되며, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]에서는 신규 및 기존 WF3 기반 솔루션을 지원합니다.  
  
 WF 4.5에서 대체되지 않은 <xref:System.Workflow.Activities.Rules> 네임스페이스의 규칙 관련 형식은 계속 사용됩니다.  
  
 응용 프로그램을 WF 4로 마이그레이션하려는 고객은 MSDN의 [Workflow 4 마이그레이션 지침](http://aka.ms/WF4MigrationGuidance) 기사와 [WF Codeplex](http://aka.ms/WFCodeplex)\(영문\) 사이트의 [WF 4 마이그레이션 키트](http://aka.ms/WF4MigrationKit)\(영문\)에서 도움말을 참조할 수 있습니다.