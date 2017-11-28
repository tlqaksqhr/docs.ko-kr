---
title: "namespace(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76cc1adc21f6cfadc93da58250336705e43e333a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-c-reference"></a><span data-ttu-id="7b1ab-102">namespace(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="7b1ab-102">namespace (C# Reference)</span></span>
<span data-ttu-id="7b1ab-103">`namespace` 키워드는 관련 개체 집합을 포함하는 범위를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="7b1ab-104">네임스페이스를 사용하여 코드 요소를 구성하고 전역적으로 고유한 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="7b1ab-105">설명</span><span class="sxs-lookup"><span data-stu-id="7b1ab-105">Remarks</span></span>  
 <span data-ttu-id="7b1ab-106">네임스페이스 내에서 다음 형식 중 하나 이상을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-106">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="7b1ab-107">다른 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7b1ab-107">another namespace</span></span>  
  
-   [<span data-ttu-id="7b1ab-108">class</span><span class="sxs-lookup"><span data-stu-id="7b1ab-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="7b1ab-109">interface</span><span class="sxs-lookup"><span data-stu-id="7b1ab-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="7b1ab-110">truct</span><span class="sxs-lookup"><span data-stu-id="7b1ab-110">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="7b1ab-111">enum</span><span class="sxs-lookup"><span data-stu-id="7b1ab-111">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="7b1ab-112">delegate</span><span class="sxs-lookup"><span data-stu-id="7b1ab-112">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="7b1ab-113">C# 소스 파일에서 네임스페이스를 명시적으로 선언하는지 여부에 관계없이 컴파일러는 기본 네임스페이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="7b1ab-114">전역 네임스페이스라고도 하는 이 명명되지 않은 네임스페이스는 모든 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="7b1ab-115">전역 네임스페이스의 모든 식별자는 명명된 네임스페이스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="7b1ab-116">네임스페이스는 암시적으로 공용 액세스를 사용하며 이 설정은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="7b1ab-117">네임스페이스의 요소에 할당할 수 있는 액세스 한정자에 대한 설명은 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="7b1ab-118">둘 이상의 선언에서 네임스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="7b1ab-119">예를 들어 다음 예제에서는 `MyCompany` 네임스페이스의 일부로 두 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="7b1ab-120">예제</span><span class="sxs-lookup"><span data-stu-id="7b1ab-120">Example</span></span>  
 <span data-ttu-id="7b1ab-121">다음 예제에서는 중첩된 네임스페이스에서 정적 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-121">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]  
  
## <a name="for-more-information"></a><span data-ttu-id="7b1ab-122">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="7b1ab-122">For More Information</span></span>  
 <span data-ttu-id="7b1ab-123">네임스페이스를 사용하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b1ab-123">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="7b1ab-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7b1ab-124">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="7b1ab-125">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="7b1ab-125">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="7b1ab-126">방법: 전역 네임스페이스 별칭 사용</span><span class="sxs-lookup"><span data-stu-id="7b1ab-126">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="7b1ab-127">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="7b1ab-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b1ab-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b1ab-128">See Also</span></span>  
 [<span data-ttu-id="7b1ab-129">C# 참조</span><span class="sxs-lookup"><span data-stu-id="7b1ab-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7b1ab-130">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7b1ab-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7b1ab-131">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="7b1ab-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7b1ab-132">네임스페이스 키워드</span><span class="sxs-lookup"><span data-stu-id="7b1ab-132">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="7b1ab-133">using</span><span class="sxs-lookup"><span data-stu-id="7b1ab-133">using</span></span>](../../../csharp/language-reference/keywords/using.md)
