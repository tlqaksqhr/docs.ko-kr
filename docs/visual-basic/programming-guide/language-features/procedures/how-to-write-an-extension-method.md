---
title: "How to: Write an Extension Method (Visual Basic) | Microsoft Docs"
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
  - "extending data types"
  - "writing extension methods"
  - "extension methods [Visual Basic]"
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Write an Extension Method (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

확장 메서드를 사용하면 기존 클래스에 메서드를 추가할 수 있습니다.  확장 메서드는 해당 클래스의 인스턴스처럼 호출될 수 있습니다.  
  
### 확장 메서드를 정의하려면  
  
1.  Visual Studio에서 새 Visual Basic 응용 프로그램 또는 기존 Visual Basic 응용 프로그램을 엽니다.  
  
2.  확장 메서드를 정의할 파일의 맨 위에 다음 가져오기 문을 추가합니다.  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  새 응용 프로그램 또는 기존 응용 프로그램의 모듈 안에서 확장 특성을 사용하여 메서드 정의를 시작합니다.  
  
    ```  
    <Extension()>  
    ```  
  
4.  일반적인 방법으로 메서드를 선언하되, 확장할 데이터 형식이 첫 번째 매개 변수의 형식이 되어야 합니다.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## 예제  
 다음 예제에서는 `StringExtensions` 모듈에 확장 메서드를 선언합니다.  두 번째 모듈 `Module1`에서는 `StringExtensions`를 가져오고 메서드를 호출합니다.  확장 메서드는 호출 시 범위 안에 있어야 합니다.  `PrintAndPunctuate` 확장 메서드는 문자열 인스턴스 및 매개 변수로 보낸 문장 부호 문자열을 차례로 표시하는 메서드를 사용하여 <xref:System.String> 클래스를 확장합니다.  
  
```vb#  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
```vb#  
' Import the module that holds the extension method you want to use,   
' and call it.  
  
Imports ConsoleApplication2.StringExtensions  
  
Module Module1  
  
    Sub Main()  
        Dim example = "Hello"  
        example.PrintAndPunctuate("?")  
        example.PrintAndPunctuate("!!!!")  
    End Sub  
  
End Module  
  
```  
  
 이 메서드는 매개 변수 두 개를 사용하여 정의되었지만 그 중 하나만 호출됩니다.  메서드 정의에서 첫 번째 매개 변수 `aString`은 메서드를 호출하는 `String`의 인스턴스인 `example`에 바인딩됩니다.  이 예제는 다음과 같이 출력됩니다.  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [확장 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)