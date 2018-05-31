---
title: Visual Studio 2017에서 .NET Core로 클래스 라이브러리 테스트
description: Visual Studio 2017을 사용하여 C#으로 작성된 클래스 라이브러리를 테스트하는 방법 알아보기
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1733f3fc66d79dafb9bc6f983773f043be6c1006
ms.sourcegitcommit: b7763f3435635850a76d4cbcf09bdce6c019208a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2018
ms.locfileid: "34483475"
---
# <a name="testing-a-class-library-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="01370-103">Visual Studio 2017에서 .NET Core로 클래스 라이브러리 테스트</span><span class="sxs-lookup"><span data-stu-id="01370-103">Testing a class library with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="01370-104">[Visual Studio 2017에서 C# 및 .NET Core를 사용하여 클래스 라이브러리 빌드](library-with-visual-studio.md) 또는 [Visual Studio 2017에서 Visual Basic 및 .NET Core를 사용하여 클래스 라이브러리 빌드](vb-library-with-visual-studio.md)에서는 <xref:System.String> 클래스에 확장 메서드를 추가하는 간단한 클래스 라이브러리를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-104">In [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md) or [Building a class library with Visual Basic and .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="01370-105">이제 예상대로 작동하는지 확인하기 위한 단위 테스트를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-105">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="01370-106">이전 항목에서 만든 솔루션에 단위 테스트 프로젝트를 추가할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01370-106">You'll add your unit test project to the solution you created in the previous topic.</span></span>

## <a name="creating-a-unit-test-project"></a><span data-ttu-id="01370-107">단위 테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="01370-107">Creating a unit test project</span></span>

<span data-ttu-id="01370-108">단위 테스트 프로젝트를 만들려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-108">To create the unit test project, do the following:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="01370-109">C#</span><span class="sxs-lookup"><span data-stu-id="01370-109">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="01370-110">**솔루션 탐색기**에서 **ClassLibraryProject** 솔루션 노드의 상황에 맞는 메뉴를 열고 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-110">In **Solution Explorer**, open the context menu for the **ClassLibraryProjects** solution node and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="01370-111">**새 프로젝트 추가** 대화 상자에서 **Visual C#** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-111">In the **Add New Project** dialog, select the **Visual C#** node.</span></span> <span data-ttu-id="01370-112">그런 다음, **.NET Core** 노드, **MSTest 테스트 프로젝트(.NET Core)** 프로젝트 템플릿을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-112">Then select the **.NET Core** node followed by the **MSTest Test Project (.NET Core)** project template.</span></span> <span data-ttu-id="01370-113">**이름** 텍스트 상자에 프로젝트 이름으로 "StringLibraryTest"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-113">In the **Name** text box, enter "StringLibraryTest" as the name of the project.</span></span> <span data-ttu-id="01370-114">**확인**을 선택하여 단위 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01370-114">Select **OK** to create the unit test project.</span></span>

   ![새 프로젝트 추가 대화 상자](./media/testing-library-with-visual-studio/testproject.png)

   > [!NOTE]  
   > <span data-ttu-id="01370-116">MSTest 테스트 프로젝트 외에 Visual Studio를 사용하여 .NET Core에 대한 xUnit 테스트 프로젝트를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-116">In addition to an MSTest Test project, you can also use Visual Studio to create an xUnit test project for .NET Core.</span></span>

