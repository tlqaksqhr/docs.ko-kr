---
title: F# Interactive(fsi.exe) 참조
description: 'F # Interactive (fsi.exe) 사용량 콘솔에 F # 코드를 대화형으로 실행 하거나 F # 스크립트를 실행 하에 대해 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e745562e4165ce6744fcb6d07268b1a5761194aa
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="b7ab3-103">F#을 사용한 대화형 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b7ab3-103">Interactive Programming with F#</span></span> #

> [!NOTE]
<span data-ttu-id="b7ab3-104">이 문서에서는 현재 Windows만을 위한 환경에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-104">This article currently describes the experience for Windows only.</span></span>  <span data-ttu-id="b7ab3-105">다시 작성될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-105">It will be rewritten.</span></span>

> [!NOTE]
<span data-ttu-id="b7ab3-106">API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-106">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="b7ab3-107">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-107">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="b7ab3-108">F# Interactive(fsi.exe)는 콘솔에서 F# 코드를 대화형으로 실행하거나 F# 스크립트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-108">F# Interactive (fsi.exe) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="b7ab3-109">즉, F# Interactive는 F# 언어에 대해 REPL(읽기, 평가, 인쇄 루프)을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-109">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="b7ab3-110">콘솔에서 F# Interactive를 실행하려면 fsi.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-110">To run F# Interactive from the console, run fsi.exe.</span></span>  <span data-ttu-id="b7ab3-111">Fsi.exe에 "c:\Program 파일 (x86) \Microsoft SDKs\F#\<버전 > \Framework\<버전 >\"합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-111">You will find fsi.exe in "c:\Program Files (x86)\Microsoft SDKs\F#\<version>\Framework\<version>\".</span></span> <span data-ttu-id="b7ab3-112">사용 가능한 명령줄 옵션에 대한 정보는 [F# Interactive Options](../../language-reference/fsharp-interactive-options.md)(F# Interactive 옵션)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-112">For information about command line options available, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

<span data-ttu-id="b7ab3-113">Visual Studio를 통해 F# Interactive를 실행하려면 **F# Interactive**라는 레이블이 있는 적절한 도구 모음 단추를 클릭하거나 **Ctrl+Alt+F** 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-113">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive**, or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="b7ab3-114">이렇게 하면 대화형 창(F# Interactive 세션을 실행하는 도구 창)이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-114">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="b7ab3-115">대화형 창에서 실행할 코드를 선택하고 **Alt+Enter** 키 조합을 눌러도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-115">You can also select some code that you want to run in the interactive window and hit the key combination **ALT+ENTER**.</span></span> <span data-ttu-id="b7ab3-116">그러면 레이블이 **F# Interactive**인 도구 창에서 F# Interactive가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-116">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="b7ab3-117">이 키 조합을 사용할 때 편집기 창에 포커스가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-117">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="b7ab3-118">콘솔을 사용하든 Visual Studio를 사용하든 상관없이 명령 프롬프트가 나타납니다. 해석기를 실행하려면 사용자가 이 명령 프롬프트에 필요한 사항을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-118">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="b7ab3-119">코드 파일에서와 같은 방법으로 코드를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-119">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="b7ab3-120">코드를 컴파일하고 실행하려면 세미콜론 두 개(**;;**)를 입력하여 입력 줄 하나 또는 여러 개를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-120">To compile and execute the code, enter two semicolons (**;;**) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="b7ab3-121">F# Interactive가 코드 컴파일을 시도하며, 컴파일이 성공하면 코드를 실행하고 컴파일된 형식과 값의 서명을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-121">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="b7ab3-122">오류가 발생하면 해석기에 오류 메시지가 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-122">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="b7ab3-123">프로그램을 빌드할 수 있도록 동일한 세션에서 입력한 코드는 이전에 입력된 모든 구문에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-123">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="b7ab3-124">도구 창에서는 확장 버퍼가 제공되므로 필요한 경우 파일에 코드를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-124">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="b7ab3-125">F# Interactive는 Visual Studio에서 실행할 때 프로젝트와 독립적으로 실행되므로 예를 들어 함수의 코드를 대화형 창에 복사하지 않으면 프로젝트에 정의한 구문을 F# Interactive에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-125">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="b7ab3-126">일부 라이브러리를 참조하는 프로젝트를 연 경우, F# Interactive에서 **솔루션 탐색기**를 통해 해당 프로젝트를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-126">If you have a project open that references some libraries, you can reference these in F# Interactive through **Solution Explorer**.</span></span> <span data-ttu-id="b7ab3-127">F# Interactive에서 라이브러리를 참조하려면 **참조** 노드를 확장하고, 라이브러리에 대한 바로 가기 메뉴를 열고, **F# Interactive로 보내기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-127">To reference a library in F# Interactive, expand the **References** node, open the shortcut menu for the library, and choose **Send to F# Interactive**.</span></span>

