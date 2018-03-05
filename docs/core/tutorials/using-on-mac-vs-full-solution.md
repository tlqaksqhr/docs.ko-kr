---
title: "Visual Studio for Mac을 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드"
description: "이 항목에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 .NET Core 솔루션을 빌드하는 과정을 안내합니다."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 6945bedf-5bf3-4955-8588-83fb87511b79
ms.workload:
- dotnetcore
ms.openlocfilehash: 0db67593340ea3bae00a45b845a0effe0c1fcab1
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="building-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a><span data-ttu-id="77be3-104">Visual Studio for Mac을 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드</span><span class="sxs-lookup"><span data-stu-id="77be3-104">Building a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>

<span data-ttu-id="77be3-105">Visual Studio for Mac은 .NET Core 응용 프로그램 개발을 위해 필요한 전기능 IDE(통합 개발 환경)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-105">Visual Studio for Mac provides a full-featured Integrated Development Environment (IDE) for developing .NET Core applications.</span></span> <span data-ttu-id="77be3-106">이 항목에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 .NET Core 솔루션을 빌드하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-106">This topic walks you through building a .NET Core solution that includes a reusable library and unit testing.</span></span>

<span data-ttu-id="77be3-107">이 자습서에서는 사용자가 입력하는 검색어 및 텍스트 문자열을 수락하고, 클래스 라이브러리의 메서드를 사용하여 해당 검색어가 문자열에 나타나는 횟수를 계산하고, 사용자에게 결과를 반환하는 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-107">This tutorial shows you how to create an application that accepts a search word and a string of text from the user, counts the number of times the search word appears in the string using a method in a class library, and returns the result to the user.</span></span> <span data-ttu-id="77be3-108">또한 이 솔루션에는 TDD(테스트 기반 개발) 개념을 소개하기 위한 클래스 라이브러리용 단위 테스트도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-108">The solution also includes unit testing for the class library as an introduction to test-driven development (TDD) concepts.</span></span> <span data-ttu-id="77be3-109">전체 샘플에 대한 자습서를 수행하려면 [샘플 솔루션](https://github.com/dotnet/docs/blob/master/samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-109">If you prefer to proceed through the tutorial with a complete sample, download the [sample solution](https://github.com/dotnet/docs/blob/master/samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter).</span></span> <span data-ttu-id="77be3-110">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77be3-110">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

> [!NOTE]
> <span data-ttu-id="77be3-111">사용자 의견은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-111">Your feedback is highly valued.</span></span> <span data-ttu-id="77be3-112">Mac용 Visual Studio의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-112">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
> * <span data-ttu-id="77be3-113">Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-113">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="77be3-114">[Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-114">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html) portal.</span></span>
> * <span data-ttu-id="77be3-115">제안하려면 메뉴에서 **도움말** > **제안하기**를 선택하거나 시작 화면에서 **제안하기**를 선택합니다. 그러면 [Mac용 Visual Studio UserVoice 웹 페이지](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-115">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac UserVoice webpage](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="77be3-116">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="77be3-116">Prerequisites</span></span>

- <span data-ttu-id="77be3-117">OpenSSL(.NET Core 1.1을 실행 중인 경우): [Mac에서 .NET Core의 필수 구성 요소](../macos-prerequisites.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77be3-117">OpenSSL (if running .NET Core 1.1): See the [Prerequisites for .NET Core on Mac](../macos-prerequisites.md) topic.</span></span>
- [<span data-ttu-id="77be3-118">.NET Core SDK 1.1 이상</span><span class="sxs-lookup"><span data-stu-id="77be3-118">.NET Core SDK 1.1 or later</span></span>](https://www.microsoft.com/net/core#macos)
- [<span data-ttu-id="77be3-119">Mac용 visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="77be3-119">Visual Studio 2017 for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

<span data-ttu-id="77be3-120">필수 구성 요소에 대한 자세한 내용은 [Mac의 .NET Core에 대한 필수 구성 요소](../../core/macos-prerequisites.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77be3-120">For more information on prerequisites, see the [Prerequisites for .NET Core on Mac](../../core/macos-prerequisites.md).</span></span> <span data-ttu-id="77be3-121">Mac용 Visual Studio 2017의 전체 시스템 요구 사항은 [Mac용 Visual Studio 2017 제품군 시스템 요구 사항](/visualstudio/productinfo/vs2017-system-requirements-mac)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77be3-121">For the full system requirements of Visual Studio 2017 for Mac, see [Visual Studio 2017 for Mac Product Family System Requirements](/visualstudio/productinfo/vs2017-system-requirements-mac).</span></span>

## <a name="building-a-library"></a><span data-ttu-id="77be3-122">라이브러리 빌드</span><span class="sxs-lookup"><span data-stu-id="77be3-122">Building a library</span></span>

1. <span data-ttu-id="77be3-123">시작 화면에서 **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-123">On the Welcome screen, select **New Project**.</span></span> <span data-ttu-id="77be3-124">**새 프로젝트** 대화 상자의 **다중 플랫폼** 노드에서 **.NET 표준 라이브러리** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-124">In the **New Project** dialog under the **Multiplatform** node, select the **.NET Standard Library** template.</span></span> <span data-ttu-id="77be3-125">**새로 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-125">Select **Next**.</span></span>

   ![새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull01.png)

1. <span data-ttu-id="77be3-127">프로젝트의 이름을 "TextUtils"("텍스트 유틸리티"의 약식 이름)로, 솔루션 이름을 "WordCounter"로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-127">Name the project "TextUtils" (a short name for "Text Utilities") and the solution "WordCounter".</span></span> <span data-ttu-id="77be3-128">**솔루션 디렉터리 내에 프로젝트 디렉터리를 만드세요.**를 선택한 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-128">Leave **Create a project directory within the solution directory** checked.</span></span> <span data-ttu-id="77be3-129">**만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-129">Select **Create**.</span></span>

   ![새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull02.png)

1. <span data-ttu-id="77be3-131">**솔루션** 사이드바에서 `TextUtils` 노드를 확장하여 템플릿에 제공되는 클래스 파일 *Class1.cs*를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-131">In the **Solution** sidebar, expand the `TextUtils` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="77be3-132">파일을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **이름 바꾸기**를 선택한 후 파일 이름을 *WordCount.cs*로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-132">Right-click the file, select **Rename** from the context menu, and rename the file to *WordCount.cs*.</span></span> <span data-ttu-id="77be3-133">파일을 열고 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-133">Open the file and replace the contents with the following code:</span></span>

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/TextUtils/WordCount.cs)]

1. <span data-ttu-id="77be3-134">세 가지 방법, 즉 바로 가기 키 <kbd>&#8984;</kbd>+<kbd>s</kbd>를 사용하거나, 메뉴에서 **파일** > **저장**을 선택하거나, 파일 탭을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **저장**을 선택하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-134">Save the file by using any of three different methods: use the keyboard shortcut <kbd>&#8984;</kbd>+<kbd>s</kbd>, select **File** > **Save** from the menu, or right-click on the file's tab and select **Save** from the contextual menu.</span></span> <span data-ttu-id="77be3-135">다음 그림에서는 IDE 창을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-135">The following image shows the IDE window:</span></span>

   ![TextUtils 클래스 라이브러리, WordCount 클래스 파일, 정적 클래스 WordCount 및 GetWordCount 메서드를 보여 주는 IDE 창](./media/using-on-mac-vs-full-solution/vsmacfull03.png)

1. <span data-ttu-id="77be3-137">IDE 창 아래쪽 여백에서 **오류**를 선택하여 **오류** 패널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-137">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="77be3-138">**빌드 출력** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-138">Select the **Build Output** button.</span></span>

   ![오류 단추를 표시하는 IDE의 아래쪽 여백](./media/using-on-mac-vs-full-solution/vsmacfull03b.png)

1. <span data-ttu-id="77be3-140">메뉴에서 **빌드** > **모두 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-140">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="77be3-141">솔루션이 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-141">The solution builds.</span></span> <span data-ttu-id="77be3-142">빌드 출력 패널에 빌드가 성공적으로 수행되었다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-142">The build output panel shows that the build is successful.</span></span>

   ![빌드 성공 메시지를 표시하는 오류 패널의 빌드 출력 창](./media/using-on-mac-vs-full-solution/vsmacfull04.png)

## <a name="creating-a-test-project"></a><span data-ttu-id="77be3-144">테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="77be3-144">Creating a test project</span></span>

<span data-ttu-id="77be3-145">단위 테스트는 개발 및 게시 동안 자동화된 소프트웨어 테스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-145">Unit tests provide automated software testing during your development and publishing.</span></span> <span data-ttu-id="77be3-146">이 자습서에서 사용하는 테스트 프레임워크는 [xUnit(버전 2.2.0 이상)](https://xunit.github.io/)이며, 이는 xUnit 테스트 프로젝트가 다음 단계에서 솔루션에 추가될 때 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-146">The testing framework that you use in this tutorial is [xUnit (version 2.2.0 or later)](https://xunit.github.io/), which is installed automatically when the xUnit test project is added to the solution in the following steps:</span></span>

1. <span data-ttu-id="77be3-147">**솔루션** 사이드바에서 `WordCounter` 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가** > **새 프로젝트 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-147">In the **Solution** sidebar, right-click the `WordCounter` solution and select **Add** > **Add New Project**.</span></span>

1. <span data-ttu-id="77be3-148">**새 프로젝트** 대화 상자의 **.NET Core** 노드에서 **테스트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-148">In the **New Project** dialog, select **Tests** from the **.NET Core** node.</span></span> <span data-ttu-id="77be3-149">**xUnit 테스트 프로젝트**와 **다음**을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-149">Select the **xUnit Test Project** followed by **Next**.</span></span>

   ![xUnit 테스트 프로젝트를 만드는 새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull05.png)

1. <span data-ttu-id="77be3-151">새 프로젝트의 이름을 "TestLibrary"로 지정하고 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-151">Name the new project "TestLibrary" and select **Create**.</span></span>

   ![프로젝트 이름을 제공하는 새 프로젝트 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull06.png)

1. <span data-ttu-id="77be3-153">테스트 라이브러리가 `WordCount` 클래스에 대해 작동하도록 하기 위해 `TextUtils` 프로젝트에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-153">In order for the test library to work with the `WordCount` class, add a reference to the `TextUtils` project.</span></span> <span data-ttu-id="77be3-154">**솔루션** 사이드바에서 **TestLibrary** 아래의 **종속성**을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-154">In the **Solution** sidebar, right-click **Dependencies** under **TestLibrary**.</span></span> <span data-ttu-id="77be3-155">상황에 맞는 메뉴에서 **참조 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-155">Select **Edit References** from the context menu.</span></span>

1. <span data-ttu-id="77be3-156">**참조 편집** 대화 상자의 **프로젝트** 탭에서 **TextUtils** 프로젝트를 선택합니다. **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-156">In the **Edit References** dialog, select the **TextUtils** project on the **Projects** tab. Select **OK**.</span></span>

   ![참조 편집 대화 상자](./media/using-on-mac-vs-full-solution/vsmacfull07.png)

1. <span data-ttu-id="77be3-158">**TestLibrary** 프로젝트에서 *UnitTest1.cs* 파일 이름을 *TextUtilsTests.cs*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-158">In the **TestLibrary** project, rename the *UnitTest1.cs* file to *TextUtilsTests.cs*.</span></span>

1. <span data-ttu-id="77be3-159">파일을 열고 코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-159">Open the file and replace the code with the following:</span></span>

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");
   
               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   <span data-ttu-id="77be3-160">다음 이미지는 단위 테스트 코드를 포함하는 IDE를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-160">The following image shows the IDE with the unit test code in place.</span></span> <span data-ttu-id="77be3-161">`Assert.NotEqual` 문을 신중히 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-161">Pay attention to the `Assert.NotEqual` statement.</span></span>

   ![IDE 주 창에서 GetWordCount를 확인하기 위한 초기 단위 테스트](./media/using-on-mac-vs-full-solution/vsmacfull08.png)

   <span data-ttu-id="77be3-163">TDD를 사용하여 새 테스트를 실패하도록 만들어 테스트 논리가 올바른지 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-163">Using TDD, it's important to make a new test fail once to confirm its testing logic is correct.</span></span> <span data-ttu-id="77be3-164">이 메서드는 이름 "Jack"(대문자)과 "Jack" 및 "jack"(대문자 및 소문자)을 포함하는 문자열을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-164">The method passes in the name "Jack" (uppercase) and a string with "Jack" and "jack" (uppercase and lowercase).</span></span> <span data-ttu-id="77be3-165">`GetWordCount` 메서드는 제대로 작동하면 검색 단어 인스턴스 2를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-165">If the `GetWordCount` method is working properly, it returns a count of two instances of the search word.</span></span> <span data-ttu-id="77be3-166">의도적으로 이 테스트가 실패하도록 하기 위해 먼저 검색 단어 "Jack"의 두 인스턴스가 `GetWordCount` 메서드에 의해 반환되지 않음을 어설션하는 테스트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-166">In order to fail this test on purpose, you first implement the test asserting that two instances of the search word "Jack" aren't returned by the `GetWordCount` method.</span></span> <span data-ttu-id="77be3-167">다음 단계를 계속 진행하여 의도적으로 이 테스트가 실패하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-167">Continue to the next step to fail the test on purpose.</span></span>

1. <span data-ttu-id="77be3-168">화면 오른쪽의 **단위 테스트** 패널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-168">Open the **Unit Tests** panel on the right side of the screen.</span></span>

![단위 테스트 패널](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanel.png)

1. <span data-ttu-id="77be3-170">패널을 열어두려면 **고정** 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-170">Click the **Dock** icon to keep the panel open.</span></span>

![단위 테스트 패널 고정 아이콘](./media/using-on-mac-vs-full-solution/vsmacfull_UnitTestPanelDockIcon.png)

1. <span data-ttu-id="77be3-172">**모두 실행** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-172">Click the **Run All** button.</span></span>
   
   <span data-ttu-id="77be3-173">테스트가 실패합니다. 이것은 올바른 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-173">The test fails, which is the correct result.</span></span> <span data-ttu-id="77be3-174">테스트 메서드는 `inputString`, "Jack"의 2개 인스턴스가 `GetWordCount` 메서드에 제공된 문자열 "Jack jack"에서 반환되지 않음을 어설션합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-174">The test method asserts that two instances of the `inputString`, "Jack," aren't returned from the string "Jack jack" provided to the `GetWordCount` method.</span></span> <span data-ttu-id="77be3-175">단어의 대/소문자가 `GetWordCount` 메서드에서 제외되었으므로 두 개의 인스턴스가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-175">Since word casing was factored out in the `GetWordCount` method, two instances are returned.</span></span> <span data-ttu-id="77be3-176">2가 2와 *과 같지 않다는* 어설션은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-176">The assertion that 2 *is not equal to* 2 fails.</span></span> <span data-ttu-id="77be3-177">이것은 올바른 결과이며 테스트 논리는 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-177">This is the correct outcome, and the logic of our test is good.</span></span>

   ![테스트 실패](./media/using-on-mac-vs-full-solution/vsmacfull09.png)

1. <span data-ttu-id="77be3-179">`Assert.NotEqual`을 `Assert.Equal`로 변경하여 `IgnoreCasing` 테스트 메서드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-179">Modify the `IgnoreCasing` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="77be3-180">바로 가기 키 <kbd>&#8984;</kbd>+<kbd>s</kbd>와 메뉴의 **파일** > **저장**을 사용하거나 파일 탭을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **저장**을 선택하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-180">Save the file by using the keyboard shortcut <kbd>&#8984;</kbd>+<kbd>s</kbd>, **File** > **Save** from the menu, or right-clicking on the file's tab and selecting **Save** from the context menu.</span></span>

   <span data-ttu-id="77be3-181">`inputString` "Jack jack"이 `GetWordCount`로 전달된 상태로 `searchWord` "Jack"은 2개 인스턴스를 반환할 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-181">You expect that the `searchWord` "Jack" returns two instances with `inputString` "Jack jack" passed into `GetWordCount`.</span></span> <span data-ttu-id="77be3-182">**단위 테스트** 패널의 **테스트 실행** 단추 또는 화면 하단에 있는 **테스트 결과** 패널의 **테스트 다시 실행** 단추를 클릭하여 테스트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-182">Run the test again by clicking the **Run Tests** button in the **Unit Tests** panel or the **Rerun Tests** button in the **Test Results** panel at the bottom of the screen.</span></span> <span data-ttu-id="77be3-183">테스트가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-183">The test passes.</span></span> <span data-ttu-id="77be3-184">문자열 "Jack jack"(대/소문자 무시)에는 "Jack" 인스턴스가 2개 있고 테스트 어설션은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-184">There are two instances of "Jack" in the string "Jack jack" (ignoring casing), and the test assertion is `true`.</span></span>

   ![테스트 통과](./media/using-on-mac-vs-full-solution/vsmacfull10.png)

1. <span data-ttu-id="77be3-186">`Fact`를 사용하여 개별 반환 값을 테스트하는 것은 단위 테스트로 수행할 수 있는 작업의 시작일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-186">Testing individual return values with a `Fact` is only the beginning of what you can do with unit testing.</span></span> <span data-ttu-id="77be3-187">다른 강력한 기법에서는 `Theory`를 사용하여 한 번에 여러 개의 값을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-187">Another powerful technique allows you to test several values at once using a `Theory`.</span></span> <span data-ttu-id="77be3-188">다음 메서드를 `TextUtils_GetWordCountShould` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-188">Add the following method to your `TextUtils_GetWordCountShould` class.</span></span> <span data-ttu-id="77be3-189">이 메서드를 추가한 후 클래스에는 다음 두 개의 메서드가 존재하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-189">You have two methods in the class after you add this method:</span></span>

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count, 
                                       string searchWord, 
                                       string inputString)
   {
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   <span data-ttu-id="77be3-190">`CountInstancesCorrectly`는 `GetWordCount` 메서드가 올바르게 계산하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-190">The `CountInstancesCorrectly` checks that the `GetWordCount` method counts correctly.</span></span> <span data-ttu-id="77be3-191">`InlineData`는 확인할 개수, 검색 단어 및 입력 문자열을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-191">The `InlineData` provides a count, a search word, and an input string to check.</span></span> <span data-ttu-id="77be3-192">테스트 메서드는 데이터의 각 줄에 대해 한 번만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-192">The test method runs once for each line of data.</span></span> <span data-ttu-id="77be3-193">데이터에 포함된 개수가 올바르며 해당 값이 `GetWordCount` 메서드에 의해 반환된 개수와 일치한다는 것을 알더라도 `Assert.NotEqual`을 사용하여 먼저 실패를 어설션하는지 한 번 더 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-193">Note once again that you're asserting a failure first by using `Assert.NotEqual`, even when you know that the counts in the data are correct and that the values match the counts returned by the `GetWordCount` method.</span></span> <span data-ttu-id="77be3-194">의도적으로 이 테스트가 실패하도록 하는 단계를 수행하는 일이 처음에는 시간 낭비처럼 보일 수 있지만 먼저 실패하여 테스트의 논리를 검토하는 일은 테스트 논리에서 중요한 확인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-194">Performing the step of failing the test on purpose might seem like a waste of time at first, but checking the logic of the test by failing it first is an important check on the logic of your tests.</span></span> <span data-ttu-id="77be3-195">실패할 것으로 예상했는데 통과한 테스트 메서드가 나타날 때 테스트 논리에서 버그가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-195">When you come across a test method that passes when you expect it to fail, you've found a bug in the logic of the test.</span></span> <span data-ttu-id="77be3-196">테스트 메서드를 만들 때마다 이 단계를 수행하는 것은 가치 있는 일입니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-196">It's worth the effort to take this step every time you create a test method.</span></span>
   
1. <span data-ttu-id="77be3-197">파일을 저장하고 테스트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-197">Save the file and run the tests again.</span></span> <span data-ttu-id="77be3-198">대/소문자 구분 테스트는 통과하지만 세 가지 계산 테스트는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-198">The casing test passes but the three count tests fail.</span></span> <span data-ttu-id="77be3-199">이것은 예상하던 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-199">This is exactly what you expect to happen.</span></span>

   ![테스트 실패](./media/using-on-mac-vs-full-solution/vsmacfull11.png)

1. <span data-ttu-id="77be3-201">`Assert.NotEqual`을 `Assert.Equal`로 변경하여 `CountInstancesCorrectly` 테스트 메서드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-201">Modify the `CountInstancesCorrectly` test method by changing `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="77be3-202">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-202">Save the file.</span></span> <span data-ttu-id="77be3-203">테스트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-203">Run the tests again.</span></span> <span data-ttu-id="77be3-204">모든 테스트가 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-204">All tests pass.</span></span>

   ![테스트 통과](./media/using-on-mac-vs-full-solution/vsmacfull12.png)

## <a name="adding-a-console-app"></a><span data-ttu-id="77be3-206">콘솔 앱 추가</span><span class="sxs-lookup"><span data-stu-id="77be3-206">Adding a console app</span></span>

1. <span data-ttu-id="77be3-207">**솔루션** 사이드바에서 `WordCounter` 솔루션을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-207">In the **Solution** sidebar, right-click the `WordCounter` solution.</span></span> <span data-ttu-id="77be3-208">**.NET Core** > **앱** 템플릿에서 템플릿을 선택하여 새 **콘솔 응용 프로그램** 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-208">Add a new **Console Application** project by selecting the template from the **.NET Core** > **App** templates.</span></span> <span data-ttu-id="77be3-209">**새로 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-209">Select **Next**.</span></span> <span data-ttu-id="77be3-210">프로젝트 이름을 **WordCounterApp**으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-210">Name the project **WordCounterApp**.</span></span> <span data-ttu-id="77be3-211">**만들기**를 선택하여 솔루션에 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-211">Select **Create** to create the project in the solution.</span></span>

1. <span data-ttu-id="77be3-212">**솔루션** 사이드바에서 새 **WordCounterApp** 프로젝트에서 **종속성**을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-212">In the **Solutions** sidebar, right-click the **Dependencies** node of the new **WordCounterApp** project.</span></span> <span data-ttu-id="77be3-213">**참조 편집** 대화 상자에서 **TextUtils**를 선택하고 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-213">In the **Edit References** dialog, check **TextUtils** and select **OK**.</span></span>

1. <span data-ttu-id="77be3-214">*Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-214">Open the *Program.cs* file.</span></span> <span data-ttu-id="77be3-215">코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-215">Replace the code with the following:</span></span>

   [!code-csharp[Main](../../../samples/core/tutorials/using-on-mac-vs-full-solution/WordCounter/WordCounterApp/Program.cs)]

1. <span data-ttu-id="77be3-216">IDE 대신 콘솔 창에는 앱을 실행하려면 `WordCounterApp` 프로젝트를 마우스 오른쪽 단추로 클릭하고 **옵션**을 선택한 후 **구성** 아래에서 **기본값** 노드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-216">To run the app in a console window instead of the IDE, right-click the `WordCounterApp` project, select **Options**, and open the **Default** node under **Configurations**.</span></span> <span data-ttu-id="77be3-217">**외부 콘솔에서 실행** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-217">Check the box for **Run on external console**.</span></span> <span data-ttu-id="77be3-218">**콘솔 출력 일시 중지** 옵션을 선택한 상태로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-218">Leave the **Pause console output** option checked.</span></span> <span data-ttu-id="77be3-219">이 설정을 사용하면 앱이 콘솔 창에 생성되므로 `Console.ReadLine` 문에 대한 입력을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-219">This setting causes the app to spawn in a console window so that you can type input for the `Console.ReadLine` statements.</span></span> <span data-ttu-id="77be3-220">앱이 IDE에서 실행되도록 하면 `Console.WriteLine` 문의 출력을 볼 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-220">If you leave the app to run in the IDE, you can only see the output of `Console.WriteLine` statements.</span></span> <span data-ttu-id="77be3-221">`Console.ReadLine` 문은 **응용 프로그램 출력** 패널에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-221">`Console.ReadLine` statements do not work in the IDE's **Application Output** panel.</span></span>

   ![프로젝트 옵션 창](./media/using-on-mac-vs-full-solution/vsmacfull13.png)

1. <span data-ttu-id="77be3-223">현재 Mac용 Visual Studio 현재 버전은 솔루션이 실행될 때 테스트를 실행할 수 없으므로 콘솔 앱을 직접 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-223">Because the current version of Visual Studio for Mac cannot run the tests when the solution is run, you run the console app directly.</span></span> <span data-ttu-id="77be3-224">`WordCounterApp` 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **항목 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-224">Right-click on the `WordCounterApp` project and select **Run item** from the context menu.</span></span> <span data-ttu-id="77be3-225">재생 단추를 사용하여 앱을 실행하려고 하면 Test Runner 및 앱이 실행되지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-225">If you attempt to run the app with the Play button, the test runner and app fail to run.</span></span> <span data-ttu-id="77be3-226">이 문제와 관련된 작업의 상태에 대한 자세한 내용은 [xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77be3-226">For more information on the status of the work on this issue, see [xunit/xamarinstudio.xunit (#60)](https://github.com/xunit/xamarinstudio.xunit/issues/60).</span></span> <span data-ttu-id="77be3-227">앱을 실행할 때 콘솔 창의 프롬프트에 검색 단어 및 입력 문자열 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-227">When you run the app, provide values for the search word and input string at the prompts in the console window.</span></span> <span data-ttu-id="77be3-228">앱은 문자열에서 검색 단어가 표시되는 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-228">The app indicates the number of times the search word appears in the string.</span></span>

   ![문자열 'Iro ate olives by the lake, and the olives were wonderful.'에서 검색된 단어 olives를 보여 주는 콘솔 창](./media/using-on-mac-vs-full-solution/vsmacfull14.png)

1. <span data-ttu-id="77be3-231">알아보려는 마지막 기능은 Visual Studio for Mac을 사용한 디버깅입니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-231">The last feature to explore is debugging with Visual Studio for Mac.</span></span> <span data-ttu-id="77be3-232">`Console.WriteLine` 문에서 중단점을 설정합니다. 줄 23의 왼쪽 여백을 선택하면 코드 줄 옆에 빨간색 원이 표시되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-232">Set a breakpoint on the `Console.WriteLine` statement: Select in the left margin of line 23, and you see a red circle appear next to the line of code.</span></span> <span data-ttu-id="77be3-233">또는 코드 줄의 아무 위치나 선택하고 메뉴에서 **실행** > **중단점 설정/해제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-233">Alternatively, select anywhere on the line of code and select **Run** > **Toggle Breakpoint** from the menu.</span></span>

   ![중단점은 줄 23, Console.WriteLine 문에 설정됨](./media/using-on-mac-vs-full-solution/vsmacfull15.png)

1. <span data-ttu-id="77be3-235">`WordCounterApp` 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-235">Right-click the `WordCounterApp` project.</span></span> <span data-ttu-id="77be3-236">상황에 맞는 메뉴에서 **디버깅 시작** 항목을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-236">Select **Start Debugging item** from the context menu.</span></span> <span data-ttu-id="77be3-237">앱이 실행될 때 검색 단어 "cat" 및 검색할 문자열 "The dog chased the cat, but the cat escaped."를</span><span class="sxs-lookup"><span data-stu-id="77be3-237">When the app runs, enter the search word "cat" and "The dog chased the cat, but the cat escaped."</span></span> <span data-ttu-id="77be3-238">입력합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-238">for the string to search.</span></span> <span data-ttu-id="77be3-239">`Console.WriteLine` 문에 도달하면 프로그램 실행이 중단된 후 해당 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-239">When the `Console.WriteLine` statement is reached, program execution halts before the statement is executed.</span></span> <span data-ttu-id="77be3-240">**지역** 탭에 `searchWord`, `inputString`, `wordCount` 및 `pluralChar` 값이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-240">In the **Locals** tab, you can see the `searchWord`, `inputString`, `wordCount`, and `pluralChar` values.</span></span>

   ![Console.WriteLine 문에서 프로그램 실행이 중지되고 지역 창에 값이 표시된 직후에 Console.WriteLine 문이 실행됩니다.](./media/using-on-mac-vs-full-solution/vsmacfull16.png)

1. <span data-ttu-id="77be3-242">**직접 실행** 창에서 "wordCount = 999;"를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-242">In the **Immediate** pane, type "wordCount = 999;" and press Enter.</span></span> <span data-ttu-id="77be3-243">이렇게 하면 의미 없는 값인 999가 `wordCount` 변수에 할당되면서 디버그 동안 변수 값을 바꿀 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-243">This assigns a nonsense value of 999 to the `wordCount` variable showing that you can replace variable values while debugging.</span></span>

   ![중단점이 적중됩니다.](./media/using-on-mac-vs-full-solution/vsmacfull17.png)

1. <span data-ttu-id="77be3-246">도구 모음에서 *계속* 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-246">In the toolbar, click the *continue* arrow.</span></span> <span data-ttu-id="77be3-247">콘솔 창에서 출력을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-247">Look at the output in the console window.</span></span> <span data-ttu-id="77be3-248">앱을 디버그할 때 설정한 잘못된 값인 999가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="77be3-248">It reports the incorrect value of 999 that you set when you were debugging the app.</span></span>

   ![도구 모음의 계속 단추](./media/using-on-mac-vs-full-solution/vsmacfull18.png)

   ![앱 출력에서 검색 단어 개수가 값 999로 변경됨](./media/using-on-mac-vs-full-solution/vsmacfull19.png)

## <a name="see-also"></a><span data-ttu-id="77be3-251">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77be3-251">See also</span></span>

[<span data-ttu-id="77be3-252">Mac용 Visual Studio 2017 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="77be3-252">Visual Studio 2017 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2017-mac-relnotes)
