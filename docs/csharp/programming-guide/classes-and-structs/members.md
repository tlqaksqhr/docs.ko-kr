---
title: "멤버(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- types [C#], nested types
- C# language, type members
ms.assetid: 4a30a4ab-d690-4936-9124-92ce9448665a
caps.latest.revision: 20
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
ms.openlocfilehash: 98446a2eb0415c92aa44cbddf8539477a00a2666
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="members-c-programming-guide"></a><span data-ttu-id="98188-102">멤버(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="98188-102">Members (C# Programming Guide)</span></span>
<span data-ttu-id="98188-103">클래스 및 구조체에는 해당 데이터와 동작을 나타내는 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-103">Classes and structs have members that represent their data and behavior.</span></span> <span data-ttu-id="98188-104">클래스의 멤버에는 클래스에서 선언된 모든 멤버가 상속 계층 구조의 모든 클래스에서 선언된 모든 멤버(생성자 및 종료자 제외)와 함께 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="98188-104">A class's members include all the members declared in the class, along with all members (except constructors and finalizers) declared in all classes in its inheritance hierarchy.</span></span> <span data-ttu-id="98188-105">기본 클래스의 private 멤버는 상속되지만 파생 클래스에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-105">Private members in base classes are inherited but are not accessible from derived classes.</span></span>  
  
 <span data-ttu-id="98188-106">다음 표에는 클래스 또는 구조체에 포함될 수 있는 멤버 종류가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-106">The following table lists the kinds of members a class or struct may contain:</span></span>  
  
|<span data-ttu-id="98188-107">멤버</span><span class="sxs-lookup"><span data-stu-id="98188-107">Member</span></span>|<span data-ttu-id="98188-108">설명</span><span class="sxs-lookup"><span data-stu-id="98188-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98188-109">필드</span><span class="sxs-lookup"><span data-stu-id="98188-109">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="98188-110">필드는 클래스 범위에서 선언된 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="98188-110">Fields are variables declared at class scope.</span></span> <span data-ttu-id="98188-111">필드는 기본 제공 숫자 형식 또는 다른 클래스의 인스턴스일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-111">A field may be a built-in numeric type or an instance of another class.</span></span> <span data-ttu-id="98188-112">예를 들어 달력 클래스에는 현재 날짜를 포함하는 필드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-112">For example, a calendar class may have a field that contains the current date.</span></span>|  
|[<span data-ttu-id="98188-113">상수</span><span class="sxs-lookup"><span data-stu-id="98188-113">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="98188-114">상수는 해당 값이 컴파일 시간에 설정되며 변경할 수 없는 필드 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="98188-114">Constants are fields or properties whose value is set at compile time and cannot be changed.</span></span>|  
|[<span data-ttu-id="98188-115">속성</span><span class="sxs-lookup"><span data-stu-id="98188-115">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="98188-116">속성은 해당 클래스의 필드처럼 액세스되는 클래스의 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="98188-116">Properties are methods on a class that are accessed as if they were fields on that class.</span></span> <span data-ttu-id="98188-117">속성은 클래스 필드에 대한 보호를 제공하여 개체 모르게 필드가 변경되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-117">A property can provide protection for a class field to keep it from being changed without the knowledge of the object.</span></span>|  
|[<span data-ttu-id="98188-118">메서드</span><span class="sxs-lookup"><span data-stu-id="98188-118">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="98188-119">메서드는 클래스가 수행할 수 있는 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98188-119">Methods define the actions that a class can perform.</span></span> <span data-ttu-id="98188-120">메서드는 입력 데이터를 제공하는 매개 변수를 사용할 수 있으며, 매개 변수를 통해 출력 데이터를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-120">Methods can take parameters that provide input data, and can return output data through parameters.</span></span> <span data-ttu-id="98188-121">메서드가 매개 변수를 사용하지 않고 직접 값을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-121">Methods can also return a value directly, without using a parameter.</span></span>|  
|[<span data-ttu-id="98188-122">이벤트</span><span class="sxs-lookup"><span data-stu-id="98188-122">Events</span></span>](../../../csharp/programming-guide/events/index.md)|<span data-ttu-id="98188-123">이벤트는 단추 클릭, 성공적인 메서드 완료 등의 발생에 대한 알림을 다른 개체에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98188-123">Events provide notifications about occurrences, such as button clicks or the successful completion of a method, to other objects.</span></span> <span data-ttu-id="98188-124">이벤트는 대리자를 사용하여 정의 및 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="98188-124">Events are defined and triggered by using delegates.</span></span>|  
|[<span data-ttu-id="98188-125">연산자</span><span class="sxs-lookup"><span data-stu-id="98188-125">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|<span data-ttu-id="98188-126">오버로드된 연산자는 클래스 멤버로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="98188-126">Overloaded operators are considered class members.</span></span> <span data-ttu-id="98188-127">연산자를 오버로드하는 경우 클래스에서 공용 정적 메서드로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98188-127">When you overload an operator, you define it as a public static method in a class.</span></span> <span data-ttu-id="98188-128">미리 정의된 연산자(`+`, `*`, `<` 등)는 멤버로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-128">The predefined operators (`+`, `*`, `<`, and so on) are not considered members.</span></span> <span data-ttu-id="98188-129">자세한 내용은 [오버로드할 수 있는 연산자](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98188-129">For more information, see [Overloadable Operators](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md).</span></span>|  
|[<span data-ttu-id="98188-130">인덱서</span><span class="sxs-lookup"><span data-stu-id="98188-130">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)|<span data-ttu-id="98188-131">인덱서를 사용하면 배열과 유사한 방식으로 개체를 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98188-131">Indexers enable an object to be indexed in a manner similar to arrays.</span></span>|  
|[<span data-ttu-id="98188-132">생성자</span><span class="sxs-lookup"><span data-stu-id="98188-132">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="98188-133">생성자는 개체를 처음 만들 때 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="98188-133">Constructors are methods that are called when the object is first created.</span></span> <span data-ttu-id="98188-134">대체로 개체의 데이터를 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98188-134">They are often used to initialize the data of an object.</span></span>|  
|[<span data-ttu-id="98188-135">종료자</span><span class="sxs-lookup"><span data-stu-id="98188-135">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)|<span data-ttu-id="98188-136">종료자는 C#에서 매우 드물게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98188-136">Finalizers are used very rarely in C#.</span></span> <span data-ttu-id="98188-137">메모리에서 개체를 제거할 때 런타임 실행 엔진이 호출하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="98188-137">They are methods that are called by the runtime execution engine when the object is about to be removed from memory.</span></span> <span data-ttu-id="98188-138">일반적으로 해제해야 하는 리소스가 적절하게 처리되도록 하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98188-138">They are generally used to make sure that any resources which must be released are handled appropriately.</span></span>|  
|[<span data-ttu-id="98188-139">중첩 형식</span><span class="sxs-lookup"><span data-stu-id="98188-139">Nested Types</span></span>](../../../csharp/programming-guide/classes-and-structs/nested-types.md)|<span data-ttu-id="98188-140">중첩 형식은 다른 형식 내에서 선언된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="98188-140">Nested types are types declared within another type.</span></span> <span data-ttu-id="98188-141">중첩 형식은 대체로 개체를 포함하는 형식에서만 사용되는 개체를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98188-141">Nested types are often used to describe objects that are used only by the types that contain them.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98188-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98188-142">See Also</span></span>  
 <span data-ttu-id="98188-143">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="98188-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="98188-144">[클래스](../../../csharp/programming-guide/classes-and-structs/classes.md) </span><span class="sxs-lookup"><span data-stu-id="98188-144">[Classes](../../../csharp/programming-guide/classes-and-structs/classes.md) </span></span>  
 <span data-ttu-id="98188-145">[메서드](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="98188-145">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 <span data-ttu-id="98188-146">[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="98188-146">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 <span data-ttu-id="98188-147">[종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span><span class="sxs-lookup"><span data-stu-id="98188-147">[Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md) </span></span>  
 <span data-ttu-id="98188-148">[속성](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="98188-148">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="98188-149">[필드](../../../csharp/programming-guide/classes-and-structs/fields.md) </span><span class="sxs-lookup"><span data-stu-id="98188-149">[Fields](../../../csharp/programming-guide/classes-and-structs/fields.md) </span></span>  
 <span data-ttu-id="98188-150">[인덱서](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="98188-150">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="98188-151">[이벤트](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="98188-151">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="98188-152">[중첩 형식](../../../csharp/programming-guide/classes-and-structs/nested-types.md) </span><span class="sxs-lookup"><span data-stu-id="98188-152">[Nested Types](../../../csharp/programming-guide/classes-and-structs/nested-types.md) </span></span>  
 <span data-ttu-id="98188-153">[연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md) </span><span class="sxs-lookup"><span data-stu-id="98188-153">[Operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md) </span></span>  
 [<span data-ttu-id="98188-154">오버로드할 수 있는 연산자</span><span class="sxs-lookup"><span data-stu-id="98188-154">Overloadable Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)

