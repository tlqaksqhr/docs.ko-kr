---
title: "Visual Basic LINQ를 지 원하는 기능 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: 51
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 728018de7e38374875b15a809e5659003519d60f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-features-that-support-linq"></a><span data-ttu-id="03561-102">LINQ를 지원하는 Visual Basic 기능</span><span class="sxs-lookup"><span data-stu-id="03561-102">Visual Basic Features That Support LINQ</span></span>
<span data-ttu-id="03561-103">이름 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] Visual Basic 쿼리 구문을 지원 하 고 다른 언어 구문이 도입 되면서 언어에서 직접 기술을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="03561-103">The name [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] refers to technology in Visual Basic that supports query syntax and other language constructs directly in the language.</span></span> <span data-ttu-id="03561-104">와 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], 외부 데이터 원본에 대 한 쿼리는 새 언어를 배울 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-104">With [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], you do not have to learn a new language to query against an external data source.</span></span> <span data-ttu-id="03561-105">Visual Basic을 사용 하 여 관계형 데이터베이스, XML 저장소 또는 개체의 데이터에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-105">You can query against data in relational databases, XML stores, or objects by using Visual Basic.</span></span> <span data-ttu-id="03561-106">이 통합 언어 쿼리 기능의 구문 오류 및 형식 안전성에 대 한 컴파일 타임 검사 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-106">This integration of query capabilities into the language enables compile-time checking for syntax errors and type safety.</span></span> <span data-ttu-id="03561-107">이 통합은 또한 대부분의 Visual Basic의 다양 한 기능의 다양 한 쿼리를 작성 하기 위해 알아야 할 사항 이미 알고 있다고 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-107">This integration also ensures that you already know most of what you have to know to write rich, varied queries in Visual Basic.</span></span>  
  
 <span data-ttu-id="03561-108">다음 단원에서는 LINQ를 지 원하는 소개 문서, 코드 예제 및 샘플 응용 프로그램을 읽기 시작 수 있도록 충분 한 세부 정보에는 언어 구문을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-108">The following sections describe the language constructs that support LINQ in enough detail to enable you to get started in reading the introductory documentation, code examples, and sample applications.</span></span> <span data-ttu-id="03561-109">언어 기능 함께 일 하 언어 통합 쿼리를 사용 하도록 설정 하는 방법의 자세한 설명을 찾을 수 있는 링크를 눌러도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03561-109">You can also click the links to find more detailed explanations of how the language features come together to enable language-integrated query.</span></span> <span data-ttu-id="03561-110">시작 하려면 먼저 [연습: Visual Basic에서 쿼리 작성](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-110">A good place to start is [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="03561-111">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="03561-111">Query Expressions</span></span>  
 <span data-ttu-id="03561-112">Visual Basic에서 쿼리 식 SQL 또는 XQuery와 유사한 선언적 구문으로 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-112">Query expressions in Visual Basic can be expressed in a declarative syntax similar to that of SQL or XQuery.</span></span> <span data-ttu-id="03561-113">컴파일 타임에 쿼리 구문은 표준 쿼리 연산자 확장 메서드의 LINQ 공급자의 구현에 대 한 메서드 호출으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03561-113">At compile time, query syntax is converted into method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="03561-114">표준 쿼리 연산자에에서 있는 범위와 적절 한 네임 스페이스를 지정 하 여 응용 프로그램 제어는 `Imports` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="03561-114">Applications control which standard query operators are in scope by specifying the appropriate namespace with an `Imports` statement.</span></span> <span data-ttu-id="03561-115">Visual Basic 쿼리 식 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-115">Syntax for a Visual Basic query expression looks like this:</span></span>  
  
 <span data-ttu-id="03561-116">[!code-vb[VbLINQVbFeatures #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-116">[!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]</span></span>  
  
 <span data-ttu-id="03561-117">자세한 내용은 참조 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-117">For more information, see [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
## <a name="implicitly-typed-variables"></a><span data-ttu-id="03561-118">암시적으로 형식화 된 변수</span><span class="sxs-lookup"><span data-stu-id="03561-118">Implicitly Typed Variables</span></span>  
 <span data-ttu-id="03561-119">대신 명시적으로 유형을 지정 하는 선언 하 고 변수를 초기화할 때 유추 하 고 유형을 할당 컴파일러를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-119">Instead of explicitly specifying a type when you declare and initialize a variable, you can enable the compiler to infer and assign the type.</span></span> <span data-ttu-id="03561-120">이 라고 *지역 형식 유추*합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-120">This is referred to as *local type inference*.</span></span>  
  
 <span data-ttu-id="03561-121">변수 형식이 유추 되는 강력한 마찬가지로 형식 변수 형식을 명시적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-121">Variables whose types are inferred are strongly typed, just like variables whose type you specify explicitly.</span></span> <span data-ttu-id="03561-122">지역 형식 유추 메서드 본문 내에서 지역 변수를 정의 하는 경우에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-122">Local type inference works only when you are defining a local variable inside a method body.</span></span> <span data-ttu-id="03561-123">자세한 내용은 참조 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [로컬 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-123">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="03561-124">다음 예제에서는 지역 형식 유추를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03561-124">The following example illustrates local type inference.</span></span> <span data-ttu-id="03561-125">이 예제를 사용 하려면 설정 해야 `Option Infer` 를 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-125">To use this example, you must set `Option Infer` to `On`.</span></span>  
  
 <span data-ttu-id="03561-126">[!code-vb[VbLINQVbFeatures #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-126">[!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]</span></span>  
  
 <span data-ttu-id="03561-127">지역 형식 유추를 하면 나중에이 섹션에 설명 되어 있으며 LINQ 쿼리에 필요한 익명 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-127">Local type inference also makes it possible to create anonymous types, which are described later in this section and are necessary for LINQ queries.</span></span>  
  
 <span data-ttu-id="03561-128">다음 LINQ 예제의 경우 형식 유추가 발생 `Option Infer` 은 `On` 또는 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-128">In the following LINQ example, type inference occurs if `Option Infer` is either `On` or `Off`.</span></span> <span data-ttu-id="03561-129">컴파일 타임 오류가 발생 하는 경우 `Option Infer` 는 `Off` 및 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-129">A compile-time error occurs if `Option Infer` is `Off` and `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="03561-130">[!code-vb[VbLINQVbFeatures #&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-130">[!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]</span></span>  
  
## <a name="object-initializers"></a><span data-ttu-id="03561-131">개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="03561-131">Object Initializers</span></span>  
 <span data-ttu-id="03561-132">개체 이니셜라이저는 쿼리 결과를 저장할 익명 형식을 만들어야 할 때 쿼리 식에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03561-132">Object initializers are used in query expressions when you have to create an anonymous type to hold the results of a query.</span></span> <span data-ttu-id="03561-133">또한 수 데 사용할 쿼리 외부에서 명명 된 형식의 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-133">They also can be used to initialize objects of named types outside of queries.</span></span> <span data-ttu-id="03561-134">개체 이니셜라이저를 사용 하 여 명시적으로 생성자를 호출 하지 않고 한 줄에 있는 개체를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-134">By using an object initializer, you can initialize an object in a single line without explicitly calling a constructor.</span></span> <span data-ttu-id="03561-135">라는 클래스가 있는 경우 `Customer` 공개 된 `Name` 및 `Phone` 속성을 다른 속성과 함께 개체 이니셜라이저는 것이 방식:</span><span class="sxs-lookup"><span data-stu-id="03561-135">Assuming that you have a class named `Customer` that has public `Name` and `Phone` properties, along with other properties, an object initializer can be used in this manner:</span></span>  
  
 <span data-ttu-id="03561-136">[!code-vb[VbLINQVbFeatures #&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-136">[!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]</span></span>  
  
 <span data-ttu-id="03561-137">자세한 내용은 참조 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-137">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="03561-138">익명 형식</span><span class="sxs-lookup"><span data-stu-id="03561-138">Anonymous Types</span></span>  
 <span data-ttu-id="03561-139">익명 형식은 일시적으로 쿼리 결과에 포함 하려는 요소에는 속성 집합을 그룹화 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-139">Anonymous types provide a convenient way to temporarily group a set of properties into an element that you want to include in a query result.</span></span> <span data-ttu-id="03561-140">이 요소에 대 한 명명 된 데이터 형식을 정의 하지 않고 임의의 순서로 쿼리에서 사용할 수 있는 필드의 조합을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-140">This enables you to choose any combination of available fields in the query, in any order, without defining a named data type for the element.</span></span>  
  
 <span data-ttu-id="03561-141">*익명 형식* 은 컴파일러에 의해 동적으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-141">An *anonymous type* is constructed dynamically by the compiler.</span></span> <span data-ttu-id="03561-142">형식의 이름은 컴파일러에 의해 할당 됩니다 하 고 새로 컴파일할 때마다 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-142">The name of the type is assigned by the compiler, and it might change with each new compilation.</span></span> <span data-ttu-id="03561-143">따라서 이름은 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-143">Therefore, the name cannot be used directly.</span></span> <span data-ttu-id="03561-144">익명 형식은 다음과 같은 방식으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03561-144">Anonymous types are initialized in the following way:</span></span>  
  
 <span data-ttu-id="03561-145">[!code-vb[VbLINQVbFeatures #&5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-145">[!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]</span></span>  
  
 <span data-ttu-id="03561-146">자세한 내용은 참조 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="03561-147">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="03561-147">Extension Methods</span></span>  
 <span data-ttu-id="03561-148">확장 메서드를 사용 하는 데이터 형식 또는 정의 외부에서 인터페이스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-148">Extension methods enable you to add methods to a data type or interface from outside the definition.</span></span> <span data-ttu-id="03561-149">이 기능을 사용 하면 실제로 실제로 형식을 수정 하지 않고도 기존 형식에 새 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-149">This feature enables you to, in effect, add new methods to an existing type without actually modifying the type.</span></span> <span data-ttu-id="03561-150">표준 쿼리 연산자를 제공 하는 확장 메서드의 집합을 자체는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> 를 구현 하는 형식에 대 한 쿼리 기능</span><span class="sxs-lookup"><span data-stu-id="03561-150">The standard query operators are themselves a set of extension methods that provide [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="03561-151">에 대 한 다른 확장 <xref:System.Collections.Generic.IEnumerable%601>포함 <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, 및 <xref:System.Linq.Enumerable.Intersect%2A>.</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Union%2A> </xref:System.Linq.Enumerable.Count%2A> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="03561-151">Other extensions to <xref:System.Collections.Generic.IEnumerable%601> include <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 <span data-ttu-id="03561-152"><xref:System.String>클래스</xref:System.String> 인쇄 메서드를 추가 하는 다음 확장 메서드</span><span class="sxs-lookup"><span data-stu-id="03561-152">The following extension method adds a print method to the <xref:System.String> class.</span></span>  
  
 <span data-ttu-id="03561-153">[!code-vb[VbLINQVbFeatures #&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-153">[!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]</span></span>  
  
 <span data-ttu-id="03561-154"><xref:System.String>::</xref:System.String> 의 일반적인 인스턴스 메서드와 같은 메서드는</span><span class="sxs-lookup"><span data-stu-id="03561-154">The method is called like an ordinary instance method of <xref:System.String>:</span></span>  
  
 <span data-ttu-id="03561-155">[!code-vb[VbLINQVbFeatures #&7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-155">[!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]</span></span>  
  
 <span data-ttu-id="03561-156">자세한 내용은 참조 [확장 메서드](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-156">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="03561-157">람다 식</span><span class="sxs-lookup"><span data-stu-id="03561-157">Lambda Expressions</span></span>  
 <span data-ttu-id="03561-158">람다 식은 계산 하 고 단일 값을 반환 하는 이름이 없는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="03561-158">A lambda expression is a function without a name that calculates and returns a single value.</span></span> <span data-ttu-id="03561-159">명명 된 함수와 달리에 람다 식을 정의 하 고 동시에 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-159">Unlike named functions, a lambda expression can be defined and executed at the same time.</span></span> <span data-ttu-id="03561-160">다음 예제에서는 4를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-160">The following example displays 4.</span></span>  
  
 <span data-ttu-id="03561-161">[!code-vb[VbLINQVbFeatures #&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-161">[!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]</span></span>  
  
 <span data-ttu-id="03561-162">변수 이름에 람다 식 정의 할당할 수 있으며 다음 이름을 사용 하 여 함수 호출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03561-162">You can assign the lambda expression definition to a variable name and then use the name to call the function.</span></span> <span data-ttu-id="03561-163">다음 예제에는 4 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03561-163">The following example also displays 4.</span></span>  
  
 <span data-ttu-id="03561-164">[!code-vb[VbLINQVbFeatures #&12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-164">[!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]</span></span>  
  
 <span data-ttu-id="03561-165">[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], 람다 식 기반 표준 쿼리 연산자 중 상당수를 갖추어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-165">In [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], lambda expressions underlie many of the standard query operators.</span></span> <span data-ttu-id="03561-166">컴파일러와 같은 기본 쿼리 메서드에 정의 된 계산을 캡처하는 람다 식을 만듭니다 `Where`, `Select`, `Order By`, `Take While`, 등입니다.</span><span class="sxs-lookup"><span data-stu-id="03561-166">The compiler creates lambda expressions to capture the calculations that are defined in fundamental query methods such as `Where`, `Select`, `Order By`, `Take While`, and others.</span></span>  
  
 <span data-ttu-id="03561-167">예를 들어 다음 코드는 학생의 목록에서 모든 선임 학생을 반환 하는 쿼리를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-167">For example, the following code defines a query that returns all senior students from a list of students.</span></span>  
  
 <span data-ttu-id="03561-168">[!code-vb[VbLINQVbFeatures #&9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-168">[!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]</span></span>  
  
 <span data-ttu-id="03561-169">쿼리 정의 대 한 인수를 지정 하는 두 개의 람다 식을 사용 하는 다음 예제와 비슷한 코드로 컴파일될 `Where` 및 `Select`합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-169">The query definition is compiled into code that is similar to the following example, which uses two lambda expressions to specify the arguments for `Where` and `Select`.</span></span>  
  
 <span data-ttu-id="03561-170">[!code-vb[VbLINQVbFeatures #&10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-170">[!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]</span></span>  
  
 <span data-ttu-id="03561-171">두 버전 중 하나를 사용 하 여 실행할 수는 `For Each` 루프:</span><span class="sxs-lookup"><span data-stu-id="03561-171">Either version can be run by using a `For Each` loop:</span></span>  
  
 <span data-ttu-id="03561-172">[!code-vb[VbLINQVbFeatures #&11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="03561-172">[!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]</span></span>  
  
 <span data-ttu-id="03561-173">자세한 내용은 참조 [람다 식](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03561-173">For more information, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03561-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03561-174">See Also</span></span>  
 <span data-ttu-id="03561-175">[언어 통합 쿼리 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="03561-175">[Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md) </span></span>  
<span data-ttu-id="03561-176"> [Visual Basic에서 LINQ 시작](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="03561-176"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
<span data-ttu-id="03561-177"> [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="03561-177"> [LINQ and Strings (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
<span data-ttu-id="03561-178"> [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="03561-178"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="03561-179"> [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="03561-179"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
