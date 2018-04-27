---
title: 개체 형식 확인(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6d24be68ea4a9872f8f4fe89c1aabb943fbcb91
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="determining-object-type-visual-basic"></a>개체 형식 확인(Visual Basic)
일반 개체 변수 (즉, 변수 선언으로 `Object`) 모든 클래스의 개체를에서 포함할 수 있습니다. 형식의 변수를 사용 하는 경우 `Object`, 개체의 클래스를 기반으로 하는 다른 작업을 수행 해야 할 수; 예를 들어 일부 개체 수 지원 하지 않습니다는 특정 속성 또는 메서드. Visual Basic에서 개체 변수에 저장 됩니다 개체의 유형을 결정 하는 두 가지 방법을 제공:는 `TypeName` 함수 및 `TypeOf...Is` 연산자입니다.  
  
## <a name="typename-and-typeofis"></a>TypeName 및 TypeOf... 은  
 `TypeName` 함수는 문자열을 반환 하 고 다음 코드 조각에 나와 있는 것 처럼 개체의 클래스 이름을 저장 하거나 표시 해야 할 때이 가장 좋습니다.  
  
 [!code-vb[VbVbalrOOP#92](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_1.vb)]  
  
 `TypeOf...Is` 연산자는 개체의 형식을 테스트 하기 위한 최상의 방법 사용 하 여 해당 하는 문자열 비교 보다 훨씬 빠릅니다 `TypeName`합니다. 다음 코드 조각에서는 `TypeOf...Is` 내는 `If...Then...Else` 문:  
  
 [!code-vb[VbVbalrOOP#93](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_2.vb)]  
  
 주의할이 여기 예정입니다. `TypeOf...Is` 연산자는 반환 `True` 개체가 특정 유형의 또는 특정 형식에서 파생 되는 경우. Visual Basic을 사용한 수행 거의 모든 작업, 문자열 및 정수 같은 개체로 간주 일반적으로 일부 요소를 포함 하는 개체를 포함 됩니다. 이러한 개체에서 파생 되 고 메서드를 상속 <xref:System.Object>합니다. 전달 될 때는 `Integer` 를 평가 하 고 `Object`, `TypeOf...Is` 연산자는 반환 `True`합니다. 다음 예제에서는 보고 하는 매개 변수 `InParam` 둘는 `Object` 및 `Integer`:  
  
 [!code-vb[VbVbalrOOP#94](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_3.vb)]  
  
 다음 예제에서는 둘 다 사용 하 여 `TypeOf...Is` 및 `TypeName` 에서 전달 된 개체의 형식을 확인 하는 `Ctrl` 인수. `TestObject` 프로시저 호출 `ShowType` 세 가지 다른 종류의 컨트롤을 사용 합니다.  
  
#### <a name="to-run-the-example"></a>예제를 실행하려면  
  
1.  새 Windows 응용 프로그램 프로젝트를 만들고 추가 <xref:System.Windows.Forms.Button> 컨트롤은 <xref:System.Windows.Forms.CheckBox> 컨트롤 및 <xref:System.Windows.Forms.RadioButton> 컨트롤을 폼입니다.  
  
2.  폼에 단추에서 호출 된 `TestObject` 프로시저입니다.  
  
3.  폼에 다음 코드를 추가 합니다.  
  
     [!code-vb[VbVbalrOOP#95](../../../../visual-basic/misc/codesnippet/VisualBasic/determining-object-type_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Information.TypeName%2A>  
 [문자열 이름을 사용하여 속성 또는 메서드 호출](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)  
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [If...Then...Else 문](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [String 데이터 형식](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Integer 데이터 형식](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
