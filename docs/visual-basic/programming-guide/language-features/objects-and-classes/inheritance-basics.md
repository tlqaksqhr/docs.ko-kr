---
title: 상속 기본 사항(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 9225e5fd9fa35ae06414018a109f66515f99363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655191"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="78afa-102">상속 기본 사항(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78afa-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="78afa-103">`Inherits` 문을 사용 하 라는 새 클래스를 선언 하는 *파생 클래스*라고 하는 기존 클래스에 따라 한 *기본 클래스*합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="78afa-104">파생된 클래스는 상속 하 고 속성, 메서드, 이벤트, 필드 및 기본 클래스에 정의 된 상수 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="78afa-105">다음 섹션에서는 일부의 상속에 대 한 규칙 한 방식으로 클래스를 변경 하는 데 한정자 상속 나 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="78afa-106">기본적으로 모든 클래스는 상속할 수로 표시 하지 않는 한는 `NotInheritable` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="78afa-107">클래스는 프로젝트에서 참조 하는 다른 어셈블리의 클래스 또는 프로젝트의 다른 클래스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="78afa-108">다중 상속을 허용 하는 언어와 달리 Visual Basic에서는; 클래스의 단일 상속만을 허용합니다 즉, 파생 된 클래스에는 기본 클래스가 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="78afa-109">다중 상속 클래스에 허용 되지 않습니다 이지만 클래스에는 같은 결과 효과적으로 얻을 수 있는 여러 인터페이스를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="78afa-110">기본 클래스에 제한 된 항목을 노출를 방지 하려면 파생된 클래스의 액세스 형식을 같거나 해당 기본 클래스 보다 더 제한적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="78afa-111">예를 들어는 `Public` 상속할 수 없습니다. 클래스는 `Friend` 또는 `Private` 클래스 및 `Friend` 클래스를 상속할 수 없습니다는 `Private` 클래스.</span><span class="sxs-lookup"><span data-stu-id="78afa-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="78afa-112">상속 한정자</span><span class="sxs-lookup"><span data-stu-id="78afa-112">Inheritance Modifiers</span></span>  
 <span data-ttu-id="78afa-113">Visual Basic에서는 다음과 같은 클래스 수준 문과 상속을 지원 하기 위한 한정자:</span><span class="sxs-lookup"><span data-stu-id="78afa-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="78afa-114">`Inherits` 문-기본 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="78afa-115">`NotInheritable` 한정자-프로그래머 클래스를 기본 클래스로 사용 하는 것을 금지 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="78afa-116">`MustInherit` 한정자-는 클래스에서 사용 하기 위한 기본 클래스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="78afa-117">인스턴스 `MustInherit` 만들 수 있습니다만 파생된 클래스의 기본으로 클래스 인스턴스; 클래스를 직접 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="78afa-118">(C + + 및 C#과 같은 다른 프로그래밍 언어의 단어를 사용 하 여. *추상 클래스* 이러한 클래스를 설명 합니다.)</span><span class="sxs-lookup"><span data-stu-id="78afa-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="78afa-119">속성 및 파생된 클래스의 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="78afa-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="78afa-120">기본적으로 파생된 클래스는 기본 클래스에서 속성 및 메서드 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="78afa-121">상속 된 속성 또는 메서드가 파생된 클래스에서 다르게 동작 하도록 경우 일 수 있습니다 *재정의*합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="78afa-122">즉, 파생된 클래스에서 메서드의 새로운 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="78afa-123">다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="78afa-124">`Overridable` -파생된 클래스에서 재정의 되도록 클래스에서 속성 또는 메서드의 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="78afa-125">`Overrides` -재정의 `Overridable` 속성 또는 메서드의 기본 클래스에 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="78afa-126">`NotOverridable` -상속 클래스에서 재정의 되는 속성 또는 메서드가 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="78afa-127">기본적으로 `Public` 메서드는 `NotOverridable`합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="78afa-128">`MustOverride` -파생된 클래스에서 속성 또는 메서드를 재정의 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="78afa-129">경우는 `MustOverride` 키워드가 사용 되는지, 메서드가 정의는 테이블만 `Sub`, `Function`, 또는 `Property` 문.</span><span class="sxs-lookup"><span data-stu-id="78afa-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="78afa-130">다른 문이 허용 여부와 특별히 없습니다 `End Sub` 또는 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="78afa-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="78afa-131">`MustOverride` 메서드를 선언 해야 `MustInherit` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="78afa-132">급여를 처리 하는 클래스를 정의 하 고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="78afa-133">제네릭을 정의할 수 있습니다 `Payroll` 클래스를 포함 하는 `RunPayroll` 일반적인 주에 대 한 급여를 계산 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="78afa-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="78afa-134">사용 하 여 수 `Payroll` 더 특수 한 작업에 대 한 기본 클래스로 `BonusPayroll` 직원에 게 보너스를 배포 하는 경우 사용할 수 있는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="78afa-135">`BonusPayroll` 클래스를 상속 하 고 재정의할 수는 `PayEmployee` 자료에 정의 된 메서드 `Payroll` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="78afa-136">다음 예제에서는 기본 클래스를 정의 `Payroll,` 및 파생된 클래스가 `BonusPayroll`, 상속된 된 메서드를 재정의 하 `PayEmployee`합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="78afa-137">프로시저 `RunPayroll`만들고 다음 전달는 `Payroll` 개체 및 `BonusPayroll` 함수에 개체 `Pay`를 실행 하는 `PayEmployee` 두 개체의 메서드.</span><span class="sxs-lookup"><span data-stu-id="78afa-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="78afa-138">MyBase 키워드</span><span class="sxs-lookup"><span data-stu-id="78afa-138">The MyBase Keyword</span></span>  
 <span data-ttu-id="78afa-139">`MyBase` 키워드는 클래스의 현재 인스턴스의 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="78afa-140">`MyBase` 재정의 되거나 파생된 클래스에서 섀도 처리 하는 기본 클래스 멤버 액세스를 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="78afa-141">특히, `MyBase.New` 파생된 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="78afa-142">예를 들어 기본 클래스에서 상속 된 메서드를 재정의 하는 파생된 클래스를 디자인 하는 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="78afa-143">재정의 된 메서드가 기본 클래스에서 메서드를 호출 하 고 다음 코드 조각에 나와 있는 것 처럼 반환 값을 수정할 수 있습니다.:</span><span class="sxs-lookup"><span data-stu-id="78afa-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 <span data-ttu-id="78afa-144">다음 목록에는 사용 하 여 작업에 제한 설명 `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="78afa-144">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="78afa-145">`MyBase` 직접 기본 클래스와 상속 된 멤버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="78afa-146">사용할 수 없습니다 액세스로 `Private` 클래스의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-146">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="78afa-147">`MyBase` 실제 개체가 아니라는 키워드가입니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="78afa-148">`MyBase` 변수에 할당, 프로시저에 전달 하거나에서 사용할 수 없습니다는 `Is` 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="78afa-149">메서드는 `MyBase` 한정;는 직접 기본 클래스에서 정의 하지 않아도 대신 간접적으로 상속된 된 기본 클래스에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="78afa-150">지정한 참조가 되려면 `MyBase` 올바르게 컴파일하기 위해 일부 기본 클래스 이름 및 유형의 호출에 표시 되는 매개 변수에 일치 하는 메서드를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="78afa-151">사용할 수 없는 `MyBase` 호출할 `MustOverride` 기본 클래스 메서드.</span><span class="sxs-lookup"><span data-stu-id="78afa-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="78afa-152">`MyBase` 자체를 정하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="78afa-153">따라서 다음 코드는 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-153">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="78afa-154">`MyBase` 모듈에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-154">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="78afa-155">`MyBase` 으로 표시 된 기본 클래스 멤버 액세스를 사용할 수 없습니다 `Friend` 는 다른 어셈블리에는 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="78afa-156">자세한 내용 및 또 다른 예에 대 한 참조 [하는 방법: 파생 클래스에 의해 변수 숨겨진 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="78afa-157">MyClass 키워드</span><span class="sxs-lookup"><span data-stu-id="78afa-157">The MyClass Keyword</span></span>  
 <span data-ttu-id="78afa-158">`MyClass` 키워드 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="78afa-159">`MyClass` 유사한 `Me`, 모든 메서드 및 속성에 호출 되지만 `MyClass` 메서드나 속성이 처럼 처리 됩니다 [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="78afa-160">따라서 메서드 또는 속성은 영향을 받지 파생된 클래스에서 재정의 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="78afa-161">`MyClass` 실제 개체가 아니라는 키워드가입니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="78afa-162">`MyClass` 변수에 할당, 프로시저에 전달 하거나에서 사용할 수 없습니다는 `Is` 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="78afa-163">`MyClass` 포함 하는 클래스와 상속 된 멤버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-163">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="78afa-164">`MyClass` 에 대 한 한정자로 사용할 수 있습니다 `Shared` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="78afa-165">`MyClass` 내에서 사용할 수 없습니다는 `Shared` 메서드를 되지만 인스턴스 메서드 내에서 사용 하는 클래스의 공유 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="78afa-166">`MyClass` 기본 모듈에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-166">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="78afa-167">`MyClass` 기본 클래스에 정의 된 해당 클래스에서 제공 되는 메서드의 구현이 없는 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="78afa-168">이러한 참조는 의미가 동일한으로 `MyBase.` *메서드*합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="78afa-169">다음 예제에서는 비교 `Me` 및 `MyClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-169">The following example compares `Me` and `MyClass`.</span></span>  
  
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
  
 <span data-ttu-id="78afa-170">경우에 `derivedClass` 재정의 `testMethod`, `MyClass` 키워드 `useMyClass` 재정의 및 컴파일러 확인 한 결과의 기본 클래스 버전에 대 한 호출 취소 `testMethod`합니다.</span><span class="sxs-lookup"><span data-stu-id="78afa-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78afa-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78afa-171">See Also</span></span>  
 [<span data-ttu-id="78afa-172">Inherits 문</span><span class="sxs-lookup"><span data-stu-id="78afa-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="78afa-173">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="78afa-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
