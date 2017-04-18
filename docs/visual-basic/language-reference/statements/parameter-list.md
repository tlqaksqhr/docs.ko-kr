---
title: "매개 변수 목록 (Visual Basic) | Microsoft 문서"
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
- Visual Basic code, procedures
- parameters, Visual Basic
- parameters, lists
- parameter lists
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures, parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
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
ms.openlocfilehash: abadaa8e035bfa4c92acc30ab633d6a7e958676c
ms.lasthandoff: 03/13/2017

---
# <a name="parameter-list-visual-basic"></a>매개 변수 목록(Visual Basic)
프로시저를 호출할 때에 필요한 매개 변수를 지정 합니다. 매개 변수가 여러 개이면 쉼표로 구분 됩니다. 다음은 하나의 매개 변수를 포함 하는 구문은입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a>요소  
 `attributelist`  
 선택적 요소. 이 매개 변수에 적용 되는 특성의 목록입니다. 묶어야는 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").  
  
 `Optional`  
 선택적 요소. 이 매개 변수가 필요 하지 않음을 프로시저가 호출 될 때 지정 합니다.  
  
 `ByVal`  
 선택적 요소. 프로시저 교체 하거나 호출 코드에서 해당 하는 인수를 내부 변수 요소를 다시 할당할 수 없습니다를 지정 합니다.  
  
 `ByRef`  
 선택적 요소. 과정 수 수정 호출 코드에서 내부 변수 요소는 방식으로 호출 코드 자체를 지정 합니다.  
  
 `ParamArray`  
 선택적 요소. 매개 변수 목록의 마지막 매개 변수는 지정 된 데이터 형식의 요소 선택적 배열 임을 지정 합니다. 이 프로시저에는 임의 개수의 인수를 전달 하는 호출 코드가 있습니다.  
  
 `parametername`  
 필수 요소. 매개 변수를 나타내는 로컬 변수의 이름입니다.  
  
 `parametertype`  
 필요한 경우 `Option Strict` 는 `On`합니다. 데이터 형식 인수를 나타내는 지역 변수입니다.  
  
 `defaultvalue`  
 에 필요한 `Optional` 매개 변수입니다. 매개 변수의 데이터 형식으로 계산 되는 모든 상수 또는 상수 식입니다. 형식이 `Object`, 클래스, 인터페이스, 배열 또는 구조를 기본값만 수 또는 `Nothing`합니다.  
  
## <a name="remarks"></a>주의  
 매개 변수는 괄호로 묶어 고 쉼표로 구분 합니다. 데이터 형식과 매개 변수를 선언할 수 있습니다. 지정 하지 않으면 `parametertype`, 기본적으로 `Object`합니다.  
  
 호출 코드에서 프로시저를 호출 할 때 전달 된 *인수* 각 필수 매개 변수를 합니다. 자세한 내용은 참조 [차이 간의 매개 변수 및 인수](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)합니다.  
  
 호출 코드에서 각 매개 변수에 전달 된 인수는 호출 코드의 내부 요소에 대 한 포인터입니다. 이 요소를 *비가변* (상수, 리터럴, 열거형 또는 식)를 변경 하는 모든 코드에 대 한 불가능 합니다. 있으면는 *변수* 요소 (선언 된 변수, 필드, 속성, 배열 요소 또는 구조 요소)를 호출 하는 코드를 변경할 수 있습니다. 자세한 내용은 참조 [수정 간의 차이점 및 수정할 수 없는 인수](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)합니다.  
  
 Variable 요소에 전달 되는 경우 `ByRef`, 프로시저도 변경할 수 있습니다. 자세한 내용은 참조 [차이 사이 값과 참조로 인수를 전달](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **괄호입니다.** 매개 변수 목록을 지정 하면 괄호로 묶을 해야 있습니다. 매개 변수가 없는 경우 빈 목록을 괄호를 여전히 사용할 수 있습니다. 요소는 프로시저는 명확 하 게 설명 하 여 코드의 가독성이 향상 됩니다.  
  
-   **선택적 매개 변수입니다.** 사용 하는 경우는 `Optional` 매개 변수 한정자를 모든 후속 매개 변수 목록에 선택적 및 사용 하 여 선언할 수는 `Optional` 한정자입니다.  
  
     모든 선택적 매개 변수 선언을 제공 해야는 `defaultvalue` 절.  
  
     자세한 내용은 참조 [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)합니다.  
  
-   **매개 변수 배열입니다.** 지정 해야 `ByVal` 에 대 한 한 `ParamArray` 매개 변수입니다.  
  
     함께 사용할 수 없습니다 `Optional` 및 `ParamArray` 동일한 매개 변수 목록입니다.  
  
     자세한 내용은 참조 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)합니다.  
  
-   **전달 메커니즘입니다.** 모든 인수에 대 한 기본 메커니즘은 `ByVal`, 프로시저를 의미 하는 내부 변수 요소를 변경할 수 없습니다. 그러나 요소 참조 형식인 경우 프로시저 수정할 수 내용이 나 기본 개체의 멤버는 교체 또는 개체 자체를 다시 할당할 수 없는 경우에 합니다.  
  
-   **매개 변수 이름입니다.** 매개 변수의 데이터 형식이 배열 인지에 따라 `parametername` 괄호 바로 뒤에 있습니다. 매개 변수 이름에 대 한 자세한 내용은 참조 하십시오. [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `Function` 두 개의 매개 변수를 정의 하는 절차입니다.  
  
 [!code-vb[VbVbalrStatements #&2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
