---
title: "런타임에 동적으로 조건자 필터 지정"
description: "런타임에 동적으로 조건자 필터를 지정하는 방법"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 90238470-0767-497c-916c-52d0d16845e0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e724428bce09e2b2fa20b9391ad131424e16413
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="dynamically-specify-predicate-filters-at-runtime"></a><span data-ttu-id="7a744-104">런타임에 동적으로 조건자 필터 지정</span><span class="sxs-lookup"><span data-stu-id="7a744-104">Dynamically specify predicate filters at runtime</span></span>

<span data-ttu-id="7a744-105">경우에 따라 `where` 절의 소스 요소에 적용해야 하는 조건자 수를 런타임할때 까지 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-105">In some cases you do not know until run time how many predicates you have to apply to source elements in the `where` clause.</span></span> <span data-ttu-id="7a744-106">다음 예제와 같이 여러 조건자 필터를 동적으로 지정하는 한 가지 방법은 <xref:System.Linq.Enumerable.Contains%2A> 메서드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-106">One way to dynamically specify multiple predicate filters is to use the <xref:System.Linq.Enumerable.Contains%2A> method, as shown in the following example.</span></span> <span data-ttu-id="7a744-107">이 예제는 두 가지 방법으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-107">The example is constructed in two ways.</span></span> <span data-ttu-id="7a744-108">먼저 프로그램에서 제공되는 값을 필터링하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-108">First, the project is run by filtering on values that are provided in the program.</span></span> <span data-ttu-id="7a744-109">그런 다음 런타임에 제공된 입력을 사용하여 프로젝트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-109">Then the project is run again by using input provided at run time.</span></span>  
  
## <a name="to-filter-by-using-the-contains-method"></a><span data-ttu-id="7a744-110">Contains 메서드를 사용하여 필터링하려면</span><span class="sxs-lookup"><span data-stu-id="7a744-110">To filter by using the Contains method</span></span>  
  
1.  <span data-ttu-id="7a744-111">새 콘솔 응용 프로그램을 열고 이름을 `PredicateFilters`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-111">Open a new console application and name it `PredicateFilters`.</span></span>  
  
2.  <span data-ttu-id="7a744-112">[개체의 컬렉션 쿼리](query-a-collection-of-objects.md)에서 `StudentClass` 클래스를 복사하여 `Program` 클래스 아래의 `PredicateFilters` 네임스페이스에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-112">Copy the `StudentClass` class from [Query a collection of objects](query-a-collection-of-objects.md) and paste it into namespace `PredicateFilters` underneath class `Program`.</span></span> <span data-ttu-id="7a744-113">`StudentClass`는 `Student` 개체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-113">`StudentClass` provides a list of `Student` objects.</span></span>  
  
3.  <span data-ttu-id="7a744-114">`StudentClass`에서 `Main` 메서드를 주석으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-114">Comment out the `Main` method in `StudentClass`.</span></span>  
  
