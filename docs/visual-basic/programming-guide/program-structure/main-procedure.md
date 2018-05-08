---
title: Visual Basic의 Main 프로시저
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 109bf94eb91292cfca700a9e456c8ab53e83d68f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="main-procedure-in-visual-basic"></a>Visual Basic의 Main 프로시저
모든 Visual Basic 응용 프로그램 호출 프로시저를 포함 해야 `Main`합니다. 이 절차는 사용 시작 지점 및 응용 프로그램에 대해 전체적으로 제어 됩니다. .NET Framework 호출 프로그램 `Main` 프로시저 응용 프로그램을 로드 하 고 제어를 전달 하도록 준비 되어 있습니다. Windows Forms 응용 프로그램을 만들 경우를 제외 작성 해야 합니다는 `Main` 자체적으로 실행 되는 응용 프로그램에 대 한 프로시저입니다.  
  
 `Main` 첫 번째 실행 되는 코드를 포함 합니다. `Main`, 프로그램을 시작할 때 먼저 로드할 폼을 확인, 응용 프로그램의 복사본은 시스템에서 실행 이미 확인, 응용 프로그램에 대 한 일련의 변수를 설정 하거나 응용 프로그램에 필요한 데이터베이스를 열 수 있습니다.  
  
## <a name="requirements-for-the-main-procedure"></a>Main 프로시저에 대 한 요구 사항  
 자체적 (일반적으로 확장명이.exe)으로 실행 되는 파일을 포함 해야 합니다는 `Main` 프로시저입니다. 라이브러리 (예를 들어 확장명.dll)에서 실행 되지 않을 자체 이며 필요 하지 않습니다는 `Main` 프로시저입니다. 만들 수 있습니다 하는 다양 한 유형의 프로젝트에 대 한 요구 사항은 다음과 같습니다.  
  
-   콘솔 응용 프로그램 자체적으로 실행을 하나 이상 지정 해야 `Main` 프로시저입니다. 입니다.  
  
-   Windows Forms 응용 프로그램을 자체적으로 실행 합니다. 그러나 Visual Basic 컴파일러를 자동으로 생성 한 `Main` 등의 절차는 응용 프로그램에서 불필요 하나 작성 합니다.  
  
-   클래스 라이브러리는 필요 하지 않습니다는 `Main` 프로시저입니다. 여기에 Windows 컨트롤 라이브러리 웹 컨트롤 라이브러리 포함 됩니다. 클래스 라이브러리는 웹 응용 프로그램 배포 됩니다.  
  
## <a name="declaring-the-main-procedure"></a>Main 프로시저를 선언합니다.  
 4 가지 방법으로 선언 하는 `Main` 프로시저입니다. 또는, 인수를 사용할 수 및 여부 값을 반환할 수 있습니다.  
  
> [!NOTE]
>  선언 하는 경우 `Main` 클래스를 사용 해야 하는 `Shared` 키워드입니다. 모듈에 `Main` 하지 않아도 `Shared`합니다.  
  
-   가장 간단한 방법은 선언 하는 `Sub` 인수 또는 값을 반환 하지 않는 프로시저입니다.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   `Main` 반환할 수도 있습니다는 `Integer` 프로그램에 대 한 종료 코드로 운영 체제를 사용 하는 값입니다. 다른 프로그램을 Windows ERRORLEVEL 값을 검사 하 여이 코드를 테스트할 수 있습니다. 종료 코드를 반환 하려면 선언 해야 `Main` 로 `Function` 프로시저 대신는 `Sub` 프로시저입니다.  
  
    ```  
    Module mainModule  
        Function Main() As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   `Main` 도 사용할 수 있습니다는 `String` 인수로 배열입니다. 배열의 각 문자열 프로그램을 호출 하는 데 사용 되는 명령줄 인수 중 하나를 포함 합니다. 값에 따라 다른 작업을 수행할 수 있습니다.  
  
    ```  
    Module mainModule  
        Function Main(ByVal cmdArgs() As String) As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   선언할 수 `Main` 를 명령줄 인수를 확인만 하지는 종료 코드를 다음과 같이 반환 합니다.  
  
    ```  
    Module mainModule  
        Sub Main(ByVal cmdArgs() As String)  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [Visual Basic 프로그램의 구조](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [공유](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [String 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)
