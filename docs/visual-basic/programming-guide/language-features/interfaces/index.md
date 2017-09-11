---
title: "인터페이스(Visual Basic)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, interfaces
- interfaces, Visual Basic
- interfaces
- interfaces [Visual Basic]
ms.assetid: 61b06674-12c9-430b-be68-cc67ecee1f5b
caps.latest.revision: 11
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
ms.translationtype: HT
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: 0b3f13cd69564a61da1a961e35c5319e4c2d79aa
ms.contentlocale: ko-kr
ms.lasthandoff: 08/11/2017

---
# <a name="interfaces-visual-basic"></a><span data-ttu-id="7c04c-102">인터페이스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c04c-102">Interfaces (Visual Basic)</span></span>
<span data-ttu-id="7c04c-103">*인터페이스*는 클래스가 구현할 수 있는 속성, 메서드 및 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-103">*Interfaces* define the properties, methods, and events that classes can implement.</span></span> <span data-ttu-id="7c04c-104">인터페이스를 사용하면 기능을 밀접한 관련이 있는 속성, 메서드, 이벤트 등의 작은 그룹으로 정의할 수 있습니다. 이렇게 하면 기존 코드를 그대로 사용하여 인터페이스에 대한 고급 구현을 개발할 수 있기 때문에 호환성 문제가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-104">Interfaces allow you to define features as small groups of closely related properties, methods, and events; this reduces compatibility problems because you can develop enhanced implementations for your interfaces without jeopardizing existing code.</span></span> <span data-ttu-id="7c04c-105">추가적인 인터페이스와 구현을 개발하여 언제든지 새로운 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-105">You can add new features at any time by developing additional interfaces and implementations.</span></span>  
  
 <span data-ttu-id="7c04c-106">클래스를 상속하는 대신 인터페이스를 사용해야 하는 몇 가지 다른 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-106">There are several other reasons why you might want to use interfaces instead of class inheritance:</span></span>  
  
-   <span data-ttu-id="7c04c-107">인터페이스는 특정 기능을 제공하기 위해 무관할 수 있는 다수의 개체 형식이 응용 프로그램에서 요구되는 경우에 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-107">Interfaces are better suited to situations in which your applications require many possibly unrelated object types to provide certain functionality.</span></span>  
  
-   <span data-ttu-id="7c04c-108">인터페이스는 다중 인터페이스를 구현하는 단일 구현을 정의할 수 있기 때문에 기본 클래스보다 더 유연합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-108">Interfaces are more flexible than base classes because you can define a single implementation that can implement multiple interfaces.</span></span>  
  
-   <span data-ttu-id="7c04c-109">인터페이스는 기본 클래스로부터 구현을 상속할 필요가 없는 경우에 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-109">Interfaces are better in situations in which you do not have to inherit implementation from a base class.</span></span>  
  
-   <span data-ttu-id="7c04c-110">인터페이스는 클래스 상속을 사용할 수 없는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-110">Interfaces are useful when you cannot use class inheritance.</span></span> <span data-ttu-id="7c04c-111">예를 들어 구조체는 클래스에서 상속할 수 없지만 인터페이스를 구현할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-111">For example, structures cannot inherit from classes, but they can implement interfaces.</span></span>  
  
