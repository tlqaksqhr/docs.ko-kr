---
title: "New Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.new"
  - "vb.NewConstraint"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "constraints, Visual Basic generic types"
  - "generics [Visual Basic], constraints"
  - "constraints, New keyword"
  - "New constraint"
  - "New keyword"
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# New Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`New` 절을 정의하여 새 개체 인스턴스를 만들거나, 형식 매개 변수에 대한 생성자 제약 조건을 지정하거나 `Sub` 프로시저를 클래스 생성자로 식별합니다.  
  
## 설명  
 선언문이나 할당문에서 `New` 절은 인스턴스를 만들 수 있는 파생 클래스를 지정해야 합니다.  즉, 해당 클래스는 호출 코드에서 액세스할 수 있는 하나 이상의 생성자를 노출해야 합니다.  
  
 `New` 절은 선언문이나 할당문에 사용할 수 있습니다.  문이 실행되면 지정한 클래스의 해당 생성자를 호출하고 제공한 인수를 전달합니다.  다음 예제에서는 두 개의 생성자, 즉 매개 변수가 없는 생성자와 문자열 매개 변수가 있는 생성자를 가진 `Customer` 클래스의 인스턴스를 만들어 이 작업을 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 배열은 클래스이므로 `New`를 사용하면 다음 예제에 나오는 것처럼 새 배열 인스턴스가 만들어질 수 있습니다.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 CLR\(공용 언어 런타임\)에서는 새 인스턴스를 만드는 데 충분한 메모리가 없을 경우 <xref:System.OutOfMemoryException> 오류를 throw합니다.  
  
> [!NOTE]
>  또한 `New` 키워드는 제공된 형식이 액세스 가능한 매개 변수 없는 생성자를 노출하도록 지정하기 위해 형식 매개 변수 목록에서 사용됩니다.  형식 매개 변수와 제약 조건에 대한 자세한 내용은 [Type List](../../../visual-basic/language-reference/statements/type-list.md)을 참조하십시오.  
  
 클래스에 대한 생성자를 프로시저를 만들려면 `Sub` 프로시저의 이름을 `New` 키워드로 설정합니다.  자세한 내용은 [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)를 참조하십시오.  
  
 `New` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 <xref:System.OutOfMemoryException>   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)   
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)