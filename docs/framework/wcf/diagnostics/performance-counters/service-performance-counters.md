---
title: "서비스 성능 카운터 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 서비스 성능 카운터
서비스 성능 카운터는 서비스 동작을 전반적으로 측정하며 전체 서비스 성능을 진단하는 데 사용할 수 있습니다.이러한 카운터는 성능 모니터\(Perfmon.exe\)에서 볼 때 `ServiceModelService 4.0.0.0` 성능 개체 아래에 있습니다.인스턴스 이름은 다음 패턴으로 지정됩니다.  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 카운터 인스턴스 이름이 최대 길이를 초과하면 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]는 인스턴스 이름 부분을 해시 값으로 바꿉니다.  
  
## 참고 항목  
 [성능 카운터](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)