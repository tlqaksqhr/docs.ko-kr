---
title: "스택 ETW 이벤트 | Microsoft Docs"
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
  - "ETW, 스택 이벤트(CLR)"
  - "스택 이벤트[.NET Framework]"
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# 스택 ETW 이벤트
이 스택 이벤트는 이벤트가 발생한 후에 스택 추적을 생성하기 위해 다른 이벤트와 함께 사용되어야 합니다.  런타임 공급자가 사용될 때 기록됩니다.  다른 런타임 이벤트가 발생할 때마다 발생하기 때문에 빈도가 매우 높은 이벤트입니다.  따라서 이 이벤트를 사용할 때는 주의하는 것이 좋습니다.  
  
 다음 표에서는 키워드 및 수준을 보여 줍니다. 자세한 내용은 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하십시오.  
  
|이벤트를 발생시키는 키워드|수준|  
|--------------------|--------|  
|`StackKeyword`\(0x40000000\)|LogAlways\(0\)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|Event|이벤트 ID|발생하는 경우|  
|-----------|------------|-------------|  
|`CLRStackWalk`|82|이벤트 이후에 스택 추적을 생성하기 위해 다른 이벤트와 함께 발생합니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|-----------|------------|--------|  
|ClrInstanceID|win:Uint16|고유한 런타임 식별자입니다.|  
|Reserved1|win:UInt8|예약됨.|  
|Reserved2|win:UInt8|예약됨.|  
|FrameCount|win:UInt32|스택 추적의 프레임 수입니다.|  
|스택|win:Pointer|명령 포인터의 열입니다.|  
  
## 참고 항목  
 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)