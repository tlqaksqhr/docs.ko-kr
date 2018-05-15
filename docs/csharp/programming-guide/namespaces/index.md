---
title: 네임스페이스(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 60e4c6e98ca9e71d1a095a0c7ee1df6be6d13f4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="namespaces-c-programming-guide"></a><span data-ttu-id="141a0-102">네임스페이스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="141a0-102">Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="141a0-103">네임스페이스는 C# 프로그래밍에서 두 가지 방법으로 많이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-103">Namespaces are heavily used in C# programming in two ways.</span></span> <span data-ttu-id="141a0-104">첫째, .NET Framework는 네임스페이스를 사용하여 다음과 같이 많은 클래스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-104">First, the .NET Framework uses namespaces to organize its many classes, as follows:</span></span>  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 <span data-ttu-id="141a0-105">`System`은 네임스페이스이고 `Console`은 해당 네임스페이스의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-105">`System` is a namespace and `Console` is a class in that namespace.</span></span> <span data-ttu-id="141a0-106">전체 키워드가 필요하지 않으므로 다음 예처럼 `using` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-106">The `using` keyword can be used so that the complete name is not required, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 <span data-ttu-id="141a0-107">자세한 내용은 [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="141a0-107">For more information, see [using Directive](../../../csharp/language-reference/keywords/using-directive.md).</span></span>  
  
 <span data-ttu-id="141a0-108">둘째, 고유한 네임스페이스를 선언하면 대규모 프로그래밍 프로젝트에서 클래스 및 메서드 이름의 범위를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-108">Second, declaring your own namespaces can help you control the scope of class and method names in larger programming projects.</span></span> <span data-ttu-id="141a0-109">다음 예와 같이 [네임스페이스](../../../csharp/language-reference/keywords/namespace.md) 키워드를 사용하여 네임스페이스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-109">Use the [namespace](../../../csharp/language-reference/keywords/namespace.md) keyword to declare a namespace, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a><span data-ttu-id="141a0-110">네임스페이스 개요</span><span class="sxs-lookup"><span data-stu-id="141a0-110">Namespaces Overview</span></span>  
 <span data-ttu-id="141a0-111">네임스페이스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-111">Namespaces have the following properties:</span></span>  
  
-   <span data-ttu-id="141a0-112">대규모 코드 프로젝트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-112">They organize large code projects.</span></span>  
  
-   <span data-ttu-id="141a0-113">`.` 연산자를 사용하여 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-113">They are delimited by using the `.` operator.</span></span>  
  
-   <span data-ttu-id="141a0-114">`using directive`는 모든 클래스에 대해 네임스페이스의 이름을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-114">The `using directive` obviates the requirement to specify the name of the namespace for every class.</span></span>  
  
-   <span data-ttu-id="141a0-115">`global` 네임스페이스는 "루트" 네임스페이스입니다. `global::System`은 항상 .NET Framework 네임스페이스 `System`을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="141a0-115">The `global` namespace is the "root" namespace: `global::System` will always refer to the .NET Framework namespace `System`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="141a0-116">관련 단원</span><span class="sxs-lookup"><span data-stu-id="141a0-116">Related Sections</span></span>  
 <span data-ttu-id="141a0-117">네임스페이스에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="141a0-117">See the following topics for more information about namespaces:</span></span>  
  
-   [<span data-ttu-id="141a0-118">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="141a0-118">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="141a0-119">방법: 전역 네임스페이스 별칭 사용</span><span class="sxs-lookup"><span data-stu-id="141a0-119">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [<span data-ttu-id="141a0-120">방법: My 네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="141a0-120">How to: Use the My Namespace</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="141a0-121">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="141a0-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="141a0-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="141a0-122">See Also</span></span>  
 [<span data-ttu-id="141a0-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="141a0-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="141a0-124">네임스페이스 키워드</span><span class="sxs-lookup"><span data-stu-id="141a0-124">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="141a0-125">using 지시문</span><span class="sxs-lookup"><span data-stu-id="141a0-125">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="141a0-126">:: 연산자</span><span class="sxs-lookup"><span data-stu-id="141a0-126">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [<span data-ttu-id="141a0-127">. 연산자</span><span class="sxs-lookup"><span data-stu-id="141a0-127">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)
