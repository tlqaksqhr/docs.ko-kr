---
title: "콘솔 응용 프로그램"
description: "이 자습서에서는 .NET Core 및 C# 언어의 다양한 기능에 대해 설명합니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.translationtype: Human Translation
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 360e93af03e00547116d1af1816c2b9b29524881
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="console-application"></a><span data-ttu-id="9f64c-104">콘솔 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9f64c-104">Console Application</span></span>

## <a name="introduction"></a><span data-ttu-id="9f64c-105">소개</span><span class="sxs-lookup"><span data-stu-id="9f64c-105">Introduction</span></span>
<span data-ttu-id="9f64c-106">이 자습서에서는 .NET Core 및 C# 언어의 다양한 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="9f64c-107">다음을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-107">You’ll learn:</span></span>
*   <span data-ttu-id="9f64c-108">.NET Core CLI(명령줄 인터페이스)의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="9f64c-108">The basics of the .NET Core Command Line Interface (CLI)</span></span>
*   <span data-ttu-id="9f64c-109">C# 콘솔 응용 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="9f64c-109">The structure of a C# Console Application</span></span>
*   <span data-ttu-id="9f64c-110">콘솔 I/O</span><span class="sxs-lookup"><span data-stu-id="9f64c-110">Console I/O</span></span>
*   <span data-ttu-id="9f64c-111">.NET Core에 포함된 파일 I/O API의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="9f64c-111">The basics of File I/O APIs in .NET Core</span></span>
*   <span data-ttu-id="9f64c-112">.NET Core에 포함된 작업 비동기 프로그래밍 모델의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="9f64c-112">The basics of the Task Asynchronous Programming Model in .NET Core</span></span>

<span data-ttu-id="9f64c-113">텍스트 파일을 읽고 콘솔에 해당 텍스트 파일의 내용을 에코하는 응용 프로그램을 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-113">You’ll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="9f64c-114">콘솔의 출력은 큰 소리로 읽는 속도에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-114">The output to the console will be paced to match reading it aloud.</span></span> <span data-ttu-id="9f64c-115">‘<’ 또는 ‘>’ 키를 눌러 속도를 높이거나 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-115">You can speed up or slow down the pace by pressing the ‘<’ or ‘>’ keys.</span></span>

<span data-ttu-id="9f64c-116">이 자습서에는 많은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="9f64c-117">하나씩 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-117">Let’s build them one by one.</span></span> 
## <a name="prerequisites"></a><span data-ttu-id="9f64c-118">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9f64c-118">Prerequisites</span></span>
<span data-ttu-id="9f64c-119">.NET Core를 실행하도록 컴퓨터에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-119">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="9f64c-120">[.NET Core](https://www.microsoft.com/net/core) 페이지에서 설치 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-120">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="9f64c-121">Windows, Linux, macOS 또는 Docker 컨테이너에서 이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-121">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="9f64c-122">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-122">You’ll need to install your favorite code editor.</span></span> 
## <a name="create-the-application"></a><span data-ttu-id="9f64c-123">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="9f64c-123">Create the Application</span></span>
<span data-ttu-id="9f64c-124">첫 번째 단계에서는 새 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-124">The first step is to create a new application.</span></span> <span data-ttu-id="9f64c-125">명령 프롬프트를 열고 응용 프로그램에 대한 새 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-125">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="9f64c-126">해당 디렉터리를 현재 디렉터리로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-126">Make that the current directory.</span></span> <span data-ttu-id="9f64c-127">명령 프롬프트에 명령 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-127">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="9f64c-128">이렇게 하면 기본 "Hello World" 응용 프로그램에 대한 시작 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-128">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="9f64c-129">파일 수정을 시작하기 전에 간단한 Hello World 응용 프로그램을 실행하는 단계를 진행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-129">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="9f64c-130">응용 프로그램을 만든 후에 명령 프롬프트에서 `dotnet restore`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-130">After creating the application, type `dotnet restore` at the command prompt.</span></span> <span data-ttu-id="9f64c-131">이 명령은 NuGet 패키지 복원 프로세스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-131">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="9f64c-132">NuGet은 .NET 패키지 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-132">NuGet is a .NET package manager.</span></span> <span data-ttu-id="9f64c-133">이 명령은 프로젝트에 대한 누락된 종속성 중 하나를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-133">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="9f64c-134">이 프로젝트는 새 프로젝트이므로 어떤 종속성도 없습니다. 따라서 처음 실행하면 .NET Core 프레임워크가 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-134">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="9f64c-135">이 초기 단계 후에 새 종속 패키지를 추가하거나 종속성 버전을 업데이트할 때 `dotnet restore`를 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-135">After this initial step, you will only need to run `dotnet restore` when you add new dependent packages, or update the versions of any of your dependencies.</span></span> <span data-ttu-id="9f64c-136">이 프로세스는 프로젝트 디렉터리에 프로젝트 잠금 파일(project.lock.json)도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-136">This process also creates the project lock file (project.lock.json) in your project directory.</span></span> <span data-ttu-id="9f64c-137">이 파일은 프로젝트 종속성을 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-137">This file helps to manage the project dependencies.</span></span> <span data-ttu-id="9f64c-138">이 파일에는 모든 프로젝트 종속성의 로컬 위치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-138">It contains the local location of all the project dependencies.</span></span> <span data-ttu-id="9f64c-139">이 파일을 소스 제어에 추가할 필요가 없습니다. `dotnet restore`를 실행할 때 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-139">You do not need to put the file in source control; it will be generated when you run `dotnet restore`.</span></span> 

