---
title: "Name &#39;&lt;name&gt;&#39; is not declared | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30451"
  - "vbc30451"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30451"
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Name &#39;&lt;name&gt;&#39; is not declared
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

문이 프로그래밍 요소를 참조하지만 컴파일러에서 똑같은 이름을 가진 요소를 찾을 수 없습니다.  
  
 **오류 ID:** BC30451  
  
### 이 오류를 해결하려면  
  
1.  참조하는 문에 있는 이름의 철자를 확인합니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 대\/소문자를 구분하지 않지만 철자가 다르면 다른 이름으로 간주됩니다.  밑줄\(`_`\)역시 이름에 포함되므로 철자의 일부입니다.  
  
2.  개체와 그 멤버 사이에 멤버 액세스 연산자\(`.`\)가 있는지 확인합니다.  예를 들어, 이름이 `TextBox1`인 <xref:System.Windows.Forms.TextBox> 컨트롤이 있을 경우 해당 <xref:System.Windows.Forms.TextBoxBase.Text%2A> 속성에 액세스하려면 `TextBox1.Text`를 입력해야 합니다.  `TextBox1Text`를 대신 입력하면 다른 이름이 만들어집니다.  
  
3.  철자가 정확하고 개체 멤버 액세스의 구문이 올바른 경우 요소가 선언되었는지 확인합니다.  자세한 내용은 [Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)를 참조하십시오.  
  
4.  프로그래밍 요소가 선언된 경우 범위 안에 있는지 확인합니다.  참조하는 문이 범위 밖에서 프로그래밍 요소를 선언하면 요소 이름을 한정해야 합니다.  자세한 내용은 [Scope in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)를 참조하십시오.  
  
## 참고 항목  
 [Declarations and Constants Summary](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)