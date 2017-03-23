---
title: "ByRef&quot; 매개 변수 값을 복사 &quot;&lt;parametername&gt;&quot;일치 하는 인수에 다시 좁힐 형식에서 &quot;&lt;typename1&gt;&quot;를 입력 하 고&quot;&lt;typename2&gt;&quot; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
dev_langs:
- VB
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
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
ms.openlocfilehash: 84574006b2e2ccc669fdd83ebfb6eec06b00f041
ms.lasthandoff: 03/13/2017

---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a>ByRef' 매개 변수 값을 복사 '&lt;parametername&gt;'일치 하는 인수에 다시 좁힐 형식에서 '&lt;typename1&gt;'를 입력 하 고'&lt;typename2&gt;'
해당 매개 변수 형식으로 확장 되는 인수와 함께 프로시저를 호출 하 고 축소 하는 인수에 매개 변수에서 변환 합니다.  
  
 클래스 또는 구조체를 정의하는 경우 해당 클래스 또는 구조체 형식을 다른 형식으로 변환하는 변환 연산자를 하나 이상 정의할 수 있습니다. 다른 형식을 클래스 또는 구조체 형식으로 다시 변환하는 역방향 변환 연산자를 정의할 수도 있습니다. 프로시저 호출에서 클래스 또는 구조체 형식을 사용할 때 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 이러한 변환 연산자를 사용 하 여 인수 형식을 해당 매개 변수의 형식으로 변환할 수 있습니다.  
  
 인수를 전달 하는 경우 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 로컬 변수에 대 한 참조를 전달 하는 대신 프로시저에 인수 값을 복사 합니다. 이 경우, 프로시저에서 반환 하는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 지역 변수 값은 호출 코드에서 인수에 다시 복사 해야 합니다.  
  
 `ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다. 그러나 형식이 서로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 양방향으로 변환 해야 합니다. 클래스 또는 구조체 형식, 형식 중 하나 이면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 하 고 다른 형식에서 변환 해야 합니다. 이러한 변환 중 하나은 확대 하는 경우 역방향 변환 축소 될 수 있습니다.  
  
 **오류 ID:** BC32053  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   따라서 프로시저 매개 변수로 동일한 형식의 호출 인수를 가능 하면 사용 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 변수와 필요 하지 않습니다.  
  
-   인수로 사용 하 여 프로시저를 호출 하는 경우 형식 매개 변수 형식과 다를 수 있지만 매개 변수를 정의 호출 인수에 값을 반환할 필요가 없습니다 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 대신 `ByRef`합니다.  
  
-   호출 인수에 값을 반환 해야 하는 경우로 역방향 변환 연산자 정의 [Widening](../../../visual-basic/language-reference/modifiers/widening.md), 가능한 경우.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [프로시저 매개 변수 및 인수](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [값 및 참조로 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
