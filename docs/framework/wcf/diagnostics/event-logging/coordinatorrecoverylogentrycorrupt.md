---
title: "CoordinatorRecoveryLogEntryCorrupt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# CoordinatorRecoveryLogEntryCorrupt
Id: 139  
  
 심각도: 오류  
  
 범주: TransactionBridge  
  
## 설명  
 이 이벤트는 코디네이터 복구 로그 항목이 손상되어 deserialize할 수 없음을 나타냅니다.이 오류로 인해 데이터가 손실될 수 있습니다.이벤트에는 트랜잭션 ID, 복구 데이터\(Base64 인코딩\), 예외, 프로세스 이름 및 프로세스 ID가 표시됩니다.  
  
## 참고 항목  
 [이벤트 로깅](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)   
 [이벤트 일반 참조](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)