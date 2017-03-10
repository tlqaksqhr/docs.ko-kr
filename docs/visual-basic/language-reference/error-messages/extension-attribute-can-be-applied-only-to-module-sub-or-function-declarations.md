---
title: "&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36550"
  - "vbc36550"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36550"
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# &#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Visual Basic에서 데이터 형식을 확장하는 유일한 방법은 표준 모듈 내에 확장 메서드를 정의하는 것입니다.  확장 메서드는 `Sub` 프로시저 또는 `Function` 프로시저가 될 수 있습니다.  모든 확장 메서드는 <xref:System.Runtime.CompilerServices?displayProperty=fullName> 네임스페이스에서 `<Extension()>` 확장 특성으로 표시해야 합니다.  필요에 따라 확장 메서드를 포함하는 모듈을 같은 방법으로 표시할 수 있습니다.  확장 특성의 다른 사용은 유효하지 않습니다.  
  
 **오류 ID:** BC36550  
  
### 이 오류를 해결하려면  
  
-   확장 특성을 제거합니다.  
  
-   바깥쪽 모듈에 정의된 메서드로 확장을 다시 설계합니다.  
  
## 예제  
 다음 예제에서는 `String` 데이터 형식에 대해 `Print` 메서드를 정의합니다.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
  
```  
  
## 참고 항목  
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [확장 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)