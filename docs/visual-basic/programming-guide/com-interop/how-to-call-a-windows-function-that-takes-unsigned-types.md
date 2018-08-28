---
title: '방법: 부호 없는 형식을 사용하는 Windows 함수 호출(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: 44c67470def430a9ba924483899f0db6a9c798a2
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999911"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>방법: 부호 없는 형식을 사용하는 Windows 함수 호출(Visual Basic)
클래스, 모듈 또는 부호 없는 정수 형식의 멤버가 있는 구조를 사용 중인 경우에 Visual Basic을 사용 하 여 이러한 멤버를 액세스할 수 있습니다.  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Windows 함수 호출을 사용 하는 부호 없는 형식  
  
1.  사용 하 여는 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) 함수가 포함 된 라이브러리, 해당 라이브러리의 이란 해당 이름, 호출 시퀀스 란, 및 호출 시 문자열을 변환 하는 방법을 Visual Basic을 알려야 합니다.  
  
2.  에 `Declare` 문을 사용 하 여 `UInteger`를 `ULong`를 `UShort`, 또는 `Byte` 부호 없는 형식 사용 하 여 각 매개 변수에 대해 적절 하 게 합니다.  
  
3.  이름 및 사용 되는 상수 값을 찾으려면 호출 하는 Windows 함수 설명서를 참조 하세요. 이러한 많은 WinUser.h 파일에 정의 됩니다.  
  
4.  코드에서 필요한 상수를 선언 합니다. 많은 Windows 상수는 32 비트 부호 없는 값 및 이러한 선언 해야 `As``UInteger`합니다.  
  
5.  일반적인 방법으로 함수를 호출 합니다. Windows 함수를 호출 하는 다음 예제에서는 `MessageBox`, 부호 없는 정수 인수입니다.  
  
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
    >  `UInteger`, `ULong`, `UShort`, 및 `SByte` 데이터 형식이 다의 일부를 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), CLS 규격 코드 구성 요소를 사용할 수 없습니다 있도록 하는 사용합니다.  
  
    > [!IMPORTANT]
    >  Windows 응용 프로그램 프로그래밍 인터페이스 (API)와 같은 관리 되지 않는 코드를 호출 하는 잠재적인 보안 위험에 코드를 제공 합니다.  
  
    > [!IMPORTANT]
    >  Windows API를 호출 하려면 부분 신뢰 상황에서 해당 실행에 영향을 줄 수 있는 비관리 코드 권한이 있어야 합니다. 자세한 내용은 <xref:System.Security.Permissions.SecurityPermission> 하 고 [코드 액세스 권한](http://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../visual-basic/language-reference/data-types/index.md)  
 [Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [연습: Windows API 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
