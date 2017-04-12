---
title: "방법: (Visual Basic) 차단을 방지 하는 사용자 지정 이벤트 선언 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34b222bdbfdae0673b7150c220ca477b7e286dda
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>방법: 차단을 방지하는 사용자 지정 이벤트 선언(Visual Basic)
이 한 이벤트 처리기를 다음 이벤트 처리기를 차단 하지 중요 한 몇 가지 경우가 있습니다. 사용자 지정 이벤트를 이벤트의 이벤트 처리기를 비동기적으로 호출할 수 있습니다.  
  
 이벤트 선언에 대 한 지원 저장소 필드는 기본적으로 모든 이벤트 처리기를 순차적으로 결합 하는 멀티 캐스트 대리자는 합니다. 이 하나의 처리기를 완료 하는 데 시간이 오래 걸리면, 다른 처리기 때까지 차단 완료 된 것을 의미 합니다. (때 이벤트 처리기 긴 또는 잠재적인 차단 작업이 수행 되지 해야 합니다.)  
  
 Visual Basic에서 제공 하는 이벤트의 기본 구현을 사용 하 여, 대신 이벤트 처리기를 비동기적으로 실행 하는 사용자 지정 이벤트를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제는 `AddHandler` 의 각 처리기에 대 한 대리자를 추가 하는 접근자는 `Click` 이벤트를는 <xref:System.Collections.ArrayList>에 저장 된는 `EventHandlerList` 필드.</xref:System.Collections.ArrayList>  
  
 발생 시키는 경우 코드는 `Click` 이벤트는 `RaiseEvent` 비동기적으로 사용 하 여 모든 이벤트 처리기 대리자를 호출 하는 접근자는 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>메서드.</xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> 이 메서드는 작업자 스레드에서 각 처리기를 호출 하 고 즉시 반환 하므로 처리기 서로 차단할 수 없습니다.  
  
 [!code-vb[VbVbalrEvents #&27;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.ArrayList></xref:System.Collections.ArrayList>   
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A></xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>   
 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [방법: 메모리를 절약하는 사용자 지정 이벤트 선언](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
