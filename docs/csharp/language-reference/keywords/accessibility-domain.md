---
title: 액세스 가능 도메인(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 8e6af35ea41f6d062bc2b8ee771a1fac21667462
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207975"
---
# <a name="accessibility-domain-c-reference"></a><span data-ttu-id="4201f-102">액세스 가능 도메인(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4201f-102">Accessibility Domain (C# Reference)</span></span>
<span data-ttu-id="4201f-103">멤버의 액세스 가능 도메인은 멤버가 참조될 수 있는 프로그램 섹션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-103">The accessibility domain of a member specifies in which program sections a member can be referenced.</span></span> <span data-ttu-id="4201f-104">멤버가 다른 형식 내에 중첩되면 해당 액세스 가능 도메인은 멤버의 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) 및 한 수준 위 형식의 액세스 가능 도메인에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-104">If the member is nested within another type, its accessibility domain is determined by both the [accessibility level](../../../csharp/language-reference/keywords/accessibility-levels.md) of the member and the accessibility domain of the immediately containing type.</span></span>  
  
 <span data-ttu-id="4201f-105">최상위 형식의 액세스 가능 도메인은 최소한 최상위 형식이 선언된 프로젝트의 프로그램 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-105">The accessibility domain of a top-level type is at least the program text of the project that it is declared in.</span></span> <span data-ttu-id="4201f-106">즉, 도메인에는 이 프로젝트의 모든 소스 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-106">That is, the domain includes all of the source files of this project.</span></span> <span data-ttu-id="4201f-107">중첩 형식의 액세스 가능 도메인은 최소한 중첩 형식이 선언된 프로젝트의 프로그램 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-107">The accessibility domain of a nested type is at least the program text of the type in which it is declared.</span></span> <span data-ttu-id="4201f-108">즉, 도메인은 모든 중첩 형식이 포함된 형식 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-108">That is, the domain is the type body, which includes all nested types.</span></span> <span data-ttu-id="4201f-109">중첩 형식의 액세스 가능 도메인은 포함하는 형식의 액세스 가능 도메인을 초과하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-109">The accessibility domain of a nested type never exceeds that of the containing type.</span></span> <span data-ttu-id="4201f-110">다음 예제에서는 이러한 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-110">These concepts are demonstrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4201f-111">예</span><span class="sxs-lookup"><span data-stu-id="4201f-111">Example</span></span>  
 <span data-ttu-id="4201f-112">이 예제에는 최상위 형식 `T1`과 두 개의 중첩 클래스 `M1` 및 `M2`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-112">This example contains a top-level type, `T1`, and two nested classes, `M1` and `M2`.</span></span> <span data-ttu-id="4201f-113">클래스에는 여러 가지 선언된 액세스 가능성을 가진 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-113">The classes contain fields that have different declared accessibilities.</span></span> <span data-ttu-id="4201f-114">`Main` 메서드에서 각 문 뒤에는 각 멤버의 액세스 가능성 도메인을 나타내는 주석이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-114">In the `Main` method, a comment follows each statement to indicate the accessibility domain of each member.</span></span> <span data-ttu-id="4201f-115">액세스할 수 없는 멤버를 참조하려고 하는 문은 주석으로 처리됩니다. 액세스할 수 없는 멤버를 참조함으로써 발생한 컴파일러 오류를 확인하려면 한 번에 하나씩 주석을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4201f-115">Notice that the statements that try to reference the inaccessible members are commented out. If you want to see the compiler errors caused by referencing an inaccessible member, remove the comments one at a time.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a><span data-ttu-id="4201f-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4201f-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4201f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4201f-117">See Also</span></span>  
 [<span data-ttu-id="4201f-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="4201f-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4201f-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4201f-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4201f-120">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="4201f-120">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4201f-121">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="4201f-121">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="4201f-122">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="4201f-122">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="4201f-123">접근성 수준 사용에 대한 제한</span><span class="sxs-lookup"><span data-stu-id="4201f-123">Restrictions on Using Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [<span data-ttu-id="4201f-124">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="4201f-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="4201f-125">public</span><span class="sxs-lookup"><span data-stu-id="4201f-125">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="4201f-126">private</span><span class="sxs-lookup"><span data-stu-id="4201f-126">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="4201f-127">protected</span><span class="sxs-lookup"><span data-stu-id="4201f-127">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="4201f-128">internal</span><span class="sxs-lookup"><span data-stu-id="4201f-128">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
