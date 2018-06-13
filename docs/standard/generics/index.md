---
title: .NET의 제네릭
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generic methods, type inference
- generics [.NET Framework], collections
- generic interfaces [.NET Framework]
- constructed generic types
- nested generic types
- generic type definitions
- generic classes [.NET Framework]
- generics [.NET Framework], interfaces
- generics [.NET Framework], about
- generics [.NET Framework]
- generic collections [.NET Framework]
- generic delegates [.NET Framework]
- generic type arguments
- generics [.NET Framework], delegates
- generics [.NET Framework], features
- constraints [.NET Framework]
- generic types
- generic type parameters
ms.assetid: 2994d786-c5c7-4666-ab23-4c83129fe39c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e5aea783640a2aa2c9f4fa7754b9a3a435d1f13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579069"
---
# <a name="generics-in-net"></a><span data-ttu-id="4f784-102">.NET의 제네릭</span><span class="sxs-lookup"><span data-stu-id="4f784-102">Generics in .NET</span></span>

<a name="top"></a> <span data-ttu-id="4f784-103">제네릭을 사용하면 메서드, 클래스, 구조체 또는 인터페이스를 사용 대상인 정확한 데이터 형식에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-103">Generics let you tailor a method, class, structure, or interface to the precise data type it acts upon.</span></span> <span data-ttu-id="4f784-104">예를 들어 모든 형식의 키와 값을 허용하는 <xref:System.Collections.Hashtable> 클래스를 사용하는 대신 <xref:System.Collections.Generic.Dictionary%602> 제네릭 클래스를 사용하고 키에 허용되는 형식과 값에 허용되는 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-104">For example, instead of using the <xref:System.Collections.Hashtable> class, which allows keys and values to be of any type, you can use the <xref:System.Collections.Generic.Dictionary%602> generic class and specify the type allowed for the key and the type allowed for the value.</span></span> <span data-ttu-id="4f784-105">제네릭의 이점으로는 향상된 코드 다시 사용 가능성과 형식 안전성 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-105">Among the benefits of generics are increased code reusability and type safety.</span></span>  
  
 <span data-ttu-id="4f784-106">이 항목에서는 .NET 제네릭에 대해 간략하게 설명하고 제네릭 형식이나 메서드의 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-106">This topic provides an overview of generics in .NET and a summary of generic types or methods.</span></span> <span data-ttu-id="4f784-107">여기에는 다음 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-107">It contains the following sections:</span></span>  
  
