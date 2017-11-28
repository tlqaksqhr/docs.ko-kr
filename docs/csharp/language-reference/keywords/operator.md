---
title: "연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords: operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8fae5487d5daa5ada52d45919598d1abd217aee9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="operator-c-reference"></a><span data-ttu-id="fe338-102">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="fe338-102">operator (C# Reference)</span></span>
<span data-ttu-id="fe338-103">`operator` 키워드를 사용하여 기본 제공 연산자를 오버로드하거나 클래스 또는 구조체 선언에서 사용자 정의 변환을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe338-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe338-104">예제</span><span class="sxs-lookup"><span data-stu-id="fe338-104">Example</span></span>  
 <span data-ttu-id="fe338-105">다음은 소수에 대한 매우 간단한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe338-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="fe338-106">+ 및 * 연산자를 오버로드하여 소수 더하기 및 곱하기를 수행하고 분수 형식을 double 형식으로 변환하는 변환 연산자도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe338-106">It overloads the + and * operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a Fraction type to a double type.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="fe338-107">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="fe338-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fe338-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe338-108">See Also</span></span>  
 [<span data-ttu-id="fe338-109">C# 참조</span><span class="sxs-lookup"><span data-stu-id="fe338-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fe338-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fe338-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fe338-111">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="fe338-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="fe338-112">implicit</span><span class="sxs-lookup"><span data-stu-id="fe338-112">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="fe338-113">explicit</span><span class="sxs-lookup"><span data-stu-id="fe338-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="fe338-114">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="fe338-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
