---
title: "방법: 한 배열에 다른 배열 할당(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0dd2d678bbfdeaa6b12b5b5a4f69d0fbca8c1944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="d3842-102">방법: 한 배열에 다른 배열 할당(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3842-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>
<span data-ttu-id="d3842-103">배열 개체 이기 때문에 다른 개체 형식 처럼 대입 문에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="d3842-104">배열 변수는 배열 요소와 순위 및 길이 정보를 구성 하는 데이터는 포인터를 보유 하 고 할당만이 포인터를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>  
  
### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="d3842-105">배열에 다른 배열 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="d3842-105">To assign one array to another array</span></span>  
  
1.  <span data-ttu-id="d3842-106">두 배열 차수 (차원 수) 및 같은 호환 되는 요소 데이터 형식 인지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3842-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>  
  
2.  <span data-ttu-id="d3842-107">소스 배열에서 대상 배열에 할당할 표준 대입문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="d3842-108">배열 이름 뒤에 괄호를 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-108">Do not follow either array name with parentheses.</span></span>  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 <span data-ttu-id="d3842-109">다른 한 배열을 할당 하는 경우 다음 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-109">When you assign one array to another, the following rules apply:</span></span>  
  
-   <span data-ttu-id="d3842-110">**동일한 차수입니다.**</span><span class="sxs-lookup"><span data-stu-id="d3842-110">**Equal Ranks.**</span></span> <span data-ttu-id="d3842-111">대상 배열의 차수 (차원 수)는 원본 배열의과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>  
  
     <span data-ttu-id="d3842-112">두 배열의 차수가 값이 같으면 제공 차원 필요가 없습니다과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="d3842-113">지정된 된 차원에 있는 요소의 수는 할당 하는 동안 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-113">The number of elements in a given dimension can change during assignment.</span></span>  
  
-   <span data-ttu-id="d3842-114">**요소 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="d3842-114">**Element Types.**</span></span> <span data-ttu-id="d3842-115">두 배열 중 하나가 있어야 *유형을 참조* 요소 또는 두 배열 있어야 *값 유형* 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="d3842-116">자세한 내용은 참조 [값 형식과 참조 형식이](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
    -   <span data-ttu-id="d3842-117">두 배열 값 형식 요소가 있으면 요소 데이터 형식이 정확히 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="d3842-118">배열에 할당할 수 있는이 유일한 예외는 `Enum` 요소를 사용 하는 기본 유형의 배열 `Enum`합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>  
  
    -   <span data-ttu-id="d3842-119">두 배열 참조 형식 요소에 있으면 소스 요소 형식은 대상 요소 형식에서 파생 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="d3842-120">이 경우 두 배열의 요소와 같은 상속 관계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="d3842-121">이 라고 *배열 공 분산*합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-121">This is called *array covariance*.</span></span>  
  
 <span data-ttu-id="d3842-122">컴파일러 오류 위의 규칙 위반 하면 예를 들어 데이터 형식이 호환 되지 않는 경우 또는 순위 같지 않습니다. 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="d3842-123">오류 처리는 할당을 시도 하기 전에 배열 호환 되는지 확인 하기 위해 코드에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3842-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="d3842-124">사용할 수도 있습니다는 [TryCast 연산자](../../../../visual-basic/language-reference/operators/trycast-operator.md) 키워드 예외가 throw 되지 않게 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="d3842-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3842-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3842-125">See Also</span></span>  
 [<span data-ttu-id="d3842-126">배열</span><span class="sxs-lookup"><span data-stu-id="d3842-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="d3842-127">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d3842-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="d3842-128">Enum 문</span><span class="sxs-lookup"><span data-stu-id="d3842-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="d3842-129">배열 규칙</span><span class="sxs-lookup"><span data-stu-id="d3842-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
