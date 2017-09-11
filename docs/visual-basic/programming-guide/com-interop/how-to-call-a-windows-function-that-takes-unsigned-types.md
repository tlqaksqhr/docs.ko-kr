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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b6b1d46b6ccab0ec8d63fb8b7d8722b518b81b4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="4ca61-102">방법: 부호 없는 형식을 사용하는 Windows 함수 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ca61-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="4ca61-103">클래스, 모듈 또는 부호 없는 정수 형식의 멤버가 있는 구조체를 사용 하는 경우이 멤버에 액세스할 수 있습니다 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="4ca61-104">부호 없는 형식을 사용 하는 Windows 함수를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="4ca61-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="4ca61-105">사용 하 여 한 [선언 문](../../../visual-basic/language-reference/statements/declare-statement.md) 를 구분할 수 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수가 포함 된 라이브러리, 해당 라이브러리에 무엇이 이름, 호출 시퀀스는 기능 및 메서드를 호출 하는 경우 문자열을 변환 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="4ca61-106">에 `Declare` 문을 사용 하 여 `UInteger`, `ULong`, `UShort`, 또는 `Byte` 각 매개 변수를 부호 없는 형식에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="4ca61-107">이름 및 사용 되는 상수 값을 찾으려는 호출 하는 Windows 함수에 대 한 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4ca61-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="4ca61-108">이들 중 대부분은 WinUser.h 파일에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="4ca61-109">코드에서 필요한 상수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="4ca61-110">많은 Windows 상수는 32 비트 부호 없는 값 및 이러한 선언 해야 `As``UInteger`합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As``UInteger`.</span></span>  
  
5.  <span data-ttu-id="4ca61-111">일반적인 방법으로 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-111">Call the function in the normal way.</span></span> <span data-ttu-id="4ca61-112">Windows 함수를 호출 하는 다음 예제에서는 `MessageBox`, 부호 없는 정수 인수를 사용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
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
  
     <span data-ttu-id="4ca61-113">함수를 테스트할 수 `messageThroughWindows` 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="4ca61-114">`UInteger`, `ULong`, `UShort`, 및 `SByte` 데이터 형식이 없는의 일부는 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS (), 하므로 CLS 규격 코드를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4ca61-115">Windows 응용 프로그램 프로그래밍 인터페이스 (API)와 같은 관리 되지 않는 코드를 호출 하는 잠재적인 보안 위험에 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4ca61-116">Windows API 호출 비관리 코드 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ca61-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="4ca61-117">자세한 내용은 참조 <xref:System.Security.Permissions.SecurityPermission>및 [코드 액세스 권한](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</xref:System.Security.Permissions.SecurityPermission></span><span class="sxs-lookup"><span data-stu-id="4ca61-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca61-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ca61-118">See Also</span></span>  
 <span data-ttu-id="4ca61-119">[데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="4ca61-119">[Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="4ca61-120"> [Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="4ca61-120"> [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="4ca61-121"> [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="4ca61-121"> [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) </span></span>  
<span data-ttu-id="4ca61-122"> [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4ca61-122"> [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="4ca61-123"> [연습: Windows API 호출](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)</span><span class="sxs-lookup"><span data-stu-id="4ca61-123"> [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)</span></span>
