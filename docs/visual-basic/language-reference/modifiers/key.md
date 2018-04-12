---
title: Key(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 20dbe4e67fb3e415ba0202555ace7fd5afed68d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="key-visual-basic"></a>Key(Visual Basic)
`Key` 키워드를 사용 하면 익명 형식의 속성에 대 한 동작을 지정할 수 있습니다. 전용 속성으로 지정 하는 키 속성이 익명 형식 인스턴스, 또는 계산의 해시 코드 값 사이의 같음 테스트에 참여 합니다. 키 속성의 값을 변경할 수 없습니다.  
  
 키워드를 배치 하 여 키 속성으로 익명 형식의 속성을 지정 `Key` 초기화 목록에서 해당 선언 앞에 있습니다. 다음 예에서 `Airline` 및 `FlightNo` 은 키 속성이 있지만 `Gate` 않습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 직접 상속 하는 새로운 무명 형식 만들어지면 <xref:System.Object>합니다. 컴파일러는 세 가지 상속 된 멤버를 재정의: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, 및 <xref:System.Object.ToString%2A>합니다. 에 대 한 생성 되는 재정의 코드 <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A> 키 속성에 기반 합니다. 형식에 키 속성이 없는 경우 <xref:System.Object.GetHashCode%2A> 및 <xref:System.Object.Equals%2A> 재정의 되지 않습니다.  
  
## <a name="equality"></a>같음  
 동일한 유형의 인스턴스인 경우 및 해당 키 속성의 값이 같으면 두 익명 형식의 인스턴스가 동일한 지 합니다. 다음 예에서 `flight2` 같으면 `flight1` 이전 예제에서 익명 같은 인스턴스 되기 때문에 형식을 가집니다 일치 하는 키 속성의 값입니다. 그러나 `flight3` 과 같지 않은 `flight1` 키 속성에 대해 다른 값을 있기 때문에 `FlightNo`합니다. 인스턴스 `flight4` 가 동일한 형식이 아닌 `flight1` 있으므로 키 속성으로 다른 속성을 지정 합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 키가 아닌 속성만, 이름, 형식, 순서 및 값에 동일한 두 인스턴스가 선언 된 두 인스턴스가 같지 않습니다. 키 속성이 없는 인스턴스 자체에 같습니다.  
  
 동일한 익명 형식의 인스턴스는 두 익명 형식 인스턴스는 조건에 대 한 자세한 내용은 참조 [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.  
  
## <a name="hash-code-calculation"></a>해시 코드 계산  
 마찬가지로 <xref:System.Object.Equals%2A>, 해시 함수에 정의 된 <xref:System.Object.GetHashCode%2A> 익명 형식을 기반으로 형식의 키 속성에 대 한 합니다. 다음 예제에서는 키 속성 및 해시 간의 상호 작용 코드 값을 보여 줍니다.  
  
 모든 키 속성에 대 한 동일한 값이 있는 익명 형식의 인스턴스는 키가 아닌 속성과 일치 하는 값을 포함 하지 않는 동일한 해시 코드 값을 가집니다. 다음 문은 반환 `True`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 하나 이상의 키 속성에 대 한 다른 값이 있는 익명 형식의 인스턴스는 다른 해시 코드 값을 가집니다. 다음 문은 반환 `False`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 키 속성으로 다른 속성을 지정 하는 익명 형식 인스턴스는 동일한 형식의 인스턴스 않습니다. 이름 및 모든 속성의 값이 동일한 경우에 다른 해시 코드 값을 가진 것입니다. 다음 문은 반환 `False`합니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a>읽기 전용 값  
 키 속성의 값을 변경할 수 없습니다. 예를 들어 `flight1` 앞의 예제에는 `Airline` 및 `FlightNo` 필드는 읽기 전용 하지만 `Gate` 변경할 수 있습니다.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [익명 형식 정의](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [방법: 익명 형식 선언에서 속성 이름 및 형식 유추](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
