---
title: "Optional parameters must specify a default value | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30812"
  - "bc30812"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30812"
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Optional parameters must specify a default value
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저 호출에서 매개 변수를 지정하지 않은 경우 사용할 수 있도록 선택적 매개 변수에 기본값을 지정해야 합니다.  
  
 **오류 ID:** BC30812  
  
### 이 오류를 해결하려면  
  
-   선택적 매개 변수에 기본값을 지정합니다. 예를 들면 다음과 같습니다.  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## 참고 항목  
 [Optional](../../../visual-basic/language-reference/modifiers/optional.md)