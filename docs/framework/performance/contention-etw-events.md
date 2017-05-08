---
title: "경합 ETW 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "경합 이벤트[.NET Framework]"
  - "ETW, 경합 이벤트(CLR)"
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# 경합 ETW 이벤트
경합 이벤트는 <xref:System.Threading.Monitor?displayProperty=fullName> 잠금에 대한 경합 또는 런타임에서 사용하는 네이티브 잠금에 대한 경합이 있을 때마다 발생합니다.  경합은 다른 스레드가 잠금을 차지하고 있는 동안 스레드가 잠금을 기다리고 있을 때를 발생합니다.  
  
 다음 표에서는 경합 이벤트가 발생하는 키워드 및 경합 이벤트의 수준을 보여 줍니다. 자세한 내용은 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하십시오.  
  
|이벤트를 발생시키는 키워드|수준|  
|--------------------|--------|  
|`ContentionKeyword`\(0x4000\)|Informational \(4\)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|Event|이벤트 ID|발생하는 경우|  
|-----------|------------|-------------|  
|`ContentionStart_V1`|81|경합이 시작됩니다.  이 이벤트에는 스레드가 잠금을 확보하기 위해 기다리기 전의 회전 시간이 포함되지 않습니다. 스레드가 잠금을 확보하기 위해 기다릴 때만 발생합니다.|  
|`ContentionStop`|81|경합이 종료됩니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|-----------|------------|--------|  
|Flags|win:UInt8|관리의 경우 0, 네이티브의 경우 1입니다.|  
|ClrInstanceID|win:UInt16|CLR 인스턴스의 고유 ID입니다.|  
  
## 참고 항목  
 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)