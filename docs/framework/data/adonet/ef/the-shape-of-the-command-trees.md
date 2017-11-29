---
title: "명령 트리의 모양"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2215585e-ca47-45f8-98d4-8cb982f8c1d3
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c3311ac88355ac0d7214ec932719e1445757d9e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="the-shape-of-the-command-trees"></a><span data-ttu-id="2559b-102">명령 트리의 모양</span><span class="sxs-lookup"><span data-stu-id="2559b-102">The Shape of the Command Trees</span></span>
<span data-ttu-id="2559b-103">SQL 생성 모듈은 지정된 입력 쿼리 명령 트리 식을 기반으로 특정 백엔드 SQL 쿼리를 생성하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-103">The SQL generation module is responsible for generating a backend specific SQL query based on a given input query command tree expression.</span></span> <span data-ttu-id="2559b-104">이 단원에서는 쿼리 명령 트리의 특성, 속성 및 구조에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-104">This section discusses the characteristics, properties, and structure of the query command trees.</span></span>  
  
## <a name="query-command-trees-overview"></a><span data-ttu-id="2559b-105">쿼리 명령 트리 개요</span><span class="sxs-lookup"><span data-stu-id="2559b-105">Query Command Trees Overview</span></span>  
 <span data-ttu-id="2559b-106">쿼리 명령 트리는 쿼리의 개체 모델 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-106">A query command tree is an object model representation of a query.</span></span> <span data-ttu-id="2559b-107">쿼리 명령 트리는 다음 두 가지 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-107">Query command trees serve two purposes:</span></span>  
  
-   <span data-ttu-id="2559b-108">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에 대해 지정된 입력 쿼리를 표현하기 위해</span><span class="sxs-lookup"><span data-stu-id="2559b-108">To express an input query that is specified against the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="2559b-109">공급자에 제공되고 백엔드에 대한 쿼리를 설명하는 출력 쿼리를 표현하기 위해</span><span class="sxs-lookup"><span data-stu-id="2559b-109">To express an output query that is given to a provider and describes a query against the backend.</span></span>  
  
 <span data-ttu-id="2559b-110">쿼리 명령 트리는 SQL:1999 규격 쿼리보다 다양한 의미 체계를 지원합니다. 예를 들어, 엔터티가 특정 형식인지 확인하거나 형식을 기반으로 집합을 필터링하는 등의 형식 작업 및 중첩 컬렉션 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-110">Query command trees support richer semantics than SQL:1999 compliant queries, including support for working with nested collections and type operations, like checking whether an entity is of a particular type, or filtering sets based on a type.</span></span>  
  
 <span data-ttu-id="2559b-111">DBQueryCommandTree.Query 속성은 쿼리 논리를 설명하는 식 트리의 루트입니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-111">The DBQueryCommandTree.Query property is the root of the expression tree that describes the query logic.</span></span> <span data-ttu-id="2559b-112">DBQueryCommandTree.Parameters 속성에는 쿼리에서 사용되는 매개 변수의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-112">The DBQueryCommandTree.Parameters property contains a list of parameters that are used in the query.</span></span> <span data-ttu-id="2559b-113">식 트리는 DbExpression 개체로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-113">The expression tree is composed of DbExpression objects.</span></span>  
  
 <span data-ttu-id="2559b-114">DbExpression 개체는 특정 계산을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-114">A DbExpression object represents some computation.</span></span> <span data-ttu-id="2559b-115">몇 가지 종류의 식이 상수, 변수, 함수, 생성자 및 표준 관계형 연산자(필터, 조인 등)를 포함하는 쿼리 식을 작성할 수 있도록 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-115">Several kinds of expressions are provided by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] for composing query expressions, including constants, variables, functions, constructors, and standard relational operators like filter and join.</span></span> <span data-ttu-id="2559b-116">모든 DbExpression 개체에 해당 식에서 생성 되는 결과의 형식을 나타내는 ResultType 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-116">Every DbExpression object has a ResultType property that represents the type of the result produced by that expression.</span></span> <span data-ttu-id="2559b-117">이 형식은 TypeUsage로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-117">This type is expressed as a TypeUsage.</span></span>  
  
