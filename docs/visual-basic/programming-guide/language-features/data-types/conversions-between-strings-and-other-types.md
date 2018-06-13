---
title: 문자열과 다른 형식 사이의 변환(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 40a28d664bc6ed3d094ccc7c342d6411fe88fd7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650571"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="a5d4d-102">문자열과 다른 형식 사이의 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5d4d-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="a5d4d-103">숫자, 변환할 수 있습니다 `Boolean`, 또는 날짜/시간 값을 한 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="a5d4d-104">반대 방향으로 변환할 수 있습니다-숫자에는 문자열 값에서 `Boolean`, 또는 `Date` -문자열의 내용을 대상 데이터 형식의 유효한 값으로 해석 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="a5d4d-105">그렇지 않을 경우 런타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="a5d4d-106">어느 방향으로든에서 이러한 모든 할당에 대 한 변환은 축소 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="a5d4d-107">형식 변환 키워드를 사용 해야 (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, 및 `CType`).</span><span class="sxs-lookup"><span data-stu-id="a5d4d-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="a5d4d-108"><xref:Microsoft.VisualBasic.Strings.Format%2A> 및 <xref:Microsoft.VisualBasic.Conversion.Val%2A> 함수 문자열 및 숫자 간의 변환에 대 한 추가 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="a5d4d-109">클래스 또는 구조체를 정의 하는 경우 간의 형식 변환 연산자를 정의할 수 있습니다 `String` 및 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="a5d4d-110">자세한 내용은 참조 [하는 방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="a5d4d-111">숫자를 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="a5d4d-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="a5d4d-112">사용할 수는 `Format` 뿐만 아니라 적절 한 숫자를 포함할 수 있는 서식이 지정된 된 문자열에 숫자를 변환할 기능 하지만 통화 기호 등의 기호 형식 지정 (같은 `$`), 1000 단위 구분 기호 또는 *자릿수 구분 기호* (같은 `,`), 및 소수 구분 기호 (같은 `.`).</span><span class="sxs-lookup"><span data-stu-id="a5d4d-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="a5d4d-113">`Format` 에 따라 적절 한 기호를 자동으로 사용 하 여 **국가별 옵션** Windows에 지정 된 설정을 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="a5d4d-114">연결 (`&`) 연산자는 다음 예제와 같이 암시적으로 숫자를 문자열로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="a5d4d-115">숫자의 문자열 변환</span><span class="sxs-lookup"><span data-stu-id="a5d4d-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="a5d4d-116">사용할 수는 `Val` 함수를 명시적으로 문자열의 자릿수를 숫자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="a5d4d-117">`Val` 숫자, 공백, 탭, 줄 바꿈 또는 마침표 이외의 문자에 도달할 때까지 문자열을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="a5d4d-118">시퀀스는 "& O" 및 "& H" 번호 시스템의 기본을 변경 하 고 검색을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="a5d4d-119">읽기를 중단할 때까지 `Val` 모든 해당 문자는 숫자 값으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="a5d4d-120">다음 문은 값을 반환 하는 예를 들어 `141.825`합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="a5d4d-121">Visual Basic 문자열을 숫자 값을 사용 하 여는 **국가별 옵션** Windows에 지정 된 설정을 **제어판** 1000 단위를 해석 하 구분 기호, 소수 구분 기호 및 통화 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="a5d4d-122">즉, 설정 해도 다른 하나는 변환이 성공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="a5d4d-123">예를 들어 `"$14.20"` 이 허용 되는 영어 (미국) 로캘을 있지만 프랑스어 로캘에서에 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d4d-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d4d-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5d4d-124">See Also</span></span>  
 [<span data-ttu-id="a5d4d-125">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="a5d4d-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="a5d4d-126">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="a5d4d-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="a5d4d-127">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="a5d4d-127">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="a5d4d-128">방법: Visual Basic에서 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="a5d4d-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="a5d4d-129">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="a5d4d-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [<span data-ttu-id="a5d4d-130">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a5d4d-130">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="a5d4d-131">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="a5d4d-131">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="a5d4d-132">.NET Framework 기반의 국가별 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="a5d4d-132">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
