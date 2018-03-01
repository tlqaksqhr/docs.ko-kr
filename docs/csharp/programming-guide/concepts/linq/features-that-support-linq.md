---
title: "LINQ를 지원하는 C# 기능"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2f5accb188e54e0d3e2b941832637ec33afc26b2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="c-features-that-support-linq"></a><span data-ttu-id="66ba1-102">LINQ를 지원하는 C# 기능</span><span class="sxs-lookup"><span data-stu-id="66ba1-102">C# Features That Support LINQ</span></span>
<span data-ttu-id="66ba1-103">다음 섹션에서는 C# 3.0에 도입된 새로운 언어 구문을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-103">The following section introduces new language constructs introduced in C# 3.0.</span></span> <span data-ttu-id="66ba1-104">이러한 새 기능은 모두 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리에서 어느 정도 사용되지만 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]로 제한되지 않고 유용한 모든 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-104">Although these new features are all used to a degree with [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, they are not limited to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] and can be used in any context where you find them useful.</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="66ba1-105">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="66ba1-105">Query Expressions</span></span>  
 <span data-ttu-id="66ba1-106">쿼리 식은 SQL이나 XQuery와 유사한 선언적 구문을 사용하여 IEnumerable 컬렉션을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-106">Queries expressions use a declarative syntax similar to SQL or XQuery to query over IEnumerable collections.</span></span> <span data-ttu-id="66ba1-107">컴파일 시간에 쿼리 구문은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자의 표준 쿼리 연산자 확장 메서드 구현에 대한 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-107">At compile time query syntax is converted to method calls to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="66ba1-108">응용 프로그램은 `using` 지시문으로 적절한 네임스페이스를 지정하여 범위 내에 있는 표준 쿼리 연산자를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-108">Applications control the standard query operators that are in scope by specifying the appropriate namespace with a `using` directive.</span></span> <span data-ttu-id="66ba1-109">다음 쿼리 식은 문자열의 배열을 사용하고 문자열의 첫 번째 문자에 따라 그룹화하며 그룹의 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-109">The following query expression takes an array of strings, groups them according to the first character in the string, and orders the groups.</span></span>  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 <span data-ttu-id="66ba1-110">자세한 내용은 [LINQ 쿼리 식](../../../../csharp/programming-guide/linq-query-expressions/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ba1-110">For more information, see [LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md).</span></span>  
  
## <a name="implicitly-typed-variables-var"></a><span data-ttu-id="66ba1-111">암시적으로 형식화된 변수(var)</span><span class="sxs-lookup"><span data-stu-id="66ba1-111">Implicitly Typed Variables (var)</span></span>  
 <span data-ttu-id="66ba1-112">변수를 선언하고 초기화할 때 명시적으로 형식을 지정하는 대신 다음과 같이 [var](../../../../csharp/language-reference/keywords/var.md) 한정자를 사용하여 형식을 유추하고 할당하도록 컴파일러에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-112">Instead of explicitly specifying a type when you declare and initialize a variable, you can use the [var](../../../../csharp/language-reference/keywords/var.md) modifier to instruct the compiler to infer and assign the type, as shown here:</span></span>  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 <span data-ttu-id="66ba1-113">`var`로 선언된 변수는 형식을 명시적으로 지정한 변수만큼 강력한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-113">Variables declared as `var` are just as strongly-typed as variables whose type you specify explicitly.</span></span> <span data-ttu-id="66ba1-114">`var`을 사용하면 무명 형식을 만들 수 있지만 모든 지역 변수에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-114">The use of `var` makes it possible to create anonymous types, but it can be used for any local variable.</span></span> <span data-ttu-id="66ba1-115">배열은 암시적 형식 지정을 사용하여 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-115">Arrays can also be declared with implicit typing.</span></span>  
  
 <span data-ttu-id="66ba1-116">자세한 내용은 [암시적으로 형식화된 지역 변수](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ba1-116">For more information, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
## <a name="object-and-collection-initializers"></a><span data-ttu-id="66ba1-117">개체 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="66ba1-117">Object and Collection Initializers</span></span>  
 <span data-ttu-id="66ba1-118">개체 및 컬렉션 이니셜라이저를 사용하면 개체에 대한 생성자를 명시적으로 호출하지 않고 개체를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-118">Object and collection initializers make it possible to initialize objects without explicitly calling a constructor for the object.</span></span> <span data-ttu-id="66ba1-119">일반적으로 이니셜라이저는 소스 데이터를 새 데이터 형식으로 프로젝션할 때 쿼리 식에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-119">Initializers are typically used in query expressions when they project the source data into a new data type.</span></span> <span data-ttu-id="66ba1-120">public `Name` 및 `Phone` 속성이 있는 `Customer`라는 클래스를 가정할 경우 다음 코드에서처럼 개체 이니셜라이저를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-120">Assuming a class named `Customer` with public `Name` and `Phone` properties, the object initializer can be used as in the following code:</span></span>  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 <span data-ttu-id="66ba1-121">자세한 내용은 [개체 및 컬렉션 이니셜라이저](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ba1-121">For more information, see [Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="66ba1-122">익명 형식</span><span class="sxs-lookup"><span data-stu-id="66ba1-122">Anonymous Types</span></span>  
 <span data-ttu-id="66ba1-123">무명 형식은 컴파일러에서 생성되며 형식 이름은 컴파일러에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-123">An anonymous type is constructed by the compiler and the type name is only available to the compiler.</span></span> <span data-ttu-id="66ba1-124">무명 형식은 별도의 명명된 형식을 정의하지 않고 쿼리 결과에서 일시적으로 속성 집합을 그룹화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-124">Anonymous types provide a convenient way to group a set of properties temporarily in a query result without having to define a separate named type.</span></span> <span data-ttu-id="66ba1-125">무명 형식은 다음과 같이 새로운 식과 개체 이니셜라이저를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-125">Anonymous types are initialized with a new expression and an object initializer, as shown here:</span></span>  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 <span data-ttu-id="66ba1-126">자세한 내용은 [무명 형식](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ba1-126">For more information, see [Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="66ba1-127">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="66ba1-127">Extension Methods</span></span>  
 <span data-ttu-id="66ba1-128">확장 메서드는 형식과 연결하여 형식에 대한 인스턴스 메서드인 것처럼 호출할 수 있는 정적 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-128">An extension method is a static method that can be associated with a type, so that it can be called as if it were an instance method on the type.</span></span> <span data-ttu-id="66ba1-129">이 기능을 사용하면 실제로 수정하지 않고도 기존 형식에 새 메서드를 "추가"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-129">This feature enables you to, in effect, "add" new methods to existing types without actually modifying them.</span></span> <span data-ttu-id="66ba1-130">표준 쿼리 연산자는 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 모든 형식에 대해 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 기능을 제공하는 확장 메서드 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-130">The standard query operators are a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="66ba1-131">자세한 내용은 [확장 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ba1-131">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="66ba1-132">람다 식</span><span class="sxs-lookup"><span data-stu-id="66ba1-132">Lambda Expressions</span></span>  
 <span data-ttu-id="66ba1-133">람다 식은 => 연산자를 사용하여 함수 본문에서 입력 매개 변수를 구분하는 인라인 함수이며 컴파일 시간에 대리자나 식 트리로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-133">A lambda expression is an inline function that uses the => operator to separate input parameters from the function body and can be converted at compile time to a delegate or an expression tree.</span></span> <span data-ttu-id="66ba1-134">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 프로그래밍에서는 표준 쿼리 연산자에 대한 메서드를 직접 호출할 때 람다 식이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-134">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] programming, you will encounter lambda expressions when you make direct method calls to the standard query operators.</span></span>  
  
 <span data-ttu-id="66ba1-135">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ba1-135">For more information, see:</span></span>  
  
-   [<span data-ttu-id="66ba1-136">익명 함수</span><span class="sxs-lookup"><span data-stu-id="66ba1-136">Anonymous Functions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [<span data-ttu-id="66ba1-137">람다 식</span><span class="sxs-lookup"><span data-stu-id="66ba1-137">Lambda Expressions</span></span>](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [<span data-ttu-id="66ba1-138">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="66ba1-138">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
  
## <a name="auto-implemented-properties"></a><span data-ttu-id="66ba1-139">자동으로 구현된 속성</span><span class="sxs-lookup"><span data-stu-id="66ba1-139">Auto-Implemented Properties</span></span>  
 <span data-ttu-id="66ba1-140">자동으로 구현된 속성을 통해 속성을 보다 간단하게 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-140">Auto-implemented properties make property-declaration more concise.</span></span> <span data-ttu-id="66ba1-141">다음 예제와 같이 속성을 선언할 때 컴파일러는 getter 및 setter 속성을 통해서만 액세스할 수 있는 전용 무명 지원 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="66ba1-141">When you declare a property as shown in the following example, the compiler will create a private, anonymous backing field that is not accessible except through the property getter and setter.</span></span>  
  
```  
public string Name {get; set;}  
```  
  
 <span data-ttu-id="66ba1-142">자세한 내용은 [자동으로 구현된 속성](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ba1-142">For more information, see [Auto-Implemented Properties](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ba1-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66ba1-143">See Also</span></span>  
 [<span data-ttu-id="66ba1-144">LINQ(Language-Integrated Query)(C#)</span><span class="sxs-lookup"><span data-stu-id="66ba1-144">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
