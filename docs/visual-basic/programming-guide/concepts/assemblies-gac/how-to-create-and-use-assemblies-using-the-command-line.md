---
title: "방법: 명령줄 (Visual Basic)를 사용 하 여 어셈블리 만들기 및 사용 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 69e9cab9dda1fefe8bee3dc46b541313d1d80e58
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="61ae5-102">방법: 명령줄 (Visual Basic)를 사용 하 여 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="61ae5-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="61ae5-103">어셈블리 또는 동적 연결 라이브러리 (DLL)는 런타임 시 프로그램에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="61ae5-104">빌드 및 DLL 사용을 보여 주기 위해 다음 시나리오를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="61ae5-105">`MathLibrary.DLL`런타임 시 호출 되는 메서드가 포함 된: 라이브러리 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="61ae5-106">이 예제에서는 DLL 포함, 두 메서드는 `Add` 및 `Multiply`합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="61ae5-107">`Add`메서드를 포함 하는 소스 파일: `Add`합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="61ae5-108">해당 매개 변수의 합계를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="61ae5-109">클래스 `AddClass` 메서드가 있는 `Add` 네임 스페이스의 멤버인 `UtilityMethods`합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="61ae5-110">`Mult`메서드를 포함 하는 소스 코드: `Multiply`합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="61ae5-111">매개 변수의 곱을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-111">It returns the product of its parameters.</span></span> <span data-ttu-id="61ae5-112">클래스 `MultiplyClass` 메서드가 있는 `Multiply` 네임 스페이스의 멤버 이기도 `UtilityMethods`합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="61ae5-113">`TestCode`: 포함 된 파일은 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="61ae5-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="61ae5-114">합계 및 제품의 런타임 인수를 계산 하는 DLL 파일의 메서드 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61ae5-115">예제</span><span class="sxs-lookup"><span data-stu-id="61ae5-115">Example</span></span>  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 <span data-ttu-id="61ae5-116">이 파일에 DLL 메서드를 사용 하는 알고리즘 `Add` 및 `Multiply`합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="61ae5-117">명령줄에 입력 된 구문 분석 `num1` 및 `num2`합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="61ae5-118">사용 하 여 합계를 계산한 다음는 `Add` 메서드를는 `AddClass` 클래스 및 사용 하 여 제품의 `Multiply` 메서드를는 `MultiplyClass` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="61ae5-119">다음에 유의 `Imports` 파일의 시작 부분에 문을 컴파일할 때 DLL 메서드를 다음과 같이 참조를 정규화 되지 않은 클래스 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="61ae5-120">그렇지 않은 경우 다음과 같이 정규화 된 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="61ae5-121">실행</span><span class="sxs-lookup"><span data-stu-id="61ae5-121">Execution</span></span>  
 <span data-ttu-id="61ae5-122">프로그램을 실행 하려면 다음과 같이 두 개의 숫자를 다음 EXE 파일의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="61ae5-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="61ae5-123">Compiling the Code</span></span>  
 <span data-ttu-id="61ae5-124">파일을 빌드하려면 `MathLibrary.DLL`, 두 개의 파일을 컴파일할 `Add` 및 `Mult` 다음 명령줄을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```vb  
vbc /target:library /out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="61ae5-125">[/target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) 컴파일러 옵션 EXE 파일 대신 DLL을 출력 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-125">The [/target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="61ae5-126">[/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) 파일 이름이 옵니다 컴파일러 옵션은 DLL 파일 이름을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-126">The [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="61ae5-127">컴파일러는 첫 번째 파일을 사용 하는 그렇지 않은 경우 (`Add.vb`) DLL의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="61ae5-128">실행 파일을 빌드합니다 `TestCode.exe`, 다음 명령줄을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```vb  
vbc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="61ae5-129">**/출력** 컴파일러 옵션 EXE 파일을 출력 하도록 컴파일러에 지시 하 고 출력 파일의 이름을 지정 합니다 (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="61ae5-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="61ae5-130">이 컴파일러 옵션은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-130">This compiler option is optional.</span></span> <span data-ttu-id="61ae5-131">[/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) 컴파일러 옵션에이 프로그램을 사용 하는 DLL 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-131">The [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="61ae5-132">명령줄에서 빌드에 대 한 자세한 내용은 참조 및 [명령줄에서 빌드](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61ae5-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ae5-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61ae5-133">See Also</span></span>  
 <span data-ttu-id="61ae5-134">[프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="61ae5-134">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="61ae5-135"> [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="61ae5-135"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="61ae5-136"> [DLL 함수가 포함 된 클래스 만들기](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)</span><span class="sxs-lookup"><span data-stu-id="61ae5-136"> [Creating a Class to Hold DLL Functions](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)</span></span>
