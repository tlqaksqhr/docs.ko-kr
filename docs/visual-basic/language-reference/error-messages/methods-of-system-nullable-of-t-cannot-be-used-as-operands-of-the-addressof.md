---
title: "Methods of &#39;System.Nullable(Of T)&#39; cannot be used as operands of the &#39;AddressOf&#39; operator | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32126"
  - "bc32126"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32126"
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Methods of &#39;System.Nullable(Of T)&#39; cannot be used as operands of the &#39;AddressOf&#39; operator
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

문에 <xref:System.Nullable%601> 구조체의 프로시저를 나타내는 피연산자와 함께 `AddressOf` 연산자가 사용되고 있습니다.  
  
 **오류 ID:** BC32126  
  
### 이 오류를 해결하려면  
  
-   `AddressOf` 절의 프로시저 이름을 <xref:System.Nullable%601>의 멤버가 아닌 피연산자로 바꿉니다.  
  
-   사용할 <xref:System.Nullable%601>의 메서드를 래핑하는 클래스를 작성합니다.  다음 예제에서는 `NullableWrapper` 클래스에 `GetValueOrDefault`라는 새 메서드를 정의합니다.  이 새 메서드는 <xref:System.Nullable%601>의 멤버가 아니므로 nullable 형식의 인스턴스인 `nullInstance`에 적용하여 `AddressOf`의 인수를 만들 수 있습니다.  
  
    ```vb#  
    Module Module1  
  
        Delegate Function Deleg() As Integer  
  
        Sub Main()  
            Dim nullInstance As New Nullable(Of Integer)(1)  
  
            Dim del As Deleg  
  
            ' GetValueOrDefault is a method of the Nullable generic  
            ' type. It cannot be used as an operand of AddressOf.  
            ' del = AddressOf nullInstance.GetValueOrDefault  
  
            ' The following line uses the GetValueOrDefault method  
            ' defined in the NullableWrapper class.  
            del = AddressOf (New NullableWrapper(  
                Of Integer)(nullInstance)).GetValueOrDefault  
  
            Console.WriteLine(del.Invoke())  
        End Sub  
  
        Class NullableWrapper(Of T As Structure)  
            Private m_Value As Nullable(Of T)  
  
            Sub New(ByVal Value As Nullable(Of T))  
                m_Value = Value  
            End Sub  
  
            Public Function GetValueOrDefault() As T  
                Return m_Value.Value  
            End Function  
        End Class  
    End Module  
    ```  
  
## 참고 항목  
 <xref:System.Nullable%601>   
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)