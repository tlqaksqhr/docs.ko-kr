---
title: "방법: 문자열 비교(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: 23
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
ms.openlocfilehash: 494b9ef1a1e6c8958dd3df2edb44debf32690eeb
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-compare-strings-c-programming-guide"></a><span data-ttu-id="a99e0-102">방법: 문자열 비교(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a99e0-102">How to: Compare Strings (C# Programming Guide)</span></span>
<span data-ttu-id="a99e0-103">문자열을 비교하면 한 문자열이 다른 문자열보다 크거나 작은지 또는 두 문자열이 같은지 나타내는 결과가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-103">When you compare strings, you are producing a result that says one string is greater than or less than the other, or that the two strings are equal.</span></span> <span data-ttu-id="a99e0-104">결과를 결정하는 규칙은 *서수 비교* 또는 *문화권 구분 비교*를 수행하는지에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-104">The rules by which the result is determined are different depending on whether you are performing *ordinal comparison* or *culture-sensitive comparison*.</span></span> <span data-ttu-id="a99e0-105">특정 작업에 올바른 유형의 비교를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-105">It is important to use the correct kind of comparison for the specific task.</span></span>  
  
 <span data-ttu-id="a99e0-106">언어 규칙에 관계없이 두 문자열의 값을 비교하거나 정렬해야 할 경우 기본 서수 비교를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-106">Use basic ordinal comparisons when you have to compare or sort the values of two strings without regard to linguistic conventions.</span></span> <span data-ttu-id="a99e0-107">기본 서수 비교(`System.StringComparison.Ordinal`)는 대/소문자를 구분합니다. 즉, 두 문자열이 문자별로 일치해야 합니다. "and"는 "And" 또는 "AND"와 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-107">A basic ordinal comparison (`System.StringComparison.Ordinal`) is case-sensitive, which means that the two strings must match character for character: "and" does not equal "And" or "AND".</span></span> <span data-ttu-id="a99e0-108">자주 사용되는 변형인 `System.StringComparison.OrdinalIgnoreCase`의 경우 "and", "And" 및 "AND"가 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-108">A frequently-used variation is `System.StringComparison.OrdinalIgnoreCase`, which will match "and", "And", and "AND".</span></span> <span data-ttu-id="a99e0-109">`StringComparison.OrdinalIgnoreCase`는 주로 파일 이름, 경로 이름, 네트워크 경로 및 사용자 컴퓨터의 로캘에 따라 값이 변경되지 않는 기타 문자열을 비교하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-109">`StringComparison.OrdinalIgnoreCase` is often used to compare file names, path names, network paths, and any other string whose value does not change based on the locale of the user's computer.</span></span> <span data-ttu-id="a99e0-110">자세한 내용은 <xref:System.StringComparison?displayProperty=fullName>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a99e0-110">For more information, see <xref:System.StringComparison?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="a99e0-111">문화권 구분 비교는 대개 최종 사용자가 입력한 문자열을 비교 및 정렬하는 데 사용됩니다. 이러한 문자열의 문자 및 정렬 규칙이 사용자 컴퓨터의 로캘에 따라 달라질 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-111">Culture-sensitive comparisons are typically used to compare and sort strings that are input by end users, because the characters and sorting conventions of these strings might vary depending on the locale of the user's computer.</span></span> <span data-ttu-id="a99e0-112">똑같은 문자가 포함된 문자열이라도 현재 스레드의 문화권에 따라 다르게 정렬될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-112">Even strings that contain identical characters might sort differently depending on the culture of the current thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a99e0-113">문자열을 비교할 때 어떤 유형의 비교를 수행할지 명시적으로 지정하는 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-113">When you compare strings, you should use the methods that explicitly specify what kind of comparison you intend to perform.</span></span> <span data-ttu-id="a99e0-114">이렇게 하면 코드를 훨씬 더 쉽게 유지 관리하고 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-114">This makes your code much more maintainable and readable.</span></span> <span data-ttu-id="a99e0-115">가능하면 <xref:System.StringComparison> 열거형 매개 변수를 사용하는 <xref:System.String?displayProperty=fullName> 및 <xref:System.Array?displayProperty=fullName> 클래스의 메서드에 대한 오버로드를 사용하여 수행할 비교 유형을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-115">Whenever possible, use the overloads of the methods of the <xref:System.String?displayProperty=fullName> and <xref:System.Array?displayProperty=fullName> classes that take a <xref:System.StringComparison> enumeration parameter, so that you can specify which type of comparison to perform.</span></span> <span data-ttu-id="a99e0-116">문자열을 비교할 때 `==` 및 `!=` 연산자를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-116">It is best to avoid using the `==` and `!=` operators when you compare strings.</span></span> <span data-ttu-id="a99e0-117">또한 오버로드는 <xref:System.StringComparison>을 사용하지 않으므로 <xref:System.String.CompareTo%2A?displayProperty=fullName> 인스턴스 메서드를 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-117">Also, avoid using the <xref:System.String.CompareTo%2A?displayProperty=fullName> instance methods because none of the overloads takes a <xref:System.StringComparison>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a99e0-118">예제</span><span class="sxs-lookup"><span data-stu-id="a99e0-118">Example</span></span>  
 <span data-ttu-id="a99e0-119">다음 예제에서는 사용자 컴퓨터의 로캘에 따라 값이 변경되지 않는 문자열을 정확히 비교하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-119">The following example shows how to correctly compare strings whose values will not change based on the locale of the user's computer.</span></span> <span data-ttu-id="a99e0-120">또한 C#의 *문자열 인터닝* 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-120">In addition, it also demonstrates the *string interning* feature of C#.</span></span> <span data-ttu-id="a99e0-121">프로그램이 두 개 이상의 동일 문자열 변수를 선언할 경우 컴파일러는 변수를 모두 같은 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-121">When a program declares two or more identical string variables, the compiler stores them all in the same location.</span></span> <span data-ttu-id="a99e0-122"><xref:System.Object.ReferenceEquals%2A> 메서드를 호출하여 두 문자열이 실제로 메모리에서 같은 개체를 참조하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-122">By calling the <xref:System.Object.ReferenceEquals%2A> method, you can see that the two strings actually refer to the same object in memory.</span></span> <span data-ttu-id="a99e0-123">예제와 같이 <xref:System.String.Copy%2A?displayProperty=fullName> 메서드를 사용하여 인터닝을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-123">Use the <xref:System.String.Copy%2A?displayProperty=fullName> method to avoid interning, as shown in the example.</span></span>  
  
 <span data-ttu-id="a99e0-124">[!code-cs[csProgGuideStrings#11](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a99e0-124">[!code-cs[csProgGuideStrings#11](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a99e0-125">예제</span><span class="sxs-lookup"><span data-stu-id="a99e0-125">Example</span></span>  
 <span data-ttu-id="a99e0-126">다음 예제에서는 <xref:System.StringComparison> 열거형을 사용하는 <xref:System.String?displayProperty=fullName> 메서드를 통해 원하는 방식으로 문자열을 비교하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-126">The following example shows how to compare strings the preferred way by using the <xref:System.String?displayProperty=fullName> methods that take a <xref:System.StringComparison> enumeration.</span></span> <span data-ttu-id="a99e0-127">또한 오버로드는 <xref:System.StringComparison>을 사용하지 않으므로 <xref:System.String.CompareTo%2A?displayProperty=fullName> 인스턴스 메서드는 여기서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-127">Note that the <xref:System.String.CompareTo%2A?displayProperty=fullName> instance methods are not used here, because none of the overloads takes a <xref:System.StringComparison>.</span></span>  
  
 <span data-ttu-id="a99e0-128">[!code-cs[csProgGuideStrings#31](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a99e0-128">[!code-cs[csProgGuideStrings#31](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a99e0-129">예제</span><span class="sxs-lookup"><span data-stu-id="a99e0-129">Example</span></span>  
 <span data-ttu-id="a99e0-130">다음 예제에서는 <xref:System.StringComparer?displayProperty=fullName> 매개 변수를 사용하는 정적 <xref:System.Array> 메서드를 통해 문화권 구분 방식으로 배열에서 문자열을 정렬 및 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-130">The following example shows how to sort and search for strings in an array in a culture-sensitive manner by using the static <xref:System.Array> methods that take a <xref:System.StringComparer?displayProperty=fullName> parameter.</span></span>  
  
 <span data-ttu-id="a99e0-131">[!code-cs[csProgGuideStrings#32](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a99e0-131">[!code-cs[csProgGuideStrings#32](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-compare-strings_3.cs)]</span></span>  
  
 <span data-ttu-id="a99e0-132"><xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>, <xref:System.Collections.Generic.List%601?displayProperty=fullName> 등의 컬렉션 클래스는 요소 또는 키의 형식이 `string`인 경우 <xref:System.StringComparer?displayProperty=fullName> 매개 변수를 사용하는 생성자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-132">Collection classes such as <xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>, and <xref:System.Collections.Generic.List%601?displayProperty=fullName> have constructors that take a <xref:System.StringComparer?displayProperty=fullName> parameter when the type of the elements or keys is `string`.</span></span> <span data-ttu-id="a99e0-133">일반적으로 가능하면 이러한 생성자를 사용하고 `Ordinal` 또는 `OrdinalIgnoreCase`를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a99e0-133">In general, you should use these constructors whenever possible, and specify either `Ordinal` or `OrdinalIgnoreCase`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a99e0-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a99e0-134">See Also</span></span>  
 <span data-ttu-id="a99e0-135"><xref:System.Globalization.CultureInfo?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a99e0-135"><xref:System.Globalization.CultureInfo?displayProperty=fullName></span></span>   
 <span data-ttu-id="a99e0-136"><xref:System.StringComparer?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a99e0-136"><xref:System.StringComparer?displayProperty=fullName></span></span>   
 <span data-ttu-id="a99e0-137">[문자열](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="a99e0-137">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="a99e0-138">[문자열 비교](../../../standard/base-types/comparing.md) </span><span class="sxs-lookup"><span data-stu-id="a99e0-138">[Comparing Strings](../../../standard/base-types/comparing.md) </span></span>  
 [<span data-ttu-id="a99e0-139">응용 프로그램 전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="a99e0-139">Globalizing and Localizing Applications</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)

