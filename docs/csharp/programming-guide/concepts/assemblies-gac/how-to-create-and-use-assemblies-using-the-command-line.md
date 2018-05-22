---
title: '방법: 명령줄을 사용하여 어셈블리 만들기 및 사용(C#)'
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: ef872992f17eaaeacf451fa10ef792c47445df80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="b12f5-102">방법: 명령줄을 사용하여 어셈블리 만들기 및 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="b12f5-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="b12f5-103">어셈블리 또는 DLL(동적 연결 라이브러리)은 런타임 시 프로그램에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="b12f5-104">DLL 빌드 및 사용을 보여 주려면 다음 시나리오를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="b12f5-105">`MathLibrary.DLL`: 런타임 시 호출할 메서드가 포함된 라이브러리 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="b12f5-106">이 예제의 DLL에는 두 개의 메서드 `Add` 및 `Multiply`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="b12f5-107">`Add`: `Add` 메서드가 포함된 소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="b12f5-108">해당 매개 변수의 합계를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="b12f5-109">`Add` 메서드가 포함된 `AddClass` 클래스는 `UtilityMethods` 네임스페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="b12f5-110">`Mult`: `Multiply` 메서드가 포함된 소스 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="b12f5-111">매개 변수의 곱을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-111">It returns the product of its parameters.</span></span> <span data-ttu-id="b12f5-112">`Multiply` 메서드가 포함된 `MultiplyClass` 클래스는 `UtilityMethods` 네임스페이스의 멤버이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="b12f5-113">`TestCode`: `Main` 메서드가 포함된 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="b12f5-114">DLL 파일의 메서드를 사용하여 런타임 인수의 합계와 곱을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b12f5-115">예</span><span class="sxs-lookup"><span data-stu-id="b12f5-115">Example</span></span>  
  
```csharp  
// File: Add.cs   
namespace UtilityMethods  
{  
    public class AddClass   
    {  
        public static long Add(long i, long j)   
        {   
            return (i + j);  
        }  
    }  
}  
```  
  
```csharp  
// File: Mult.cs  
namespace UtilityMethods   
{  
    public class MultiplyClass  
    {  
        public static long Multiply(long x, long y)   
        {  
            return (x * y);   
        }  
    }  
}  
```  
  
```csharp  
// File: TestCode.cs  
  
using UtilityMethods;  
  
class TestCode  
{  
    static void Main(string[] args)   
    {  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:");  
  
        if (args.Length != 2)  
        {  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>");  
            return;  
        }  
  
        long num1 = long.Parse(args[0]);  
        long num2 = long.Parse(args[1]);  
  
        long sum = AddClass.Add(num1, num2);  
        long product = MultiplyClass.Multiply(num1, num2);  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum);  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product);  
    }  
}  
/* Output (assuming 1234 and 5678 are entered as command-line arguments):  
    Calling methods from MathLibrary.DLL:  
    1234 + 5678 = 6912  
    1234 * 5678 = 7006652          
*/  
```  
  
 <span data-ttu-id="b12f5-116">이 파일에는 DLL 메서드 `Add` 및 `Multiply`를 사용하는 알고리즘이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="b12f5-117">명령줄에서 입력된 인수 `num1` 및 `num2`의 구문 분석으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="b12f5-118">그런 다음 `AddClass` 클래스의 `Add` 메서드를 사용하여 합계를 계산하고 `MultiplyClass` 클래스의 `Multiply` 메서드를 사용하여 곱을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="b12f5-119">파일의 시작 부분에 `using` 지시문을 사용하면 정규화되지 않은 클래스 이름을 통해 컴파일 시간에 DLL 메서드를 다음과 같이 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="b12f5-120">사용하지 않을 경우 정규화된 이름을 다음과 같이 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="b12f5-121">실행</span><span class="sxs-lookup"><span data-stu-id="b12f5-121">Execution</span></span>  
 <span data-ttu-id="b12f5-122">프로그램을 실행하려면 다음과 같이 EXE 파일의 이름과 두 개의 숫자를 차례로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b12f5-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b12f5-123">Compiling the Code</span></span>  
 <span data-ttu-id="b12f5-124">`MathLibrary.DLL` 파일을 빌드하려면 다음 명령줄을 사용하여 두 개의 파일 `Add` 및 `Mult`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 <span data-ttu-id="b12f5-125">[/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) 컴파일러 옵션은 EXE 파일 대신 DLL을 출력하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-125">The [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="b12f5-126">[/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) 컴파일러 옵션은 DLL 파일 이름을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-126">The [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="b12f5-127">사용하지 않을 경우 컴파일러는 첫 번째 파일(`Add.cs`)을 DLL의 이름으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-127">Otherwise, the compiler uses the first file (`Add.cs`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="b12f5-128">실행 파일 `TestCode.exe`를 빌드하려면 다음 명령줄을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 <span data-ttu-id="b12f5-129">**/out** 컴파일러 옵션은 EXE 파일을 출력하도록 컴파일러에 지시하고 출력 파일의 이름(`TestCode.exe`)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="b12f5-130">이 컴파일러 옵션은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-130">This compiler option is optional.</span></span> <span data-ttu-id="b12f5-131">[/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 컴파일러 옵션은 이 프로그램이 사용하는 DLL 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b12f5-131">The [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option specifies the DLL file or files that this program uses.</span></span> <span data-ttu-id="b12f5-132">자세한 내용은 [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b12f5-132">For more information, see [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="b12f5-133">명령줄에서 빌드하는 방법에 대한 자세한 내용은 [csc.exe를 사용한 명령줄 빌드](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b12f5-133">For more information about building from the command line, see [Command-line Building With csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b12f5-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b12f5-134">See Also</span></span>  
 [<span data-ttu-id="b12f5-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b12f5-135">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b12f5-136">어셈블리 및 전역 어셈블리 캐시(C#)</span><span class="sxs-lookup"><span data-stu-id="b12f5-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="b12f5-137">DLL 함수가 포함된 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="b12f5-137">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
