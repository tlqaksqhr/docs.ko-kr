---
title: "How to: Label Statements (Visual Basic) | Microsoft Docs"
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
  - "colons (:)"
  - "statements [Visual Basic], labels"
  - ": separator character"
  - "Visual Basic code, labeling statements"
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Label Statements (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

문 블록은 콜론으로 분리된 코드 줄로 이루어집니다.  문자열이나 정수를 식별하기 위해 앞에 놓이는 코드 줄을 *레이블*이라고 합니다.  문 레이블은 `On Error Goto`와 같은 문에서 사용하기 위한 식별 코드 줄을 표시하는 데 사용됩니다.  
  
 레이블유효한Visual Basic식별자 중 하나를 수 있습니다\-같은 프로그래밍 요소를 식별 하는\-또는정수리터럴.  같은 행에서 뒤에 문이 오는지 여부에 관계없이 레이블은 소스 코드 줄의 맨 앞에 와야 하며 그 뒤에 콜론을 붙여야 합니다.  
  
 컴파일러는 줄의 맨 앞 부분이 미리 정의된 식별자와 일치하는지 여부를 확인하여 레이블을 식별합니다.  일치하지 않는 경우 컴파일러는 이를 레이블이라고 가정합니다.  
  
 레이블에는 고유한 선언 공간이 있으며 다른 식별자를 방해하지 않습니다.  레이블의 범위는 메서드의 본문입니다.  모호한 상황에서는 레이블 선언이 우선합니다.  
  
> [!NOTE]
>  레이블은 메서드 내의 실행 문에서만 사용할 수 있습니다.  
  
### 코드 줄에 레이블을 지정하려면  
  
-   소스 코드 줄의 맨 앞에 식별자를 놓고 그 뒤에 콜론을 추가합니다.  
  
     예를 들어, 다음 코드 줄에는 각각 `Jump`와 `120`이라는 레이블이 사용되었습니다.  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/how-to-label-statements_1.vb)]  
  
## 참고 항목  
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)