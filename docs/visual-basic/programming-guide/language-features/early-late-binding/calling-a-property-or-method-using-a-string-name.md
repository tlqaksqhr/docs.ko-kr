---
title: 문자열 이름을 사용하여 속성 또는 메서드 호출(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: 76be426049489bb58e50878822c03fa5cd5cca8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>문자열 이름을 사용하여 속성 또는 메서드 호출(Visual Basic)
대부분의 경우에서 디자인 타임에 개체의 메서드와 속성을 검색 하 고 처리 하기 위한 코드를 작성할 수 있습니다. 그러나 경우에 따라 있습니다 모를 수도 개체의 속성 및 메서드에 대 한 사전에 있고 속성을 지정 하거나 실행 시 메서드를 실행 하려면 최종 사용자의 유연성 할 수 있습니다.  
  
## <a name="callbyname-function"></a>CallByName 함수  
 예를 들어 COM 구성 요소는 연산자를 전달 하 여 사용자가 입력 한 식을 계산 하는 클라이언트 응용 프로그램을 고려 합니다. 지속적으로 새 기능에 추가할 새 연산자를 필요로 하는 구성 요소를 가정 합니다. 표준 개체 액세스 기술을 사용 하는 경우 다시 컴파일해야 하 고 새 연산자를 사용 하려면 클라이언트 응용 프로그램을 재배포 해야 합니다. 이 문제를 방지 하려면 사용할 수 있습니다는 `CallByName` 함수를 응용 프로그램을 변경 하지 않고도 새 연산자를 문자열로 전달 합니다.  
  
 `CallByName` 함수는 문자열을 사용 하 여 런타임 시 속성이 나 메서드를 지정할 수 있습니다. 에 대 한 시그니처는 `CallByName` 함수는 다음과 같습니다.  
  
 *결과* = `CallByName`(*개체*, *ProcedureName*, *CallType*, *인수*())  
  
 첫 번째 인수 *개체*, 작업을 수행할 원하는 개체의 이름을 사용 합니다. *ProcedureName* 인수에는 호출할 메서드 또는 속성 프로시저의 이름을 포함 하는 문자열입니다. *CallType* 인수를 호출 하는 프로시저의 종류를 나타내는 상수에는: 메서드 (`Microsoft.VisualBasic.CallType.Method`), 속성 읽기 (`Microsoft.VisualBasic.CallType.Get`), 또는 속성 설정 (`Microsoft.VisualBasic.CallType.Set`). *인수* 인수는 선택 항목인 형식의 배열을 사용 `Object` 프로시저에 인수를 포함 하 합니다.  
  
 사용할 수 있습니다 `CallByName` 에서 개체를 늘리거나 현재 솔루션에 클래스를 가장 많이 사용 하 여 COM 개체에 액세스할 수 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리입니다.  
  
 클래스를 포함 하는 어셈블리에 대 한 참조를 추가 한다고 가정 `MathClass`, 라는 새 함수가 `SquareRoot`다음 코드에 나온 것 처럼:  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 응용 프로그램 제어 호출 되는 메서드 및 해당 인수에 텍스트 상자 컨트롤을 사용할 수 없습니다. 예를 들어 경우 `TextBox1` 계산 되도록 식을 포함 하 고 `TextBox2` 는 함수 이름을 입력 하는 데 사용을 하는 데 다음 코드를 호출는 `SquareRoot` 의 식에서 함수 `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 "64"를 입력 하는 경우 `TextBox1`, "SquareRoot" `TextBox2`, 한 다음 호출에서 `CallMath` 프로시저, 된 숫자의 제곱근 `TextBox1` 평가 됩니다. 예제에서 코드 호출는 `SquareRoot` (사용 하는 필수 인수도 계산 되는 식을 포함 하는 문자열) 작동 하 고 "8" 반환 `TextBox1` (64의 제곱근). 물론:의 잘못 된 문자열을 입력할 경우 `TextBox2`메서드 추가적인 필수 인수가 있으면 런타임에 오류가 발생 하는 경우 문자열에는 메서드 대신 속성의 이름을 포함 합니다. 사용 하는 경우 오류 처리 코드를 추가 해야 `CallByName` 이러한 열 데이터 나 다른 오류를 예상할 수 있습니다.  
  
> [!NOTE]
>  동안는 `CallByName` 함수 일부 경우에 유용할 수 있지만, 성능에 미치는 영향에 대 한 유용성 균형을 맞춰야-를 사용 하 여 `CallByName` 프로시저를 호출 하는 런타임에 바인딩된 호출 보다 약간 더 느려집니다. 반복적으로 호출 되, 예: 루프 내부으로 하는 함수를 호출 하는 경우 `CallByName` 성능에 심각한 영향을 줄 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>  
 [개체 형식 확인](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
