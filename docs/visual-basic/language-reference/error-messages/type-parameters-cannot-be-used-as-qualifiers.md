---
title: "Type parameters cannot be used as qualifiers | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32098"
  - "bc32098"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32098"
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Type parameters cannot be used as qualifiers
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로그래밍 요소가 형식 매개 변수를 포함하는 한정 문자열로 한정되었습니다.  
  
 형식 매개 변수는 제네릭 형식이 구성될 때 제공될 형식에 대한 요구 사항을 나타내며  정의된 특정 형식을 나타내지는 않습니다.  한정 문자열은 컴파일 타임에 정의되는 요소만 포함해야 합니다.  
  
 다음 문을 실행하면 이 오류가 발생할 수 있습니다.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **오류 ID:** BC32098  
  
### 이 오류를 해결하려면  
  
1.  한정 문자열에서 형식 매개 변수를 제거하거나 형식 매개 변수를 정의된 형식으로 바꿉니다.  
  
2.  생성된 형식을 사용하여 한정할 프로그래밍 요소를 찾아야 하는 경우 프로그램 논리를 추가로 사용해야 합니다.  
  
## 참고 항목  
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)