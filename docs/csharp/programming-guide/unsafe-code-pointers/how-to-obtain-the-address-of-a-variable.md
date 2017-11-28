---
title: "방법: 변수의 주소 가져오기(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d0969f7e62864c682660f08cd4198aa4032e0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a><span data-ttu-id="856ea-102">방법: 변수의 주소 가져오기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="856ea-102">How to: Obtain the Address of a Variable (C# Programming Guide)</span></span>
<span data-ttu-id="856ea-103">고정 변수로 계산되는 단항 식의 주소를 가져오려면 address-of 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-103">To obtain the address of a unary expression, which evaluates to a fixed variable, use the address-of operator:</span></span>  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 <span data-ttu-id="856ea-104">address-of 연산자는 변수에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-104">The address-of operator can only be applied to a variable.</span></span> <span data-ttu-id="856ea-105">변수가 이동 가능한 변수인 경우 해당 주소를 가져오기 전에 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)을 사용하여 일시적으로 변수를 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-105">If the variable is a moveable variable, you can use the [fixed statement](../../../csharp/language-reference/keywords/fixed-statement.md) to temporarily fix the variable before obtaining its address.</span></span>  
  
 <span data-ttu-id="856ea-106">변수가 초기화되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-106">It is your responsibility to ensure that the variable is initialized.</span></span> <span data-ttu-id="856ea-107">변수가 초기화되지 않은 경우 컴파일러가 오류 메시지를 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-107">The compiler will not issue an error message if the variable is not initialized.</span></span>  
  
 <span data-ttu-id="856ea-108">상수 또는 값의 주소를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-108">You cannot get the address of a constant or a value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="856ea-109">예제</span><span class="sxs-lookup"><span data-stu-id="856ea-109">Example</span></span>  
 <span data-ttu-id="856ea-110">이 예제에서는 `int`에 대한 포인터인 `p`가 선언되고 정수 변수 `number`의 주소가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-110">In this example, a pointer to `int`, `p`, is declared and assigned the address of an integer variable, `number`.</span></span> <span data-ttu-id="856ea-111">`number` 변수는 *p에 대한 할당 결과로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-111">The variable `number` is initialized as a result of the assignment to *p.</span></span> <span data-ttu-id="856ea-112">이 대입문을 주석으로 설정하면 `number` 변수의 초기화가 제거되지만 컴파일 시간 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-112">If you make this assignment statement a comment, the initialization of the variable `number` will be removed, but no compile-time error is issued.</span></span> <span data-ttu-id="856ea-113">[멤버 액세스](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) 연산자 `->`을 사용하여 포인터에 저장된 주소를 가져오고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="856ea-113">Notice the use of the [Member Access](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) operator `->` to obtain and display the address stored in the pointer.</span></span>  
  
 [!code-csharp[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="856ea-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="856ea-114">See Also</span></span>  
 [<span data-ttu-id="856ea-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="856ea-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="856ea-116">포인터 식</span><span class="sxs-lookup"><span data-stu-id="856ea-116">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="856ea-117">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="856ea-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="856ea-118">유형</span><span class="sxs-lookup"><span data-stu-id="856ea-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="856ea-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="856ea-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="856ea-120">fixed 문</span><span class="sxs-lookup"><span data-stu-id="856ea-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="856ea-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="856ea-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
