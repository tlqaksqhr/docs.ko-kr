---
title: Generic Procedures in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e019ca32277f93f798e99e996a3670c8302ba9b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="3997b-102">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3997b-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="3997b-103">A *제네릭 프로시저*라고도 하는 *제네릭 메서드*, 하나 이상의 형식 매개 변수를 사용 하 여 정의 하는 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="3997b-104">따라서 호출 코드를를 프로시저를 호출할 때마다 데이터 형식을 요구 사항에 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="3997b-105">프로시저는 제네릭 클래스 또는 일반 구조체 내에 정의 되는 것 만으로 제네릭이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="3997b-106">제네릭일, 해당 프로시저는 일반 매개 변수를 걸릴 수 있습니다 하나 이상의 형식 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="3997b-107">제네릭이 아닌 프로시저 및 제네릭이 아닌 클래스, 구조, 제네릭 클래스 또는 구조체를 포함 하거나 모듈에서 제네릭 프로시저를 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="3997b-108">제네릭 프로시저의 반환 형식이 있으며 자체 프로시저에서 코드를 설정한 경우에 일반 매개 변수 목록의 해당 형식 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="3997b-109">형식 유추</span><span class="sxs-lookup"><span data-stu-id="3997b-109">Type Inference</span></span>  
 <span data-ttu-id="3997b-110">제네릭 프로시저가 형식 인수를 전혀 제공 하지 않고 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="3997b-111">이러한 방식으로 호출을 하는 경우 컴파일러는 프로시저의 형식 인수에 전달 하는 적절 한 데이터 형식을 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="3997b-112">이 라고 *형식 유추*합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-112">This is called *type inference*.</span></span> <span data-ttu-id="3997b-113">다음 코드는 호출을 보여 줍니다. 컴파일러 유추 하 종류를 전달 해야 `String` 형식 매개 변수에 `t`합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 <span data-ttu-id="3997b-114">컴파일러가 호출한 컨텍스트에서 형식 인수를 유추할 수 없습니다, 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="3997b-115">이러한 오류가 발생할 수는 배열의 차수가 일치 하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="3997b-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="3997b-116">예를 들어, 형식 매개 변수 배열로 서는 기본 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="3997b-117">제네릭 프로시저를 호출 하는 경우 다른 차수 (차원 수)의 배열을 제공는 차수가 일치 하지 않으면 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="3997b-118">다음 코드는 호출을 보여 줍니다. 2 차원 배열은 1 차원 배열 예상 하는 프로시저에 전달 되는에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 <span data-ttu-id="3997b-119">모든 형식 인수를 생략 하는 것에 의해서만 형식 유추를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="3997b-120">하나의 형식 인수를 제공 하는 경우 모두 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="3997b-121">형식 유추가 제네릭 프로시저에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="3997b-122">제네릭 클래스, 구조체, 인터페이스 또는 대리자에서 형식 유추를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3997b-123">예제</span><span class="sxs-lookup"><span data-stu-id="3997b-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="3997b-124">설명</span><span class="sxs-lookup"><span data-stu-id="3997b-124">Description</span></span>  
 <span data-ttu-id="3997b-125">다음 예제에서는 제네릭 `Function` 프로시저 배열에서 특정 요소를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="3997b-126">하나의 형식 매개 변수를 정의 하 고 하는 매개 변수 목록에 두 개의 매개 변수를 생성 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3997b-127">코드</span><span class="sxs-lookup"><span data-stu-id="3997b-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="3997b-128">설명</span><span class="sxs-lookup"><span data-stu-id="3997b-128">Comments</span></span>  
 <span data-ttu-id="3997b-129">앞의 예제를 비교 하기 위해서는 `searchValue` 의 각 요소에 대해 `searchArray`합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="3997b-130">형식 매개 변수는이 기능을 보장 하기 위해 제한 `T` 구현 하는 <xref:System.IComparable%601> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="3997b-131">코드를 사용 하 여는 <xref:System.IComparable%601.CompareTo%2A> 메서드 대신는 `=` 연산자에 대 한 형식 인수를 제공 하지 않을 수도 있기 때문에 `T` 지원는 `=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="3997b-132">테스트할 수 있습니다는 `findElement` 프로시저 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 <span data-ttu-id="3997b-133">에 대 한 호출이 이전 `MsgBox` "0", "1" 및 "-1"은 각각 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3997b-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3997b-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3997b-134">See Also</span></span>  
 [<span data-ttu-id="3997b-135">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="3997b-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="3997b-136">방법: 다른 데이터 형식에 동일한 기능을 제공할 수 있는 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="3997b-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [<span data-ttu-id="3997b-137">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="3997b-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="3997b-138">절차</span><span class="sxs-lookup"><span data-stu-id="3997b-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="3997b-139">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="3997b-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="3997b-140">형식 목록</span><span class="sxs-lookup"><span data-stu-id="3997b-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="3997b-141">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="3997b-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