<span data-ttu-id="9f64c-140">패키지를 복원한 후 `dotnet build`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-140">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="9f64c-141">이렇게 하면 빌드 엔진이 실행되고 응용 프로그램 실행 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-141">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="9f64c-142">마지막으로 `dotnet run`을 실행하여 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-142">Finally, you execute `dotnet run` to run your application.</span></span>  

<span data-ttu-id="9f64c-143">이 간단한 Hello World 응용 프로그램 코드은 모두 Program.cs에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-143">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="9f64c-144">원하는 텍스트 편집기를 사용하여 해당 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-144">Open that file with your favorite text editor.</span></span> <span data-ttu-id="9f64c-145">이제 첫 번째 변경을 수행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-145">We’re about to make our first changes.</span></span>
<span data-ttu-id="9f64c-146">파일 맨 위에서 using 문을 보세요.</span><span class="sxs-lookup"><span data-stu-id="9f64c-146">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="9f64c-147">이 문은 `System` 네임스페이스의 모든 형식이 범위 내에 있음을 컴파일러에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-147">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="9f64c-148">사용해본 적이 있을 수 다른 개체 지향 언어와 마찬가지로 C#에서도 네임스페이스를 사용하여 형식을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-148">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="9f64c-149">이 hello world 프로그램도 다르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-149">This hello world program is no different.</span></span> <span data-ttu-id="9f64c-150">프로그램이 `ConsoleApplication` 네임스페이스에 포함되어 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-150">You can see that the program is enclosed in the `ConsoleApplication` namespace.</span></span> <span data-ttu-id="9f64c-151">해당 이름은 설명을 포함하지 않으므로 `TeleprompterConsole`로 변경하세요.</span><span class="sxs-lookup"><span data-stu-id="9f64c-151">That’s not a very descriptive name, so change it to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="9f64c-152">파일 읽기 및 에코</span><span class="sxs-lookup"><span data-stu-id="9f64c-152">Reading and Echoing the File</span></span>
<span data-ttu-id="9f64c-153">추가할 첫 번째 기능은 텍스트 파일을 읽고 콘솔에 해당 텍스트를 모두 표시하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-153">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="9f64c-154">먼저 텍스트 파일을 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-154">First, let’s add a text file.</span></span> <span data-ttu-id="9f64c-155">이 [샘플](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter)에 대한 GitHub 리포지토리의 [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) 파일을 프로젝트 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-155">Copy the [sampleQuotes.txt](https://raw.githubusercontent.com/dotnet/docs/master/samples/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="9f64c-156">이 파일은 응용 프로그램에 대한 스크립트로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-156">This will serve as the script for your application.</span></span> <span data-ttu-id="9f64c-157">이 항목에 대한 샘플 앱을 다운로드하는 방법에 대한 정보를 원하는 경우 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) 항목의 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f64c-157">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="9f64c-158">다음에는 다음 메서드를 Program 클래스에 추가합니다(`Main` 메서드 바로 아래).</span><span class="sxs-lookup"><span data-stu-id="9f64c-158">Next, add the following method in your Program class (right below the `Main` method):</span></span>

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

