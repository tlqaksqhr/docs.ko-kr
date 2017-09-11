---
title: "Main() 반환 값(C# 프로그래밍 가이드)"
ms.date: 2017-08-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: d019d1c5757a961c03439d756e808ae13fd8a67b
ms.openlocfilehash: 50943bdd0b7726145797faf82719537a388dad89
ms.contentlocale: ko-kr
ms.lasthandoff: 08/03/2017

---

# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="e7c99-102">Main() 반환 값(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e7c99-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="e7c99-103">`Main` 메서드는 `void`를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-103">The `Main` method can return `void`:</span></span>

<span data-ttu-id="e7c99-104">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7c99-104">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]</span></span>

<span data-ttu-id="e7c99-105">`int`를 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-105">It can also return an `int`:</span></span>

<span data-ttu-id="e7c99-106">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7c99-106">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]</span></span>

<span data-ttu-id="e7c99-107">`Main`의 반환 값을 사용하지 않는 경우 `void`를 반환하면 코드가 다소 단순해집니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-107">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="e7c99-108">그러나 정수를 반환하면 프로그램이 실행 파일을 호출하는 다른 프로그램 또는 스크립트에 상태 정보를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-108">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="e7c99-109">`Main`의 반환 값은 프로세스에 대한 종료 코드로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-109">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="e7c99-110">다음 예제에서는 `Main`의 반환 값을 어떻게 액세스할 수 있는지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-110">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="e7c99-111">예제</span><span class="sxs-lookup"><span data-stu-id="e7c99-111">Example</span></span>

<span data-ttu-id="e7c99-112">이 예제에서는 [.NET Core](../../../core/index.md) 명령줄 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-112">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="e7c99-113">.NET Core 명령줄 도구에 대해 잘 모르는 경우 이 [시작 항목](../../../core/tutorials/using-with-xplat-cli.md)에서 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-113">If you are unfamilar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/using-with-xplat-cli.md).</span></span>

<span data-ttu-id="e7c99-114">*program.cs* 에서 `Main` 메서드를 다음과 같이 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-114">Modify the `Main` method in *program.cs* as follows:</span></span>

<span data-ttu-id="e7c99-115">[!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e7c99-115">[!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]</span></span>

<span data-ttu-id="e7c99-116">Windows에서 프로그램을 실행하는 경우 `Main` 함수에서 반환된 값은 환경 변수에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-116">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="e7c99-117">이 환경 변수는 배치 파일에서 `ERRORLEVEL`을 사용하거나 PowerShell에서 `$LastExitCode`를 사용하여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-117">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="e7c99-118">[dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` 명령을 사용하여 응용 프로그램을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-118">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="e7c99-119">다음으로 응용 프로그램을 실행하고 결과를 표시하는 PowerShell 스크립트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-119">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="e7c99-120">다음 코드를 텍스트 파일에 붙여넣고 이 파일을 프로젝트가 포함된 폴더에 `test.ps1`로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-120">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="e7c99-121">PowerShell 프롬프트에 `test.ps1`을 입력하여 PowerShell 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-121">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="e7c99-122">코드에서 0을 반환하기 때문에 배치 파일이 성공했다고 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-122">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="e7c99-123">그러나 0이 아닌 값을 반환하도록 MainReturnValTest.cs를 변경한 다음 프로그램을 다시 컴파일하면 다음에 PowerShell 스크립트를 실행할 때 오류가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-123">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

```powershell
dotnet run
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="e7c99-124">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="e7c99-124">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="e7c99-125">비동기 Main 반환 값</span><span class="sxs-lookup"><span data-stu-id="e7c99-125">Async Main return values</span></span>

<span data-ttu-id="e7c99-126">비동기 Main 반환 값은 `Main`에서 비동기 메서드를 호출하는 데 필요한 상용구 코드를 컴파일러에서 생성하는 코드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-126">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="e7c99-127">기존에는 이 구문을 작성하여 비동기 코드를 호출하고 비동기 작업이 완료될 때까지 프로그램이 실행되는지 확인해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-127">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

<span data-ttu-id="e7c99-128">이제는 이 구문을 다음으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-128">Now, this can be replaced by:</span></span>

<span data-ttu-id="e7c99-129">[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]</span><span class="sxs-lookup"><span data-stu-id="e7c99-129">[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]</span></span>

<span data-ttu-id="e7c99-130">새 구문의 장점은 컴파일러에서 항상 올바른 코드를 생성한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-130">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="e7c99-131">컴파일러 생성 코드</span><span class="sxs-lookup"><span data-stu-id="e7c99-131">Compiler generated code</span></span>

<span data-ttu-id="e7c99-132">응용 프로그램 진입점에서 `Task` 또는 `Task<int>`를 반환하는 경우 컴파일러는 응용 프로그램 코드에서 선언된 진입점 메서드를 호출하는 새 진입점을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-132">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="e7c99-133">이 진입점이 `$GeneratedMain`이라고 가정하면 컴파일러는 이러한 진입점에 대해 다음 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-133">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="e7c99-134">`static Task Main()` - 컴파일러에서 `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-134">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="e7c99-135">`static Task Main(string[])` - 컴파일러에서 `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-135">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="e7c99-136">`static Task<int> Main()` - 컴파일러에서 `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-136">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="e7c99-137">`static Task<int> Main(string[])` - 컴파일러에서 `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`에 해당하는 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-137">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="e7c99-138">예제에서 `Main` 메서드에 `async` 한정자를 사용하더라도 컴파일러는 동일한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e7c99-138">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7c99-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7c99-139">See also</span></span>
<span data-ttu-id="e7c99-140">[C# 프로그래밍 가이드](../../programming-guide/index.md)
[C# 참조](../index.md)
[Main()과 명령줄 인수](index.md)
[방법: 명령줄 인수 표시](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[방법: foreach를 사용하여 명령줄 인수 액세스](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span><span class="sxs-lookup"><span data-stu-id="e7c99-140">[C# Programming Guide](../../programming-guide/index.md)
[C# Reference](../index.md)
[Main() and Command-Line Arguments](index.md)
[How to: Display Command Line Arguments](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[How to: Access Command-Line Arguments Using foreach](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span></span>

