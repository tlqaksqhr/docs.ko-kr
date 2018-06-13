---
title: Visual Basic의 제네릭 형식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- generic interfaces
- data type arguments [Visual Basic], defining
- generic delegates
- arguments [Visual Basic], data types
- Of keyword [Visual Basic], using
- delegates, generic
- constraints, Visual Basic generic types
- generic parameters
- data type parameters
- procedures [Visual Basic], generic
- generic procedures
- data types [Visual Basic], generic
- data types [Visual Basic], as parameters
- generics [Visual Basic], generic types
- data types [Visual Basic], as arguments
- generic classes [Visual Basic], Visual Basic
- parameters [Visual Basic], type
- type arguments
- interfaces [Visual Basic], generic
- generics [Visual Basic]
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generic structures [Visual Basic]
- generic classes [Visual Basic]
- type parameters
- data type arguments
- structures [Visual Basic], generic
- parameters [Visual Basic], data type
- collections, generic
- classes [Visual Basic], generic
- data type parameters [Visual Basic], defining
- type arguments [Visual Basic], defining
- arguments [Visual Basic], type
ms.assetid: 89f771d9-ecbb-4737-88b8-116b63c6cf4d
ms.openlocfilehash: f86819f9bd3cbcceb4be696852655018868f4a56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655599"
---
# <a name="generic-types-in-visual-basic-visual-basic"></a><span data-ttu-id="364eb-102">Visual Basic의 제네릭 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="364eb-102">Generic Types in Visual Basic (Visual Basic)</span></span>
<span data-ttu-id="364eb-103">*제네릭 형식* 은 다양한 데이터 형식에 대해 동일한 기능을 수행하도록 조정되는 단일 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-103">A *generic type* is a single programming element that adapts to perform the same functionality for a variety of data types.</span></span> <span data-ttu-id="364eb-104">제네릭 클래스 또는 프로시저를 정의할 때는 해당 기능을 수행하고자 하는 각 데이터 형식마다 별도의 버전을 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-104">When you define a generic class or procedure, you do not have to define a separate version for each data type for which you might want to perform that functionality.</span></span>  
  
 <span data-ttu-id="364eb-105">비유하자면 헤드를 교체할 수 있는 스크루드라이버와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-105">An analogy is a screwdriver set with removable heads.</span></span> <span data-ttu-id="364eb-106">즉, 돌려야 하는 나사에 맞는 헤드(일자, 십자, 별 모양)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-106">You inspect the screw you need to turn and select the correct head for that screw (slotted, crossed, starred).</span></span> <span data-ttu-id="364eb-107">그리고 올바른 헤드를 스크루드라이버 핸들에 삽입하면 스크루드라이버와 정확하게 동일한 기능, 즉 나사를 돌리는 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-107">Once you insert the correct head in the screwdriver handle, you perform the exact same function with the screwdriver, namely turning the screw.</span></span>  
  
 <span data-ttu-id="364eb-108">![제네릭 도구로 설정 된 스크루 드라이버의 다이어그램](../../../../visual-basic/programming-guide/language-features/data-types/media/genericscrewdriver.gif "GenericScrewDriver")</span><span class="sxs-lookup"><span data-stu-id="364eb-108">![Diagram of a screwdriver set as a generic tool](../../../../visual-basic/programming-guide/language-features/data-types/media/genericscrewdriver.gif "GenericScrewDriver")</span></span>  
