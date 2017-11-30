---
title: "개체 및 컬렉션 이니셜라이저(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7445a2919baaa477b4611c4c5ee5a0031539ca30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="0fabc-102">개체 및 컬렉션 이니셜라이저(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0fabc-102">Object and Collection Initializers (C# Programming Guide)</span></span>
<span data-ttu-id="0fabc-103">개체 이니셜라이저를 사용하면 명시적으로 생성자를 호출한 다음 할당문 줄을 추가하지 않고도 생성 시 개체의 모든 액세스 가능한 필드나 속성에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-103">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="0fabc-104">개체 이니셜라이저 구문을 사용하면 생성자의 인수를 지정하거나 인수(및 괄호 구문)를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-104">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="0fabc-105">다음 예제는 명명된 형식인 `Cat`의 개체 이니셜라이저를 사용하는 방법과 기본 생성자를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-105">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the default constructor.</span></span> <span data-ttu-id="0fabc-106">`Cat` 클래스의 자동 구현된 속성 사용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-106">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="0fabc-107">자세한 내용은 [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fabc-107">For more information, see [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]  
  
 [!code-csharp[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)] 
 
<span data-ttu-id="0fabc-108">개체 이니셜라이저 구문을 인스턴스를 만들 수 있으며 그 후 할당의 변수에 할당 된 속성을 새로 만든된 개체를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-108">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>
  
## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="0fabc-109">익명 형식의 개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="0fabc-109">Object Initializers with anonymous types</span></span>  
 <span data-ttu-id="0fabc-110">개체 이니셜라이저는 모든 컨텍스트에서 사용할 수 있지만 특히 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-110">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="0fabc-111">쿼리 식은 [무명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 자주 사용합니다. 이 형식은 다음 선언에 표시된 바와 같이 개체 이니셜라이저를 사용하는 경우에만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-111">Query expressions make frequent use of [anonymous types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 <span data-ttu-id="0fabc-112">무명 형식을 사용하면 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식의 `select` 절에서 원래 시퀀스의 개체를 값과 모양이 원본과 다를 수 있는 개체로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-112">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="0fabc-113">이 기능은 각 개체의 일부 정보만 시퀀스에 저장하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-113">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="0fabc-114">다음 예제에서 제품 개체(`p`)는 많은 필드와 메서드를 포함하며, 제품 이름과 단위 가격이 들어 있는 개체 시퀀스만 만들려 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-114">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]  
  
 <span data-ttu-id="0fabc-115">이 쿼리를 실행하면 다음 예제와 같이 `productInfos` 문에서 액세스할 수 있는 개체 시퀀스가 `foreach` 변수에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-115">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 <span data-ttu-id="0fabc-116">새 익명 형식의 각 개체에는 원래 개체의 속성이나 필드와 동일한 이름을 받는 두 개의 public 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-116">Each object in the new anonymous type has two public properties which receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="0fabc-117">익명 형식을 만들 때 필드 이름을 바꿀 수도 있습니다. 다음 예제에서는 `UnitPrice` 필드의 이름을 `Price`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-117">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a><span data-ttu-id="0fabc-118">nullable 형식의 개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="0fabc-118">Object initializers with nullable types</span></span>  
 <span data-ttu-id="0fabc-119">개체 이니셜라이저에 nullable 구조체를 사용하는 것은 컴파일 시간 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-119">It is a compile-time error to use an object initializer with a nullable struct.</span></span>  
  
## <a name="collection-initializers"></a><span data-ttu-id="0fabc-120">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="0fabc-120">Collection initializers</span></span>  
 <span data-ttu-id="0fabc-121">컬렉션 이니셜라이저를 사용하면 <xref:System.Collections.IEnumerable>을 구현하고 적절한 시그니처가 있는 `Add`를 인스턴스 메서드 또는 확장 메서드로 포함하는 컬렉션 형식을 초기화할 때 하나 이상의 요소 이니셜라이저를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-121">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="0fabc-122">요소 이니셜라이저는 단순한 값, 식 또는 개체 이니셜라이저일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-122">The element initializers can be a simple value, an expression or an object initializer.</span></span> <span data-ttu-id="0fabc-123">컬렉션 이니셜라이저를 사용하면 소스 코드에서 클래스의 `Add` 메서드에 대한 호출을 여러 번 지정할 필요가 없습니다. 컴파일러가 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-123">By using a collection initializer you do not have to specify multiple calls to the `Add` method of the class in your source code; the compiler adds the calls.</span></span>  
  
 <span data-ttu-id="0fabc-124">다음 예제에서는 두 개의 단순한 컬렉션 이니셜라이저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-124">The following examples shows two simple collection initializers:</span></span>  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 <span data-ttu-id="0fabc-125">다음 컬렉션 이니셜라이저는 개체 이니셜라이저를 사용하여 앞의 예제에서 정의된 `Cat` 클래스의 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-125">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="0fabc-126">개별 개체 이니셜라이저는 괄호로 묶이고 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-126">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]  
  
 <span data-ttu-id="0fabc-127">컬렉션의 `Add` 메서드에서 허용하는 경우 [null](../../../csharp/language-reference/keywords/null.md)을 컬렉션 이니셜라이저의 요소로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-127">You can specify [null](../../../csharp/language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]  
  
 <span data-ttu-id="0fabc-128">컬렉션이 인덱싱을 지원하는 경우 인덱싱된 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fabc-128">You can specify indexed elements if the collection supports indexing.</span></span>  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="example"></a><span data-ttu-id="0fabc-129">예제</span><span class="sxs-lookup"><span data-stu-id="0fabc-129">Example</span></span>  
 [!code-csharp[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0fabc-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fabc-130">See Also</span></span>  
 [<span data-ttu-id="0fabc-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0fabc-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0fabc-132">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="0fabc-132">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="0fabc-133">익명 형식</span><span class="sxs-lookup"><span data-stu-id="0fabc-133">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
