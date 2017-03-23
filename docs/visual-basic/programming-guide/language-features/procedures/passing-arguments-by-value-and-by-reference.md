---
title: "참조 (Visual Basic) 및 값으로 인수를 전달 | Microsoft 문서"
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
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- passing arguments, by value or by reference
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing, by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
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
ms.openlocfilehash: 56d1ceba14020ca7f3dc750c2318efd3e9586af0
ms.lasthandoff: 03/13/2017

---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a>값 및 참조로 인수 전달(Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 프로시저에 인수를 전달할 수 있습니다 *값별로* 또는 *참조에 의해*합니다. 이 이라고는 *전달 메커니즘*, 프로시저 내부에서 호출 코드의 인수로 사용 하는 프로그래밍 요소를 수정할 수 있는지 여부를 결정 하 고 있습니다. 지정 하 여 각 매개 변수에 대해 전달 메커니즘을 결정 하는 프로시저 선언에서 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드입니다.  
  
## <a name="distinctions"></a>차이점  
 프로시저에 인수를 전달 하는 경우에 몇 가지 다른 차이점 서로 상호 작용을 고려해 야 합니다.  
  
-   기본 프로그래밍 요소를 수정할 수 있는지 여부  
  
-   인수 자체를 수정할 수 있는지 여부  
  
-   값별 또는 참조로 인수 전달 되 고 있는지 여부  
  
-   값 형식 또는 참조 형식 인수 데이터 형식 인지  
  
 자세한 내용은 참조 [수정 간의 차이점 및 수정할 수 없는 인수](./differences-between-modifiable-and-nonmodifiable-arguments.md) 및 [차이 사이 값과 참조로 인수를 전달](./differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.  
  
## <a name="choice-of-passing-mechanism"></a>전달 메커니즘의 선택  
 각 인수에 대해 신중 하 게 전달 메커니즘을 선택 해야 합니다.  
  
-   **보호**합니다. 두 전달 메커니즘 중 하나를 선택할 가장 중요 한 조건이 변경 하는 변수를 호출 합니다. 인수를 전달 `ByRef` 프로시저가 해당 인수를 통해 호출 코드에 값을 반환할 수는 있습니다. 인수를 전달 `ByVal` 변수는 프로시저에 의해 변경 되지 않도록 보호 하는지 됩니다.  
  
-   **성능**합니다. 전달 메커니즘은 코드의 성능에 영향을 줄 수, 있지만 차이 일반적으로 중요 하지 않습니다. 이 한 가지 예외는 전달 되는 값 형식 `ByVal`합니다. 이 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 인수의 전체 데이터 내용을 복사 합니다. 따라서 구조체와 같은 큰 값 형식에 대해 수 전달 하는 것이 효율적 `ByRef`합니다.  
  
     참조 형식에 대 한 데이터에 대 한 포인터만 복사 된 (4 바이트 32 비트 플랫폼에서는 64 비트 플랫폼에서 8 바이트)입니다. 따라서 형식의 인수를 전달할 수 있습니다 `String` 또는 `Object` 성능 영향을 주지 않고 값입니다.  
  
## <a name="determination-of-the-passing-mechanism"></a>전달 메커니즘의 결정  
 각 매개 변수에 대해 전달 메커니즘을 지정 하는 프로시저 선언 합니다. 재정의할 수 없습니다. 호출 하는 코드는 `ByVal` 메커니즘입니다.  
  
 매개 변수가 선언 된 경우 `ByRef`, 호출 코드 하는 메커니즘을 강제할 수 `ByVal` 인수 이름에서에서 괄호로 묶어 호출에서 합니다. 자세한 내용은 참조 [하는 방법: 인수가 값으로 전달 되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)합니다.  
  
 대화 상자에서 기본 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 값으로 인수를 전달 하는 것입니다.  
  
## <a name="when-to-pass-an-argument-by-value"></a>값으로 인수를 전달 하는 경우  
  
-   인수를 내부 호출 코드 요소가 수정할 수 없는 요소는 해당 매개 변수를 선언 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다. 코드 없이 수정할 수 없는 요소 값을 변경할 수 있습니다.  
  
-   기본 요소는 수정할 수 있도록 해당 값을 변경 하는 절차를 원하지 않는 표시 되지만 매개 변수를 선언 `ByVal`합니다. 호출 코드에만 값으로 전달 하는 수정 가능한 요소 값을 변경할 수 있습니다.  
  
## <a name="when-to-pass-an-argument-by-reference"></a>참조로 인수를 전달 하는 경우  
  
-   프로시저 호출 코드에서 요소를 반드시 변경 해야 하는 경우 해당 매개 변수를 선언 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다.  
  
-   코드의 올바르게 실행 되는 호출 코드에서 해당 요소를 변경 하는 절차에 따라 달라 지, 매개 변수를 선언 `ByRef`합니다. 값으로 전달 하는 경우 또는 호출 하는 코드를 재정의 하는 경우는 `ByRef` 인수를 괄호로 묶어 전달 메커니즘 프로시저 호출에 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 값으로 인수를 전달 하는 시기 및 참조로 전달 하는 경우를 보여 줍니다. 프로시저 `Calculate` 둘 다는 `ByVal` 및 `ByRef` 매개 변수입니다. 이자율을 지정 된 `rate`, 금액의 합계와 `debt`, 프로시저의 작업에 대 한 새 값을 계산 하는 `debt` 이자의 원래 값을 적용 한 결과인 `debt`합니다. 때문에 `debt` 는 `ByRef` 매개 변수를 새 합계에 해당 하는 호출 코드에서 인수 값에 반영 됩니다 `debt`합니다. 매개 변수 `rate` 는 `ByVal` 매개 변수 때문에 `Calculate` 값을 변경 해야 합니다.  
  
### <a name="code"></a>코드  
 [!code-vb[VbVbcnProcedures #&74;](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)   
 [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md)   
 [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [방법: 인수가 값으로 전달 되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)   
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