<span data-ttu-id="9f64c-159">이 메서드는 두 개의 새 네임스페이스에 있는 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-159">This method uses types from two new namespaces.</span></span> <span data-ttu-id="9f64c-160">이를 컴파일하려면 파일 맨 위에 다음 두 줄을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-160">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="9f64c-161">`IEnumerable<T>` 인터페이스는 `System.Collections.Generic` 네임스페이스에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-161">The `IEnumerable<T>` interface is defined in the `System.Collections.Generic` namespace.</span></span> <span data-ttu-id="9f64c-162">@System.IO.File 클래스는 `System.IO` 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-162">The @System.IO.File class is defined in the `System.IO` namespace.</span></span>

<span data-ttu-id="9f64c-163">이 메서드는 *열거자 메서드*라는 특수한 형식의 C# 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-163">This method is a special type of C# method called an *Enumerator method*.</span></span> <span data-ttu-id="9f64c-164">열거자 메서드는 지연 계산되는 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-164">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="9f64c-165">즉, 시퀀스의 각 항목은 시퀀스를 사용하는 코드에서 요청된 것처럼 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-165">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="9f64c-166">열거자 메서드는 하나 이상의 `yield return` 문을 포함하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-166">Enumerator methods are methods that contain one or more `yield return` statements.</span></span> <span data-ttu-id="9f64c-167">`ReadFrom` 메서드에서 반환된 개체는 시퀀스의 각 항목을 생성하는 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-167">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="9f64c-168">이 예제에서는 소스 파일에서 다음 텍스트 줄을 읽고 해당 문자열을 반환하는 코드에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-168">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="9f64c-169">호출하는 코드가 시퀀스에서 다음 항목을 요청할 때마다 코드는 파일에서 다음 텍스트 줄을 읽고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-169">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="9f64c-170">파일이 완전히 읽히면 시퀀스는 항목이 더 이상 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-170">When the file has been completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="9f64c-171">여러분에게 생소할 수 있는 두 개의 다른 C# 구문 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-171">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="9f64c-172">이 메서드의 `using` 문은 리소스 정리를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-172">The `using` statement in this method manages resource cleanup.</span></span> <span data-ttu-id="9f64c-173">`using` 문(이 예제의 `reader`)에서 초기화되는 변수는 `IDisposable` 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-173">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the `IDisposable` interface.</span></span> <span data-ttu-id="9f64c-174">@System.IDisposable 인터페이스는 리소스를 해제해야 할 때 호출되어야 하는 단일 메서드 `Dispose`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-174">The @System.IDisposable interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="9f64c-175">컴파일러는 실행 중에 `using` 문의 닫는 중괄호에 도달하면 해당 호출을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-175">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="9f64c-176">컴파일러에서 생성된 코드는 using 문으로 정의된 블록의 코드에서 예외가 throw되더라도 리소스가 해제되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-176">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="9f64c-177">`reader` 변수는 `var` 키워드를 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-177">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="9f64c-178">`var`은 *암시적으로 형식화한 지역 변수*를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-178">`var` defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="9f64c-179">즉, 변수의 형식이 변수에 할당된 개체의 컴파일 타임 형식에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-179">That means the type of the variable is determined by the compile time type of the object assigned to the variable.</span></span> <span data-ttu-id="9f64c-180">여기서는 @System.IO.StreamReader 개체에 해당하는 @System.IO.File.OpenText의 반환 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-180">Here, that is the return value from @System.IO.File.OpenText, which is a @System.IO.StreamReader object.</span></span>
 
