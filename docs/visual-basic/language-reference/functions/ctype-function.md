---
title: "CType 함수(Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.CType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "식 변환 결과"
  - "명시적 데이터 형식 변환"
  - "CType 함수"
  - "변환, 식"
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# CType 함수(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

식을 지정한 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스로 명시적으로 변환한 결과를 반환합니다.  
  
## 구문  
  
```  
CType(expression, typename)  
```  
  
## 요소  
 `expression`  
 임의의 유효한 식입니다.  `expression` 값이 `typename`에서 허용되는 범위를 벗어나면 Visual Basic에서 예외가 throw됩니다.  
  
 `typename`  
 `Dim` 문의 `As` 절에서 유효한 임의의 식, 즉 임의의 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스 이름입니다.  
  
## 설명  
  
> [!TIP]
>  다음 함수를 사용하여 형식 변환을 수행할 수도 있습니다.  
>   
>  -   특정 데이터 형식으로의 변환을 수행하는 `CByte`, `CDbl` 및 `CInt`와 같은 변환 함수를 입력합니다.  자세한 내용은 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)을\(를\) 참조하십시오.  
> -   [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) 또는 [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) 이러한 연산자에서는 다른 형식에서 상속된 형식 또는 다른 형식을 구현하는 형식을 사용해야 합니다.  `Object` 데이터 형식 사이에서 변환할 때 `CType`보다 약간 더 나은 성능을 제공할 수 있습니다.  
  
 `CType`은 인라인으로 컴파일됩니다. 즉, 변환 코드가 식을 계산하는 코드의 일부입니다.  변환을 수행하기 위해 프로시저를 호출하지 않으므로 코드가 더 빠르게 실행되는 경우도 있습니다.  
  
 `expression`에서 `typename`으로\(예: `Integer`에서 `Date`로\)의 변환이 정의되어 있지 않으면 Visual Basic에서 컴파일 타임 오류 메시지가 표시됩니다.  
  
 런타임에 변환이 실패하면 해당 예외가 throw됩니다.  축소 변환이 실패할 경우에는 <xref:System.OverflowException>이 가장 많이 발생합니다.  변환이 정의되지 않으면 <xref:System.InvalidCastException>이 throw됩니다.  예를 들어, `expression`이 `Object` 형식이고 해당 런타임 형식이 `typename`으로 변환되지 않을 경우에 이러한 결과가 발생합니다.  
  
 `expression` 또는 `typename`의 데이터 형식이 사용자가 정의한 클래스나 구조체이면 해당 클래스나 구조체에 대해 `CType`을 변환 연산자로 정의할 수 있습니다.  이렇게 하면 `CType`은 *오버로드된 연산자* 기능을 합니다.  이때 throw될 수 있는 예외를 비롯하여 클래스나 구조체에 대한 변환 동작을 제어할 수 있습니다.  
  
## 오버로딩  
 `CType` 연산자는 코드 외부에서 정의된 클래스나 구조체에 대해서도 오버로드될 수 있습니다.  그러한 클래스나 구조체와 코드 간의 변환을 수행할 때는 해당 `CType` 연산자의 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을\(를\) 참조하십시오.  
  
## 동적 개체 변환  
 동적 개체의 형식 변환은 <xref:System.Dynamic.DynamicObject.TryConvert%2A> 또는 <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> 메서드를 사용하는 사용자 정의 동적 변환을 통해 수행됩니다.  동적 개체를 사용하여 작업하는 경우 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 메서드를 사용하여 동적 개체를 변환합니다.  
  
## 예제  
 다음 예제에서는 `CType` 함수를 사용하여 식을 `Single` 데이터 형식으로 변환합니다.  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/ctype-function_1.vb)]  
  
 다른 예제를 보려면 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.OverflowException>   
 <xref:System.InvalidCastException>   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Conversion Functions](../../../visual-basic/language-reference/functions/conversion-functions.md)   
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [.NET Framework의 형식 변환](../Topic/Type%20Conversion%20in%20the%20.NET%20Framework.md)