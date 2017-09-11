---
title: "입니다. 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ._CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: 21
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
ms.openlocfilehash: fdc7c1821548509f3a3750aef2836c034f7aa53b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="b65fb-103">입니다.</span><span class="sxs-lookup"><span data-stu-id="b65fb-103">.</span></span> <span data-ttu-id="b65fb-104">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b65fb-104">Operator (C# Reference)</span></span>
<span data-ttu-id="b65fb-105">점 연산자(`.`)는 멤버 액세스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b65fb-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="b65fb-106">점 연산자는 형식 또는 네임스페이스의 멤버를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b65fb-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="b65fb-107">예를 들어 점 연산자는 .NET Framework 클래스 라이브러리 내의 특정 메서드에 액세스하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b65fb-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 <span data-ttu-id="b65fb-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b65fb-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="b65fb-109">예를 들어 다음 클래스를 예로 들어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b65fb-109">For example, consider the following class:</span></span>  
  
 <span data-ttu-id="b65fb-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b65fb-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="b65fb-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b65fb-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="b65fb-112">`s` 변수에는 두 개의 멤버 `a`와 `b`가 있으며, 액세스하려면 점 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b65fb-112">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 <span data-ttu-id="b65fb-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="b65fb-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="b65fb-114">예를 들어 점은 속하는 네임스페이스 또는 인터페이스를 지정하는 이름인 정규화된 이름을 형성하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b65fb-114">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 <span data-ttu-id="b65fb-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="b65fb-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="b65fb-116">using 지시문을 사용하면 일부 이름 한정이 선택 사항이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b65fb-116">The using directive makes some name qualification optional:</span></span>  
  
 <span data-ttu-id="b65fb-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="b65fb-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span></span>  
  
 <span data-ttu-id="b65fb-118">하지만 식별자가 모호한 경우 정규화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b65fb-118">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 <span data-ttu-id="b65fb-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="b65fb-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b65fb-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b65fb-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b65fb-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b65fb-121">See Also</span></span>  
 <span data-ttu-id="b65fb-122">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b65fb-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b65fb-123">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b65fb-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b65fb-124">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="b65fb-124">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