1. <span data-ttu-id="01370-117">Visual Studio가 해당 프로젝트를 만들고 코드 창에서 *UnitTest1.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="01370-117">Visual Studio creates the project and opens the *UnitTest1.cs* file in the code window.</span></span>

   ![기본 단위 테스트 프로젝트 UnitTest1 클래스 및 TestMethod1 메서드를 표시하는 Visual Studio 코드 창](./media/testing-library-with-visual-studio/unittestwindow.png)

   <span data-ttu-id="01370-119">단위 테스트 템플릿을 통해 만들어진 소스 코드는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-119">The source code created by the unit test template does the following:</span></span>

   * <span data-ttu-id="01370-120">단위 테스트에 사용되는 형식이 포함되어 있는 [Microsoft.VisualStudio.TestTools.UnitTesting](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.aspx) 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01370-120">It imports the [Microsoft.VisualStudio.TestTools.UnitTesting](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.aspx) namespace, which contains the types used for unit testing.</span></span>

   * <span data-ttu-id="01370-121">[ \[TestClass\] ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) 특성을 `UnitTest1` 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-121">It applies the [\[TestClass\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="01370-122">\[TestMethod\] 특성으로 태그가 지정된 테스트 클래스의 각 테스트 메서드는 단위 테스트를 실행할 때 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="01370-122">Each test method in a test class tagged with the \[TestMethod\] attribute is executed automatically when the unit test is run.</span></span>

   * <span data-ttu-id="01370-123">[\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) 특성을 적용하여 단위 테스트를 실행할 때 자동으로 실행되는 테스트 메서드로 `TestMethod1`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-123">It applies the [\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) attribute to define `TestMethod1` as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="01370-124">**솔루션 탐색기**에서 **StringLibraryTest** 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-124">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   ![StringLibraryTest 종속성의 상황에 맞는 메뉴](./media/testing-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="01370-126">**참조 관리자** 대화 상자에서 **프로젝트** 노드를 확장하고 **StringLibrary** 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-126">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="01370-127">`StringLibrary` 어셈블리에 대한 참조를 추가하면 컴파일러가 **StringLibrary** 메서드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-127">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="01370-128">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-128">Select the **OK** button.</span></span> <span data-ttu-id="01370-129">그러면 클래스 라이브러리 프로젝트 `StringLibrary`에 대한 참조가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="01370-129">This adds a reference to your class library project, `StringLibrary`.</span></span>

   ![참조 관리자](./media/testing-library-with-visual-studio/referencemanager.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="01370-131">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01370-131">Visual Basic</span></span>](#tab/visual-basic) 
1. <span data-ttu-id="01370-132">**솔루션 탐색기**에서 **ClassLibraryProject** 솔루션 노드의 상황에 맞는 메뉴를 열고 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-132">In **Solution Explorer**, open the context menu for the **ClassLibraryProjects** solution node and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="01370-133">**새 프로젝트 추가** 대화 상자에서 **Visual Basic** 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-133">In the **Add New Project** dialog, select the **Visual Basic** node.</span></span> <span data-ttu-id="01370-134">그런 다음, **.NET Core** 노드, **MSTest 테스트 프로젝트(.NET Core)** 프로젝트 템플릿을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-134">Then select the **.NET Core** node followed by the **MSTest Test Project (.NET Core)** project template.</span></span> <span data-ttu-id="01370-135">**이름** 텍스트 상자에 프로젝트 이름으로 "StringLibraryTest"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-135">In the **Name** text box, enter "StringLibraryTest" as the name of the project.</span></span> <span data-ttu-id="01370-136">**확인**을 선택하여 단위 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01370-136">Select **OK** to create the unit test project.</span></span>

   ![새 프로젝트 추가 대화 상자](./media/testing-library-with-visual-studio/vb-testproject.png)

   > [!NOTE]  
   > <span data-ttu-id="01370-138">MSTest 테스트 프로젝트 외에 Visual Studio를 사용하여 .NET Core에 대한 xUnit 테스트 프로젝트를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-138">In addition to an MSTest Test project, you can also use Visual Studio to create an xUnit test project for .NET Core.</span></span>

1. <span data-ttu-id="01370-139">Visual Studio가 해당 프로젝트를 만들고 코드 창에서 *UnitTest1.vb* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="01370-139">Visual Studio creates the project and opens the *UnitTest1.vb* file in the code window.</span></span>

   ![기본 단위 테스트 프로젝트 UnitTest1 클래스 및 TestMethod1 메서드를 표시하는 Visual Studio 코드 창](./media/testing-library-with-visual-studio/vb-unittestwindow.png)

   <span data-ttu-id="01370-141">단위 테스트 템플릿을 통해 만들어진 소스 코드는 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-141">The source code created by the unit test template does the following:</span></span>

   * <span data-ttu-id="01370-142">단위 테스트에 사용되는 형식이 포함되어 있는 [Microsoft.VisualStudio.TestTools.UnitTesting](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.aspx) 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01370-142">It imports the [Microsoft.VisualStudio.TestTools.UnitTesting](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.aspx) namespace, which contains the types used for unit testing.</span></span>

   * <span data-ttu-id="01370-143">[ \[TestClass\] ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) 특성을 `UnitTest1` 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-143">It applies the [\[TestClass\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="01370-144">\[TestMethod\] 특성으로 태그가 지정된 테스트 클래스의 각 테스트 메서드는 단위 테스트를 실행할 때 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="01370-144">Each test method in a test class tagged with the \[TestMethod\] attribute is executed automatically when the unit test is run.</span></span>

   * <span data-ttu-id="01370-145">[\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) 특성을 적용하여 단위 테스트를 실행할 때 자동으로 실행되는 테스트 메서드로 `TestMethod1`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-145">It applies the [\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) attribute to define `TestMethod1` as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="01370-146">**솔루션 탐색기**에서 **StringLibraryTest** 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-146">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   ![StringLibraryTest 종속성의 상황에 맞는 메뉴](./media/testing-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="01370-148">**참조 관리자** 대화 상자에서 **프로젝트** 노드를 확장하고 **StringLibrary** 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-148">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="01370-149">`StringLibrary` 어셈블리에 대한 참조를 추가하면 컴파일러가 **StringLibrary** 메서드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-149">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="01370-150">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-150">Select the **OK** button.</span></span> <span data-ttu-id="01370-151">그러면 클래스 라이브러리 프로젝트 `StringLibrary`에 대한 참조가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="01370-151">This adds a reference to your class library project, `StringLibrary`.</span></span>

   ![참조 관리자](./media/testing-library-with-visual-studio/referencemanager.png)
---

## <a name="adding-and-running-unit-test-methods"></a><span data-ttu-id="01370-153">단위 테스트 메서드 추가 및 실행</span><span class="sxs-lookup"><span data-stu-id="01370-153">Adding and running unit test methods</span></span>

<span data-ttu-id="01370-154">Visual Studio는 단위 테스트를 실행할 때 단위 테스트 클래스([\[TestClass\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) 특성이 적용된 클래스)에서 [\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) 특성으로 표시된 각 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-154">When Visual Studio runs a unit test, it executes each method marked with the [\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) attribute in a unit test class, the class to which the  [\[TestClass\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) attribute is applied.</span></span> <span data-ttu-id="01370-155">테스트 메서드는 첫 번째 오류가 발생하거나 메서드에 포함된 모든 테스트가 성공적으로 수행되면 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="01370-155">A test method ends when the first failure is encountered or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="01370-156">가장 일반적인 테스트는 [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx) 클래스의 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-156">The most common tests call members of the [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx) class.</span></span> <span data-ttu-id="01370-157">많은 어설션 메서드에는 2개 이상의 매개 변수가 포함되며, 그 중 하나는 예상된 테스트 결과이고, 다른 하나는 실제 테스트 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="01370-157">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="01370-158">가장 자주 호출되는 일부 메서드는 아래 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-158">Some of its most frequently called methods are shown in the table below.</span></span>

<span data-ttu-id="01370-159">Assert 메서드</span><span class="sxs-lookup"><span data-stu-id="01370-159">Assert methods</span></span> | <span data-ttu-id="01370-160">함수</span><span class="sxs-lookup"><span data-stu-id="01370-160">Function</span></span>
--- | ---
`Assert.AreEqual` | <span data-ttu-id="01370-161">두 개의 값이나 개체가 같은지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-161">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="01370-162">값이나 개체가 같지 않으면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-162">The assert fails if the values or objects are not equal.</span></span>
`Assert.AreSame` | <span data-ttu-id="01370-163">두 개의 개체 변수가 같은 개체를 참조하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-163">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="01370-164">변수가 서로 다른 개체를 참조하면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-164">The assert fails if the variables refer to different objects.</span></span>
`Assert.IsFalse` | <span data-ttu-id="01370-165">조건이 `false`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-165">Verifies that a condition is `false`.</span></span> <span data-ttu-id="01370-166">조건이 `true`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-166">The assert fails if the condition is `true`.</span></span>
`Assert.IsNotNull` | <span data-ttu-id="01370-167">개체가 `null`이 아닌지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-167">Verifies that an object is not `null`.</span></span> <span data-ttu-id="01370-168">개체가 `null`이면 어설션이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-168">The assert fails if the object is `null`.</span></span>

<span data-ttu-id="01370-169">테스트 메서드에 [\[ExpectedException\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.expectedexceptionattribute.aspx) 특성을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-169">You can also apply the [\[ExpectedException\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.expectedexceptionattribute.aspx) attribute to a test method.</span></span> <span data-ttu-id="01370-170">테스트 메서드에서 throw해야 하는 예외 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="01370-170">It indicates the type of exception a test method is expected to throw.</span></span> <span data-ttu-id="01370-171">지정된 예외가 throw되지 않으면 테스트가 실패한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01370-171">The test fails if the specified exception is not thrown.</span></span>

<span data-ttu-id="01370-172">`StringLibrary.StartsWithUpper` 메서드를 테스트할 때 대문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-172">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="01370-173">이러한 경우에 메서드가 `true`를 반환할 것으로 기대하므로 [Assert.IsTrue(Boolean, String)](https://msdn.microsoft.com/library/ms243754.aspx) 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-173">You expect the method to return `true` in these cases, so you can call the [Assert.IsTrue(Boolean, String)](https://msdn.microsoft.com/library/ms243754.aspx) method.</span></span> <span data-ttu-id="01370-174">마찬가지로, 대문자 이외의 문자로 시작하는 많은 문자열을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-174">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="01370-175">이러한 경우에 메서드가 `false`를 반환할 것으로 기대하므로 [Assert.IsFalse(Boolean, String)](https://msdn.microsoft.com/library/ms243805.aspx) 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-175">You expect the method to return `false` in these cases, so you can call the [Assert.IsFalse(Boolean, String)](https://msdn.microsoft.com/library/ms243805.aspx) method.</span></span>

<span data-ttu-id="01370-176">또한 라이브러리 메서드가 문자열을 처리하므로 [빈 문자열(`String.Empty`)](xref:System.String.Empty)(문자가 없고 해당 <xref:System.String.Length>가 0인 유효한 문자열) 및 `null` 문자열(초기화되지 않은 문자열)을 성공적으로 처리하는지 확인하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-176">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that has not been initialized.</span></span> <span data-ttu-id="01370-177">`StartsWithUpper`가 <xref:System.String> 인스턴스에 대한 확장 메서드로 호출될 경우 `null` 문자열이 제공될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-177">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it cannot be passed a `null` string.</span></span> <span data-ttu-id="01370-178">그러나 정적 메서드로 직접 호출하고 단일 <xref:System.String> 인수를 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-178">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="01370-179">각 메서드가 문자열 배열의 각 요소에 대해 해당 [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx) 메서드를 반복적으로 호출하는 메서드 3개를 정의해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-179">You'll define three methods, each of which calls its [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx) method repeatedly for each element in a string array.</span></span> <span data-ttu-id="01370-180">첫 번째 오류가 발생하는 즉시 테스트 메서드가 실패하기 때문에 메서드 호출에 사용되는 문자열 값을 나타내는 문자열을 전달할 수 있도록 하는 메서드 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-180">Because the test method fails as soon as it encounters the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="01370-181">테스트 메서드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="01370-181">To create the test methods:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="01370-182">C#</span><span class="sxs-lookup"><span data-stu-id="01370-182">C#</span></span>](#tab/csharp) 
1. <span data-ttu-id="01370-183">*UnitTest1.cs* 코드 창의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="01370-183">In the *UnitTest1.cs* code window, replace the code with the following code:</span></span>

   [!CODE-csharp[Test#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]

   <span data-ttu-id="01370-184">`TestStartsWithUpper` 메서드의 대문자 테스트는 그리스어 대문자 알파(U+0391) 및 키릴 자모 대문자 EM(U+041C)을 포함하고, `TestDoesNotStartWithUpper` 메서드의 소문자의 테스트는 그리스어 소문자 알파(U+03B1) 및 키릴 자모 소문자 Ghe(U+0433)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-184">Note that your test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C), and the test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="01370-185">메뉴 모음에서 **파일** > **다른 이름으로 UnitTest1.cs 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-185">On the menu bar, select **File** > **Save UnitTest1.cs As**.</span></span> <span data-ttu-id="01370-186">**다른 이름으로 파일 저장** 대화 상자에서 **저장** 단추 옆에 있는 화살표를 선택한 다음 **인코딩하여 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-186">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   ![다른 이름으로 파일 저장 대화 상자](./media/testing-library-with-visual-studio/savefileas.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="01370-188">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01370-188">Visual Basic</span></span>](#tab/visual-basic) 
1. <span data-ttu-id="01370-189">*UnitTest1.vb* 코드 창의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="01370-189">In the *UnitTest1.vb* code window, replace the code with the following code:</span></span>

    [!CODE-vb[Test#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="01370-190">`TestStartsWithUpper` 메서드의 대문자 테스트는 그리스어 대문자 알파(U+0391) 및 키릴 자모 대문자 EM(U+041C)을 포함하고, `TestDoesNotStartWithUpper` 메서드의 소문자의 테스트는 그리스어 소문자 알파(U+03B1) 및 키릴 자모 소문자 Ghe(U+0433)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-190">Note that your test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C), and the test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="01370-191">메뉴 모음에서 **파일** > **다른 이름으로 UnitTest1.vb 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-191">On the menu bar, select **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="01370-192">**다른 이름으로 파일 저장** 대화 상자에서 **저장** 단추 옆에 있는 화살표를 선택한 다음 **인코딩하여 저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-192">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   ![다른 이름으로 파일 저장 대화 상자](./media/testing-library-with-visual-studio/savefileas.png)
---

1. <span data-ttu-id="01370-194">**다른 이름으로 저장 확인** 대화 상자에서 **예** 단추를 선택하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-194">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="01370-195">**고급 저장 옵션** 대화 상자의 **인코딩** 드롭다운 목록에서 **유니코드(시그니처가 있는 UTF-8) - 코드 페이지 65001**을 선택한 다음 **확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-195">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   ![고급 저장 옵션 대화 상자](./media/testing-library-with-visual-studio/advancedsaveoptions.png)

   <span data-ttu-id="01370-197">소스 코드를 UTF8로 인코드된 파일에 저장하지 못하면 Visual Studio에서 해당 파일이 ASCII 파일로 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-197">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="01370-198">이 경우 런타임은 ASCII 범위 밖의 UTF8 문자를 정확히 디코드하지 않으며 테스트 결과가 정확하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01370-198">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be accurate.</span></span>

1. <span data-ttu-id="01370-199">메뉴 모음에서 **테스트** > **실행** > **모든 테스트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-199">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="01370-200">**테스트 탐색기** 창이 열리고 테스트가 성공적으로 실행되었는지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01370-200">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="01370-201">세 가지 테스트가 **통과한 테스트** 섹션에 표시되고 **요약** 섹션에 테스트 실행 결과가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="01370-201">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   ![테스트 탐색기 창](./media/testing-library-with-visual-studio/firsttest.png)

## <a name="handling-test-failures"></a><span data-ttu-id="01370-203">테스트 오류 처리</span><span class="sxs-lookup"><span data-stu-id="01370-203">Handling test failures</span></span>

<span data-ttu-id="01370-204">테스트를 실행할 때 오류가 발생하지는 않았지만 테스트 메서드 중 하나가 실패하도록 약간 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-204">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="01370-205">`TestDoesNotStartWithUpper` 메서드의 `words` 배열이 "Error" 문자열을 포함하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-205">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="01370-206">테스트를 실행하도록 솔루션을 빌드하면 Visual Studio에서 열려 있는 파일을 자동으로 저장하기 때문에 파일을 저장할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-206">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```
   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```
1. <span data-ttu-id="01370-207">메뉴 모음에서 **테스트** > **실행** > **모든 테스트**를 선택하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-207">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="01370-208">**테스트 탐색기** 창에 두 가지 테스트는 성공하고 한 가지 테스트는 실패한 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="01370-208">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   ![테스트 탐색기 창](./media/testing-library-with-visual-studio/failedtest.png)

1. <span data-ttu-id="01370-210">**실패한 테스트** 섹션에서 실패한 테스트 `TestDoesNotStartWith`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-210">In the **Failed Tests** section, select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="01370-211">**테스트 탐색기** 창에 어설션이 생성하는 메시지 "Assert.IsFalse가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-211">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="01370-212">'Error'에 필요한 값: false, 실제: True"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01370-212">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="01370-213">이 오류 때문에 "Error" 다음에 나오는 배열의 모든 문자열이 테스트되지는 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-213">Because of the failure, all strings in the array after "Error" were not tested.</span></span>

   ![Is False 어설션 실패를 표시하는 테스트 탐색기 창](./media/testing-library-with-visual-studio/failedtestdetail.png)

1. <span data-ttu-id="01370-215">추가한 코드(`"Error", `)를 제거하고 테스트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-215">Remove the code that you added (`"Error", `) and rerun the test.</span></span> <span data-ttu-id="01370-216">테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-216">The tests will pass.</span></span>

## <a name="testing-the-release-version-of-the-library"></a><span data-ttu-id="01370-217">라이브러리의 릴리스 버전 테스트</span><span class="sxs-lookup"><span data-stu-id="01370-217">Testing the Release version of the library</span></span>

<span data-ttu-id="01370-218">지금까지 디버그 버전의 라이브러리에 대한 테스트를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-218">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="01370-219">테스트를 모두 통과하고 라이브러리를 적절히 테스트했으므로 추가 시간 동안 라이브러리의 릴리스 빌드에 대해 테스트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-219">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="01370-220">컴파일러 최적화를 비롯한 여러 가지 요인 때문에 디버그 및 릴리스 빌드 간에 서로 다른 동작이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-220">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="01370-221">릴리스 빌드를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="01370-221">To test the Release build:</span></span>

1. <span data-ttu-id="01370-222">Visual Studio 도구 모음에서 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-222">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   ![Visual Studio 도구 모음](./media/testing-library-with-visual-studio/toolbar.png)

1. <span data-ttu-id="01370-224">**솔루션 탐색기**에서 **StringLibrary** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **빌드**를 선택하여 라이브러리를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-224">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   ![StringLibrary 상황에 맞는 메뉴](./media/testing-library-with-visual-studio/buildlibrary.png)

1. <span data-ttu-id="01370-226">메뉴 모음에서 **테스트** > **실행** > **모든 테스트**를 선택하여 단위 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-226">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="01370-227">테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="01370-227">The tests pass.</span></span>

<span data-ttu-id="01370-228">라이브러리에 테스트를 마쳤으므로 다음 단계는 호출자가 사용할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01370-228">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="01370-229">하나 이상의 응용 프로그램과 함께 번들로 묶거나 NuGet 패키지로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01370-229">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="01370-230">자세한 내용은 [.NET Standard 클래스 라이브러리 사용](./consuming-library-with-visual-studio.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01370-230">For more information, see [Consuming a .NET Standard Class Library](./consuming-library-with-visual-studio.md).</span></span>
