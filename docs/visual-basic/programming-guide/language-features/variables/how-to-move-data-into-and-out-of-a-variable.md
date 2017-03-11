---
title: "How to: Move Data Into and Out of a Variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], retrieving values"
  - "variables [Visual Basic], storing data"
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Move Data Into and Out of a Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

대입문의 왼쪽에 변수 이름을 입력하여 변수에 값을 저장할 수 있습니다.  
  
## 변수에 데이터 입력  
  
#### 변수에 값을 저장하려면  
  
-   대입문의 왼쪽에 변수 이름을 입력합니다.  
  
     다음 예제에서는 `alpha` 변수의 값을 설정합니다.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     이렇게 하면 대입문의 오른쪽에 생성된 값이 변수에 저장됩니다.  
  
## 변수에서 데이터 가져오기  
 식에 변수 이름을 포함하여 변수 값을 검색할 수 있습니다.  
  
#### 변수에서 값을 검색하려면  
  
-   식에 변수 이름을 사용합니다.  상수 값을 정의하는 식을 제외하고 상수 또는 리터럴을 사용할 수 있는 모든 위치에 변수를 사용할 수 있습니다.  
  
     또는  
  
-   대입문에서 등호 기호\(`=`\) 뒤에 변수 이름을 입력합니다.  
  
     다음 예제에서는 `startValue` 변수의 값을 읽고 식에 `counter` 변수 값을 사용합니다.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     변수 값은 상수와 같은 방식으로 식에 사용된 다음 대입문 왼쪽의 변수 또는 속성에 저장됩니다.  
  
## 참고 항목  
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)