---
title: "void(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords: void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a71cac30132417abce60cdde54322b5f2067d39d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="void-c-reference"></a><span data-ttu-id="65f6a-102">void(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="65f6a-102">void (C# Reference)</span></span>
<span data-ttu-id="65f6a-103">메서드에 대한 반환 형식으로 사용될 경우 `void`는 메서드가 값을 반환하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="65f6a-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="65f6a-104">`void`는 메서드의 매개 변수 목록에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65f6a-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="65f6a-105">매개 변수를 사용하지 않고 값을 반환하지 않는 메서드는 다음과 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="65f6a-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="65f6a-106">`void`는 또한 알 수 없는 형식에 대한 포인터를 선언하기 위해 안전하지 않은 컨텍스트에서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="65f6a-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="65f6a-107">자세한 내용은 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65f6a-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="65f6a-108">`void`는 .NET Framework <xref:System.Void?displayProperty=nameWithType> 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="65f6a-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="65f6a-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="65f6a-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="65f6a-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65f6a-110">See also</span></span>
 [<span data-ttu-id="65f6a-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="65f6a-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="65f6a-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="65f6a-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="65f6a-113">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="65f6a-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="65f6a-114">참조 형식</span><span class="sxs-lookup"><span data-stu-id="65f6a-114">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="65f6a-115">값 형식</span><span class="sxs-lookup"><span data-stu-id="65f6a-115">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="65f6a-116">메서드</span><span class="sxs-lookup"><span data-stu-id="65f6a-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="65f6a-117">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="65f6a-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
