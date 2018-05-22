---
title: csc.exe를 사용한 명령줄 빌드
ms.date: 04/19/2017
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
ms.openlocfilehash: 3cd49a17991f3d7606b0364a83be2b2e30ba0cce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-build-with-cscexe"></a><span data-ttu-id="0e154-102">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="0e154-102">Command-line build with csc.exe</span></span>
<span data-ttu-id="0e154-103">명령 프롬프트에서 실행 파일(*csc.exe*)의 이름을 입력하여 C# 컴파일러를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-103">You can invoke the C# compiler by typing the name of its executable file (*csc.exe*) at a command prompt.</span></span>

<span data-ttu-id="0e154-104">**Visual Studio용 개발자 명령 프롬프트** 창을 사용하는 경우 필요한 환경 변수가 모두 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-104">If you use the **Developer Command Prompt for Visual Studio** window, all the necessary environment variables are set for you.</span></span> <span data-ttu-id="0e154-105">이 도구에 액세스하는 방법에 대한 자세한 내용은 [Visual Studio용 개발자 명령 프롬프트](../../../framework/tools/developer-command-prompt-for-vs.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e154-105">For information on how to access this tool, see the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md) topic.</span></span> 

<span data-ttu-id="0e154-106">표준 명령 프롬프트 창을 사용하는 경우 컴퓨터의 하위 디렉터리에서 *csc.exe*를 호출하려면 먼저 경로를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-106">If you use a standard Command Prompt window, you must adjust your path before you can invoke *csc.exe* from any subdirectory on your computer.</span></span> <span data-ttu-id="0e154-107">또한 *vsvars32.bat*를 실행하여 명령줄 빌드를 지원하도록 적절한 환경 변수를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-107">You also must run *vsvars32.bat* to set the appropriate environment variables to support command-line builds.</span></span> <span data-ttu-id="0e154-108">*vsvars32.bat*를 찾아서 실행하는 방법에 대한 지침을 포함하여 vsvars32.bat에 대한 자세한 내용은 [방법: Visual Studio 명령줄에 필요한 환경 변수 설정](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e154-108">For more information about *vsvars32.bat*, including instructions for how to find and run it, see [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

<span data-ttu-id="0e154-109">[!INCLUDE[winsdklong](~/includes/winsdklong-md.md)]만 있는 컴퓨터에서 작업 중인 경우 **Microsoft .NET Framework SDK** 메뉴 옵션에서 여는 **SDK 명령 프롬프트**에서 C# 컴파일러를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-109">If you're working on a computer that has only the [!INCLUDE[winsdklong](~/includes/winsdklong-md.md)], you can use the C# compiler at the **SDK Command Prompt**, which you open from the **Microsoft .NET Framework SDK** menu option.</span></span>

<span data-ttu-id="0e154-110">또한 MSBuild를 사용하여 프로그래밍 방식으로 C# 프로그램을 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-110">You can also use MSBuild to build C# programs programmatically.</span></span> <span data-ttu-id="0e154-111">자세한 내용은 [MSBuild](/visualstudio/msbuild/msbuild)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e154-111">For more information, see [MSBuild](/visualstudio/msbuild/msbuild).</span></span>

<span data-ttu-id="0e154-112">*csc.exe* 실행 파일은 대개 *Windows* 디렉터리 아래의 Microsoft.NET\Framework\\*\<Version>* 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-112">The *csc.exe* executable file usually is located in the Microsoft.NET\Framework\\*\<Version>* folder under the *Windows* directory.</span></span> <span data-ttu-id="0e154-113">이 위치는 개별 컴퓨터의 구성에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-113">Its location might vary depending on the exact configuration of a particular computer.</span></span> <span data-ttu-id="0e154-114">컴퓨터에 .NET Framework 버전이 두 개 이상 설치된 경우 이 파일의 여러 버전을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-114">If more than one version of the .NET Framework is installed on your computer, you'll find multiple versions of this file.</span></span> <span data-ttu-id="0e154-115">해당 설치에 대한 자세한 내용은 [방법: 설치된 .NET Framework 버전 확인](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0e154-115">For more information about such installations, see [How to: determine which versions of the .NET Framework are installed](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

> [!TIP]
>  <span data-ttu-id="0e154-116">Visual Studio IDE를 사용하여 프로젝트를 빌드할 때 **출력** 창에 **csc** 명령과 관련 컴파일러 옵션을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-116">When you build a project by using the Visual Studio IDE, you can display the **csc** command and its associated compiler options in the **Output** window.</span></span> <span data-ttu-id="0e154-117">이 정보를 표시하려면 [방법: 빌드 로그 파일 보기, 저장 및 구성](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log)의 지침에 따라 로그 데이터의 세부 정보 표시 수준을 **보통** 또는 **자세히**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-117">To display this information, follow the instructions in [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) to change the verbosity level of the log data to **Normal** or **Detailed**.</span></span> <span data-ttu-id="0e154-118">프로젝트를 다시 빌드한 후 **출력** 창에서 **csc**를 검색하여 C# 컴파일러 호출을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-118">After you rebuild your project, search the **Output** window for **csc** to find the invocation of the C# compiler.</span></span>

 <span data-ttu-id="0e154-119">**항목 내용**</span><span class="sxs-lookup"><span data-stu-id="0e154-119">**In this topic**</span></span>

- [<span data-ttu-id="0e154-120">명령줄 구문에 대한 규칙</span><span class="sxs-lookup"><span data-stu-id="0e154-120">Rules for command-line syntax</span></span>](#-rules-for-command-line-syntax-for-the-c-compiler)

- [<span data-ttu-id="0e154-121">샘플 명령줄</span><span class="sxs-lookup"><span data-stu-id="0e154-121">Sample command lines</span></span>](#sample-command-lines-for-the-c-compiler)

- [<span data-ttu-id="0e154-122">C# 컴파일러 및 C++ 컴파일러 출력의 차이점</span><span class="sxs-lookup"><span data-stu-id="0e154-122">Differences between C# compiler and C++ compiler output</span></span>](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a><span data-ttu-id="0e154-123">C# 컴파일러의 명령줄 구문에 대한 규칙</span><span class="sxs-lookup"><span data-stu-id="0e154-123">Rules for command-line syntax for the C# compiler</span></span>

<span data-ttu-id="0e154-124">C# 컴파일러에서는 운영 체제 명령줄에 지정된 인수를 해석할 때 다음 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-124">The C# compiler uses the following rules when it interprets arguments given on the operating system command line:</span></span>

- <span data-ttu-id="0e154-125">인수를 공백이나 탭으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-125">Arguments are delimited by white space, which is either a space or a tab.</span></span>

- <span data-ttu-id="0e154-126">캐럿 문자(^)는 이스케이프 문자나 구분 기호로 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-126">The caret character (^) is not recognized as an escape character or delimiter.</span></span> <span data-ttu-id="0e154-127">문자는 프로그램의 `argv` 배열에 전달된 후 운영 체제의 명령줄 구문 분석기에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-127">The character is handled by the command-line parser in the operating system before it's passed to the `argv` array in the program.</span></span>

- <span data-ttu-id="0e154-128">큰따옴표로 묶은 문자열(“string”)은 포함된 공백에 상관없이 하나의 인수로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-128">A string enclosed in double quotation marks ("string") is interpreted as a single argument, regardless of white space that is contained within.</span></span> <span data-ttu-id="0e154-129">따옴표로 묶은 문자열은 인수에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-129">A quoted string can be embedded in an argument.</span></span>

- <span data-ttu-id="0e154-130">백슬래시 다음의 큰따옴표(\\")는 리터럴 큰따옴표 문자(")로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-130">A double quotation mark preceded by a backslash (\\") is interpreted as a literal double quotation mark character (").</span></span>

- <span data-ttu-id="0e154-131">백슬래시는 큰따옴표 바로 앞에 있지 않으면 리터럴로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-131">Backslashes are interpreted literally, unless they immediately precede a double quotation mark.</span></span>

- <span data-ttu-id="0e154-132">짝수 개의 백슬래시 다음에 큰따옴표가 오는 경우, 백슬래시 쌍마다 하나의 백슬래시가 `argv` 배열에 배치되고 큰따옴표는 문자열 구분 기호로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-132">If an even number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is interpreted as a string delimiter.</span></span>

- <span data-ttu-id="0e154-133">홀수 개의 백슬래시 다음에 큰따옴표가 오는 경우, 백슬래시 쌍마다 하나의 백슬래시가 `argv` 배열에 배치되고 큰따옴표는 나머지 백슬래시에 의해 "이스케이프"됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-133">If an odd number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is "escaped" by the remaining backslash.</span></span> <span data-ttu-id="0e154-134">이로 인해 리터럴 큰따옴표(")가 `argv`에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-134">This causes a literal double quotation mark (") to be added in `argv`.</span></span>

## <a name="sample-command-lines-for-the-c-compiler"></a><span data-ttu-id="0e154-135">C# 컴파일러에 대한 샘플 명령줄</span><span class="sxs-lookup"><span data-stu-id="0e154-135">Sample command lines for the C# compiler</span></span>

- <span data-ttu-id="0e154-136">*File.cs*를 컴파일하여 *File.exe*를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-136">Compiles *File.cs* producing *File.exe*:</span></span>

```console
csc File.cs 
```

- <span data-ttu-id="0e154-137">*File.cs*를 컴파일하여 *File.dll*을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-137">Compiles *File.cs* producing *File.dll*:</span></span>

```console
csc -target:library File.cs
```

- <span data-ttu-id="0e154-138">*File.cs*를 컴파일하여 *My.exe*를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-138">Compiles *File.cs* and creates *My.exe*:</span></span>

```console
csc -out:My.exe File.cs
```

- <span data-ttu-id="0e154-139">최적화를 사용하여 현재 디렉터리에 있는 모든 C# 파일을 컴파일하고 DEBUG 기호를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-139">Compiles all the C# files in the current directory with optimizations enabled and defines the DEBUG symbol.</span></span> <span data-ttu-id="0e154-140">출력은 *File2.exe*입니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-140">The output is *File2.exe*:</span></span>

```console
csc -define:DEBUG -optimize -out:File2.exe *.cs
```

- <span data-ttu-id="0e154-141">현재 디렉터리에 있는 모든 C# 파일을 컴파일하여 *File2.dll*의 디버그 버전을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-141">Compiles all the C# files in the current directory producing a debug version of *File2.dll*.</span></span> <span data-ttu-id="0e154-142">로고 및 경고가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-142">No logo and no warnings are displayed:</span></span>

```console
csc -target:library -out:File2.dll -warn:0 -nologo -debug *.cs
```

- <span data-ttu-id="0e154-143">현재 디렉터리에 있는 모든 C# 파일을 *Something.xyz*(DLL)로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-143">Compiles all the C# files in the current directory to *Something.xyz* (a DLL):</span></span>

```console
csc -target:library -out:Something.xyz *.cs
```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a><span data-ttu-id="0e154-144">C# 컴파일러 및 C++ 컴파일러 출력의 차이점</span><span class="sxs-lookup"><span data-stu-id="0e154-144">Differences between C# compiler and C++ compiler output</span></span>
<span data-ttu-id="0e154-145">C# 컴파일러를 호출하면 개체 파일(*.obj*)은 만들어지지 않고 출력 파일이 직접 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-145">There are no object (*.obj*) files created as a result of invoking the C# compiler; output files are created directly.</span></span> <span data-ttu-id="0e154-146">따라서 C# 컴파일러에는 링커가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e154-146">As a result of this, the C# compiler does not need a linker.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e154-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e154-147">See also</span></span>
 [<span data-ttu-id="0e154-148">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="0e154-148">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="0e154-149">사전순 C# 컴파일러 옵션 목록</span><span class="sxs-lookup"><span data-stu-id="0e154-149">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 [<span data-ttu-id="0e154-150">범주별 C# 컴파일러 옵션 목록</span><span class="sxs-lookup"><span data-stu-id="0e154-150">C# Compiler Options Listed by Category</span></span>](../../../csharp/language-reference/compiler-options/listed-by-category.md)  
 [<span data-ttu-id="0e154-151">Main()과 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="0e154-151">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [<span data-ttu-id="0e154-152">명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="0e154-152">Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/command-line-arguments.md)  
 [<span data-ttu-id="0e154-153">방법: 명령줄 인수 표시</span><span class="sxs-lookup"><span data-stu-id="0e154-153">How to: Display Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [<span data-ttu-id="0e154-154">방법: foreach를 사용하여 명령줄 인수 액세스</span><span class="sxs-lookup"><span data-stu-id="0e154-154">How to: Access Command-Line Arguments Using foreach</span></span>](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
 [<span data-ttu-id="0e154-155">Main() 반환 값</span><span class="sxs-lookup"><span data-stu-id="0e154-155">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
