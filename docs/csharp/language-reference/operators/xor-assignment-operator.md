---
title: "^= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 16
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
ms.openlocfilehash: 33b0dccf5031809bb4fcb73d0f7d6a344accdea3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="8c54b-102">^= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8c54b-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="8c54b-103">배타적 OR 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="8c54b-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c54b-104">설명</span><span class="sxs-lookup"><span data-stu-id="8c54b-104">Remarks</span></span>  
 <span data-ttu-id="8c54b-105">다음 형태의 식이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c54b-105">An expression of the form</span></span>  
  
```  
x ^= y  
```  
  
 <span data-ttu-id="8c54b-106">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c54b-106">is evaluated as</span></span>  
  
```  
x = x ^ y  
```  
  
 <span data-ttu-id="8c54b-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c54b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="8c54b-108">[^ 연산자](../../../csharp/language-reference/operators/xor-operator.md)는 정수 피연산자에 대한 배타적 비트 OR 연산과 [bool](../../../csharp/language-reference/keywords/bool.md) 피연산자에 대한 배타적 논리 OR 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8c54b-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="8c54b-109">^= 연산자는 직접 오버로드할 수 없지만 사용자 정의 형식은 [^ 연산자](../../../csharp/language-reference/operators/xor-operator.md)를 오버로드할 수 있습니다([연산자](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="8c54b-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c54b-110">예제</span><span class="sxs-lookup"><span data-stu-id="8c54b-110">Example</span></span>  
 <span data-ttu-id="8c54b-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8c54b-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c54b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c54b-112">See Also</span></span>  
 <span data-ttu-id="8c54b-113">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8c54b-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8c54b-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8c54b-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="8c54b-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="8c54b-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

