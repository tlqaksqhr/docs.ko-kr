---
title: "방법: 부호 없는 형식 (Visual Basic)를 사용 하는 Windows 함수를 호출 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Windows functions, calling
- unsigned data types
- UShort data type, using
- functions [Visual Basic], calling Windows functions
- ULong data type, using
- UInteger data type, using
- data types [Visual Basic], using
- unsigned types
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types, using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fbff07f4923b0633a2bc9b4fd558d9d51f64370a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>방법: 부호 없는 형식을 사용하는 Windows 함수 호출(Visual Basic)
클래스, 모듈 또는 부호 없는 정수 형식의 멤버가 있는 구조체를 사용 하는 경우이 멤버에 액세스할 수 있습니다 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>부호 없는 형식을 사용 하는 Windows 함수를 호출 하려면  
  
1.  사용 하 여 한 [선언 문](../../../visual-basic/language-reference/statements/declare-statement.md) 를 구분할 수 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수가 포함 된 라이브러리, 해당 라이브러리에 무엇이 이름, 호출 시퀀스는 기능 및 메서드를 호출 하는 경우 문자열을 변환 하는 방법입니다.  
  
2.  에 `Declare` 문을 사용 하 여 `UInteger`, `ULong`, `UShort`, 또는 `Byte` 각 매개 변수를 부호 없는 형식에 적합 합니다.  
  
3.  이름 및 사용 되는 상수 값을 찾으려는 호출 하는 Windows 함수에 대 한 설명서를 참조 하십시오. 이들 중 대부분은 WinUser.h 파일에 정의 됩니다.  
  
4.  코드에서 필요한 상수를 선언 합니다. 많은 Windows 상수는 32 비트 부호 없는 값 및 이러한 선언 해야 `As``UInteger`합니다.  
  
5.  일반적인 방법으로 함수를 호출 합니다. Windows 함수를 호출 하는 다음 예제에서는 `MessageBox`, 부호 없는 정수 인수를 사용 하 합니다.  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     함수를 테스트할 수 `messageThroughWindows` 다음 코드를 사용 합니다.  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  `UInteger`, `ULong`, `UShort`, 및 `SByte` 데이터 형식이 없는의 일부는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS (), 하므로 CLS 규격 코드를 사용 하는 구성 요소를 사용할 수 없습니다.  
  
    > [!IMPORTANT]
    >  Windows 응용 프로그램 프로그래밍 인터페이스 (API)와 같은 관리 되지 않는 코드를 호출 하는 잠재적인 보안 위험에 코드를 제공 합니다.  
  
    > [!IMPORTANT]
    >  Windows API 호출 비관리 코드 권한이 필요 합니다. 자세한 내용은 참조 <xref:System.Security.Permissions.SecurityPermission>및 [코드 액세스 권한](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</xref:System.Security.Permissions.SecurityPermission>  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)   
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [연습: Windows API 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