<span data-ttu-id="9f64c-181">이제 `Main` 메서드에서 파일을 읽는 코드를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-181">Now, let’s fill in the code to read the file in the `Main` method:</span></span> 

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line); 
}
```

<span data-ttu-id="9f64c-182">프로그램을 실행합니다(`dotnet run`을 사용하면 콘솔에 출력되는 모든 줄을 볼 수 있음).</span><span class="sxs-lookup"><span data-stu-id="9f64c-182">Run the program (using `dotnet run` and you can see every line printed out to the console).</span></span>  

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="9f64c-183">지연 추가 및 출력 서식 지정</span><span class="sxs-lookup"><span data-stu-id="9f64c-183">Adding Delays and Formatting output</span></span>
<span data-ttu-id="9f64c-184">결과가 너무 빨리 표시되어 큰 표시로 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-184">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="9f64c-185">이제 출력에 지연을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-185">Now you need to add the delays in the output.</span></span> <span data-ttu-id="9f64c-186">처음에는 비동기 처리를 가능하게 하는 일부 코어 코드를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-186">As you start, you’ll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="9f64c-187">그러나 이러한 첫 번째 단계는 몇 가지 안티 패턴을 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-187">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="9f64c-188">안티 패턴은 코드를 추가할 때 주석에 표시되며 코드는 이후 단계에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-188">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="9f64c-189">이 섹션에는 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-189">There are two steps to this section.</span></span> <span data-ttu-id="9f64c-190">먼저 전체 줄이 아니라 단일 단어를 반환하는 반복기 메서드를 업데이트하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-190">First, you’ll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="9f64c-191">이 작업은 다음과 같이 수정하면 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-191">That’s done with these modifications.</span></span> <span data-ttu-id="9f64c-192">`yield return line;` 문을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-192">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="9f64c-193">다음에는 해당 파일 줄을 사용하는 방법을 수정하고 각 단어를 쓴 후에 지연을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-193">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="9f64c-194">`Main` 메서드의 `Console.WriteLine(line)` 문을 다음 블록으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-194">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

<span data-ttu-id="9f64c-195">`Task` 클래스는 `System.Threading.Tasks` 네임스페이스에 있으므로 해당 `using` 문을 파일 맨 위에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-195">The `Task` class is in the `System.Threading.Tasks` namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="9f64c-196">샘플을 실행하고 출력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-196">Run the sample, and check the output.</span></span> <span data-ttu-id="9f64c-197">이제 개별 단어가 출력되고 200밀리초의 지연이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-197">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="9f64c-198">그러나 표시된 출력은 소스 텍스트 파일이 줄 바꿈 없는 80자 이상을 포함하는 여러 줄로 구성되므로 몇 가지 문제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-198">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="9f64c-199">스크롤하면서 읽기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-199">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="9f64c-200">이 문제는 쉽게 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-200">That’s easy to fix.</span></span> <span data-ttu-id="9f64c-201">각 줄의 길이를 추적하고 줄 길이가 특정 임계값에 도달할 때마다 새 줄을 생성하도록 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-201">You’ll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="9f64c-202">줄 길이를 포함하는 `words` 선언 다음에 지역 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-202">Declare a local variable after the declaration of `words` that holds the line length:</span></span>

```csharp
var lineLength = 0;
```
 
<span data-ttu-id="9f64c-203">그런 후 `yield return word + " ";` 문 뒤에(닫는 중괄호 이전) 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-203">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```
 
<span data-ttu-id="9f64c-204">샘플을 실행하면 미리 구성된 속도로 크게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-204">Run the sample, and you’ll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="9f64c-205">비동기 작업</span><span class="sxs-lookup"><span data-stu-id="9f64c-205">Async Tasks</span></span>
<span data-ttu-id="9f64c-206">이 마지막 단계에서는 텍스트 표시 속도를 높이거나 낮추려는 경우 사용자로부터 입력을 읽는 작업을 실행하면서 다른 작업에서 비동기적으로 출력을 쓰는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-206">In this final step, you’ll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display.</span></span> <span data-ttu-id="9f64c-207">이 과정은 몇 가지 단계로 진행되며 마지막에 필요한 모든 업데이트가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-207">This has a few steps in it and by the end, you’ll have all the updates that you need.</span></span>
<span data-ttu-id="9f64c-208">첫 번째 단계는 지금까지 파일을 읽고 표시하기 위해 만든 코드를 나타내는 비동기 @System.Threading.Tasks.Task 반환 메서드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-208">The first step is to create an asynchronous @System.Threading.Tasks.Task returning method that represents the code you’ve created so far to read and display the file.</span></span>