## <a name="shapes-of-the-output-query-command-tree"></a><span data-ttu-id="2559b-118">출력 쿼리 명령 트리의 모양</span><span class="sxs-lookup"><span data-stu-id="2559b-118">Shapes of the Output Query Command Tree</span></span>  
 <span data-ttu-id="2559b-119">출력 쿼리 명령 트리는 관계형(SQL) 쿼리를 유사하게 나타내며 쿼리 명령 트리에 적용되는 것보다 훨씬 엄격한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-119">Output query command trees closely represent relational (SQL) queries and adhere to much stricter rules than those that apply to query command trees.</span></span> <span data-ttu-id="2559b-120">일반적으로 출력 쿼리 명령 트리에는 SQL로 쉽게 변환되는 구문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-120">They typically contain constructs that are easily translated to SQL.</span></span>  
  
 <span data-ttu-id="2559b-121">입력 명령 트리는 탐색 속성, 엔터티 간의 연결 및 상속을 지원하는 개념적 모델에 대해 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-121">Input command trees are expressed against the conceptual model, which supports navigation properties, associations among entities, and inheritance.</span></span> <span data-ttu-id="2559b-122">출력 명령 트리는 저장소 모델에 대해 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-122">Output command trees are expressed against the storage model.</span></span> <span data-ttu-id="2559b-123">입력 명령 트리는 중첩 컬렉션을 프로젝션할 수 있도록 하지만 출력 명령 트리는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-123">Input command trees allow you to project nested collections, but output command trees do not.</span></span>  
  
 <span data-ttu-id="2559b-124">출력 쿼리 명령 트리는 사용 가능한 DbExpression 개체의 하위 집합을 사용하여 작성되며 해당 하위 집합의 일부 식은 제한적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-124">Output query command trees are built using a subset of the available DbExpression objects and even some expressions in that subset have restricted usage.</span></span>  
  
 <span data-ttu-id="2559b-125">지정된 식이 특정 형식인지 확인하거나 형식을 기반으로 집합을 필터링하는 등의 형식 작업은 출력 명령 트리에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-125">Type operations, like checking whether a given expression is of a particular type or filtering sets based on a type, are not present in output command trees.</span></span>  
  
 <span data-ttu-id="2559b-126">출력 명령 트리에서는 부울 값을 반환하는 식만 프로젝션에 사용되며 필터 또는 CASE 문과 같은 조건자가 필요한 식에서 조건자에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-126">In output command trees, only expressions that return Boolean values are used for projections and only for predicates in expressions requiring a predicate, like a filter or a case statement.</span></span>  
  
 <span data-ttu-id="2559b-127">출력 쿼리 명령 트리의 루트는 DbProjectExpression 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-127">The root of an output query command trees is a DbProjectExpression object.</span></span>  
  
### <a name="expression-types-not-present-in-output-query-command-trees"></a><span data-ttu-id="2559b-128">출력 쿼리 명령 트리에 없는 식 형식</span><span class="sxs-lookup"><span data-stu-id="2559b-128">Expression Types Not Present in Output Query Command Trees</span></span>  
 <span data-ttu-id="2559b-129">다음 식 형식은 출력 쿼리 명령 트리에서 유효하지 않으며 공급자가 처리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-129">The following expression types are not valid in an output query command tree and do not need to be handled by providers:</span></span>  
  
 <span data-ttu-id="2559b-130">DbDerefExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-130">DbDerefExpression</span></span>  
  
 <span data-ttu-id="2559b-131">DbEntityRefExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-131">DbEntityRefExpression</span></span>  
  
 <span data-ttu-id="2559b-132">DbRefKeyExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-132">DbRefKeyExpression</span></span>  
  
 <span data-ttu-id="2559b-133">DbIsOfExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-133">DbIsOfExpression</span></span>  
  
 <span data-ttu-id="2559b-134">DbOfTypeExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-134">DbOfTypeExpression</span></span>  
  
 <span data-ttu-id="2559b-135">DbRefExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-135">DbRefExpression</span></span>  
  
 <span data-ttu-id="2559b-136">DbRelationshipNavigationExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-136">DbRelationshipNavigationExpression</span></span>  
  
 <span data-ttu-id="2559b-137">DbTreatExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-137">DbTreatExpression</span></span>  
  
### <a name="expression-restrictions-and-notes"></a><span data-ttu-id="2559b-138">식 제한 사항 및 참고 정보</span><span class="sxs-lookup"><span data-stu-id="2559b-138">Expression Restrictions and Notes</span></span>  
 <span data-ttu-id="2559b-139">출력 쿼리 명령 트리에서 제한된 방식으로만 사용할 수 있는 식이 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-139">Many expressions can only be used in a restricted manner in output query command trees:</span></span>  
  
#### <a name="dbfunctionexpression"></a><span data-ttu-id="2559b-140">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-140">DbFunctionExpression</span></span>  
 <span data-ttu-id="2559b-141">다음 함수 형식이 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-141">The following function types can be passed:</span></span>  
  
-   <span data-ttu-id="2559b-142">Edm 네임스페이스에서 인식되는 정식 함수</span><span class="sxs-lookup"><span data-stu-id="2559b-142">Canonical functions that are recognized by the Edm namespace.</span></span>  
  
