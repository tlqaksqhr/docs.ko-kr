---
title: Visual Basic의 문자열 기본
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 7d2477070dce558aa932c822852ac8ac9c6721e4
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332677"
---
# <a name="string-basics-in-visual-basic"></a><span data-ttu-id="9f805-102">Visual Basic의 문자열 기본</span><span class="sxs-lookup"><span data-stu-id="9f805-102">String Basics in Visual Basic</span></span>
<span data-ttu-id="9f805-103">`String` 데이터 형식은 일련의 문자를 나타내며, 각각은 차례로 `Char` 데이터 형식의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-103">The `String` data type represents a series of characters (each representing in turn an instance of the `Char` data type).</span></span> <span data-ttu-id="9f805-104">이 항목에서는 Visual Basic에서 문자열의 기본 개념을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-104">This topic introduces the basic concepts of strings in Visual Basic.</span></span>  
  
## <a name="string-variables"></a><span data-ttu-id="9f805-105">문자열 변수</span><span class="sxs-lookup"><span data-stu-id="9f805-105">String Variables</span></span>  
 <span data-ttu-id="9f805-106">문자열의 인스턴스에 일련의 문자를 나타내는 리터럴 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-106">An instance of a string can be assigned a literal value that represents a series of characters.</span></span> <span data-ttu-id="9f805-107">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9f805-107">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#63](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]  
  
 <span data-ttu-id="9f805-108">또한 `String` 변수는 문자열로 계산되는 모든 식을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-108">A `String` variable can also accept any expression that evaluates to a string.</span></span> <span data-ttu-id="9f805-109">예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-109">Examples are shown below:</span></span>  
  
 [!code-vb[VbVbalrStrings#64](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]  
  
 <span data-ttu-id="9f805-110">`String` 변수에 할당되는 모든 리터럴은 큰따옴표("")로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-110">Any literal that is assigned to a `String` variable must be enclosed in quotation marks ("").</span></span> <span data-ttu-id="9f805-111">즉, 문자열 내의 큰따옴표는 큰따옴표로 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-111">This means that a quotation mark within a string cannot be represented by a quotation mark.</span></span> <span data-ttu-id="9f805-112">예를 들어 다음 코드는 컴파일러 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-112">For example, the following code causes a compiler error:</span></span>  
  
 [!code-vb[VbVbalrStrings#65](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]  
  
 <span data-ttu-id="9f805-113">이 코드에서는 컴파일러가 두번째 큰따옴표 다음 문자열을 종료하고 문자열의 나머지 부분이 코드로 해석되기 때문에 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-113">This code causes an error because the compiler terminates the string after the second quotation mark, and the remainder of the string is interpreted as code.</span></span> <span data-ttu-id="9f805-114">이 문제를 해결 하려면 Visual Basic를 하나의 따옴표로 문자열에서 리터럴 문자열에 두 개의 따옴표를 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-114">To solve this problem, Visual Basic interprets two quotation marks in a string literal as one quotation mark in the string.</span></span> <span data-ttu-id="9f805-115">다음 예제에서는 문자열에 큰따옴표를 포함하는 올바른 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-115">The following example demonstrates the correct way to include a quotation mark in a string:</span></span>  
  
 [!code-vb[VbVbalrStrings#66](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]  
  
 <span data-ttu-id="9f805-116">이전 예제에서 `Look`이라는 단어 앞에 오는 두 개의 큰따옴표가 문자열에서 하나의 큰따옴표가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-116">In the preceding example, the two quotation marks preceding the word `Look` become one quotation mark in the string.</span></span> <span data-ttu-id="9f805-117">줄의 끝에 있는 큰따옴표 세 개는 문자열의 큰따옴표 한 개와 문자열 종료 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-117">The three quotation marks at the end of the line represent one quotation mark in the string and the string termination character.</span></span>  
  
 <span data-ttu-id="9f805-118">문자열 리터럴에 여러 줄이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-118">String literals can contain multiple lines:</span></span>  
  
```vb  
Dim x = "hello  
world"  
```  
  
 <span data-ttu-id="9f805-119">결과 문자열에는 문자열 리터럴(vbcr, vbcrlf 등)에서 사용한 줄 바꿈 시퀀스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-119">The resulting string contains newline sequences that you used in your string literal (vbcr, vbcrlf, etc.).</span></span>  <span data-ttu-id="9f805-120">이전 해결 방법은 더 이상 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-120">You no longer need to use the old workaround:</span></span>  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a><span data-ttu-id="9f805-121">문자열의 문자</span><span class="sxs-lookup"><span data-stu-id="9f805-121">Characters in Strings</span></span>  
 <span data-ttu-id="9f805-122">문자열은 일련은 `Char` 값으로 간주되며 `String` 형식에는 배열에서 허용하는 조작과 유사한 많은 조작을 문자열에서 수행할 수 있는 기본 제공 함수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-122">A string can be thought of as a series of `Char` values, and the `String` type has built-in functions that allow you to perform many manipulations on a string that resemble the manipulations allowed by arrays.</span></span> <span data-ttu-id="9f805-123">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 모든 배열과 마찬가지로 이러한 배열은 0부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-123">Like all array in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], these are zero-based arrays.</span></span> <span data-ttu-id="9f805-124">문자열에서 나타나는 위치를 기준으로 문자에 액세스하는 방법을 제공하는 `Chars` 속성을 통해 문자열의 특정 문자를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-124">You may refer to a specific character in a string through the `Chars` property, which provides a way to access a character by the position in which it appears in the string.</span></span> <span data-ttu-id="9f805-125">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9f805-125">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#67](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]  
  
 <span data-ttu-id="9f805-126">위 예제에서 문자열의 `Chars` 속성은 문자열에서 네 번째 문자인 `D`를 반환하고 `myChar`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-126">In the above example, the `Chars` property of the string returns the fourth character in the string, which is `D`, and assigns it to `myChar`.</span></span> <span data-ttu-id="9f805-127">`Length` 속성을 통해 특정 문자열의 길이를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-127">You can also get the length of a particular string through the `Length` property.</span></span> <span data-ttu-id="9f805-128">문자열에서 여러 배열 형식 조작을 수행해야 하는 경우 문자열의 `ToCharArray` 함수를 사용하여 `Char` 인스턴스의 배열로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-128">If you need to perform multiple array-type manipulations on a string, you can convert it to an array of `Char` instances using the `ToCharArray` function of the string.</span></span> <span data-ttu-id="9f805-129">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="9f805-129">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#68](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]  
  
 <span data-ttu-id="9f805-130">이제 변수 `myArray`에 `Char` 값의 배열이 포함되며, 각각은 `myString`의 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-130">The variable `myArray` now contains an array of `Char` values, each representing a character from `myString`.</span></span>  
  
## <a name="the-immutability-of-strings"></a><span data-ttu-id="9f805-131">문자열의 불변성</span><span class="sxs-lookup"><span data-stu-id="9f805-131">The Immutability of Strings</span></span>  
 <span data-ttu-id="9f805-132">문자열은 *변경할 수 없는*, 해당 값을 한 번만 변경할 수 없습니다. 즉 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-132">A string is *immutable*, which means its value cannot be changed once it has been created.</span></span> <span data-ttu-id="9f805-133">그러나 둘 이상의 값을 문자열 변수에 할당할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-133">However, this does not prevent you from assigning more than one value to a string variable.</span></span> <span data-ttu-id="9f805-134">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f805-134">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#69](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]  
  
 <span data-ttu-id="9f805-135">여기에서는 문자열 변수를 만들고 값을 지정한 다음 해당 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-135">Here, a string variable is created, given a value, and then its value is changed.</span></span>  
  
 <span data-ttu-id="9f805-136">좀더 구체적으로 첫 번째 줄에서는 `String` 형식의 인스턴스를 만들고 `This string is immutable`값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-136">More specifically, in the first line, an instance of type `String` is created and given the value `This string is immutable`.</span></span> <span data-ttu-id="9f805-137">예제의 두 번째 줄에서는 새 인스턴스를 만들고 `Or is it?` 값을 지정합니다. 문자열 변수는 첫 번째 인스턴스에 대한 참조를 삭제하고 새 인스턴스에 대한 참조를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-137">In the second line of the example, a new instance is created and given the value `Or is it?`, and the string variable discards its reference to the first instance and stores a reference to the new instance.</span></span>  
  
 <span data-ttu-id="9f805-138">다른 내장 데이터 형식과 달리 `String`은 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-138">Unlike other intrinsic data types, `String` is a reference type.</span></span> <span data-ttu-id="9f805-139">참조 형식의 변수가 인수로 함수 또는 서브루틴에 전달되면 데이터가 저장되는 메모리 주소에 대한 참조가 문자열의 실제 값 대신 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-139">When a variable of reference type is passed as an argument to a function or subroutine, a reference to the memory address where the data is stored is passed instead of the actual value of the string.</span></span> <span data-ttu-id="9f805-140">따라서 이전 예제에서 변수의 이름은 동일하게 유지되지만 새 값을 보유하는 `String` 클래스의 다른 새 인스턴스를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="9f805-140">So in the previous example, the name of the variable remains the same, but it points to a new and different instance of the `String` class, which holds the new value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f805-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f805-141">See Also</span></span>  
 [<span data-ttu-id="9f805-142">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="9f805-142">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [<span data-ttu-id="9f805-143">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9f805-143">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="9f805-144">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9f805-144">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="9f805-145">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="9f805-145">Basic String Operations</span></span>](../../../../standard/base-types/basic-string-operations.md)
