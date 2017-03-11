---
title: "IsTrue Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.istrue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IsTrue operator"
  - "OrElse operator [Visual Basic]"
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# IsTrue Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

식이 `True`인지 확인합니다.  
  
 사용자 코드에서는 `IsTrue`를 명시적으로 호출할 수 없지만 Visual Basic 컴파일러는 이 연산자를 사용하여 `OrElse` 절에서 코드를 생성할 수 있습니다.  클래스나 구조체를 정의한 다음 `OrElse` 절에서 해당 형식의 변수를 사용하는 경우 해당 클래스나 구조체에 대해 `IsTrue`를 정의해야 합니다.  
  
 컴파일러는 `IsTrue`와 `IsFalse` 연산자를 *일치하는 쌍*으로 간주합니다.  즉, 둘 중 하나를 정의할 경우 다른 하나도 정의해야 합니다.  
  
## 컴파일러의 IsTrue 사용  
 클래스나 구조체를 정의한 경우 `For`, `If`, `Else` `If` 또는 `While` 문이나 `When` 절에서 해당 형식의 변수를 사용할 수 있습니다.  이렇게 하면 컴파일러에서 조건을 테스트할 수 있도록 해당 형식을 `Boolean` 값으로 변환하는 연산자가 필요합니다.  다음과 같은 순서로 적합한 연산자가 검색됩니다.  
  
1.  클래스나 구조체를 `Boolean`으로 확대 변환하는 연산자  
  
2.  클래스나 구조체를 `Boolean?`으로 확대 변환하는 연산자  
  
3.  클래스나 구조체에 대한 `IsTrue` 연산자  
  
4.  `Boolean`에서 `Boolean?`로의 변환을 포함하지 않는 `Boolean?`에 대한 축소 변환입니다.  
  
5.  클래스나 구조체를 `Boolean`으로 축소 변환하는 연산자  
  
 `Boolean` 형식으로의 변환이나 `IsTrue` 연산자를 정의하지 않았으면 컴파일러에서 오류가 표시됩니다.  
  
> [!NOTE]
>  `IsTrue` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 `IsFalse`와 `IsTrue` 연산자에 대한 정의를 포함하는 구조체의 윤곽을 정의합니다.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/istrue-operator_1.vb)]  
  
## 참고 항목  
 [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md)