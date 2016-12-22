---
title: "Variable &#39;&lt;variablename&gt;&#39; hides a variable in an enclosing block | Microsoft Docs"
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
  - "vbc30616"
  - "bc30616"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30616"
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Variable &#39;&lt;variablename&gt;&#39; hides a variable in an enclosing block
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

블록에 포함된 변수의 이름이 다른 지역 변수의 이름과 같습니다.  
  
 **오류 ID:** BC30616  
  
### 이 오류를 해결하려면  
  
-   다른 지역 변수와 이름이 같지 않도록 블록 내부에 있는 변수의 이름을 다시 지정합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   일반적으로 이벤트 처리기 내에서 `Catch e As Exception`을 사용하면 이 오류가 발생합니다.  이러한 경우 `Catch` 블록 변수의 이름을 `e`가 아니라 `ex`로 지정합니다.  
  
-   별도의 `Catch` 블록에 있는 `Try` 블록 내에서 선언된 지역 변수에 액세스하려고 할 때도 이 오류가 발생합니다.  이 오류를 해결하려면 `Try...Catch...Finally` 구조체의 외부에서 변수를 선언합니다.  
  
## 참고 항목  
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)