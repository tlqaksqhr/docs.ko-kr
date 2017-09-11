---
title: "$(C# 참조)"
ms.date: 2017-02-09
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
dev_langs:
- CSharp
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
ms.assetid: 7d9e21b5-eac3-4878-9530-50e4da578acd
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: 65dfc7b28059c4d41dd9113fd60c6a64987bfc2b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-c-reference"></a><span data-ttu-id="3033c-102">$(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="3033c-102">$ (C# Reference)</span></span>

<span data-ttu-id="3033c-103">문자열 리터럴을 [보간된 문자열](../keywords/interpolated-strings.md)로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3033c-103">Identifies a string literal as an [interpolated string](../keywords/interpolated-strings.md).</span></span> <span data-ttu-id="3033c-104">보간된 문자열은 *보간된 식*과 함께 리터럴 텍스트를 포함하는 템플릿과 유사한 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3033c-104">An interpolated string is a template-like string that contains literal text along with *interpolated expressions*.</span></span> <span data-ttu-id="3033c-105">예를 들어 대입문이나 메서드 호출에서 보간된 문자열이 확인되면 보간된 식이 결과 문자열의 해당 문자열 표현으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="3033c-105">When the interpolated string is resolved, for example in an assignment statement or a method call, its interpolated expressions are replaced by their string representations in the result string.</span></span> <span data-ttu-id="3033c-106">보간된 문자열은 .NET Framework에서 지원되는 [복합 형식 문자열](../../../standard/base-types/composite-format.md)을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="3033c-106">Interpolated strings are replacements for the [composite format strings](../../../standard/base-types/composite-format.md) supported by the .NET Framework.</span></span>

<span data-ttu-id="3033c-107">다음 예제에서는 `$` 문자를 사용하여 보간된 문자열을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3033c-107">The following example uses the `$` character to define an interpolated string.</span></span>

<span data-ttu-id="3033c-108">[!CODE-cs[interpolated-string-symbol](../../../../samples/snippets/csharp/language-reference/keywords/dollar-sign1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="3033c-108">[!CODE-cs[interpolated-string-symbol](../../../../samples/snippets/csharp/language-reference/keywords/dollar-sign1.cs#1)]</span></span>

<span data-ttu-id="3033c-109">보간된 문자열에 대한 자세한 내용은 [보간된 문자열](../keywords/interpolated-strings.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3033c-109">For more information on interpolated strings, see the [Interpolated Strings](../keywords/interpolated-strings.md) topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="3033c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3033c-110">See Also</span></span>  
 <span data-ttu-id="3033c-111">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3033c-111">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3033c-112">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3033c-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3033c-113">C# 특수 문자</span><span class="sxs-lookup"><span data-stu-id="3033c-113">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)

