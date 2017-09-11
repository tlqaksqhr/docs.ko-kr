---
title: "delegate(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
dev_langs:
- CSharp
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
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
ms.openlocfilehash: 402eedd0c59b5c95e1a9b44faca66ccb4d4e04e7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="delegate-c-reference"></a><span data-ttu-id="4c736-102">delegate(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4c736-102">delegate (C# Reference)</span></span>
<span data-ttu-id="4c736-103">delegate 형식의 선언은 메서드 시그니처와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4c736-103">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="4c736-104">반환 값이 있으며 모든 형식의 매개 변수를 개수에 관계없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c736-104">It has a return value and any number of parameters of any type:</span></span>  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 <span data-ttu-id="4c736-105">`delegate`는 명명된 메서드나 무명 메서드를 캡슐화하는 데 사용할 수 있는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4c736-105">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="4c736-106">대리자는 C++의 함수 포인터와 비슷하지만 형식 안전성과 보안성을 제공한다는 점이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4c736-106">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="4c736-107">대리자 적용에 대해서는 [대리자](../../../csharp/programming-guide/delegates/index.md) 및 [제네릭 대리자](../../../csharp/programming-guide/generics/generic-delegates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c736-107">For applications of delegates, see [Delegates](../../../csharp/programming-guide/delegates/index.md) and [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c736-108">주의</span><span class="sxs-lookup"><span data-stu-id="4c736-108">Remarks</span></span>  
 <span data-ttu-id="4c736-109">대리자는 [이벤트](../../../csharp/programming-guide/events/index.md)의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c736-109">Delegates are the basis for [Events](../../../csharp/programming-guide/events/index.md).</span></span>  
  
 <span data-ttu-id="4c736-110">대리자는 명명된 메서드나 무명 메서드와 연결하여 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c736-110">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span> <span data-ttu-id="4c736-111">자세한 내용은 [명명된 메서드](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) 및 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c736-111">For more information, see [Named Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) and [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
 <span data-ttu-id="4c736-112">대리자는 호환되는 반환 형식 및 입력 매개 변수가 있는 메서드나 람다 식을 사용하여 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c736-112">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="4c736-113">메서드 시그니처에서 허용되는 가변성 수준에 대한 자세한 내용은 [대리자의 가변성](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c736-113">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca).</span></span> <span data-ttu-id="4c736-114">무명 메서드에서 사용하기 위해 메서드에 연결할 대리자와 코드를 함께 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4c736-114">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> <span data-ttu-id="4c736-115">대리자를 인스턴스화하는 두 가지 방법은 이 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c736-115">Both ways of instantiating delegates are discussed in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c736-116">예제</span><span class="sxs-lookup"><span data-stu-id="4c736-116">Example</span></span>  
 <span data-ttu-id="4c736-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4c736-117">[!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4c736-118">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4c736-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4c736-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c736-119">See Also</span></span>  
 <span data-ttu-id="4c736-120">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c736-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4c736-121">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c736-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4c736-122">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c736-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4c736-123">[참조 형식](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="4c736-123">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="4c736-124">[대리자](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c736-124">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="4c736-125">[이벤트](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="4c736-125">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="4c736-126">[명명된 메서드 및 무명 메서드의 대리자 비교](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span><span class="sxs-lookup"><span data-stu-id="4c736-126">[Delegates with Named vs. Anonymous Methods](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) </span></span>  
 [<span data-ttu-id="4c736-127">무명 메서드</span><span class="sxs-lookup"><span data-stu-id="4c736-127">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)

