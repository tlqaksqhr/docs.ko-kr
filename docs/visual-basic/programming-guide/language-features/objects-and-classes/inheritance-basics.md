---
title: "상속 기본 사항 (Visual Basic) | Microsoft 문서"
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
- derived classes, inheritance
- MyClass keyword, using
- MyBase keyword, using
- Inherits statement, inheritance
- overriding, Overridable keyword
- MustInherit keyword, using
- Overrides keyword, using
- inheritance
- MustInherit classes
- MustOverride keyword, using
- classes [Visual Basic], derived
- NotInheritable keyword, using
- base classes, extending properties and methods
- NotOverridable keyword, using
- base classes, inheritance
- abstract classes, inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
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
ms.sourcegitcommit: 4892ed6dcfb3843bd6cb2de2d3e032bfeb1efdf9
ms.openlocfilehash: 43b6505634b12f7f8353866e938151f1e00fb073
ms.contentlocale: ko-kr
ms.lasthandoff: 05/16/2017

---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="2479a-102">상속 기본 사항(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2479a-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="2479a-103">`Inherits` 문을 사용 하 라는 새 클래스를 선언 하는 *파생 클래스*라고 하는 기존 클래스에 따라 한 *기본 클래스*합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="2479a-104">파생된 클래스는 상속 하 고 속성, 메서드, 이벤트, 필드 및 기본 클래스에 정의 된 상수 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="2479a-105">상속에 대 한 규칙 중 일부는 다음 섹션에서는 및 방식으로 클래스를 변경 하는 데 한정자 상속 하거나 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="2479a-106">기본적으로 모든 클래스는 상속할 수로 표시 하지 않는 한는 `NotInheritable` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="2479a-107">클래스는 프로젝트의 다른 클래스 또는 프로젝트가 참조 하는 다른 어셈블리의 클래스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="2479a-108">다중 상속을 허용 하는 언어와 달리 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 클래스;에 단일 상속을 사용 하면 파생 된 클래스 즉, 하나의 기본 클래스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-108">Unlike languages that allow multiple inheritance, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="2479a-109">다중 상속 클래스에 허용 되지 않습니다 하지만 클래스에는 같은 결과 효과적으로 얻을 수 있는 여러 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="2479a-110">기본 클래스의 제한 된 항목을 공개를 방지 하려면 파생된 클래스의 액세스 형식을 같은 경우 또는 기본 클래스 보다 더 제한적인 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="2479a-111">예를 들어 한 `Public` 클래스에서 상속할 수 없습니다는 `Friend` 또는 `Private` 클래스 및 `Friend` 클래스에서 상속할 수 없습니다는 `Private` 클래스.</span><span class="sxs-lookup"><span data-stu-id="2479a-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="2479a-112">상속 한정자</span><span class="sxs-lookup"><span data-stu-id="2479a-112">Inheritance Modifiers</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="2479a-113">에서는 다음 클래스 수준의 문과 한정자를 상속을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-113"> introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="2479a-114">`Inherits`문-기본 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="2479a-115">`NotInheritable`한정자-프로그래머를 기본 클래스로 클래스를 사용 하는 것을 금지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="2479a-116">`MustInherit`한정자-하는 클래스 사용 하기 위한 기본 클래스로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="2479a-117">인스턴스 `MustInherit` 클래스를 직접 만들 수 없습니다; 만들 수 있습니다만 파생된 클래스의 클래스 인스턴스를 기본으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="2479a-118">(이라는 용어를 사용 하는 c + + 및 C#과 같은 다른 프로그래밍 언어에서는 *추상 클래스* 이러한 클래스를 설명 합니다.)</span><span class="sxs-lookup"><span data-stu-id="2479a-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="2479a-119">파생된 클래스의 속성 및 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="2479a-120">기본적으로 파생된 클래스는 기본 클래스에서 속성 및 메서드 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="2479a-121">상속 된 속성 또는 메서드는 파생된 클래스에서 다르게 동작 하는 경우 일 수 있습니다 *재정의*합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="2479a-122">즉, 파생된 클래스에서 메서드의 새로운 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="2479a-123">다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="2479a-124">`Overridable`-파생된 클래스에서 재정의 해야 하는 클래스에서 속성 또는 메서드의 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="2479a-125">`Overrides`-재정의 `Overridable` 속성이 나 메서드의 기본 클래스에서 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="2479a-126">`NotOverridable`-상속 클래스에서 재정의 되는 속성 또는 메서드 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="2479a-127">기본적으로 `Public` 메서드는 `NotOverridable`합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="2479a-128">`MustOverride`-파생된 클래스에서 속성 또는 메서드를 재정의 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="2479a-129">때는 `MustOverride` 키워드가 사용 되는지, 메서드 정의의 구성만 `Sub`, `Function`, 또는 `Property` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="2479a-130">다른 문이 허용 여부와 특별히 없습니다 `End Sub` 또는 `End Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="2479a-131">`MustOverride`메서드를 선언 해야 `MustInherit` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="2479a-132">급여를 처리 하는 클래스를 정의 하려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="2479a-133">일반을 정의할 수 있습니다 `Payroll` 클래스를 포함 하는 `RunPayroll` 일반적인 주에 대 한 급여를 계산 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="2479a-134">사용 하 여 수 `Payroll` 좀 더 특수 한 작업에 대 한 기본 클래스로 `BonusPayroll` 직원에 게 보너스를 배포 하는 경우 사용할 수 있는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="2479a-135">`BonusPayroll` 클래스를 상속 하 고 재정의할 수는 `PayEmployee` 자료에 정의 된 메서드 `Payroll` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="2479a-136">다음 예제에서는 기본 클래스를 정의 `Payroll,` 및 파생된 클래스가 `BonusPayroll`, 상속된 된 메서드를 재정의 하 `PayEmployee`합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="2479a-137">프로시저 `RunPayroll`을 만들고 다음 전달는 `Payroll` 개체 및 `BonusPayroll` , 함수 개체 `Pay`, 실행 하는 `PayEmployee` 두 개체의 메서드.</span><span class="sxs-lookup"><span data-stu-id="2479a-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 <span data-ttu-id="2479a-138">[!code-vb[VbVbalrOOP #&28;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2479a-138">[!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]</span></span>  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="2479a-139">MyBase 키워드</span><span class="sxs-lookup"><span data-stu-id="2479a-139">The MyBase Keyword</span></span>  
 <span data-ttu-id="2479a-140">`MyBase` 키워드는 클래스의 현재 인스턴스는 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-140">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="2479a-141">`MyBase`재정의 되거나 파생된 클래스에서 숨겨진 하는 기본 클래스 멤버 액세스를 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-141">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="2479a-142">특히, `MyBase.New` 파생된 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-142">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="2479a-143">예를 들어, 기본 클래스에서 상속 된 메서드를 재정의 하는 파생된 클래스를 디자인 하는 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-143">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="2479a-144">재정의 된 메서드는 기본 클래스에서 메서드를 호출 하 고 다음 코드 조각에서와 같이 반환 값을 수정할 수 있습니다.:</span><span class="sxs-lookup"><span data-stu-id="2479a-144">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 <span data-ttu-id="2479a-145">[!code-vb[VbVbalrOOP #&109;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="2479a-145">[!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]</span></span>  
  
 <span data-ttu-id="2479a-146">사용 하 여 다음 목록에는 제한이 정리 되어 `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="2479a-146">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="2479a-147">`MyBase`직접 기본 클래스와 상속 된 멤버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-147">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="2479a-148">사용할 수 없습니다에 액세스 하려면 `Private` 클래스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-148">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="2479a-149">`MyBase`실제 개체가 아니라 키워드가입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-149">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="2479a-150">`MyBase`변수에 할당, 프로시저에 전달 하거나 사용할 수 없습니다에 `Is` 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-150">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="2479a-151">메서드는 `MyBase` 한정;는 직접 기본 클래스에서 정의 하지 않아도 간접적으로 상속된 하는 기본 클래스에서 대신 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-151">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="2479a-152">지정한 참조가 위해 `MyBase` 올바르게 컴파일하기 위해 일부 기본 클래스 이름 및 호출에 나타나는 매개 변수의 형식과 일치 하는 메서드를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-152">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="2479a-153">사용할 수 없는 `MyBase` 호출할 `MustOverride` 기본 클래스 메서드.</span><span class="sxs-lookup"><span data-stu-id="2479a-153">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="2479a-154">`MyBase`자체를 정하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-154">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="2479a-155">따라서 다음 코드는 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-155">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="2479a-156">`MyBase`모듈에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-156">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="2479a-157">`MyBase`로 표시 된 기본 클래스 멤버 액세스를 사용할 수 없습니다 `Friend` 다른 어셈블리에 기본 클래스는 경우.</span><span class="sxs-lookup"><span data-stu-id="2479a-157">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="2479a-158">자세한 내용 및 다른 예에 대 한 참조 [하는 방법: 파생 클래스에 의해 변수 숨겨진 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-158">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="2479a-159">MyClass 키워드</span><span class="sxs-lookup"><span data-stu-id="2479a-159">The MyClass Keyword</span></span>  
 <span data-ttu-id="2479a-160">`MyClass` 키워드는 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-160">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="2479a-161">`MyClass`유사한 `Me`, 모든 메서드 및 속성에 호출 되지만 `MyClass` 메서드 또는 속성 처럼 처리 됩니다 [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-161">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="2479a-162">따라서 메서드 또는 속성은 영향을 받지 파생된 클래스에서 재정의 하 여.</span><span class="sxs-lookup"><span data-stu-id="2479a-162">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="2479a-163">`MyClass`실제 개체가 아니라 키워드가입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-163">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="2479a-164">`MyClass`변수에 할당, 프로시저에 전달 하거나 사용할 수 없습니다에 `Is` 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-164">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="2479a-165">`MyClass`포함 하는 클래스와 상속 된 멤버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-165">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="2479a-166">`MyClass`에 대 한 한정자로 사용할 수 있습니다 `Shared` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-166">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="2479a-167">`MyClass`내에서 사용할 수 없습니다는 `Shared` 메서드를 되지만 인스턴스 메서드 내에서 사용 하는 클래스의 공유 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-167">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="2479a-168">`MyClass`표준 모듈에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-168">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="2479a-169">`MyClass`데 사용할 수는 기본 클래스에 정의 된 해당 클래스에서 제공 하는 메서드의 구현이 없는 메서드.</span><span class="sxs-lookup"><span data-stu-id="2479a-169">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="2479a-170">이러한 참조는 동일한 의미를 갖는 `MyBase.` *메서드*합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-170">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="2479a-171">다음 예제에서는 비교 `Me` 및 `MyClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-171">The following example compares `Me` and `MyClass`.</span></span>  
  
```vb
Class baseClass  
    Public Overridable Sub testMethod()  
        MsgBox("Base class string")  
    End Sub  
    Public Sub useMe()  
        ' The following call uses the calling class's method, even if   
        ' that method is an override.  
        Me.testMethod()  
    End Sub  
    Public Sub useMyClass()  
        ' The following call uses this instance's method and not any  
        ' override.  
        MyClass.testMethod()  
    End Sub  
End Class  
Class derivedClass : Inherits baseClass  
    Public Overrides Sub testMethod()  
        MsgBox("Derived class string")  
    End Sub  
End Class  
Class testClasses  
    Sub startHere()  
        Dim testObj As derivedClass = New derivedClass()  
        ' The following call displays "Derived class string".  
        testObj.useMe()  
        ' The following call displays "Base class string".  
        testObj.useMyClass()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="2479a-172">경우에 `derivedClass` 재정의 `testMethod`, `MyClass` 키워드 `useMyClass` 재정의 및 컴파일러 확인 한 결과의 기본 클래스 버전에 대 한 호출을 취소 `testMethod`합니다.</span><span class="sxs-lookup"><span data-stu-id="2479a-172">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2479a-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2479a-173">See Also</span></span>  
 <span data-ttu-id="2479a-174">[Inherits 문](../../../../visual-basic/language-reference/statements/inherits-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2479a-174">[Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md) </span></span>  
<span data-ttu-id="2479a-175"> [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="2479a-175"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>

