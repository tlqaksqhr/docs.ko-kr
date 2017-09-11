---
title: "개체 및 컬렉션 이니셜라이저(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
caps.latest.revision: 27
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
ms.openlocfilehash: c4144f383d539129b4e03d5cad262e5a7b9e6b34
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="efe10-102">개체 및 컬렉션 이니셜라이저(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="efe10-102">Object and Collection Initializers (C# Programming Guide)</span></span>
<span data-ttu-id="efe10-103">개체 이니셜라이저를 사용하면 명시적으로 생성자를 호출한 다음 할당문 줄을 추가하지 않고도 생성 시 개체의 모든 액세스 가능한 필드나 속성에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-103">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="efe10-104">개체 이니셜라이저 구문을 사용하면 생성자의 인수를 지정하거나 인수(및 괄호 구문)를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-104">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="efe10-105">다음 예제는 명명된 형식인 `Cat`의 개체 이니셜라이저를 사용하는 방법과 기본 생성자를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-105">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the default constructor.</span></span> <span data-ttu-id="efe10-106">`Cat` 클래스의 자동 구현된 속성 사용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-106">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="efe10-107">자세한 내용은 [자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efe10-107">For more information, see [Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="efe10-108">[!code-cs[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="efe10-108">[!code-cs[csProgGuideLINQ#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_1.cs)]</span></span>  
  
 <span data-ttu-id="efe10-109">[!code-cs[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="efe10-109">[!code-cs[csProgGuideLINQ#45](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_2.cs)]</span></span>  
  
## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="efe10-110">익명 형식의 개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="efe10-110">Object Initializers with anonymous types</span></span>  
 <span data-ttu-id="efe10-111">개체 이니셜라이저는 모든 컨텍스트에서 사용할 수 있지만 특히 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-111">Although object initializers can be used in any context, they are especially useful in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="efe10-112">쿼리 식은 [무명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 자주 사용합니다. 이 형식은 다음 선언에 표시된 바와 같이 개체 이니셜라이저를 사용하는 경우에만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-112">Query expressions make frequent use of [anonymous types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  
  
```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```  
  
 <span data-ttu-id="efe10-113">무명 형식을 사용하면 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식의 `select` 절에서 원래 시퀀스의 개체를 값과 모양이 원본과 다를 수 있는 개체로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-113">Anonymous types enable the `select` clause in a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="efe10-114">이 기능은 각 개체의 일부 정보만 시퀀스에 저장하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-114">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="efe10-115">다음 예제에서 제품 개체(`p`)는 많은 필드와 메서드를 포함하며, 제품 이름과 단위 가격이 들어 있는 개체 시퀀스만 만들려 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-115">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
 <span data-ttu-id="efe10-116">[!code-cs[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="efe10-116">[!code-cs[csProgGuideLINQ#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_3.cs)]</span></span>  
  
 <span data-ttu-id="efe10-117">이 쿼리를 실행하면 다음 예제와 같이 `productInfos` 문에서 액세스할 수 있는 개체 시퀀스가 `foreach` 변수에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-117">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  
  
```csharp
foreach(var p in productInfos){...}  
```  
  
 <span data-ttu-id="efe10-118">새 익명 형식의 각 개체에는 원래 개체의 속성이나 필드와 동일한 이름을 받는 두 개의 public 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-118">Each object in the new anonymous type has two public properties which receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="efe10-119">익명 형식을 만들 때 필드 이름을 바꿀 수도 있습니다. 다음 예제에서는 `UnitPrice` 필드의 이름을 `Price`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-119">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  
  
```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```  
  
## <a name="object-initializers-with-nullable-types"></a><span data-ttu-id="efe10-120">nullable 형식의 개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="efe10-120">Object initializers with nullable types</span></span>  
 <span data-ttu-id="efe10-121">개체 이니셜라이저에 nullable 구조체를 사용하는 것은 컴파일 시간 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-121">It is a compile-time error to use an object initializer with a nullable struct.</span></span>  
  
## <a name="collection-initializers"></a><span data-ttu-id="efe10-122">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="efe10-122">Collection initializers</span></span>  
 <span data-ttu-id="efe10-123">컬렉션 이니셜라이저를 사용하면 <xref:System.Collections.IEnumerable>을 구현하고 적절한 시그니처가 있는 `Add`를 인스턴스 메서드 또는 확장 메서드로 포함하는 컬렉션 형식을 초기화할 때 하나 이상의 요소 이니셜라이저를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-123">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="efe10-124">요소 이니셜라이저는 단순한 값, 식 또는 개체 이니셜라이저일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-124">The element initializers can be a simple value, an expression or an object initializer.</span></span> <span data-ttu-id="efe10-125">컬렉션 이니셜라이저를 사용하면 소스 코드에서 클래스의 `Add` 메서드에 대한 호출을 여러 번 지정할 필요가 없습니다. 컴파일러가 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-125">By using a collection initializer you do not have to specify multiple calls to the `Add` method of the class in your source code; the compiler adds the calls.</span></span>  
  
 <span data-ttu-id="efe10-126">다음 예제에서는 두 개의 단순한 컬렉션 이니셜라이저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-126">The following examples shows two simple collection initializers:</span></span>  
  
```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```  
  
 <span data-ttu-id="efe10-127">다음 컬렉션 이니셜라이저는 개체 이니셜라이저를 사용하여 앞의 예제에서 정의된 `Cat` 클래스의 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-127">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="efe10-128">개별 개체 이니셜라이저는 괄호로 묶이고 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-128">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
 <span data-ttu-id="efe10-129">[!code-cs[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="efe10-129">[!code-cs[csProgGuideLINQ#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_4.cs)]</span></span>  
  
 <span data-ttu-id="efe10-130">컬렉션의 `Add` 메서드에서 허용하는 경우 [null](../../../csharp/language-reference/keywords/null.md)을 컬렉션 이니셜라이저의 요소로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-130">You can specify [null](../../../csharp/language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
 <span data-ttu-id="efe10-131">[!code-cs[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="efe10-131">[!code-cs[csProgGuideLINQ#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_5.cs)]</span></span>  
  
 <span data-ttu-id="efe10-132">컬렉션이 인덱싱을 지원하는 경우 인덱싱된 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efe10-132">You can specify indexed elements if the collection supports indexing.</span></span>  
  
```csharp
var numbers = new Dictionary<int, string> {   
    [7] = "seven",   
    [9] = "nine",   
    [13] = "thirteen"   
};  
```  
  
## <a name="example"></a><span data-ttu-id="efe10-133">예제</span><span class="sxs-lookup"><span data-stu-id="efe10-133">Example</span></span>  
 <span data-ttu-id="efe10-134">[!code-cs[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="efe10-134">[!code-cs[csProgGuideLINQ#46](../../../csharp/programming-guide/arrays/codesnippet/CSharp/object-and-collection-initializers_6.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe10-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efe10-135">See Also</span></span>  
 <span data-ttu-id="efe10-136">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="efe10-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="efe10-137">[LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="efe10-137">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="efe10-138">익명 형식</span><span class="sxs-lookup"><span data-stu-id="efe10-138">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

