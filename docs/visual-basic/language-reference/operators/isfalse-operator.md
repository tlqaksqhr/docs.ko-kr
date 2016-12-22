---
title: "IsFalse Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.isfalse"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AndAlso operator"
  - "IsFalse operator"
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# IsFalse Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

식이 `False`인지 확인합니다.  
  
 사용자 코드에서는 `IsFalse`를 명시적으로 호출할 수 없지만 Visual Basic 컴파일러는 이 연산자를 사용하여 `AndAlso` 절에서 코드를 생성할 수 있습니다.  클래스나 구조체를 정의한 다음 `AndAlso` 절에서 해당 형식의 변수를 사용하는 경우 해당 클래스나 구조체에 대해 `IsFalse`를 정의해야 합니다.  
  
 컴파일러는 `IsFalse`와 `IsTrue` 연산자를 *일치하는 쌍*으로 간주합니다.  즉, 둘 중 하나를 정의할 경우 다른 하나도 정의해야 합니다.  
  
> [!NOTE]
>  `IsFalse` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 코드 예제에서는 `IsFalse`와 `IsTrue` 연산자에 대한 정의를 포함하는 구조체의 윤곽을 정의합니다.  
  
 [!CODE [VbVbalrOperators#28](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#28)]  
  
## 참고 항목  
 [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md)