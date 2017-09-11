---
title: "구조체와 클래스 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures
- classes [Visual Basic]
- structures, compared to classes
- structures, structure variables
- structure variables
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c6874192a09db9ff5f247274247630d0bfa05ea3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="structures-and-classes-visual-basic"></a><span data-ttu-id="cf7c3-102">구조체와 클래스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf7c3-102">Structures and Classes (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="cf7c3-103">구조체와 클래스에 대 한 구문의 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-103"> unifies the syntax for structures and classes, with the result that both entities support most of the same features.</span></span> <span data-ttu-id="cf7c3-104">그러나 구조체와 클래스 간의 중요 한 차이점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-104">However, there are also important differences between structures and classes.</span></span>  
  
 <span data-ttu-id="cf7c3-105">클래스에는 참조 형식 이라는 이점이-참조를 전달 하는 것은 해당 데이터를 모두 사용 하 여 구조체 변수를 전달 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-105">Classes have the advantage of being reference types — passing a reference is more efficient than passing a structure variable with all its data.</span></span> <span data-ttu-id="cf7c3-106">반면에 구조는 메모리는 전역 힙에 할당이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-106">On the other hand, structures do not require allocation of memory on the global heap.</span></span>  
  
 <span data-ttu-id="cf7c3-107">구조체를 상속할 수 없습니다 확장할 필요 하지 않은 개체에 대해서만 구조를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-107">Because you cannot inherit from a structure, structures should be used only for objects that do not need to be extended.</span></span> <span data-ttu-id="cf7c3-108">만들려는 개체 소규모 인스턴스 크기가 고 구조체와 클래스의 성능 특성을 고려 하는 경우에 구조를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-108">Use structures when the object you wish to create has a small instance size, and take into account the performance characteristics of classes versus structures.</span></span>  
  
## <a name="similarities"></a><span data-ttu-id="cf7c3-109">유사점</span><span class="sxs-lookup"><span data-stu-id="cf7c3-109">Similarities</span></span>  
 <span data-ttu-id="cf7c3-110">구조체와 클래스에는 다음과 같은 점에서 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-110">Structures and classes are similar in the following respects:</span></span>  
  
-   <span data-ttu-id="cf7c3-111">둘 다 *컨테이너* 형식, 다른 형식을 멤버로 포함 되어 있는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-111">Both are *container* types, meaning that they contain other types as members.</span></span>  
  
-   <span data-ttu-id="cf7c3-112">둘 다에 생성자, 메서드, 속성, 필드, 상수, 열거형, 이벤트 및 이벤트 처리기를 포함할 수 있는 멤버를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-112">Both have members, which can include constructors, methods, properties, fields, constants, enumerations, events, and event handlers.</span></span> <span data-ttu-id="cf7c3-113">그러나 이러한 멤버는 선언 된와 혼동 하지 마십시오 *요소* 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-113">However, do not confuse these members with the declared *elements* of a structure.</span></span>  
  
-   <span data-ttu-id="cf7c3-114">둘 다의 구성원에는 액세스 수준을 개별화 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-114">Members of both can have individualized access levels.</span></span> <span data-ttu-id="cf7c3-115">예를 들어 하나의 멤버를 선언할 수 있습니다 `Public` 및 다른 `Private`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-115">For example, one member can be declared `Public` and another `Private`.</span></span>  
  
-   <span data-ttu-id="cf7c3-116">두 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-116">Both can implement interfaces.</span></span>  
  
-   <span data-ttu-id="cf7c3-117">둘 다 사용 하거나 매개 변수 없이 공유 생성자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-117">Both can have shared constructors, with or without parameters.</span></span>  
  
-   <span data-ttu-id="cf7c3-118">모두 노출할 수는 *기본 속성*속성은 하나 이상의 매개 변수는 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-118">Both can expose a *default property*, provided that property takes at least one parameter.</span></span>  
  
-   <span data-ttu-id="cf7c3-119">둘 다를 선언 하 고 이벤트를 발생 시킬 수 및 대리자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-119">Both can declare and raise events, and both can declare delegates.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="cf7c3-120">차이점</span><span class="sxs-lookup"><span data-stu-id="cf7c3-120">Differences</span></span>  
 <span data-ttu-id="cf7c3-121">구조체와 클래스는 다음과 같은 점에서 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-121">Structures and classes differ in the following particulars:</span></span>  
  
