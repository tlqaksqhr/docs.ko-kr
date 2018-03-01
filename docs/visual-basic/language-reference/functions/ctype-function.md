---
title: "CType 함수(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d804ce75929592675068fdc434a1ba7429fa5373
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ctype-function-visual-basic"></a>CType 함수(Visual Basic)
명시적으로 지정 된 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스에는 식을 변환한 결과를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
CType(expression, typename)  
```  
  
## <a name="parts"></a>요소  
 `expression`  
 모든 유효한 식입니다. 하는 경우의 값 `expression` 에서 허용 되는 범위를 벗어납니다 `typename`, Visual Basic 예외를 throw 합니다.  
  
 `typename`  
 유효한 모든 식은 `As` 절에는 `Dim` 문, 즉, 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스의 이름입니다.  
  
## <a name="remarks"></a>설명  
  
> [!TIP]
>  또한 형식 변환을 수행 하려면 다음 함수를 사용할 수 있습니다.  
>   
>  -   변환 함수를 같은 입력 `CByte`, `CDbl`, 및 `CInt` 특정 데이터 형식으로의 변환을 수행 하는 합니다. 자세한 내용은 참조 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.  
> -   [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 또는 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)합니다. 이러한 연산자는 한 형식에서 상속 하거나 다른 형식을 구현에 필요 합니다. 보다 약간 더 나은 성능을 제공 하 `CType` 에서 변환 하는 경우는 `Object` 데이터 형식입니다.  
  
 `CType`즉, 형식 변환 식을 계산 하는 코드의 일부 컴파일된 인라인으로가 됩니다. 경우에 따라 코드가 더 빠르게 실행에서 변환을 수행할 호출 되므로 프로시저가 없습니다.  
  
 정의 된 변환이 없는 경우 `expression` 를 `typename` (예:에서 `Integer` 를 `Date`), Visual Basic 컴파일 타임 오류 메시지를 표시 합니다.  
  
 런타임에 변환에 실패 하면 해당 예외가 throw 됩니다. 축소 변환에 실패 하면는 <xref:System.OverflowException> 은 가장 일반적인 결과입니다. 정의 되지 않으면 경우는 <xref:System.InvalidCastException> throw 합니다. 예를 들어 이러한 경우 `expression` 유형의 `Object` 해당 런타임 형식에는 변환 되지 않습니다 및 `typename`합니다.  
  
 데이터 형식이 `expression` 또는 `typename` 클래스 또는 구조를 정의 했으면 정의할 수 있습니다 `CType` 해당 클래스 또는 변환 연산자와 구조에서. 이렇게 하면 `CType` 프록시로 *오버 로드 된 연산자*합니다. 이 작업을 수행 하는 경우에 클래스 또는 구조체를 throw 할 수 있는 예외를 포함 하 여에서 변환 하 고 동작을 제어할 수 있습니다.  
  
## <a name="overloading"></a>오버로딩  
 `CType` 연산자 클래스 또는 코드 외부에 정의 된 구조체에 오버 로드 될 수도 있습니다. 코드로 변환 되 면 해당 클래스 또는 구조에서 사용할의 동작을 알고 있어야 해당 `CType` 연산자입니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="converting-dynamic-objects"></a>동적 개체 변환  
 동적 개체의 형식 변환을 사용 하는 사용자 지정 동적 변환을 수행한는 <xref:System.Dynamic.DynamicObject.TryConvert%2A> 또는 <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> 메서드. 동적 개체를 사용 하는 경우 사용 된 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 동적 개체를 변환 하는 메서드입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `CType` 식으로 변환 하는 함수는 `Single` 데이터 형식입니다.  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 추가 예제를 참조 하십시오. [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.OverflowException>  
 <xref:System.InvalidCastException>  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [변환 함수](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [.NET Framework의 형식 변환](../../../standard/base-types/type-conversion.md)
