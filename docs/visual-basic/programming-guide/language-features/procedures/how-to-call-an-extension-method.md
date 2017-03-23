---
title: "How to: Call an Extension Method (Visual Basic) | Microsoft Docs"
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
  - "calling extension methods"
  - "extension methods [Visual Basic]"
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Call an Extension Method (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

확장 메서드를 사용하면 기존 클래스에 메서드를 추가할 수 있습니다.  확장 메서드를 선언하여 범위로 가져온 후에는 해당 메서드가 확장하는 형식의 인스턴스 메서드와 마찬가지로 확장 메서드를 호출할 수 있습니다.  확장 메서드 작성 방법에 대한 자세한 내용은 [How to: Write an Extension Method](../../../../visual-basic/programming-guide/language-features/procedures/how-to-write-an-extension-method.md)을 참조하십시오.  
  
 다음 명령에서는 메서드를 호출한 문자열 인스턴스 및 두 번째 매개 변수 `punc`에 보내는 값을 차례로 표시하는 `PrintAndPunctuate` 확장 메서드를 사용합니다.  
  
```vb#  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
  
```  
  
 메서드는 호출 시 범위 안에 있어야 합니다.  
  
### 확장 메서드를 호출하려면  
  
1.  확장 메서드의 첫 번째 매개 변수의 데이터 형식을 가진 변수를 선언합니다.  `PrintAndPunctuate`의 경우에는 <xref:System.String> 변수가 필요합니다.  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  이 변수는 확장 메서드를 호출하고, 변수 값은 첫 번째 매개 변수 `aString`에 바인딩됩니다.  다음 호출 문은 `Ready?`를 표시합니다.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     이 확장 메서드를 호출하는 방법은 다음과 같이 매개 변수 하나를 필요로 하는 <xref:System.String> 인스턴스 메서드를 호출하는 방법과 동일합니다.  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  다른 문자열 변수를 선언하고 메서드를 다시 호출하여 어떠한 문자열에도 코드가 제대로 실행되는지 테스트해 봅니다.  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     이번에는 결과가 `or not!!!`입니다.  
  
## 예제  
 다음 코드는 간단한 확장 메서드를 만들고 사용하는 전체 예제입니다.  
  
```vb#  
Imports System.Runtime.CompilerServices  
Imports ConsoleApplication1.StringExtensions  
  
Module Module1  
  
    Sub Main()  
  
        Dim example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
        Dim example2 = "Goodbye"  
        example2.PrintAndPunctuate("?")  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
End Module  
  
' Output:  
' Hello.  
' Hello!!!!  
' Goodbye?  
```  
  
## 참고 항목  
 [How to: Write an Extension Method](../../../../visual-basic/programming-guide/language-features/procedures/how-to-write-an-extension-method.md)   
 [확장 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)