4.  <span data-ttu-id="7a744-115">`Program` 클래스를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-115">Replace class `Program` with the following code.</span></span>  
  
     <span data-ttu-id="7a744-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7a744-116">[!code-cs[csProgGuideLINQ#26](../../../samples/snippets/csharp/concepts/linq/how-to-dynamically-specify-predicate-filters-at-runtime_1.cs)]</span></span>  
  
5.  <span data-ttu-id="7a744-117">`ids`의 선언 아래에서 `DynamicPredicates` 클래스의 `Main` 메서드에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-117">Add the following line to the `Main` method in class `DynamicPredicates`, under the declaration of `ids`.</span></span>  
  
     ```csharp
     QueryById(ids);
     ```

6.  <span data-ttu-id="7a744-118">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-118">Run the project.</span></span>  
  
7.  <span data-ttu-id="7a744-119">다음 출력이 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-119">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="7a744-120">Garcia: 114</span><span class="sxs-lookup"><span data-stu-id="7a744-120">Garcia: 114</span></span>  
  
     <span data-ttu-id="7a744-121">O'Donnell: 112</span><span class="sxs-lookup"><span data-stu-id="7a744-121">O'Donnell: 112</span></span>  
  
     <span data-ttu-id="7a744-122">Omelchenko: 111</span><span class="sxs-lookup"><span data-stu-id="7a744-122">Omelchenko: 111</span></span>  
  
8.  <span data-ttu-id="7a744-123">다음 단계로 프로젝트를 다시 실행합니다. 이번에는 `ids` 배열 대신 런타임에 입력된 입력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-123">The next step is to run the project again, this time by using input entered at run time instead of array `ids`.</span></span> <span data-ttu-id="7a744-124">`Main` 메서드에서 `QueryByID(ids)`를 `QueryByID(args)`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-124">Change `QueryByID(ids)` to `QueryByID(args)` in the `Main` method.</span></span>  
  
9. <span data-ttu-id="7a744-125">명령줄 인수 `122 117 120 115`를 사용하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-125">Run the project with the command line arguments `122 117 120 115`.</span></span> <span data-ttu-id="7a744-126">프로젝트가 실행되면 해당 값은 `Main` 메서드의 매개 변수인 `args`의 요소가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-126">When the project is run, those values become elements of `args`, the parameter of the `Main` method..</span></span>  
  
10. <span data-ttu-id="7a744-127">다음 출력이 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-127">The following output is displayed in a console window:</span></span>  
  
     <span data-ttu-id="7a744-128">Adams: 120</span><span class="sxs-lookup"><span data-stu-id="7a744-128">Adams: 120</span></span>  
  
     <span data-ttu-id="7a744-129">Feng: 117</span><span class="sxs-lookup"><span data-stu-id="7a744-129">Feng: 117</span></span>  
  
     <span data-ttu-id="7a744-130">Garcia: 115</span><span class="sxs-lookup"><span data-stu-id="7a744-130">Garcia: 115</span></span>  
  
     <span data-ttu-id="7a744-131">Tucker: 122</span><span class="sxs-lookup"><span data-stu-id="7a744-131">Tucker: 122</span></span>  
  
## <a name="to-filter-by-using-a-switch-statement"></a><span data-ttu-id="7a744-132">switch 문을 사용하여 필터링하려면</span><span class="sxs-lookup"><span data-stu-id="7a744-132">To filter by using a switch statement</span></span>  
  
1.  <span data-ttu-id="7a744-133">`switch` 문을 사용하여 미리 결정된 대체 쿼리 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-133">You can use a `switch` statement to select among predetermined alternative queries.</span></span> <span data-ttu-id="7a744-134">다음 예제에서 `studentQuery`는 런타임에 지정되는 성적 수준 또는 학년에 따라 다른 `where` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-134">In the following example, `studentQuery` uses a different `where` clause depending on which grade level, or year, is specified at run time.</span></span>  
  
2.  <span data-ttu-id="7a744-135">다음 메서드를 복사하여 `DynamicPredicates` 클래스에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-135">Copy the following method and paste it into class `DynamicPredicates`.</span></span>  
  
     <span data-ttu-id="7a744-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7a744-136">[!code-cs[csProgGuideLINQ#27](../../../samples/snippets/csharp/concepts/linq//how-to-dynamically-specify-predicate-filters-at-runtime_2.cs)]</span></span>  
  
3.  <span data-ttu-id="7a744-137">`Main` 메서드에서 `QueryByID` 호출을 `QueryByYear(args[0])` 호출로 바꿔 `args` 배열의 첫 번째 요소를 인수로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-137">In the `Main` method, replace the call to `QueryByID` with the following call, which sends the first element from the `args` array as its argument: `QueryByYear(args[0])`.</span></span>  
  
4.  <span data-ttu-id="7a744-138">1에서 4 사이의 정수 값인 명령줄 인수를 사용하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a744-138">Run the project with a command line argument of an integer value between 1 and 4.</span></span>  
  
 
## <a name="see-also"></a><span data-ttu-id="7a744-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a744-139">See Also</span></span>  
 <span data-ttu-id="7a744-140">[LINQ 쿼리 식](index.md) </span><span class="sxs-lookup"><span data-stu-id="7a744-140">[LINQ Query Expressions](index.md) </span></span>  
 [<span data-ttu-id="7a744-141">where 절</span><span class="sxs-lookup"><span data-stu-id="7a744-141">where clause</span></span>](../language-reference/keywords/where-clause.md)

