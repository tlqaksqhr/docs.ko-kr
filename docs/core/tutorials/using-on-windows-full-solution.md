---
title: "Visual Studio 2017을 사용하여 Windows에서 완전한 .NET Core 솔루션 구축"
description: "Windows의 Visual Studio 2017에서 완전한 .NET Core 솔루션을 구축하는 방법에 관해 알아봅니다."
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ba7e082c-a7c8-431e-a342-f67734b660f6
ms.workload: dotnetcore
ms.openlocfilehash: e922a2c91fab5c513f5c560920d37d77da2d6f84
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="building-a-complete-net-core-solution-on-windows-using-visual-studio-2017"></a><span data-ttu-id="bf7e4-104">Visual Studio 2017을 사용하여 Windows에서 완전한 .NET Core 솔루션 구축</span><span class="sxs-lookup"><span data-stu-id="bf7e4-104">Building a complete .NET Core solution on Windows, using Visual Studio 2017</span></span>

<span data-ttu-id="bf7e4-105">Visual Studio 2017은 .NET Core 응용 프로그램 개발을 위해 필요한 모든 기능을 갖춘 개발 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-105">Visual Studio 2017 provides a full-featured development environment for developing .NET Core applications.</span></span> <span data-ttu-id="bf7e4-106">이 문서의 절차에서는 재사용 가능한 라이브러리, 테스트 및 타사 라이브러리 사용을 비롯하여 일반적인 .NET Core 솔루션을 빌드하는 데 필요한 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-106">The procedures in this document describe the steps necessary to build a typical .NET Core solution that includes reusable libraries, testing, and using third-party libraries.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="bf7e4-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="bf7e4-107">Prerequisites</span></span>

<span data-ttu-id="bf7e4-108">[필수 조건 페이지](../windows-prerequisites.md)의 지침에 따라 환경을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-108">Follow the instructions on [our prerequisites page](../windows-prerequisites.md) to update your environment.</span></span>

## <a name="a-solution-using-only-net-core-projects"></a><span data-ttu-id="bf7e4-109">.NET Core 프로젝트만을 사용하는 솔루션</span><span class="sxs-lookup"><span data-stu-id="bf7e4-109">A solution using only .NET Core projects</span></span>

### <a name="writing-the-library"></a><span data-ttu-id="bf7e4-110">라이브러리 작성</span><span class="sxs-lookup"><span data-stu-id="bf7e4-110">Writing the library</span></span>

1. <span data-ttu-id="bf7e4-111">Visual Studio에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-111">In Visual Studio, choose **File**, **New**, **Project**.</span></span> <span data-ttu-id="bf7e4-112">**새 프로젝트** 대화 상자에서 **Visual C#** 노드를 확장하고 **.NET Standard** 노드를 선택한 다음 **클래스 라이브러리(.NET Standard)**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-112">In the **New Project** dialog, expand the **Visual C#** node and choose the **.NET Standard** node, and then choose **Class Library (.NET Standard)**.</span></span> 

2. <span data-ttu-id="bf7e4-113">프로젝트 이름을 "Library", 솔루션 이름을 "Golden"으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-113">Name the project "Library" and the solution "Golden".</span></span> <span data-ttu-id="bf7e4-114">**솔루션용 디렉터리 만들기** 확인란을 선택한 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-114">Leave **Create directory for solution** checked.</span></span> <span data-ttu-id="bf7e4-115">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-115">Click **OK**.</span></span>

3. <span data-ttu-id="bf7e4-116">솔루션 탐색기에서 **종속성** 노드의 상황에 맞는 메뉴를 열고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-116">In Solution Explorer, open the context menu for the **Dependencies** node and choose **Manage NuGet Packages**.</span></span>

4. <span data-ttu-id="bf7e4-117">**패키지 소스**로 "nuget.org"를 선택하고 **찾아보기** 탭을 선택합니다. **Newtonsoft.Json**을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-117">Choose "nuget.org" as the **Package source**, and choose the **Browse** tab. Browse for **Newtonsoft.Json**.</span></span> <span data-ttu-id="bf7e4-118">**설치**를 클릭하고 사용권 계약에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-118">Click **Install**, and accept the license agreement.</span></span> <span data-ttu-id="bf7e4-119">이제 패키지에 **종속성/NuGet**이 표시되며 자동으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-119">The package should now appear under **Dependencies/NuGet** and be automatically restored.</span></span>

5. <span data-ttu-id="bf7e4-120">`Class1.cs` 파일이 이름을 `Thing.cs`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-120">Rename the `Class1.cs` file to `Thing.cs`.</span></span> <span data-ttu-id="bf7e4-121">클래스의 이름 바꾸기를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-121">Accept the rename of the class.</span></span> <span data-ttu-id="bf7e4-122">메서드 추가: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span><span class="sxs-lookup"><span data-stu-id="bf7e4-122">Add a method: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span></span>

7. <span data-ttu-id="bf7e4-123">**빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-123">On the **Build** menu, choose **Build Solution**.</span></span>

   <span data-ttu-id="bf7e4-124">솔루션이 오류 없이 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-124">The solution should build without error.</span></span>

### <a name="writing-the-test-project"></a><span data-ttu-id="bf7e4-125">테스트 프로젝트 작성</span><span class="sxs-lookup"><span data-stu-id="bf7e4-125">Writing the test project</span></span>

