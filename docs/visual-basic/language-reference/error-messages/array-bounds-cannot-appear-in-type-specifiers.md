---
title: "Array bounds cannot appear in type specifiers | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30638"
  - "bc30638"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30638"
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Array bounds cannot appear in type specifiers
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

배열 크기는 데이터 형식 지정자의 일부로 선언할 수 없습니다.  
  
 **오류 ID:** BC30638  
  
### 이 오류를 해결하려면  
  
-   다음 예제와 같이 형식 뒤가 아닌 변수 이름 바로 다음에 배열의 크기를 지정합니다.  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   다음 예제와 같이 배열을 정의한 다음 원하는 개수의 요소로 초기화합니다.  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## 참고 항목  
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)