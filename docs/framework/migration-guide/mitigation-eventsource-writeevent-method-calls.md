---
title: "완화: EventSource.WriteEvent 메서드 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 270f89183bced5d07598b1731f18acf90ec9715a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-eventsourcewriteevent-method-calls"></a>완화: EventSource.WriteEvent 메서드 호출
[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 은 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 에서 파생된 클래스의 ETW 이벤트 메서드와 기본 클래스의 <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> 메서드 간 계약을 적용합니다. ETW 이벤트 메서드는 <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> 메서드에 이벤트 ID 및 이벤트 메서드에 전달된 동일한 인수를 순서대로 전달해야 합니다.  
  
## <a name="impact"></a>영향  
 다음과 같은 방식으로 정의된 ETW 이벤트 메서드는 계약을 중단합니다.  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message, "-");  
}  
```  
  
 이 계약을 위반하면 <xref:System.IndexOutOfRangeException> 개체가 프로세스에서 <xref:System.Diagnostics.Tracing.EventListener> 데이터를 읽는 경우 런타임에 <xref:System.Diagnostics.Tracing.EventSource> 예외가 발생합니다.  
  
 이 ETW 이벤트 메서드에 대한 정의는 다음 패턴을 따라야 합니다.  
  
```  
[Event(2, Level = EventLevel.Informational)]  
public void Info2(string message)  
{  
   base.WriteEvent(2, message);  
}  
```  
  
## <a name="mitigation"></a>완화  
 필수 패턴에 맞게 기존 코드를 수정해야 합니다.  
  
 <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> 메서드를 호출하기 위한 두 개의 메서드를 다음과 같이 정의하여 변경해야 하는 코드의 양을 최소화할 수 있습니다.  
  
```  
[NonEvent]  
public void Info2(string message)  
{  
   Info2Internal(message, "-");  
}  
  
public void Info2Internal(string message, string prefix)  
{  
   WriteEvent(2, message, prefix);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 변경 내용](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

