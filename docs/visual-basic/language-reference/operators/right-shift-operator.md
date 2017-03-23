---
title: "&gt;&gt; Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.>>"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operator>>"
  - ">> operator [Visual Basic]"
  - "bit shift operators"
  - "operator >>"
  - "right shift operators"
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# &gt;&gt; Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

비트 패턴에 대해 산술 오른쪽 시프트 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = pattern >> amount  
```  
  
## 요소  
 `result`  
 필수 요소.  정수 숫자 값입니다.  비트 패턴을 이동한 결과입니다.  데이터 형식은 `pattern`의 형식과 같습니다.  
  
 `pattern`  
 필수 요소.  정수 숫자 식입니다.  이동할 비트 패턴입니다.  데이터 형식은 정수 계열 형식\(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` 또는 `ULong`\)이어야 합니다.  
  
 `amount`  
 필수 요소.  숫자 식입니다.  비트 패턴을 이동할 비트 수입니다.  데이터 형식은 `Integer`이거나 `Integer`로 확장되어야 합니다.  
  
## 설명  
 산술 시프트 연산은 순환되지 않습니다. 즉, 한 쪽 끝에서 이동하여 빠져나가는 비트가 다른 쪽 끝으로 다시 들어가지 않습니다.  산술 오른쪽 시프트 연산에서는 맨 오른쪽 비트 위치를 벗어나 이동하는 비트는 무시되고 맨 왼쪽\(부호\) 비트는 왼쪽의 비워진 비트 위치로 전파됩니다.  즉, `pattern`이 음수 값을 가지면 비워진 위치는 1로 설정되고, 양수 값을 가지면 0으로 설정됩니다.  
  
 데이터 형식 `Byte`, `UShort`, `UInteger` 및 `ULong`은 부호 없는 형식이므로 전파할 부호 비트가 없습니다.  `pattern`이 부호 없는 형식이면 비워진 위치는 항상 0으로 설정됩니다.  
  
 결과에 포함될 수 있는 비트 수보다 더 많은 횟수가 이동되는 것을 막기 위해 Visual Basic에서는 `pattern`의 데이터 형식에 해당하는 크기 마스크를 사용하여 `amount`의 값을 마스크합니다.  이들 값의 이항 AND를 수행한 결과가 이동할 비트 수로 사용됩니다.  크기 마스크는 다음과 같습니다.  
  
|`pattern`의 데이터 형식|크기 마스크\(10진수\)|크기 마스크\(16진수\)|  
|-----------------------|--------------------|--------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 `amount`가 0이면 `result` 값은 `pattern` 값과 같습니다.  `amount`가 음수이면 부호 없는 값으로 처리되며 적절한 크기 마스크로 마스크됩니다.  
  
 산술 시프트 연산에서는 오버플로 예외가 생성되지 않습니다.  
  
## 오버로딩  
 `>>` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `>>` 연산자를 사용하여 정수 값에 대한 산술 오른쪽 시프트 연산을 수행합니다.  결과의 데이터 형식은 항상 이동되는 식의 데이터 형식과 동일합니다.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 이전 예제의 결과는 다음과 같습니다.  
  
-   `result1`은 2560\(0000 1010 0000 0000\)입니다.  
  
-   `result2`는 160\(0000 0000 1010 0000\)입니다.  
  
-   `result3`은 2\(0000 0000 0000 0010\)입니다.  
  
-   `result4`는 640\(0000 0010 1000 0000\)입니다.  
  
-   `result5`는 0\(오른쪽으로 15자리 이동\)입니다.  
  
 `result4`의 이동할 비트 수는 18 AND 15로 계산되며 2와 같습니다.  
  
 다음 예제에서는 음수 값의 산술 시프트를 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 이전 예제의 결과는 다음과 같습니다.  
  
-   `negresult1`은 \-512\(1111 1110 0000 0000\)입니다.  
  
-   `negresult2`는 \-1\(부호 비트가 전파됨\)입니다.  
  
## 참고 항목  
 [Bit Shift Operators](../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [\>\>\= Operator](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)