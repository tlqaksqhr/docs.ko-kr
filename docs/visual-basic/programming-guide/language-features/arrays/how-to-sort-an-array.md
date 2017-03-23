---
title: "How to: Sort An Array in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Array.Sort"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arrays [Visual Basic], sorting"
  - "examples [Visual Basic], arrays"
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Sort An Array in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 예제에서는 `String` 개체로 이루어진 `zooAnimals`라는 배열을 선언하고 배열을 채운 다음 사전순으로 정렬합니다.  
  
## 예제  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Mscorlib.dll과 <xref:System> 네임스페이스에 대한 액세스 권한  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   배열이 비어 있는 경우\(<xref:System.ArgumentNullException> 클래스\)  
  
-   배열이 다차원인 경우\(<xref:System.RankException> 클래스\)  
  
-   배열 요소 중 하나 이상에서 <xref:System.IComparable> 인터페이스가 구현되지 않는 경우\(<xref:System.InvalidOperationException> 클래스\)  
  
## 참고 항목  
 <xref:System.Array.Sort%2A?displayProperty=fullName>   
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Troubleshooting Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)   
 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)