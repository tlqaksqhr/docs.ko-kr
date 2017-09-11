---
title: "-- 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
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
ms.openlocfilehash: 100e68f3b07164b0cfb398a32f47137f2726943f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="---operator-c-reference"></a><span data-ttu-id="200f9-102">-- 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="200f9-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="200f9-103">감소 연산자(`--`)는 피연산자를 1씩 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="200f9-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="200f9-104">감소 연산자는 피연산자 앞이나 뒤에 나타날 수 있습니다(`--variable` 및 `variable--`).</span><span class="sxs-lookup"><span data-stu-id="200f9-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="200f9-105">첫 번째 형태는 전위 감소 연산입니다.</span><span class="sxs-lookup"><span data-stu-id="200f9-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="200f9-106">연산 결과는 감소된 후의 피연산자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="200f9-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="200f9-107">두 번째 형태는 후위 감소 연산입니다.</span><span class="sxs-lookup"><span data-stu-id="200f9-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="200f9-108">연산 결과는 감소되기 전의 피연산자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="200f9-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="200f9-109">설명</span><span class="sxs-lookup"><span data-stu-id="200f9-109">Remarks</span></span>  
 <span data-ttu-id="200f9-110">숫자 및 열거형 형식에는 미리 정의된 감소 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="200f9-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="200f9-111">사용자 정의 형식은 `--` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="200f9-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="200f9-112">정수 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="200f9-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="200f9-113">예제</span><span class="sxs-lookup"><span data-stu-id="200f9-113">Example</span></span>  
 <span data-ttu-id="200f9-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="200f9-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200f9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="200f9-115">See Also</span></span>  
 <span data-ttu-id="200f9-116">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="200f9-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="200f9-117">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="200f9-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="200f9-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="200f9-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

