---
title: Object Data Type
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 847f2b50296ad1a1ba6f0009d1d6afced27f9abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="object-data-type"></a><span data-ttu-id="3c1bb-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="3c1bb-102">Object Data Type</span></span>
<span data-ttu-id="3c1bb-103">개체를 참조 하는 주소를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="3c1bb-104">참조 형식 (문자열, 배열, 클래스 또는 인터페이스)를 할당할 수 있습니다는 `Object` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="3c1bb-105">`Object` 변수 값 형식의 데이터에도 참조할 수 있습니다 (숫자, `Boolean`, `Char`, `Date`, 구조체 또는 열거형)입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c1bb-106">설명</span><span class="sxs-lookup"><span data-stu-id="3c1bb-106">Remarks</span></span>  
 <span data-ttu-id="3c1bb-107">`Object` 데이터 형식은 응용 프로그램에서 인식 하는 모든 개체 인스턴스를 포함 하 여 모든 데이터 형식의 데이터를 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="3c1bb-108">사용 하 여 `Object` 컴파일 타임에 알지 못하는 경우를 가리킬 수 있습니다 데이터 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>  
  
 <span data-ttu-id="3c1bb-109">기본값 `Object` 은 `Nothing` (null 참조).</span><span class="sxs-lookup"><span data-stu-id="3c1bb-109">The default value of `Object` is `Nothing` (a null reference).</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="3c1bb-110">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3c1bb-110">Data Types</span></span>  
 <span data-ttu-id="3c1bb-111">변수, 상수 또는 모든 데이터 형식의 식을 할당할 수는 `Object` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="3c1bb-112">데이터 형식을 결정 하는 `Object` 변수가 현재 참조 하는 데는 <xref:System.Type.GetTypeCode%2A> 의 메서드는 <xref:System.Type?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="3c1bb-113">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-113">The following example illustrates this.</span></span>  
  
```  
Dim myObject As Object  
' Suppose myObject has now had something assigned to it.  
Dim datTyp As Integer  
datTyp = Type.GetTypeCode(myObject.GetType())  
```  
  
 <span data-ttu-id="3c1bb-114">`Object` 데이터 형식이 참조 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="3c1bb-115">그러나 Visual Basic에서 처리는 `Object` 값 형식의 데이터를 참조 하는 경우 값 형식으로 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>  
  
## <a name="storage"></a><span data-ttu-id="3c1bb-116">저장소</span><span class="sxs-lookup"><span data-stu-id="3c1bb-116">Storage</span></span>  
 <span data-ttu-id="3c1bb-117">참조 하는 데이터 형식에 관계 없이 `Object` 변수를 포함 데이터 값 자체를 아니라 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="3c1bb-118">항상 컴퓨터 메모리에 4 바이트를 사용 하지만 여기 변수의 값을 나타내는 데이터 저장소에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="3c1bb-119">포인터를 사용 하 여 데이터를 찾을 코드로 인해 `Object` 값 형식을 있는 변수는 액세스할 때 보다 명시적으로 형식화 된 변수 약간 더 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="3c1bb-120">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="3c1bb-120">Programming Tips</span></span>  
  
-   <span data-ttu-id="3c1bb-121">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="3c1bb-121">**Interop Considerations.**</span></span> <span data-ttu-id="3c1bb-122">Automation 또는 COM 개체를 위한.NET Framework에 대해 작성 되지 않은 구성 요소와 상호 작용 하는 경우 유의 포인터 형식은 다른 환경에서 Visual Basic과 호환 되는지 `Object` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>  
  
-   <span data-ttu-id="3c1bb-123">**성능.**</span><span class="sxs-lookup"><span data-stu-id="3c1bb-123">**Performance.**</span></span> <span data-ttu-id="3c1bb-124">으로 선언 된 변수는 `Object` 형식이 개체에 대 한 참조를 포함할 수 있을 만큼 유연 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="3c1bb-125">그러나 메서드 또는 속성에 이러한 변수를 호출 하면 항상 발생 *런타임에 바인딩* (실행 시)입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="3c1bb-126">강제로 *초기 바인딩* (컴파일 시) 및 성능 향상, 특정 클래스 이름 사용 하 여 변수를 선언 하거나 특정 데이터 형식으로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>  
  
     <span data-ttu-id="3c1bb-127">개체 변수를 선언 하는 경우 예를 들어 특정 클래스 형식에 사용 하려고 <xref:System.OperatingSystem>, 일반화 된 대신 `Object` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="3c1bb-128">와 같은 사용 가능한 가장 구체적인 클래스도 사용 해야 <xref:System.Windows.Forms.TextBox> 대신 <xref:System.Windows.Forms.Control>, 속성 및 메서드에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="3c1bb-129">일반적으로 사용할 수 있습니다는 **클래스** 목록에 **개체 브라우저** 사용할 수 있는 클래스 이름을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>  
  
-   <span data-ttu-id="3c1bb-130">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c1bb-130">**Widening.**</span></span> <span data-ttu-id="3c1bb-131">모든 데이터 형식 및 모든 참조 형식으로 확장 된 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="3c1bb-132">즉, 모든 형식을 변환할 수 있습니다 `Object` 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
     <span data-ttu-id="3c1bb-133">그러나 다른 값 형식으로 변환 하는 경우 및 `Object`, 작업을 수행 하는 Visual Basic *boxing* 및 *unboxing*, 실행 속도가 느린 확인입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>  
  
-   <span data-ttu-id="3c1bb-134">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="3c1bb-134">**Type Characters.**</span></span> <span data-ttu-id="3c1bb-135">`Object`에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-135">`Object` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="3c1bb-136">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="3c1bb-136">**Framework Type.**</span></span> <span data-ttu-id="3c1bb-137">.NET Framework에 있는 해당 형식이 고 <xref:System.Object?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c1bb-138">예제</span><span class="sxs-lookup"><span data-stu-id="3c1bb-138">Example</span></span>  
 <span data-ttu-id="3c1bb-139">다음 예제는 `Object` 개체 인스턴스를 가리키는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c1bb-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>  
  
```  
Dim objDb As Object  
Dim myCollection As New Collection()  
' Suppose myCollection has now been populated.  
objDb = myCollection.Item(1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c1bb-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c1bb-140">See Also</span></span>  
 <xref:System.Object>  
 [<span data-ttu-id="3c1bb-141">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3c1bb-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="3c1bb-142">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="3c1bb-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="3c1bb-143">변환 요약</span><span class="sxs-lookup"><span data-stu-id="3c1bb-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="3c1bb-144">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="3c1bb-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="3c1bb-145">방법: 두 개체가 관련이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="3c1bb-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="3c1bb-146">방법: 두 개체가 동일한지 확인</span><span class="sxs-lookup"><span data-stu-id="3c1bb-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
