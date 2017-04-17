---
title: "WF의 런타임 활동 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# WF의 런타임 활동
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]는 지속성 및 종료와 같이 워크플로 런타임의 기능에 액세스하기 위한 여러 시스템 제공 활동을 제공합니다.  
  
|동작|설명|  
|--------|--------|  
|<xref:System.Activities.Statements.Persist>|워크플로가 상태를 유지하도록 명시적으로 요청합니다.|  
|<xref:System.Activities.Statements.TerminateWorkflow>|실행 중인 워크플로 인스턴스를 종료합니다.|  
|<xref:System.Activities.Statements.NoPersistScope>|자식 활동이 유지되지 않도록 하는 컨테이너 활동입니다.|