<span data-ttu-id="364eb-109">제네릭 도구 역할을 하는 스크루드라이버 세트</span><span class="sxs-lookup"><span data-stu-id="364eb-109">Screwdriver set as a generic tool</span></span>  
  
 <span data-ttu-id="364eb-110">제네릭 형식을 정의할 때는 하나 이상의 데이터 형식을 사용하여 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-110">When you define a generic type, you parameterize it with one or more data types.</span></span> <span data-ttu-id="364eb-111">이렇게 하면 코드를 사용하여 데이터 형식을 요구 사항에 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-111">This allows the using code to tailor the data types to its requirements.</span></span> <span data-ttu-id="364eb-112">각각 서로 다른 데이터 형식 집합에 대해 작동하는 여러 프로그래밍 요소를 제네릭 요소에서 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-112">Your code can declare several different programming elements from the generic element, each one acting on a different set of data types.</span></span> <span data-ttu-id="364eb-113">하지만 선언된 요소는 사용하는 데이터 형식에 관계없이 모두 동일한 논리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-113">But the declared elements all perform the identical logic, no matter what data types they are using.</span></span>  
  
 <span data-ttu-id="364eb-114">예를 들어 `String`과 같은 특정 데이터 형식에서 작동하는 큐 클래스를 만들어 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-114">For example, you might want to create and use a queue class that operates on a specific data type such as `String`.</span></span> <span data-ttu-id="364eb-115">이러한 클래스를 선언할 수 <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-115">You can declare such a class from <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#1](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_1.vb)]  
  
 <span data-ttu-id="364eb-116">이제 `stringQ` 를 사용하여 `String` 값으로만 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-116">You can now use `stringQ` to work exclusively with `String` values.</span></span> <span data-ttu-id="364eb-117">`stringQ` 는 `String` 값에 일반화되는 것이 아니라 `Object` 에 한정되므로 런타임에 바인딩 또는 형식 변환이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-117">Because `stringQ` is specific for `String` instead of being generalized for `Object` values, you do not have late binding or type conversion.</span></span> <span data-ttu-id="364eb-118">이를 통해 실행 시간을 절약하고 런타임 오류를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-118">This saves execution time and reduces run-time errors.</span></span>  
  
 <span data-ttu-id="364eb-119">제네릭 형식 사용에 대한 자세한 내용은 [How to: Use a Generic Class](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="364eb-119">For more information on using a generic type, see [How to: Use a Generic Class](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md).</span></span>  
  
## <a name="example-of-a-generic-class"></a><span data-ttu-id="364eb-120">제네릭 클래스의 예</span><span class="sxs-lookup"><span data-stu-id="364eb-120">Example of a Generic Class</span></span>  
 <span data-ttu-id="364eb-121">다음 예에서는 제네릭 클래스의 기본 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-121">The following example shows a skeleton definition of a generic class.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#2](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_2.vb)]  
  
 <span data-ttu-id="364eb-122">앞의 기본 정의에서 `t` 은 *형식 매개 변수*, 즉 클래스를 선언할 때 제공하는 데이터 형식에 대한 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-122">In the preceding skeleton, `t` is a *type parameter*, that is, a placeholder for a data type that you supply when you declare the class.</span></span> <span data-ttu-id="364eb-123">코드의 다른 곳에서 `classHolder` 에 대한 다양한 데이터 형식을 제공하여 여러 버전의 `t`를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-123">Elsewhere in your code, you can declare various versions of `classHolder` by supplying various data types for `t`.</span></span> <span data-ttu-id="364eb-124">다음 예제에서는 이러한 선언 두 가지를  보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-124">The following example shows two such declarations.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#3](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_3.vb)]  
  
 <span data-ttu-id="364eb-125">위의 문에서는 특정 형식이 형식 매개 변수를 대체하는 *생성된 클래스*를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-125">The preceding statements declare *constructed classes*, in which a specific type replaces the type parameter.</span></span> <span data-ttu-id="364eb-126">이 대체는 생성된 클래스 내에서 코드 전체로 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-126">This replacement is propagated throughout the code within the constructed class.</span></span> <span data-ttu-id="364eb-127">다음 예에서는 `processNewItem` 의 `integerClass`프로시저 모습을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-127">The following example shows what the `processNewItem` procedure looks like in `integerClass`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#4](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_4.vb)]  
  
 <span data-ttu-id="364eb-128">자세한 예제를 참조 하십시오. [하는 방법: 기능을 정의 클래스는 수를 제공 동일한 서로 다른 데이터 형식에](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-128">For a more complete example, see [How to: Define a Class That Can Provide Identical Functionality on Different Data Types](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md).</span></span>  
  
## <a name="eligible-programming-elements"></a><span data-ttu-id="364eb-129">적용 가능한 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="364eb-129">Eligible Programming Elements</span></span>  
 <span data-ttu-id="364eb-130">제네릭 클래스, 구조체, 인터페이스, 프로시저 및 대리자를 정의하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-130">You can define and use generic classes, structures, interfaces, procedures, and delegates.</span></span> <span data-ttu-id="364eb-131">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 에서는 많이 사용되는 제네릭 요소를 나타내는 몇 개의 제네릭 클래스, 구조체 및 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-131">Note that the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] defines several generic classes, structures, and interfaces that represent commonly used generic elements.</span></span> <span data-ttu-id="364eb-132"><xref:System.Collections.Generic?displayProperty=nameWithType> 사전, 목록, 큐 및 스택 네임 스페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-132">The <xref:System.Collections.Generic?displayProperty=nameWithType> namespace provides dictionaries, lists, queues, and stacks.</span></span> <span data-ttu-id="364eb-133">사용자 고유의 제네릭 요소를 정의 하기 전에 사용할 수 있는 이미 있는지 확인 하십시오 <xref:System.Collections.Generic?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-133">Before defining your own generic element, see if it is already available in <xref:System.Collections.Generic?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="364eb-134">프로시저는 형식이 아니지만 제네릭 프로시저를 정의하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-134">Procedures are not types, but you can define and use generic procedures.</span></span> <span data-ttu-id="364eb-135">[Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="364eb-135">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="advantages-of-generic-types"></a><span data-ttu-id="364eb-136">제네릭 형식의 장점</span><span class="sxs-lookup"><span data-stu-id="364eb-136">Advantages of Generic Types</span></span>  
 <span data-ttu-id="364eb-137">제네릭 형식은 각각 특정 데이터 형식에서 작동하는 서로 다른 프로그래밍 요소 여러 개를 선언하는 기초의 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-137">A generic type serves as a basis for declaring several different programming elements, each of which operates on a specific data type.</span></span> <span data-ttu-id="364eb-138">제네릭 형식의 대안은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-138">The alternatives to a generic type are:</span></span>  
  
1.  <span data-ttu-id="364eb-139">`Object` 데이터 형식에서 작동하는 단일 형식.</span><span class="sxs-lookup"><span data-stu-id="364eb-139">A single type operating on the `Object` data type.</span></span>  
  
2.  <span data-ttu-id="364eb-140">형식의 *형식 특정* 버전 집합. 각 버전은 `String`, `Integer`또는 사용자 정의 형식(예: `customer`)과 같은 하나의 특정 데이터 형식에 대해 개별적으로 코딩되고 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-140">A set of *type-specific* versions of the type, each version individually coded and operating on one specific data type such as `String`, `Integer`, or a user-defined type such as `customer`.</span></span>  
  
 <span data-ttu-id="364eb-141">이러한 대안에 비교했을 때 제네릭 형식에는 다음과 같은 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-141">A generic type has the following advantages over these alternatives:</span></span>  
  
-   <span data-ttu-id="364eb-142">**형식 안전성.**</span><span class="sxs-lookup"><span data-stu-id="364eb-142">**Type Safety.**</span></span> <span data-ttu-id="364eb-143">제네릭 형식은 컴파일 시간 형식 검사를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-143">Generic types enforce compile-time type checking.</span></span> <span data-ttu-id="364eb-144">`Object` 에 기반한 형식은 모든 데이터 형식을 수락하며 입력 데이터 형식이 수락 가능한지 확인하기 위한 코드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-144">Types based on `Object` accept any data type, and you must write code to check whether an input data type is acceptable.</span></span> <span data-ttu-id="364eb-145">제네릭 형식을 사용하면 컴파일러가 런타임 전에 불일치를 찾아낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-145">With generic types, the compiler can catch type mismatches before run time.</span></span>  
  
-   <span data-ttu-id="364eb-146">**성능.**</span><span class="sxs-lookup"><span data-stu-id="364eb-146">**Performance.**</span></span> <span data-ttu-id="364eb-147">제네릭 형식은 데이터 *box* 및 *unbox* 작업을 수행할 필요가 없습니다. 각각 하나의 데이터 형식에 특수화되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-147">Generic types do not have to *box* and *unbox* data, because each one is specialized for one data type.</span></span> <span data-ttu-id="364eb-148">`Object` 에 기반한 작업에서는 입력 데이터 형식에 box 작업을 수행하여 `Object` 로 변환한 다음 출력을 위한 데이터를 unbox해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-148">Operations based on `Object` must box input data types to convert them to `Object` and unbox data destined for output.</span></span> <span data-ttu-id="364eb-149">이러한 box 및 unbox 작업으로 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-149">Boxing and unboxing reduce performance.</span></span>  
  
     <span data-ttu-id="364eb-150">또한 `Object` 에 기반한 형식은 런타임에 바인딩되므로 해당 멤버에 액세스하려면 런타임에 추가 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-150">Types based on `Object` are also late-bound, which means that accessing their members requires extra code at run time.</span></span> <span data-ttu-id="364eb-151">이 경우에도 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-151">This also reduces performance.</span></span>  
  
-   <span data-ttu-id="364eb-152">**코드 통합.**</span><span class="sxs-lookup"><span data-stu-id="364eb-152">**Code Consolidation.**</span></span> <span data-ttu-id="364eb-153">제네릭 형식의 코드는 한 번만 정의하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-153">The code in a generic type has to be defined only once.</span></span> <span data-ttu-id="364eb-154">형식의 형식 특정 버전 집합은 각 버전에서 동일한 코드를 복제해야 하며 유일한 차이는 해당 버전의 특정 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-154">A set of type-specific versions of a type must replicate the same code in each version, with the only difference being the specific data type for that version.</span></span> <span data-ttu-id="364eb-155">제네릭 형식을 사용하면 형식 특정 버전이 모두 원본 제네릭 형식에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-155">With generic types, the type-specific versions are all generated from the original generic type.</span></span>  
  
-   <span data-ttu-id="364eb-156">**코드 재사용.**</span><span class="sxs-lookup"><span data-stu-id="364eb-156">**Code Reuse.**</span></span> <span data-ttu-id="364eb-157">특정 데이터 형식에 종속되지 않는 코드는 제네릭일 경우 여러 데이터 형식에 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-157">Code that does not depend on a particular data type can be reused with various data types if it is generic.</span></span> <span data-ttu-id="364eb-158">원래 예상하지 않았던 데이터 형식에도 재사용할 수 있는 경우도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-158">You can often reuse it even with a data type that you did not originally predict.</span></span>  
  
-   <span data-ttu-id="364eb-159">**IDE 지원.**</span><span class="sxs-lookup"><span data-stu-id="364eb-159">**IDE Support.**</span></span> <span data-ttu-id="364eb-160">제네릭 형식에서 선언된 생성된 형식을 사용하면 코드 개발 시 IDE(통합 개발 환경)에서 더 많은 지원 기능이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-160">When you use a constructed type declared from a generic type, the integrated development environment (IDE) can give you more support while you are developing your code.</span></span> <span data-ttu-id="364eb-161">예를 들어 IntelliSense가 생성자 또는 메서드의 인수에 대한 형식 특정 옵션을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-161">For example, IntelliSense can show you the type-specific options for an argument to a constructor or method.</span></span>  
  
-   <span data-ttu-id="364eb-162">**제네릭 알고리즘.**</span><span class="sxs-lookup"><span data-stu-id="364eb-162">**Generic Algorithms.**</span></span> <span data-ttu-id="364eb-163">형식에 독립적인 추상 알고리즘이 제네릭 형식의 좋은 후보입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-163">Abstract algorithms that are type-independent are good candidates for generic types.</span></span> <span data-ttu-id="364eb-164">예를 들어 <xref:System.IComparable> 인터페이스를 사용하여 항목을 정렬하는 제네릭 프로시저는 <xref:System.IComparable>를 구현하는 모든 데이터 형식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-164">For example, a generic procedure that sorts items using the <xref:System.IComparable> interface can be used with any data type that implements <xref:System.IComparable>.</span></span>  
  
## <a name="constraints"></a><span data-ttu-id="364eb-165">제약 조건</span><span class="sxs-lookup"><span data-stu-id="364eb-165">Constraints</span></span>  
 <span data-ttu-id="364eb-166">제네릭 형식 정의의 코드는 가능한 형식에 독립적이어야 하지만 제네릭 형식에 제공되는 모든 데이터 형식의 특정 기능을 요구해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-166">Although the code in a generic type definition should be as type-independent as possible, you might need to require a certain capability of any data type supplied to your generic type.</span></span> <span data-ttu-id="364eb-167">예를 들어 정렬을 목적으로 두 항목을 비교하려는 경우에는 해당 데이터 형식이 <xref:System.IComparable> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-167">For example, if you want to compare two items for the purpose of sorting or collating, their data type must implement the <xref:System.IComparable> interface.</span></span> <span data-ttu-id="364eb-168">형식 매개 변수에 *제약 조건* 을 추가하여 이 요구 사항을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-168">You can enforce this requirement by adding a *constraint* to the type parameter.</span></span>  
  
### <a name="example-of-a-constraint"></a><span data-ttu-id="364eb-169">제약 조건의 예</span><span class="sxs-lookup"><span data-stu-id="364eb-169">Example of a Constraint</span></span>  
 <span data-ttu-id="364eb-170">다음 예에서는 형식 인수가 <xref:System.IComparable>을 구현해야 한다는 제약 조건을 가진 클래스의 기본 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-170">The following example shows a skeleton definition of a class with a constraint that requires the type argument to implement <xref:System.IComparable>.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#5](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_5.vb)]  
  
 <span data-ttu-id="364eb-171">이후의 코드에서 `itemManager` 을 구현하지 않는 형식을 제공하여 <xref:System.IComparable>에서 클래스를 생성하려고 시도하면 컴파일러가 오류를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-171">If subsequent code attempts to construct a class from `itemManager` supplying a type that does not implement <xref:System.IComparable>, the compiler signals an error.</span></span>  
  
### <a name="types-of-constraints"></a><span data-ttu-id="364eb-172">제약 조건의 형식</span><span class="sxs-lookup"><span data-stu-id="364eb-172">Types of Constraints</span></span>  
 <span data-ttu-id="364eb-173">제약 조건은 다음 요구 사항을 원하는 대로 조합하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-173">Your constraint can specify the following requirements in any combination:</span></span>  
  
-   <span data-ttu-id="364eb-174">형식 인수는 하나 이상의 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-174">The type argument must implement one or more interfaces</span></span>  
  
-   <span data-ttu-id="364eb-175">형식 인수는 최대 하나의 클래스에서 형식을 상속하거나 해당 클래스의 형식이어야 함</span><span class="sxs-lookup"><span data-stu-id="364eb-175">The type argument must be of the type of, or inherit from, at most one class</span></span>  
  
-   <span data-ttu-id="364eb-176">형식 인수는 매개 변수 없는 생성자로부터 개체를 만드는 코드에 액세스할 수 있는 매개 변수 없는 생성자를 노출해야 함</span><span class="sxs-lookup"><span data-stu-id="364eb-176">The type argument must expose a parameterless constructor accessible to the code that creates objects from it</span></span>  
  
-   <span data-ttu-id="364eb-177">형식 인수는 *참조 형식*이거나 *값 형식*이어야 함</span><span class="sxs-lookup"><span data-stu-id="364eb-177">The type argument must be a *reference type*, or it must be a *value type*</span></span>  
  
 <span data-ttu-id="364eb-178">둘 이상의 요구 사항을 적용해야 하는 경우 쉼표로 구분된 *제약 조건 목록* 을 중괄호(`{ }`) 안에 넣으세요.</span><span class="sxs-lookup"><span data-stu-id="364eb-178">If you need to impose more than one requirement, you use a comma-separated *constraint list* inside braces (`{ }`).</span></span> <span data-ttu-id="364eb-179">액세스 가능한 생성자를 요구 하려면 포함는 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-179">To require an accessible constructor, you include the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the list.</span></span> <span data-ttu-id="364eb-180">참조 형식을 요구하려면 `Class` 키워드를 넣고, 값 형식을 요구하려면 `Structure` 키워드를 넣으세요.</span><span class="sxs-lookup"><span data-stu-id="364eb-180">To require a reference type, you include the `Class` keyword; to require a value type, you include the `Structure` keyword.</span></span>  
  
 <span data-ttu-id="364eb-181">제약 조건에 대한 자세한 내용은 [Type List](../../../../visual-basic/language-reference/statements/type-list.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="364eb-181">For more information on constraints, see [Type List](../../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
### <a name="example-of-multiple-constraints"></a><span data-ttu-id="364eb-182">다중 제약 조건의 예</span><span class="sxs-lookup"><span data-stu-id="364eb-182">Example of Multiple Constraints</span></span>  
 <span data-ttu-id="364eb-183">다음 예제에서는 형식 매개 변수에 제약 조건 목록이 있는 제네릭 클래스의 기본 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-183">The following example shows a skeleton definition of a generic class with a constraint list on the type parameter.</span></span> <span data-ttu-id="364eb-184">이 클래스의 인스턴스를 만드는 코드에서 형식 인수는 <xref:System.IComparable> 및 <xref:System.IDisposable> 인터페이스를 모두 구현해야 하고, 참조 형식어야 하며, 액세스 가능한 매개 변수 없는 생성자를 노출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-184">In the code that creates an instance of this class, the type argument must implement both the <xref:System.IComparable> and <xref:System.IDisposable> interfaces, be a reference type, and expose an accessible parameterless constructor.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#6](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-types_6.vb)]  
  
## <a name="important-terms"></a><span data-ttu-id="364eb-185">중요 용어</span><span class="sxs-lookup"><span data-stu-id="364eb-185">Important Terms</span></span>  
 <span data-ttu-id="364eb-186">제네릭 형식에서는 다음의 용어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-186">Generic types introduce and use the following terms:</span></span>  
  
-   <span data-ttu-id="364eb-187">*제네릭 형식*.</span><span class="sxs-lookup"><span data-stu-id="364eb-187">*Generic Type*.</span></span> <span data-ttu-id="364eb-188">선언할 때 최소 하나의 데이터 형식을 제공하는 클래스, 구조체, 인터페이스, 프로시저 또는 대리자의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-188">A definition of a class, structure, interface, procedure, or delegate for which you supply at least one data type when you declare it.</span></span>  
  
-   <span data-ttu-id="364eb-189">*형식 매개 변수*.</span><span class="sxs-lookup"><span data-stu-id="364eb-189">*Type Parameter*.</span></span> <span data-ttu-id="364eb-190">제네릭 형식 정의에서 형식을 선언할 때 제공하는 데이터 형식에 대한 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-190">In a generic type definition, a placeholder for a data type you supply when you declare the type.</span></span>  
  
-   <span data-ttu-id="364eb-191">*형식 인수*.</span><span class="sxs-lookup"><span data-stu-id="364eb-191">*Type Argument*.</span></span> <span data-ttu-id="364eb-192">제네릭 형식에서 생성된 형식을 선언할 때 형식 매개 변수를 대체하는 특정 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-192">A specific data type that replaces a type parameter when you declare a constructed type from a generic type.</span></span>  
  
-   <span data-ttu-id="364eb-193">*제약 조건*.</span><span class="sxs-lookup"><span data-stu-id="364eb-193">*Constraint*.</span></span> <span data-ttu-id="364eb-194">제공할 수 있는 형식 인수를 제한하는 형식 매개 변수에 대한 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-194">A condition on a type parameter that restricts the type argument you can supply for it.</span></span> <span data-ttu-id="364eb-195">제약 조건은 형식 인수가 특정 인터페이스를 구현하도록 요구하거나, 특정 클래스이거나 특정 클래스에서 상속되도록 요구하거나, 액세스 가능한 매개 변수 없는 생성자를 가지도록 요구하거나, 참조 형식 또는 값 형식이도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-195">A constraint can require that the type argument must implement a particular interface, be or inherit from a particular class, have an accessible parameterless constructor, or be a reference type or a value type.</span></span> <span data-ttu-id="364eb-196">이러한 제약 조건을 결합할 수 있지만 최대 하나의 클래스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-196">You can combine these constraints, but you can specify at most one class.</span></span>  
  
-   <span data-ttu-id="364eb-197">*생성된 형식*.</span><span class="sxs-lookup"><span data-stu-id="364eb-197">*Constructed Type*.</span></span> <span data-ttu-id="364eb-198">형식 매개 변수에 대한 형식 인수를 제공하여 제네릭 형식에서 선언된 클래스, 구조체, 인터페이스, 프로시저 또는 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="364eb-198">A class, structure, interface, procedure, or delegate declared from a generic type by supplying type arguments for its type parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="364eb-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="364eb-199">See Also</span></span>  
 [<span data-ttu-id="364eb-200">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="364eb-200">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="364eb-201">형식 문자</span><span class="sxs-lookup"><span data-stu-id="364eb-201">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="364eb-202">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="364eb-202">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="364eb-203">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="364eb-203">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="364eb-204">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="364eb-204">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="364eb-205">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="364eb-205">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="364eb-206">Of</span><span class="sxs-lookup"><span data-stu-id="364eb-206">Of</span></span>](../../../../visual-basic/language-reference/statements/of-clause.md)  
 [<span data-ttu-id="364eb-207">As</span><span class="sxs-lookup"><span data-stu-id="364eb-207">As</span></span>](../../../../visual-basic/language-reference/statements/as-clause.md)  
 [<span data-ttu-id="364eb-208">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="364eb-208">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="364eb-209">공 분산 및 반공 분산</span><span class="sxs-lookup"><span data-stu-id="364eb-209">Covariance and Contravariance</span></span>](../../concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="364eb-210">반복기</span><span class="sxs-lookup"><span data-stu-id="364eb-210">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
