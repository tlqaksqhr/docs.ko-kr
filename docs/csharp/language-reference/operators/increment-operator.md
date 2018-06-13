---
title: ++ 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: 0fe1150ca7267d02feeab33168eab7f79734c2a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275066"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="44060-102">++ 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="44060-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="44060-103">증가 연산자(`++`)는 피연산자를 1씩 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="44060-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="44060-104">증가 연산자는 피연산자 앞이나 뒤에 나타날 수 있습니다( `++variable` 및 `variable++`).</span><span class="sxs-lookup"><span data-stu-id="44060-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44060-105">설명</span><span class="sxs-lookup"><span data-stu-id="44060-105">Remarks</span></span>  
 <span data-ttu-id="44060-106">첫 번째 형태는 전위 증가 연산입니다.</span><span class="sxs-lookup"><span data-stu-id="44060-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="44060-107">연산 결과는 증가된 후의 피연산자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44060-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="44060-108">두 번째 형태는 후위 증가 연산입니다.</span><span class="sxs-lookup"><span data-stu-id="44060-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="44060-109">연산 결과는 증가되기 전의 피연산자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44060-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="44060-110">숫자 및 열거형 형식에는 미리 정의된 증가 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44060-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="44060-111">사용자 정의 형식은 `++` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44060-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="44060-112">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44060-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44060-113">예</span><span class="sxs-lookup"><span data-stu-id="44060-113">Example</span></span>  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="44060-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44060-114">See Also</span></span>  
 [<span data-ttu-id="44060-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="44060-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="44060-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="44060-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="44060-117">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="44060-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
