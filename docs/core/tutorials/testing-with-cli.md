---
title: .NET Core 명령줄을 사용하여 프로젝트 구성 및 테스트
description: 이 자습서에서는 명령줄에서 .NET Core 프로젝트를 구성하고 테스트하는 방법을 설명합니다.
author: cartermp
ms.author: mairaw
ms.date: 05/16/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 718f60d6321c1d24670ac177de64725d88bdd148
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a><span data-ttu-id="1da01-103">.NET Core 명령줄을 사용하여 프로젝트 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="1da01-103">Organizing and testing projects with the .NET Core command line</span></span>

<span data-ttu-id="1da01-104">이 자습서에서는 [명령줄을 사용하여 Windows/Linux/macOS에서 .NET Core 시작](using-with-xplat-cli.md)에 따라 간단한 콘솔 앱 이상의 잘 구성된 고급 응용 프로그램을 개발하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-104">This tutorial follows [Getting started with .NET Core on Windows/Linux/macOS using the command line](using-with-xplat-cli.md), taking you beyond the creation of a simple console app to develop advanced and well-organized applications.</span></span> <span data-ttu-id="1da01-105">이 자습서에서는 폴더를 사용하여 코드를 구성하는 방법을 보여 준 후에 [xUnit](https://xunit.github.io/) 테스트 프레임워크를 사용하여 콘솔 응용 프로그램을 확장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-105">After showing you how to use folders to organize your code, this tutorial shows you how to extend a console application with the [xUnit](https://xunit.github.io/) testing framework.</span></span>

## <a name="using-folders-to-organize-code"></a><span data-ttu-id="1da01-106">폴더를 사용하여 코드 구성</span><span class="sxs-lookup"><span data-stu-id="1da01-106">Using folders to organize code</span></span>

<span data-ttu-id="1da01-107">콘솔 앱에 새 유형을 도입하려는 경우 유형이 포함된 파일을 앱에 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-107">If you want to introduce new types into a console app, you can do so by adding files containing the types to the app.</span></span> <span data-ttu-id="1da01-108">예를 들어 `AccountInformation` 및 `MonthlyReportRecords` 유형이 포함된 파일을 프로젝트에 추가하는 경우 프로젝트 파일 구조가 단순하며 쉽게 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-108">For example if you add files containing `AccountInformation` and `MonthlyReportRecords` types to your project, the project file structure is flat and easy to navigate:</span></span>

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="1da01-109">그러나 이 방법은 프로젝트의 크기가 비교적 작은 경우에만 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-109">However, this only works well when the size of your project is relatively small.</span></span> <span data-ttu-id="1da01-110">프로젝트에 20개의 유형을 추가하면 어떻게 될지 상상이 되시나요?</span><span class="sxs-lookup"><span data-stu-id="1da01-110">Can you imagine what will happen if you add 20 types to the project?</span></span> <span data-ttu-id="1da01-111">프로젝트의 루트 디렉터리에 너무 많은 파일이 있으면 분명히 프로젝트 탐색과 유지 관리가 쉽지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-111">The project definitely wouldn't be easy to navigate and maintain with that many files littering the project's root directory.</span></span>

<span data-ttu-id="1da01-112">프로젝트를 구성하려면 유형 파일을 보관할 새 폴더를 만들고 이름을 *Models*로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-112">To organize the project, create a new folder and name it *Models* to hold the type files.</span></span> <span data-ttu-id="1da01-113">*Models* 폴더에 유형 파일을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-113">Place the type files into the *Models* folder:</span></span>

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="1da01-114">논리적으로 파일을 폴더로 그룹화하는 프로젝트는 탐색과 유지 관리가 용이합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-114">Projects that logically group files into folders are easy to navigate and maintain.</span></span> <span data-ttu-id="1da01-115">다음 섹션에서는 폴더 및 유닛 테스트를 사용하여 좀 더 복잡한 샘플을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-115">In the next section, you create a more complex sample with folders and unit testing.</span></span>

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a><span data-ttu-id="1da01-116">NewTypes Pets 샘플을 사용하여 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="1da01-116">Organizing and testing using the NewTypes Pets Sample</span></span>

### <a name="building-the-sample"></a><span data-ttu-id="1da01-117">샘플 빌드</span><span class="sxs-lookup"><span data-stu-id="1da01-117">Building the sample</span></span>

<span data-ttu-id="1da01-118">다음 단계를 위해 [NewTypes Pets 샘플](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild)을 사용할 수도 있고, 고유한 파일과 폴더를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-118">For the following steps, you can either follow along using the [NewTypes Pets Sample](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) or create your own files and folders.</span></span> <span data-ttu-id="1da01-119">나중에 더 많은 유형을 추가할 수 있는 폴더 구조로 유형이 논리적으로 구성되며, 테스트도 나중에 더 많은 테스트를 추가할 수 있는 폴더에 논리적으로 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-119">The types are logically organized into a folder structure that permits the addition of more types later, and tests are also logically placed in folders permitting the addition of more tests later.</span></span>

<span data-ttu-id="1da01-120">샘플에는 두 유형 `Dog` 및 `Cat`이 포함되어 있으며, 두 유형이 공용 인터페이스 `IPet`을 구현하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-120">The sample contains two types, `Dog` and `Cat`, and has them implement a common interface, `IPet`.</span></span> <span data-ttu-id="1da01-121">`NewTypes` 프로젝트의 목표는 애완 동물 관련 유형을 *Pets* 폴더로 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-121">For the `NewTypes` project, your goal is to organize the pet-related types into a *Pets* folder.</span></span> <span data-ttu-id="1da01-122">나중에 *WildAnimals*등의 다른 유형 집합을 추가하면 *Pets* 폴더와 함께 *NewTypes* 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-122">If another set of types is added later, *WildAnimals* for example, they're placed in the *NewTypes* folder alongside the *Pets* folder.</span></span> <span data-ttu-id="1da01-123">*WildAnimals* 폴더에는 애완 동물이 아닌 동물 유형(예: `Squirrel` 및 `Rabbit`)이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-123">The *WildAnimals* folder may contain types for animals that aren't pets, such as `Squirrel` and `Rabbit` types.</span></span> <span data-ttu-id="1da01-124">이렇게 하면 유형을 추가해도 프로젝트의 체계적인 구성이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-124">In this way as types are added, the project remains well organized.</span></span> 

<span data-ttu-id="1da01-125">표시된 파일 내용으로 다음 폴더 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-125">Create the following folder structure with file content indicated:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
```

<span data-ttu-id="1da01-126">*IPet.cs*:</span><span class="sxs-lookup"><span data-stu-id="1da01-126">*IPet.cs*:</span></span>

[!code-csharp[IPet interface](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/IPet.cs)]

<span data-ttu-id="1da01-127">*Dog.cs*:</span><span class="sxs-lookup"><span data-stu-id="1da01-127">*Dog.cs*:</span></span>

[!code-csharp[Dog class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Dog.cs)]

<span data-ttu-id="1da01-128">*Cat.cs*:</span><span class="sxs-lookup"><span data-stu-id="1da01-128">*Cat.cs*:</span></span>

[!code-csharp[Cat class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Cat.cs)]

<span data-ttu-id="1da01-129">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="1da01-129">*Program.cs*:</span></span>

[!code-csharp[Main](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Program.cs)]

<span data-ttu-id="1da01-130">*NewTypes.csproj*:</span><span class="sxs-lookup"><span data-stu-id="1da01-130">*NewTypes.csproj*:</span></span>

[!code-xml[NewTypes csproj](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/NewTypes.csproj)]

<span data-ttu-id="1da01-131">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-131">Execute the following commands:</span></span>

```console
dotnet run
```

<span data-ttu-id="1da01-132">다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-132">Obtain the following output:</span></span>

```console
Woof!
Meow!
```

<span data-ttu-id="1da01-133">연습(옵션): 이 프로젝트를 확장하여 `Bird` 등의 새로운 애완 동물 유형을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-133">Optional exercise: You can add a new pet type, such as a `Bird`, by extending this project.</span></span> <span data-ttu-id="1da01-134">새의 `TalkToOwner` 메서드를 통해 소유자에게 `Tweet!`을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-134">Make the bird's `TalkToOwner` method give a `Tweet!` to the owner.</span></span> <span data-ttu-id="1da01-135">앱을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-135">Run the app again.</span></span> <span data-ttu-id="1da01-136">출력에 `Tweet!`이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-136">The output will include `Tweet!`</span></span>

### <a name="testing-the-sample"></a><span data-ttu-id="1da01-137">샘플 테스트</span><span class="sxs-lookup"><span data-stu-id="1da01-137">Testing the sample</span></span>

<span data-ttu-id="1da01-138">`NewTypes` 프로젝트가 구현되었으며, 애완 동물 관련 유형을 폴더에 보관하여 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-138">The `NewTypes` project is in place, and you've organized it by keeping the pets-related types in a folder.</span></span> <span data-ttu-id="1da01-139">다음으로, 테스트 프로젝트를 만들고 [xUnit](https://xunit.github.io/) 테스트 프레임워크를 사용하여 테스트 작성을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-139">Next, create your test project and start writing tests with the [xUnit](https://xunit.github.io/) test framework.</span></span> <span data-ttu-id="1da01-140">유닛 테스트를 사용하면 애완 동물 유형의 동작을 자동으로 검사하여 제대로 작동하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-140">Unit testing allows you to automatically check the bevahior of your pet types to confirm that they're operating properly.</span></span>

<span data-ttu-id="1da01-141">*test* 폴더를 만들고, 이 폴더 안에 *NewTypesTests* 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-141">Create a *test* folder with a *NewTypesTests* folder within it.</span></span> <span data-ttu-id="1da01-142">*NewTypesTests* 폴더의 명령 프롬프트에서 `dotnet new xunit`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-142">At a command prompt from the *NewTypesTests* folder, execute `dotnet new xunit`.</span></span> <span data-ttu-id="1da01-143">그러면 *NewTypesTests.csproj* 및 *UnitTest1.cs*라는 두 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-143">This produces two files: *NewTypesTests.csproj* and *UnitTest1.cs*.</span></span>

<span data-ttu-id="1da01-144">테스트 프로젝트는 현재 `NewTypes`의 형식을 테스트할 수 없으며, `NewTypes` 프로젝트에 대한 프로젝트 참조가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-144">The test project cannot currently test the types in `NewTypes` and requires a project reference to the `NewTypes` project.</span></span> <span data-ttu-id="1da01-145">프로젝트 참조를 추가하려면 [`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-145">To add a project reference, use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

<span data-ttu-id="1da01-146">*NewTypesTests.csproj* 파일에 `<ItemGroup>` 노드를 추가하여 수동으로 프로젝트 참조를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-146">You also have the option of manually adding the project reference by adding an `<ItemGroup>` node to the *NewTypesTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

<span data-ttu-id="1da01-147">*NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="1da01-147">*NewTypesTests.csproj*:</span></span>

[!code-xml[NewTypesTests csproj](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/NewTypesTests.csproj)]

<span data-ttu-id="1da01-148">*NewTypesTests.csproj* 파일에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-148">The *NewTypesTests.csproj* file contains the following:</span></span>

* <span data-ttu-id="1da01-149">.NET 테스트 인프라인 `Microsoft.NET.Test.Sdk`에 대한 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="1da01-149">Package reference to `Microsoft.NET.Test.Sdk`, the .NET testing infrastructure</span></span>
* <span data-ttu-id="1da01-150">xUnit 테스트 프레임워크인 `xunit`에 대한 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="1da01-150">Package reference to `xunit`, the xUnit testing framework</span></span>
* <span data-ttu-id="1da01-151">테스트 실행기인 `xunit.runner.visualstudio`에 대한 패키지 참조</span><span class="sxs-lookup"><span data-stu-id="1da01-151">Package reference to `xunit.runner.visualstudio`, the test runner</span></span>
* <span data-ttu-id="1da01-152">테스트할 코드인 `NewTypes`에 대한 프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="1da01-152">Project reference to `NewTypes`, the code to test</span></span>

<span data-ttu-id="1da01-153">*UnitTest1.cs*의 이름을 *PetTests.cs*로 변경하고 파일의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-153">Change the name of *UnitTest1.cs* to *PetTests.cs* and replace the code in the file with the following:</span></span>

```csharp
using System;
using Xunit;
using Pets;

public class PetTests
{
    [Fact]
    public void DogTalkToOwnerReturnsWoof()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();
        
        Assert.NotEqual(expected, actual);
    }
    
    [Fact]
    public void CatTalkToOwnerReturnsMeow()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();
        
        Assert.NotEqual(expected, actual);
    }
}
```

<span data-ttu-id="1da01-154">연습(옵션): 소유자에 대한 `Tweet!`을 생성하는 `Bird` 유형을 이전에 추가한 경우 *PetTests.cs* 파일에 테스트 메서드 `BirdTalkToOwnerReturnsTweet`을 추가하여 `TalkToOwner` 메서드가 `Bird` 유형에 대해 제대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-154">Optional exercise: If you added a `Bird` type earlier that yields a `Tweet!` to the owner, add a test method to the *PetTests.cs* file, `BirdTalkToOwnerReturnsTweet`, to check that the `TalkToOwner` method works correctly for the `Bird` type.</span></span>

> [!NOTE]
> <span data-ttu-id="1da01-155">`expected` 및 `actual` 값이 같다고 예상하는 경우에도 `Assert.NotEqual` 검사를 사용한 초기 어설션에서는 두 값이 *같지 않다*고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-155">Although you expect that the `expected` and `actual` values are equal, the initial assertions with the `Assert.NotEqual` checks specify that they are *not equal*.</span></span> <span data-ttu-id="1da01-156">테스트 논리를 검사하기 위해 처음에는 항상 한 번 실패하도록 테스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-156">Always initially create your tests to fail once in order to check the logic of the tests.</span></span> <span data-ttu-id="1da01-157">이는 TDD(테스트 기반 디자인) 방법론에서 중요한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-157">This is an important step in test-driven design (TDD) methodology.</span></span> <span data-ttu-id="1da01-158">테스트가 실패하는지 확인한 후에 테스트를 통과할 수 있도록 어설션을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-158">After you confirm the tests fail, you adjust the assertions to allow them to pass.</span></span>

<span data-ttu-id="1da01-159">전체 프로젝트 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-159">The following shows the complete project structure:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

<span data-ttu-id="1da01-160">*test/NewTypesTests* 디렉터리에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-160">Start in the *test/NewTypesTests* directory.</span></span> <span data-ttu-id="1da01-161">[`dotnet restore`](../tools/dotnet-restore.md) 명령을 사용하여 테스트 프로젝트를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-161">Restore the test project with the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="1da01-162">[`dotnet test`](../tools/dotnet-test.md) 명령을 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-162">Run the tests with the [`dotnet test`](../tools/dotnet-test.md) command.</span></span> <span data-ttu-id="1da01-163">이 명령은 프로젝트 파일에 지정된 Test Runner를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-163">This command starts the test runner specified in the project file.</span></span>

 [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

 
<span data-ttu-id="1da01-164">예상대로 테스트에 실패하고, 콘솔에 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-164">As expected, testing fails, and the console displays the following output:</span></span>
 
```
Test run for C:\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp1.1\NewTypesTests.dll(.NETCoreApp,Version=v1.1)
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.7271827]   Discovering: NewTypesTests
[xUnit.net 00:00:00.8258687]   Discovered:  NewTypesTests
[xUnit.net 00:00:00.8663545]   Starting:    NewTypesTests
[xUnit.net 00:00:01.0109236]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
[xUnit.net 00:00:01.0119107]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0120278]       Expected: Not "Meow!"
[xUnit.net 00:00:01.0120968]       Actual:   "Meow!"
[xUnit.net 00:00:01.0130500]       Stack Trace:
[xUnit.net 00:00:01.0141240]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(22,0): at PetTests.CatTalkToOwnerReturnsMeow()
[xUnit.net 00:00:01.0272364]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:01.0273649]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0274166]       Expected: Not "Woof!"
[xUnit.net 00:00:01.0274690]       Actual:   "Woof!"
[xUnit.net 00:00:01.0275264]       Stack Trace:
[xUnit.net 00:00:01.0275960]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(13,0): at PetTests.DogTalkToOwnerReturnsWoof()
[xUnit.net 00:00:01.0294509]   Finished:    NewTypesTests
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 2.1371 Seconds
```

<span data-ttu-id="1da01-165">테스트 어설션을 `Assert.NotEqual`에서 `Assert.Equal`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-165">Change the assertions of your tests from `Assert.NotEqual` to `Assert.Equal`:</span></span>

[!code-csharp[PetTests class](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/PetTests.cs)]

<span data-ttu-id="1da01-166">`dotnet test` 명령을 사용하여 테스트를 다시 실행하면 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-166">Re-run the tests with the `dotnet test` command and obtain the following output:</span></span>

```
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:01.3882374]   Discovering: NewTypesTests
[xUnit.net 00:00:01.4767970]   Discovered:  NewTypesTests
[xUnit.net 00:00:01.5157667]   Starting:    NewTypesTests
[xUnit.net 00:00:01.6408870]   Finished:    NewTypesTests

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6634 Seconds
```

<span data-ttu-id="1da01-167">테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-167">Testing passes.</span></span> <span data-ttu-id="1da01-168">애완 동물 유형의 메서드가 소유자에게 설명할 때 올바른 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-168">The pet types' methods return the correct values when talking to the owner.</span></span>

<span data-ttu-id="1da01-169">xUnit를 사용하여 프로젝트를 구성 및 테스트하는 기술을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="1da01-169">You've learned techniques for organizing and testing projects using xUnit.</span></span> <span data-ttu-id="1da01-170">이러한 기술을 활용하여 사용자 고유의 프로젝트에 적용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="1da01-170">Go forward with these techniques applying them in your own projects.</span></span> <span data-ttu-id="1da01-171">*즐거운 코딩을 경험하시기 바랍니다!*</span><span class="sxs-lookup"><span data-stu-id="1da01-171">*Happy coding!*</span></span>