<span data-ttu-id="9f64c-209">이 메서드를 `Program` 클래스(`Main` 메서드 본문에서 가져옴)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-209">Add this method to your `Program` class (it’s taken from the body of your `Main` method):</span></span>

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(200);
        }
    }
}
```

<span data-ttu-id="9f64c-210">두 가지가 변경된 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-210">You’ll notice two changes.</span></span> <span data-ttu-id="9f64c-211">첫째, 이 버전은 메서드 본문에서 @System.Threading.Tasks.Task.Wait 를 호출하여 작업이 완료되기를 동기식으로 대기하지 않고, `await` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-211">First, in the body of the method, instead of calling @System.Threading.Tasks.Task.Wait to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="9f64c-212">이 작업을 수행하기 위해 메서드 시그니처에 `async` 한정자를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-212">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="9f64c-213">이 메서드는 `Task`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-213">This method returns a `Task`.</span></span> <span data-ttu-id="9f64c-214">`Task` 개체를 반환하는 Return 문은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-214">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="9f64c-215">대신, `Task` 개체는 `await` 연산자를 사용할 때 컴파일러가 생성하는 코드에 의해 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-215">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="9f64c-216">`await`에 도달하면 이 메서드가 반환되는 것을 상상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-216">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="9f64c-217">반환된 `Task`는 작업이 완료되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-217">The returned `Task` indicates that the work has not completed.</span></span>
<span data-ttu-id="9f64c-218">이 메서드는 대기 중인 작업이 완료되면 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-218">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="9f64c-219">실행되어 완료되면 반환된 `Task`는 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-219">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="9f64c-220">호출하는 코드는 반환된 `Task`를 모니터링하여 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-220">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="9f64c-221">`Main` 메서드에서 다음 새 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-221">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="9f64c-222">여기 `Main`에서 코드는 동기적으로 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-222">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="9f64c-223">가능한 경우 동기적으로 대기하는 대신 `await` 연산자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-223">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="9f64c-224">그러나 콘솔 응용 프로그램의 `Main` 메서드에서는 `await` 연산자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-224">But, in a console application’s `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="9f64c-225">결과적으로 모든 작업을 완료하기 전에 응용 프로그램이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-225">That would result in the application exiting before all tasks have completed.</span></span>

<span data-ttu-id="9f64c-226">다음에는 두 번째 비동기 메서드를 작성하여 콘솔에서 읽고 '<’ 및 ‘>’ 키를 조사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-226">Next, you need to write the second asynchronous method to read from the Console and watch for the ‘<’ and ‘>’ keys.</span></span> <span data-ttu-id="9f64c-227">해당 작업에 대해 추가하는 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-227">Here’s the method you add for that task:</span></span>

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="9f64c-228">이 메서드는 콘솔에서 키를 읽고 사용자가 ‘<’ 또는 ‘>’를 누를 때 지연을 나타내는 지역 변수를 수정하는 @System.Action 대리자를 나타내는 람다 식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-228">This creates a lambda expression to represent an @System.Action delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the ‘<’ or ‘>’ keys.</span></span> <span data-ttu-id="9f64c-229">이 메서드는 @System.Console.ReadKey 를 사용하여 차단한 후 사용자가 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-229">This method uses @System.Console.ReadKey to block and wait for the user to press a key.</span></span>

<span data-ttu-id="9f64c-230">이 기능을 완료하려면 이러한 두 작업(`GetInput` 및 `ShowTeleprompter`)을 시작하고 이러한 두 작업 간에 공유 데이터를 관리하는 새 `async Task` 반환 메서드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-230">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>
 
