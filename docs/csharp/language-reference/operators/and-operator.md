---
title: "&amp; 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d92a860df6fcc9acf14aab4ec558556735ac8aac
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="ff468-102">&amp; 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ff468-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="ff468-103">& 연산자는 단항 또는 이항 연산자로 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff468-104">설명</span><span class="sxs-lookup"><span data-stu-id="ff468-104">Remarks</span></span>  
 <span data-ttu-id="ff468-105">단항 & 연산자는 해당 피연산자의 주소를 반환합니다([안전하지 않은](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트 필요).</span><span class="sxs-lookup"><span data-stu-id="ff468-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="ff468-106">이항 & 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="ff468-107">정수 형식의 경우 & 연산자는 해당 피연산자의 논리적 비트 AND를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="ff468-108">`bool` 피연산자의 경우 & 연산자는 해당 피연산자의 논리적 AND 연산을 계산합니다. 즉, 피연산자가 둘 다 `true`일 경우에만 결과가 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="ff468-109">`&` 연산자는 첫 번째 피연산자의 값과 관계없이 두 피연산자를 모두 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="ff468-110">예:</span><span class="sxs-lookup"><span data-stu-id="ff468-110">For example:</span></span>  
  
 <span data-ttu-id="ff468-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ff468-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="ff468-112">사용자 정의 형식으로 이항 `&` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="ff468-112">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="ff468-113">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-113">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="ff468-114">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff468-114">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff468-115">예제</span><span class="sxs-lookup"><span data-stu-id="ff468-115">Example</span></span>  
 <span data-ttu-id="ff468-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ff468-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff468-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff468-117">See Also</span></span>  
 <span data-ttu-id="ff468-118">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ff468-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ff468-119">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ff468-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ff468-120">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="ff468-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

