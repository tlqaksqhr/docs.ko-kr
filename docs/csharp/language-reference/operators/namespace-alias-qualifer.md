---
title: ":: 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ::_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
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
ms.openlocfilehash: 97b9fa706669244ac579602a107c092e8593567d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="a8aad-102">:: 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a8aad-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="a8aad-103">네임스페이스 별칭 한정자(`::`)는 식별자를 조회하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="a8aad-104">다음 예제와 같이 항상 두 식별자 사이에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 <span data-ttu-id="a8aad-105">[!code-cs[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8aad-105">[!code-cs[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8aad-106">설명</span><span class="sxs-lookup"><span data-stu-id="a8aad-106">Remarks</span></span>  
 <span data-ttu-id="a8aad-107">네임스페이스 별칭 한정자는 `global`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="a8aad-108">별칭이 지정된 네임스페이스가 아니라 전역 네임스페이스에서 조회를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a8aad-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="a8aad-109">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="a8aad-109">For More Information</span></span>  
 <span data-ttu-id="a8aad-110">`::` 연산자를 사용하는 방법의 예는 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8aad-110">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="a8aad-111">방법: 전역 네임스페이스 별칭 사용</span><span class="sxs-lookup"><span data-stu-id="a8aad-111">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="a8aad-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a8aad-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a8aad-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8aad-113">See Also</span></span>  
 <span data-ttu-id="a8aad-114">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8aad-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a8aad-115">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8aad-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a8aad-116">[C# 연산자](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8aad-116">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="a8aad-117">[네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="a8aad-117">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="a8aad-118">[. 연산자](../../../csharp/language-reference/operators/member-access-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a8aad-118">[. Operator](../../../csharp/language-reference/operators/member-access-operator.md) </span></span>  
 [<span data-ttu-id="a8aad-119">extern alias</span><span class="sxs-lookup"><span data-stu-id="a8aad-119">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)

