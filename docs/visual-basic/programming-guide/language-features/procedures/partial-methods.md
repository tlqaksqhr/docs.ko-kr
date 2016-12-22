---
title: "Partial Methods (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.PartialMethod"
  - "PartialMethod"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "custom logic into code [Visual Basic]"
  - "partial methods [Visual Basic]"
  - "partial, methods [Visual Basic]"
  - "methods [Visual Basic], partial methods"
  - "inserting custom logic into code"
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Partial Methods (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

부분 메서드를 사용하면 개발자가 사용자 지정 논리를 코드에 삽입할 수 있습니다.  일반적으로 코드는 디자이너 생성 클래스의 일부입니다.  부분 메서드는 코드 생성기에 의해 생성된 Partial 클래스에 정의되어 있으며 변경된 내용이 있음을 나타내는 알림을 제공합니다.  부분 메서드를 사용하여 개발자는 변경에 따라 사용자 지정 동작을 지정할 수 있습니다.  
  
 코드 생성기의 디자이너는 메서드 시그니처 및 메서드에 대한 하나 이상의 호출만 정의합니다.  그런 다음 개발자는 생성된 코드의 동작을 사용자 지정하는 경우 메서드의 구현을 제공할 수 있습니다.  구현이 제공되어 있지 않은 경우 메서드에 의한 호출은 컴파일러에 의해 제거되므로 추가 성능 오버헤드가 발생하지 않습니다.  
  
## 선언  
 생성된 코드는 시그니처 줄의 시작 부분에 키워드 `Partial`을 배치하여 부분 메서드의 정의를 표시합니다.  
  
```vb#  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 정의는 다음 조건을 만족해야 합니다.  
  
-   메서드는 `Function`이 아닌 `Sub`여야 합니다.  
  
-   메서드의 본문은 비어 있어야 합니다.  
  
-   액세스 한정자는 `Private`이어야 합니다.  
  
## 구현  
 구현은 주로 부분 메서드의 본문 채우기로 구성됩니다.  구현은 일반적으로 정의와는 별도의 Partial 클래스에 있으며 생성된 코드를 확장하려는 개발자에 의해 작성됩니다.  
  
```vb#  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 앞의 예제는 선언에서 확실히 시그니처가 중복되지만 변형이 가능합니다.  특히 `Overloads` 또는 `Overrides`와 같은 다른 한정자를 추가할 수 있습니다.  하나의 `Overrides` 한정자만 허용됩니다.  메서드 한정자에 대한 자세한 내용은 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)을 참조하십시오.  
  
## 사용할 도구  
 다른 `Sub` 프로시저를 호출하는 것처럼 부분 메서드를 호출합니다.  메서드가 구현된 경우 인수가 평가되고 메서드의 본문이 실행됩니다.  그러나 부분 메서드를 구현하는 것은 선택 사항입니다.  메서드가 구현되지 않은 경우 메서드에 대한 호출은 효과가 없으며 인수로 메서드에 전달된 식은 평가되지 않습니다.  
  
## 예제  
 Product.Designer.vb라는 파일에서 `Quantity` 속성이 있는 `Product` 클래스를 정의합니다.  
  
 [!code-vb[VbVbalrPartialMeths#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 Product.vb라는 파일에서 `QuantityChanged`에 대한 구현을 제공합니다.  
  
 [!code-vb[VbVbalrPartialMeths#5](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 마지막으로 프로젝트의 Main 메서드에서 `Product` 인스턴스를 선언하고 해당 `Quantity` 속성에 대해 초기 값을 제공합니다.  
  
 [!code-vb[VbVbalrPartialMeths#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 이 메시지를 표시하는 메시지 상자가 나타나야 합니다.  
  
 `Quantity was changed to 100`  
  
## 참고 항목  
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [LINQ to SQL의 코드 생성](../Topic/Code%20Generation%20in%20LINQ%20to%20SQL.md)   
 [부분 메서드를 사용하여 비즈니스 논리 추가](../Topic/Adding%20Business%20Logic%20By%20Using%20Partial%20Methods.md)