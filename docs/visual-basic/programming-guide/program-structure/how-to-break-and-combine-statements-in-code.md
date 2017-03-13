---
title: "방법: 코드에서 문 분리 및 결합(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb._"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "콜론(:)"
  - "줄 연속"
  - "_ 줄 연속 문자"
  - ": 줄 구분 문자"
  - "Visual Basic 코드, 줄 바꿈"
  - "Visual Basic 코드, 줄 바꿈"
  - "Visual Basic 코드, 줄 연속"
  - "긴 줄로 된 코드"
  - "줄 종결자"
  - "줄 연속 시퀀스"
  - "밑줄, 코드"
  - "문[Visual Basic], 줄 연속"
  - "줄 바꿈, 코드"
  - "줄 연속 문자"
  - "Visual Basic 코드, 줄 연속"
  - "문[Visual Basic], 줄 바꿈"
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# 방법: 코드에서 문 분리 및 결합(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

코드를 작성할 때 코드 편집기 화면을 가로로 스크롤해야 볼 수 있는 긴 문을 작성하는 경우가 있습니다.  코드가 실행 되는 방식을 영향을 주지 않습니다 하지만 그 사용자나 다른 사람이 모니터에 표시 되는 코드를 읽기 어렵습니다.  한 줄로 된 긴 문은 여러 줄로 분리하는 것이 좋습니다.  
  
### 하나의 문을 여러 줄로 분리하려면  
  
-   줄을 바꿀 지점에서 줄 연속 문자로 밑줄\(`_`\)을 사용합니다.  밑줄 바로 앞에 공백으로 하 고 바로 뒤에 줄 종결자 \(캐리지 리턴\) 해야 합니다.  
  
    > [!NOTE]
    >  줄 연속 문자를 생략 하는 경우에 따라서는 Visual Basic 컴파일러 암시적 문을 코드의 다음 줄에서 계속 됩니다.  "암시적 줄 연속"에서 줄 연속 문자를 생략할 수 있는 구문 요소 목록은 참조 하십시오. [Statements](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     다음 예제에서는 마지막 줄을 제외한 모든 줄의 끝에 줄 연속 문자를 사용하여 문을 네 줄로 분리합니다.  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     이 시퀀스를 사용하면 온라인상에서나 인쇄 시 코드를 쉽게 읽을 수 있습니다.  
  
     줄 연속 문자를 줄에서 마지막 문자 여야 합니다.  하면이 모든 것을 같은 줄에 올 수 없습니다.  
  
     줄 연속 문자를 사용할 수 있는 위치에 대 한 존재 하는 몇 가지 제한이 따릅니다. 예를 들어, 인수 이름 중에 사용할 수 없습니다.  인수 목록은 줄 연속 문자를 사용하여 분리할 수 있지만 각 인수 이름은 같은 줄에 있어야 합니다.  
  
     줄 연속 문자를 사용 하 여 주석을 계속할 수 없습니다.  컴파일러의 문자가 특별 한 의미에 대 한 설명 검사 하지 않습니다.  여러 줄로 된 주석의 경우에는 각 줄에 주석 기호\(`'`\)를 반복합니다.  
  
 각 문은 별도 줄에 배치 하는, 것이 바람직하지만 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 또한 여러 개의 문을 같은 줄에 배치할 수 있습니다.  
  
### 여러 개의 문을 같은 줄에 결합하려면  
  
-   다음 예제와 같이 각 문을 콜론\(`:`\)으로 구분합니다.  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## 참고 항목  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)