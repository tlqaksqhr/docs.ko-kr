---
title: extern alias(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: a2803d09ee64af854cad352f6a158fb84bb6d410
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33217391"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="31827-102">extern alias(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="31827-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="31827-103">정규화된 형식 이름이 동일한 어셈블리의 두 버전을 참조해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31827-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="31827-104">예를 들어 동일한 응용 프로그램에서 어셈블리 버전을 두 개 이상 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31827-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="31827-105">외부 어셈블리 별칭을 사용하면 각 어셈블리의 네임스페이스를 별칭으로 명명된 루트 수준 네임스페이스 내에서 래핑하여 동일한 파일에서 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31827-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31827-106">[extern](../../../csharp/language-reference/keywords/extern.md) 키워드는 메서드 한정자로도 사용되어 비관리 코드로 작성된 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="31827-106">The [extern](../../../csharp/language-reference/keywords/extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="31827-107">정규화된 형식 이름이 동일한 두 어셈블리를 참조하려면 다음과 같이 명령 프롬프트에서 별칭을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31827-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="31827-108">그러면 외부 별칭 `GridV1` 및 `GridV2`가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="31827-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="31827-109">프로그램 내에서 이러한 별칭을 사용하려면 `extern` 키워드를 사용하여 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="31827-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="31827-110">예:</span><span class="sxs-lookup"><span data-stu-id="31827-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="31827-111">각 extern alias 선언에서는 전역 네임스페이스와 병렬이지만 전역 네임스페이스 내에 있지 않는 추가 루트 수준 네임스페이스를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="31827-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="31827-112">따라서 각 어셈블리의 형식은 적절한 namespace-alias에서 시작되는 정규화된 이름을 사용하여 명확하게 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31827-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="31827-113">이전 예제에서 `GridV1::Grid`는 `grid.dll`의 표 컨트롤이 되고 `GridV2::Grid`는 `grid20.dll`의 표 컨트롤이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31827-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="31827-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="31827-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="31827-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31827-115">See Also</span></span>  
 [<span data-ttu-id="31827-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="31827-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="31827-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="31827-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="31827-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="31827-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="31827-119">네임스페이스 키워드</span><span class="sxs-lookup"><span data-stu-id="31827-119">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="31827-120">:: 연산자</span><span class="sxs-lookup"><span data-stu-id="31827-120">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [<span data-ttu-id="31827-121">/reference(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="31827-121">/reference (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
