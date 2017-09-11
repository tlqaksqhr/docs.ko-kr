---
title: "++ 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
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
ms.openlocfilehash: 9f481dbe2437495b109d6d41cd24c8b4bb5b6a5b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="891a1-102">++ 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="891a1-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="891a1-103">증가 연산자(`++`)는 피연산자를 1씩 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="891a1-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="891a1-104">증가 연산자는 피연산자 앞이나 뒤에 나타날 수 있습니다( `++variable` 및 `variable++`).</span><span class="sxs-lookup"><span data-stu-id="891a1-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="891a1-105">설명</span><span class="sxs-lookup"><span data-stu-id="891a1-105">Remarks</span></span>  
 <span data-ttu-id="891a1-106">첫 번째 형태는 전위 증가 연산입니다.</span><span class="sxs-lookup"><span data-stu-id="891a1-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="891a1-107">연산 결과는 증가된 후의 피연산자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="891a1-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="891a1-108">두 번째 형태는 후위 증가 연산입니다.</span><span class="sxs-lookup"><span data-stu-id="891a1-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="891a1-109">연산 결과는 증가되기 전의 피연산자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="891a1-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="891a1-110">숫자 및 열거형 형식에는 미리 정의된 증가 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="891a1-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="891a1-111">사용자 정의 형식은 `++` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="891a1-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="891a1-112">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="891a1-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="891a1-113">예제</span><span class="sxs-lookup"><span data-stu-id="891a1-113">Example</span></span>  
 <span data-ttu-id="891a1-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="891a1-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891a1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="891a1-115">See Also</span></span>  
 <span data-ttu-id="891a1-116">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="891a1-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="891a1-117">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="891a1-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="891a1-118">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="891a1-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

