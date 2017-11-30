---
title: "배열 변환(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 40dc9805157dd0bc991ca2375c3436aa6b6e09a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="0db9b-102">배열 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0db9b-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="0db9b-103">다음 조건이 충족 되는 배열 형식이 다른 배열 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
-   <span data-ttu-id="0db9b-104">**동일한 차수입니다.**</span><span class="sxs-lookup"><span data-stu-id="0db9b-104">**Equal Rank.**</span></span> <span data-ttu-id="0db9b-105">두 배열의 차수가 같아야, 즉, 동일한 차원 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="0db9b-106">그러나 각 차원의 길이 같이 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
-   <span data-ttu-id="0db9b-107">**요소 데이터 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="0db9b-107">**Element Data Type.**</span></span> <span data-ttu-id="0db9b-108">데이터 형식의 두 배열의 요소에는 참조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="0db9b-109">변환할 수 없습니다는 `Integer` 배열을 `Long` 배열 또는 심지어는 `Object` 하나 이상 값 형식이 포함 되어 있으므로 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="0db9b-110">자세한 내용은 참조 [값 형식과 참조 형식이](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
-   <span data-ttu-id="0db9b-111">**변환 가능성입니다.**</span><span class="sxs-lookup"><span data-stu-id="0db9b-111">**Convertibility.**</span></span> <span data-ttu-id="0db9b-112">두 배열의 요소 형식 간에 변환, 확대 또는 축소 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="0db9b-113">이 요구 사항은 실패 하는 예제 변환을 시도 하는 사이 `String` 에서 파생 된 클래스의 배열 및 배열 <xref:System.Attribute?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0db9b-114">이 두 가지 종류로 아무 공통으로 있고 서로 간에 어떤 종류의 변환 작업 없이 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="0db9b-115">다른 배열 형식 변환은 확대 또는 축소 되는 각 요소의 변환 확대 또는 축소 여부에 따라 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="0db9b-116">자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0db9b-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="0db9b-117">개체 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="0db9b-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="0db9b-118">선언 하는 경우는 `Object` 배열 요소 형식은 초기화 하지 않고 `Object` 으로 초기화 되지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="0db9b-119">특정 클래스의 배열에 설정 하는 경우 해당 클래스의 형식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="0db9b-120">그러나 내부 형식은 여전히 `Object`, 이후에 다른 배열을 관련 없는 클래스를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="0db9b-121">모든 클래스에서 파생 되므로 `Object`, 다른 클래스는 클래스에서 배열의 요소 형식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="0db9b-122">다음 예제에서는 변환 된 항목이 없고 형식 간의 `student` 및 `String`, 둘 다에서 파생 되지만 `Object`이므로 모든 할당은 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="0db9b-123">내부 배열 형식</span><span class="sxs-lookup"><span data-stu-id="0db9b-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="0db9b-124">특정 클래스에 배열을으로 원래 선언 내부 요소 형식은 해당는 해당 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="0db9b-125">이후에 값을 설정 하면 다른 클래스의 배열에는 두 클래스 간에 변환 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="0db9b-126">다음 예에서 `students` 는 `student` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="0db9b-127">변환 작업 없이 사이 존재 하므로 `String` 및 `student`, 마지막 문은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="0db9b-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="0db9b-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0db9b-128">See Also</span></span>  
 [<span data-ttu-id="0db9b-129">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0db9b-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="0db9b-130">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="0db9b-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="0db9b-131">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="0db9b-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="0db9b-132">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="0db9b-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="0db9b-133">방법: Visual Basic에서 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="0db9b-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="0db9b-134">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0db9b-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="0db9b-135">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="0db9b-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="0db9b-136">배열</span><span class="sxs-lookup"><span data-stu-id="0db9b-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
