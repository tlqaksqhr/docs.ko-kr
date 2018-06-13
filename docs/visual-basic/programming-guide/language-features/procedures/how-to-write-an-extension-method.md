---
title: '방법: 확장명 메서드 작성(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: e220a025c39757b492be033caeb8924523515804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648735"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>방법: 확장명 메서드 작성(Visual Basic)
확장 메서드를 사용 하 여 기존 클래스에 메서드를 추가할 수 있습니다. 해당 클래스의 인스턴스 된 확장 메서드를 호출할 수 있습니다.  
  
### <a name="to-define-an-extension-method"></a>확장 메서드를 정의 하려면  
  
1.  Visual Studio에서 기존 또는 새 Visual Basic 응용 프로그램을 엽니다.  
  
2.  확장 메서드를 정의 하려는 파일 맨 위에 있는 다음 import 문을 포함:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  기존 또는 새 응용 프로그램에서 모듈 내에서 확장 특성으로 메서드 정의 시작 합니다.  
  
    ```  
    <Extension()>  
    ```  
  
4.  일반적인 방법으로 메서드를 선언는 첫 번째 매개 변수 형식의 확장 하려는 데이터 형식을 여야 합니다.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a>예제  
 다음 예제에서는 모듈의 확장 메서드를 선언 `StringExtensions`합니다. 두 번째 모듈 `Module1`, 가져옵니다 `StringExtensions` 메서드를 호출 합니다. 확장 메서드를 호출할 때 범위 여야 합니다. 확장 메서드 `PrintAndPunctuate` 확장은 <xref:System.String> 문자열 인스턴스를 표시 하는 메서드를 사용 하 여 클래스 다음 매개 변수로 전송 문장 부호 기호 문자열입니다.  
  
```vb  
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
  
```vb  
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
  
 고 해당 메서드는 두 개의 매개 변수를 사용 하 여 정의 중 하나만 호출 됩니다. 첫 번째 매개 변수 `aString`, 메서드 정의에 바인딩된 `example`, 인스턴스의 `String` 메서드를 호출 하는 합니다. 예제의 출력은 다음과 같습니다.  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [확장명 메서드](./extension-methods.md)  
 [Module 문](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
