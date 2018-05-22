---
title: 포인터 비교(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: af264cd1572faafe25ee170b35cbeb48ed0fb2aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="59830-102">포인터 비교(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="59830-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="59830-103">다음 연산자를 적용하여 임의 형식의 포인터를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59830-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="59830-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="59830-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="59830-105">비교 연산자는 부호 없는 정수처럼 두 피연산자의 주소를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="59830-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59830-106">예</span><span class="sxs-lookup"><span data-stu-id="59830-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a><span data-ttu-id="59830-107">샘플 출력</span><span class="sxs-lookup"><span data-stu-id="59830-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="59830-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59830-108">See Also</span></span>  
 [<span data-ttu-id="59830-109">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="59830-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="59830-110">포인터 식</span><span class="sxs-lookup"><span data-stu-id="59830-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="59830-111">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="59830-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="59830-112">포인터 조작</span><span class="sxs-lookup"><span data-stu-id="59830-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="59830-113">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="59830-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="59830-114">유형</span><span class="sxs-lookup"><span data-stu-id="59830-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="59830-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="59830-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="59830-116">fixed 문</span><span class="sxs-lookup"><span data-stu-id="59830-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="59830-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="59830-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
