---
title: "^ 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: 19
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
ms.openlocfilehash: f081dd2979930404639638179444adc05dd462e1
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="f0845-102">^ 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f0845-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="f0845-103">이항 `^` 연산자는 정수 형식 및 `bool`에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="f0845-104">정수 형식의 경우 `^` 연산자는 해당 피연산자의 배타적 비트 OR 연산자를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="f0845-105">`bool` 피연산자의 경우 `^` 연산자는 피연산자의 배타적 논리 OR 연산을 계산합니다. 즉 피연산자 중 정확히 하나가 `true`일 경우에만 결과가 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0845-106">설명</span><span class="sxs-lookup"><span data-stu-id="f0845-106">Remarks</span></span>  
 <span data-ttu-id="f0845-107">사용자 정의 형식은 `^` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="f0845-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="f0845-108">정수 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0845-109">예제</span><span class="sxs-lookup"><span data-stu-id="f0845-109">Example</span></span>  
 <span data-ttu-id="f0845-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0845-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="f0845-111">이전 예제에서의 `0xf8 ^ 0x3f` 계산은 16진수 값 F8 및 3F에 해당하는 다음 두 이진 값에 대하여 배타적 비트 OR 연산을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-111">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="f0845-112">배타적 OR 연산 결과는 `1100 0111`이며 16진수로 나타내면 C7입니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-112">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0845-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0845-113">See Also</span></span>  
 <span data-ttu-id="f0845-114">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0845-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f0845-115">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0845-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="f0845-116">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="f0845-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

