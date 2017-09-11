---
title: "Visual Basic의 데이터 형식"
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
- data types [Visual Basic], declaring
- typing
- data types [Visual Basic]
- Visual Basic code, data types
- data types [Visual Basic], improving speed with
ms.assetid: 5e1b9aaf-c7ca-4b29-9b22-0e82ed8e85e2
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 8b90a5e58d135a3769761ca431fd0c05f79e045f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="data-types-in-visual-basic"></a><span data-ttu-id="773cf-102">Visual Basic의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="773cf-102">Data Types in Visual Basic</span></span>
<span data-ttu-id="773cf-103">프로그래밍 요소의 *데이터 형식*은 사용할 수 있는 데이터의 종류 및 데이터를 저장하는 방식을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-103">The *data type* of a programming element refers to what kind of data it can hold and how it stores that data.</span></span> <span data-ttu-id="773cf-104">데이터 형식은 컴퓨터 메모리에 저장할 수 있거나 식의 계산에 사용되는 모든 값에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-104">Data types apply to all values that can be stored in computer memory or participate in the evaluation of an expression.</span></span> <span data-ttu-id="773cf-105">모든 변수, 리터럴, 상수, 열거형, 속성, 프로시저 매개 변수, 프로시저 인수 및 프로시저 반환 값은 데이터 형식을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-105">Every variable, literal, constant, enumeration, property, procedure parameter, procedure argument, and procedure return value has a data type.</span></span>  
  
## <a name="declared-data-types"></a><span data-ttu-id="773cf-106">선언된 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="773cf-106">Declared Data Types</span></span>  
 <span data-ttu-id="773cf-107">선언문을 사용하여 프로그래밍 요소를 정의하고 `As` 절을 사용하여 데이터 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-107">You define a programming element with a declaration statement, and you specify its data type with the `As` clause.</span></span> <span data-ttu-id="773cf-108">다음 표에서는 다양한 요소를 선언하기 위해 사용하는 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-108">The following table shows the statements you use to declare various elements.</span></span>  
  