<span data-ttu-id="b7ab3-128">설정을 조정하여 F# Interactive 명령줄 인수(옵션)를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-128">You can control the F# Interactive command line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="b7ab3-129">이렇게 하려면 **도구** 메뉴에서 **옵션...** 을 선택하고 **F# 도구**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-129">On the **Tools** menu, select **Options...**, and then expand **F# Tools**.</span></span> <span data-ttu-id="b7ab3-130">변경 가능한 두 가지 설정은 F# Interactive 옵션과 **64비트 F# Interactive** 설정(F# Interactive를 64비트 컴퓨터에서 실행하는 경우만 해당)입니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-130">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="b7ab3-131">이 설정은 전용 64비트 버전의 fsi.exe 또는 fsianycpu.exe(컴퓨터 아키텍처를 사용하여 32비트 또는 64비트 프로세스로 실행할지 여부를 결정)를 실행할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-131">This setting determines whether you want to run the dedicated 64-bit version of fsi.exe or fsianycpu.exe, which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>


## <a name="scripting-with-f"></a><span data-ttu-id="b7ab3-132">F#을 사용한 스크립팅</span><span class="sxs-lookup"><span data-stu-id="b7ab3-132">Scripting with F#</span></span> #
<span data-ttu-id="b7ab3-133">스크립트는 파일 확장명 **.fsx** 또는 **.fsscript**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-133">Scripts use the file extension **.fsx** or **.fsscript**.</span></span> <span data-ttu-id="b7ab3-134">소스 코드를 컴파일한 다음 나중에 컴파일된 어셈블리를 실행하는 대신 **fsi.exe**를 실행하고 F# 소스 코드의 스크립트 파일 이름을 지정하면 F# Interactive가 코드를 읽어 실시간으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-134">Instead of compiling source code and then later running the compiled assembly, you can just run **fsi.exe** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span>


## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a><span data-ttu-id="b7ab3-135">대화형, 스크립팅 및 컴파일된 환경의 차이점</span><span class="sxs-lookup"><span data-stu-id="b7ab3-135">Differences Between the Interactive, Scripting and Compiled Environments</span></span>
<span data-ttu-id="b7ab3-136">F# Interactive에서 코드를 컴파일할 때는 대화형으로 실행하든 스크립트를 실행하든 관계없이 **INTERACTIVE** 기호가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-136">When you are compiling code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="b7ab3-137">컴파일러에서 코드를 컴파일할 때는 **COMPILED** 기호가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-137">When you are compiling code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="b7ab3-138">따라서 컴파일된 모드와 대화형 모드에서 코드가 달라야 하는 경우 조건부 컴파일용 전처리기 지시문을 통해 사용할 코드를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-138">Thus, if code needs to be different in compiled and interactive modes, you can use preprocessor directives for conditional compilation to determine which to use.</span></span>

<span data-ttu-id="b7ab3-139">F# Interactive에서 스크립트를 실행할 때는 컴파일러에서 실행하는 경우 제공되지 않는 일부 지시문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-139">Some directives are available when you are executing scripts in F# Interactive that are not available when you are executing the compiler.</span></span> <span data-ttu-id="b7ab3-140">다음 표에는 F# Interactive를 사용할 때 제공되는 지시문이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-140">The following table summarizes directives that are available when you are using F# Interactive.</span></span>

