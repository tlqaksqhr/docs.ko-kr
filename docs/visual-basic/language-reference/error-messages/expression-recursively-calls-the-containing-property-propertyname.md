---
title: "Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39; | Microsoft Docs"
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
  - "vbc42026"
  - "BC42026"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42026"
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

속성 정의의 `Set` 프로시저에 있는 문은 값을 속성 이름에 저장합니다.  
  
 속성 값을 보관하는 권장 방법은 속성 컨테이너에 `Private` 변수를 정의하고 `Get` 및 `Set` 프로시저에서 사용하는 것입니다.  `Set` 프로시저는 이 `Private` 변수에 들어오는 값을 저장해야 합니다.  
  
 `Get` 프로시저는 `Function` 프로시저처럼 동작하므로 값을 속성 이름에 할당하고 `End Get` 문을 발견하면 제어를 반환할 수 있습니다.  그러나 권장 방법은 `Private` 변수를 [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)에 변수로 포함하는 것입니다.  
  
 `Set` 프로시저는 값을 반환하지 않는 `Sub` 프로시저처럼 동작합니다.  따라서 프로시저나 속성 이름은 `Set` 프로시저 내에서 특별한 의미를 갖지 않으므로 이러한 이름에 값을 저장할 수 없습니다.  
  
 다음 예제에서는 이 오류를 일으킬 수 있는 방법과 권장 방법을 차례로 보여 줍니다.  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC42026  
  
### 이 오류를 해결하려면  
  
-   위의 예제에 나타난 대로 권장 방법을 사용하도록 속성 정의를 다시 작성합니다.  
  
## 참고 항목  
 [Property 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)