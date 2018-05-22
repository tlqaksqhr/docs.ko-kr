---
title: 로컬 환경 자습서 - C# 로컬 빠른 시작
description: 이 빠른 시작은 로컬에서 빠른 시작을 실행하기 위한 기본 사항을 제공합니다.
ms.date: 12/07/2017
ms.custom: mvc
ms.openlocfilehash: ad8405bf9d453bd2cc5fad8af4b7897654368a9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="local-environment"></a><span data-ttu-id="8aa19-103">로컬 환경</span><span class="sxs-lookup"><span data-stu-id="8aa19-103">Local environment</span></span>

<span data-ttu-id="8aa19-104">로컬에서 빠른 시작을 수행하는 첫 번째 단계는 로컬 컴퓨터에서 개발 환경을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-104">The first step to trying a quickstart locally is to setup a development environment on your local machine.</span></span>
<span data-ttu-id="8aa19-105">.NET 항목 [Get Started in 10 minutes](https://www.microsoft.com/net/core)(10분 안에 시작)에는 Mac, PC 또는 Linux의 로컬 개발 환경 설정에 대한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span>

<span data-ttu-id="8aa19-106">또는 [.NET Core SDK](http://dot.net/core) 및 [Visual Studio Code](https://code.visualstudio.com/)를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-106">Alternatively, you can install the [.NET Core SDK](http://dot.net/core) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="8aa19-107">기본 응용 프로그램 개발 흐름</span><span class="sxs-lookup"><span data-stu-id="8aa19-107">Basic application development flow</span></span>

<span data-ttu-id="8aa19-108">[`dotnet new`](../../core/tools/dotnet-new.md) 명령을 사용하여 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-108">You'll create applications using the [`dotnet new`](../../core/tools/dotnet-new.md) command.</span></span> <span data-ttu-id="8aa19-109">이 명령은 응용 프로그램에 필요한 파일과 자산을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-109">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="8aa19-110">빠른 시작에서는 모두 `console` 응용 프로그램 종류를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-110">The quickstarts all use the `console` application type.</span></span>

<span data-ttu-id="8aa19-111">사용할 다른 명령은 실행 파일을 빌드하기 위한 [`dotnet build`](../../core/tools/dotnet-build.md) 및 실행 파일을 실행하기 위한 [`dotnet run`](../../core/tools/dotnet-run.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-111">The other commands you'll use are [`dotnet build`](../../core/tools/dotnet-build.md) to build the executable, and [`dotnet run`](../../core/tools/dotnet-run.md) to run the executable.</span></span>

## <a name="pick-your-quickstart"></a><span data-ttu-id="8aa19-112">빠른 시작 선택</span><span class="sxs-lookup"><span data-stu-id="8aa19-112">Pick your quickstart</span></span>

<span data-ttu-id="8aa19-113">다음과 같은 빠른 시작 중 하나를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-113">You can start with any of the following quickstarts:</span></span>

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[<span data-ttu-id="8aa19-114">C#의 숫자</span><span class="sxs-lookup"><span data-stu-id="8aa19-114">Numbers in C#</span></span>](numbers-in-csharp-local.md)

<span data-ttu-id="8aa19-115">[C#의 숫자](numbers-in-csharp-local.md) 빠른 시작에서는 컴퓨터가 숫자를 저장하는 방법과 여러 숫자 형식으로 계산을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-115">In the [Numbers in C#](numbers-in-csharp-local.md) quickstart, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="8aa19-116">반올림의 기본 사항과 C#을 사용하여 수학 계산을 수행하는 방법에 대해 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-116">You'll learn the basics of rounding, and how to perform mathematical calculations using C#.</span></span> 

<span data-ttu-id="8aa19-117">이 빠른 시작에서는 [Hello World](hello-world.yml) 단원을 완료했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-117">This quickstart assumes that you have finished the [Hello world](hello-world.yml) lesson.</span></span>

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[<span data-ttu-id="8aa19-118">분기 및 루프</span><span class="sxs-lookup"><span data-stu-id="8aa19-118">Branches and loops</span></span>](branches-and-loops-local.md)

<span data-ttu-id="8aa19-119">[분기 및 루프](branches-and-loops-local.md) 빠른 시작에서는 변수에 저장된 값에 따라 코드 실행의 여러 경로를 선택하는 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-119">The [Branches and loops](branches-and-loops-local.md) quickstart teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="8aa19-120">프로그램에서 결정하고 여러 작업을 선택하는 방법에 대한 기본 사항인 제어 흐름의 기본 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-120">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span> 

<span data-ttu-id="8aa19-121">이 빠른 시작에서는 [Hello World](hello-world.yml) 및 [C#의 숫자](numbers-in-csharp-local.md) 단원을 완료했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-121">This quickstart assumes that you have finished the [Hello world](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="string-interpolationinterpolated-strings-localmd"></a>[<span data-ttu-id="8aa19-122">문자열 보간</span><span class="sxs-lookup"><span data-stu-id="8aa19-122">String interpolation</span></span>](interpolated-strings-local.md)

<span data-ttu-id="8aa19-123">[문자열 보간](interpolated-strings-local.md) 빠른 시작에서는 문자열에 값을 삽입하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-123">The [String interpolation](interpolated-strings-local.md) quickstart shows you how to insert values into a string.</span></span> <span data-ttu-id="8aa19-124">포함된 C# 식을 사용하여 보간된 문자열을 만드는 방법과 결과 문자열에서 식 결과의 텍스트 모양을 제어하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-124">You'll learn how to create an interpolated string with embedded C# expressions and how to control the text appearance of the expression results in the result string.</span></span>

<span data-ttu-id="8aa19-125">이 빠른 시작에서는 [Hello World](hello-world.yml), [C#의 숫자](numbers-in-csharp-local.md) 및 [분기 및 루프](branches-and-loops-local.md) 단원을 완료했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-125">This quickstart assumes that you have finished the [Hello world](hello-world.yml), [Numbers in C#](numbers-in-csharp-local.md), and [Branches and loops](branches-and-loops-local.md) lessons.</span></span>

## <a name="list-collectionarrays-and-collectionsmd"></a>[<span data-ttu-id="8aa19-126">목록 컬렉션</span><span class="sxs-lookup"><span data-stu-id="8aa19-126">List collection</span></span>](arrays-and-collections.md)

<span data-ttu-id="8aa19-127">[목록 컬렉션](arrays-and-collections.md) 단원에서는 데이터 시퀀스를 저장하는 목록 컬렉션 형식을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-127">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="8aa19-128">항목을 추가 및 제거하고, 항목을 검색하고, 목록을 정렬하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-128">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="8aa19-129">여러 종류의 목록을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-129">You'll explore different kinds of lists.</span></span> 

<span data-ttu-id="8aa19-130">이 빠른 시작에서는 위에 나열된 단원을 완료했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-130">This quickstart assumes that you have finished the lessons listed above.</span></span>

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[<span data-ttu-id="8aa19-131">클래스 소개</span><span class="sxs-lookup"><span data-stu-id="8aa19-131">Introduction to classes</span></span>](introduction-to-classes.md)

<span data-ttu-id="8aa19-132">이 마지막 빠른 시작은 사용자의 로컬 개발 환경 및 .NET Core를 사용하여 사용자의 컴퓨터에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-132">This final quickstart is only available to run on your machine, using your own local development environment and .NET Core.</span></span>
<span data-ttu-id="8aa19-133">콘솔 응용 프로그램을 빌드하고 C# 언어의 일부인 기본 개체 지향 기능을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8aa19-133">You'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span>
