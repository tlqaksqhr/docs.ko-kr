---
title: "&#39;&lt;variablename&gt;&#39; 변수는 바깥쪽 범위의 필드에 바인딩되어 있으므로 변수 형식이 유추되지 않습니다. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42110"
  - "bc42110"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42110"
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
caps.latest.revision: 33
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 33
---
# &#39;&lt;variablename&gt;&#39; 변수는 바깥쪽 범위의 필드에 바인딩되어 있으므로 변수 형식이 유추되지 않습니다.
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

다양한 '\<변수명\>'의 형식은 변수가 바깥쪽 범위의 필드에 바인딩되어 있으므로 유추할 수 없습니다.'\<변수명\>'의 이름을 바꾸거나 정규화된 이름을 사용하십시오\(예: 'Me.variablename' 또는 'MyBase.variablename'\).  
  
 코드에서 루프 제어 변수에 사용한 이름이 클래스 또는 기타 바깥쪽 범위의 필드에 사용한 이름과 같습니다.  제어 변수는 `As` 절 없이 사용되므로 바깥쪽 범위의 필드에 바인딩됩니다. 컴파일러에서는 제어 변수에 대한 새 변수를 만들거나 해당 형식을 유추하지 않습니다.  
  
 다음 예제에서 `For` 문의 제어 변수 `Index`는 `Customer` 클래스의 `Index` 필드에 바인딩됩니다.  따라서 컴파일러에서 제어 변수 `Index`의 새 변수를 만들거나 해당 형식을 유추할 수 없습니다.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
  
```  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC42110  
  
### 이 경고를 처리하려면  
  
-   해당 이름을 클래스의 필드 이름이 아닌 식별자로 변경하여 루프 제어 변수를 지역 변수로 설정합니다.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   변수 이름에 접두사로 `Me.`를 사용하여 루프 제어 변수가 클래스 필드에 바인딩되도록 합니다.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   지역 형식 유추를 사용하는 대신 `As` 절을 사용하여 루프 제어 변수의 형식을 지정합니다.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## 예제  
 다음 코드에서는 첫 번째 수정 사항이 적용된 이전 예제를 보여 줍니다.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## 참고 항목  
 [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [How to: Refer to the Current Instance of an Object](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)