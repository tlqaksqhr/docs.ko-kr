---
title: static(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: b7e2981c8832d6ac1744c102d5bde55bbe25c256
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33287269"
---
# <a name="static-c-reference"></a><span data-ttu-id="8f211-102">static(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8f211-102">static (C# Reference)</span></span>
<span data-ttu-id="8f211-103">`static` 한정자를 사용하여 특정 개체가 아니라 형식 자체에 속하는 정적 멤버를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="8f211-104">`static` 한정자는 클래스, 필드, 메서드, 속성, 연산자, 이벤트 및 생성자와 함께 사용할 수 있지만 인덱서, 종료자 또는 클래스 이외의 형식에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-104">The `static` modifier can be used with classes, fields, methods, properties, operators, events, and constructors, but it cannot be used with indexers, finalizers, or types other than classes.</span></span> <span data-ttu-id="8f211-105">자세한 내용은 [static 클래스 및 static 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f211-105">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f211-106">예</span><span class="sxs-lookup"><span data-stu-id="8f211-106">Example</span></span>  
 <span data-ttu-id="8f211-107">다음 클래스는 `static`으로 선언되며 `static` 메서드만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-107">The following class is declared as `static` and contains only `static` methods:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_1.cs)]  
  
 <span data-ttu-id="8f211-108">상수 또는 형식 선언은 암시적으로 정적 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-108">A constant or type declaration is implicitly a static member.</span></span>  
  
 <span data-ttu-id="8f211-109">정적 멤버는 인스턴스를 통해 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-109">A static member cannot be referenced through an instance.</span></span> <span data-ttu-id="8f211-110">대신, 형식 이름을 통해 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-110">Instead, it is referenced through the type name.</span></span> <span data-ttu-id="8f211-111">예를 들어 다음 클래스를 예로 들어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-111">For example, consider the following class:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_2.cs)]  
  
 <span data-ttu-id="8f211-112">정적 멤버 `x`를 참조하려면 동일한 범위에서 멤버에 액세스할 수 없는 경우 정규화된 이름 `MyBaseC.MyStruct.x`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-112">To refer to the static member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>  
  
```csharp  
Console.WriteLine(MyBaseC.MyStruct.x);  
```  
  
 <span data-ttu-id="8f211-113">클래스 인스턴스에는 클래스의 모든 인스턴스 필드에 대한 별도 복사본이 포함되지만 각 정적 필드의 복사본은 한 개만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-113">While an instance of a class contains a separate copy of all instance fields of the class, there is only one copy of each static field.</span></span>  
  
 <span data-ttu-id="8f211-114">[this](../../../csharp/language-reference/keywords/this.md)를 사용하여 정적 메서드 또는 속성 접근자를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-114">It is not possible to use [this](../../../csharp/language-reference/keywords/this.md) to reference static methods or property accessors.</span></span>  
  
 <span data-ttu-id="8f211-115">`static` 키워드가 클래스에 적용된 경우 클래스의 모든 멤버가 정적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-115">If the `static` keyword is applied to a class, all the members of the class must be static.</span></span>  
  
 <span data-ttu-id="8f211-116">클래스 및 정적 클래스에 정적 생성자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-116">Classes and static classes may have static constructors.</span></span> <span data-ttu-id="8f211-117">프로그램이 시작된 후, 클래스가 인스턴스화되기 전에 정적 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-117">Static constructors are called at some point between when the program starts and the class is instantiated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f211-118">`static` 키워드는 C++보다 사용이 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-118">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="8f211-119">C++ 키워드와 비교하려면 [저장소 클래스(C++)](/cpp/cpp/storage-classes-cpp#static)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f211-119">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>
  
 <span data-ttu-id="8f211-120">정적 멤버를 보여 주려면 회사 직원을 나타내는 클래스를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="8f211-120">To demonstrate static members, consider a class that represents a company employee.</span></span> <span data-ttu-id="8f211-121">클래스에 직원 수를 구하는 메서드와 직원 수를 저장하는 필드가 포함되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-121">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="8f211-122">메서드와 필드는 둘 다 인스턴스 직원에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-122">Both the method and the field do not belong to any instance employee.</span></span> <span data-ttu-id="8f211-123">대신 회사 클래스에 속해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-123">Instead they belong to the company class.</span></span> <span data-ttu-id="8f211-124">따라서 클래스의 정적 멤버로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-124">Therefore, they should be declared as static members of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f211-125">예</span><span class="sxs-lookup"><span data-stu-id="8f211-125">Example</span></span>  
 <span data-ttu-id="8f211-126">이 예제에서는 새 직원의 이름 및 ID를 읽고, 직원 카운터를 1만큼 늘린 다음 새 직원에 대한 정보와 새 직원 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-126">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="8f211-127">간단히 하기 위해 이 프로그램은 키보드에서 현재 직원 수를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-127">For simplicity, this program reads the current number of employees from the keyboard.</span></span> <span data-ttu-id="8f211-128">실제 응용 프로그램에서는 이 정보를 파일에서 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-128">In a real application, this information should be read from a file.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="8f211-129">예</span><span class="sxs-lookup"><span data-stu-id="8f211-129">Example</span></span>  
 <span data-ttu-id="8f211-130">이 예제에서는 아직 선언되지 않은 다른 정적 필드를 사용하여 정적 필드를 초기화할 수 있지만 정적 필드에 값을 명시적으로 할당할 때까지 결과가 정의되지 않음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f211-130">This example shows that although you can initialize a static field by using another static field not yet declared, the results will be undefined until you explicitly assign a value to the static field.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/static_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8f211-131">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8f211-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f211-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f211-132">See Also</span></span>  
 [<span data-ttu-id="8f211-133">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8f211-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8f211-134">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8f211-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8f211-135">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="8f211-135">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8f211-136">한정자</span><span class="sxs-lookup"><span data-stu-id="8f211-136">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="8f211-137">정적 클래스 및 정적 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="8f211-137">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
