---
title: "네임스페이스 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.names
dev_langs:
- CSharp
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 61b5d78f1c4924e3858c14876d36e52d4ee46ceb
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="9240d-102">네임스페이스 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="9240d-102">Using Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="9240d-103">네임스페이스는 C# 프로그램 내에서 두 가지 방법으로 많이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="9240d-104">첫째, .NET Framework 클래스는 네임스페이스를 사용하여 많은 클래스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="9240d-105">둘째, 고유한 네임스페이스를 선언하면 대규모 프로그래밍 프로젝트에서 클래스 및 메서드 이름의 범위를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="9240d-106">네임스페이스 액세스</span><span class="sxs-lookup"><span data-stu-id="9240d-106">Accessing Namespaces</span></span>  
 <span data-ttu-id="9240d-107">대부분의 C# 응용 프로그램은 `using` 지시문 섹션으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="9240d-108">이 섹션에는 응용 프로그램이 자주 사용하는 네임스페이스가 나열되어, 프로그래머가 내부에 포함된 메서드를 사용할 때마다 정규화된 이름을 지정할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="9240d-109">예를 들어 다음 줄을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-109">For example, by including the line:</span></span>  
  
 <span data-ttu-id="9240d-110">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-110">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]</span></span>  
  
 <span data-ttu-id="9240d-111">프로그램의 시작 부분에서 프로그래머는 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-111">At the start of a program, the programmer can use the code:</span></span>  
  
 <span data-ttu-id="9240d-112">[!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-112">[!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]</span></span>  
  
 <span data-ttu-id="9240d-113">위 코드를 아래 코드 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-113">Instead of:</span></span>  
  
 <span data-ttu-id="9240d-114">[!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-114">[!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]</span></span>  
  
## <a name="namespace-aliases"></a><span data-ttu-id="9240d-115">네임스페이스 별칭</span><span class="sxs-lookup"><span data-stu-id="9240d-115">Namespace Aliases</span></span>  
 <span data-ttu-id="9240d-116">[using 지시문](../../../csharp/language-reference/keywords/using-directive.md)을 사용하여 [namespace](../../../csharp/language-reference/keywords/namespace.md)의 별칭을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-116">The [using Directive](../../../csharp/language-reference/keywords/using-directive.md) can also be used to create an alias for a [namespace](../../../csharp/language-reference/keywords/namespace.md).</span></span> <span data-ttu-id="9240d-117">예를 들어 중첩 네임스페이스가 포함된 이전에 작성한 네임스페이스를 사용하는 경우, 다음 예제와 같이 특정 네임스페이스를 약식으로 참조하는 별칭을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-117">For example, if you are using a previously written namespace that contains nested namespaces, you might want to declare an alias to provide a shorthand way of referencing one in particular, as in the following example:</span></span>  
  
 <span data-ttu-id="9240d-118">[!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-118">[!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]</span></span>  
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="9240d-119">네임스페이스를 사용하여 범위 제어</span><span class="sxs-lookup"><span data-stu-id="9240d-119">Using Namespaces to control scope</span></span>  
 <span data-ttu-id="9240d-120">`namespace` 키워드는 범위를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-120">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="9240d-121">프로젝트 내에서 범위를 만드는 기능은 코드 구성에 도움이 되며, 전역적으로 고유한 형식을 만들 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-121">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="9240d-122">다음 예제에서 `SampleClass`라는 클래스는 서로 중첩된 두 개의 네임스페이스에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-122">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="9240d-123">[ 연산자](../../../csharp/language-reference/operators/member-access-operator.md)는 호출되는 메서드를 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-123">The [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) is used to differentiate which method gets called.</span></span>  
  
 <span data-ttu-id="9240d-124">[!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-124">[!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="9240d-125">정규화된 이름</span><span class="sxs-lookup"><span data-stu-id="9240d-125">Fully Qualified Names</span></span>  
 <span data-ttu-id="9240d-126">네임스페이스 및 형식에는 논리적 계층 구조를 나타내는 정규화된 이름으로 설명된 고유한 제목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-126">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="9240d-127">예를 들어 `A.B` 문은 `A`는 네임스페이스 또는 형식의 이름이고 `B`는 그 안에 중첩됨을 암시합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-127">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="9240d-128">다음 예제에서는 중첩된 클래스 및 네임스페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-128">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="9240d-129">정규화된 이름이 각 엔터티 뒤에 주석으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-129">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 <span data-ttu-id="9240d-130">[!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-130">[!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]</span></span>  
  
 <span data-ttu-id="9240d-131">앞의 코드 세그먼트에서:</span><span class="sxs-lookup"><span data-stu-id="9240d-131">In the previous code segment:</span></span>  
  
-   <span data-ttu-id="9240d-132">`N1` 네임스페이스는 전역 네임스페이스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-132">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="9240d-133">정규화된 이름은 `N1`입니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-133">Its fully qualified name is `N1`.</span></span>  
  
-   <span data-ttu-id="9240d-134">`N2` 네임스페이스는 `N1`의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-134">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="9240d-135">정규화된 이름은 `N1.N2`입니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-135">Its fully qualified name is `N1.N2`.</span></span>  
  
-   <span data-ttu-id="9240d-136">`C1` 클래스는 `N1`의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-136">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="9240d-137">정규화된 이름은 `N1.C1`입니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-137">Its fully qualified name is `N1.C1`.</span></span>  
  
-   <span data-ttu-id="9240d-138">이 코드에서는 클래스 이름 `C2`가 두 번 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-138">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="9240d-139">그러나 정규화된 이름은 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-139">However, the fully qualified names are unique.</span></span> <span data-ttu-id="9240d-140">`C2`의 첫 번째 인스턴스는 `C1` 내에서 선언되었으므로 정규화된 이름이 `N1.C1.C2`입니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-140">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="9240d-141">`C2`의 두 번째 인스턴스는 `N2` 네임스페이스 내에서 선언되었으므로 정규화된 이름이 `N1.N2.C2`입니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-141">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="9240d-142">앞의 코드 세그먼트를 사용하여 다음과 같이 `N1.N2` 네임스페이스에 새 클래스 멤버 `C3`를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-142">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 <span data-ttu-id="9240d-143">[!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-143">[!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]</span></span>  
  
 <span data-ttu-id="9240d-144">일반적으로 `::`을 사용하여 네임스페이스 별칭을 참조하거나, `global::`을 사용하여 전역 네임스페이스를 참조하고 `.`를 사용하여 형식 또는 멤버를 한정합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-144">In general, use `::` to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="9240d-145">네임스페이스 대신 형식을 참조하는 별칭과 함께 `::`을 사용하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-145">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="9240d-146">예:</span><span class="sxs-lookup"><span data-stu-id="9240d-146">For example:</span></span>  
  
 <span data-ttu-id="9240d-147">[!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-147">[!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]</span></span>  
  
 <span data-ttu-id="9240d-148">[!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-148">[!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]</span></span>  
  
 <span data-ttu-id="9240d-149">`global` 단어는 미리 정의된 별칭이 아니므로 `global.X`에 특별한 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-149">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="9240d-150">`::`과 함께 사용하는 경우에만 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-150">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="9240d-151">`global::`은 항상 별칭이 아니라 전역 네임스페이스를 참조하기 때문에 global이란 별칭을 정의할 경우 컴파일러 경고 CS0440이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-151">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="9240d-152">예를 들어 다음 줄에서는 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-152">For example, the following line generates the warning:</span></span>  
  
 <span data-ttu-id="9240d-153">[!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-153">[!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]</span></span>  
  
 <span data-ttu-id="9240d-154">별칭과 함께 `::`을 사용하는 것은 좋은 방법이며, 예기치 않은 추가 형식의 도입을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-154">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="9240d-155">예를 들어 다음 예제를 고려해보세요.</span><span class="sxs-lookup"><span data-stu-id="9240d-155">For example, consider this example:</span></span>  
  
 <span data-ttu-id="9240d-156">[!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-156">[!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]</span></span>  
  
 <span data-ttu-id="9240d-157">[!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="9240d-157">[!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]</span></span>  
  
 <span data-ttu-id="9240d-158">이 예제는 작동하지만, `Alias`라는 형식을 이후에 도입할 경우 `Alias.`가 해당 형식에 대신 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-158">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="9240d-159">`Alias::Exception`을 사용하면 `Alias`가 네임스페이스 별칭으로 처리되며 형식으로 잘못 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9240d-159">Using `Alias::Exception` insures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  
  
 <span data-ttu-id="9240d-160">`global` 별칭과 관련된 자세한 내용은 [방법: 전역 네임스페이스 별칭 사용](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9240d-160">See the topic [How to: Use the Global Namespace Alias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) for more information regarding the `global` alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9240d-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9240d-161">See Also</span></span>  
 <span data-ttu-id="9240d-162">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9240d-162">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9240d-163">[네임스페이스](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="9240d-163">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 <span data-ttu-id="9240d-164">[네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="9240d-164">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="9240d-165">[. 연산자](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="9240d-165">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 <span data-ttu-id="9240d-166">[:: 연산자](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span><span class="sxs-lookup"><span data-stu-id="9240d-166">[:: Operator](../../../csharp/language-reference/operators/namespace-alias-qualifer.md) </span></span>  
 [<span data-ttu-id="9240d-167">extern</span><span class="sxs-lookup"><span data-stu-id="9240d-167">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)

