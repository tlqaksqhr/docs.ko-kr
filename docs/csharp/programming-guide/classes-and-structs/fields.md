---
title: "필드(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- fields [C#]
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8eef9bb644a28c69a1db59dcba3c12c9e3fa86b0
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="fields-c-programming-guide"></a><span data-ttu-id="68d72-102">필드(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="68d72-102">Fields (C# Programming Guide)</span></span>
<span data-ttu-id="68d72-103">*필드*는 [클래스](../../../csharp/language-reference/keywords/class.md) 또는 [구조체](../../../csharp/language-reference/keywords/struct.md)에서 직접 선언되는 모든 형식의 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-103">A *field* is a variable of any type that is declared directly in a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md).</span></span> <span data-ttu-id="68d72-104">필드는 포함하는 형식의 *멤버*입니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-104">Fields are *members* of their containing type.</span></span>  
  
 <span data-ttu-id="68d72-105">클래스 또는 구조체에는 인스턴스 필드, 정적 필드 또는 둘 다 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-105">A class or struct may have instance fields or static fields or both.</span></span> <span data-ttu-id="68d72-106">인스턴스 필드는 형식의 인스턴스와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-106">Instance fields are specific to an instance of a type.</span></span> <span data-ttu-id="68d72-107">인스턴스 필드가 F인 T 클래스가 있는 경우 형식이 T인 개체 두 개를 만들고 각 개체에서 다른 개체의 값에 영향을 주지 않고 F 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-107">If you have a class T, with an instance field F, you can create two objects of type T, and modify the value of F in each object without affecting the value in the other object.</span></span> <span data-ttu-id="68d72-108">반면 정적 필드는 클래스 자체에 속하며 해당 클래스의 모든 인스턴스에서 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-108">By contrast, a static field belongs to the class itself, and is shared among all instances of that class.</span></span> <span data-ttu-id="68d72-109">인스턴스 A에서 변경한 내용은 인스턴스 B와 C가 필드에 액세스하는 경우 바로 인스턴스 B와 C에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-109">Changes made from instance A will be visibly immediately to instances B and C if they access the field.</span></span>  
  
 <span data-ttu-id="68d72-110">일반적으로 필드는 액세스 가능성이 private 또는 protected인 변수에만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-110">Generally, you should use fields only for variables that have private or protected accessibility.</span></span> <span data-ttu-id="68d72-111">클래스에서 클라이언트 코드에 노출하는 데이터는 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md), [속성](../../../csharp/programming-guide/classes-and-structs/properties.md) 및 [인덱서](../../../csharp/programming-guide/indexers/index.md)를 통해 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-111">Data that your class exposes to client code should be provided through [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) and [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="68d72-112">내부 필드에 직접 액세스하는 데 이러한 구문을 사용하면 잘못된 입력 값으로부터 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-112">By using these constructs for indirect access to internal fields, you can guard against invalid input values.</span></span> <span data-ttu-id="68d72-113">공용 속성에 의해 노출된 데이터를 저장하는 private 필드는 *백업 저장소* 또는 *지원 필드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-113">A private field that stores the data exposed by a public property is called a *backing store* or *backing field*.</span></span>  
  
 <span data-ttu-id="68d72-114">필드는 일반적으로 둘 이상의 클래스 메서드에서 액세스할 수 있고 단일 메서드의 수명보다 오랫동안 저장되어야 하는 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-114">Fields typically store the data that must be accessible to more than one class method and must be stored for longer than the lifetime of any single method.</span></span> <span data-ttu-id="68d72-115">예를 들어 달력 날짜를 나타내는 클래스에는 각각 월, 일 및 연도에 대한 세 개의 정수 필드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-115">For example, a class that represents a calendar date might have three integer fields: one for the month, one for the day, and one for the year.</span></span> <span data-ttu-id="68d72-116">단일 메서드 범위 내에서만 사용되는 변수는 메서드 본문 자체 내에 *지역 변수*로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-116">Variables that are not used outside the scope of a single method should be declared as *local variables* within the method body itself.</span></span>  
  
 <span data-ttu-id="68d72-117">필드는 필드의 액세스 수준을 지정한 다음 필드의 형식, 필드의 이름순으로 지정하여 클래스 블록에서 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-117">Fields are declared in the class block by specifying the access level of the field, followed by the type of the field, followed by the name of the field.</span></span> <span data-ttu-id="68d72-118">예:</span><span class="sxs-lookup"><span data-stu-id="68d72-118">For example:</span></span>  
  
 <span data-ttu-id="68d72-119">[!code-cs[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="68d72-119">[!code-cs[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]</span></span>  
  
 <span data-ttu-id="68d72-120">개체의 필드에 액세스하려면 `objectname.fieldname`와 같이 개체 이름과 필드 이름 뒤에 마침표를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-120">To access a field in an object, add a period after the object name, followed by the name of the field, as in `objectname.fieldname`.</span></span> <span data-ttu-id="68d72-121">예:</span><span class="sxs-lookup"><span data-stu-id="68d72-121">For example:</span></span>  
  
 <span data-ttu-id="68d72-122">[!code-cs[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="68d72-122">[!code-cs[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]</span></span>  
  
 <span data-ttu-id="68d72-123">필드를 선언할 때 대입 연산자를 사용하여 필드에 초기 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-123">A field can be given an initial value by using the assignment operator when the field is declared.</span></span> <span data-ttu-id="68d72-124">예를 들어 `day` 필드를 `"Monday"`에 자동으로 할당하려면 다음 예제와 같이 `day`를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-124">To automatically assign the `day` field to `"Monday"`, for example, you would declare `day` as in the following example:</span></span>  
  
 <span data-ttu-id="68d72-125">[!code-cs[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="68d72-125">[!code-cs[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]</span></span>  
  
 <span data-ttu-id="68d72-126">필드는 개체 인스턴스에 대한 생성자를 호출 하기 직전에 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-126">Fields are initialized immediately before the constructor for the object instance is called.</span></span> <span data-ttu-id="68d72-127">생성자가 필드의 값을 할당하면 필드 선언 중에 지정된 모든 값을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-127">If the constructor assigns the value of a field, it will overwrite any value given during field declaration.</span></span> <span data-ttu-id="68d72-128">자세한 내용은 [생성자 사용](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68d72-128">For more information, see [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68d72-129">필드 이니셜라이저는 다른 인스턴스 필드를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-129">A field initializer cannot refer to other instance fields.</span></span>  
  
 <span data-ttu-id="68d72-130">필드는 [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 `protected internal`로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-130">Fields can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="68d72-131">이러한 액세스 한정자는 클래스 사용자가 필드에 액세스 하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-131">These access modifiers define how users of the class can access the fields.</span></span> <span data-ttu-id="68d72-132">자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68d72-132">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="68d72-133">필요에 따라 필드를 [static](../../../csharp/language-reference/keywords/static.md)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-133">A field can optionally be declared [static](../../../csharp/language-reference/keywords/static.md).</span></span> <span data-ttu-id="68d72-134">그러면 클래스의 인스턴스가 없는 경우에도 언제든지 호출자가 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-134">This makes the field available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="68d72-135">자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68d72-135">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="68d72-136">필드를 [readonly](../../../csharp/language-reference/keywords/readonly.md)로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-136">A field can be declared [readonly](../../../csharp/language-reference/keywords/readonly.md).</span></span> <span data-ttu-id="68d72-137">읽기 전용 필드는 초기화 중이나 생성자에서만 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-137">A read-only field can only be assigned a value during initialization or in a constructor.</span></span> <span data-ttu-id="68d72-138">C# 컴파일러가 컴파일 시간에는 정적 읽기 전용 필드의 값에 액세스할 수 없고 런타임 시에만 액세스할 수 있다는 점을 제외하면`static``readonly` 필드는 상수와 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="68d72-138">A `static``readonly` field is very similar to a constant, except that the C# compiler does not have access to the value of a static read-only field at compile time, only at run time.</span></span> <span data-ttu-id="68d72-139">자세한 내용은 [상수](../../../csharp/programming-guide/classes-and-structs/constants.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68d72-139">For more information, see [Constants](../../../csharp/programming-guide/classes-and-structs/constants.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="68d72-140">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="68d72-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="68d72-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68d72-141">See Also</span></span>  
 <span data-ttu-id="68d72-142">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="68d72-142">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="68d72-143">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="68d72-143">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="68d72-144">[생성자 사용](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span><span class="sxs-lookup"><span data-stu-id="68d72-144">[Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span></span>  
 <span data-ttu-id="68d72-145">[상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="68d72-145">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="68d72-146">[액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="68d72-146">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 [<span data-ttu-id="68d72-147">추상/봉인된 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="68d72-147">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)

