---
title: "예외가 throw된 V1 ETW 이벤트 | Microsoft Docs"
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
  - "ETW, ExceptionThrown_V1 이벤트(CLR)"
  - "ExceptionThrown_V1 이벤트[.NET Framework]"
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
caps.latest.revision: 6
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 6
---
# 예외가 throw된 V1 ETW 이벤트
이 이벤트는 throw된 예외와 관련된 정보를 캡처합니다.  
  
 다음 표에서는 이 이벤트가 발생하는 키워드 및 이벤트 수준을 보여 줍니다. 자세한 내용은 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하십시오.  
  
|이벤트를 발생시키는 키워드|수준|  
|--------------------|--------|  
|`ExceptionKeyword`\(0x8000\)|경고 \(2\)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|Event|이벤트 ID|발생하는 경우|  
|-----------|------------|-------------|  
|`ExceptionThrown_V1`|80|관리되는 예외가 throw됩니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|-----------|------------|--------|  
|예외 형식|win:UnicodeString|`System.NullReferenceException`과 같은 예외 형식입니다.|  
|Exception Message|win:UnicodeString|실제 예외 메시지입니다.|  
|EIPCodeThrow|win:Pointer|예외가 발생한 명령 포인터입니다.|  
|ExceptionHR|win:UInt32|Exception [HRESULT](http://go.microsoft.com/fwlink/?LinkId=179679).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException\(Visual Basic 설명서에서 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md) 참조\)<br /><br /> 0x02: IsNestedException<br /><br /> 0x04: IsRethrownException<br /><br /> 0x08: IsCorruptedStateException\(프로세스 상태가 손상되었음을 나타냄. MSDN에서 [Handling Corrupted State Exceptions](http://go.microsoft.com/fwlink/?LinkId=179681)참조\)<br /><br /> 0x10: IsCLSCompliant\(<xref:System.Exception>에서 파생된 예외는 CLS 규격이고, 그렇지 않은 경우에는 CLS 규격이 아님\)|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스의 고유 ID입니다.|  
  
## 참고 항목  
 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)