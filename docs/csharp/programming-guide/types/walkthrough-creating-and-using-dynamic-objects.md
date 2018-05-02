---
title: '연습: 동적 개체 만들기 및 사용(C# 및 Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dynamic objects [Visual Basic]
- dynamic objects
- dynamic objects [C#]
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 16c08ff42ce77b3901f5909571c528394d139e03
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-creating-and-using-dynamic-objects-c-and-visual-basic"></a><span data-ttu-id="b973f-102">연습: 동적 개체 만들기 및 사용(C# 및 Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b973f-102">Walkthrough: Creating and Using Dynamic Objects (C# and Visual Basic)</span></span>

<span data-ttu-id="b973f-103">동적 개체는 컴파일 시간이 아닌 런타임에 속성 및 메서드 같은 멤버를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-103">Dynamic objects expose members such as properties and methods at run time, instead of in at compile time.</span></span> <span data-ttu-id="b973f-104">이를 통해 형식 또는 정적 형식과 일치하지 않는 구조와 작동할 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-104">This enables you to create objects to work with structures that do not match a static type or format.</span></span> <span data-ttu-id="b973f-105">예를 들어 동적 개체를 사용하여 DOM(문서 개체 모델)을 참조할 수 있습니다. DOM에는 유효한 HTML 마크업 요소 및 특성의 조합을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-105">For example, you can use a dynamic object to reference the HTML Document Object Model (DOM), which can contain any combination of valid HTML markup elements and attributes.</span></span> <span data-ttu-id="b973f-106">각 HTML 문서는 고유하므로, 특정 HTML 문서에 대한 멤버는 런타임에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-106">Because each HTML document is unique, the members for a particular HTML document are determined at run time.</span></span> <span data-ttu-id="b973f-107">HTML 요소의 특성을 참조하는 일반적인 방법은 요소의 `GetProperty` 메서드에 특성의 이름을 전달하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-107">A common method to reference an attribute of an HTML element is to pass the name of the attribute to the `GetProperty` method of the element.</span></span> <span data-ttu-id="b973f-108">HTML 요소 `<div id="Div1">`의 `id` 특성을 참조하려면 먼저 `<div>` 요소에 대한 참조를 가져온 다음 `divElement.GetProperty("id")`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-108">To reference the `id` attribute of the HTML element `<div id="Div1">`, you first obtain a reference to the `<div>` element, and then use `divElement.GetProperty("id")`.</span></span> <span data-ttu-id="b973f-109">동적 개체를 사용하는 경우 `id` 특성을 `divElement.id`로서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-109">If you use a dynamic object, you can reference the `id` attribute as `divElement.id`.</span></span>  
  
 <span data-ttu-id="b973f-110">동적 개체를 사용하면 IronPython 및 IronRuby와 같은 동적 언어에 편리하게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-110">Dynamic objects also provide convenient access to dynamic languages such as IronPython and IronRuby.</span></span> <span data-ttu-id="b973f-111">동적 개체를 사용하면 런타임에 해석되는 동적 스크립트를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-111">You can use a dynamic object to refer to a dynamic script that is interpreted at run time.</span></span>  
  
 <span data-ttu-id="b973f-112">런타임에 바인딩을 사용하여 동적 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-112">You reference a dynamic object by using late binding.</span></span> <span data-ttu-id="b973f-113">C#에서는 런타임에 바인딩된 개체의 형식을 `dynamic`으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-113">In C#, you specify the type of a late-bound object as `dynamic`.</span></span> <span data-ttu-id="b973f-114">Visual Basic에서는 런타임에 바인딩된 개체의 형식을 `Object`으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-114">In Visual Basic, you specify the type of a late-bound object as `Object`.</span></span> <span data-ttu-id="b973f-115">자세한 내용은 [dynamic](../../../csharp/language-reference/keywords/dynamic.md) 및 [초기 바인딩 및 런타임에 바인딩](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b973f-115">For more information, see [dynamic](../../../csharp/language-reference/keywords/dynamic.md) and [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).</span></span>  
  
 <span data-ttu-id="b973f-116"><xref:System.Dynamic?displayProperty=nameWithType> 네임스페이스의 클래스를 사용하여 사용자 지정 동적 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-116">You can create custom dynamic objects by using the classes in the <xref:System.Dynamic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="b973f-117">예를 들어 <xref:System.Dynamic.ExpandoObject>를 만들고 해당 개체의 멤버를 런타임에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-117">For example, you can create an <xref:System.Dynamic.ExpandoObject> and specify the members of that object at run time.</span></span> <span data-ttu-id="b973f-118"><xref:System.Dynamic.DynamicObject> 클래스를 상속하는 고유한 형식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-118">You can also create your own type that inherits the <xref:System.Dynamic.DynamicObject> class.</span></span> <span data-ttu-id="b973f-119">그런 다음 런타임 동적 기능을 제공하도록 <xref:System.Dynamic.DynamicObject> 클래스의 멤버를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-119">You can then override the members of the <xref:System.Dynamic.DynamicObject> class to provide run-time dynamic functionality.</span></span>  
  
 <span data-ttu-id="b973f-120">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-120">In this walkthrough you will perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b973f-121">텍스트 파일의 내용을 개체의 속성으로서 동적으로 노출하는 사용자 지정 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-121">Create a custom object that dynamically exposes the contents of a text file as properties of an object.</span></span>  
  
-   <span data-ttu-id="b973f-122">`IronPython` 라이브러리를 사용하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-122">Create a project that uses an `IronPython` library.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b973f-123">전제 조건</span><span class="sxs-lookup"><span data-stu-id="b973f-123">Prerequisites</span></span>  
<span data-ttu-id="b973f-124">이 연습을 완료하려면 .NET용 [IronPython](http://ironpython.net/)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-124">You need [IronPython](http://ironpython.net/) for .NET to complete this walkthrough.</span></span> <span data-ttu-id="b973f-125">[다운로드 페이지](http://ironpython.net/download/)로 이동하여 최신 버전을 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="b973f-125">Go to their [Download page](http://ironpython.net/download/) to obtain the latest version.</span></span>
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-custom-dynamic-object"></a><span data-ttu-id="b973f-126">사용자 지정 동적 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="b973f-126">Creating a Custom Dynamic Object</span></span>  
 <span data-ttu-id="b973f-127">이 연습에서 만드는 첫 번째 프로젝트는 텍스트 파일의 내용을 검색하는 사용자 지정 동적 개체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-127">The first project that you create in this walkthrough defines a custom dynamic object that searches the contents of a text file.</span></span> <span data-ttu-id="b973f-128">검색할 텍스트는 동적 속성의 이름으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-128">Text to search for is specified by the name of a dynamic property.</span></span> <span data-ttu-id="b973f-129">예를 들어, 호출 코드가 `dynamicFile.Sample`을 지정하면 동적 클래스는 "Sample"로 시작하는 파일의 모든 줄을 포함하는 문자열의 제네릭 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-129">For example, if calling code specifies `dynamicFile.Sample`, the dynamic class returns a generic list of strings that contains all of the lines from the file that begin with "Sample".</span></span> <span data-ttu-id="b973f-130">검색은 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-130">The search is case-insensitive.</span></span> <span data-ttu-id="b973f-131">동적 클래스는 또한 두 개의 선택적 인수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-131">The dynamic class also supports two optional arguments.</span></span> <span data-ttu-id="b973f-132">첫 번째 인수는 동적 클래스가 행의 시작, 행의 끝 또는 행의 어디에서나 일치를 검색하도록 지정하는 검색 옵션 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-132">The first argument is a search option enum value that specifies that the dynamic class should search for matches at the start of the line, the end of the line, or anywhere in the line.</span></span> <span data-ttu-id="b973f-133">두 번째 인수는 동적 클래스가 검색 전에 각 행의 선행 및 후행 공백을 잘라내야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-133">The second argument specifies that the dynamic class should trim leading and trailing spaces from each line before searching.</span></span> <span data-ttu-id="b973f-134">예를 들어 호출 코드가 `dynamicFile.Sample(StringSearchOption.Contains)`을 지정하면 동적 클래스는 한 줄의 어디에서나 "Sample"을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-134">For example, if calling code specifies `dynamicFile.Sample(StringSearchOption.Contains)`, the dynamic class searches for "Sample" anywhere in a line.</span></span> <span data-ttu-id="b973f-135">호출 코드가 `dynamicFile.Sample(StringSearchOption.StartsWith, false)`을 지정하면 동적 클래스는 각 줄의 시작 부분에서 "Sample"을 검색하고, 선행 및 후행 공백을 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-135">If calling code specifies `dynamicFile.Sample(StringSearchOption.StartsWith, false)`, the dynamic class searches for "Sample" at the start of each line, and does not remove leading and trailing spaces.</span></span> <span data-ttu-id="b973f-136">동적 클래스의 기본 동작은 각 줄의 시작 부분에서 일치를 검색하고 선행 및 후행 공백을 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-136">The default behavior of the dynamic class is to search for a match at the start of each line and to remove leading and trailing spaces.</span></span>  
  
#### <a name="to-create-a-custom-dynamic-class"></a><span data-ttu-id="b973f-137">사용자 지정 동적 클래스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b973f-137">To create a custom dynamic class</span></span>  
  
1.  <span data-ttu-id="b973f-138">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-138">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="b973f-139">**파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-139">On the **File** menu, point to **New** and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="b973f-140">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-140">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="b973f-141">**템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-141">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="b973f-142">**이름** 상자에 `DynamicSample`를 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-142">In the **Name** box, type `DynamicSample`, and then click **OK**.</span></span> <span data-ttu-id="b973f-143">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-143">The new project is created.</span></span>  
  
4.  <span data-ttu-id="b973f-144">DynamicSample 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **클래스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-144">Right-click the DynamicSample project and point to **Add**, and then click **Class**.</span></span> <span data-ttu-id="b973f-145">**이름** 상자에 `ReadOnlyFile`을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-145">In the **Name** box, type `ReadOnlyFile`, and then click **OK**.</span></span> <span data-ttu-id="b973f-146">ReadOnlyFile 클래스가 포함된 새 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-146">A new file is added that contains the ReadOnlyFile class.</span></span>  
  
5.  <span data-ttu-id="b973f-147">ReadOnlyFile.cs 또는 ReadOnlyFile.vb 파일 맨 위에 다음 코드를 추가하여 <xref:System.IO?displayProperty=nameWithType> 및 <xref:System.Dynamic?displayProperty=nameWithType> 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-147">At the top of the ReadOnlyFile.cs or ReadOnlyFile.vb file, add the following code to import the <xref:System.IO?displayProperty=nameWithType> and <xref:System.Dynamic?displayProperty=nameWithType> namespaces.</span></span>  
  
     [!code-csharp[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_1.cs)]

     [!code-vb[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_1.vb)]  
  
6.  <span data-ttu-id="b973f-148">사용자 지정 동적 개체는 열거형을 사용하여 검색 기준을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-148">The custom dynamic object uses an enum to determine the search criteria.</span></span> <span data-ttu-id="b973f-149">Class 문 앞에 다음 열거형 정의를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-149">Before the class statement, add the following enum definition.</span></span>  
  
     [!code-csharp[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_2.cs)]

     [!code-vb[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_2.vb)]  
  
7.  <span data-ttu-id="b973f-150">다음 코드 예제와 같이, `DynamicObject` 클래스를 상속하도록 class 문을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-150">Update the class statement to inherit the `DynamicObject` class, as shown in the following code example.</span></span>  
  
     [!code-csharp[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_3.cs)]

     [!code-vb[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_3.vb)]  
  
8.  <span data-ttu-id="b973f-151">다음 코드를 `ReadOnlyFile` 클래스에 추가하여 파일 경로의 전용 필드 및 `ReadOnlyFile` 클래스의 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-151">Add the following code to the `ReadOnlyFile` class to define a private field for the file path and a constructor for the `ReadOnlyFile` class.</span></span>  
  
     [!code-csharp[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_4.cs)]
     
     [!code-vb[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_4.vb)]  
  
9. <span data-ttu-id="b973f-152">다음 `GetPropertyValue` 메서드를 `ReadOnlyFile` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-152">Add the following `GetPropertyValue` method to the `ReadOnlyFile` class.</span></span> <span data-ttu-id="b973f-153">`GetPropertyValue` 메서드는 검색 기준을 입력으로 가져오고 해당 검색 기준과 일치하는 텍스트 파일로부터 줄을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-153">The `GetPropertyValue` method takes, as input, search criteria and returns the lines from a text file that match that search criteria.</span></span> <span data-ttu-id="b973f-154">`ReadOnlyFile` 클래스가 제공하는 동적 메서드는 `GetPropertyValue` 메서드를 호출하여 각 결과를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-154">The dynamic methods provided by the `ReadOnlyFile` class call the `GetPropertyValue` method to retrieve their respective results.</span></span>  
  
     [!code-csharp[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_5.cs)]
     
     [!code-vb[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_5.vb)]  
  
10. <span data-ttu-id="b973f-155">`GetPropertyValue` 메서드 뒤에 다음 코드를 추가하여 <xref:System.Dynamic.DynamicObject> 클래스의 <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-155">After the `GetPropertyValue` method, add the following code to override the <xref:System.Dynamic.DynamicObject.TryGetMember%2A> method of the <xref:System.Dynamic.DynamicObject> class.</span></span> <span data-ttu-id="b973f-156">동적 클래스의 멤버를 요청했는데 지정된 인수가 없는 경우 <xref:System.Dynamic.DynamicObject.TryGetMember%2A> 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-156">The <xref:System.Dynamic.DynamicObject.TryGetMember%2A> method is called when a member of a dynamic class is requested and no arguments are specified.</span></span> <span data-ttu-id="b973f-157">`binder` 인수는 참조된 멤버에 대한 정보를 포함하며, `result` 인수는 지정된 멤버에 대해 반환된 결과를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-157">The `binder` argument contains information about the referenced member, and the `result` argument references the result returned for the specified member.</span></span> <span data-ttu-id="b973f-158"><xref:System.Dynamic.DynamicObject.TryGetMember%2A> 메서드는 요청한 멤버가 있는 경우 `true`, 없는 경우 `false`를 반환하는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-158">The <xref:System.Dynamic.DynamicObject.TryGetMember%2A> method returns a Boolean value that returns `true` if the requested member exists; otherwise it returns `false`.</span></span>  
  
     [!code-csharp[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_6.cs)]
     
     [!code-vb[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_6.vb)]  
  
11. <span data-ttu-id="b973f-159">`TryGetMember` 메서드 뒤에 다음 코드를 추가하여 <xref:System.Dynamic.DynamicObject> 클래스의 <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-159">After the `TryGetMember` method, add the following code to override the <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> method of the <xref:System.Dynamic.DynamicObject> class.</span></span> <span data-ttu-id="b973f-160">인수를 사용하여 동적 클래스의 멤버를 요청하면 <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-160">The <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> method is called when a member of a dynamic class is requested with arguments.</span></span> <span data-ttu-id="b973f-161">`binder` 인수는 참조된 멤버에 대한 정보를 포함하며, `result` 인수는 지정된 멤버에 대해 반환된 결과를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-161">The `binder` argument contains information about the referenced member, and the `result` argument references the result returned for the specified member.</span></span> <span data-ttu-id="b973f-162">`args` 인수는 멤버에 전달되는 인수의 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-162">The `args` argument contains an array of the arguments that are passed to the member.</span></span> <span data-ttu-id="b973f-163"><xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> 메서드는 요청한 멤버가 있는 경우 `true`, 없는 경우 `false`를 반환하는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-163">The <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> method returns a Boolean value that returns `true` if the requested member exists; otherwise it returns `false`.</span></span>  
  
     <span data-ttu-id="b973f-164">`TryInvokeMember` 메서드의 사용자 지정 버전은 첫 번째 인수로 이전 단계에서 정의한 `StringSearchOption` 열거형의 값을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-164">The custom version of the `TryInvokeMember` method expects the first argument to be a value from the `StringSearchOption` enum that you defined in a previous step.</span></span> <span data-ttu-id="b973f-165">`TryInvokeMember` 메서드는 두 번째 인수로 부울 값을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-165">The `TryInvokeMember` method expects the second argument to be a Boolean value.</span></span> <span data-ttu-id="b973f-166">하나 또는 두 인수가 유효한 값인 경우 결과를 검색할 수 있도록 `GetPropertyValue` 메서드로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-166">If one or both arguments are valid values, they are passed to the `GetPropertyValue` method to retrieve the results.</span></span>  
  
     [!code-csharp[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_7.cs)]
     
     [!code-vb[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_7.vb)]  
  
12. <span data-ttu-id="b973f-167">파일을 저장한 후 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-167">Save and close the file.</span></span>  
  
#### <a name="to-create-a-sample-text-file"></a><span data-ttu-id="b973f-168">샘플 텍스트 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b973f-168">To create a sample text file</span></span>  
  
1.  <span data-ttu-id="b973f-169">DynamicSample 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-169">Right-click the DynamicSample project and point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="b973f-170">**설치된 템플릿** 창에서 **일반**을 선택한 다음 **텍스트 파일** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-170">In the **Installed Templates** pane, select **General**, and then select the **Text File** template.</span></span> <span data-ttu-id="b973f-171">**이름** 상자에 있는 기본 이름 TextFile1.txt를 그대로 두고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-171">Leave the default name of TextFile1.txt in the **Name** box, and then click **Add**.</span></span> <span data-ttu-id="b973f-172">새 텍스트 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-172">A new text file is added to the project.</span></span>  
  
2.  <span data-ttu-id="b973f-173">TextFile1.txt 파일에 다음 텍스트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-173">Copy the following text to the TextFile1.txt file.</span></span>  
  
    ```  
    List of customers and suppliers  
  
    Supplier: Lucerne Publishing (http://www.lucernepublishing.com/)  
    Customer: Preston, Chris  
    Customer: Hines, Patrick  
    Customer: Cameron, Maria  
    Supplier: Graphic Design Institute (http://www.graphicdesigninstitute.com/)   
    Supplier: Fabrikam, Inc. (http://www.fabrikam.com/)   
    Customer: Seubert, Roxanne  
    Supplier: Proseware, Inc. (http://www.proseware.com/)   
    Customer: Adolphi, Stephan  
    Customer: Koch, Paul  
    ```  
  
3.  <span data-ttu-id="b973f-174">파일을 저장한 후 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-174">Save and close the file.</span></span>  
  
#### <a name="to-create-a-sample-application-that-uses-the-custom-dynamic-object"></a><span data-ttu-id="b973f-175">사용자 지정 동적 개체를 사용하는 샘플 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b973f-175">To create a sample application that uses the custom dynamic object</span></span>  
  
1.  <span data-ttu-id="b973f-176">**솔루션 탐색기**에서, Visual Basic을 사용 중인 경우 Module1.vb 파일, Visual C#을 사용 중인 경우 Program.cs 파일을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-176">In **Solution Explorer**, double-click the Module1.vb file if you are using Visual Basic or the Program.cs file if you are using Visual C#.</span></span>  
  
2.  <span data-ttu-id="b973f-177">Main 프로시저에 다음 코드를 추가하여 TextFile1.txt 파일에 대한 `ReadOnlyFile` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-177">Add the following code to the Main procedure to create an instance of the `ReadOnlyFile` class for the TextFile1.txt file.</span></span> <span data-ttu-id="b973f-178">코드는 런타임에 바인딩을 사용하여 동적 멤버를 호출하고 "Customer" 문자열이 포함된 텍스트의 줄을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-178">The code uses late binding to call dynamic members and retrieve lines of text that contain the string "Customer".</span></span>  
  
     [!code-csharp[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_8.cs)]
     
     [!code-vb[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_8.vb)]  
  
3.  <span data-ttu-id="b973f-179">파일을 저장한 다음 Ctrl+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-179">Save the file and press CTRL+F5 to build and run the application.</span></span>  
  
## <a name="calling-a-dynamic-language-library"></a><span data-ttu-id="b973f-180">동적 언어 라이브러리 호출</span><span class="sxs-lookup"><span data-stu-id="b973f-180">Calling a Dynamic Language Library</span></span>  

<span data-ttu-id="b973f-181">이 연습에서 만드는 새 프로젝트는 동적 언어 IronPython에서 작성된 라이브러리에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-181">The next project that you create in this walkthrough accesses a library that is written in the dynamic language IronPython.</span></span>
  
#### <a name="to-create-a-custom-dynamic-class"></a><span data-ttu-id="b973f-182">사용자 지정 동적 클래스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b973f-182">To create a custom dynamic class</span></span>  
  
1.  <span data-ttu-id="b973f-183">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-183">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="b973f-184">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Windows**가 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-184">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="b973f-185">**템플릿** 창에서 **콘솔 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-185">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="b973f-186">**이름** 상자에 `DynamicIronPythonSample`를 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-186">In the **Name** box, type `DynamicIronPythonSample`, and then click **OK**.</span></span> <span data-ttu-id="b973f-187">새 프로젝트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-187">The new project is created.</span></span>  
  
3.  <span data-ttu-id="b973f-188">Visual Basic을 사용 중인 경우 DynamicIronPythonSample 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-188">If you are using Visual Basic, right-click the DynamicIronPythonSample project and then click **Properties**.</span></span> <span data-ttu-id="b973f-189">**참조** 탭을 클릭합니다. **추가** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-189">Click the **References** tab. Click the **Add** button.</span></span> <span data-ttu-id="b973f-190">Visual C#을 사용 중인 경우 **솔루션 탐색기**에서 **References** 폴더를 마우스 오른쪽 단추로 클릭한 다음 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-190">If you are using Visual C#, in **Solution Explorer**, right-click the **References** folder and then click **Add Reference**.</span></span>  
  
4.  <span data-ttu-id="b973f-191">**찾아보기** 탭에서 IronPython 라이브러리가 설치된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-191">On the **Browse** tab, browse to the folder where the IronPython libraries are installed.</span></span> <span data-ttu-id="b973f-192">예를 들어 .NET 4.0의 경우 C:\Program Files\IronPython 2.6입니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-192">For example, C:\Program Files\IronPython 2.6 for .NET 4.0.</span></span> <span data-ttu-id="b973f-193">**IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** 및 **Microsoft.Dynamic.dll** 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-193">Select the **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll**, and **Microsoft.Dynamic.dll** libraries.</span></span> <span data-ttu-id="b973f-194">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-194">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="b973f-195">Visual Basic을 사용 중인 경우 Module1.vb 파일을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-195">If you are using Visual Basic, edit the Module1.vb file.</span></span> <span data-ttu-id="b973f-196">Visual C#을 사용 중인 경우 Program.cs 파일을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-196">If you are using Visual C#, edit the Program.cs file.</span></span>  
  
6.  <span data-ttu-id="b973f-197">파일 맨 위에 다음 코드를 추가하여 IronPython 라이브러리에서 `Microsoft.Scripting.Hosting` 및 `IronPython.Hosting` 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-197">At the top of the file, add the following code to import the `Microsoft.Scripting.Hosting` and `IronPython.Hosting` namespaces from the IronPython libraries.</span></span>  
  
     [!code-csharp[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_9.cs)]
     
     [!code-vb[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_9.vb)]  
  
7.  <span data-ttu-id="b973f-198">Main 메서드에서 다음 코드를 추가하여 IronPython 라이브러리를 호스트하기 위한 새 `Microsoft.Scripting.Hosting.ScriptRuntime` 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-198">In the Main method, add the following code to create a new `Microsoft.Scripting.Hosting.ScriptRuntime` object to host the IronPython libraries.</span></span> <span data-ttu-id="b973f-199">`ScriptRuntime` 개체는 IronPython 라이브러리 모듈 random.py를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-199">The `ScriptRuntime` object loads the IronPython library module random.py.</span></span>  
  
     [!code-csharp[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_10.cs)]
     
     [!code-vb[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_10.vb)]  
  
8.  <span data-ttu-id="b973f-200">random.py 모듈을 로드할 코드 뒤에 다음 코드를 추가하여 정수 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-200">After the code to load the random.py module, add the following code to create an array of integers.</span></span> <span data-ttu-id="b973f-201">배열은 random.py 모듈의 `shuffle` 메서드로 전달되며, 이 모듈은 배열의 값을 임의로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-201">The array is passed to the `shuffle` method of the random.py module, which randomly sorts the values in the array.</span></span>  
  
     [!code-csharp[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_11.cs)]
     
     [!code-vb[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_11.vb)]  
  
9. <span data-ttu-id="b973f-202">파일을 저장한 다음 Ctrl+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b973f-202">Save the file and press CTRL+F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b973f-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b973f-203">See Also</span></span>  
 <xref:System.Dynamic?displayProperty=nameWithType>  
 <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>  
 [<span data-ttu-id="b973f-204">dynamic 형식 사용</span><span class="sxs-lookup"><span data-stu-id="b973f-204">Using Type dynamic</span></span>](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [<span data-ttu-id="b973f-205">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="b973f-205">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [<span data-ttu-id="b973f-206">dynamic</span><span class="sxs-lookup"><span data-stu-id="b973f-206">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
 [<span data-ttu-id="b973f-207">동적 인터페이스 구현(Microsoft TechNet에서 다운로드 가능한 PDF)</span><span class="sxs-lookup"><span data-stu-id="b973f-207">Implementing Dynamic Interfaces (downloadable PDF from Microsoft TechNet)</span></span>](http://download.microsoft.com/download/5/4/B/54B83DFE-D7AA-4155-9687-B0CF58FF65D7/implementing-dynamic-interfaces.pdf)
