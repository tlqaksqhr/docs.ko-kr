---
title: '방법: 차단을 방지하는 사용자 지정 이벤트 선언(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
ms.openlocfilehash: 3cb66aed71195d2fd2335fbd59cc499b3dbf808e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-custom-events-to-avoid-blocking-visual-basic"></a>방법: 차단을 방지하는 사용자 지정 이벤트 선언(Visual Basic)
이 하나의 이벤트 처리기는 후속 이벤트 처리기를 차단 하지 중요 한 몇 가지 경우가 있습니다. 사용자 지정 이벤트의 이벤트 처리기를 비동기적으로 호출 하려면 이벤트를 허용 합니다.  
  
 기본적으로는 이벤트 선언에 대 한 지원 저장소 필드는 멀티 캐스트 대리자 모든 이벤트 처리기를 순차적입니다. 이 하나의 처리기는 완료 하는 데 시간이 오래 걸리면, 차단할 다른 처리기 완료 될 때까지 것을 의미 합니다. (때 이벤트 처리기 긴 또는 잠재적인 차단 작업이 수행 해야 합니다.)  
  
 Visual Basic에서 제공 하는 이벤트의 기본 구현을 사용 하는 대신 이벤트 처리기를 비동기적으로 실행 하는 사용자 지정 이벤트를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 이 예제는 `AddHandler` 의 각 처리기에 대 한 대리자를 추가 하는 접근자는 `Click` 이벤트를는 <xref:System.Collections.ArrayList> 에 저장 된는 `EventHandlerList` 필드입니다.  
  
 발생 시키는 경우 코드는 `Click` 이벤트는 `RaiseEvent` 비동기적으로 사용 하 여 모든 이벤트 처리기 대리자를 호출 하는 접근자는 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> 메서드. 해당 메서드는 작업자 스레드에서 각 처리기를 호출 하 고 즉시 반환 하므로 처리기 서로 차단할 수 없습니다.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-avoid-blocking_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.ArrayList>  
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>  
 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [방법: 메모리를 절약하는 사용자 지정 이벤트 선언](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
