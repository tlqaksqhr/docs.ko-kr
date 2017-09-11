---
title: "Visual Studio 2017에서 Visual Basic 및 .NET Core로 클래스 라이브러리 빌드"
description: "Visual Studio 2017을 사용하여 Visual Basic으로 작성된 클래스 라이브러리를 빌드하는 방법 알아보기"
keywords: ".NET Core, .NET Standard 클래스 라이브러리, Visual Studio 2017, Visual Basic"
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-vb
ms.devlang: vb
ms.translationtype: HT
ms.sourcegitcommit: 3a25c1c3b540bac8ef963a8bbf708b0700c3e9e2
ms.openlocfilehash: a933e1eef6e4e9814aeba4206469a64563a7e91d
ms.contentlocale: ko-kr
ms.lasthandoff: 08/12/2017

---

# <a name="building-a-class-library-with-visual-basic-and-net-core-in-visual-studio-2017"></a><span data-ttu-id="594d2-104">Visual Studio 2017에서 Visual Basic 및 .NET Core로 클래스 라이브러리 빌드</span><span class="sxs-lookup"><span data-stu-id="594d2-104">Building a class library with Visual Basic and .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="594d2-105">*클래스 라이브러리*는 응용 프로그램에서 호출되는 형식 및 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="594d2-106">.NET Standard 2.0을 대상으로 하는 클래스 라이브러리는 .NET Standard의 해당 버전을 지원하는 모든 .NET 구현에서 라이브러리를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-106">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="594d2-107">클래스 라이브러리를 마칠 때 타사 구성 요소로 배포할지 또는 하나 이상의 응용 프로그램과 함께 번들 구성 요소로 포함할지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-107">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="594d2-108">.NET Standard 버전 및 지원되는 플랫폼 목록은 [.NET Standard](../../standard/net-standard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="594d2-108">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="594d2-109">이 항목에서는 단일 문자열 처리 메서드를 포함하는 간단한 유틸리티 라이브러리를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-109">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="594d2-110"><xref:System.String> 클래스의 멤버인 것처럼 호출할 수 있도록 [확장 메서드](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)로 구현하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-110">You'll implement it as an [extension method](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="594d2-111">클래스 라이브러리 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="594d2-111">Creating a class library solution</span></span>

<span data-ttu-id="594d2-112">먼저 클래스 라이브러리 프로젝트의 솔루션과 관련 프로젝트를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-112">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="594d2-113">Visual Studio 솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-113">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="594d2-114">솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="594d2-114">To create the solution:</span></span>

1. <span data-ttu-id="594d2-115">Visual Studio 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-115">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="594d2-116">**새 프로젝트** 대화 상자에서 **기타 프로젝트 형식** 노드를 확장하고 **Visual Studio 솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-116">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="594d2-117">솔루션의 이름을 "ClassLibraryProjects"로 지정하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-117">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![새 프로젝트 대화 상자](./media/library-with-visual-studio/newproject.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="594d2-119">클래스 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="594d2-119">Creating the class library project</span></span>

<span data-ttu-id="594d2-120">클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-120">Create your class library project:</span></span>

1. <span data-ttu-id="594d2-121">**솔루션 탐색기**에서 **ClassLibraryProjects** 솔루션 파일을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-121">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="594d2-122">**새 프로젝트 추가** 대화 상자에서 **Visual Basic** 노드를 확장하고 **.NET Standard** 노드, **클래스 라이브러리(.NET Standard)** 프로젝트 템플릿을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-122">In the **Add New Project** dialog, expand the **Visual Basic** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="594d2-123">**이름** 텍스트 상자에 프로젝트 이름으로 "StringLibrary"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-123">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="594d2-124">**확인**을 선택하여 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-124">Select **OK** to create the class library project.</span></span>

   ![새 프로젝트 추가 대화 상자](./media/vb-library-with-visual-studio/libproject.png)

   <span data-ttu-id="594d2-126">그런 다음 코드 창이 Visual Studio 개발 환경에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-126">The code window then opens in the Visual Studio development environment.</span></span> 
 
   ![기본 클래스 라이브러리 템플릿 코드를 보여 주는 Visual Studio 응용 프로그램 창](./media/vb-library-with-visual-studio/stringlibrary.png)

1. <span data-ttu-id="594d2-128">라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-128">Check to make sure that the library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="594d2-129">**솔루션 탐색기** 창에서 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-129">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="594d2-130">**대상 프레임워크** 텍스트 상자에 .NET Standard 2.0을 대상으로 하는 것이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-130">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![클래스 라이브러리에 대한 프로젝트 속성](./media/library-with-visual-studio/properties.png)

1. <span data-ttu-id="594d2-132">또한 **속성** 대화 상자에서 **루트 네임스페이스** 텍스트 상자의 텍스트를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-132">Also in the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="594d2-133">각 프로젝트에 대해 Visual Basic에서는 프로젝트 이름에 해당하는 네임스페이스를 자동으로 만들고, 소스 코드 파일에 정의된 네임스페이스는 해당 네임스페이스의 부모입니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-133">For each project, Visual Basic automatically creates a namespace that corresponds to the project name, and any namespaces defined in source code files are parents of that namespace.</span></span> <span data-ttu-id="594d2-134">[`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) 키워드를 사용하여 최상위 네임스페이스를 정의하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-134">We want to define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword.</span></span>
  
1. <span data-ttu-id="594d2-135">코드 창의 코드를 다음 코드로 바꾸고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-135">Replace the code in the code window with the following code and save the file:</span></span>

  <span data-ttu-id="594d2-136">[!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]</span><span class="sxs-lookup"><span data-stu-id="594d2-136">[!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]</span></span>

   <span data-ttu-id="594d2-137">클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함됩니다. 이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-137">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="594d2-138">유니코드 표준은 대문자와 소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-138">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="594d2-139"><xref:System.Char.IsUpper(System.Char)?displayProperty=fullName> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-139">The <xref:System.Char.IsUpper(System.Char)?displayProperty=fullName> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="594d2-140">메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-140">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="594d2-141">프로젝트가 오류 없이 컴파일되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-141">The project should compile without error.</span></span>

   ![빌드에 성공했음을 표시하는 출력 창](./media/library-with-visual-studio/buildsucceeds.png)



## <a name="next-step"></a><span data-ttu-id="594d2-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="594d2-143">Next step</span></span>

<span data-ttu-id="594d2-144">라이브러리를 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-144">You've successfully built the library.</span></span> <span data-ttu-id="594d2-145">해당 메서드를 호출하지 않았으므로 예상대로 작동하는지 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-145">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="594d2-146">라이브러리 개발의 다음 단계는 [단위 테스트 프로젝트](testing-library-with-visual-studio.md)를 사용하여 테스트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="594d2-146">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>

