---
title: params(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: d7e0094d0f60aa201ae7229983f3e4b9764d2cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="params-c-reference"></a><span data-ttu-id="325a7-102">params(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="325a7-102">params (C# Reference)</span></span>
<span data-ttu-id="325a7-103">`params` 키워드를 사용하면 가변 개수의 인수를 사용하는 [메서드 매개 변수](../../../csharp/language-reference/keywords/method-parameters.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="325a7-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="325a7-104">매개 변수 선언이나 지정된 형식의 인수 배열에 지정된 형식의 쉼표로 구분된 인수 목록을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="325a7-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="325a7-105">인수를 보내지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="325a7-105">You also can send no arguments.</span></span> <span data-ttu-id="325a7-106">인수를 보내지 않는 경우 `params` 목록의 길이는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="325a7-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="325a7-107">메서드 선언에서 `params` 키워드 뒤에는 추가 매개 변수가 허용되지 않으며, `params` 키워드 하나만 메서드 선언에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="325a7-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="325a7-108">예</span><span class="sxs-lookup"><span data-stu-id="325a7-108">Example</span></span>  
 <span data-ttu-id="325a7-109">다음 예제에서는 `params` 매개 변수에 인수를 보낼 수 있는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="325a7-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="325a7-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="325a7-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="325a7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="325a7-111">See Also</span></span>  
 [<span data-ttu-id="325a7-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="325a7-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="325a7-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="325a7-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="325a7-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="325a7-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="325a7-115">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="325a7-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