|<span data-ttu-id="b7ab3-141">지시문</span><span class="sxs-lookup"><span data-stu-id="b7ab3-141">Directive</span></span>|<span data-ttu-id="b7ab3-142">설명</span><span class="sxs-lookup"><span data-stu-id="b7ab3-142">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="b7ab3-143">**#help**</span><span class="sxs-lookup"><span data-stu-id="b7ab3-143">**#help**</span></span>|<span data-ttu-id="b7ab3-144">사용 가능한 지시문에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-144">Displays information about available directives.</span></span>|
|<span data-ttu-id="b7ab3-145">**#I**</span><span class="sxs-lookup"><span data-stu-id="b7ab3-145">**#I**</span></span>|<span data-ttu-id="b7ab3-146">어셈블리 검색 경로를 따옴표로 묶어 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-146">Specifies an assembly search path in quotation marks.</span></span>|
|<span data-ttu-id="b7ab3-147">**#load**</span><span class="sxs-lookup"><span data-stu-id="b7ab3-147">**#load**</span></span>|<span data-ttu-id="b7ab3-148">소스 파일을 읽고 컴파일한 다음 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-148">Reads a source file, compiles it, and runs it.</span></span>|
|<span data-ttu-id="b7ab3-149">**#quit**</span><span class="sxs-lookup"><span data-stu-id="b7ab3-149">**#quit**</span></span>|<span data-ttu-id="b7ab3-150">F# Interactive 세션을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-150">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="b7ab3-151">**#r**</span><span class="sxs-lookup"><span data-stu-id="b7ab3-151">**#r**</span></span>|<span data-ttu-id="b7ab3-152">어셈블리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-152">References an assembly.</span></span>|
|<span data-ttu-id="b7ab3-153">**#time ["on"&#124;"off"]**</span><span class="sxs-lookup"><span data-stu-id="b7ab3-153">**#time ["on"&#124;"off"]**</span></span>|<span data-ttu-id="b7ab3-154">**#time** 자체는 성능 정보 표시 여부를 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-154">By itself, **#time** toggles whether to display performance information.</span></span> <span data-ttu-id="b7ab3-155">이 지시문을 사용하도록 설정하면 F# Interactive가 해석 및 실행되는 각 코드 섹션에 대해 실제 시간, CPU 시간 및 가비지 컬렉션 정보를 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-155">When it is enabled, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="b7ab3-156">F# Interactive에서 파일 또는 경로를 지정할 때는 문자열 리터럴이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-156">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="b7ab3-157">따라서 파일 및 경로를 따옴표로 묶어야 하며, 일반적인 이스케이프 문자가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-157">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="b7ab3-158">또한 @ 문자를 사용하여 F# Interactive가 경로를 포함하는 문자열을 축자 문자열로 해석하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-158">Also, you can use the @ character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="b7ab3-159">그러면 F# Interactive에서 이스케이프 문자를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-159">This causes F# Interactive to ignore any escape characters.</span></span>

<span data-ttu-id="b7ab3-160">컴파일된 모드와 대화형 모드 간의 차이점 중 하나는 명령줄 인수에 액세스하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-160">One of the differences between compiled and interactive mode is the way you access command line arguments.</span></span> <span data-ttu-id="b7ab3-161">컴파일된 모드에서 **System.Environment.GetCommandLineArgs**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-161">In compiled mode, use **System.Environment.GetCommandLineArgs**.</span></span> <span data-ttu-id="b7ab3-162">스크립트에서는 **fsi.CommandLineArgs**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-162">In scripts, use **fsi.CommandLineArgs**.</span></span>

<span data-ttu-id="b7ab3-163">다음 코드에서는 스크립트에서 명령줄 인수를 읽는 함수를 만드는 방법과 스크립트에서 다른 어셈블리를 참조하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-163">The following code illustrates how to create a function that reads the command line arguments in a script and also demonstrates how to reference another assembly from a script.</span></span> <span data-ttu-id="b7ab3-164">첫 번째 코드 파일인 **MyAssembly.fs**는 참조되는 어셈블리의 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-164">The first code file, **MyAssembly.fs**, is the code for the assembly being referenced.</span></span> <span data-ttu-id="b7ab3-165">**fsc-a MyAssembly.fs** 명령줄을 사용하여 이 파일을 컴파일한 다음 **fsi-exec file1.fsx** 테스트 명령줄을 사용하여 두 번째 파일을 스크립트로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-165">Compile this file with the command line: **fsc -a MyAssembly.fs** and then execute the second file as a script with the command line: **fsi --exec file1.fsx** test</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="b7ab3-166">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-166">The output is as follows:</span></span>

```
Command line arguments: 
file1.fsx
test
60
```

## <a name="related-topics"></a><span data-ttu-id="b7ab3-167">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b7ab3-167">Related Topics</span></span>

|<span data-ttu-id="b7ab3-168">제목</span><span class="sxs-lookup"><span data-stu-id="b7ab3-168">Title</span></span>|<span data-ttu-id="b7ab3-169">설명</span><span class="sxs-lookup"><span data-stu-id="b7ab3-169">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="b7ab3-170">F# Interactive 옵션</span><span class="sxs-lookup"><span data-stu-id="b7ab3-170">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="b7ab3-171">명령줄 구문 및 F # Interactive에 대 한 옵션을 설명 fsi.exe 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-171">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
|[<span data-ttu-id="b7ab3-172">F# Interactive 라이브러리 참조</span><span class="sxs-lookup"><span data-stu-id="b7ab3-172">F# Interactive Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-interactive-library-reference)|<span data-ttu-id="b7ab3-173">F# Interactive에서 코드를 실행할 때 사용할 수 있는 라이브러리 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7ab3-173">Describes library functionality available when executing code in F# interactive.</span></span>|
