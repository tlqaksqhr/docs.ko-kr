---
title: .NET Core 시작
description: Windows, Linux 및 macOS에서 .NET Core 응용 프로그램을 빌드하는 방법을 알아볼 수 있는 리소스를 찾아보세요.
author: thraka
ms.author: adegeo
ms.date: 06/27/2018
ms.openlocfilehash: fa5deb46b64e1a09c9ad6582486a993a24336b42
ms.sourcegitcommit: 702d5ffc6e733b6c4ded85bf1c92e2293638ee9a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/04/2018
ms.locfileid: "37792402"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="344df-103">.NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="344df-103">Get started with .NET Core</span></span>

<span data-ttu-id="344df-104">이 문서에서는 .NET Core로 시작하는 데 필요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="344df-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="344df-105">Windows, Linux 및 macOS에서 .NET Core를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344df-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="344df-106">원하는 텍스트 편집기에서 코딩하고 플랫폼 간 라이브러리 및 응용 프로그램을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344df-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span> 

<span data-ttu-id="344df-107">.NET Core가 무엇인지 또는 다른 .NET 기술과 어떻게 관련있는지에 대해 잘 모를 경우 [.NET이란](https://www.microsoft.com/net/learn/what-is-dotnet) 개요로 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="344df-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://www.microsoft.com/net/learn/what-is-dotnet) overview.</span></span> <span data-ttu-id="344df-108">간단히 말해 .NET Core는 오픈 소스의 플랫폼 간 .NET의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="344df-108">Put simply, .NET Core is an open-source, cross-platform, implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="344df-109">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="344df-109">Create an application</span></span>

<span data-ttu-id="344df-110">먼저 사용자의 컴퓨터에 [.NET Core SDK](https://www.microsoft.com/net/download/)를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="344df-110">First, download and install the [.NET Core SDK](https://www.microsoft.com/net/download/) on your computer.</span></span>

<span data-ttu-id="344df-111">다음으로 **PowerShell**, **명령 프롬프트** 또는 **Bash**와 같은 터미널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="344df-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="344df-112">다음 `dotnet` 명령을 입력하여 C# 응용 프로그램을 만들고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="344df-112">Type the following `dotnet` commands to create and run a C# application.</span></span>

```console
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="344df-113">다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="344df-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="344df-114">지금까지</span><span class="sxs-lookup"><span data-stu-id="344df-114">Congratulations!</span></span> <span data-ttu-id="344df-115">간단한 .NET Core 응용 프로그램을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="344df-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="344df-116">또한 [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio 2017](tutorials/with-visual-studio.md)(Windows만 해당) 또는 [Mac용 Visual Studio](tutorials/using-on-mac-vs.md)(macOS만 해당)를 사용하여 .NET Core 응용 프로그램을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344df-116">You can also use [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio 2017](tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="344df-117">자습서</span><span class="sxs-lookup"><span data-stu-id="344df-117">Tutorials</span></span>

<span data-ttu-id="344df-118">다음 단계별 자습서에 따라 .NET Core 응용 프로그램 개발을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344df-118">You can get started developing .NET Core applications by following these step-by-step tutorials.</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="344df-119">Windows</span><span class="sxs-lookup"><span data-stu-id="344df-119">Windows</span></span>](#tab/windows)

* [<span data-ttu-id="344df-120">Visual Studio 2017에서 .NET Core를 사용하여 C# “Hello World” 응용 프로그램 빌드.</span><span class="sxs-lookup"><span data-stu-id="344df-120">Build a C# "Hello World" Application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/with-visual-studio.md)

* [<span data-ttu-id="344df-121">Visual Studio 2017에서 .NET Core를 사용하여 C# 클래스 라이브러리 빌드.</span><span class="sxs-lookup"><span data-stu-id="344df-121">Build a C# class library with .NET Core in Visual Studio 2017.</span></span>](./tutorials/library-with-visual-studio.md)

* [<span data-ttu-id="344df-122">Visual Studio 2017에서 .NET Core를 사용하여 Visual Basic “Hello World” 응용 프로그램 빌드.</span><span class="sxs-lookup"><span data-stu-id="344df-122">Build a Visual Basic "Hello World" application with .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-with-visual-studio.md)

* [<span data-ttu-id="344df-123">Visual Studio 2017에서 Visual Basic 및 .NET Core로 클래스 라이브러리 빌드.</span><span class="sxs-lookup"><span data-stu-id="344df-123">Build a class library with Visual Basic and .NET Core in Visual Studio 2017.</span></span>](./tutorials/vb-library-with-visual-studio.md)  

* <span data-ttu-id="344df-124">[Visual Studio Code 및 .NET Core를 설치 및 사용하는 방법](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/)에 관한 비디오 시청.</span><span class="sxs-lookup"><span data-stu-id="344df-124">Watch a video on [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).</span></span>

* <span data-ttu-id="344df-125">[Visual Studio 2017 및 .NET Core를 설치 및 사용하는 방법](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/)에 관한 비디오 시청.</span><span class="sxs-lookup"><span data-stu-id="344df-125">Watch a video on [how to install and use Visual Studio 2017 and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).</span></span>

* [<span data-ttu-id="344df-126">명령줄을 사용하여 .NET Core 시작.</span><span class="sxs-lookup"><span data-stu-id="344df-126">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

<span data-ttu-id="344df-127">지원되는 Windows 버전 목록은 [Windows 개발을 위한 필수 조건](windows-prerequisites.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="344df-127">See the [Prerequisites for Windows development](windows-prerequisites.md) article for a list of the supported Windows versions.</span></span>

# <a name="linuxtablinux"></a>[<span data-ttu-id="344df-128">Linux</span><span class="sxs-lookup"><span data-stu-id="344df-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="344df-129">다음 단계별 자습서에 따라 .NET Core 응용 프로그램 개발을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344df-129">You can get started developing .NET Core application by following these step-by-step tutorials.</span></span>

* [<span data-ttu-id="344df-130">명령줄을 사용하여 .NET Core 시작.</span><span class="sxs-lookup"><span data-stu-id="344df-130">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

* <span data-ttu-id="344df-131">[Ubuntu에서 C# 및 .NET Core를 사용하여 Visual Studio Code 시작](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)에 관한 비디오 시청.</span><span class="sxs-lookup"><span data-stu-id="344df-131">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

<span data-ttu-id="344df-132">지원되는 Linux 배포판 및 버전 목록은 [Linux 개발을 위한 필수 조건](linux-prerequisites.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="344df-132">See the [Prerequisites for Linux development](linux-prerequisites.md) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macostabmacos"></a>[<span data-ttu-id="344df-133">macOS</span><span class="sxs-lookup"><span data-stu-id="344df-133">macOS</span></span>](#tab/macos)

<span data-ttu-id="344df-134">다음 단계별 자습서에 따라 .NET Core 응용 프로그램 개발을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="344df-134">You can get started developing .NET Core application by following these step-by-step tutorials.</span></span>

* <span data-ttu-id="344df-135">[macOS에서 C# 및 .NET Core를 사용하여 Visual Studio Code 시작](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac)에 관한 비디오 시청.</span><span class="sxs-lookup"><span data-stu-id="344df-135">Watch a video on [Getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span>

* [<span data-ttu-id="344df-136">Visual Studio Code를 사용하여 macOS에서 .NET Core 시작.</span><span class="sxs-lookup"><span data-stu-id="344df-136">Getting started with .NET Core on macOS, using Visual Studio Code.</span></span>](tutorials/using-on-macos.md)

* [<span data-ttu-id="344df-137">명령줄을 사용하여 .NET Core 시작.</span><span class="sxs-lookup"><span data-stu-id="344df-137">Getting started with .NET Core using the command-line.</span></span>](tutorials/using-with-xplat-cli.md)

* [<span data-ttu-id="344df-138">Mac용 Visual Studio를 사용하여 macOS에서 .NET Core 시작.</span><span class="sxs-lookup"><span data-stu-id="344df-138">Getting started with .NET Core on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs.md)

* [<span data-ttu-id="344df-139">Mac용 Visual Studio를 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드.</span><span class="sxs-lookup"><span data-stu-id="344df-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac.</span></span>](tutorials/using-on-mac-vs-full-solution.md)

<span data-ttu-id="344df-140">지원되는 OS X/macOS 버전 목록은 [macOS 개발을 위한 필수 구성 요소](macos-prerequisites.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="344df-140">See the [Prerequisites for macOS development](macos-prerequisites.md) article for a list of the supported OS X / macOS versions.</span></span>

***