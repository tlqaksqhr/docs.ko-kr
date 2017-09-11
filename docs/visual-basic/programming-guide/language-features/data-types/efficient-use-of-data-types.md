---
title: "(Visual Basic) 데이터 형식의 효율적 사용 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function, preferred to Asc
- data types [Visual Basic], using efficiently
- optimization, data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function, preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ca8d5885aea12a3f1f9cb35f08bf63c1a89e7ebc
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="efficient-use-of-data-types-visual-basic"></a><span data-ttu-id="f7c4b-102">데이터 형식의 효율적 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7c4b-102">Efficient Use of Data Types (Visual Basic)</span></span>
<span data-ttu-id="f7c4b-103">선언 되지 않은 변수 및 데이터 형식 없이 선언 된 변수에 할당 되는 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-103">Undeclared variables and variables declared without a data type are assigned the `Object` data type.</span></span> <span data-ttu-id="f7c4b-104">이렇게 하면 쉽게 프로그램을 신속 하 게 작성할 수 있지만 더 느리게 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-104">This makes it easy to write programs quickly, but it can cause them to execute more slowly.</span></span>  
  
## <a name="strong-typing"></a><span data-ttu-id="f7c4b-105">강력한 형식</span><span class="sxs-lookup"><span data-stu-id="f7c4b-105">Strong Typing</span></span>  
 <span data-ttu-id="f7c4b-106">모든 변수에 대해 데이터 형식 지정 이라고 *강력한 형식 지정*합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-106">Specifying data types for all your variables is known as *strong typing*.</span></span> <span data-ttu-id="f7c4b-107">강력한 형식화를 사용 하 여 몇 가지 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-107">Using strong typing has several advantages:</span></span>  
  
-   <span data-ttu-id="f7c4b-108">변수에 대 한 IntelliSense 지원을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-108">It enables IntelliSense support for your variables.</span></span> <span data-ttu-id="f7c4b-109">이렇게 하면 코드를 입력 하면 해당 속성 및 기타 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-109">This allows you to see their properties and other members as you type in the code.</span></span>  
  
-   <span data-ttu-id="f7c4b-110">컴파일러에서 형식 검사의 장점은 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-110">It takes advantage of compiler type checking.</span></span> <span data-ttu-id="f7c4b-111">이 런타임에 오버플로와 같은 오류로 인해 실패할 수 있는 문을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-111">This catches statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="f7c4b-112">또한 지원 하지 않는 개체에 메서드 호출을 찾아냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-112">It also catches calls to methods on objects that do not support them.</span></span>  
  
-   <span data-ttu-id="f7c4b-113">그 결과, 코드의 실행이 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-113">It results in faster execution of your code.</span></span>  
  
## <a name="most-efficient-data-types"></a><span data-ttu-id="f7c4b-114">가장 효율적인 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f7c4b-114">Most Efficient Data Types</span></span>  
 <span data-ttu-id="f7c4b-115">분수를 포함 하지 않은 변수의 정수 계열 데이터 형식은 비정 수 형식 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-115">For variables that never contain fractions, the integral data types are more efficient than the nonintegral types.</span></span> <span data-ttu-id="f7c4b-116">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` 및 `UInteger` 는 가장 효율적인 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-116">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` and `UInteger` are the most efficient numeric types.</span></span>  
  
 <span data-ttu-id="f7c4b-117">소수에 `Double` 은 가장 효율적인 데이터 형식이 고, 현재 플랫폼의 프로세서 배정밀도의 부동 소수점 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-117">For fractional numbers, `Double` is the most efficient data type, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="f7c4b-118">그러나 작업과 `Double` 과 같은 정수 계열 형식에서와 마찬가지로 빠르지 않습니다 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-118">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
## <a name="specifying-data-type"></a><span data-ttu-id="f7c4b-119">데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="f7c4b-119">Specifying Data Type</span></span>  
 <span data-ttu-id="f7c4b-120">사용 하 여는 [Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) 특정 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-120">Use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) to declare a variable of a specific type.</span></span> <span data-ttu-id="f7c4b-121">액세스 수준을 사용 하 여 동시에 지정할 수 있습니다는 [공용](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [친구](../../../../visual-basic/language-reference/modifiers/friend.md), 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 다음 예제에서와 같이 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-121">You can simultaneously specify its access level by using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, as in the following example.</span></span>  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a><span data-ttu-id="f7c4b-122">문자 변환</span><span class="sxs-lookup"><span data-stu-id="f7c4b-122">Character Conversion</span></span>  
 <span data-ttu-id="f7c4b-123">`AscW` 및 `ChrW` 함수는 유니코드에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-123">The `AscW` and `ChrW` functions operate in Unicode.</span></span> <span data-ttu-id="f7c4b-124">항상 사용 해야 `Asc` 및 `Chr`, 변환이 필요로 하는 내부 및 외부로 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f7c4b-124">You should use them in preference to `Asc` and `Chr`, which must translate into and out of Unicode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c4b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7c4b-125">See Also</span></span>  
 <span data-ttu-id="f7c4b-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></xref:Microsoft.VisualBasic.Strings.Asc%2A></span><span class="sxs-lookup"><span data-stu-id="f7c4b-126"><xref:Microsoft.VisualBasic.Strings.Asc%2A></span></span>   
 <span data-ttu-id="f7c4b-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="f7c4b-127"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
 <span data-ttu-id="f7c4b-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></xref:Microsoft.VisualBasic.Strings.Chr%2A></span><span class="sxs-lookup"><span data-stu-id="f7c4b-128"><xref:Microsoft.VisualBasic.Strings.Chr%2A></span></span>   
 <span data-ttu-id="f7c4b-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></xref:Microsoft.VisualBasic.Strings.ChrW%2A></span><span class="sxs-lookup"><span data-stu-id="f7c4b-129"><xref:Microsoft.VisualBasic.Strings.ChrW%2A></span></span>   
<span data-ttu-id="f7c4b-130"> [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="f7c4b-130"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="f7c4b-131"> [숫자 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="f7c4b-131"> [Numeric Data Types](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md) </span></span>  
<span data-ttu-id="f7c4b-132"> [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="f7c4b-132"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="f7c4b-133"> [IntelliSense 사용](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span><span class="sxs-lookup"><span data-stu-id="f7c4b-133"> [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)</span></span>
