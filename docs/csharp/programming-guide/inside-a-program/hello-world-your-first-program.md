---
title: "Hello World -- 프로그램 처음 만들기(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: get-started-article
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
dev_langs:
- CSharp
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
caps.latest.revision: 39
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
ms.sourcegitcommit: b7cb84362c96dac50ae5136334138b55ed1ce00b
ms.openlocfilehash: 03891f83885cf41ab157ebd78ef7e72767b4b163
ms.contentlocale: ko-kr
ms.lasthandoff: 07/31/2017

---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="d646c-102">Hello World -- 프로그램 처음 만들기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d646c-102">Hello World -- Your First Program (C# Programming Guide)</span></span>
<span data-ttu-id="d646c-103">다음 절차에서는 기존 "Hello World!" 프로그램의 C# 버전을</span><span class="sxs-lookup"><span data-stu-id="d646c-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="d646c-104">만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-104">program.</span></span> <span data-ttu-id="d646c-105">이 프로그램은 문자열 `Hello World!`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-105">The program displays the string `Hello World!`</span></span>  
  
 <span data-ttu-id="d646c-106">소개 개념에 대한 추가 예제는 [Visual C# 및 Visual Basic 시작](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d646c-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="d646c-107">콘솔 응용 프로그램을 만들고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d646c-107">To create and run a console application</span></span>  
  
1.  <span data-ttu-id="d646c-108">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-108">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d646c-109">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="d646c-110">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-110">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="d646c-111">**설치됨**, **템플릿**, **Visual C#**을 차례로 확장하고 **콘솔 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4.  <span data-ttu-id="d646c-112">**이름** 상자에 프로젝트의 이름을 지정하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="d646c-113">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-113">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="d646c-114">Program.cs가 **코드 편집기**에 열려 있지 않으면 **솔루션 탐색기**에서 **Program.cs**의 바로 가기 메뉴를 열고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="d646c-115">Program.cs의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-115">Replace the contents of Program.cs with the following code.</span></span>  
  
     <span data-ttu-id="d646c-116">[!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d646c-116">[!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]</span></span>  
  
7.  <span data-ttu-id="d646c-117">F5 키를 선택하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-117">Choose the F5 key to run the project.</span></span> <span data-ttu-id="d646c-118">`Hello World!` 줄이 포함된 명령 프롬프트 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-118">A Command Prompt window appears that contains the line `Hello World!`</span></span>  
  
 <span data-ttu-id="d646c-119">다음으로 이 프로그램의 중요 경로가 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-119">Next, the important parts of this program are examined.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="d646c-120">설명</span><span class="sxs-lookup"><span data-stu-id="d646c-120">Comments</span></span>  
 <span data-ttu-id="d646c-121">첫 번째 줄에는 설명이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-121">The first line contains a comment.</span></span> <span data-ttu-id="d646c-122">`//` 문자는 줄의 나머지 부분을 설명으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-122">The characters `//` convert the rest of the line to a comment.</span></span>  
  
 <span data-ttu-id="d646c-123">[!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d646c-123">[!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]</span></span>  
  
 <span data-ttu-id="d646c-124">텍스트 블록을 `/*` 및 `*/` 문자 사이에 포함하여 주석으로 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-124">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="d646c-125">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-125">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="d646c-126">[!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="d646c-126">[!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]</span></span>  
  
## <a name="main-method"></a><span data-ttu-id="d646c-127">Main 메서드</span><span class="sxs-lookup"><span data-stu-id="d646c-127">Main Method</span></span>  
 <span data-ttu-id="d646c-128">C# 콘솔 응용 프로그램에는 시작 및 끝을 제어하는 `Main` 메서드가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-128">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="d646c-129">`Main` 메서드에서 개체를 만들고 다른 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-129">The `Main` method is where you create objects and execute other methods.</span></span>  
  
 <span data-ttu-id="d646c-130">`Main` 메서드는 클래스나 구조체 내부에 있는 [정적](../../../csharp/language-reference/keywords/static.md) 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-130">The `Main` method is a [static](../../../csharp/language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="d646c-131">이전 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="d646c-131">In the previous "Hello World!"</span></span> <span data-ttu-id="d646c-132">예제에서 이 메서드는 `Hello` 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-132">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="d646c-133">다음 방법 중 하나로 `Main` 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-133">You can declare the `Main` method in one of the following ways:</span></span>  
  
-   <span data-ttu-id="d646c-134">이 메서드는 `void`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-134">It can return `void`.</span></span>  
  
     <span data-ttu-id="d646c-135">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="d646c-135">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]</span></span>  
  
-   <span data-ttu-id="d646c-136">정수를 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-136">It can also return an integer.</span></span>  
  
     <span data-ttu-id="d646c-137">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="d646c-137">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]</span></span>  
  
-   <span data-ttu-id="d646c-138">반환 형식은 각각 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-138">With either of the return types, it can take arguments.</span></span>  
  
     <span data-ttu-id="d646c-139">[!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="d646c-139">[!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]</span></span>  
  
     <span data-ttu-id="d646c-140">또는</span><span class="sxs-lookup"><span data-stu-id="d646c-140">-or-</span></span>  
  
     <span data-ttu-id="d646c-141">[!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="d646c-141">[!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]</span></span>  
  
 <span data-ttu-id="d646c-142">`Main` 메서드의 매개 변수 `args`는 프로그램을 호출하는 데 사용된 명령줄 인수가 포함된 `string` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-142">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="d646c-143">C++의 경우와는 달리 배열에 실행(exe) 파일의 이름이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-143">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>  
  
 <span data-ttu-id="d646c-144">명령줄 인수를 사용하는 방법에 대한 자세한 내용은 [Main() 및 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/index.md) 및 [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)(방법: 명령줄을 사용하여 어셈블리 만들기 및 사용)의 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d646c-144">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span></span>  
  
 <span data-ttu-id="d646c-145">`Main` 메서드가 끝날 때 <xref:System.Console.ReadKey%2A>를 호출하면 프로그램을 디버그 모드에서 실행할 경우 F5 키를 눌러 출력을 읽을 수 있게 될 때까지 콘솔 창이 닫히지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-145">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>  
  
## <a name="input-and-output"></a><span data-ttu-id="d646c-146">입력 및 출력</span><span class="sxs-lookup"><span data-stu-id="d646c-146">Input and Output</span></span>  
 <span data-ttu-id="d646c-147">일반적으로 C# 프로그램에서는 .NET Framework의 런타임 라이브러리에서 제공되는 입출력 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-147">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="d646c-148">`System.Console.WriteLine("Hello World!");` 문은 <xref:System.Console.WriteLine%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-148">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="d646c-149">이 메서드는 런타임 라이브러리에 있는 <xref:System.Console> 클래스의 출력 메서드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-149">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="d646c-150">이 메서드는 표준 출력 스트림에 문자열 매개 변수를 표시하고 이어서 새 줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-150">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="d646c-151">기타 <xref:System.Console> 메서드는 다양한 입력 및 출력 작업에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-151">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="d646c-152">프로그램 시작 부분에 `using System;` 지시문을 포함하면 <xref:System> 클래스 및 메서드를 정규화하지 않고 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-152">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="d646c-153">예를 들어 `System.Console.WriteLine` 대신 `Console.WriteLine`을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-153">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>  
  
 <span data-ttu-id="d646c-154">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="d646c-154">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]</span></span>  
  
 <span data-ttu-id="d646c-155">[!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="d646c-155">[!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]</span></span>  
  
 <span data-ttu-id="d646c-156">입출력 메서드에 대한 자세한 내용은 <xref:System.IO>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d646c-156">For more information about input/output methods, see <xref:System.IO>.</span></span>  
  
## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="d646c-157">명령줄 컴파일 및 실행</span><span class="sxs-lookup"><span data-stu-id="d646c-157">Command-Line Compilation and Execution</span></span>  
 <span data-ttu-id="d646c-158">"Hello World!"</span><span class="sxs-lookup"><span data-stu-id="d646c-158">You can compile the "Hello World!"</span></span> <span data-ttu-id="d646c-159">프로그램을 컴파일하려면 Visual Studio IDE(통합 개발 환경) 대신 명령줄을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-159">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>  
  
#### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="d646c-160">명령 프롬프트에서 컴파일 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d646c-160">To compile and run from a command prompt</span></span>  
  
1.  <span data-ttu-id="d646c-161">이전 절차의 코드를 텍스트 편집기에 붙여넣고 파일을 텍스트 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-161">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="d646c-162">파일 이름을 `Hello.cs`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-162">Name the file `Hello.cs`.</span></span> <span data-ttu-id="d646c-163">C# 소스 코드 파일에는 `.cs` 확장명이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-163">C# source code files use the extension `.cs`.</span></span>  
  
2.  <span data-ttu-id="d646c-164">다음 단계 중 하나를 수행하여 명령 프롬프트 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-164">Perform one of the following steps to open a command-prompt window:</span></span>  
  
    -   <span data-ttu-id="d646c-165">Windows 10의 경우 **시작** 메뉴에서 `Developer Command Prompt`를 검색하고 **VS 2017용 개발자 명령 프롬프트**를 탭하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-165">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="d646c-166">개발자 명령 프롬프트 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-166">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="d646c-167">Windows 7의 경우 **시작** 메뉴를 열고, Visual Studio 현재 버전의 폴더를 확장하고, **Visual Studio Tools**의 바로 가기 메뉴를 열고 나서, **VS 2017용 개발자 명령 프롬프트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-167">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="d646c-168">개발자 명령 프롬프트 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-168">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="d646c-169">표준 명령 프롬프트 창에서 명령줄 빌드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-169">Enable command-line builds from a standard Command Prompt window.</span></span>  
  
         <span data-ttu-id="d646c-170">[방법: Visual Studio 명령줄에 필요한 환경 변수 설정](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d646c-170">See [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>  
  
3.  <span data-ttu-id="d646c-171">명령 프롬프트 창에서 `Hello.cs` 파일이 포함된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-171">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>  
  
4.  <span data-ttu-id="d646c-172">다음 명령을 입력하여 `Hello.cs`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-172">Enter the following command to compile `Hello.cs`.</span></span>  
  
     `csc Hello.cs`  
  
     <span data-ttu-id="d646c-173">프로그램에 컴파일 오류가 없으면 `Hello.exe`라는 실행 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-173">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>  
  
5.  <span data-ttu-id="d646c-174">명령 프롬프트 창에서 다음 명령을 입력하여 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d646c-174">In the command-prompt window, enter the following command to run the program:</span></span>  
  
     `Hello`  
  
 <span data-ttu-id="d646c-175">C# 컴파일러 및 관련 옵션에 대한 자세한 내용은 [C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d646c-175">For more information about the C# compiler and its options, see [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d646c-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d646c-176">See Also</span></span>  
 <span data-ttu-id="d646c-177">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d646c-177">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d646c-178">[C# 프로그램 내부](../../../csharp/programming-guide/inside-a-program/index.md) </span><span class="sxs-lookup"><span data-stu-id="d646c-178">[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md) </span></span>  
 <span data-ttu-id="d646c-179">[문자열](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="d646c-179">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="d646c-180">[\<paveover>C# 샘플 응용 프로그램](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15) </span><span class="sxs-lookup"><span data-stu-id="d646c-180">[\<paveover>C# Sample Applications](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15) </span></span>  
 <span data-ttu-id="d646c-181">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d646c-181">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d646c-182">[Main()과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="d646c-182">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 [<span data-ttu-id="d646c-183">Visual C# 및 Visual Basic 시작</span><span class="sxs-lookup"><span data-stu-id="d646c-183">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)

