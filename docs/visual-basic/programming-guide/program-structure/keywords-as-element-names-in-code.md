---
title: "Keywords as Element Names in Code (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, naming conventions"
  - "keywords [Visual Basic], in code"
  - "name conflicts"
  - "element names, in code"
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Keywords as Element Names in Code (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

변수, 클래스 또는 멤버 등의 일부 프로그램 요소는 제한된 키워드와 같은 이름을 가질 수 있습니다.  예를 들면, 이름이 `Loop`인 변수를 만들 수 있습니다.  그러나 이 변수를 같은 이름의 제한된 `Loop` 키워드와 구별하려면 다음 예제와 같이 이 변수 이름 앞에 전체 한정 문자열을 포함하거나 변수 이름을 대괄호\(`[ ]`\)로 묶어야 합니다.  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 그렇지 않으면 Visual Basic에서는 내장 `Loop` 키워드를 사용한 것으로 간주하고 다음 예제와 같은 오류를 발생시킵니다.  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 대괄호는 폼과 컨트롤을 나타낼 때 또는 제한된 키워드와 같은 이름을 사용하여 변수를 선언하거나 프로시저를 정의할 때 사용할 수 있습니다.  이름을 한정하거나 대괄호로 묶는 것을 잊어버리면 코드에 오류가 발생하고 읽기가 어려워집니다.  따라서 제한된 키워드는 프로그램 요소 이름으로 사용하지 않는 것이 좋습니다.  그러나 Visual Basic의 이후 버전에서 기존 폼 또는 컨트롤 이름과 충돌하는 새 키워드를 정의하는 경우 이 방법을 사용하여 새 버전에서 작동할 수 있도록 코드를 업데이트시킵니다.  
  
> [!NOTE]
>  프로그램에는 기타 참조 어셈블리에서 제공되는 요소 이름이 포함될 수도 있습니다.  이러한 요소 이름이 제한된 키워드와 충돌하는 경우 해당 요소 이름을 대괄호로 묶으면 Visual Basic에서는 사용자가 정의한 요소를 해석할 수 있습니다.  
  
## 참고 항목  
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [키워드](../../../visual-basic/language-reference/keywords/index.md)