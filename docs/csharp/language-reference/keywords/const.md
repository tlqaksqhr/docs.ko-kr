---
title: "const(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f54b686b170622ca1ead736a9f614c9bbef52dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="const-c-reference"></a><span data-ttu-id="4b81f-102">const(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4b81f-102">const (C# Reference)</span></span>
<span data-ttu-id="4b81f-103">상수 필드 또는 지역 상수를 선언할 때는 `const` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="4b81f-104">상수 필드 및 지역 상수는 변수가 아니며 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="4b81f-105">상수는 숫자, 부울 값, 문자열 또는 null 참조일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="4b81f-106">언제든지 변경될 수 있는 정보를 나타낼 때는 상수를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4b81f-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="4b81f-107">예를 들어, 상수 필드를 사용하여 서비스의 가격, 제품 버전 번호 또는 회사의 브랜드 이름을 저장하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4b81f-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="4b81f-108">이러한 값은 시간이 지남에 따라 변경될 수 있으며, 컴파일러는 상수를 전파하므로 변경 내용을 보기 위해서는 라이브러리를 사용하여 컴파일된 다른 코드를 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="4b81f-109">[readonly](../../../csharp/language-reference/keywords/readonly.md) 키워드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b81f-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="4b81f-110">예:</span><span class="sxs-lookup"><span data-stu-id="4b81f-110">For example:</span></span>  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a><span data-ttu-id="4b81f-111">주의</span><span class="sxs-lookup"><span data-stu-id="4b81f-111">Remarks</span></span>  
 <span data-ttu-id="4b81f-112">상수 선언 형식은 선언에서 제공하는 멤버의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="4b81f-113">지역 상수 또는 상수 필드의 이니셜라이저는 대상 형식으로 암시적으로 변환될 수 있는 상수 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>  
  
 <span data-ttu-id="4b81f-114">상수 식은 컴파일 시간에 완전히 계산될 수 있는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="4b81f-115">따라서 참조 형식의 상수에 대해 가능한 값은 `string` 및 null 참조뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>  
  
 <span data-ttu-id="4b81f-116">상수 선언에서는 다음과 같이 여러 상수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-116">The constant declaration can declare multiple constants, such as:</span></span>  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 <span data-ttu-id="4b81f-117">`static` 한정자는 상수 선언에는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-117">The `static` modifier is not allowed in a constant declaration.</span></span>  
  
 <span data-ttu-id="4b81f-118">상수는 다음과 같이 상수 식에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-118">A constant can participate in a constant expression, as follows:</span></span>  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  <span data-ttu-id="4b81f-119">[readonly](../../../csharp/language-reference/keywords/readonly.md) 키워드는 `const` 키워드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="4b81f-120">`const` 필드는 필드 선언에서만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="4b81f-121">`readonly` 필드는 선언이나 생성자에서 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="4b81f-122">따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="4b81f-123">또한 `const` 필드가 컴파일 시간 상수라고 하더라도 `readonly` 필드는 다음 줄에서와 같이 런타임 상수에 사용될 수 있습니다. `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="4b81f-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b81f-124">예제</span><span class="sxs-lookup"><span data-stu-id="4b81f-124">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="4b81f-125">예제</span><span class="sxs-lookup"><span data-stu-id="4b81f-125">Example</span></span>  
 <span data-ttu-id="4b81f-126">이 예제에서는 상수를 지역 변수로 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b81f-126">This example demonstrates how to use constants as local variables.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="4b81f-127">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4b81f-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4b81f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b81f-128">See Also</span></span>  
 [<span data-ttu-id="4b81f-129">C# 참조</span><span class="sxs-lookup"><span data-stu-id="4b81f-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4b81f-130">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4b81f-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4b81f-131">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="4b81f-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4b81f-132">한정자</span><span class="sxs-lookup"><span data-stu-id="4b81f-132">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="4b81f-133">readonly</span><span class="sxs-lookup"><span data-stu-id="4b81f-133">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)
