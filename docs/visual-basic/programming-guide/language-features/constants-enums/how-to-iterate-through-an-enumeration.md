---
title: "How to: Iterate Through An Enumeration in Visual Basic | Microsoft Docs"
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
  - "arrays [Visual Basic], iterating"
  - "enumerations [Visual Basic], iterating"
  - "ListBox control [Windows Forms], populating from an enumeration"
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Iterate Through An Enumeration in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

열거형은 관련 상수 집합을 사용하고 상수 값을 이름과 연결하는 편리한 방법을 제공합니다.  열거형을 반복하려면 <xref:System.Enum.GetValues%2A> 메서드를 사용하여 열거형을 배열로 이동하면 됩니다.  또한 `For...Each` 문을 사용하거나, 문자열 또는 숫자 값을 추출하는 <xref:System.Enum.GetNames%2A> 또는 <xref:System.Enum.GetValues%2A> 메서드를 사용하여 열거형을 반복할 수도 있습니다.  
  
### 열거형을 반복하려면  
  
-   배열을 선언한 후 다른 변수를 전달하는 것과 마찬가지로 해당 배열을 전달하기 전에 <xref:System.Enum.GetValues%2A> 메서드를 사용하여 열거형을 해당 배열로 변환합니다.  다음 예제에서는 열거형 <xref:Microsoft.VisualBasic.FirstDayOfWeek>의 각 멤버가 열거형을 반복할 때 이를 표시합니다.  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#7)]  
  
## 참고 항목  
 [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)