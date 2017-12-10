---
title: "부분 메서드(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 975a86e33eb5744f94cd58efb227bf52eb07c1e8
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="partial-methods-visual-basic"></a>부분 메서드(Visual Basic)
부분 메서드는 개발자가 코드를 사용자 지정 논리를 삽입할 수를 사용 합니다. 일반적으로 코드는 디자이너에서 생성 된 클래스의 일부입니다. 부분 메서드는 코드 생성기에 의해 만들어진 partial 클래스에 정의 된 하 고 변경 된 내용이 알림을 제공 하 여 일반적으로 사용 됩니다. 사용 개발자는 변경에 따른에서 사용자 지정 동작을 지정할 수 있습니다.  
  
 코드 생성기의 디자이너 메서드 서명과 메서드에 하나 이상의 호출을 정의합니다. 그런 다음 개발자는 생성된 된 코드의 동작을 사용자 지정 하는 경우 메서드의 구현을 제공할 수 있습니다. 구현이 제공 되 면 메서드를 호출 하는 컴파일러에 추가적인 성능 오버 헤드 없음 통해 제거 됩니다.  
  
## <a name="declaration"></a>선언  
 키워드를 배치 하 여 부분 메서드의 정의 표시 하는 생성 된 코드 `Partial` 서명 줄의 시작 부분에 있습니다.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 정의는 다음 조건을 충족 해야 합니다.  
  
-   메서드는 이어야 합니다는 `Sub`이 아니라는 `Function`합니다.  
  
-   메서드의 본문 비어 있어야 합니다.  
  
-   액세스 한정자 이어야 합니다. `Private`합니다.  
  
## <a name="implementation"></a>구현  
 구현에서는 주로 채우기로 부분 메서드의 본문에 구성 됩니다. 구현 정의에서 별도 partial 클래스에는 일반적으로 고 생성된 된 코드를 확장 하려는 개발자가 기록 됩니다.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 앞의 예제는 선언의 시그니처를 정확 하 게 복제 되지만 변형이 가능 합니다. 특히, 다른 한정자를 추가할 수와 같은 `Overloads` 또는 `Overrides`합니다. 하나의 `Overrides` 한정자는 허용 됩니다. 메서드 한정자에 대 한 자세한 내용은 참조 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)합니다.  
  
## <a name="use"></a>기능  
 다른 모든를 호출 하는 것 처럼 부분 메서드를 호출 `Sub` 프로시저입니다. 메서드 구현 된 경우 인수 평가 되 고 메서드 본문이 실행 됩니다. 그러나 부분 메서드를 구현 하는 선택적 임을 고려해 야 합니다. 메서드가 구현 되지 않은 경우에이 호출이 아무 효과가 없으며 메서드에 인수로 전달 된 식은 계산 되지 않습니다.  
  
## <a name="example"></a>예제  
 Product.Designer.vb 라는 파일에 정의 된 `Product` 가 있는 클래스는 `Quantity` 속성.  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 Product.vb 라는 파일에 대 한 구현을 제공 `QuantityChanged`합니다.  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 마지막으로, 프로젝트의 Main 메서드를 선언는 `Product` 인스턴스를 초기 값을 제공 합니다. 해당 `Quantity` 속성입니다.  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 이 메시지를 표시 하는 메시지 상자가 나타납니다.  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>참고 항목  
 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [선택적 매개 변수](./optional-parameters.md)  
 [부분](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [LINQ to SQL에서 코드 생성](../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [부분 메서드를 사용 하 여 비즈니스 논리 추가](../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
