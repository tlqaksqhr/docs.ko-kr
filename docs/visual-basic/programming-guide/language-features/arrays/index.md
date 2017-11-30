---
title: "Visual Basic의 배열"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Array
helpviewer_keywords:
- arrays [Visual Basic]
- Visual Basic, arrays
ms.assetid: dbf29737-b589-4443-bee6-a27588d9c67e
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 04deeccd19fd4edb3f2c88310d660eedf5c707d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="arrays-in-visual-basic"></a><span data-ttu-id="d14d7-102">Visual Basic의 배열</span><span class="sxs-lookup"><span data-stu-id="d14d7-102">Arrays in Visual Basic</span></span>
<span data-ttu-id="d14d7-103">배열은 초등학교에서 각 학년의 학생 수와 같이 서로 논리적으로 관련된 값의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-103">An array is a set of values that are logically related to each other, such as the number of students in each grade in a grammar school.</span></span>  <span data-ttu-id="d14d7-104">VBA(Visual Basic for Applications)의 배열에 대한 도움말을 찾으려는 경우 [언어 참조](https://msdn.microsoft.com/library/office/gg264383\(v=office.14\).aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d14d7-104">If you are looking for help on arrays in Visual Basic for Applications (VBA), see the [language reference](https://msdn.microsoft.com/library/office/gg264383\(v=office.14\).aspx).</span></span>  
  
 <span data-ttu-id="d14d7-105">배열을 사용하면 이러한 관련된 값을 동일한 이름으로 참조하고 인덱스 또는 아래 첨자라는 번호를 사용하여 서로 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-105">By using an array, you can refer to these related values by the same name, and use a number that’s called an index or subscript to tell them apart.</span></span> <span data-ttu-id="d14d7-106">개별 값을 배열의 요소라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-106">The individual values are called the elements of the array.</span></span> <span data-ttu-id="d14d7-107">인덱스 0부터 가장 높은 인덱스 값까지 연속됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-107">They’re contiguous from index 0 through the highest index value.</span></span>  
  
 <span data-ttu-id="d14d7-108">배열과 달리 단일 값을 포함하는 변수를 *스칼라* 변수라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-108">In contrast to an array, a variable that contain a single value is called a *scalar* variable.</span></span>  
  
 <span data-ttu-id="d14d7-109">설명하기 전에 몇 가지 빠른 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-109">Some quick examples before explanation:</span></span>  
  
```vb  
'Declare a single-dimension array of 5 values  
Dim numbers(4) As Integer   
  
'Declare a single-dimension array and set array element values  
Dim numbers = New Integer() {1, 2, 4, 8}  
  
'Redefine the size of an existing array retaining the current values  
ReDim Preserve numbers(15)  
  
'Redefine the size of an existing array, resetting the values  
ReDim numbers(15)  
  
'Declare a multi-dimensional array  
Dim matrix(5, 5) As Double  
  
'Declare a multi-dimensional array and set array element values  
Dim matrix = New Integer(4, 4) {{1, 2}, {3, 4}, {5, 6}, {7, 8}}  
  
'Declare a jagged array  
Dim sales()() As Double = New Double(11)() {}  
```  
  
 <span data-ttu-id="d14d7-110">**항목 내용**</span><span class="sxs-lookup"><span data-stu-id="d14d7-110">**In this topic**</span></span>  
  
-   [<span data-ttu-id="d14d7-111">1차원 배열의 배열 요소</span><span class="sxs-lookup"><span data-stu-id="d14d7-111">Array Elements in a Simple Array</span></span>](#BKMK_ArrayElements)  
  
-   [<span data-ttu-id="d14d7-112">배열 만들기</span><span class="sxs-lookup"><span data-stu-id="d14d7-112">Creating an Array</span></span>](#BKMK_CreatingAnArray)  
  
-   [<span data-ttu-id="d14d7-113">배열에 값 저장</span><span class="sxs-lookup"><span data-stu-id="d14d7-113">Storing Values in an Array</span></span>](#BKMK_StoringValues)  
  
-   [<span data-ttu-id="d14d7-114">배열을 초기 값으로 채우기</span><span class="sxs-lookup"><span data-stu-id="d14d7-114">Populating an Array with Initial Values</span></span>](#BKMK_Populating)  
  
    -   [<span data-ttu-id="d14d7-115">중첩된 배열 리터럴</span><span class="sxs-lookup"><span data-stu-id="d14d7-115">Nested Array Literals</span></span>](#BKMK_NestedArrayLiterals)  
  
-   [<span data-ttu-id="d14d7-116">배열 반복</span><span class="sxs-lookup"><span data-stu-id="d14d7-116">Iterating Through an Array</span></span>](#BKMK_Iterating)  
  
-   [<span data-ttu-id="d14d7-117">반환 값 및 매개 변수로 사용되는 배열</span><span class="sxs-lookup"><span data-stu-id="d14d7-117">Arrays as Return Values and Parameters</span></span>](#BKMK_ReturnValues)  
  
-   [<span data-ttu-id="d14d7-118">가변 배열</span><span class="sxs-lookup"><span data-stu-id="d14d7-118">Jagged Arrays</span></span>](#BKMK_JaggedArrays)  
  
-   [<span data-ttu-id="d14d7-119">길이가 0인 배열</span><span class="sxs-lookup"><span data-stu-id="d14d7-119">Zero-Length Arrays</span></span>](#BKMK_ZeroLength)  
  
-   [<span data-ttu-id="d14d7-120">배열 크기</span><span class="sxs-lookup"><span data-stu-id="d14d7-120">Array Size</span></span>](#BKMK_ArraySize)  
  
-   [<span data-ttu-id="d14d7-121">배열 형식 및 기타 형식</span><span class="sxs-lookup"><span data-stu-id="d14d7-121">Array Types and Other Types</span></span>](#BKMK_ArrayTypes)  
  
-   [<span data-ttu-id="d14d7-122">배열의 대안으로 사용되는 컬렉션</span><span class="sxs-lookup"><span data-stu-id="d14d7-122">Collections as an Alternative to Arrays</span></span>](#BKMK_Collections)  
  
##  <span data-ttu-id="d14d7-123"><a name="BKMK_ArrayElements"></a> 1차원 배열의 배열 요소</span><span class="sxs-lookup"><span data-stu-id="d14d7-123"><a name="BKMK_ArrayElements"></a> Array Elements in a Simple Array</span></span>  
 <span data-ttu-id="d14d7-124">다음 예제에서는 초등학교 각 학년의 학생 수를 보유하는 배열 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-124">The following example declares an array variable to hold the number of students in each grade in a grammar school.</span></span>  
  
 [!code-vb[VbVbalrArrays#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#2)]  
  
 <span data-ttu-id="d14d7-125">앞의 예제에서 `students` 배열은 7개 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-125">The array `students` in the preceding example contains seven elements.</span></span> <span data-ttu-id="d14d7-126">요소의 인덱스 범위는 0부터 6까지입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-126">The indexes of the elements range from 0 through 6.</span></span> <span data-ttu-id="d14d7-127">이 배열은 사용하는 것이 7개의 변수를 선언하는 것보다 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-127">Having this array is simpler than declaring seven variables.</span></span>  
  
 <span data-ttu-id="d14d7-128">다음 그림은 배열 `students`를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-128">The following illustration shows the array `students`.</span></span> <span data-ttu-id="d14d7-129">각 배열 요소에서</span><span class="sxs-lookup"><span data-stu-id="d14d7-129">For each element of the array:</span></span>  
  
-   <span data-ttu-id="d14d7-130">요소의 인덱스는 학년을 나타냅니다(인덱스 0은 유치원을 나타냄).</span><span class="sxs-lookup"><span data-stu-id="d14d7-130">The index of the element represents the grade (index 0 represents kindergarten).</span></span>  
  
-   <span data-ttu-id="d14d7-131">요소에 포함된 값은 해당 학년의 학생 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-131">The value that’s contained in the element represents the number of students in that grade.</span></span>  
  
 <span data-ttu-id="d14d7-132">![학생 수를 보여 주는 배열 그림](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexampleschool.gif "ArrayExampleSchool")</span><span class="sxs-lookup"><span data-stu-id="d14d7-132">![Picture of array showing numbers of students](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexampleschool.gif "ArrayExampleSchool")</span></span>  
<span data-ttu-id="d14d7-133">"학생" 배열의 요소</span><span class="sxs-lookup"><span data-stu-id="d14d7-133">Elements of the "students" array</span></span>  
  
 <span data-ttu-id="d14d7-134">다음 예제에서는 `students`배열의 첫 번째, 두 번째 및 마지막 요소를 참조하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-134">The following example shows how to refer to the first, second, and last element of the array `students`.</span></span>  
  
 [!code-vb[VbVbalrArrays#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#3)]  
  
 <span data-ttu-id="d14d7-135">인덱스 없이 배열 변수 이름만 사용하여 배열 전체를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-135">You can refer to the array as a whole by using just the array variable name without indexes.</span></span>  
  
 <span data-ttu-id="d14d7-136">앞의 예제에서 `students` 배열은 하나의 인덱스를 사용하며 1차원 배열로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-136">The array `students` in the preceding example uses one index and is said to be one-dimensional.</span></span> <span data-ttu-id="d14d7-137">둘 이상의 인덱스 또는 아래 첨자를 사용하는 배열을 다차원 배열이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-137">An array that uses more than one index or subscript is called multidimensional.</span></span> <span data-ttu-id="d14d7-138">자세한 내용은 이 항목의 나머지 부분과 [Array Dimensions in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d14d7-138">For more information, see the rest of this topic and [Array Dimensions in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
##  <span data-ttu-id="d14d7-139"><a name="BKMK_CreatingAnArray"></a> 배열 만들기</span><span class="sxs-lookup"><span data-stu-id="d14d7-139"><a name="BKMK_CreatingAnArray"></a> Creating an Array</span></span>  
 <span data-ttu-id="d14d7-140">여러 가지 방법으로 배열의 크기를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-140">You can define the size of an array several ways.</span></span> <span data-ttu-id="d14d7-141">다음 예제와 같이 배열을 선언할 때 크기를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-141">You can supply the size when the array is declared, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrArrays#12](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#12)]  
  
 <span data-ttu-id="d14d7-142">다음 예제와 같이 배열을 만들 때 `New` 절을 사용하여 배열의 크기를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-142">You can also use a `New` clause to supply the size of an array when it’s created, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrArrays#11](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#11)]  
  
 <span data-ttu-id="d14d7-143">기존 배열이 있는 경우 `Redim` 문을 사용하여 해당 크기를 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-143">If you have an existing array, you can redefine its size by using the `Redim` statement.</span></span> <span data-ttu-id="d14d7-144">`Redim` 문이 배열에 있는 값을 유지하도록 지정하거나 빈 배열을 만들도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-144">You can specify that the `Redim` statement should keep the values that are in the array, or you can specify that it create an empty array.</span></span> <span data-ttu-id="d14d7-145">다음 예제에서는 `Redim` 문을 사용하여 기존 배열의 크기를 수정하는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-145">The following example shows different uses of the `Redim` statement to modify the size of an existing array.</span></span>  
  
 [!code-vb[VbVbalrArrays#13](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#13)]  
  
 <span data-ttu-id="d14d7-146">자세한 내용은 [ReDim 문](../../../../visual-basic/language-reference/statements/redim-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d14d7-146">For more information, see [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md).</span></span>  
  
##  <span data-ttu-id="d14d7-147"><a name="BKMK_StoringValues"></a> 배열에 값 저장</span><span class="sxs-lookup"><span data-stu-id="d14d7-147"><a name="BKMK_StoringValues"></a> Storing Values in an Array</span></span>  
 <span data-ttu-id="d14d7-148">`Integer`형식의 인덱스를 사용하여 배열의 각 위치에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-148">You can access each location in an array by using an index of type `Integer`.</span></span> <span data-ttu-id="d14d7-149">괄호로 묶인 해당 인덱스를 통해 각 배열 위치를 참조하여 배열에 값을 저장하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-149">You can store and retrieve values in an array by referencing each array location by using its index enclosed in parentheses.</span></span> <span data-ttu-id="d14d7-150">다차원 배열에 대한 인덱스는 쉼표(,)로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-150">Indexes for multi-dimensional arrays are separated by commas (,).</span></span> <span data-ttu-id="d14d7-151">각 배열 차원에 대해 하나의 인덱스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-151">You need one index for each array dimension.</span></span> <span data-ttu-id="d14d7-152">다음 예제는 배열에 값을 저장하는 몇 가지 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-152">The following example shows some statements that store values in arrays.</span></span>  
  
 [!code-vb[VbVbalrArrays#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#5)]  
  
 <span data-ttu-id="d14d7-153">다음 예제는 배열에서 값을 가져오는 몇 가지 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-153">The following example shows some statements that get values from arrays.</span></span>  
  
 [!code-vb[VbVbalrArrays#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#6)]  
  
##  <span data-ttu-id="d14d7-154"><a name="BKMK_Populating"></a> 배열을 초기 값으로 채우기</span><span class="sxs-lookup"><span data-stu-id="d14d7-154"><a name="BKMK_Populating"></a> Populating an Array with Initial Values</span></span>  
 <span data-ttu-id="d14d7-155">배열 리터럴을 사용하여 초기 값 집합을 포함하는 배열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-155">By using an array literal, you can create an array that contains an initial set of values.</span></span> <span data-ttu-id="d14d7-156">배열 리터럴은 중괄호(`{}`)로 묶인 쉼표로 구분된 값 목록으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-156">An array literal consists of a list of comma-separated values that are enclosed in braces (`{}`).</span></span>  
  
 <span data-ttu-id="d14d7-157">배열 리터럴을 사용하여 배열을 만드는 경우 배열 형식을 제공하거나 형식 유추를 사용하여 배열 형식을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-157">When you create an array by using an array literal, you can either supply the array type or use type inference to determine the array type.</span></span> <span data-ttu-id="d14d7-158">다음 코드에서는 두 가지 옵션을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-158">The following code shows both options.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#3)]  
  
 <span data-ttu-id="d14d7-159">형식 유추를 사용하는 경우 배열 리터럴에 대해 제공된 값 목록의 기준 형식에 의해 배열 형식이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-159">When you use type inference, the type of the array is determined by the dominant type in the list of values that’s supplied for the array literal.</span></span> <span data-ttu-id="d14d7-160">기준 형식은 배열 리터럴의 다른 모든 형식이 확장될 수 있는 고유 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-160">The dominant type is a unique type to which all other types in the array literal can widen.</span></span> <span data-ttu-id="d14d7-161">이 고유 형식을 확인할 수 없는 경우 기준 형식은 배열의 다른 모든 형식이 축소될 수 있는 고유 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-161">If this unique type can’t be determined, the dominant type is the unique type to which all other types in the array can narrow.</span></span> <span data-ttu-id="d14d7-162">이러한 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-162">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="d14d7-163">예를 들어 배열 리터럴에 제공된 값 목록이 `Integer`, `Long`및 `Double`형식의 값을 포함하는 경우 결과 배열은 `Double`형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-163">For example, if the list of values that’s supplied to the array literal contains values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="d14d7-164">`Integer` 및 `Long` 은 둘 다 `Double`로만 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-164">Both `Integer` and `Long` widen only to `Double`.</span></span> <span data-ttu-id="d14d7-165">따라서 기준 형식은 `Double` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-165">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="d14d7-166">자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d14d7-166">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="d14d7-167">이러한 유추 규칙은 클래스 멤버에서 정의된 지역 변수인 배열에 대해 유추된 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-167">These inference rules apply to types that are inferred for arrays that are local variables that are defined in a class member.</span></span> <span data-ttu-id="d14d7-168">클래스 수준 변수를 만들 때 배열 리터럴을 사용할 수 있지만 클래스 수준에서 형식 유추를 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-168">Although you can use array literals when you create class-level variables, you can’t use type inference at the class level.</span></span> <span data-ttu-id="d14d7-169">따라서 클래스 수준에서 지정된 배열 리터럴은 배열 리터럴에 대해 제공된 값을 `Object`형식으로 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-169">As a result, array literals that are specified at the class level infer the values that are supplied for the array literal as type `Object`.</span></span>  
  
 <span data-ttu-id="d14d7-170">배열 리터럴을 사용하여 만든 배열의 요소 형식을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-170">You can explicitly specify the type of the elements in an array that’s created by using an array literal.</span></span> <span data-ttu-id="d14d7-171">이 경우 배열 리터럴의 값이 배열 요소의 형식으로 확장되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-171">In this case, the values in the array literal must widen to the type of the elements of the array.</span></span> <span data-ttu-id="d14d7-172">다음 코드 예제는 정수 목록에서 `Double` 형식의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-172">The following code example creates an array of type `Double` from a list of integers.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#4)]  
  
###  <span data-ttu-id="d14d7-173"><a name="BKMK_NestedArrayLiterals"></a> 중첩된 배열 리터럴</span><span class="sxs-lookup"><span data-stu-id="d14d7-173"><a name="BKMK_NestedArrayLiterals"></a> Nested Array Literals</span></span>  
 <span data-ttu-id="d14d7-174">중첩된 배열 리터럴을 사용하여 다차원 배열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-174">You can create a multidimensional array by using nested array literals.</span></span> <span data-ttu-id="d14d7-175">중첩된 배열 리터럴에는 결과 배열과 일치하는 차원 및 차원 수 또는 차수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-175">Nested array literals must have a dimension and number of dimensions, or rank, that’s consistent with the resulting array.</span></span> <span data-ttu-id="d14d7-176">다음 코드 예제는 배열 리터럴을 사용하여 정수의 2차원 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-176">The following code example creates a two-dimensional array of integers by using an array literal.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#7)]  
  
 <span data-ttu-id="d14d7-177">이전 예제에서 중첩된 배열 리터럴의 요소 수가 일치하지 않으면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-177">In the previous example, an error would occur if the number of elements in the nested array literals didn’t match.</span></span> <span data-ttu-id="d14d7-178">배열 변수를 2차원 이외의 배열로 명시적으로 선언한 경우에도 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-178">An error would also occur if you explicitly declared the array variable to be other than two-dimensional.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d14d7-179">내부 배열 리터럴을 괄호로 묶어 여러 차원의 중첩된 배열 리터럴을 제공하면 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-179">You can avoid an error when you supply nested array literals of different dimensions by enclosing the inner array literals in parentheses.</span></span> <span data-ttu-id="d14d7-180">다음 코드와 같이 괄호는 배열 리터럴 식이 계산되도록 강제하며, 결과 값이 외부 배열 리터럴과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-180">The parentheses force the array literal expression to be evaluated, and the resulting values are used with the outer array literal, as the following code shows.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#11](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#11)]  
  
 <span data-ttu-id="d14d7-181">중첩된 배열 리터럴을 사용하여 다차원 배열을 만드는 경우 형식 유추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-181">When you create a multidimensional array by using nested array literals, you can use type inference.</span></span> <span data-ttu-id="d14d7-182">형식 유추를 사용하는 경우 유추된 형식은 중첩 수준의 모든 배열 리터럴에 있는 모든 값에 대한 기준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-182">When you use type inference, the inferred type is the dominant type for all the values in all the array literals for a nesting level.</span></span> <span data-ttu-id="d14d7-183">다음 코드 예제는 `Double` 및 `Integer` 형식의 값에서 `Double`형식의 2차원 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-183">The following code example creates a two-dimensional array of type `Double` from values that are of type `Integer` and `Double`.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializers#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#8)]  
  
 <span data-ttu-id="d14d7-184">추가 예제를 보려면 [방법: Visual Basic에서 배열 변수 초기화](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d14d7-184">For additional examples, see [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md).</span></span>  
  
##  <span data-ttu-id="d14d7-185"><a name="BKMK_Iterating"></a> 배열 반복</span><span class="sxs-lookup"><span data-stu-id="d14d7-185"><a name="BKMK_Iterating"></a> Iterating Through an Array</span></span>  
 <span data-ttu-id="d14d7-186">배열을 반복하는 경우 가장 낮은 인덱스부터 가장 높은 인덱스까지 배열의 각 요소에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-186">When you iterate through an array, you access each element in the array from the lowest index to the highest index.</span></span>  
  
 <span data-ttu-id="d14d7-187">다음 예제에서는 [For...Next 문](../../../../visual-basic/language-reference/statements/for-next-statement.md)을 사용하여 1차원 배열을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-187">The following example iterates through a one-dimensional array by using the [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span> <span data-ttu-id="d14d7-188"><xref:System.Array.GetUpperBound%2A> 메서드는 인덱스가 가질 수 있는 가장 큰 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-188">The <xref:System.Array.GetUpperBound%2A> method returns the highest value that the index can have.</span></span> <span data-ttu-id="d14d7-189">가장 낮은 인덱스 값은 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-189">The lowest index value is always 0.</span></span>  
  
 [!code-vb[VbVbalrArrays#41](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#41)]  
  
 <span data-ttu-id="d14d7-190">다음 예제에서는 `For...Next` 문을 사용하여 다차원 배열을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-190">The following example iterates through a multidimensional array by using a `For...Next` statement.</span></span> <span data-ttu-id="d14d7-191"><xref:System.Array.GetUpperBound%2A> 메서드에는 차원을 지정하는 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-191">The <xref:System.Array.GetUpperBound%2A> method has a parameter that specifies the dimension.</span></span> <span data-ttu-id="d14d7-192">`GetUpperBound(0)` 는 첫 번째 차원에 대한 높은 인덱스 값을 반환하고 `GetUpperBound(1)` 는 두 번째 차원에 대한 높은 인덱스 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-192">`GetUpperBound(0)` returns the high index value for the first dimension, and `GetUpperBound(1)` returns the high index value for the second dimension.</span></span>  
  
 [!code-vb[VbVbalrArrays#42](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#42)]  
  
 <span data-ttu-id="d14d7-193">다음 예제에서는 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)을 사용하여 1차원 배열을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-193">The following example iterates through a one-dimensional array by using a [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
 [!code-vb[VbVbalrArrays#43](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#43)]  
  
 <span data-ttu-id="d14d7-194">다음 예제에서는 `For Each...Next` 문을 사용하여 다차원 배열을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-194">The following example iterates through a multidimensional array by using a `For Each...Next` statement.</span></span> <span data-ttu-id="d14d7-195">그러나 이전 예제와 같이 중첩된 `For…Next` 문을 `For Each…Next` 문 대신 사용하면 다차원 배열의 요소를 보다 효과적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-195">However, you have more control over the elements of a multidimensional array if you use a nested `For…Next` statement, as in a previous example, instead of a `For Each…Next` statement.</span></span>  
  
 [!code-vb[VbVbalrArrays#44](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#44)]  
  
##  <span data-ttu-id="d14d7-196"><a name="BKMK_ReturnValues"></a> 반환 값 및 매개 변수로 사용되는 배열</span><span class="sxs-lookup"><span data-stu-id="d14d7-196"><a name="BKMK_ReturnValues"></a> Arrays as Return Values and Parameters</span></span>  
 <span data-ttu-id="d14d7-197">`Function` 프로시저에서 배열을 반환하려면 배열 데이터 형식 및 차원 수를 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)의 반환 형식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-197">To return an array from a `Function` procedure, specify the array data type and the number of dimensions as the return type of the [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="d14d7-198">함수 내에서 동일한 데이터 형식 및 차원 수의 지역 배열 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-198">Within the function, declare a local array variable with same data type and number of dimensions.</span></span> <span data-ttu-id="d14d7-199">[Return 문](../../../../visual-basic/language-reference/statements/return-statement.md)에 지역 배열 변수를 괄호 없이 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-199">In the [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md), include the local array variable without parentheses.</span></span>  
  
 <span data-ttu-id="d14d7-200">`Sub` 또는 `Function` 프로시저에 대한 매개 변수로 배열을 지정하려면 지정된 데이터 형식 및 차원 수의 배열로 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-200">To specify an array as a parameter to a `Sub` or `Function` procedure, define the parameter as an array with a specified data type and number of dimensions.</span></span> <span data-ttu-id="d14d7-201">프로시저 호출에서 동일한 데이터 형식 및 차원 수의 배열 변수를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-201">In the call to the procedure, send an array variable with the same data type and number of dimensions.</span></span>  
  
 <span data-ttu-id="d14d7-202">다음 예제에서 `GetNumbers` 함수는 `Integer()`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-202">In the following example, the `GetNumbers` function returns an `Integer()`.</span></span> <span data-ttu-id="d14d7-203">이 배열 형식은 `Integer`형식의 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-203">This array type is a one dimensional array of type `Integer`.</span></span> <span data-ttu-id="d14d7-204">`ShowNumbers` 프로시저는 `Integer()` 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-204">The `ShowNumbers` procedure accepts an `Integer()` argument.</span></span>  
  
 [!code-vb[VbVbalrArrays#51](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#51)]  
  
 <span data-ttu-id="d14d7-205">다음 예제에서 `GetNumbersMultiDim` 함수는 `Integer(,)`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-205">In the following example, the `GetNumbersMultiDim` function returns an `Integer(,)`.</span></span> <span data-ttu-id="d14d7-206">이 배열 형식은 `Integer`형식의 2차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-206">This array type is a two dimensional array of type `Integer`.</span></span>  <span data-ttu-id="d14d7-207">`ShowNumbersMultiDim` 프로시저는 `Integer(,)` 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-207">The `ShowNumbersMultiDim` procedure accepts an `Integer(,)` argument.</span></span>  
  
 [!code-vb[VbVbalrArrays#52](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#52)]  
  
##  <span data-ttu-id="d14d7-208"><a name="BKMK_JaggedArrays"></a> 가변 배열</span><span class="sxs-lookup"><span data-stu-id="d14d7-208"><a name="BKMK_JaggedArrays"></a> Jagged Arrays</span></span>  
 <span data-ttu-id="d14d7-209">다른 배열을 요소로 포함하는 배열을 배열의 배열 또는 가변 배열이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-209">An array that holds other arrays as elements is known as an array of arrays or a jagged array.</span></span> <span data-ttu-id="d14d7-210">가변 배열 및 가변 배열의 각 요소에는 하나 이상의 차원이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-210">A jagged array and each element in a jagged array can have one or more dimensions.</span></span> <span data-ttu-id="d14d7-211">응용 프로그램의 데이터 구조가 2차원 배열이지만 사각형이 아닌 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-211">Sometimes the data structure in your application is two-dimensional but not rectangular.</span></span>  
  
 <span data-ttu-id="d14d7-212">다음 예제에는 각 요소가 일 배열인 월 배열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-212">The following example has an array of months, each element of which is an array of days.</span></span> <span data-ttu-id="d14d7-213">각 월의 일수가 서로 다르기 때문에 요소는 사각형 2차원 배열을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-213">Because different months have different numbers of days, the elements don’t form a rectangular two-dimensional array.</span></span> <span data-ttu-id="d14d7-214">따라서 다차원 배열 대신 가변 배열이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-214">Therefore, a jagged array is used instead of a multidimensional array.</span></span>  
  
 [!code-vb[VbVbalrArrays#21](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#21)]  
  
##  <span data-ttu-id="d14d7-215"><a name="BKMK_ZeroLength"></a> 길이가 0인 배열</span><span class="sxs-lookup"><span data-stu-id="d14d7-215"><a name="BKMK_ZeroLength"></a> Zero-Length Arrays</span></span>  
 <span data-ttu-id="d14d7-216">요소를 포함하지 않는 배열을 길이가 0인 배열이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-216">An array that contains no elements is also called a zero-length array.</span></span> <span data-ttu-id="d14d7-217">길이가 0인 배열을 저장하는 변수에는 `Nothing`값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-217">A variable that holds a zero-length array doesn’t have the value `Nothing`.</span></span> <span data-ttu-id="d14d7-218">요소가 없는 배열을 만들려면 다음 예제와 같이 배열의 차원 중 하나를 -1로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-218">To create an array that has no elements, declare one of the array's dimensions to be -1, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrArrays#14](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#14)]  
  
 <span data-ttu-id="d14d7-219">다음과 같은 경우 길이가 0인 배열을 만들어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-219">You might need to create a zero-length array under the following circumstances:</span></span>  
  
-   <span data-ttu-id="d14d7-220"><xref:System.NullReferenceException> 예외가 발생할 위험 없이 코드에서 <xref:System.Array> 또는 <xref:System.Array.Length%2A> 와 같은 <xref:System.Array.Rank%2A>클래스의 멤버에 액세스하거나 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 와 같은 <xref:Microsoft.VisualBasic.Information.UBound%2A>함수를 호출해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="d14d7-220">Without risking a <xref:System.NullReferenceException> exception, your code must access members of the <xref:System.Array> class, such as <xref:System.Array.Length%2A> or <xref:System.Array.Rank%2A>, or call a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function such as <xref:Microsoft.VisualBasic.Information.UBound%2A>.</span></span>  
  
-   <span data-ttu-id="d14d7-221">`Nothing` 을 특별한 경우로 확인할 필요가 없도록 하여 사용하는 코드를 보다 간단하게 유지하려는 경우</span><span class="sxs-lookup"><span data-stu-id="d14d7-221">You want to keep the consuming code simpler by not having to check for `Nothing` as a special case.</span></span>  
  
-   <span data-ttu-id="d14d7-222">코드가 하나 이상의 프로시저에 길이가 0인 배열을 전달해야 하거나 하나 이상의 프로시저에서 길이가 0인 배열을 반환하는 API(응용 프로그래밍 인터페이스)와 상호 작용하는 경우</span><span class="sxs-lookup"><span data-stu-id="d14d7-222">Your code interacts with an application programming interface (API) that either requires you to pass a zero-length array to one or more procedures or returns a zero-length array from one or more procedures.</span></span>  
  
##  <span data-ttu-id="d14d7-223"><a name="BKMK_ArraySize"></a> 배열 크기</span><span class="sxs-lookup"><span data-stu-id="d14d7-223"><a name="BKMK_ArraySize"></a> Array Size</span></span>  
 <span data-ttu-id="d14d7-224">배열 크기는 모든 차원의 길이 곱입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-224">The size of an array is the product of the lengths of all its dimensions.</span></span> <span data-ttu-id="d14d7-225">현재 배열에 포함된 요소의 총 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-225">It represents the total number of elements currently contained in the array.</span></span>  
  
 <span data-ttu-id="d14d7-226">다음 예제에서는 3차원 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-226">The following example declares a three-dimensional array.</span></span>  
  
```vb
Dim prices(3, 4, 5) As Long  
```  
  
 <span data-ttu-id="d14d7-227">`prices` 변수에서 배열의 전체 크기는 (3 + 1) x (4 + 1) x (5 + 1) = 120입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-227">The overall size of the array in variable `prices` is (3 + 1) x (4 + 1) x (5 + 1) = 120.</span></span>  
  
 <span data-ttu-id="d14d7-228"><xref:System.Array.Length%2A> 속성을 사용하여 배열의 크기를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-228">You can find the size of an array by using the <xref:System.Array.Length%2A> property.</span></span> <span data-ttu-id="d14d7-229"><xref:System.Array.GetLength%2A> 메서드를 사용하여 다차원 배열의 각 차원 길이를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-229">You can find the length of each dimension of a multi-dimensional array by using the <xref:System.Array.GetLength%2A> method.</span></span>  
  
 <span data-ttu-id="d14d7-230">새 배열 개체를 할당하거나 `ReDim` 문을 사용하여 배열 변수의 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-230">You can resize an array variable by assigning a new array object to it or by using the `ReDim` statement.</span></span>  
  
 <span data-ttu-id="d14d7-231">배열의 크기를 처리할 때 유의해야 하는 여러 가지 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-231">There are several things to keep in mind when dealing with the size of an array.</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="d14d7-232">차원 길이</span><span class="sxs-lookup"><span data-stu-id="d14d7-232">Dimension Length</span></span>|<span data-ttu-id="d14d7-233">각 차원의 인덱스는 0부터 시작하므로 0부터 상한까지의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-233">The index of each dimension is 0-based, which means it ranges from 0 through its upper bound.</span></span> <span data-ttu-id="d14d7-234">따라서 지정된 차원의 길이는 해당 차원에 대해 선언된 상한보다 1만큼 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-234">Therefore, the length of a given dimension is greater by 1 than the declared upper bound for that dimension.</span></span>|  
|<span data-ttu-id="d14d7-235">길이 제한</span><span class="sxs-lookup"><span data-stu-id="d14d7-235">Length Limits</span></span>|<span data-ttu-id="d14d7-236">배열의 각 차원 길이는 `Integer` 데이터 형식의 최대값, 즉 (2 ^ 31) - 1로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-236">The length of every dimension of an array is limited to the maximum value of the `Integer` data type, which is (2 ^ 31) - 1.</span></span> <span data-ttu-id="d14d7-237">그러나 배열의 총 크기는 시스템에서 사용 가능한 메모리에 의해서도 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-237">However, the total size of an array is also limited by the memory available on your system.</span></span> <span data-ttu-id="d14d7-238">사용 가능한 RAM 크기를 초과하는 배열을 초기화하려고 하면 공용 언어 런타임에서 <xref:System.OutOfMemoryException> 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-238">If you attempt to initialize an array that exceeds the amount of available RAM, the common language runtime throws an <xref:System.OutOfMemoryException> exception.</span></span>|  
|<span data-ttu-id="d14d7-239">크기 및 요소 크기</span><span class="sxs-lookup"><span data-stu-id="d14d7-239">Size and Element Size</span></span>|<span data-ttu-id="d14d7-240">배열의 크기는 해당 요소의 데이터 형식과 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-240">An array's size is independent of the data type of its elements.</span></span> <span data-ttu-id="d14d7-241">크기는 항상 저장소에서 사용하는 바이트 수가 아니라 요소의 총 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-241">The size always represents the total number of elements, not the number of bytes that they consume in storage.</span></span>|  
|<span data-ttu-id="d14d7-242">메모리 소비</span><span class="sxs-lookup"><span data-stu-id="d14d7-242">Memory Consumption</span></span>|<span data-ttu-id="d14d7-243">배열이 메모리에 저장되는 방법에 대해서는 어떠한 가정도 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-243">It is not safe to make any assumptions regarding how an array is stored in memory.</span></span> <span data-ttu-id="d14d7-244">저장소는 각 데이터 너비의 플랫폼마다 달라지므로 동일한 배열이 32비트 시스템보다 64비트 시스템에서 더 많은 메모리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-244">Storage varies on platforms of different data widths, so the same array can consume more memory on a 64-bit system than on a 32-bit system.</span></span> <span data-ttu-id="d14d7-245">시스템 구성에 따라 배열을 초기화할 때 CLR(공용 언어 런타임)에서 저장소를 할당하여 요소를 최대한 가깝게 압축하거나 모두 일반적인 하드웨어 경계에 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-245">Depending on system configuration when you initialize an array, the common language runtime (CLR) can assign storage either to pack elements as close together as possible, or to align them all on natural hardware boundaries.</span></span> <span data-ttu-id="d14d7-246">또한 배열의 제어 정보로 인해 저장소 오버헤드가 필요하며, 차원이 추가될 때마다 이 오버헤드가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-246">Also, an array requires a storage overhead for its control information, and this overhead increases with each added dimension.</span></span>|  
  
##  <span data-ttu-id="d14d7-247"><a name="BKMK_ArrayTypes"></a> 배열 형식 및 기타 형식</span><span class="sxs-lookup"><span data-stu-id="d14d7-247"><a name="BKMK_ArrayTypes"></a> Array Types and Other Types</span></span>  
 <span data-ttu-id="d14d7-248">각 배열에는 데이터 형식이 있지만 해당 요소의 데이터 형식과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-248">Every array has a data type, but it differs from the data type of its elements.</span></span> <span data-ttu-id="d14d7-249">모든 배열에 대한 단일 데이터 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-249">There is no single data type for all arrays.</span></span> <span data-ttu-id="d14d7-250">대신, 배열의 데이터 형식은 배열의 차원 수 또는 *차수*와 배열에 있는 요소의 데이터 형식에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-250">Instead, the data type of an array is determined by the number of dimensions, or *rank*, of the array, and the data type of the elements in the array.</span></span> <span data-ttu-id="d14d7-251">두 배열 변수는 동일한 차수이고 해당 요소가 동일한 데이터 형식인 경우에만 동일한 데이터 형식으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-251">Two array variables are considered to be of the same data type only when they have the same rank and their elements have the same data type.</span></span> <span data-ttu-id="d14d7-252">배열의 차원 길이는 배열 데이터 형식에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-252">The lengths of the dimensions in an array do not influence the array data type.</span></span>  
  
 <span data-ttu-id="d14d7-253">모든 배열은 <xref:System.Array?displayProperty=nameWithType> 클래스에서 상속되며 `Array` 형식으로 변수를 선언할 수 있지만, `Array` 형식의 배열을 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-253">Every array inherits from the <xref:System.Array?displayProperty=nameWithType> class, and you can declare a variable to be of type `Array`, but you cannot create an array of type `Array`.</span></span> <span data-ttu-id="d14d7-254">또한 [ReDim 문](../../../../visual-basic/language-reference/statements/redim-statement.md)은 `Array` 형식으로 선언된 변수에 대해 작업할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-254">Also, the [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md) cannot operate on a variable declared as type `Array`.</span></span> <span data-ttu-id="d14d7-255">이러한 이유 및 형식 안전성을 위해 앞의 예제에서 모든 배열을 `Integer` 와 같은 특정 형식으로 선언하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-255">For these reasons, and for type safety, it is advisable to declare every array as a specific type, such as `Integer` in the preceding example.</span></span>  
  
 <span data-ttu-id="d14d7-256">배열이나 해당 요소의 데이터 형식을 여러 가지 방법으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-256">You can find out the data type of either an array or its elements in several ways.</span></span>  
  
-   <span data-ttu-id="d14d7-257">변수에서 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 메서드를 호출하여 변수의 런타임 형식에 대한 <xref:System.Type> 개체를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-257">You can call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on the variable to receive a <xref:System.Type> object for the run-time type of the variable.</span></span> <span data-ttu-id="d14d7-258"><xref:System.Type> 개체는 해당 속성과 메서드에 광범위한 정보를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-258">The <xref:System.Type> object holds extensive information in its properties and methods.</span></span>  
  
-   <span data-ttu-id="d14d7-259"><xref:Microsoft.VisualBasic.Information.TypeName%2A> 함수에 변수를 전달하여 런타임 형식의 이름을 포함하는 `String` 을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-259">You can pass the variable to the <xref:Microsoft.VisualBasic.Information.TypeName%2A> function to receive a `String` containing the name of run-time type.</span></span>  
  
-   <span data-ttu-id="d14d7-260"><xref:Microsoft.VisualBasic.Information.VarType%2A> 함수에 변수를 전달하여 변수의 형식 분류를 나타내는 `VariantType` 값을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-260">You can pass the variable to the <xref:Microsoft.VisualBasic.Information.VarType%2A> function to receive a `VariantType` value representing the type classification of the variable.</span></span>  
  
 <span data-ttu-id="d14d7-261">다음 예제에서는 `TypeName` 함수를 호출하여 배열 형식과 배열의 요소 형식을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-261">The following example calls the `TypeName` function to determine the type of the array and the type of the elements in the array.</span></span> <span data-ttu-id="d14d7-262">배열 형식은 `Integer(,)` 이고 배열의 요소는 `Integer`형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-262">The array type is `Integer(,)` and the elements in the array are of type `Integer`.</span></span>  
  
 [!code-vb[VbVbalrArrays#15](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#15)]  
  
##  <span data-ttu-id="d14d7-263"><a name="BKMK_Collections"></a> 배열의 대안으로 사용되는 컬렉션</span><span class="sxs-lookup"><span data-stu-id="d14d7-263"><a name="BKMK_Collections"></a> Collections as an Alternative to Arrays</span></span>  
 <span data-ttu-id="d14d7-264">배열은 고정된 개수의 강력한 형식 개체를 만들고 작업하는 데 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-264">Arrays are most useful for creating and working with a fixed number of strongly typed objects.</span></span> <span data-ttu-id="d14d7-265">컬렉션은 개체 그룹에 대해 작업하는 보다 유연한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-265">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="d14d7-266">배열과 달리, 응용 프로그램의 요구가 변경됨에 따라 작업하는 개체 그룹이 동적으로 확장되거나 축소될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-266">Unlike arrays, the group of objects that you work with can grow and shrink dynamically as the needs of the application change.</span></span>  
  
 <span data-ttu-id="d14d7-267">배열 크기를 변경해야 하는 경우 [ReDim 문](../../../../visual-basic/language-reference/statements/redim-statement.md)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-267">If you need to change the size of an array, you must use the [ReDim Statement](../../../../visual-basic/language-reference/statements/redim-statement.md).</span></span> <span data-ttu-id="d14d7-268">이렇게 하면 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 새 배열을 만들고 이전 배열을 삭제하도록 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-268">When you do this, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] creates a new array and releases the previous array for disposal.</span></span> <span data-ttu-id="d14d7-269">이 경우 실행 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-269">This takes execution time.</span></span> <span data-ttu-id="d14d7-270">따라서 작업하는 항목 수가 자주 변경되거나 필요한 항목의 최대 개수를 예측할 수 없는 경우 컬렉션을 사용하여 성능을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-270">Therefore, if the number of items you are working with changes frequently, or you cannot predict the maximum number of items you need, you might obtain better performance using a collection.</span></span>  
  
 <span data-ttu-id="d14d7-271">일부 컬렉션의 경우 키를 사용하여 개체를 신속하게 검색할 수 있도록 컬렉션에 추가하는 모든 개체에 키를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-271">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>  
  
 <span data-ttu-id="d14d7-272">컬렉션에 단일 데이터 형식의 요소만 포함된 경우 <xref:System.Collections.Generic?displayProperty=nameWithType> 네임스페이스의 클래스 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-272">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="d14d7-273">제네릭 컬렉션은 다른 데이터 형식을 추가할 수 없도록 형식 안전성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-273">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="d14d7-274">제네릭 컬렉션에서 요소를 검색하는 경우 해당 데이터 형식을 결정하거나 변환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-274">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>  
  
 <span data-ttu-id="d14d7-275">항목 컬렉션에 대한 자세한 내용은 [컬렉션](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d14d7-275">For more information about collections, see [Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b).</span></span>  
  
### <a name="example"></a><span data-ttu-id="d14d7-276">예제</span><span class="sxs-lookup"><span data-stu-id="d14d7-276">Example</span></span>  
 <span data-ttu-id="d14d7-277">다음 예제에서는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 제네릭 클래스 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>을 사용하여 `Customer` 개체의 목록 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-277">The following example uses the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] generic class <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> to create a list collection of `Customer` objects.</span></span>  
  
 [!code-vb[VbVbalrArrays#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#1)]  
  
 <span data-ttu-id="d14d7-278">`CustomerFile` 컬렉션의 선언은 `Customer`형식의 요소만 포함될 수 있도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-278">The declaration of the `CustomerFile` collection specifies that it can contain elements only of type `Customer`.</span></span> <span data-ttu-id="d14d7-279">또한 200개 요소의 초기 용량을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-279">It also provides for an initial capacity of 200 elements.</span></span> <span data-ttu-id="d14d7-280">`AddNewCustomer` 프로시저는 새 요소의 유효성을 확인하고 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-280">The procedure `AddNewCustomer` checks the new element for validity and then adds it to the collection.</span></span> <span data-ttu-id="d14d7-281">`PrintCustomers` 프로시저는 `For Each` 루프를 사용하여 컬렉션을 트래버스하고 해당 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-281">The procedure `PrintCustomers` uses a `For Each` loop to traverse the collection and display its elements.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="d14d7-282">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d14d7-282">Related Topics</span></span>  
  
|<span data-ttu-id="d14d7-283">용어</span><span class="sxs-lookup"><span data-stu-id="d14d7-283">Term</span></span>|<span data-ttu-id="d14d7-284">정의</span><span class="sxs-lookup"><span data-stu-id="d14d7-284">Definition</span></span>|  
|----------|----------------|  
|[<span data-ttu-id="d14d7-285">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d14d7-285">Array Dimensions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)|<span data-ttu-id="d14d7-286">배열의 차수 및 차원을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-286">Explains rank and dimensions in arrays.</span></span>|  
|[<span data-ttu-id="d14d7-287">방법: Visual Basic에서 배열 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="d14d7-287">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)|<span data-ttu-id="d14d7-288">배열에 초기 값을 채우는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-288">Describes how to populate arrays with initial values.</span></span>|  
|[<span data-ttu-id="d14d7-289">방법: Visual Basic에서 배열 정렬</span><span class="sxs-lookup"><span data-stu-id="d14d7-289">How to: Sort An Array in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-sort-an-array.md)|<span data-ttu-id="d14d7-290">배열의 요소를 사전순으로 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-290">Shows how to sort the elements of an array alphabetically.</span></span>|  
|[<span data-ttu-id="d14d7-291">방법: 한 배열에 다른 배열 할당</span><span class="sxs-lookup"><span data-stu-id="d14d7-291">How to: Assign One Array to Another Array</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-assign-one-array-to-another-array.md)|<span data-ttu-id="d14d7-292">다른 배열 변수에 배열을 할당하는 규칙 및 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-292">Describes the rules and steps for assigning an array to another array variable.</span></span>|  
|[<span data-ttu-id="d14d7-293">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d14d7-293">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)|<span data-ttu-id="d14d7-294">배열에서 작업할 때 발생할 수 있는 몇 가지 일반적인 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d14d7-294">Discusses some common problems that arise when working with arrays.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d14d7-295">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d14d7-295">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="d14d7-296">Dim 문</span><span class="sxs-lookup"><span data-stu-id="d14d7-296">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="d14d7-297">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="d14d7-297">ReDim Statement</span></span>](../../../../visual-basic/language-reference/statements/redim-statement.md)
