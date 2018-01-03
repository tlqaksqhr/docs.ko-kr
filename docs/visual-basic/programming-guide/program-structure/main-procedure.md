---
title: "Visual Basic의 Main 프로시저"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6de98ad4e470cd0becaf25f5a9a00c8095e44b15
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="595bc-102">Visual Basic의 Main 프로시저</span><span class="sxs-lookup"><span data-stu-id="595bc-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="595bc-103">모든 Visual Basic 응용 프로그램 호출 프로시저를 포함 해야 `Main`합니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="595bc-104">이 절차는 사용 시작 지점 및 응용 프로그램에 대해 전체적으로 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="595bc-105">.NET Framework 호출 프로그램 `Main` 프로시저 응용 프로그램을 로드 하 고 제어를 전달 하도록 준비 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="595bc-106">Windows Forms 응용 프로그램을 만들 경우를 제외 작성 해야 합니다는 `Main` 자체적으로 실행 되는 응용 프로그램에 대 한 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>  
  
 <span data-ttu-id="595bc-107">`Main`첫 번째 실행 되는 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="595bc-108">`Main`, 프로그램을 시작할 때 먼저 로드할 폼을 확인, 응용 프로그램의 복사본은 시스템에서 실행 이미 확인, 응용 프로그램에 대 한 일련의 변수를 설정 하거나 응용 프로그램에 필요한 데이터베이스를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>  
  
## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="595bc-109">Main 프로시저에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="595bc-109">Requirements for the Main Procedure</span></span>  
 <span data-ttu-id="595bc-110">자체적 (일반적으로 확장명이.exe)으로 실행 되는 파일을 포함 해야 합니다는 `Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="595bc-111">라이브러리 (예를 들어 확장명.dll)에서 실행 되지 않을 자체 이며 필요 하지 않습니다는 `Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="595bc-112">만들 수 있습니다 하는 다양 한 유형의 프로젝트에 대 한 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-112">The requirements for the different types of projects you can create are as follows:</span></span>  
  
-   <span data-ttu-id="595bc-113">콘솔 응용 프로그램 자체적으로 실행을 하나 이상 지정 해야 `Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span> <span data-ttu-id="595bc-114">입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-114">.</span></span>  
  
-   <span data-ttu-id="595bc-115">Windows Forms 응용 프로그램을 자체적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-115">Windows Forms applications run on their own.</span></span> <span data-ttu-id="595bc-116">그러나 Visual Basic 컴파일러를 자동으로 생성 한 `Main` 등의 절차는 응용 프로그램에서 불필요 하나 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-116">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>  
  
-   <span data-ttu-id="595bc-117">클래스 라이브러리는 필요 하지 않습니다는 `Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-117">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="595bc-118">여기에 Windows 컨트롤 라이브러리 웹 컨트롤 라이브러리 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-118">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="595bc-119">클래스 라이브러리는 웹 응용 프로그램 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-119">Web applications are deployed as class libraries.</span></span>  
  
## <a name="declaring-the-main-procedure"></a><span data-ttu-id="595bc-120">Main 프로시저를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-120">Declaring the Main Procedure</span></span>  
 <span data-ttu-id="595bc-121">4 가지 방법으로 선언 하는 `Main` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-121">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="595bc-122">또는, 인수를 사용할 수 및 여부 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-122">It can take arguments or not, and it can return a value or not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="595bc-123">선언 하는 경우 `Main` 클래스를 사용 해야 하는 `Shared` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-123">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="595bc-124">모듈에 `Main` 하지 않아도 `Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-124">In a module, `Main` does not need to be `Shared`.</span></span>  
  
-   <span data-ttu-id="595bc-125">가장 간단한 방법은 선언 하는 `Sub` 인수 또는 값을 반환 하지 않는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-125">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   <span data-ttu-id="595bc-126">`Main`반환할 수도 있습니다는 `Integer` 프로그램에 대 한 종료 코드로 운영 체제를 사용 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-126">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="595bc-127">다른 프로그램을 Windows ERRORLEVEL 값을 검사 하 여이 코드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-127">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="595bc-128">종료 코드를 반환 하려면 선언 해야 `Main` 로 `Function` 프로시저 대신는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-128">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>  
  
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
  
-   <span data-ttu-id="595bc-129">`Main`도 사용할 수 있습니다는 `String` 인수로 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-129">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="595bc-130">배열의 각 문자열 프로그램을 호출 하는 데 사용 되는 명령줄 인수 중 하나를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-130">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="595bc-131">값에 따라 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-131">You can take different actions depending on their values.</span></span>  
  
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
  
-   <span data-ttu-id="595bc-132">선언할 수 `Main` 를 명령줄 인수를 확인만 하지는 종료 코드를 다음과 같이 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="595bc-132">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="595bc-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="595bc-133">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [<span data-ttu-id="595bc-134">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="595bc-134">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="595bc-135">/main</span><span class="sxs-lookup"><span data-stu-id="595bc-135">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="595bc-136">공유</span><span class="sxs-lookup"><span data-stu-id="595bc-136">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="595bc-137">Sub 문</span><span class="sxs-lookup"><span data-stu-id="595bc-137">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="595bc-138">Function 문</span><span class="sxs-lookup"><span data-stu-id="595bc-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="595bc-139">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="595bc-139">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="595bc-140">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="595bc-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
