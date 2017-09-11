---
title: "namespace(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
dev_langs:
- CSharp
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
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
ms.openlocfilehash: d2cef3949d9a41db36406db059218f7a204172ea
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="namespace-c-reference"></a><span data-ttu-id="f8a5c-102">namespace(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f8a5c-102">namespace (C# Reference)</span></span>
<span data-ttu-id="f8a5c-103">`namespace` 키워드는 관련 개체 집합을 포함하는 범위를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="f8a5c-104">네임스페이스를 사용하여 코드 요소를 구성하고 전역적으로 고유한 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 <span data-ttu-id="f8a5c-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8a5c-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8a5c-106">주의</span><span class="sxs-lookup"><span data-stu-id="f8a5c-106">Remarks</span></span>  
 <span data-ttu-id="f8a5c-107">네임스페이스 내에서 다음 형식 중 하나 이상을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-107">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="f8a5c-108">다른 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="f8a5c-108">another namespace</span></span>  
  
-   [<span data-ttu-id="f8a5c-109">class</span><span class="sxs-lookup"><span data-stu-id="f8a5c-109">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="f8a5c-110">interface</span><span class="sxs-lookup"><span data-stu-id="f8a5c-110">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="f8a5c-111">truct</span><span class="sxs-lookup"><span data-stu-id="f8a5c-111">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="f8a5c-112">enum</span><span class="sxs-lookup"><span data-stu-id="f8a5c-112">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="f8a5c-113">delegate</span><span class="sxs-lookup"><span data-stu-id="f8a5c-113">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="f8a5c-114">C# 소스 파일에서 네임스페이스를 명시적으로 선언하는지 여부에 관계없이 컴파일러는 기본 네임스페이스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="f8a5c-115">전역 네임스페이스라고도 하는 이 명명되지 않은 네임스페이스는 모든 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="f8a5c-116">전역 네임스페이스의 모든 식별자는 명명된 네임스페이스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="f8a5c-117">네임스페이스는 암시적으로 공용 액세스를 사용하며 이 설정은 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="f8a5c-118">네임스페이스의 요소에 할당할 수 있는 액세스 한정자에 대한 설명은 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="f8a5c-119">둘 이상의 선언에서 네임스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="f8a5c-120">예를 들어 다음 예제에서는 `MyCompany` 네임스페이스의 일부로 두 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 <span data-ttu-id="f8a5c-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8a5c-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8a5c-122">예제</span><span class="sxs-lookup"><span data-stu-id="f8a5c-122">Example</span></span>  
 <span data-ttu-id="f8a5c-123">다음 예제에서는 중첩된 네임스페이스에서 정적 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-123">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 <span data-ttu-id="f8a5c-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8a5c-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="f8a5c-125">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="f8a5c-125">For More Information</span></span>  
 <span data-ttu-id="f8a5c-126">네임스페이스를 사용하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8a5c-126">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="f8a5c-127">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="f8a5c-127">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="f8a5c-128">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="f8a5c-128">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="f8a5c-129">방법: 전역 네임스페이스 별칭 사용</span><span class="sxs-lookup"><span data-stu-id="f8a5c-129">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f8a5c-130">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f8a5c-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8a5c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8a5c-131">See Also</span></span>  
 <span data-ttu-id="f8a5c-132">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8a5c-132">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f8a5c-133">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8a5c-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f8a5c-134">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f8a5c-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f8a5c-135">[네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="f8a5c-135">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 [<span data-ttu-id="f8a5c-136">using</span><span class="sxs-lookup"><span data-stu-id="f8a5c-136">using</span></span>](../../../csharp/language-reference/keywords/using.md)

