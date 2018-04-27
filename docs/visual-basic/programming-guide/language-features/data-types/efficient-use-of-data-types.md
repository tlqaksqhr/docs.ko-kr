---
title: 데이터 형식의 효율적 사용(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4cac585cdc3072d595d2446e1937678f9ab03335
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="ae4f2-102">데이터 형식의 효율적 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae4f2-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="ae4f2-103">할당 된 선언 되지 않은 변수 및 데이터 형식 없이 선언 된 변수는 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="ae4f2-104">이렇게 하면 프로그램을 신속 하 게 작성 하지만 더 느리게 실행 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="ae4f2-105">강력한 형식화</span><span class="sxs-lookup"><span data-stu-id="ae4f2-105">Strong Typing</span></span>  
 <span data-ttu-id="ae4f2-106">모든 변수에 대 한 데이터 형식 지정 이라고 *강력한 형식 지정*합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="ae4f2-107">강력한 형식 지정을 사용 하 여에 몇 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="ae4f2-108">변수에 대 한 IntelliSense 지원도를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="ae4f2-109">그러면 코드에 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="ae4f2-110">이용할 컴파일러에서 형식 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="ae4f2-111">이 문은 오버플로와 같은 오류로 인해 런타임에 실패할 수 있는 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="ae4f2-112">또한 지원 하지 않는 개체에 메서드 호출을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="ae4f2-113">코드의 더 빠른 실행에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="ae4f2-114">가장 효율적인 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ae4f2-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="ae4f2-115">분수를 포함 하지 않은 변수의 경우 정수 데이터 형식이 비정 수 계열 형식 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="ae4f2-116">Visual Basic에서는 `Integer` 및 `UInteger` 은 가장 효율적인 숫자 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-116">In Visual Basic, `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="ae4f2-117">소수 자릿수의 숫자에 대 한 `Double` 가장 효율적인 데이터 형식 이므로 현재 플랫폼의 프로세서 배정밀도의 부동 소수점 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="ae4f2-118">그러나 작업과 `Double` 과 같은 정수 계열 형식에서와 마찬가지로 빠르지 않습니다 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="ae4f2-119">데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="ae4f2-119">Specifying Data Type</span></span>  
 <span data-ttu-id="ae4f2-120">사용 하 여는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 특정 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="ae4f2-121">해당 액세스 수준을 사용 하 여 동시에 지정할 수 있습니다는 [공용](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 다음과 같이 키워드는 다음 예제에서는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="ae4f2-122">문자 변환</span><span class="sxs-lookup"><span data-stu-id="ae4f2-122">Character Conversion</span></span>  
 <span data-ttu-id="ae4f2-123">`AscW` 및 `ChrW` 함수는 유니코드에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="ae4f2-124">항상 사용 해야 `Asc` 및 `Chr`, 변환이 필요로 하는 내부 및 외부로 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f2-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae4f2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae4f2-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="ae4f2-126">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ae4f2-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="ae4f2-127">숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ae4f2-127">Numeric Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [<span data-ttu-id="ae4f2-128">변수 선언</span><span class="sxs-lookup"><span data-stu-id="ae4f2-128">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="ae4f2-129">IntelliSense 사용</span><span class="sxs-lookup"><span data-stu-id="ae4f2-129">Using IntelliSense</span></span>](/visualstudio/ide/using-intellisense)