## <a name="declaring-interfaces"></a><span data-ttu-id="7c04c-112">인터페이스 선언</span><span class="sxs-lookup"><span data-stu-id="7c04c-112">Declaring Interfaces</span></span>  
 <span data-ttu-id="7c04c-113">인터페이스 정의는 `Interface` 및 `End Interface` 문 내에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-113">Interface definitions are enclosed within the `Interface` and `End Interface` statements.</span></span> <span data-ttu-id="7c04c-114">`Interface` 문 다음에, 하나 이상의 상속된 인터페이스를 나열하는 `Inherits` 문을 선택적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-114">Following the `Interface` statement, you can add an optional `Inherits` statement that lists one or more inherited interfaces.</span></span> <span data-ttu-id="7c04c-115">`Inherits` 문은 선언에서 주석을 제외하고는 다른 모든 문 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-115">The `Inherits` statements must precede all other statements in the declaration except comments.</span></span> <span data-ttu-id="7c04c-116">인터페이스 정의에 나오는 나머지 문은 `Event`, `Sub`, `Function`, `Property`, `Interface`, `Class`, `Structure` 및 `Enum` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-116">The remaining statements in the interface definition should be `Event`, `Sub`, `Function`, `Property`, `Interface`, `Class`, `Structure`, and `Enum` statements.</span></span> <span data-ttu-id="7c04c-117">인터페이스는 구현 코드 또는 구현 코드와 관련된 문(예: `End Sub` 또는 `End Property`)을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-117">Interfaces cannot contain any implementation code or statements associated with implementation code, such as `End Sub` or `End Property`.</span></span>  
  
 <span data-ttu-id="7c04c-118">네임스페이스에서 인터페이스 문은 기본적으로 `Friend`이지만 `Public` 또는 `Friend`로 명시적으로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-118">In a namespace, interface statements are `Friend` by default, but they can also be explicitly declared as `Public` or `Friend`.</span></span> <span data-ttu-id="7c04c-119">클래스, 모듈, 인터페이스 및 구조체 내에서 정의되는 인터페이스는 기본적으로 `Public`이지만 `Public`, `Friend`, `Protected` 또는 `Private`으로 명시적으로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-119">Interfaces defined within classes, modules, interfaces, and structures are `Public` by default, but they can also be explicitly declared as `Public`, `Friend`, `Protected`, or `Private`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c04c-120">`Shadows` 키워드는 모든 인터페이스 멤버에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-120">The `Shadows` keyword can be applied to all interface members.</span></span> <span data-ttu-id="7c04c-121">`Overloads` 키워드는 인터페이스 정의에서 정의되는 `Sub`, `Function` 및 `Property` 문에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-121">The `Overloads` keyword can be applied to `Sub`, `Function`, and `Property` statements declared in an interface definition.</span></span> <span data-ttu-id="7c04c-122">또한 `Property` 문은 `Default`, `ReadOnly` 또는 `WriteOnly` 한정자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-122">In addition, `Property` statements can have the `Default`, `ReadOnly`, or `WriteOnly` modifiers.</span></span> <span data-ttu-id="7c04c-123">`Public`, `Private`, `Friend`, `Protected`, `Shared`, `Overrides`, `MustOverride` 또는 `Overridable` 등의 다른 한정자는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-123">None of the other modifiers—`Public`, `Private`, `Friend`, `Protected`, `Shared`, `Overrides`, `MustOverride`, or `Overridable`—are allowed.</span></span> <span data-ttu-id="7c04c-124">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c04c-124">For more information, see [Declaration Contexts and Default Access Levels](../../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="7c04c-125">예를 들어 다음 코드는 하나의 함수, 하나의 속성, 하나의 이벤트가 있는 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-125">For example, the following code defines an interface with one function, one property, and one event.</span></span>  
  
 <span data-ttu-id="7c04c-126">[!code-vb[VbVbalrOOP#17](../../../../visual-basic/misc/codesnippet/VisualBasic/index_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c04c-126">[!code-vb[VbVbalrOOP#17](../../../../visual-basic/misc/codesnippet/VisualBasic/index_1.vb)]</span></span>  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="7c04c-127">인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="7c04c-127">Implementing Interfaces</span></span>  
 <span data-ttu-id="7c04c-128">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 예약어인 `Implements`는 두 가지 방법으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-128">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] reserved word `Implements` is used in two ways.</span></span> <span data-ttu-id="7c04c-129">`Implements` 문은 클래스 또는 구조체가 인터페이스를 구현한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-129">The `Implements` statement signifies that a class or structure implements an interface.</span></span> <span data-ttu-id="7c04c-130">`Implements` 키워드는 클래스 멤버 또는 구조체 멤버가 특정 인터페이스 멤버를 구현한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-130">The `Implements` keyword signifies that a class member or structure member implements a specific interface member.</span></span>  
  
### <a name="implements-statement"></a><span data-ttu-id="7c04c-131">Implements 문</span><span class="sxs-lookup"><span data-stu-id="7c04c-131">Implements Statement</span></span>  
 <span data-ttu-id="7c04c-132">하나 이상의 인터페이스를 구현하는 클래스 또는 구조체에는 `Class` 또는 `Structure` 문 바로 다음에 `Implements`문이 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-132">If a class or structure implements one or more interfaces, it must include the `Implements` statement immediately after the `Class` or `Structure` statement.</span></span> <span data-ttu-id="7c04c-133">`Implements` 문에는 클래스에 의해 구현될 인터페이스를 나열한, 쉼표로 구분된 목록이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-133">The `Implements` statement requires a comma-separated list of interfaces to be implemented by a class.</span></span> <span data-ttu-id="7c04c-134">클래스 또는 구조체는 `Implements` 키워드를 사용하여 모든 인터페이스 멤버를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-134">The class or structure must implement all interface members using the `Implements` keyword.</span></span>  
  
### <a name="implements-keyword"></a><span data-ttu-id="7c04c-135">Implements 키워드</span><span class="sxs-lookup"><span data-stu-id="7c04c-135">Implements Keyword</span></span>  
 <span data-ttu-id="7c04c-136">`Implements` 키워드에는 구현될 인터페이스 멤버를 나열한, 쉼표로 구분된 목록이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-136">The `Implements` keyword requires a comma-separated list of interface members to be implemented.</span></span> <span data-ttu-id="7c04c-137">일반적으로 단일 인터페이스 멤버만 지정되지만 여러 멤버를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-137">Generally, only a single interface member is specified, but you can specify multiple members.</span></span> <span data-ttu-id="7c04c-138">인터페이스 멤버의 사양은 인터페이스 이름(클래스 내의 implements 문에서 지정해야 함)과 기간 및 구현할 멤버 함수, 속성 또는 이벤트의 이름으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-138">The specification of an interface member consists of the interface name, which must be specified in an implements statement within the class; a period; and the name of the member function, property, or event to be implemented.</span></span> <span data-ttu-id="7c04c-139">인터페이스 멤버를 구현하는 멤버의 이름에는 유효한 식별자를 사용할 수 있으며, 이는 이전 버전의 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 사용되는 `InterfaceName_MethodName` 규칙에 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-139">The name of a member that implements an interface member can use any legal identifier, and it is not limited to the `InterfaceName_MethodName` convention used in earlier versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="7c04c-140">예를 들어 다음 코드에서는 인터페이스의 메서드를 구현하는 `Sub1`이라는 서브루틴을 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-140">For example, the following code shows how to declare a subroutine named `Sub1` that implements a method of an interface:</span></span>  
  
 <span data-ttu-id="7c04c-141">[!code-vb[VbVbalrOOP#69](../../../../visual-basic/misc/codesnippet/VisualBasic/index_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c04c-141">[!code-vb[VbVbalrOOP#69](../../../../visual-basic/misc/codesnippet/VisualBasic/index_2.vb)]</span></span>  
  
 <span data-ttu-id="7c04c-142">구현 멤버의 매개 변수 형식 및 반환 형식은 인터페이스의 인터페이스 속성 또는 멤버 선언과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-142">The parameter types and return types of the implementing member must match the interface property or member declaration in the interface.</span></span> <span data-ttu-id="7c04c-143">인터페이스의 요소를 구현하는 가장 일반적인 방법은 이전 예제와 같이 인터페이스와 이름이 같은 멤버를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-143">The most common way to implement an element of an interface is with a member that has the same name as the interface, as shown in the previous example.</span></span>  
  
 <span data-ttu-id="7c04c-144">인터페이스 메서드의 구현을 선언하려면 인스턴스 메서드 선언에 `Overloads`, `Overrides`, `Overridable`, `Public`, `Private`, `Protected`, `Friend`, `Protected Friend`, `MustOverride`, `Default`, `Static` 등의 유효한 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-144">To declare the implementation of an interface method, you can use any attributes that are legal on instance method declarations, including `Overloads`, `Overrides`, `Overridable`, `Public`, `Private`, `Protected`, `Friend`, `Protected Friend`, `MustOverride`, `Default`, and `Static`.</span></span> <span data-ttu-id="7c04c-145">`Shared` 특성은 인스턴스 메서드가 아니라 클래스를 정의하므로 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-145">The `Shared` attribute is not legal since it defines a class rather than an instance method.</span></span>  
  
 <span data-ttu-id="7c04c-146">`Implements`를 사용하여 다음 예제와 같이 인터페이스에서 정의된 여러 메서드를 구현하는 단일 메서드를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-146">Using `Implements`, you can also write a single method that implements multiple methods defined in an interface, as in the following example:</span></span>  
  
 <span data-ttu-id="7c04c-147">[!code-vb[VbVbalrOOP#70](../../../../visual-basic/misc/codesnippet/VisualBasic/index_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c04c-147">[!code-vb[VbVbalrOOP#70](../../../../visual-basic/misc/codesnippet/VisualBasic/index_3.vb)]</span></span>  
  
 <span data-ttu-id="7c04c-148">전용 멤버를 사용하여 인터페이스 멤버를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-148">You can use a private member to implement an interface member.</span></span> <span data-ttu-id="7c04c-149">전용 멤버가 인터페이스의 멤버를 구현하는 경우 이 멤버는 클래스에 대한 개체 변수에 대해 직접 사용할 수 없더라도 인터페이스를 통해 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-149">When a private member implements a member of an interface, that member becomes available by way of the interface even though it is not available directly on object variables for the class.</span></span>  
  
### <a name="interface-implementation-examples"></a><span data-ttu-id="7c04c-150">인터페이스 구현 예제</span><span class="sxs-lookup"><span data-stu-id="7c04c-150">Interface Implementation Examples</span></span>  
 <span data-ttu-id="7c04c-151">인터페이스를 구현하는 클래스는 모든 속성, 메서드 및 이벤트를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-151">Classes that implement an interface must implement all its properties, methods, and events.</span></span>  
  
 <span data-ttu-id="7c04c-152">다음 예제에서는 두 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-152">The following example defines two interfaces.</span></span> <span data-ttu-id="7c04c-153">두 번째 인터페이스인 `Interface2`는 `Interface1`을 상속하며 추가 속성 및 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-153">The second interface, `Interface2`, inherits `Interface1` and defines an additional property and method.</span></span>  
  
 <span data-ttu-id="7c04c-154">[!code-vb[VbVbalrOOP#39](../../../../visual-basic/misc/codesnippet/VisualBasic/index_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c04c-154">[!code-vb[VbVbalrOOP#39](../../../../visual-basic/misc/codesnippet/VisualBasic/index_4.vb)]</span></span>  
  
 <span data-ttu-id="7c04c-155">다음 예제에서는 이전 예제에서 정의된 인터페이스인 `Interface1`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-155">The next example implements `Interface1`, the interface defined in the previous example:</span></span>  
  
 <span data-ttu-id="7c04c-156">[!code-vb[VbVbalrOOP#40](../../../../visual-basic/misc/codesnippet/VisualBasic/index_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c04c-156">[!code-vb[VbVbalrOOP#40](../../../../visual-basic/misc/codesnippet/VisualBasic/index_5.vb)]</span></span>  
  
 <span data-ttu-id="7c04c-157">마지막 예제에서는 `Interface1`에서 상속된 메서드를 포함하여 `Interface2`를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-157">The final example implements `Interface2`, including a method inherited from `Interface1`:</span></span>  
  
 <span data-ttu-id="7c04c-158">[!code-vb[VbVbalrOOP#41](../../../../visual-basic/misc/codesnippet/VisualBasic/index_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c04c-158">[!code-vb[VbVbalrOOP#41](../../../../visual-basic/misc/codesnippet/VisualBasic/index_6.vb)]</span></span>  
  
 <span data-ttu-id="7c04c-159">읽기/쓰기 속성을 사용하여 읽기 전용 속성을 구현할 수 있습니다(즉, 구현 클래스에서 읽기 전용으로 선언할 필요가 없음).</span><span class="sxs-lookup"><span data-stu-id="7c04c-159">You can implement a readonly property with a readwrite property (that is, you do not have to declare it readonly in the implementing class).</span></span>  <span data-ttu-id="7c04c-160">인터페이스를 선언하면 최소한 이 인터페이스가 선언하는 멤버가 구현됩니다. 하지만 속성을 쓰기 가능하도록 허용하는 등, 더 많은 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-160">Implementing an interface promises to implement at least the members that the interface declares, but you can offer more functionality, such as allowing your property to be writable.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="7c04c-161">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7c04c-161">Related Topics</span></span>  
  
|<span data-ttu-id="7c04c-162">제목</span><span class="sxs-lookup"><span data-stu-id="7c04c-162">Title</span></span>|<span data-ttu-id="7c04c-163">설명</span><span class="sxs-lookup"><span data-stu-id="7c04c-163">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7c04c-164">연습: 인터페이스 만들기 및 구현</span><span class="sxs-lookup"><span data-stu-id="7c04c-164">Walkthrough: Creating and Implementing Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/walkthrough-creating-and-implementing-interfaces.md)|<span data-ttu-id="7c04c-165">고유한 인터페이스를 정의하고 구현하는 프로세스를 안내하는 자세한 절차를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-165">Provides a detailed procedure that takes you through the process of defining and implementing your own interface.</span></span>|  
|[<span data-ttu-id="7c04c-166">제네릭 인터페이스의 가변성</span><span class="sxs-lookup"><span data-stu-id="7c04c-166">Variance in Generic Interfaces</span></span>](../../concepts/covariance-contravariance/variance-in-generic-interfaces.md)|<span data-ttu-id="7c04c-167">제네릭 인터페이스의 공분산 및 반공분산에 대해 설명하고 .NET Framework의 Variant 제네릭 인터페이스의 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c04c-167">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|

