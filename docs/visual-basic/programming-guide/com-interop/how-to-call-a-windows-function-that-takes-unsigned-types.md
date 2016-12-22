---
title: "How to: Call a Windows Function that Takes Unsigned Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Windows functions, calling"
  - "unsigned data types"
  - "UShort data type, using"
  - "functions [Visual Basic], calling Windows functions"
  - "ULong data type, using"
  - "UInteger data type, using"
  - "data types [Visual Basic], using"
  - "unsigned types"
  - "data types [Visual Basic], unsigned"
  - "data types [Visual Basic], numeric"
  - "unsigned types, using"
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

부호 없는 정수 형식의 멤버가 있는 클래스, 모듈 또는 구조체를 사용하는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 이 멤버에 액세스할 수 있습니다.  
  
### 부호 없는 형식을 사용하는 Windows 함수를 호출하려면  
  
1.  [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)을 사용하여 함수가 포함된 라이브러리, 해당 라이브러리에서의 함수 이름, 함수 호출 시퀀스 및 함수 호출 시 문자열 변환 방법을 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에 지정합니다.  
  
2.  `Declare` 문에서 부호 없는 형식을 사용하는 각 매개 변수에 적절한 형식\(`UInteger`, `ULong`, `UShort` 또는 `Byte`\)을 사용합니다.  
  
3.  호출할 Windows 함수에 대한 설명서를 참조하여 해당 함수가 사용하는 이름 및 상수 값을 찾습니다.  대부분의 이름 및 상수 값은 WinUser.h 파일에 정의되어 있습니다.  
  
4.  코드에 필요한 상수를 선언합니다.  대부분의 Windows 상수는 부호 없는 32비트 값이고 이러한 값은 `As` `UInteger`로 선언해야 합니다.  
  
5.  일반적인 방법으로 함수를 호출합니다.  다음 예제에서는 부호 없는 정수 인수를 사용하는 Windows 함수 `MessageBox`를 호출합니다.  
  
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
  
     다음 코드를 사용하여 `messageThroughWindows` 함수를 테스트할 수 있습니다.  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  `UInteger`, `ULong`, `UShort` 및 `SByte` 데이터 형식은 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\)에 포함되어 있지 않으므로 CLS 규격 코드에서는 이 데이터 형식을 사용하는 구성 요소를 사용할 수 없습니다.  
  
    > [!IMPORTANT]
    >  Windows API\(응용 프로그래밍 인터페이스\)와 같은 비관리 코드를 호출하면 사용하는 코드가 잠재적인 보안 위험에 노출됩니다.  
  
    > [!IMPORTANT]
    >  Windows API를 호출하려면 비관리 코드 권한이 있어야 합니다. 이 권한은 부분 신뢰 상태에서 코드 실행을 제한할 수 있습니다.  자세한 내용은 <xref:System.Security.Permissions.SecurityPermission> 및 [Code Access Permissions](http://msdn.microsoft.com/ko-kr/e5ae402f-6dda-4732-bbe8-77296630f675)을 참조하십시오.  
  
## 참고 항목  
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)