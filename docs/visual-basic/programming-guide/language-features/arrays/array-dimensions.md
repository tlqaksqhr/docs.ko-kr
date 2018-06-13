---
title: Array Dimensions in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: cf295288dd034d744dceb71b5c58278be5cc2a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651758"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="11146-102">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11146-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="11146-103">A *차원* 은 방향 배열 요소의 사양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11146-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="11146-104">각 날짜의 월에 대 한 총 판매를 포함 하는 배열에는 1 차원 (해당 월의 일)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11146-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="11146-105">총 판매액이 들어 부서별로 각 날짜의 월에 대 한 배열 차원이 두 개 (부서 번호 및 월의 일).</span><span class="sxs-lookup"><span data-stu-id="11146-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="11146-106">배열의 차원 수 라고 해당 *순위*합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11146-107">사용할 수는 <xref:System.Array.Rank%2A> 배열이 차원 수를 결정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="11146-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="11146-108">차원 작업</span><span class="sxs-lookup"><span data-stu-id="11146-108">Working with Dimensions</span></span>  
 <span data-ttu-id="11146-109">배열의 요소를 제공 하 여 지정 된 *인덱스* 또는 *아래 첨자* 배열의 각 차원에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="11146-110">요소는 해당 차원에 대 한 가장 높은 인덱스를 인덱스 0에서에서 각 차원에 따라 연속입니다.</span><span class="sxs-lookup"><span data-stu-id="11146-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="11146-111">다음 그림의 순위에 다른 배열 개념적 구조를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="11146-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="11146-112">각 요소는 그림에 액세스 하는 인덱스 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11146-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="11146-113">예를 들어 2 차원 배열의 두 번째 행의 첫 번째 요소 인덱스를 지정 하 여 액세스할 수 있습니다 `(1, 0)`합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 <span data-ttu-id="11146-114">![하나는 그래픽 다이어그램&#45;차원 배열](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span><span class="sxs-lookup"><span data-stu-id="11146-114">![Graphic diagram of one&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span></span>  
<span data-ttu-id="11146-115">1 차원 배열</span><span class="sxs-lookup"><span data-stu-id="11146-115">One-dimensional array</span></span>  
  
 <span data-ttu-id="11146-116">![2의 그래픽 다이어그램&#45;차원 배열](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span><span class="sxs-lookup"><span data-stu-id="11146-116">![Graphic diagram of two&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span></span>  
<span data-ttu-id="11146-117">2 차원 배열</span><span class="sxs-lookup"><span data-stu-id="11146-117">Two-dimensional array</span></span>  
  
 <span data-ttu-id="11146-118">![세 개의의 그래픽 다이어그램&#45;차원 배열](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span><span class="sxs-lookup"><span data-stu-id="11146-118">![Graphic diagram of three&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span></span>  
<span data-ttu-id="11146-119">3 차원 배열</span><span class="sxs-lookup"><span data-stu-id="11146-119">Three-dimensional array</span></span>  
  
### <a name="one-dimension"></a><span data-ttu-id="11146-120">차원이 두 개</span><span class="sxs-lookup"><span data-stu-id="11146-120">One Dimension</span></span>  
 <span data-ttu-id="11146-121">많은 배열을는 각 나이 사용자 수와 같이 차원이 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-121">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="11146-122">요소를 지정 하는 유일한 요구 사항은 나가는 해당 요소의 개수를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-122">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="11146-123">따라서 이러한 배열 인덱스는 하나만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-123">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="11146-124">다음 예제에서는 선언 보유 하는 변수는 *1 차원 배열* age의 나가 120 사이의 0에 대 한 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-124">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="11146-125">2 차원</span><span class="sxs-lookup"><span data-stu-id="11146-125">Two Dimensions</span></span>  
 <span data-ttu-id="11146-126">일부 배열은 있는 캠퍼스 각 건물의 각 층에서 사무실의 수와 같은 두 개의 차원입니다.</span><span class="sxs-lookup"><span data-stu-id="11146-126">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="11146-127">요소를 지정할 건물 번호와 층이 모두를 차지 하며 각 요소를 함께 건물과 층의 개수를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-127">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="11146-128">따라서 이러한 배열에서는 두 개의 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-128">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="11146-129">다음 예제에서는 보유 하는 변수를 선언는 *2 차원 배열* 0 ~ 40 건물과 층 0 ~ 5에 대 한 office 카운트 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-129">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="11146-130">2 차원 배열을 라고도 *사각형 배열을*합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-130">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="11146-131">3 차원</span><span class="sxs-lookup"><span data-stu-id="11146-131">Three Dimensions</span></span>  
 <span data-ttu-id="11146-132">몇 가지 배열은 있는 3d 공간에서 값과 같은 3 차원입니다.</span><span class="sxs-lookup"><span data-stu-id="11146-132">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="11146-133">이러한 배열은 경우 x, y 및 z 좌표 물리적 공간을 나타내는 세 개의 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-133">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="11146-134">다음 예제에서는 보유 하는 변수를 선언는 *3 차원 배열을* 한 다양 한 시점에서 차원 공간의 온도가 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-134">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="11146-135">4 개 이상의 차원</span><span class="sxs-lookup"><span data-stu-id="11146-135">More than Three Dimensions</span></span>  
 <span data-ttu-id="11146-136">배열 32 차원을 수 있지만에 거의 3 개를 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-136">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11146-137">배열에 차원을 추가 하면 상당히 다차원 배열은 주의 하 여 배열에 필요한 총 저장소 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-137">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="11146-138">다른 차원 사용</span><span class="sxs-lookup"><span data-stu-id="11146-138">Using Different Dimensions</span></span>  
 <span data-ttu-id="11146-139">현재 월의 모든 날에 대 한 판매 금액을 추적 하 고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-139">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="11146-140">다음 예제와 같이 해당 월의 각 날짜에 대 한 한 표시 31 요소는 1 차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11146-140">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="11146-141">이제 한 달의 뿐만 아니라 해당 연도의 매월을 매일 뿐만 아니라 동일한 정보를 추적 하려는 경우 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-141">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="11146-142">다음 예제와 같이 (개월)에 대 한 12 개의 행과 31 열 일)에 대 한 2 차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11146-142">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="11146-143">현재 사용 하기로 결정할 경우를 가정해 볼 배열 1 년 이상에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-143">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="11146-144">5 년에 대 한 총 판매액을 추적 하려는 경우 다음 예제와 같이 5 개의 레이어, 12 개의 행과 31 열이 있는 3 차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11146-144">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="11146-145">각 인덱스 0에서 최대값의 각 차원 다릅니다 때문에 `salesAmounts` 해당 차원에 필요한 길이 보다 1 작은 값으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11146-145">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="11146-146">배열의 크기 각 새 차원에 따라 카운터가 증가 또한 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-146">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="11146-147">이전 예제에서 세 가지 크기만 각각 31, 372, 및 1,860 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="11146-147">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11146-148">사용 하지 않고 배열을 만들 수는 `Dim` 문 또는 `New` 절.</span><span class="sxs-lookup"><span data-stu-id="11146-148">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="11146-149">예를 들어, 호출할 수 있습니다는 <xref:System.Array.CreateInstance%2A> 메서드 또는 다른 구성 요소 배열을 전달할 수 코드 이런이 방식으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="11146-149">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="11146-150">이러한 배열은 0이 아닌 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11146-150">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="11146-151">사용 하 여 차원의 최소치 항상 테스트할 수 있습니다는 <xref:System.Array.GetLowerBound%2A> 메서드 또는 `LBound` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="11146-151">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11146-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11146-152">See Also</span></span>  
 [<span data-ttu-id="11146-153">배열</span><span class="sxs-lookup"><span data-stu-id="11146-153">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="11146-154">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="11146-154">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
