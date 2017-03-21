---
title: "속성 또는 문자열 이름 (Visual Basic)를 사용 하 여 메서드를 호출 합니다. | Microsoft 문서"
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
- passing operators
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls, strings
- methods [Visual Basic], calling with string names
- calling methods, string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 87af2816ba42e2901c53bec5e9c19f34c676ed5c
ms.lasthandoff: 03/13/2017

---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>문자열 이름을 사용하여 속성 또는 메서드 호출(Visual Basic)
대부분의 경우에서 디자인 타임에 개체의 메서드와 속성을 검색 하 고 처리 하는 코드를 작성할 수 있습니다. 그러나 경우에 따라 있습니다 수 알 개체의 속성 및 메서드에 대 한 사전에 없거나 속성을 지정 하거나 런타임에 메서드를 실행 하려면 최종 사용자의 유연성 할 수 있습니다.  
  
## <a name="callbyname-function"></a>CallByName 함수  
 예를 들어, COM 구성 요소에는 연산자를 전달 하 여 사용자가 입력 한 식을 계산 하는 클라이언트 응용 프로그램입니다. 새 연산자를 필요로 하는 구성 요소에 새 함수를 추가할 지속적으로 가정 합니다. 표준 개체 액세스 기술을 사용 하 여를 다시 컴파일해야 하 고 새 연산자를 사용 하기 전에 클라이언트 응용 프로그램을 다시 배포 해야 합니다. 이 방지 하려면 사용할 수는 `CallByName` 응용 프로그램을 변경 하지 않고도 새 연산자를 문자열로 전달 하는 함수입니다.  
  
 `CallByName` 함수는 문자열을 사용 하 여 런타임 시 속성이 나 메서드를 지정할 수 있습니다. 에 대 한 서명 된 `CallByName` 함수는 다음과 같습니다.  
  
 *Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())  
  
 첫 번째 인수 *개체*, 작업할 하려는 개체의 이름을 사용 합니다. *ProcedureName* 인수에는 호출할 메서드 또는 속성 프로시저의 이름을 포함 하는 문자열입니다. *CallType* 인수를 호출 하는 프로시저의 유형을 나타내는 상수입니다: 메서드 (`Microsoft.VisualBasic.CallType.Method`), 속성 읽기 (`Microsoft.VisualBasic.CallType.Get`), 또는 속성 설정 (`Microsoft.VisualBasic.CallType.Set`). *인수* 인수는 선택 항목인 형식의 배열을 받는 `Object` 프로시저에 인수를 포함 하는 합니다.  
  
 사용할 수 있습니다 `CallByName` 하지만 현재 솔루션의 클래스와는 가장 자주 액세스 하는 데 COM 개체 또는 개체에서 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리입니다.  
  
 클래스를 포함 하는 어셈블리에 대 한 참조를 추가 한다고 가정 `MathClass`, 라는 새 함수를 가지는 `SquareRoot`다음 코드에 표시 된 것 처럼:  
  
 [!code-vb[VbVbalrOOP #&53;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 응용 프로그램이 어떤 메서드가 호출 하는 컨트롤 및 해당 인수에 텍스트 상자 컨트롤을 사용할 수 있습니다. 예를 들어 경우 `TextBox1` 식이 평가 되 고, 포함 및 `TextBox2` 는 함수 이름을 입력 하는 데 사용 합니다 수는 다음 코드를 사용 하면 호출에서 `SquareRoot` 의 식에서 함수 `TextBox1`:  
  
 [!code-vb[VbVbalrOOP #&54;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 "64"를 입력 하는 경우 `TextBox1`, "SquareRoot" `TextBox2`, 다음 호출에서 `CallMath` 프로시저, 숫자의 제곱근 `TextBox1` 평가 됩니다. 예제에서 코드에서는 호출 된 `SquareRoot` (필수 인수로 계산 될 식을 포함 하는 문자열 걸림) 작동 하 고 "8" 반환 `TextBox1` (64의 제곱근). 물론 사용자가에 잘못 된 문자열을 입력 하는 경우 `TextBox2`메서드를 대신 속성의 이름을 포함 하는 문자열 또는 메서드가 추가적인 필수 인수 있으면 런타임에 오류가 발생 하는 경우. 사용 하는 경우 강력한 오류 처리 코드를 추가 해야 `CallByName` 사항이 나 기타 모든 오류를 정확히 예상 하 합니다.  
  
> [!NOTE]
>  동안는 `CallByName` 함수 일부 경우에 유용할 수 있지만, 성능에 미치는 영향에 대해 유용성을 평가 해야-를 사용 하 여 `CallByName` 프로시저를 호출 하는 런타임에 바인딩된 호출 보다 약간 더 느려집니다. 라고 하는 반복 해 서 같은 루프 내부로 함수를 호출 하는 경우 `CallByName` 성능에 심각한 영향을 줄 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A></xref:Microsoft.VisualBasic.Interaction.CallByName%2A>   
 [개체 형식 확인](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
