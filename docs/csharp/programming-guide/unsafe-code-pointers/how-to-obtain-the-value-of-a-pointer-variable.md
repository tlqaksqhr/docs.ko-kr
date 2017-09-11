---
title: "방법: 포인터 변수의 값 가져오기(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
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
ms.openlocfilehash: 4cff42de07f2edb279ddd1cafefe9f4b67a38ce1
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a><span data-ttu-id="350d0-102">방법: 포인터 변수의 값 가져오기(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="350d0-102">How to: Obtain the Value of a Pointer Variable (C# Programming Guide)</span></span>
<span data-ttu-id="350d0-103">포인터 간접 참조 연산자를 사용하여 포인터가 가리키는 위치에 있는 변수를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350d0-103">Use the pointer indirection operator to obtain the variable at the location pointed to by a pointer.</span></span> <span data-ttu-id="350d0-104">식의 형식은 다음과 같습니다. 여기서 `p`는 포인터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="350d0-104">The expression takes the following form, where `p` is a pointer type:</span></span>  
  
```  
*p;  
```  
  
 <span data-ttu-id="350d0-105">포인터 형식이 아닌 식에서는 단항 간접 참조 연산자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="350d0-105">You cannot use the unary indirection operator on an expression of any type other than the pointer type.</span></span> <span data-ttu-id="350d0-106">또한 [void](../../../csharp/language-reference/keywords/void.md) 포인터에는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="350d0-106">Also, you cannot apply it to a [void](../../../csharp/language-reference/keywords/void.md) pointer.</span></span>  
  
 <span data-ttu-id="350d0-107">[null](../../../csharp/language-reference/keywords/null.md) 포인터에 간접 참조 연산자를 적용할 때의 결과는 구현에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="350d0-107">When you apply the indirection operator to a [null](../../../csharp/language-reference/keywords/null.md) pointer, the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="350d0-108">예제</span><span class="sxs-lookup"><span data-stu-id="350d0-108">Example</span></span>  
 <span data-ttu-id="350d0-109">다음 예제에서는 다양한 형식의 포인터를 사용하여 `char` 형식의 변수에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="350d0-109">In the following example, a variable of the type `char` is accessed by using pointers of different types.</span></span> <span data-ttu-id="350d0-110">변수에 할당되는 물리적 주소가 변경될 수 있으므로 `theChar`의 주소는 실행할 때마다 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="350d0-110">Note that the address of `theChar` will vary from run to run, because the physical address allocated to a variable can change.</span></span>  
  
 <span data-ttu-id="350d0-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="350d0-111">[!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]</span></span>  
  
 <span data-ttu-id="350d0-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="350d0-112">[!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]</span></span>  
  
 <span data-ttu-id="350d0-113">**Value of theChar = Z** </span><span class="sxs-lookup"><span data-stu-id="350d0-113">**Value of theChar = Z** </span></span>  
<span data-ttu-id="350d0-114">**Address of theChar = 12F718**</span><span class="sxs-lookup"><span data-stu-id="350d0-114">**Address of theChar = 12F718**</span></span>  
<span data-ttu-id="350d0-115">**Value of pChar = Z** </span><span class="sxs-lookup"><span data-stu-id="350d0-115">**Value of pChar = Z** </span></span>  
<span data-ttu-id="350d0-116">**Value of pInt = 90**</span><span class="sxs-lookup"><span data-stu-id="350d0-116">**Value of pInt = 90**</span></span>    
## <a name="see-also"></a><span data-ttu-id="350d0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="350d0-117">See Also</span></span>  
 <span data-ttu-id="350d0-118">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="350d0-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="350d0-119">[포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="350d0-119">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="350d0-120">[포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="350d0-120">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="350d0-121">[형식](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="350d0-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="350d0-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="350d0-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="350d0-123">[fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="350d0-123">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="350d0-124">stackalloc</span><span class="sxs-lookup"><span data-stu-id="350d0-124">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