-   [<span data-ttu-id="4f784-108">제네릭 정의 및 사용</span><span class="sxs-lookup"><span data-stu-id="4f784-108">Defining and Using Generics</span></span>](#defining_and_using_generics)  
  
-   [<span data-ttu-id="4f784-109">제네릭 관련 용어</span><span class="sxs-lookup"><span data-stu-id="4f784-109">Generics Terminology</span></span>](#generics_terminology)  
  
-   [<span data-ttu-id="4f784-110">클래스 라이브러리 및 언어 지원</span><span class="sxs-lookup"><span data-stu-id="4f784-110">Class Library and Language Support</span></span>](#class_library_and_language_support)  
  
-   [<span data-ttu-id="4f784-111">중첩 형식 및 제네릭</span><span class="sxs-lookup"><span data-stu-id="4f784-111">Nested Types and Generics</span></span>](#nested_types_and_generics)  
  
-   [<span data-ttu-id="4f784-112">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4f784-112">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="4f784-113">참조</span><span class="sxs-lookup"><span data-stu-id="4f784-113">Reference</span></span>](#reference)  
  
<a name="defining_and_using_generics"></a>   
## <a name="defining-and-using-generics"></a><span data-ttu-id="4f784-114">제네릭 정의 및 사용</span><span class="sxs-lookup"><span data-stu-id="4f784-114">Defining and Using Generics</span></span>  
 <span data-ttu-id="4f784-115">제네릭은 저장하거나 사용하는 하나 이상의 형식에 대한 자리 표시자(형식 매개 변수)를 포함하는 클래스, 구조체, 인터페이스 및 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-115">Generics are classes, structures, interfaces, and methods that have placeholders (type parameters) for one or more of the types that they store or use.</span></span> <span data-ttu-id="4f784-116">제네릭 컬렉션 클래스는 저장하는 개체 형식에 대해 형식 매개 변수를 자리 표시자로 사용할 수 있습니다. 형식 매개 변수는 필드의 형식과 메서드의 매개 변수 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-116">A generic collection class might use a type parameter as a placeholder for the type of objects that it stores; the type parameters appear as the types of its fields and the parameter types of its methods.</span></span> <span data-ttu-id="4f784-117">제네릭 메서드는 형식 매개 변수를 반환 값의 형식 또는 정식 매개 변수 중 하나의 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-117">A generic method might use its type parameter as the type of its return value or as the type of one of its formal parameters.</span></span> <span data-ttu-id="4f784-118">다음 코드에서는 간단한 제네릭 클래스 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-118">The following code illustrates a simple generic class definition.</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#2)]
 [!code-csharp[Conceptual.Generics.Overview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#2)]
 [!code-vb[Conceptual.Generics.Overview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#2)]  
  
 <span data-ttu-id="4f784-119">제네릭 클래스의 인스턴스를 만들 때는 형식 매개 변수를 대체할 실제 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-119">When you create an instance of a generic class, you specify the actual types to substitute for the type parameters.</span></span> <span data-ttu-id="4f784-120">이렇게 하면 형식 매개 변수가 표시되는 모든 위치에서 선택한 형식으로 대체된 새 제네릭 클래스인 생성된 제네릭 형식이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-120">This establishes a new generic class, referred to as a constructed generic class, with your chosen types substituted everywhere that the type parameters appear.</span></span> <span data-ttu-id="4f784-121">그 결과 다음 코드에 나와 있는 것처럼 선택한 형식에 맞게 조정된 형식이 안전한 클래스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-121">The result is a type-safe class that is tailored to your choice of types, as the following code illustrates.</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#3)]
 [!code-csharp[Conceptual.Generics.Overview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#3)]
 [!code-vb[Conceptual.Generics.Overview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#3)]  
  
<a name="generics_terminology"></a>   
### <a name="generics-terminology"></a><span data-ttu-id="4f784-122">제네릭 관련 용어</span><span class="sxs-lookup"><span data-stu-id="4f784-122">Generics terminology</span></span>  
 <span data-ttu-id="4f784-123">.NET에서 제네릭을 설명하는 데 사용되는 용어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-123">The following terms are used to discuss generics in .NET:</span></span>  
  
-   <span data-ttu-id="4f784-124">*제네릭 형식 정의* 는 포함하거나 사용할 수 있는 형식에 대한 자리 표시자를 포함하며 템플릿으로 작동하는 클래스, 구조체 또는 인터페이스 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-124">A *generic type definition* is a class, structure, or interface declaration that functions as a template, with placeholders for the types that it can contain or use.</span></span> <span data-ttu-id="4f784-125">예를 들어 <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> 클래스는 키와 값의 두 형식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-125">For example, the <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class can contain two types: keys and values.</span></span> <span data-ttu-id="4f784-126">제네릭 형식 정의는 템플릿일 뿐이므로 제네릭 형식 정의인 클래스, 구조체 또는 인터페이스의 인스턴스를 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-126">Because a generic type definition is only a template, you cannot create instances of a class, structure, or interface that is a generic type definition.</span></span>  
  
-   <span data-ttu-id="4f784-127">*제네릭 형식 매개 변수*( *형식 매개 변수*)는 제네릭 형식 또는 메서드 정의의 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-127">*Generic type parameters*, or *type parameters*, are the placeholders in a generic type or method definition.</span></span> <span data-ttu-id="4f784-128"><xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> 제네릭 형식에는 키와 값의 형식을 나타내는 두 형식 매개 변수 `TKey` 및 `TValue`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-128">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> generic type has two type parameters, `TKey` and `TValue`, that represent the types of its keys and values.</span></span>  
  
-   <span data-ttu-id="4f784-129">*생성된 제네릭 형식*( *생성된 형식*)은 제네릭 형식 정의의 제네릭 형식 매개 변수에 대한 형식을 지정한 결과로 생성된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-129">A *constructed generic type*, or *constructed type*, is the result of specifying types for the generic type parameters of a generic type definition.</span></span>  
  
-   <span data-ttu-id="4f784-130">*제네릭 형식 인수* 는 제네릭 형식 매개 변수에 대해 대체되는 모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-130">A *generic type argument* is any type that is substituted for a generic type parameter.</span></span>  
  
-   <span data-ttu-id="4f784-131">일반 용어인 *제네릭 형식* 에는 생성된 형식과 제네릭 형식 정의가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-131">The general term *generic type* includes both constructed types and generic type definitions.</span></span>  
  
-   <span data-ttu-id="4f784-132">제네릭 형식 매개 변수의*공 분산(covariance)* 및 *반공변성(contravariance)* of generic type parameters enable you to use constructed generic types whose type arguments are more derived (covariance) or less derived (반공변성(contravariance)) than a target constructed type.</span><span class="sxs-lookup"><span data-stu-id="4f784-132">*Covariance* and *contravariance* of generic type parameters enable you to use constructed generic types whose type arguments are more derived (covariance) or less derived (contravariance) than a target constructed type.</span></span> <span data-ttu-id="4f784-133">공 분산과 반공 분산을 통칭하여 *가변성(variance)* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-133">Covariance and contravariance are collectively referred to as *variance*.</span></span> <span data-ttu-id="4f784-134">자세한 내용은 [공변성(Covariance) 및 반공변성(Contravariance)](../../../docs/standard/generics/covariance-and-contravariance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f784-134">For more information, see [Covariance and Contravariance](../../../docs/standard/generics/covariance-and-contravariance.md).</span></span>  
  
-   <span data-ttu-id="4f784-135">*제약 조건*은 제네릭 형식 매개 변수에 대해 적용되는 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-135">*Constraints* are limits placed on generic type parameters.</span></span> <span data-ttu-id="4f784-136">예를 들어 형식 인스턴스의 순서를 지정할 수 있도록 <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> 제네릭 인터페이스를 구현하는 형식으로 형식 매개 변수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-136">For example, you might limit a type parameter to types that implement the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> generic interface, to ensure that instances of the type can be ordered.</span></span> <span data-ttu-id="4f784-137">또한 참조 형식 또는 값 형식이거나 특정 기본 클래스 또는 기본 생성자를 포함하는 형식으로 형식 매개 변수를 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-137">You can also constrain type parameters to types that have a particular base class, that have a default constructor, or that are reference types or value types.</span></span> <span data-ttu-id="4f784-138">제네릭 형식의 사용자는 제약 조건을 충족하지 않는 형식 인수를 대체할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-138">Users of the generic type cannot substitute type arguments that do not satisfy the constraints.</span></span>  
  
-   <span data-ttu-id="4f784-139">*제네릭 메서드 정의* 는 두 개의 매개 변수 목록(제네릭 형식 매개 변수 목록 및 정식 매개 변수 목록)을 포함하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-139">A *generic method definition* is a method with two parameter lists: a list of generic type parameters and a list of formal parameters.</span></span> <span data-ttu-id="4f784-140">형식 매개 변수는 다음 코드에 나와 있는 것처럼 정식 매개 변수의 형식 또는 반환 형식으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-140">Type parameters can appear as the return type or as the types of the formal parameters, as the following code shows.</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#4)]
 [!code-csharp[Conceptual.Generics.Overview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#4)]
 [!code-vb[Conceptual.Generics.Overview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#4)]  
  
 <span data-ttu-id="4f784-141">제네릭 메서드는 제네릭 형식 또는 제네릭이 아닌 형식으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-141">Generic methods can appear on generic or nongeneric types.</span></span> <span data-ttu-id="4f784-142">메서드는 단순히 제네릭 형식에 속한다고 해서 제네릭인 것은 아니며, 형식이 바깥쪽 형식의 제네릭 매개 변수인 정식 매개 변수를 포함하더라도 제네릭은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-142">It is important to note that a method is not generic just because it belongs to a generic type, or even because it has formal parameters whose types are the generic parameters of the enclosing type.</span></span> <span data-ttu-id="4f784-143">메서드는 자체 형식 매개 변수 목록을 포함하는 경우에만 제네릭입니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-143">A method is generic only if it has its own list of type parameters.</span></span> <span data-ttu-id="4f784-144">다음 코드에서는 `G` 메서드만 제네릭입니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-144">In the following code, only method `G` is generic.</span></span>  
  
 [!code-cpp[Conceptual.Generics.Overview#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source.cpp#5)]
 [!code-csharp[Conceptual.Generics.Overview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source.cs#5)]
 [!code-vb[Conceptual.Generics.Overview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source.vb#5)]  
  
 [<span data-ttu-id="4f784-145">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="4f784-145">Back to top</span></span>](#top)  
  
<a name="advantages_limitations"></a>   
## <a name="advantages-and-disadvantages-of-generics"></a><span data-ttu-id="4f784-146">제네릭의 장점 및 단점</span><span class="sxs-lookup"><span data-stu-id="4f784-146">Advantages and disadvantages of generics</span></span>  
 <span data-ttu-id="4f784-147">제네릭 컬렉션과 대리자를 사용하는 경우의 장점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-147">There are many advantages to using generic collections and delegates:</span></span>  
  
-   <span data-ttu-id="4f784-148">형식 안전성.</span><span class="sxs-lookup"><span data-stu-id="4f784-148">Type safety.</span></span> <span data-ttu-id="4f784-149">제네릭을 사용하면 컴파일러에서 형식 안전성을 보장해야 하는 부담이 없어집니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-149">Generics shift the burden of type safety from you to the compiler.</span></span> <span data-ttu-id="4f784-150">컴파일 타임에 올바른 데이터 형식이 적용되므로 코드를 작성하여 데이터 형식을 테스트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-150">There is no need to write code to test for the correct data type because it is enforced at compile time.</span></span> <span data-ttu-id="4f784-151">형식 캐스팅의 필요성과 런타임 오류 발생 가능성도 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-151">The need for type casting and the possibility of run-time errors are reduced.</span></span>  
  
-   <span data-ttu-id="4f784-152">코드의 양이 감소하며 코드를 보다 쉽게 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-152">Less code and code is more easily reused.</span></span> <span data-ttu-id="4f784-153">기본 형식에서 상속하고 멤버를 재정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-153">There is no need to inherit from a base type and override members.</span></span> <span data-ttu-id="4f784-154">예를 들어 <xref:System.Collections.Generic.LinkedList%601> 은 즉시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-154">For example, the <xref:System.Collections.Generic.LinkedList%601> is ready for immediate use.</span></span> <span data-ttu-id="4f784-155">다음 변수 선언을 사용하면 문자열의 연결된 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-155">For example, you can create a linked list of strings with the following variable declaration:</span></span>  
  
     [!code-cpp[HowToGeneric#24](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/source2.cpp#24)]
     [!code-csharp[HowToGeneric#24](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/source2.cs#24)]
     [!code-vb[HowToGeneric#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/source2.vb#24)]  
  
-   <span data-ttu-id="4f784-156">성능 향상.</span><span class="sxs-lookup"><span data-stu-id="4f784-156">Better performance.</span></span> <span data-ttu-id="4f784-157">제네릭 컬렉션 형식은 값 형식을 boxing할 필요가 없기 때문에 일반적으로 값 형식 저장 및 조작 시 성능이 보다 우수합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-157">Generic collection types generally perform better for storing and manipulating value types because there is no need to box the value types.</span></span>  
  
-   <span data-ttu-id="4f784-158">제네릭 대리자를 사용하면 여러 대리자 클래스를 만들지 않고도 형식이 안전한 콜백을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-158">Generic delegates enable type-safe callbacks without the need to create multiple delegate classes.</span></span> <span data-ttu-id="4f784-159">예를 들어 <xref:System.Predicate%601> 제네릭 대리자를 사용하면 특정 형식에 대해 고유한 검색 기준을 구현하는 메서드를 만든 다음 <xref:System.Array> , <xref:System.Array.Find%2A>, <xref:System.Array.FindLast%2A>등의 <xref:System.Array.FindAll%2A>형식 메서드와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-159">For example, the <xref:System.Predicate%601> generic delegate allows you to create a method that implements your own search criteria for a particular type and to use your method with methods of the <xref:System.Array> type such as <xref:System.Array.Find%2A>, <xref:System.Array.FindLast%2A>, and <xref:System.Array.FindAll%2A>.</span></span>  
  
-   <span data-ttu-id="4f784-160">제네릭을 통해 동적으로 생성된 코드를 원활하게 실행.</span><span class="sxs-lookup"><span data-stu-id="4f784-160">Generics streamline dynamically generated code.</span></span> <span data-ttu-id="4f784-161">동적으로 생성된 코드에서 제네릭을 사용하는 경우 형식을 생성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-161">When you use generics with dynamically generated code you do not need to generate the type.</span></span> <span data-ttu-id="4f784-162">이로 인해 전체 어셈블리를 생성하는 대신 간단한 동적 메서드를 사용할 수 있는 시나리오의 수가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-162">This increases the number of scenarios in which you can use lightweight dynamic methods instead of generating entire assemblies.</span></span> <span data-ttu-id="4f784-163">자세한 내용은 방법: 동적 메서드 및 DynamicMethod 정의 및 실행을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f784-163">For more information, see How to: Define and Execute Dynamic Methods and DynamicMethod.</span></span>  
  
 <span data-ttu-id="4f784-164">아래에는 제네릭의 몇 가지 제한이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-164">The following are some limitations of generics:</span></span>  
  
-   <span data-ttu-id="4f784-165">제네릭 형식은 <xref:System.MarshalByRefObject> 와 같은 대부분의 기본 클래스에서 파생될 수 있으며, 제약 조건을 사용하면 제네릭 형식 매개 변수가 <xref:System.MarshalByRefObject>와 같은 기본 클래스에서 파생되어야 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-165">Generic types can be derived from most base classes, such as <xref:System.MarshalByRefObject> (and constraints can be used to require that generic type parameters derive from base classes like <xref:System.MarshalByRefObject>).</span></span> <span data-ttu-id="4f784-166">그러나 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 에서는 컨텍스트에 바인딩된 제네릭 형식을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-166">However, the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] does not support context-bound generic types.</span></span> <span data-ttu-id="4f784-167">제네릭 형식이 <xref:System.ContextBoundObject>에서 파생될 수는 있지만 해당 형식의 인스턴스를 만들려고 하면 <xref:System.TypeLoadException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-167">A generic type can be derived from <xref:System.ContextBoundObject>, but trying to create an instance of that type causes a <xref:System.TypeLoadException>.</span></span>  
  
-   <span data-ttu-id="4f784-168">열거형은 제네릭 형식 매개 변수를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-168">Enumerations cannot have generic type parameters.</span></span> <span data-ttu-id="4f784-169">열거형은 Visual Basic, C# 또는 C++를 사용하여 정의되는 제네릭 형식에 중첩되는 경우 부수적으로만 제네릭이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-169">An enumeration can be generic only incidentally (for example, because it is nested in a generic type that is defined using Visual Basic, C#, or C++).</span></span> <span data-ttu-id="4f784-170">자세한 내용은 [Common Type System](../../../docs/standard/base-types/common-type-system.md)에서 “열거”를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f784-170">For more information, see "Enumerations" in [Common Type System](../../../docs/standard/base-types/common-type-system.md).</span></span>  
  
-   <span data-ttu-id="4f784-171">경량의 동적 메서드는 제네릭이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-171">Lightweight dynamic methods cannot be generic.</span></span>  
  
-   <span data-ttu-id="4f784-172">Visual Basic, C# 및 C++에서는 모든 바깥쪽 형식의 형식 매개 변수에 형식이 할당된 경우가 아니면 제네릭 형식으로 묶인 중첩 형식을 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-172">In Visual Basic, C#, and C++, a nested type that is enclosed in a generic type cannot be instantiated unless types have been assigned to the type parameters of all enclosing types.</span></span> <span data-ttu-id="4f784-173">다시 말해서, 리플렉션에서 이러한 언어를 사용하여 정의되는 중첩 형식은 모든 바깥쪽 형식의 형식 매개 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-173">Another way of saying this is that in reflection, a nested type that is defined using these languages includes the type parameters of all its enclosing types.</span></span> <span data-ttu-id="4f784-174">따라서 바깥쪽 형식의 형식 매개 변수를 중첩 형식의 멤버 정의에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-174">This allows the type parameters of enclosing types to be used in the member definitions of a nested type.</span></span> <span data-ttu-id="4f784-175">자세한 내용은 <xref:System.Type.MakeGenericType%2A>의 "중첩 형식"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f784-175">For more information, see "Nested Types" in <xref:System.Type.MakeGenericType%2A>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f784-176">동적 어셈블리에서 코드를 내보내거나 [Ilasm.exe(IL 어셈블러)](../../../docs/framework/tools/ilasm-exe-il-assembler.md)를 사용하여 정의되는 중첩 형식은 바깥쪽 형식의 형식 매개 변수를 포함하지 않아도 됩니다. 그러나 형식 매개 변수를 포함하지 않는 경우에는 중첩 클래스의 범위 내에 형식 매개 변수가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-176">A nested type that is defined by emitting code in a dynamic assembly or by using the [Ilasm.exe (IL Assembler)](../../../docs/framework/tools/ilasm-exe-il-assembler.md) is not required to include the type parameters of its enclosing types; however, if it does not include them, the type parameters are not in scope in the nested class.</span></span>  
  
     <span data-ttu-id="4f784-177">자세한 내용은 <xref:System.Type.MakeGenericType%2A>의 "중첩 형식"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f784-177">For more information, see "Nested Types" in <xref:System.Type.MakeGenericType%2A>.</span></span>  
  
 [<span data-ttu-id="4f784-178">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="4f784-178">Back to top</span></span>](#top)  
  
<a name="class_library_and_language_support"></a>   
## <a name="class-library-and-language-support"></a><span data-ttu-id="4f784-179">클래스 라이브러리 및 언어 지원</span><span class="sxs-lookup"><span data-stu-id="4f784-179">Class Library and Language Support</span></span>  
 <span data-ttu-id="4f784-180">.NET에서는 다음 네임스페이스에서 다양한 제네릭 컬렉션 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-180">.NET provides a number of generic collection classes in the following namespaces:</span></span>  
  
-   <span data-ttu-id="4f784-181"><xref:System.Collections.Generic> 네임스페이스에는 <xref:System.Collections.Generic.List%601> 및 <xref:System.Collections.Generic.Dictionary%602> 제네릭 클래스와 같이 .NET에서 제공하는 대부분의 제네릭 컬렉션 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-181">The <xref:System.Collections.Generic> namespace contains most of the generic collection types provided by .NET, such as the <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602> generic classes.</span></span>  
  
-   <span data-ttu-id="4f784-182"><xref:System.Collections.ObjectModel> 네임스페이스에는 클래스 사용자에게 개체 모델을 노출하는 데 유용한 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 제네릭 클래스와 같은 추가 제네릭 컬렉션 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-182">The <xref:System.Collections.ObjectModel> namespace contains additional generic collection types, such as the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> generic class, that are useful for exposing object models to users of your classes.</span></span>  
  
 <span data-ttu-id="4f784-183">정렬 및 같음 비교를 구현하는 제네릭 인터페이스는 이벤트 처리기, 변환 및 검색 조건자용 제네릭 대리자 형식과 함께 <xref:System> 네임스페이스에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-183">Generic interfaces for implementing sort and equality comparisons are provided in the <xref:System> namespace, along with generic delegate types for event handlers, conversions, and search predicates.</span></span>  
  
 <span data-ttu-id="4f784-184">제네릭 형식 및 제네릭 메서드 검사를 위한 <xref:System.Reflection> 네임스페이스, 제네릭 형식과 메서드를 포함하는 동적 어셈블리 내보내기를 위한 <xref:System.Reflection.Emit> 네임스페이스 그리고 제네릭을 포함하는 소스 그래프 생성을 위한 <xref:System.CodeDom> 네임스페이스에 제네릭 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-184">Support for generics has been added to the <xref:System.Reflection> namespace for examining generic types and generic methods, to <xref:System.Reflection.Emit> for emitting dynamic assemblies that contain generic types and methods, and to <xref:System.CodeDom> for generating source graphs that include generics.</span></span>  
  
 <span data-ttu-id="4f784-185">공용 언어 런타임에서는 <xref:System.Reflection.Emit.OpCodes.Stelem>, <xref:System.Reflection.Emit.OpCodes.Ldelem>, <xref:System.Reflection.Emit.OpCodes.Unbox_Any>, <xref:System.Reflection.Emit.OpCodes.Constrained>, <xref:System.Reflection.Emit.OpCodes.Readonly>등의 MSIL(Microsoft Intermediate Language)에서 제네릭 형식을 지원하기 위한 새로운 opcode 및 접두사를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-185">The common language runtime provides new opcodes and prefixes to support generic types in Microsoft intermediate language (MSIL), including <xref:System.Reflection.Emit.OpCodes.Stelem>, <xref:System.Reflection.Emit.OpCodes.Ldelem>, <xref:System.Reflection.Emit.OpCodes.Unbox_Any>, <xref:System.Reflection.Emit.OpCodes.Constrained>, and <xref:System.Reflection.Emit.OpCodes.Readonly>.</span></span>  
  
 <span data-ttu-id="4f784-186">Visual C++, C# 및 Visual Basic은 모두 제네릭 정의 및 사용을 위한 모든 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-186">Visual C++, C#, and Visual Basic all provide full support for defining and using generics.</span></span> <span data-ttu-id="4f784-187">언어 지원에 대한 자세한 내용은 [Visual Basic의 제네릭 형식](~/docs/visual-basic/programming-guide/language-features/data-types/generic-types.md), [제네릭 소개](~/docs/csharp/programming-guide/generics/introduction-to-generics.md) 및 [Visual C++의 제네릭 개요](/cpp/windows/overview-of-generics-in-visual-cpp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f784-187">For more information about language support, see [Generic Types in Visual Basic](~/docs/visual-basic/programming-guide/language-features/data-types/generic-types.md), [Introduction to Generics](~/docs/csharp/programming-guide/generics/introduction-to-generics.md), and [Overview of Generics in Visual C++](/cpp/windows/overview-of-generics-in-visual-cpp).</span></span>  
  
 [<span data-ttu-id="4f784-188">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="4f784-188">Back to top</span></span>](#top)  
  
<a name="nested_types_and_generics"></a>   
## <a name="nested-types-and-generics"></a><span data-ttu-id="4f784-189">중첩 형식 및 제네릭</span><span class="sxs-lookup"><span data-stu-id="4f784-189">Nested Types and Generics</span></span>  
 <span data-ttu-id="4f784-190">제네릭 형식에 중첩된 형식은 바깥쪽 제네릭 형식의 형식 매개 변수에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-190">A type that is nested in a generic type can depend on the type parameters of the enclosing generic type.</span></span> <span data-ttu-id="4f784-191">공용 언어 런타임은 고유한 제네릭 형식 매개 변수를 포함하지 않는 중첩 형식도 제네릭으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-191">The common language runtime considers nested types to be generic, even if they do not have generic type parameters of their own.</span></span> <span data-ttu-id="4f784-192">중첩 형식의 인스턴스를 만들 때는 모든 바깥쪽 제네릭 형식에 대해 형식 인수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-192">When you create an instance of a nested type, you must specify type arguments for all enclosing generic types.</span></span>  
  
 [<span data-ttu-id="4f784-193">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="4f784-193">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="4f784-194">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4f784-194">Related Topics</span></span>  
  
|<span data-ttu-id="4f784-195">제목</span><span class="sxs-lookup"><span data-stu-id="4f784-195">Title</span></span>|<span data-ttu-id="4f784-196">설명</span><span class="sxs-lookup"><span data-stu-id="4f784-196">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4f784-197">.NET의 제네릭 컬렉션</span><span class="sxs-lookup"><span data-stu-id="4f784-197">Generic Collections in .NET</span></span>](../../../docs/standard/generics/collections.md)|<span data-ttu-id="4f784-198">.NET의 제네릭 컬렉션 클래스 및 기타 제네릭 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-198">Describes generic collection classes and other generic types in .NET.</span></span>|  
|[<span data-ttu-id="4f784-199">배열과 목록을 조작하기 위한 제네릭 대리자</span><span class="sxs-lookup"><span data-stu-id="4f784-199">Generic Delegates for Manipulating Arrays and Lists</span></span>](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)|<span data-ttu-id="4f784-200">배열 또는 컬렉션의 요소에 대해 수행할 작업, 검색 조건자 및 변환을 위한 제네릭 대리자에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-200">Describes generic delegates for conversions, search predicates, and actions to be taken on elements of an array or collection.</span></span>|  
|[<span data-ttu-id="4f784-201">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f784-201">Generic Interfaces</span></span>](../../../docs/standard/generics/interfaces.md)|<span data-ttu-id="4f784-202">여러 제네릭 형식 패밀리에 대해 공통 기능을 제공하는 제네릭 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-202">Describes generic interfaces that provide common functionality across families of generic types.</span></span>|  
|[<span data-ttu-id="4f784-203">공 분산 및 반공 분산</span><span class="sxs-lookup"><span data-stu-id="4f784-203">Covariance and Contravariance</span></span>](../../../docs/standard/generics/covariance-and-contravariance.md)|<span data-ttu-id="4f784-204">제네릭 형식 매개 변수의 공 분산(covariance) 및 반공변성(contravariance)에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-204">Describes covariance and contravariance in generic type parameters.</span></span>|  
|[<span data-ttu-id="4f784-205">일반적으로 사용되는 컬렉션 형식</span><span class="sxs-lookup"><span data-stu-id="4f784-205">Commonly Used Collection Types</span></span>](../../../docs/standard/collections/commonly-used-collection-types.md)|<span data-ttu-id="4f784-206">제네릭 형식을 비롯하여 .NET의 컬렉션 형식 특성과 사용 시나리오에 대한 요약 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-206">Provides summary information about the characteristics and usage scenarios of the collection types in .NET, including generic types.</span></span>|  
|[<span data-ttu-id="4f784-207">제네릭 컬렉션 사용 기준</span><span class="sxs-lookup"><span data-stu-id="4f784-207">When to Use Generic Collections</span></span>](../../../docs/standard/collections/when-to-use-generic-collections.md)|<span data-ttu-id="4f784-208">제네릭 컬렉션 형식의 사용 시기를 결정하기 위한 일반 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-208">Describes general rules for determining when to use generic collection types.</span></span>|  
|[<span data-ttu-id="4f784-209">방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의</span><span class="sxs-lookup"><span data-stu-id="4f784-209">How to: Define a Generic Type with Reflection Emit</span></span>](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)|<span data-ttu-id="4f784-210">제네릭 형식과 메서드가 포함된 동적 어셈블리를 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-210">Explains how to generate dynamic assemblies that include generic types and methods.</span></span>|  
|[<span data-ttu-id="4f784-211">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f784-211">Generic Types in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/generic-types.md)|<span data-ttu-id="4f784-212">제네릭 형식 사용 및 정의에 대한 방법 항목을 포함하여 Visual Basic 사용자를 위한 제네릭 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-212">Describes the generics feature for Visual Basic users, including how-to topics for using and defining generic types.</span></span>|  
|[<span data-ttu-id="4f784-213">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="4f784-213">Introduction to Generics</span></span>](~/docs/csharp/programming-guide/generics/introduction-to-generics.md)|<span data-ttu-id="4f784-214">C# 사용자를 위한 제네릭 형식 사용 및 정의 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-214">Provides an overview of defining and using generic types for C# users.</span></span>|  
|[<span data-ttu-id="4f784-215">Visual C++의 제네릭 개요</span><span class="sxs-lookup"><span data-stu-id="4f784-215">Overview of Generics in Visual C++</span></span>](/cpp/windows/overview-of-generics-in-visual-cpp)|<span data-ttu-id="4f784-216">제네릭과 템플릿 간의 차이점을 비롯하여 C++ 사용자를 위한 제네릭 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f784-216">Describes the generics feature for C++ users, including the differences between generics and templates.</span></span>|  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="4f784-217">참조</span><span class="sxs-lookup"><span data-stu-id="4f784-217">Reference</span></span>  
 <xref:System.Collections.Generic>  
  
 <xref:System.Collections.ObjectModel>  
  
 <xref:System.Reflection.Emit.OpCodes?displayProperty=nameWithType>  
  
 [<span data-ttu-id="4f784-218">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="4f784-218">Back to top</span></span>](#top)
