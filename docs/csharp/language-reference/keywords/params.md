---
title: "params(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e66cfc8e7b131a4443ee227df5e39c7e3b775324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="params-c-reference"></a><span data-ttu-id="89a0f-102">params(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="89a0f-102">params (C# Reference)</span></span>
<span data-ttu-id="89a0f-103">`params` 키워드를 사용하면 가변 개수의 인수를 사용하는 [메서드 매개 변수](../../../csharp/language-reference/keywords/method-parameters.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89a0f-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="89a0f-104">매개 변수 선언이나 지정된 형식의 인수 배열에 지정된 형식의 쉼표로 구분된 인수 목록을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89a0f-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="89a0f-105">인수를 보내지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89a0f-105">You also can send no arguments.</span></span> <span data-ttu-id="89a0f-106">인수를 보내지 않는 경우 `params` 목록의 길이는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="89a0f-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="89a0f-107">메서드 선언에서 `params` 키워드 뒤에는 추가 매개 변수가 허용되지 않으며, `params` 키워드 하나만 메서드 선언에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89a0f-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89a0f-108">예제</span><span class="sxs-lookup"><span data-stu-id="89a0f-108">Example</span></span>  
 <span data-ttu-id="89a0f-109">다음 예제에서는 `params` 매개 변수에 인수를 보낼 수 있는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89a0f-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="89a0f-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="89a0f-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="89a0f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89a0f-111">See Also</span></span>  
 [<span data-ttu-id="89a0f-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="89a0f-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="89a0f-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="89a0f-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="89a0f-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="89a0f-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="89a0f-115">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="89a0f-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