-   <span data-ttu-id="cf7c3-122">구조체는 *값 형식이*; 클래스는 *참조 형식*합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-122">Structures are *value types*; classes are *reference types*.</span></span> <span data-ttu-id="cf7c3-123">클래스 형식으로 데이터에 대 한 참조를 포함 하는 하지 않고 구조체의 데이터를 포함 하는 구조체 형식의 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-123">A variable of a structure type contains the structure's data, rather than containing a reference to the data as a class type does.</span></span>  
  
-   <span data-ttu-id="cf7c3-124">스택 할당;를 사용 하는 구조체 클래스는 힙 할당을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-124">Structures use stack allocation; classes use heap allocation.</span></span>  
  
-   <span data-ttu-id="cf7c3-125">구조체 요소는 모두 `Public` 기본적으로 클래스 변수 및 상수는 `Private` 다른 클래스 멤버는 기본적으로 `Public` 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-125">All structure elements are `Public` by default; class variables and constants are `Private` by default, while other class members are `Public` by default.</span></span> <span data-ttu-id="cf7c3-126">이 동작은 클래스 멤버에 대 한 기본값의 Visual Basic 6.0 시스템와의 호환성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-126">This behavior for class members provides compatibility with the Visual Basic 6.0 system of defaults.</span></span>  
  
-   <span data-ttu-id="cf7c3-127">구조체에는 하나 이상의 비공유 변수 또는 비공유, 사용자를 사용 해야 합니다. 이벤트 요소입니다. 클래스는 완전히 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-127">A structure must have at least one nonshared variable or nonshared, noncustom event element; a class can be completely empty.</span></span>  
  
-   <span data-ttu-id="cf7c3-128">구조 요소로 선언할 수 없습니다 `Protected`; 클래스 멤버 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-128">Structure elements cannot be declared as `Protected`; class members can.</span></span>  
  