-   <span data-ttu-id="2559b-143">BuiltInAttribute에서 인식되는 기본 제공(저장소) 함수</span><span class="sxs-lookup"><span data-stu-id="2559b-143">Built-in (store) functions that are recognized by the BuiltInAttribute.</span></span>  
  
-   <span data-ttu-id="2559b-144">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="2559b-144">User-defined functions.</span></span>  
  
 <span data-ttu-id="2559b-145">정식 함수 (참조 [정식 함수](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) 자세한 내용은)의 일부로 지정는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], 공급자는 이러한 사양을 기반으로 하는 정식 함수에 대 한 구현을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-145">Canonical functions (see [Canonical Functions](../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) for more information) are specified as part of the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], and providers should supply implementations for canonical functions based on those specifications.</span></span> <span data-ttu-id="2559b-146">저장소 함수는 해당 공급자 매니페스트에 지정된 사항을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-146">Store functions are based on the specifications in the corresponding provider manifest.</span></span> <span data-ttu-id="2559b-147">사용자 정의 함수는 SSDL에서 지정된 사항을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-147">User defined functions are based on specifications in the SSDL.</span></span>  
  
 <span data-ttu-id="2559b-148">또한 NiladicFunction 특성이 있는 함수에는 인수가 없으며 끝에 괄호 없이 변환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-148">Also, functions having the NiladicFunction attribute have no arguments and should be translated without the parenthesis at the end.</span></span>  <span data-ttu-id="2559b-149">즉,  *\<functionName >* 대신  *\<functionName > ()*합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-149">That is, to *\<functionName>* instead of *\<functionName>()*.</span></span>  
  
#### <a name="dbnewinstanceexpression"></a><span data-ttu-id="2559b-150">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-150">DbNewInstanceExpression</span></span>  
 <span data-ttu-id="2559b-151">DbNewInstanceExpression은 다음 두 경우에만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-151">DbNewInstanceExpression can only occur in the following two cases:</span></span>  
  
-   <span data-ttu-id="2559b-152">DbProjectExpression의 Projection 속성으로.</span><span class="sxs-lookup"><span data-stu-id="2559b-152">As the Projection property of DbProjectExpression.</span></span>  <span data-ttu-id="2559b-153">이렇게 사용되는 경우 다음 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-153">When used as such the following restrictions apply:</span></span>  
  
    -   <span data-ttu-id="2559b-154">결과 형식이 행 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-154">The result type must be a row type.</span></span>  
  
    -   <span data-ttu-id="2559b-155">각 인수가 기본 형식을 사용하여 결과를 생성하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-155">Each of its arguments is an expression that produces a result with a primitive type.</span></span> <span data-ttu-id="2559b-156">일반적으로 각 인수는 DbVariableReferenceExpression을 통한 PropertyExpression과 같은 스칼라 식, 함수 호출 또는 DbVariableReferenceExpression을 통한 DbPropertyExpression 또는 함수 호출의 산술 계산입니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-156">Typically, each argument is a scalar expression, like a PropertyExpression over a DbVariableReferenceExpression, a function invocation, or an arithmetic computation of the DbPropertyExpression over a DbVariableReferenceExpression or a function invocation.</span></span> <span data-ttu-id="2559b-157">그러나 스칼라 하위 쿼리를 나타내는 식은 DbNewInstanceExpression의 인수 목록에서도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-157">However, an expression representing a scalar subquery can also occur in the list of arguments for a DbNewInstanceExpression.</span></span> <span data-ttu-id="2559b-158">스칼라 하위 쿼리를 나타내는 식은 DbElementExperession 개체 루트와 함께 기본 형식의 한 열과 한 행만 반환하는 하위 쿼리를 나타내는 식 트리입니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-158">An expression that represents a scalar subquery is an expression tree that represents a subquery that returns exactly one row and one column of a primitive type with a DbElementExperession object root</span></span>  
  
-   <span data-ttu-id="2559b-159">컬렉션 반환 형식과 함께. 이 경우 DbNewInstanceExpression은 인수로 제공된 식의 새 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-159">With a collection return type, in which case it defines a new collection of the expressions provided as arguments.</span></span>  
  
#### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="2559b-160">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-160">DbVariableReferenceExpression</span></span>  
 <span data-ttu-id="2559b-161">DbVariableReferenceExpression은 DbPropertyExpression 노드의 자식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-161">A DbVariableReferenceExpression has to be a child of DbPropertyExpression node.</span></span>  
  