1. <span data-ttu-id="bf7e4-126">솔루션 탐색기에서 **솔루션** 노드의 상황에 맞는 메뉴를 열고 **추가**, **새 프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-126">In Solution Explorer, open the context menu for the **Solution** node and choose **Add**, **New Project**.</span></span> <span data-ttu-id="bf7e4-127">**새 프로젝트** 대화 상자에서 **Visual C# / .NET Core**를 선택하고 **단위 테스트 프로젝트(.NET Core)**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-127">In the **New Project** dialog, under **Visual C# / .NET Core**, choose **Unit Test Project (.NET Core)**.</span></span> <span data-ttu-id="bf7e4-128">이름을 "TestLibrary"로 지정하고 [확인]을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-128">Name it "TestLibrary" and click OK.</span></span> 

2. <span data-ttu-id="bf7e4-129">**TestLibrary** 프로젝트에서 **종속성** 노드의 상황에 맞는 메뉴를 열고 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-129">In the **TestLibrary** project, open the context menu for the **Dependencies** node and choose **Add Reference**.</span></span> <span data-ttu-id="bf7e4-130">**프로젝트**를 클릭한 다음 라이브러리 프로젝트를 확인한 후 [확인]을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-130">Click **Projects**, then check the Library project and click OK.</span></span> <span data-ttu-id="bf7e4-131">이렇게 하면 테스트 프로젝트에 라이브러리에 대한 참조가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-131">This adds a reference to your library from the test project.</span></span>

3. <span data-ttu-id="bf7e4-132">`UnitTest1.cs` 파일의 이름을 `LibraryTests.cs`로 바꾸고 클래스 이름 바꾸기를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-132">Rename the `UnitTest1.cs` file to `LibraryTests.cs` and accept the class rename.</span></span> <span data-ttu-id="bf7e4-133">파일 맨 위에 `using Library;`를 추가하고 `TestMethod1` 메서드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-133">Add `using Library;` to the top of the file, and replace the `TestMethod1` method with the following code:</span></span>
    ```csharp
    [TestMethod]
    public void ThingGetsObjectValFromNumber()
    {
        Assert.AreEqual(42, new Thing().Get(42));
    }
    ```

   <span data-ttu-id="bf7e4-134">이제 솔루션을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-134">You should now be able to build the solution.</span></span> 
   
4. <span data-ttu-id="bf7e4-135">작업 영역에 테스트 탐색기 창을 가져오도록 **테스트** 메뉴에서 **Windows**, **테스트 탐색기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-135">On the **Test** menu, choose **Windows**, **Test Explorer** in order to get the test explorer window into your workspace.</span></span> <span data-ttu-id="bf7e4-136">몇 초 후에 `ThingGetsObjectValFromNumber` 테스트가 테스트 탐색기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-136">After a few seconds, the `ThingGetsObjectValFromNumber` test should appear in the test explorer.</span></span> <span data-ttu-id="bf7e4-137">**모두 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-137">Choose **Run All**.</span></span>
   
   <span data-ttu-id="bf7e4-138">테스트를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-138">The test should pass.</span></span>

### <a name="writing-the-console-app"></a><span data-ttu-id="bf7e4-139">콘솔 앱 작성</span><span class="sxs-lookup"><span data-stu-id="bf7e4-139">Writing the console app</span></span>

1. <span data-ttu-id="bf7e4-140">솔루션 탐색기에서 솔루션의 상황에 맞는 메뉴를 열고 새 **콘솔 앱(.NET Core)** 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-140">In Solution Explorer, open the context menu for the solution, and add a new **Console App (.NET Core)** project.</span></span> <span data-ttu-id="bf7e4-141">"App"으로 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-141">Name it "App".</span></span>

2. <span data-ttu-id="bf7e4-142">**App** 프로젝트에서 **종속성** 노드의 상황에 맞는 메뉴를 열고 **추가**, **참조**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-142">In the **App** project, open the context menu for the **Dependencies** node and choose **Add**,  **Reference**.</span></span> 

3. <span data-ttu-id="bf7e4-143">**참조 관리자** 대화 상자에서 **프로젝트** 아래에 있는 **라이브러리**, **솔루션** 노드를 선택한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-143">In the **Reference Manager** dialog, check **Library** under the **Projects**, **Solution** node, and then click **OK**</span></span>

6. <span data-ttu-id="bf7e4-144">**앱** 노드의 상황에 맞는 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-144">Open the context menu for the **App** node and choose **Set as StartUp Project**.</span></span> <span data-ttu-id="bf7e4-145">F5 또는 CTRL + F5 키를 눌러 콘솔 앱이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-145">This ensures that hitting F5 or CTRL+F5 will start the console app.</span></span>

7. <span data-ttu-id="bf7e4-146">`Program.cs` 파일을 열고 `using Library;` 지시문을 파일의 상단에 추가한 다음 `Console.WriteLine($"The answer is {new Thing().Get(42)}.");`을 `Main` 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-146">Open the `Program.cs` file, add a `using Library;` directive to the top of the file, and then add `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` to the `Main` method.</span></span>

8. <span data-ttu-id="bf7e4-147">방금 추가한 줄 뒤에 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-147">Set a breakpoint after the line that you just added.</span></span>

9. <span data-ttu-id="bf7e4-148">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-148">Press F5 to run the application..</span></span>

   <span data-ttu-id="bf7e4-149">응용 프로그램이 오류 없이 빌드되고 중단점에 도달합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-149">The application should build without error, and should hit the breakpoint.</span></span> <span data-ttu-id="bf7e4-150">또한 응용 프로그램 출력이 "The answer is 42."인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7e4-150">You should also be able to check that the application output "The answer is 42.".</span></span>