-   <span data-ttu-id="cf7c3-129">구조체 프로시저에서는 경우에 이벤트를 처리할 수는 [공유](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` 프로시저 및만 방법으로 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md); 클래스는 모든 프로시저 중 하나를 사용 하 여 이벤트를 처리할 수는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 키워드 또는 `AddHandler` 문.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-129">A structure procedure can handle events only if it is a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure, and only by means of the [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md); any class procedure can handle events, using either the [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) keyword or the `AddHandler` statement.</span></span> <span data-ttu-id="cf7c3-130">자세한 내용은 참조 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-130">For more information, see [Events](../../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
-   <span data-ttu-id="cf7c3-131">구조체 변수 선언 이니셜라이저 또는; 배열의 초기 크기를 지정할 수 없습니다. 변수 선언 클래스는 다음 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-131">Structure variable declarations cannot specify initializers or initial sizes for arrays; class variable declarations can.</span></span>  
  
-   <span data-ttu-id="cf7c3-132">구조에서 암시적으로 상속는 <xref:System.ValueType?displayProperty=fullName>클래스 및 다른 모든 형식;에서 상속할 수 없는 클래스 또는 <xref:System.ValueType?displayProperty=fullName>.</xref:System.ValueType?displayProperty=fullName> 이외의 클래스에서 상속할 수 있습니다</xref:System.ValueType?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="cf7c3-132">Structures implicitly inherit from the <xref:System.ValueType?displayProperty=fullName> class and cannot inherit from any other type; classes can inherit from any class or classes other than <xref:System.ValueType?displayProperty=fullName>.</span></span>  
  
-   <span data-ttu-id="cf7c3-133">구조체가 상속할 수 있습니다. 클래스는입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-133">Structures are not inheritable; classes are.</span></span>  
  
-   <span data-ttu-id="cf7c3-134">구조는 절대 종료 되지 않으므로 공용 언어 런타임 (CLR)를 호출 하지 않습니다는 <xref:System.Object.Finalize%2A>모든 구조; 메서드 클래스를 호출 하는 가비지 수집기 (GC)에 의해 종료 됩니다 <xref:System.Object.Finalize%2A>남은 활성 참조가 없는 것을 발견 하면 클래스에.</xref:System.Object.Finalize%2A> </xref:System.Object.Finalize%2A></span><span class="sxs-lookup"><span data-stu-id="cf7c3-134">Structures are never terminated, so the common language runtime (CLR) never calls the <xref:System.Object.Finalize%2A> method on any structure; classes are terminated by the garbage collector (GC), which calls <xref:System.Object.Finalize%2A> on a class when it detects there are no active references remaining.</span></span>  
  
-   <span data-ttu-id="cf7c3-135">구조체는 생성자; 필요 하지 않습니다. 클래스는 다음 작업을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-135">A structure does not require a constructor; a class does.</span></span>  
  
-   <span data-ttu-id="cf7c3-136">구조체는 포함할 수 매개 변수를 사용 하는 경우에 비공유 생성자 클래스는 또는 매개 변수 없이 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-136">Structures can have nonshared constructors only if they take parameters; classes can have them with or without parameters.</span></span>  
  
 <span data-ttu-id="cf7c3-137">모든 구조에는 매개 변수 없이 암시적인 공용 생성자를 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-137">Every structure has an implicit public constructor without parameters.</span></span> <span data-ttu-id="cf7c3-138">이 생성자는 구조체의 모든 데이터 요소를를 기본값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-138">This constructor initializes all the structure's data elements to their default values.</span></span> <span data-ttu-id="cf7c3-139">이 동작을 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-139">You cannot redefine this behavior.</span></span>  
  
## <a name="instances-and-variables"></a><span data-ttu-id="cf7c3-140">인스턴스 및 변수</span><span class="sxs-lookup"><span data-stu-id="cf7c3-140">Instances and Variables</span></span>  
 <span data-ttu-id="cf7c3-141">구조는 값 형식 이므로 각 구조체 변수 개별 구조체 인스턴스에 영구적으로 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-141">Because structures are value types, each structure variable is permanently bound to an individual structure instance.</span></span> <span data-ttu-id="cf7c3-142">하지만 클래스는 참조 형식 및 개체 변수에 서로 다른 시간에 다양 한 클래스 인스턴스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-142">But classes are reference types, and an object variable can refer to various class instances at different times.</span></span> <span data-ttu-id="cf7c3-143">이러한 차이점으로이 인해 다음과 같은 방법으로 구조체 및 클래스의 사용 현황을 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-143">This distinction affects your usage of structures and classes in the following ways:</span></span>  
  
-   <span data-ttu-id="cf7c3-144">**초기화 합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf7c3-144">**Initialization.**</span></span> <span data-ttu-id="cf7c3-145">구조체 변수 구조체의 매개 변수가 없는 생성자를 사용 하 여 요소의 초기화가 암시적으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-145">A structure variable implicitly includes an initialization of the elements using the structure's parameterless constructor.</span></span> <span data-ttu-id="cf7c3-146">따라서 `Dim s As struct1` 같습니다 `Dim s As struct1 = New struct1()`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-146">Therefore, `Dim s As struct1` is equivalent to `Dim s As struct1 = New struct1()`.</span></span>  
  
-   <span data-ttu-id="cf7c3-147">**변수를 지정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf7c3-147">**Assigning Variables.**</span></span> <span data-ttu-id="cf7c3-148">다른 구조체 변수를 할당 하거나 구조체 인스턴스 프로시저 인수를 전달할 때 모든 변수 요소의 현재 값을 새 구조로 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-148">When you assign one structure variable to another, or pass a structure instance to a procedure argument, the current values of all the variable elements are copied to the new structure.</span></span> <span data-ttu-id="cf7c3-149">다른 개체 변수 할당 또는 프로시저에는 개체 변수를 전달 하는 경우 참조 포인터가 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-149">When you assign one object variable to another, or pass an object variable to a procedure, only the reference pointer is copied.</span></span>  
  
-   <span data-ttu-id="cf7c3-150">**아무 것도 할당 합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf7c3-150">**Assigning Nothing.**</span></span> <span data-ttu-id="cf7c3-151">값을 할당할 수 [Nothing](../../../../visual-basic/language-reference/nothing.md) 구조에 인스턴스가 되지만 변수를 계속 해 서 변수와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-151">You can assign the value [Nothing](../../../../visual-basic/language-reference/nothing.md) to a structure variable, but the instance continues to be associated with the variable.</span></span> <span data-ttu-id="cf7c3-152">해당 메서드를 호출 하 고 변수 요소가 할당 하 여 다시 초기화 하는 있지만 해당 데이터 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-152">You can still call its methods and access its data elements, although variable elements are reinitialized by the assignment.</span></span>  
  
     <span data-ttu-id="cf7c3-153">반대로, 개체 변수를 설정 하면 `Nothing`클래스 인스턴스에서 분리 하 고 다른 인스턴스를 할당할 때까지 변수를 통해 모든 멤버를 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-153">In contrast, if you set an object variable to `Nothing`, you dissociate it from any class instance, and you cannot access any members through the variable until you assign another instance to it.</span></span>  
  
-   <span data-ttu-id="cf7c3-154">**여러 개의 인스턴스입니다.**</span><span class="sxs-lookup"><span data-stu-id="cf7c3-154">**Multiple Instances.**</span></span> <span data-ttu-id="cf7c3-155">개체 변수는 서로 다른 시간에 할당 된 다른 클래스 인스턴스를 가질 수와 동시에 여러 개의 개체 변수가 동일한 클래스 인스턴스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-155">An object variable can have different class instances assigned to it at different times, and several object variables can refer to the same class instance at the same time.</span></span> <span data-ttu-id="cf7c3-156">클래스 멤버의 값에 수행한 변경 내용을 동일한 인스턴스를 가리키는 다른 변수를 통해 액세스할 때 해당 멤버를 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-156">Changes you make to the values of class members affect those members when accessed through another variable pointing to the same instance.</span></span>  
  
     <span data-ttu-id="cf7c3-157">그러나 구조 요소는 자체 인스턴스 내에 격리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-157">Structure elements, however, are isolated within their own instance.</span></span> <span data-ttu-id="cf7c3-158">값으로 변경 같은 다른 인스턴스에 있는 변수를 포함 하 여 다른 구조체 변수에 반영 되지 않습니다 `Structure` 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-158">Changes to their values are not reflected in any other structure variables, even in other instances of the same `Structure` declaration.</span></span>  
  
-   <span data-ttu-id="cf7c3-159">**같음입니다.**</span><span class="sxs-lookup"><span data-stu-id="cf7c3-159">**Equality.**</span></span> <span data-ttu-id="cf7c3-160">두 구조체의 같음 테스트를 요소 별로 테스트와 함께 수행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7c3-160">Equality testing of two structures must be performed with an element-by-element test.</span></span> <span data-ttu-id="cf7c3-161">두 개체 변수를 사용 하 여 비교할 수는 <xref:System.Object.Equals%2A>메서드.</xref:System.Object.Equals%2A></span><span class="sxs-lookup"><span data-stu-id="cf7c3-161">Two object variables can be compared using the <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="cf7c3-162"><xref:System.Object.Equals%2A>두 변수의 같은 인스턴스를 가리키는지 여부를 나타냅니다.</xref:System.Object.Equals%2A></span><span class="sxs-lookup"><span data-stu-id="cf7c3-162"><xref:System.Object.Equals%2A> indicates whether the two variables point to the same instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7c3-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf7c3-163">See Also</span></span>  
 <span data-ttu-id="cf7c3-164">[데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf7c3-164">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="cf7c3-165"> [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="cf7c3-165"> [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
<span data-ttu-id="cf7c3-166"> [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="cf7c3-166"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="cf7c3-167"> [구조](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span><span class="sxs-lookup"><span data-stu-id="cf7c3-167"> [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md) </span></span>  
<span data-ttu-id="cf7c3-168"> [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="cf7c3-168"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="cf7c3-169"> [구조체 및 기타 프로그래밍 요소](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md) </span><span class="sxs-lookup"><span data-stu-id="cf7c3-169"> [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md) </span></span>  
<span data-ttu-id="cf7c3-170"> [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span><span class="sxs-lookup"><span data-stu-id="cf7c3-170"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span></span>