|<span data-ttu-id="773cf-109">프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="773cf-109">Programming element</span></span>|<span data-ttu-id="773cf-110">데이터 형식 선언</span><span class="sxs-lookup"><span data-stu-id="773cf-110">Data type declaration</span></span>|  
|-------------------------|---------------------------|  
|<span data-ttu-id="773cf-111">변수</span><span class="sxs-lookup"><span data-stu-id="773cf-111">Variable</span></span>|<span data-ttu-id="773cf-112">[Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-112">In a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)</span></span><br /><br /> <span data-ttu-id="773cf-113">`Dim`   `amount As Double`</span><span class="sxs-lookup"><span data-stu-id="773cf-113">`Dim`   `amount As Double`</span></span><br /><br /> <span data-ttu-id="773cf-114">`Static`   `yourName As String`</span><span class="sxs-lookup"><span data-stu-id="773cf-114">`Static`   `yourName As String`</span></span><br /><br /> <span data-ttu-id="773cf-115">`Public`   `billsPaid As Decimal = 0`</span><span class="sxs-lookup"><span data-stu-id="773cf-115">`Public`   `billsPaid As Decimal = 0`</span></span>|  
|<span data-ttu-id="773cf-116">Literal</span><span class="sxs-lookup"><span data-stu-id="773cf-116">Literal</span></span>|<span data-ttu-id="773cf-117">리터럴 형식 문자에 지정합니다. [형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)에서 "리터럴 형식 문자"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="773cf-117">With a literal type character; see "Literal Type Characters" in [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span><br /><br /> <span data-ttu-id="773cf-118">`Dim searchChar As Char = "."`  `C`</span><span class="sxs-lookup"><span data-stu-id="773cf-118">`Dim searchChar As Char = "."`  `C`</span></span>|  
|<span data-ttu-id="773cf-119">상수</span><span class="sxs-lookup"><span data-stu-id="773cf-119">Constant</span></span>|<span data-ttu-id="773cf-120">[Const 문](../../../../visual-basic/language-reference/statements/const-statement.md)에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-120">In a [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)</span></span><br /><br /> <span data-ttu-id="773cf-121">`Const`   `modulus As Single = 4.17825F`</span><span class="sxs-lookup"><span data-stu-id="773cf-121">`Const`   `modulus As Single = 4.17825F`</span></span>|  
|<span data-ttu-id="773cf-122">열거형</span><span class="sxs-lookup"><span data-stu-id="773cf-122">Enumeration</span></span>|<span data-ttu-id="773cf-123">[Enum 문](../../../../visual-basic/language-reference/statements/enum-statement.md)에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-123">In an [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)</span></span><br /><br /> <span data-ttu-id="773cf-124">`Public`   `Enum`   `colors`</span><span class="sxs-lookup"><span data-stu-id="773cf-124">`Public`   `Enum`   `colors`</span></span>|  
|<span data-ttu-id="773cf-125">속성</span><span class="sxs-lookup"><span data-stu-id="773cf-125">Property</span></span>|<span data-ttu-id="773cf-126">[Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-126">In a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)</span></span><br /><br /> <span data-ttu-id="773cf-127">`Property`   `region() As String`</span><span class="sxs-lookup"><span data-stu-id="773cf-127">`Property`   `region() As String`</span></span>|  
|<span data-ttu-id="773cf-128">프로시저 매개 변수</span><span class="sxs-lookup"><span data-stu-id="773cf-128">Procedure parameter</span></span>|<span data-ttu-id="773cf-129">[Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md) 또는 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-129">In a [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md), [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md), or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="773cf-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span><span class="sxs-lookup"><span data-stu-id="773cf-130">`Sub addSale(ByVal`   `amount`   `As Double)`</span></span>|  
|<span data-ttu-id="773cf-131">프로시저 인수</span><span class="sxs-lookup"><span data-stu-id="773cf-131">Procedure argument</span></span>|<span data-ttu-id="773cf-132">호출 코드에서 지정합니다. 각 인수는 이미 선언된 프로그래밍 요소이거나 선언된 요소를 포함하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-132">In the calling code; each argument is a programming element that has already been declared, or an expression containing declared elements</span></span><br /><br /> <span data-ttu-id="773cf-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span><span class="sxs-lookup"><span data-stu-id="773cf-133">`subString = Left(`  `inputString`  `,`   `5`  `)`</span></span>|  
|<span data-ttu-id="773cf-134">프로시저 반환 값</span><span class="sxs-lookup"><span data-stu-id="773cf-134">Procedure return value</span></span>|<span data-ttu-id="773cf-135">[Function 문](../../../../visual-basic/language-reference/statements/function-statement.md) 또는 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="773cf-135">In a [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) or [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)</span></span><br /><br /> <span data-ttu-id="773cf-136">`Function convert(ByVal b As Byte)`   `As String`</span><span class="sxs-lookup"><span data-stu-id="773cf-136">`Function convert(ByVal b As Byte)`   `As String`</span></span>|  
  
 <span data-ttu-id="773cf-137">Visual Basic 데이터 형식 목록은 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="773cf-137">For a list of Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="773cf-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="773cf-138">See Also</span></span>  
 <span data-ttu-id="773cf-139">[형식 문자](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span><span class="sxs-lookup"><span data-stu-id="773cf-139">[Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md) </span></span>  
 <span data-ttu-id="773cf-140">[기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="773cf-140">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
 <span data-ttu-id="773cf-141">[복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="773cf-141">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
 <span data-ttu-id="773cf-142">[Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="773cf-142">[Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
 <span data-ttu-id="773cf-143">[값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="773cf-143">[Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
 <span data-ttu-id="773cf-144">[Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="773cf-144">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
 <span data-ttu-id="773cf-145">[구조체](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="773cf-145">[Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
 <span data-ttu-id="773cf-146">[튜플](tuples.md)   </span><span class="sxs-lookup"><span data-stu-id="773cf-146">[Tuples](tuples.md)   </span></span>  
 <span data-ttu-id="773cf-147">[데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="773cf-147">[Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
 <span data-ttu-id="773cf-148">[데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="773cf-148">[Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
 [<span data-ttu-id="773cf-149">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="773cf-149">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

