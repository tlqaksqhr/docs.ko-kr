---
title: "방법: 포인터 변수의 값 가져오기(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8065c10bec737789f13dcbafe147b50eedb9da36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="81180-102">방법: 포인터 변수의 값 가져오기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="81180-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="81180-103">포인터 간접 참조 연산자를 사용하여 포인터가 가리키는 위치에 있는 변수를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81180-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="81180-104">식의 형식은 다음과 같습니다. 여기서 `p`는 포인터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81180-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="81180-105">포인터 형식이 아닌 식에서는 단항 간접 참조 연산자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81180-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="81180-106">또한 [void](../../../csharp/language-reference/keywords/void.md) 포인터에는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81180-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="81180-107">[null](../../../csharp/language-reference/keywords/null.md) 포인터에 간접 참조 연산자를 적용할 때의 결과는 구현에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="81180-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81180-108">예제</span><span class="sxs-lookup"><span data-stu-id="81180-108">Example</span></span>  
 <span data-ttu-id="81180-109">다음 예제에서는 다양한 형식의 포인터를 사용하여 `char` 형식의 변수에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="81180-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="81180-110">변수에 할당되는 물리적 주소가 변경될 수 있으므로 `theChar`의 주소는 실행할 때마다 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="81180-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
 <span data-ttu-id="81180-111">**TheChar 값 Z =**</span><span class="sxs-lookup"><span data-stu-id="81180-111">**Value of theChar = Z**</span></span>  
<span data-ttu-id="81180-112">**Address of theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="81180-112">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="81180-113">**Value of pChar = Z** </span><span class="sxs-lookup"><span data-stu-id="81180-113">**Value of pChar = Z** </span></span>  
<span data-ttu-id="81180-114">**Value of pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="81180-114">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="81180-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81180-115">See Also</span></span>  
 [<span data-ttu-id="81180-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="81180-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="81180-117">포인터 식</span><span class="sxs-lookup"><span data-stu-id="81180-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="81180-118">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="81180-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="81180-119">유형</span><span class="sxs-lookup"><span data-stu-id="81180-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="81180-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="81180-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="81180-121">fixed 문</span><span class="sxs-lookup"><span data-stu-id="81180-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="81180-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="81180-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
