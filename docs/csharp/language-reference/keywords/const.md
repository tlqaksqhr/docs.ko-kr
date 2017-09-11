---
title: "const(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- const_CSharpKeyword
- const
dev_langs:
- CSharp
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
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
ms.openlocfilehash: b8f6d567deed513ff5693fe39bd21c8607677402
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="const-c-reference"></a><span data-ttu-id="4f7ef-102">const(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4f7ef-102">const (C# Reference)</span></span>
<span data-ttu-id="4f7ef-103">상수 필드 또는 지역 상수를 선언할 때는 `const` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="4f7ef-104">상수 필드 및 지역 상수는 변수가 아니며 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="4f7ef-105">상수는 숫자, 부울 값, 문자열 또는 null 참조일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="4f7ef-106">언제든지 변경될 수 있는 정보를 나타낼 때는 상수를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="4f7ef-107">예를 들어, 상수 필드를 사용하여 서비스의 가격, 제품 버전 번호 또는 회사의 브랜드 이름을 저장하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="4f7ef-108">이러한 값은 시간이 지남에 따라 변경될 수 있으며, 컴파일러는 상수를 전파하므로 변경 내용을 보기 위해서는 라이브러리를 사용하여 컴파일된 다른 코드를 다시 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="4f7ef-109">[readonly](../../../csharp/language-reference/keywords/readonly.md) 키워드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="4f7ef-110">예:</span><span class="sxs-lookup"><span data-stu-id="4f7ef-110">For example:</span></span>  
  
```csharp
const int x = 0;  
public const double gravitationalConstant = 6.673e-11;  
private const string productName = "Visual C#";  
```  
  
## <a name="remarks"></a><span data-ttu-id="4f7ef-111">주의</span><span class="sxs-lookup"><span data-stu-id="4f7ef-111">Remarks</span></span>  
 <span data-ttu-id="4f7ef-112">상수 선언 형식은 선언에서 제공하는 멤버의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="4f7ef-113">지역 상수 또는 상수 필드의 이니셜라이저는 대상 형식으로 암시적으로 변환될 수 있는 상수 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>  
  
 <span data-ttu-id="4f7ef-114">상수 식은 컴파일 시간에 완전히 계산될 수 있는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="4f7ef-115">따라서 참조 형식의 상수에 대해 가능한 값은 `string` 및 null 참조뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>  
  
 <span data-ttu-id="4f7ef-116">상수 선언에서는 다음과 같이 여러 상수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-116">The constant declaration can declare multiple constants, such as:</span></span>  
  
```csharp
public const double x = 1.0, y = 2.0, z = 3.0;  
```  
  
 <span data-ttu-id="4f7ef-117">`static` 한정자는 상수 선언에는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-117">The `static` modifier is not allowed in a constant declaration.</span></span>  
  
 <span data-ttu-id="4f7ef-118">상수는 다음과 같이 상수 식에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-118">A constant can participate in a constant expression, as follows:</span></span>  
  
```csharp
public const int c1 = 5;  
public const int c2 = c1 + 100;  
```  
  
> [!NOTE]
>  <span data-ttu-id="4f7ef-119">[readonly](../../../csharp/language-reference/keywords/readonly.md) 키워드는 `const` 키워드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="4f7ef-120">`const` 필드는 필드 선언에서만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="4f7ef-121">`readonly` 필드는 선언이나 생성자에서 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="4f7ef-122">따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="4f7ef-123">또한 `const` 필드가 컴파일 시간 상수라고 하더라도 `readonly` 필드는 다음 줄에서와 같이 런타임 상수에 사용될 수 있습니다. `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="4f7ef-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f7ef-124">예제</span><span class="sxs-lookup"><span data-stu-id="4f7ef-124">Example</span></span>  
 <span data-ttu-id="4f7ef-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4f7ef-125">[!code-cs[csrefKeywordsModifiers#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f7ef-126">예제</span><span class="sxs-lookup"><span data-stu-id="4f7ef-126">Example</span></span>  
 <span data-ttu-id="4f7ef-127">이 예제에서는 상수를 지역 변수로 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f7ef-127">This example demonstrates how to use constants as local variables.</span></span>  
  
 <span data-ttu-id="4f7ef-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4f7ef-128">[!code-cs[csrefKeywordsModifiers#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/const_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4f7ef-129">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4f7ef-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f7ef-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f7ef-130">See Also</span></span>  
 <span data-ttu-id="4f7ef-131">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4f7ef-131">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4f7ef-132">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4f7ef-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4f7ef-133">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4f7ef-133">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4f7ef-134">[한정자](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="4f7ef-134">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="4f7ef-135">readonly</span><span class="sxs-lookup"><span data-stu-id="4f7ef-135">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)