<span data-ttu-id="9f64c-231">이러한 두 작업 간에 공유 데이터를 처리할 수 있는 클래스를 만들 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-231">It’s time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="9f64c-232">이 클래스에는 두 개의 공용 속성, 즉 지연과 파일이 완전히 읽혔음을 나타내는 이 플래그가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-232">This class contains two public properties: the delay, and a flag to indicate that the file has been completely read:</span></span>

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        private object lockHandle = new object();
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            lock (lockHandle)
            {
                DelayInMilliseconds = newDelay;
            }
        }
    }
}
```

<span data-ttu-id="9f64c-233">해당 클래스를 새 파일에 추가하고 위와 같이 `TeleprompterConsole` 네임스페이스에 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-233">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="9f64c-234">또한 바깥쪽 클래스 또는 네임스페이스 이름 없이 `Min` 및 `Max` 메서드를 참조할 수 있도록 `using static` 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-234">You’ll also need to add a `using static` statement so that you can reference the `Min` and `Max` method without the enclosing class or namespace names.</span></span> <span data-ttu-id="9f64c-235">`using static` 문은 하나의 클래스에서 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-235">A `using static` statement imports the methods from one class.</span></span> <span data-ttu-id="9f64c-236">이것은 네임스페이스에서 모든 클래스를 가져오는 지금까지 사용했던 `using` 문과는 반대됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-236">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="9f64c-237">`lock` 문에 새로 추가된 다른 언어 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-237">The other language feature that’s new is the `lock` statement.</span></span> <span data-ttu-id="9f64c-238">이 문은 언제든지 단일 스레드만 해당 코드에 포함될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-238">This statement ensures that only a single thread can be in that code at any given time.</span></span> <span data-ttu-id="9f64c-239">한 스레드가 잠긴 섹션에 있으면 다른 스레드는 첫 번째 스레드가 해당 섹션을 종료할 때까지 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-239">If one thread is in the locked section, other threads must wait for the first thread to exit that section.</span></span> <span data-ttu-id="9f64c-240">`lock` 문은 잠금 섹션을 보호하는 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-240">The `lock` statement uses an object that guards the lock section.</span></span> <span data-ttu-id="9f64c-241">이 클래스를 클래스의 전용 개체를 잠그기 위해 표준 관용구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-241">This class follows a standard idiom to lock a private object in the class.</span></span>

<span data-ttu-id="9f64c-242">다음에는 새 `config` 개체를 사용하도록 `ShowTeleprompter` 및 `GetInput` 메서드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-242">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="9f64c-243">두 작업을 모두 시작한 다음 첫 번째 작업이 완료될 때 종료되는 하나의 최종 `Task` 반환 `async` 메서드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-243">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="9f64c-244">여기에서 새 메서드 하나는 @System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[]) 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-244">The one new method here is the @System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[]) call.</span></span> <span data-ttu-id="9f64c-245">그러면 인수 목록의 모든 작업이 완료되는 즉시 완료되는 `Task`가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-245">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="9f64c-246">다음에는 지연을 위해 `config` 개체를 사용하도록 `ShowTeleprompter` 및 `GetInput` 메서드를 모두 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-246">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{

    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="9f64c-247">이 새 버전의 `ShowTeleprompter`는 `TeleprompterConfig` 클래스에서 새 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-247">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="9f64c-248">이제 `ShowTeleprompter` 대신 `RunTeleprompter`를 호출하도록 `Main`을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-248">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

<span data-ttu-id="9f64c-249">완료하려면 `SetDone` 메서드 및 `Done` 속성을 `TelePrompterConfig` 클래스에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-249">To finish, you'll need to add the `SetDone` method, and the `Done` property to the `TelePrompterConfig` class:</span></span>

```csharp
public bool Done => done;

private bool done;

public void SetDone()
{
    done = true;    
}
```

## <a name="conclusion"></a><span data-ttu-id="9f64c-250">결론</span><span class="sxs-lookup"><span data-stu-id="9f64c-250">Conclusion</span></span>
<span data-ttu-id="9f64c-251">이 자습서에서는 콘솔 응용 프로그램 사용과 관련된 다양한 C# 언어 및 .NET Core 라이브러리 기능을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-251">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span>
<span data-ttu-id="9f64c-252">이 지식을 토대로 해당 언어 및 여기서 소개된 클래스에 대해 좀 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-252">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="9f64c-253">지금까지 파일 및 콘솔 I/O 기본 사항, 작업 기반 비동기 프로그래밍 모델의 차단 및 비차단 사용, C# 언어 둘러보기, C# 프로그램이 구성되는 방식, .NET Core 명령줄 인터페이스 및 도구에 대해 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="9f64c-253">You’ve seen the basics of File and Console I/O, blocking and non-blocking use of the Task based Asynchronous programming model, a tour of the C# language and how C# programs are organized and the .NET Core Command Line Interface and tools.</span></span>
 

