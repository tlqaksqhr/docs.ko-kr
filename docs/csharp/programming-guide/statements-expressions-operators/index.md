---
title: "문, 식, 연산자(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- expressions [C#]
- operators [C#]
- C# language, statements
- C# language, operators
- C# language, expressions
- statements [C#]
ms.assetid: 20f8469d-5a6a-4084-ad90-0856b7e97e45
caps.latest.revision: 22
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
ms.openlocfilehash: 71988a5b9aa59b2655b4fd7b91522fe69c8064b6
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="statements-expressions-and-operators-c-programming-guide"></a><span data-ttu-id="42458-102">문, 식, 연산자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="42458-102">Statements, Expressions, and Operators (C# Programming Guide)</span></span>
<span data-ttu-id="42458-103">응용 프로그램을 구성하는 C# 코드는 키워드, 식, 연산자가 포함된 문으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42458-103">The C# code that comprises an application consists of statements made up of keywords, expressions and operators.</span></span> <span data-ttu-id="42458-104">이 섹션에서는 C# 프로그램의 이러한 기본 요소에 대한 정보를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="42458-104">This section contains information regarding these fundamental elements of a C# program.</span></span>  
  
 <span data-ttu-id="42458-105">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42458-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="42458-106">문</span><span class="sxs-lookup"><span data-stu-id="42458-106">Statements</span></span>](../../../csharp/programming-guide/statements-expressions-operators/statements.md)  
  
-   [<span data-ttu-id="42458-107">식</span><span class="sxs-lookup"><span data-stu-id="42458-107">Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
    -   [<span data-ttu-id="42458-108">식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="42458-108">Expression-bodied members</span></span>](expression-bodied-members.md)
 
-   [<span data-ttu-id="42458-109">연산자</span><span class="sxs-lookup"><span data-stu-id="42458-109">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
-   [<span data-ttu-id="42458-110">익명 함수</span><span class="sxs-lookup"><span data-stu-id="42458-110">Anonymous Functions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="42458-111">오버로드할 수 있는 연산자</span><span class="sxs-lookup"><span data-stu-id="42458-111">Overloadable Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)  
  
-   [<span data-ttu-id="42458-112">변환 연산자</span><span class="sxs-lookup"><span data-stu-id="42458-112">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
  
    -   [<span data-ttu-id="42458-113">변환 연산자 사용</span><span class="sxs-lookup"><span data-stu-id="42458-113">Using Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
    -   [<span data-ttu-id="42458-114">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="42458-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [<span data-ttu-id="42458-115">방법: 연산자 오버로드를 사용하여 복소수 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="42458-115">How to: Use Operator Overloading to Create a Complex Number Class</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-operator-overloading-to-create-a-complex-number-class.md)  
  
-   [<span data-ttu-id="42458-116">같음 비교</span><span class="sxs-lookup"><span data-stu-id="42458-116">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="42458-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="42458-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="42458-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42458-118">See Also</span></span>  
 <span data-ttu-id="42458-119">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="42458-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="42458-120">캐스팅 및 형식 변환</span><span class="sxs-lookup"><span data-stu-id="42458-120">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)

