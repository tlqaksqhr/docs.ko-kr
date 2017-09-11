---
title: "클래스(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
caps.latest.revision: 40
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eedb087f177b1bff6f4d4177cd56ac4cca016490
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="classes-c-programming-guide"></a><span data-ttu-id="aad0c-102">클래스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="aad0c-102">Classes (C# Programming Guide)</span></span>
<span data-ttu-id="aad0c-103">*클래스*는 기타 형식, 메서드 및 이벤트의 변수를 그룹화하여 자체 사용자 지정 형식을 만들 수 있는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-103">A *class* is a construct that enables you to create your own custom types by grouping together variables of other types, methods and events.</span></span> <span data-ttu-id="aad0c-104">클래스는 청사진과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-104">A class is like a blueprint.</span></span> <span data-ttu-id="aad0c-105">클래스는 형식의 데이터 및 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-105">It defines the data and behavior of a type.</span></span> <span data-ttu-id="aad0c-106">클래스가 static으로 선언되지 않으면 클라이언트 코드는 변수에 할당되는 *개체* 또는 *인스턴스*를 만드는 방식으로 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-106">If the class is not declared as static, client code can use it by creating *objects* or *instances* which are assigned to a variable.</span></span> <span data-ttu-id="aad0c-107">변수는 변수에 대한 모든 참조가 범위를 벗어날 때까지 메모리에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-107">The variable remains in memory until all references to it go out of scope.</span></span> <span data-ttu-id="aad0c-108">이때 CLR는 변수를 가비지 수집에 적격한 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-108">At that time, the CLR marks it as eligible for garbage collection.</span></span> <span data-ttu-id="aad0c-109">클래스가 [static](../../../csharp/language-reference/keywords/static.md)으로 선언되면 메모리에는 복사본이 하나만 존재하고 클라이언트 코드는 *인스턴스 변수*가 아니라 클래스 자체를 통해서만 클래스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-109">If the class is declared as [static](../../../csharp/language-reference/keywords/static.md), then only one copy exists in memory and client code can only access it through the class itself, not an *instance variable*.</span></span> <span data-ttu-id="aad0c-110">자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aad0c-110">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="aad0c-111">구조체와 달리 클래스는 개체 지향 프로그래밍의 기본적인 특성인 *상속*을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-111">Unlike structs, classes support *inheritance*, a fundamental characteristic of object-oriented programming.</span></span> <span data-ttu-id="aad0c-112">자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aad0c-112">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
## <a name="declaring-classes"></a><span data-ttu-id="aad0c-113">클래스 선언</span><span class="sxs-lookup"><span data-stu-id="aad0c-113">Declaring Classes</span></span>  
 <span data-ttu-id="aad0c-114">다음 예제와 같이 [class](../../../csharp/language-reference/keywords/class.md) 키워드를 사용하여 클래스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-114">Classes are declared by using the [class](../../../csharp/language-reference/keywords/class.md) keyword, as shown in the following example:</span></span>  
  
 <span data-ttu-id="aad0c-115">[!code-cs[csProgGuideObjects#79](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="aad0c-115">[!code-cs[csProgGuideObjects#79](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_1.cs)]</span></span>  
  
 <span data-ttu-id="aad0c-116">`class` 키워드는 액세스 수준 뒤에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-116">The `class` keyword is preceded by the access level.</span></span> <span data-ttu-id="aad0c-117">이 경우 [public](../../../csharp/language-reference/keywords/public.md)이 사용되므로 누구나 이 클래스에서 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-117">Because [public](../../../csharp/language-reference/keywords/public.md) is used in this case, anyone can create objects from this class.</span></span> <span data-ttu-id="aad0c-118">클래스 이름은 `class` 키워드 뒤에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-118">The name of the class follows the `class` keyword.</span></span> <span data-ttu-id="aad0c-119">정의의 나머지 부분은 동작과 데이터가 정의되는 클래스 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-119">The remainder of the definition is the class body, where the behavior and data are defined.</span></span> <span data-ttu-id="aad0c-120">클래스의 필드, 속성, 메서드 및 이벤트를 모두 *클래스 멤버*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-120">Fields, properties, methods, and events on a class are collectively referred to as *class members*.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="aad0c-121">개체 만들기</span><span class="sxs-lookup"><span data-stu-id="aad0c-121">Creating Objects</span></span>  
 <span data-ttu-id="aad0c-122">클래스와 개체는 바꿔 사용되기도 하지만 서로 다른 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-122">Although they are sometimes used interchangeably, a class and an object are different things.</span></span> <span data-ttu-id="aad0c-123">클래스는 개체의 형식을 정의하지만 개체 자체는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-123">A class defines a type of object, but it is not an object itself.</span></span> <span data-ttu-id="aad0c-124">개체는 클래스에 기반을 둔 구체적 엔터티이고 클래스의 인스턴스라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-124">An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.</span></span>  
  
 <span data-ttu-id="aad0c-125">개체를 만들려면 다음과 같이 [new](../../../csharp/language-reference/keywords/new.md) 키워드 뒤에 개체의 기반이 되는 클래스의 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-125">Objects can be created by using the [new](../../../csharp/language-reference/keywords/new.md) keyword followed by the name of the class that the object will be based on, like this:</span></span>  
  
 <span data-ttu-id="aad0c-126">[!code-cs[csProgGuideObjects#80](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="aad0c-126">[!code-cs[csProgGuideObjects#80](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_2.cs)]</span></span>  
  
 <span data-ttu-id="aad0c-127">클래스 인스턴스가 만들어질 때 개체에 대한 참조가 다시 프로그래머에게 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-127">When an instance of a class is created, a reference to the object is passed back to the programmer.</span></span> <span data-ttu-id="aad0c-128">이전 예제에서 `object1`은 `Customer`에 기반을 둔 개체에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-128">In the previous example, `object1` is a reference to an object that is based on `Customer`.</span></span> <span data-ttu-id="aad0c-129">이 참조는 새 개체를 참조하지만 개체 데이터 자체를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-129">This reference refers to the new object but does not contain the object data itself.</span></span> <span data-ttu-id="aad0c-130">실제로 개체를 만들지 않고도 개체 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-130">In fact, you can create an object reference without creating an object at all:</span></span>  
  
 <span data-ttu-id="aad0c-131">[!code-cs[csProgGuideObjects#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="aad0c-131">[!code-cs[csProgGuideObjects#81](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_3.cs)]</span></span>  
  
 <span data-ttu-id="aad0c-132">런타임에는 참조를 통한 개체 액세스 시도에 실패하므로 개체를 참조하지 않는 이와 같은 개체 참조는 만들지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-132">We don't recommend creating object references such as this one that don't refer to an object because trying to access an object through such a reference will fail at run time.</span></span> <span data-ttu-id="aad0c-133">그러나 새 개체를 만들거나 다음과 같이 기존 개체에 개체를 할당하여 개체를 참조하는 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-133">However, such a reference can be made to refer to an object, either by creating a new object, or by assigning it to an existing object, such as this:</span></span>  
  
 <span data-ttu-id="aad0c-134">[!code-cs[csProgGuideObjects#82](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="aad0c-134">[!code-cs[csProgGuideObjects#82](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_4.cs)]</span></span>  
  
 <span data-ttu-id="aad0c-135">이 코드에서는 같은 개체를 참조하는 두 개의 개체 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-135">This code creates two object references that both refer to the same object.</span></span> <span data-ttu-id="aad0c-136">따라서 `object3`을 통해 이루어진 모든 개체 변경 내용은 이후 `object4` 사용 시 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-136">Therefore, any changes to the object made through `object3` will be reflected in subsequent uses of `object4`.</span></span> <span data-ttu-id="aad0c-137">클래스에 기반을 둔 개체는 참조를 통해 참조되므로 클래스를 참조 형식이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-137">Because objects that are based on classes are referred to by reference, classes are known as reference types.</span></span>  
  
## <a name="class-inheritance"></a><span data-ttu-id="aad0c-138">클래스 상속</span><span class="sxs-lookup"><span data-stu-id="aad0c-138">Class Inheritance</span></span>  
 <span data-ttu-id="aad0c-139">상속은 *파생*을 통해 수행합니다. 즉, 클래스는 데이터와 동작을 상속하는 소스 *기본 클래스*를 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-139">Inheritance is accomplished by using a *derivation*, which means a class is declared by using a *base class* from which it inherits data and behavior.</span></span> <span data-ttu-id="aad0c-140">다음과 같이 파생 클래스 이름 뒤에 콜론 및 기본 클래스 이름을 추가하여 기본 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-140">A base class is specified by appending a colon and the name of the base class following the derived class name, like this:</span></span>  
  
 <span data-ttu-id="aad0c-141">[!code-cs[csProgGuideObjects#83](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="aad0c-141">[!code-cs[csProgGuideObjects#83](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_5.cs)]</span></span>  
  
 <span data-ttu-id="aad0c-142">기본 클래스를 선언하는 클래스는 생성자를 제외하고 기본 클래스의 모든 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-142">When a class declares a base class, it inherits all the members of the base class except the constructors.</span></span>  
  
 <span data-ttu-id="aad0c-143">C++와 달리 C#의 클래스는 하나의 기본 클래스에서만 직접 상속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-143">Unlike C++, a class in C# can only directly inherit from one base class.</span></span> <span data-ttu-id="aad0c-144">그러나 기본 클래스 자체는 다른 클래스에서 상속될 수 있으므로 클래스는 여러 기본 클래스를 간접적으로 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-144">However, because a base class may itself inherit from another class, a class may indirectly inherit multiple base classes.</span></span> <span data-ttu-id="aad0c-145">게다가 클래스는 두 개 이상의 인터페이스를 직접 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-145">Furthermore, a class can directly implement more than one interface.</span></span> <span data-ttu-id="aad0c-146">자세한 내용은 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aad0c-146">For more information, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="aad0c-147">클래스는 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-147">A class can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="aad0c-148">추상 클래스에는 시그니처 정의가 있지만 구현이 없는 추상 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-148">An abstract class contains abstract methods that have a signature definition but no implementation.</span></span> <span data-ttu-id="aad0c-149">추상 클래스는 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-149">Abstract classes cannot be instantiated.</span></span> <span data-ttu-id="aad0c-150">추상 클래스는 추상 메서드를 구현하는 파생 클래스를 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-150">They can only be used through derived classes that implement the abstract methods.</span></span> <span data-ttu-id="aad0c-151">이와 달리 [sealed](../../../csharp/language-reference/keywords/sealed.md) 클래스에서는 다른 클래스가 파생될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-151">By contrast, a [sealed](../../../csharp/language-reference/keywords/sealed.md) class does not allow other classes to derive from it.</span></span> <span data-ttu-id="aad0c-152">자세한 내용은 [Abstract 및 Sealed 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aad0c-152">For more information, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="aad0c-153">클래스 정의는 여러 소스 파일로 분할될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-153">Class definitions can be split between different source files.</span></span> <span data-ttu-id="aad0c-154">자세한 내용은 참조 [Partial 클래스 및 메서드](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-154">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="aad0c-155">설명</span><span class="sxs-lookup"><span data-stu-id="aad0c-155">Description</span></span>  
 <span data-ttu-id="aad0c-156">다음 예제에서는 단일 필드, 메서드 및 생성자라는 특수 메서드가 포함된 public 클래스가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-156">In the following example, a public class that contains a single field, a method, and a special method called a constructor is defined.</span></span> <span data-ttu-id="aad0c-157">자세한 내용은 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aad0c-157">For more information, see [Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span></span> <span data-ttu-id="aad0c-158">그런 다음 클래스는 `new` 키워드를 사용하여 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad0c-158">The class is then instantiated with the `new` keyword.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aad0c-159">예제</span><span class="sxs-lookup"><span data-stu-id="aad0c-159">Example</span></span>  
 <span data-ttu-id="aad0c-160">[!code-cs[csProgGuideObjects#84](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="aad0c-160">[!code-cs[csProgGuideObjects#84](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/classes_6.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="aad0c-161">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="aad0c-161">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aad0c-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aad0c-162">See Also</span></span>  
 <span data-ttu-id="aad0c-163">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="aad0c-163">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="aad0c-164">[개체 지향 프로그래밍](../concepts/object-oriented-programming.md) </span><span class="sxs-lookup"><span data-stu-id="aad0c-164">[Object-Oriented Programming](../concepts/object-oriented-programming.md) </span></span>  
 <span data-ttu-id="aad0c-165">[다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span><span class="sxs-lookup"><span data-stu-id="aad0c-165">[Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span></span>  
 <span data-ttu-id="aad0c-166">[멤버](../../../csharp/programming-guide/classes-and-structs/members.md) </span><span class="sxs-lookup"><span data-stu-id="aad0c-166">[Members](../../../csharp/programming-guide/classes-and-structs/members.md) </span></span>  
 <span data-ttu-id="aad0c-167">[메서드](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="aad0c-167">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 <span data-ttu-id="aad0c-168">[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="aad0c-168">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="aad0c-169">[종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="aad0c-169">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 [<span data-ttu-id="aad0c-170">개체</span><span class="sxs-lookup"><span data-stu-id="aad0c-170">Objects</span></span>](../../../csharp/programming-guide/classes-and-structs/objects.md)

