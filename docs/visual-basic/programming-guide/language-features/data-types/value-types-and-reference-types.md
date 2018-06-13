---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 9456316f71a213905bcb50336533c4e618f5174a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651585"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="b221c-102">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="b221c-102">Value Types and Reference Types</span></span>
<span data-ttu-id="b221c-103">Visual Basic의 데이터 형식은 분류에 따라 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="b221c-104">Visual Basic 데이터 형식 특정 형식의 변수는 자체 데이터 또는 데이터에 대 한 포인터를 저장 하는지 여부에 따라 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-104">The Visual Basic data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="b221c-105">자체 데이터를 저장 하는 경우는 *값 유형*는 메모리의 다른 위치에서 데이터에 대 한 포인터를 보유 하는 경우는 *유형을 참조*합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="b221c-106">값 형식</span><span class="sxs-lookup"><span data-stu-id="b221c-106">Value Types</span></span>  
 <span data-ttu-id="b221c-107">데이터 형식이 *값 유형* 메모리를 할당 하는 자체 내에서 데이터를 보유 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="b221c-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="b221c-108">값 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="b221c-109">모든 숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b221c-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="b221c-110">`Boolean`, `Char` 및 `Date`</span><span class="sxs-lookup"><span data-stu-id="b221c-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="b221c-111">해당 멤버는 참조 형식의 경우에 모든 구조</span><span class="sxs-lookup"><span data-stu-id="b221c-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="b221c-112">열거형의 내부 형식이 항상 이므로 `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, 또는 `ULong`</span><span class="sxs-lookup"><span data-stu-id="b221c-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="b221c-113">모든 구조체는 값 형식에는 참조 형식 멤버를 포함 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="b221c-114">이러한 이유로 값과 같은 형식이 `Char` 및 `Integer` .NET Framework 구조체에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="b221c-115">예를 들어 예약 된 키워드를 사용 하 여 값 형식을 선언할 수 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="b221c-116">사용할 수도 있습니다는 `New` 값 형식을 초기화 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="b221c-117">형식에 매개 변수를 사용 하는 생성자가 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="b221c-118">이 예제는 <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> 생성자는 새 빌드를 `Decimal` 는 지정 된 부분에서 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="b221c-119">참조 형식</span><span class="sxs-lookup"><span data-stu-id="b221c-119">Reference Types</span></span>  
 <span data-ttu-id="b221c-120">A *유형을 참조* 데이터를 보유 하는 다른 메모리 위치에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="b221c-121">참조 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="b221c-122">해당 요소는 경우에 모든 배열 값 형식</span><span class="sxs-lookup"><span data-stu-id="b221c-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="b221c-123">와 같은 클래스 형식 <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="b221c-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="b221c-124">대리자</span><span class="sxs-lookup"><span data-stu-id="b221c-124">Delegates</span></span>  
  
 <span data-ttu-id="b221c-125">클래스는는 *유형을 참조*합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-125">A class is a *reference type*.</span></span> <span data-ttu-id="b221c-126">이러한 이유로 같은 참조 형식이 `Object` 및 `String` 에서 지 원하는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="b221c-127">참고의 멤버는 값 형식의 경우에 모든 배열은 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="b221c-128">사용 해야 하므로 모든 참조 형식이 기본.NET Framework 클래스를 나타내는 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 초기화할 때는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="b221c-129">다음 문은 배열을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="b221c-130">형식 없는 요소</span><span class="sxs-lookup"><span data-stu-id="b221c-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="b221c-131">선언 된 요소에 대 한 데이터 형식으로 그 중 하나를 지정할 수 없으므로 다음 프로그래밍 요소 형식으로 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="b221c-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="b221c-132">Namespaces</span></span>  
  
-   <span data-ttu-id="b221c-133">모듈</span><span class="sxs-lookup"><span data-stu-id="b221c-133">Modules</span></span>  
  
-   <span data-ttu-id="b221c-134">이벤트</span><span class="sxs-lookup"><span data-stu-id="b221c-134">Events</span></span>  
  
-   <span data-ttu-id="b221c-135">속성 및 프로시저</span><span class="sxs-lookup"><span data-stu-id="b221c-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="b221c-136">변수, 상수 및 필드</span><span class="sxs-lookup"><span data-stu-id="b221c-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="b221c-137">Object 데이터 형식 사용</span><span class="sxs-lookup"><span data-stu-id="b221c-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="b221c-138">참조 형식 또는 값 형식 변수에 할당할 수 있습니다는 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="b221c-139">`Object` 변수 항상 데이터를 데이터 자체에 대 한 포인터를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="b221c-140">그러나 값 형식을 할당 하는 경우는 `Object` 변수인 것 처럼 동작 자체 데이터를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="b221c-141">자세한 내용은 참조 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="b221c-142">하는지를 알 수 있습니다는 `Object` 변수 역할을 하는 참조 형식 또는 값 형식을 전달 하 여는 <xref:Microsoft.VisualBasic.Information.IsReference%2A> 에서 메서드는 <xref:Microsoft.VisualBasic.Information> 의 클래스는 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="b221c-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 반환 `True` 경우의 콘텐츠는 `Object` 참조 형식 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b221c-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b221c-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b221c-144">See Also</span></span>  
 [<span data-ttu-id="b221c-145">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="b221c-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="b221c-146">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="b221c-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="b221c-147">Structure 문</span><span class="sxs-lookup"><span data-stu-id="b221c-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="b221c-148">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="b221c-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="b221c-149">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b221c-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="b221c-150">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b221c-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
