---
title: Handles 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Handles
- vb.Handles
helpviewer_keywords:
- Handles keyword [Visual Basic]
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
ms.openlocfilehash: 15ce6a25aa5f403a2e55beb57b3693095743e52f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="handles-clause-visual-basic"></a>Handles 절(Visual Basic)
지정된 이벤트를 처리하는 프로시저를 선언합니다.  
  
## <a name="syntax"></a>구문  
  
```  
proceduredeclaration Handles eventlist  
```  
  
## <a name="parts"></a>요소  
 `proceduredeclaration`  
 이벤트를 처리할 프로시저에 대한 `Sub` 프로시저 선언입니다.  
  
 `eventlist`  
 처리할 `proceduredeclaration`에 대한 이벤트 목록으로, 쉼표로 구분합니다. 이벤트는 현재 클래스에 대한 기본 클래스 또는 `WithEvents` 키워드를 사용하여 선언된 개체에 의해 발생해야 합니다.  
  
## <a name="remarks"></a>설명  
 프로시저 선언의 끝에서 `Handles` 키워드를 사용하여 `WithEvents` 키워드로 선언된 개체 변수에 의해 발생된 이벤트를 처리합니다. `Handles` 키워드는 파생 클래스에서 기본 클래스의 이벤트를 처리하는 데도 사용할 수 있습니다.  
  
 `Handles` 키워드와 `AddHandler` 문 모두 특정 프로시저에서 특정 이벤트를 처리하도록 지정하는 데 사용할 수 있지만 차이가 있습니다. 특정 이벤트를 처리하도록 지정하는 프로시저를 정의할 때 `Handles` 키워드를 사용합니다. `AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다. 자세한 내용은 참조 [AddHandler 문](../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다.  
  
 사용자 지정 이벤트의 경우 응용 프로그램은 이벤트 처리기로 프로시저를 추가할 때 이벤트의 `AddHandler` 접근자를 호출합니다. 사용자 지정 이벤트에 대 한 자세한 내용은 참조 하십시오. [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrEvents#2](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_1.vb)]  
  
 다음 예제에서는 파생 클래스가 `Handles` 문을 사용하여 기본 클래스의 이벤트를 처리하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrEvents#3](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_2.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에 대 한 두 가지 단추 이벤트 처리기는 **WPF 응용 프로그램** 프로젝트.  
  
 [!code-vb[VbVbalrEvents#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_3.vb)]  
  
## <a name="example"></a>예제  
 다음 예제는 이전 예제와 동일합니다. `Handles` 절의 `eventlist`에는 두 단추에 대한 이벤트가 포함되어 있습니다.  
  
 [!code-vb[VbVbalrEvents#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [AddHandler 문](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
 [RaiseEvent 문](../../../visual-basic/language-reference/statements/raiseevent-statement.md)  
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
