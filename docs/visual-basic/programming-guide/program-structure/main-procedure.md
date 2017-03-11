---
title: "Main Procedure in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Main"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Main procedure"
  - "Main method [Visual Basic]"
  - "main function"
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Main Procedure in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

모든 Visual Basic 응용 프로그램에는 `Main`이라는 프로시저가 있어야 합니다.  이 프로시저는 응용 프로그램의 시작 위치를 나타내며 해당 응용 프로그램을 전체적으로 제어하는 데 사용됩니다.  .NET Framework는 응용 프로그램을 로드하고 이 프로시저에 제어를 전달할 준비가 되면 `Main` 프로시저를 호출합니다.  Windows Forms 응용 프로그램을 만드는 경우가 아니면 자체적으로 실행되는 응용 프로그램에 `Main` 프로시저를 작성해야 합니다.  
  
 `Main`에는 가장 먼저 실행되는 코드가 들어 있습니다.  `Main`을 사용하면 프로그램을 시작할 때 가장 먼저 로드될 폼을 확인하거나, 응용 프로그램의 복사본이 시스템에서 이미 실행 중인지를 확인하거나, 응용 프로그램의 변수 집합을 설정하거나, 응용 프로그램에 필요한 데이터베이스를 열 수 있습니다.  
  
## Main 프로시저의 요구 사항  
 자체 실행되는 파일\(일반적으로 확장명이 .exe인 파일\)은 반드시 `Main` 프로시저를 포함해야 합니다.  자체 실행되지 않는 라이브러리\(예: 확장명이.dll인 파일\)에는 `Main` 프로시저가 필요하지 않습니다.  만들 수 있는 다른 형식의 프로젝트에 대한 요구 사항은 다음과 같습니다.  
  
-   콘솔 응용 프로그램은 자체 실행되므로 하나 이상의 `Main` 프로시저를 제공해야 합니다.  .  
  
-   Windows Forms 응용 프로그램은 자체 실행되지만  이러한 응용 프로그램의 경우 Visual Basic 컴파일러가 `Main` 프로시저를 자동으로 생성하므로 이 프로시저를 직접 작성할 필요가 없습니다.  
  
-   클래스 라이브러리에는 `Main` 프로시저가 필요하지 않습니다.  클래스 라이브러리에는 Windows 컨트롤 라이브러리와 웹 컨트롤 라이브러리가 포함됩니다.  웹 응용 프로그램은 클래스 라이브러리로 배포됩니다.  
  
## Main 프로시저 선언  
 네 가지 방법으로 `Main` 프로시저를 선언할 수 있습니다.  인수를 선택적으로 사용할 수 있으며 값 또한 선택적으로 반환할 수 있습니다.  
  
> [!NOTE]
>  클래스에서 `Main`을 선언하는 경우 `Shared` 키워드를 사용해야 합니다.  그러나 모듈에서 `Main`을 선언하는 경우에는 `Shared`를 사용하지 않아도 됩니다.  
  
-   가장 간단한 방법은 인수를 사용하지 않거나 값을 반환하지 않는 `Sub` 프로시저를 선언하는 것입니다.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   또한 `Main`은 운영 체제에서 해당 프로그램에 대한 종료 코드로 사용하는 `Integer` 값을 반환할 수 있습니다.  다른 프로그램에서는 Windows ERRORLEVEL 값을 검사하여 이 코드를 테스트할 수 있습니다.  종료 코드를 반환하려면 `Main`을 `Sub` 프로시저 대신 `Function` 프로시저로 선언해야 합니다.  
  
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
  
-   또한 `Main`은 인수로 `String` 배열을 사용할 수 있습니다.  해당 배열의 각 문자열에는 프로그램을 호출하는 데 사용되는 하나의 명령줄 인수가 포함되어 있습니다.  해당 값에 따라 서로 다른 작업을 수행할 수 있습니다.  
  
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
  
-   다음과 같이 명령줄 인수를 검사하지만 종료 코드는 반환하지 않도록 `Main`을 선언할 수 있습니다.  
  
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
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>   
 <xref:System.Array.Length%2A>   
 <xref:Microsoft.VisualBasic.Information.UBound%2A>   
 [Structure of a Visual Basic Program](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)   
 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/ko-kr/9d030b60-e148-4366-a462-69532f02294c)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md)