#### <a name="dbgroupbyexpression"></a><span data-ttu-id="2559b-162">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-162">DbGroupByExpression</span></span>  
 <span data-ttu-id="2559b-163">DbGroupByExpression의 Aggregates 속성에는 DbFunctionAggregate 형식의 요소만 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-163">The Aggregates property of a DbGroupByExpression can only have elements of type DbFunctionAggregate.</span></span> <span data-ttu-id="2559b-164">다른 집계 형식은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-164">There are no other aggregate types.</span></span>  
  
#### <a name="dblimitexpression"></a><span data-ttu-id="2559b-165">DbLimitExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-165">DbLimitExpression</span></span>  
 <span data-ttu-id="2559b-166">Limit 속성은 DbConstantExpression 또는 DbParameterReferenceExpression일 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-166">The property Limit can only be a DbConstantExpression or a DbParameterReferenceExpression.</span></span> <span data-ttu-id="2559b-167">또한 WithTies 속성은 .NET Framework 버전 3.5부터 항상 false입니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-167">Also property WithTies is always false as of version 3.5 of the .NET Framework.</span></span>  
  
#### <a name="dbscanexpression"></a><span data-ttu-id="2559b-168">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="2559b-168">DbScanExpression</span></span>  
 <span data-ttu-id="2559b-169">출력 명령 트리에서 사용되는 경우 DbScanExpression은 EnitySetBase::Target이 나타내는 테이블, 뷰 또는 저장소 쿼리에 대한 검색을 효과적으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-169">When used in output command trees, the DbScanExpression effectively represents a scan over a table, a view, or a store query, represented by EnitySetBase::Target.</span></span>  
  
 <span data-ttu-id="2559b-170">메타 데이터 속성 "정의 쿼리"는 대상의 이면 null이 아닌 쿼리 나타냅니다 쿼리 텍스트를 공급자의 특정 언어 (또는 언어)는 저장소 스키마 정의에 지정 된 대로 해당 메타 데이터 속성에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-170">If the metadata property "Defining Query" of the target is non-null, then it represents a query, the query text for which is provided in that metadata property in the provider’s specific language (or dialect) as specified in the store schema definition.</span></span>  
  
 <span data-ttu-id="2559b-171">대상의 메타데이터 속성 “정의 쿼리”가 null이면 대상은 테이블 또는 뷰를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-171">Otherwise, the target represents a table or a view.</span></span> <span data-ttu-id="2559b-172">해당 스키마 접두사는 "스키마" 메타 데이터 속성에서 아니면 null로, 그렇지 않으면 엔터티 컨테이너 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-172">Its schema prefix is either in the "Schema" metadata property, if not null, otherwise is the entity container name.</span></span>  <span data-ttu-id="2559b-173">테이블 또는 뷰 이름은 중 하나는 "Table" 메타 데이터 속성이 null이 아니면, 그렇지 않으면 집합 기반의 Name 속성은 엔터티의입니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-173">The table or view name is either the "Table" metadata property, if not null, otherwise the Name property of the entity set base.</span></span>  
  
 <span data-ttu-id="2559b-174">이러한 모든 속성은 저장소 스키마 정의 파일(SSDL)에 있는 해당 EntitySet의 정의에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-174">All these properties originate from the definition of the corresponding EntitySet in the store schema definition file (the SSDL).</span></span>  
  
### <a name="using-primitive-types"></a><span data-ttu-id="2559b-175">기본 형식 사용</span><span class="sxs-lookup"><span data-stu-id="2559b-175">Using Primitive Types</span></span>  
 <span data-ttu-id="2559b-176">기본 형식이 출력 명령 트리에서 참조되는 경우 일반적으로 개념적 모델의 기본 형식에서 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-176">When primitive types are referenced in output command trees, they are typically referenced in the conceptual model's primitive types.</span></span> <span data-ttu-id="2559b-177">그러나 특정 식의 경우 공급자에 해당 저장소 기본 형식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-177">However, for certain expressions, providers need the corresponding store primitive type.</span></span> <span data-ttu-id="2559b-178">이러한 식에는 DbCastExpression, DbNullExpression(공급자가 null을 해당 형식으로 캐스팅해야 하는 경우) 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-178">Examples of such expressions include DbCastExpression and possibly DbNullExpression, if the provider needs to cast the null to the corresponding type.</span></span> <span data-ttu-id="2559b-179">이러한 경우에 공급자는 기본 형식 종류와 해당 패싯에 따라 공급자 형식으로 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2559b-179">In these cases, providers should do the mapping to the provider type based on the primitive type kind and its facets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2559b-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2559b-180">See Also</span></span>  
 [<span data-ttu-id="2559b-181">SQL 생성</span><span class="sxs-lookup"><span data-stu-id="2559b-181">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
