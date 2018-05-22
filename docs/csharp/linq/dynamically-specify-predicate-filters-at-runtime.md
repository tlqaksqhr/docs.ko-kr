---
title: 런타임에 동적으로 조건자 필터 지정
description: 런타임에 동적으로 조건자 필터를 지정하는 방법
ms.date: 12/1/2016
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.openlocfilehash: fa3426a513758d8c30bf381ec480b9b8d12a5f81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="22add-103">런타임에 동적으로 조건자 필터 지정</span><span class="sxs-lookup"><span data-stu-id="22add-103">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="22add-104">경우에 따라 `where` 절의 소스 요소에 적용해야 하는 조건자 수를 런타임할때 까지 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22add-104">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="22add-105">다음 예제와 같이 여러 조건자 필터를 동적으로 지정하는 한 가지 방법은 <xref:System.Linq.Enumerable.Contains%2A> 메서드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="22add-105">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="22add-106">이 예제는 두 가지 방법으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="22add-106">The example is constructed in two ways.</span></span> <span data-ttu-id="22add-107">먼저 프로그램에서 제공되는 값을 필터링하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-107">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="22add-108">그런 다음 런타임에 제공된 입력을 사용하여 프로젝트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-108">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="22add-109">Contains 메서드를 사용하여 필터링하려면</span><span class="sxs-lookup"><span data-stu-id="22add-109">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="22add-110">새 콘솔 응용 프로그램을 열고 이름을 `PredicateFilters`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-110">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="22add-111">[개체의 컬렉션 쿼리](query-a-collection-of-objects.md)에서 `StudentClass` 클래스를 복사하여 `Program` 클래스 아래의 `PredicateFilters` 네임스페이스에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="22add-111">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="22add-112">`StudentClass`는 `Student` 개체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-112">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="22add-113">`StudentClass`에서 `Main` 메서드를 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-113">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="22add-114">`Program` 클래스를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="22add-114">Replace class `Program` with the following code.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]  
  
5.  <span data-ttu-id="22add-115">`ids`의 선언 아래에서 `DynamicPredicates` 클래스의 `Main` 메서드에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-115">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="22add-116">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-116">Run the project.</span></span>  
  
7.  <span data-ttu-id="22add-117">다음 출력이 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="22add-117">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="22add-118">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="22add-118">Garcia: 114</span></span>  
  
     <span data-ttu-id="22add-119">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="22add-119">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="22add-120">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="22add-120">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="22add-121">다음 단계로 프로젝트를 다시 실행합니다. 이번에는 `ids` 배열 대신 런타임에 입력된 입력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-121">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="22add-122">`Main` 메서드에서 `QueryByID(ids)`를 `QueryByID(args)`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-122">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="22add-123">명령줄 인수 `122 117 120 115`를 사용하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-123">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="22add-124">프로젝트가 실행되면 해당 값은 `Main` 메서드의 매개 변수인 `args`의 요소가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22add-124">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="22add-125">다음 출력이 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="22add-125">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="22add-126">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="22add-126">Adams: 120</span></span>  
  
     <span data-ttu-id="22add-127">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="22add-127">Feng: 117</span></span>  
  
     <span data-ttu-id="22add-128">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="22add-128">Garcia: 115</span></span>  
  
     <span data-ttu-id="22add-129">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="22add-129">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="22add-130">switch 문을 사용하여 필터링하려면</span><span class="sxs-lookup"><span data-stu-id="22add-130">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="22add-131">`switch` 문을 사용하여 미리 결정된 대체 쿼리 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22add-131">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="22add-132">다음 예제에서 `studentQuery`는 런타임에 지정되는 성적 수준 또는 학년에 따라 다른 `where` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-132">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="22add-133">다음 메서드를 복사하여 `DynamicPredicates` 클래스에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="22add-133">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     [!code-csharp[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]  
  
3.  <span data-ttu-id="22add-134">`Main` 메서드에서 `QueryByID` 호출을 `QueryByYear(args[0])` 호출로 바꿔 `args` 배열의 첫 번째 요소를 인수로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-134">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="22add-135">1에서 4 사이의 정수 값인 명령줄 인수를 사용하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="22add-135">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="22add-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22add-136">See Also</span></span>  
 [<span data-ttu-id="22add-137">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="22add-137">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="22add-138">where 절</span><span class="sxs-lookup"><span data-stu-id="22add-138">where clause</span></span>](../language-reference/keywords/where-clause.md)
