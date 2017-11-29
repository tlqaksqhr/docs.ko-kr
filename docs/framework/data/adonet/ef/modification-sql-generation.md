---
title: "수정 SQL 생성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0c41f818c554b61dd6e63818627cb494f7c01577
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="modification-sql-generation"></a><span data-ttu-id="f7717-102">수정 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="f7717-102">Modification SQL Generation</span></span>
<span data-ttu-id="f7717-103">이 단원에서는 SQL:1999 규격 데이터베이스 공급자에 대한 수정 SQL 생성 모듈을 개발하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-103">This section discusses how to develop a modification SQL generation module for your (SQL:1999-compliant database) provider.</span></span> <span data-ttu-id="f7717-104">이 모듈은 수정 명령 트리를 적절한 SQL INSERT, UPDATE 또는 DELETE 문으로 변환하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-104">This module is responsible for translating a modification command tree into the appropriate SQL INSERT, UPDATE or DELETE statements.</span></span>  
  
 <span data-ttu-id="f7717-105">Select 문에 대 한 SQL 생성에 대 한 정보를 참조 하십시오. [SQL 생성](../../../../../docs/framework/data/adonet/ef/sql-generation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-105">For information about SQL generation for select statements, see [SQL Generation](../../../../../docs/framework/data/adonet/ef/sql-generation.md).</span></span>  
  
## <a name="overview-of-modification-command-trees"></a><span data-ttu-id="f7717-106">수정 명령 트리 개요</span><span class="sxs-lookup"><span data-stu-id="f7717-106">Overview of Modification Command Trees</span></span>  
 <span data-ttu-id="f7717-107">수정 SQL 생성 모듈은 지정된 입력 DbModificationCommandTree를 기반으로 데이터베이스 관련 수정 SQL 문을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-107">The modification SQL generation module generates database-specific modification SQL statements based on a given input DbModificationCommandTree.</span></span>  
  
 <span data-ttu-id="f7717-108">DbModificationCommandTree는 DbCommandTree에서 상속하는 수정 DML 작업(삽입, 업데이트 또는 삭제 작업)의 개체 모델 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-108">A DbModificationCommandTree is an object model representation of a modification DML operation (an insert, an update, or a delete operation), inheriting from DbCommandTree.</span></span> <span data-ttu-id="f7717-109">DbModificationCommandTree의 구현은 다음 세 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-109">There are three implementations of DbModificationCommandTree:</span></span>  
  
-   <span data-ttu-id="f7717-110">DbInsertCommandTree</span><span class="sxs-lookup"><span data-stu-id="f7717-110">DbInsertCommandTree</span></span>  
  
-   <span data-ttu-id="f7717-111">DbUpdateCommandTree</span><span class="sxs-lookup"><span data-stu-id="f7717-111">DbUpdateCommandTree</span></span>  
  
-   <span data-ttu-id="f7717-112">DbDeleteCommandTree</span><span class="sxs-lookup"><span data-stu-id="f7717-112">DbDeleteCommandTree</span></span>  
  
 <span data-ttu-id="f7717-113">DbModificationCommandTree 및 구현 과정에서 생성 되는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 항상 단일 행 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-113">DbModificationCommandTree and its implementations that are produced by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] always represent a single row operation.</span></span> <span data-ttu-id="f7717-114">이 단원에서는 .NET Framework 버전 3.5에서 이러한 형식과 관련 제약 조건에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-114">This section describes these types with their constraints in the .NET Framework version 3.5.</span></span>  
  
 <span data-ttu-id="f7717-115">![다이어그램](../../../../../docs/framework/data/adonet/ef/media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span><span class="sxs-lookup"><span data-stu-id="f7717-115">![Diagram](../../../../../docs/framework/data/adonet/ef/media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")</span></span>  
  
 <span data-ttu-id="f7717-116">DbModificationCommandTree에는 수정 작업의 대상 집합을 나타내는 Target 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-116">DbModificationCommandTree has a Target property that represents the target set for the modification operation.</span></span> <span data-ttu-id="f7717-117">Target의 Expression 속성은 입력 집합을 정의하며 항상 DbScanExpression입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-117">The Target’s Expression property, which defines the input set is always DbScanExpression.</span></span>  <span data-ttu-id="f7717-118">DbScanExpression 테이블 또는 뷰를 나타낼 수 있습니다 또는 데이터 집합이 정의 된 쿼리를 통해 메타 데이터 속성 "정의 쿼리"는 대상의 경우 null이 아닌.</span><span class="sxs-lookup"><span data-stu-id="f7717-118">A DbScanExpression can either represent a table or a view, or a set of data defined with a query if the metadata property "Defining Query" of its Target is non-null.</span></span>  
  
 <span data-ttu-id="f7717-119">쿼리를 나타내는 DbScanExpression은 모델에서 정의 쿼리를 사용하여 집합이 정의되었지만 해당 수정 작업에 대한 함수가 제공되지 않은 경우 수정 대상으로만 공급자에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-119">A DbScanExpression that represents a query could only reach a provider as a target of modification if the set was defined by using a defining query in the model but no function was provided for the corresponding modification operation.</span></span> <span data-ttu-id="f7717-120">공급자가 이러한 시나리오를 지원하지 못할 수도 있습니다. 예를 들어, SqlClient는 이러한 시나리오를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-120">Providers may not be able to support such a scenario (SqlClient, for example, does not).</span></span>  
  
 <span data-ttu-id="f7717-121">DbInsertCommandTree는 명령 트리로 표현된 단일 행 삽입 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-121">DbInsertCommandTree represents a single row insert operation expressed as a command tree.</span></span>  
  
```  
public sealed class DbInsertCommandTree : DbModificationCommandTree {  
   public IList<DbModificationClause> SetClauses { get }  
   public DbExpression Returning { get }  
}  
```  
  
 <span data-ttu-id="f7717-122">DbUpdateCommandTree는 명령 트리로 표현된 단일 행 업데이트 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-122">DbUpdateCommandTree represents a single-row update operation expressed as a command tree.</span></span>  
  
 <span data-ttu-id="f7717-123">DbDeleteCommandTree는 명령 트리로 표현된 단일 행 삭제 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-123">DbDeleteCommandTree represents a single row delete operation expressed as a command tree.</span></span>  
  
### <a name="restrictions-on-modification-command-tree-properties"></a><span data-ttu-id="f7717-124">수정 명령 트리 속성에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="f7717-124">Restrictions on Modification Command Tree Properties</span></span>  
 <span data-ttu-id="f7717-125">다음 정보와 제한 사항은 수정 명령 트리 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-125">The following information and restrictions apply to the modification command tree properties.</span></span>  
  
#### <a name="returning-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="f7717-126">DbInsertCommandTree 및 DbUpdateCommandTree의 Returning</span><span class="sxs-lookup"><span data-stu-id="f7717-126">Returning in DbInsertCommandTree and DbUpdateCommandTree</span></span>  
 <span data-ttu-id="f7717-127">Returning이 null이 아니면 명령이 판독기를 반환함을 나타내고,</span><span class="sxs-lookup"><span data-stu-id="f7717-127">When non-null, Returning indicates that the command returns a reader.</span></span> <span data-ttu-id="f7717-128">그렇지 않으면 명령이 영향을 받는(삽입 또는 업데이트되는) 행의 수를 나타내는 스칼라 값을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-128">Otherwise, the command should return a scalar value indicating the number of rows affected (inserted or updated).</span></span>  
  
 <span data-ttu-id="f7717-129">Returning 값은 삽입되거나 업데이트된 행을 기반으로 반환될 결과의 프로젝션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-129">The Returning value specifies a projection of results to be returned based on the inserted or the updated row.</span></span> <span data-ttu-id="f7717-130">이 값은 행을 나타내는 DbNewInstanceExpression 형식일 수만 있으며 각 인수는 해당 DbModificationCommandTree의 Target에 대한 참조를 나타내는 DbVariableReferenceExpression을 통한 DbPropertyExpression입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-130">It can only be of type DbNewInstanceExpression representing a row, with each of its arguments being a DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span> <span data-ttu-id="f7717-131">Returning 속성에서 사용되는 DbPropertyExpressions가 나타내는 속성은 항상 저장소 생성 또는 계산 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-131">The properties represented by the DbPropertyExpressions used in the property Returning are always store generated or computed values.</span></span> <span data-ttu-id="f7717-132">DbInsertCommandTree에서 Returning은 행이 삽입될 테이블의 속성 중 하나 이상이 저장소 생성 또는 계산으로 지정된 경우(ssdl에서 StoreGeneratedPattern.Identity 또는 StoreGeneratedPattern.Computed로 표시됨) null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-132">In DbInsertCommandTree, Returning is not null when at least one property of the table in which the row is being inserted is specified as store generated or computed (marked as StoreGeneratedPattern.Identity or StoreGeneratedPattern.Computed in the ssdl).</span></span> <span data-ttu-id="f7717-133">DbUpdateCommandTree에서 Returning은 행이 업데이트될 테이블의 속성 중 하나 이상이 저장소 계산으로 지정된 경우(ssdl에서 StoreGeneratedPattern.Computed로 표시됨) null이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-133">In DbUpdateCommandTrees, Returning is not null when at least one property of the table in which the row is being updated is specified as store computed (marked as StoreGeneratedPattern.Computed in the ssdl).</span></span>  
  
#### <a name="setclauses-in-dbinsertcommandtree-and-dbupdatecommandtree"></a><span data-ttu-id="f7717-134">DbInsertCommandTree 및 DbUpdateCommandTree의 SetClauses</span><span class="sxs-lookup"><span data-stu-id="f7717-134">SetClauses in DbInsertCommandTree and DbUpdateCommandTree</span></span>  
 <span data-ttu-id="f7717-135">SetClauses는 삽입 또는 업데이트 작업을 정의하는 insert 또는 update set 절의 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-135">SetClauses specifies the list of insert or update set clauses that define the insert or update operation.</span></span>  
  
```  
The elements of the list are specified as type DbModificationClause, which specifies a single clause in an insert or update modification operation. DbSetClause inherits from DbModificationClause and specifies the clause in a modification operation that sets the value of a property. Beginning in version 3.5 of the .NET Framework, all elements in SetClauses are of type SetClause.   
```  
  
 <span data-ttu-id="f7717-136">Property는 업데이트할 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-136">Property specifies the property that should be updated.</span></span> <span data-ttu-id="f7717-137">Property는 항상 해당 DbModificationCommandTree의 Target에 대한 참조를 나타내는 DbVariableReferenceExpression을 통한 DbPropertyExpression입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-137">It is always a DbPropertyExpression over a DbVariableReferenceExpression, which represents a reference to the Target of the corresponding DbModificationCommandTree.</span></span>  
  
 <span data-ttu-id="f7717-138">Value는 속성을 업데이트할 새 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-138">Value specifies the new value with which to update the property.</span></span> <span data-ttu-id="f7717-139">Value는 DbConstantExpression 또는 DbNullExpression 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-139">It is either of type DbConstantExpression or DbNullExpression.</span></span>  
  
#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a><span data-ttu-id="f7717-140">DbUpdateCommandTree 및 DbDeleteCommandTree의 Predicate</span><span class="sxs-lookup"><span data-stu-id="f7717-140">Predicate in DbUpdateCommandTree and DbDeleteCommandTree</span></span>  
 <span data-ttu-id="f7717-141">Predicate는 대상 컬렉션에서 업데이트하거나 삭제할 멤버를 결정하는 데 사용되는 조건자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-141">Predicate specifies the predicate used to determine which members of the target collection should be updated or deleted.</span></span> <span data-ttu-id="f7717-142">Predicate는 DbExpression의 다음 하위 집합으로 작성된 식 트리입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-142">It is an expression tree built of the following subset of DbExpressions:</span></span>  
  
-   <span data-ttu-id="f7717-143">오른쪽 자식은 아래에 제한된 대로 DbPropertyExression이고 왼쪽 자식은 DbConstantExpression인 Equals 유형의 DbComparisonExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-143">DbComparisonExpression of kind Equals, with the right child being a DbPropertyExression as restricted below and the left child a DbConstantExpression.</span></span>  
  
-   <span data-ttu-id="f7717-144">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-144">DbConstantExpression</span></span>  
  
-   <span data-ttu-id="f7717-145">아래에 제한된 대로 DbPropertyExpresison을 통한 DbIsNullExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-145">DbIsNullExpression over a DbPropertyExpresison as restricted below</span></span>  
  
-   <span data-ttu-id="f7717-146">해당 DbModificationCommandTree의 Target에 대한 참조를 나타내는 DbVariableReferenceExpression을 통한 DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-146">DbPropertyExpression over a DbVariableReferenceExpression representing a reference to the Target of the corresponding DbModificationCommandTree.</span></span>  
  
-   <span data-ttu-id="f7717-147">DbAndExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-147">DbAndExpression</span></span>  
  
-   <span data-ttu-id="f7717-148">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-148">DbNotExpression</span></span>  
  
-   <span data-ttu-id="f7717-149">DbOrExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-149">DbOrExpression</span></span>  
  
## <a name="modification-sql-generation-in-the-sample-provider"></a><span data-ttu-id="f7717-150">샘플 공급자의 수정 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="f7717-150">Modification SQL Generation in the Sample Provider</span></span>  
 <span data-ttu-id="f7717-151">[Entity Framework 샘플 공급자](http://go.microsoft.com/fwlink/?LinkId=180616) 지 원하는 ADO.NET 데이터 공급자의 구성 요소가 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-151">The [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="f7717-152">샘플 공급자는 SQL Server 2005 데이터베이스를 대상으로 하며 System.Data.SqlClient ADO.NET 2.0 데이터 공급자 위에 래퍼로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-152">It targets a SQL Server 2005 database and is implemented as a wrapper on top of System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="f7717-153">샘플 공급자의 수정 SQL 생성 모듈(SQL Generation\DmlSqlGenerator.cs 파일에 있음)은 DbModificationCommandTree를 입력으로 사용하고 단일 수정 SQL 문을 생성합니다. 이 문 뒤에는 DbModificationCommandTree에서 지정된 경우 판독기를 반환하기 위해 SELECT 문이 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-153">The modification SQL generation module of the sample provider (located in the file SQL Generation\DmlSqlGenerator.cs) takes an input DbModificationCommandTree and produces a single modification SQL statement possibly followed by a select statement to return a reader if specified by the DbModificationCommandTree.</span></span> <span data-ttu-id="f7717-154">생성된 명령의 모양은 대상 SQL Server 데이터베이스의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-154">Note that the shape of the commands generated is affected by the target SQL Server database.</span></span>  
  
### <a name="helper-classes-expressiontranslator"></a><span data-ttu-id="f7717-155">도우미 클래스: ExpressionTranslator</span><span class="sxs-lookup"><span data-stu-id="f7717-155">Helper Classes: ExpressionTranslator</span></span>  
 <span data-ttu-id="f7717-156">ExpressionTranslator는 DbExpression 형식의 모든 수정 명령 트리 속성에 대해 공통적인 간단한 변환기 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-156">ExpressionTranslator serves as a common lightweight translator for all modification command tree properties of type DbExpression.</span></span> <span data-ttu-id="f7717-157">ExpressionTranslator는 수정 명령 트리의 속성이 제한된 식 형식의 변환만 지원하며 특정 제약 조건을 염두에 두고 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-157">It supports translation of only the expression types to which the properties of the modification command tree are constrained and is built with the particular constraints in mind.</span></span>  
  
 <span data-ttu-id="f7717-158">아래에서는 특정 식 형식의 방문에 대해 설명합니다(사소한 변환이 포함된 노드는 생략됨).</span><span class="sxs-lookup"><span data-stu-id="f7717-158">The following information discusses visiting specific expression types (nodes with trivial translations are omitted).</span></span>  
  
### <a name="dbcomparisonexpression"></a><span data-ttu-id="f7717-159">DbComparisonExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-159">DbComparisonExpression</span></span>  
 <span data-ttu-id="f7717-160">ExpressionTranslator가 preserveMemberValues = true를 사용하여 생성된 경우 오른쪽 상수가 DbNullExpression이 아니라 DbConstantExpression이면 왼쪽 피연산자(DbPropertyExpressions)를 해당 DbConstantExpression과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-160">When the ExpressionTranslator is constructed with preserveMemberValues = true, and when the constant to the right is a DbConstantExpression (instead of DbNullExpression), it associates the left operand (a DbPropertyExpressions) with that DbConstantExpression.</span></span> <span data-ttu-id="f7717-161">이는 영향을 받는 행을 식별하기 위해 반환 SELECT 문이 생성되어야 하는 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-161">That is used if a return Select statement needs to be generated to identify the affected row.</span></span>  
  
### <a name="dbconstantexpression"></a><span data-ttu-id="f7717-162">DbConstantExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-162">DbConstantExpression</span></span>  
 <span data-ttu-id="f7717-163">방문된 각 상수에 대해 매개 변수가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-163">For each visited constant a parameter is created.</span></span>  
  
### <a name="dbpropertyexpression"></a><span data-ttu-id="f7717-164">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="f7717-164">DbPropertyExpression</span></span>  
 <span data-ttu-id="f7717-165">DbPropertyExpression의 인스턴스가 항상 입력 테이블을 나타내는 경우 생성에서 별칭을 만들지 않았으면(테이블 변수가 사용되는 업데이트 시나리오에서만 별칭이 발생함) 입력에 대해 별칭을 지정할 필요가 없습니다. 변환에서는 기본적으로 속성 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-165">Given that the Instance of the DbPropertyExpression always represents the input table, unless the generation has created an alias (which only happens in update scenarios when a table variable is used), no alias needs to be specified for the input; the translation defaults to the property name.</span></span>  
  
## <a name="generating-an-insert-sql-command"></a><span data-ttu-id="f7717-166">INSERT SQL 명령 생성</span><span class="sxs-lookup"><span data-stu-id="f7717-166">Generating an Insert SQL Command</span></span>  
 <span data-ttu-id="f7717-167">샘플 공급자에서 지정된 DbInsertCommandTree의 경우 생성된 INSERT 명령은 아래의 두 삽입 템플릿 중 하나를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-167">For a given DbInsertCommandTree in the sample provider, the generated insert command follows one of the two insert templates below.</span></span>  
  
 <span data-ttu-id="f7717-168">첫 번째 템플릿에는 SetClauses 목록의 값에 따라 삽입을 수행하는 명령과 Returning 속성이 null이 아닌 경우 삽입된 행의 Returning 속성에 지정된 속성을 반환하는 SELECT 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-168">The first template has a command to perform the insert given the values in the list of SetClauses, and a SELECT statement to return the properties specified in the Returning property for the inserted row if the Returning property was not null.</span></span> <span data-ttu-id="f7717-169">조건자 요소 "@@ROWCOUNT > 0" 행이 삽입 되 면 true입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-169">The predicate element "@@ROWCOUNT > 0" is true if a row was inserted.</span></span> <span data-ttu-id="f7717-170">조건자 요소 "keyMemberI = keyValueI &#124; scope_identity () "는" keyMemberI = scope_identity () "scope_identity () id (저장소 생성) 열에 삽입 된 마지막 id 값을 반환 하기 때문에 keyMemeberI이 저장소 생성 키를 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-170">The predicate element "keyMemberI =  keyValueI &#124; scope_identity()" takes the shape  "keyMemberI =  scope_identity()" only if keyMemeberI is a store-generated key, because scope_identity() returns the last identity value inserted into an identity (store-generated) column.</span></span>  
  
```  
-- first insert Template  
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]    
VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES   
  
[SELECT <returning>   
 FROM <target>  
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]  
```  
  
 <span data-ttu-id="f7717-171">두 번째 템플릿은 기본 키가 저장소 생성 키이지만 정수 형식이 아니라서 scope_identity()와 함께 사용할 수 없는 행의 삽입을 지정하는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-171">The second template is needed if the insert specifies inserting a row where the primary key is store-generated but is not an integer type and therefore can't be used with scope_identity()).</span></span> <span data-ttu-id="f7717-172">또한 복합 저장소 생성 키가 있는 경우에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-172">It is also used if there is a compound store-generated key.</span></span>  
  
```  
-- second insert template  
DECLARE @generated_keys TABLE [(keyMember0, … keyMemberN)  
  
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]    
 OUTPUT inserted.KeyMember0, …, inserted.KeyMemberN INTO @generated_keys  
 VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES  
  
[SELECT <returning_over_t>   
 FROM @generated_keys  AS g  
JOIN <target> AS t ON g.KeyMember0 = t.KeyMember0 AND … g.KeyMemberN = t.KeyMemberN  
 WHERE @@ROWCOUNT > 0  
```  
  
 <span data-ttu-id="f7717-173">다음은 샘플 공급자에 포함된 모델을 사용하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-173">The following is an example that uses the model that is included with the sample provider.</span></span> <span data-ttu-id="f7717-174">이 예제에서는 DbInsertCommandTree에서 삽입 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-174">It generates an insert command from a DbInsertCommandTree.</span></span>  
  
 <span data-ttu-id="f7717-175">다음 코드에서는 Category를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-175">The following code inserts a Category:</span></span>  
  
```  
using (NorthwindEntities northwindContext = new NorthwindEntities()) {  
   Category c = new Category();  
   c.CategoryName = "Test Category";  
   c.Description = "A new category for testing";  
   northwindContext.AddObject("Categories", c);  
   northwindContext.SaveChanges();  
}  
```  
  
 <span data-ttu-id="f7717-176">이 코드에서는 공급자에 전달되는 다음 명령 트리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-176">This code produces the following command tree, which is passed to the provider:</span></span>  
  
```  
DbInsertCommandTree  
|_Parameters  
|_Target : 'target'  
| |_Scan : dbo.Categories  
|_SetClauses  
| |_DbSetClause  
| | |_Property  
| | | |_Var(target).CategoryName  
| | |_Value  
| |   |_'Test Category'  
| |_DbSetClause  
| | |_Property  
| | | |_Var(target).Description  
| | |_Value  
| |   |_'A new category for testing'  
| |_DbSetClause  
|   |_Property  
|   | |_Var(target).Picture  
|   |_Value  
|     |_null  
|_Returning  
  |_NewInstance : Record['CategoryID'=Edm.Int32]  
    |_Column : 'CategoryID'  
      |_Var(target).CategoryID  
```  
  
 <span data-ttu-id="f7717-177">샘플 공급자가 생성하는 저장소 명령은 다음 SQL 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-177">The store command that the sample provider produces is the following SQL statement:</span></span>  
  
```  
insert [dbo].[Categories]([CategoryName], [Description], [Picture])  
values (@p0, @p1, null)  
select [CategoryID]  
from [dbo].[Categories]  
where @@ROWCOUNT > 0 and [CategoryID] = scope_identity()  
```  
  
## <a name="generating-an-update-sql-command"></a><span data-ttu-id="f7717-178">UPDATE SQL 명령 생성</span><span class="sxs-lookup"><span data-stu-id="f7717-178">Generating an Update SQL Command</span></span>  
 <span data-ttu-id="f7717-179">지정된 DbUpdateCommandTree의 경우 생성된 UPDATE 명령은 다음 템플릿을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-179">For a given DbUpdateCommandTree, the generated update command is based on the following template:</span></span>  
  
```  
-- UPDATE Template   
UPDATE <target>   
SET setClauseProprerty0 = setClauseValue0,  .. setClauseProprertyN = setClauseValueN  | @i = 0  
WHERE <predicate>  
  
[SELECT <returning>   
 FROM <target>  
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]  
```  
  
 <span data-ttu-id="f7717-180">Set 절에 모조 set 절 ("@i = 0") 없는 set 절이 지정 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-180">The set clause has the fake set clause ("@i = 0") only if no set clauses are specified.</span></span> <span data-ttu-id="f7717-181">이는 모든 저장소 계산 열이 다시 계산되도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-181">This is to ensure that any store-computed columns are recomputed.</span></span>  
  
 <span data-ttu-id="f7717-182">Returning 속성이 null이 아닌 경우에만 Returning 속성에 지정된 속성을 반환하기 위해 SELECT 문이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-182">Only if the Returning property is not null, a select statement is generated to return the properties specified in the Returning property.</span></span>  
  
 <span data-ttu-id="f7717-183">다음 예제에서는 샘플 공급자와 함께 포함된 모델을 사용하여 UPDATE 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-183">The following example uses the model that is included with the sample provider to generate an update command.</span></span>  
  
 <span data-ttu-id="f7717-184">다음 사용자 코드에서는 Category를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-184">The following user code updates a Category:</span></span>  
  
```  
using (NorthwindEntities northwindContext = new NorthwindEntities()) {  
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "Test Category").First();  
   c.CategoryName = "New test name";  
   northwindContext.SaveChanges();  
}  
```  
  
 <span data-ttu-id="f7717-185">이 사용자 코드에서는 공급자에 전달되는 다음 명령 트리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-185">This user code produces the following command tree, which is passed to the provider:</span></span>  
  
```  
DbUpdateCommandTree  
|_Parameters  
|_Target : 'target'  
| |_Scan : dbo.Categories  
|_SetClauses  
| |_DbSetClause  
|   |_Property  
|   | |_Var(target).CategoryName  
|   |_Value  
|     |_'New test name'  
|_Predicate  
| |_  
|   |_Var(target).CategoryID  
|   |_=  
|   |_10  
|_Returning   
```  
  
 <span data-ttu-id="f7717-186">샘플 공급자는 다음과 같은 저장소 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-186">The sample provider produces the following store command:</span></span>  
  
```  
update [dbo].[Categories]  
set [CategoryName] = @p0  
where ([CategoryID] = @p1)   
```  
  
### <a name="generating-a-delete-sql-command"></a><span data-ttu-id="f7717-187">DELETE SQL 명령 생성</span><span class="sxs-lookup"><span data-stu-id="f7717-187">Generating a Delete SQL Command</span></span>  
 <span data-ttu-id="f7717-188">지정된 DbDeleteCommandTree의 경우 생성된 DELETE 명령은 다음 템플릿을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-188">For a given DbDeleteCommandTree, the generated DELETE command is based on the following template:</span></span>  
  
```  
-- DELETE Template   
DELETE <target>   
WHERE <predicate>  
```  
  
 <span data-ttu-id="f7717-189">다음 예제에서는 샘플 공급자와 함께 포함된 모델을 사용하여 DELETE 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-189">The following example uses the model that is included with the sample provider to generate a delete command.</span></span>  
  
 <span data-ttu-id="f7717-190">다음 사용자 코드에서는 Category를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-190">The following user code deletes a Category:</span></span>  
  
```  
using (NorthwindEntities northwindContext = new NorthwindEntities()) {  
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "New test name").First();  
   northwindContext.DeleteObject(c);  
   northwindContext.SaveChanges();  
}  
```  
  
 <span data-ttu-id="f7717-191">이 사용자 코드에서는 공급자에 전달되는 다음 명령 트리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-191">This user code produces the following command tree, which is passed to the provider.</span></span>  
  
```  
DbDeleteCommandTree  
|_Parameters  
|_Target : 'target'  
| |_Scan : dbo.Categories  
|_Predicate  
  |_  
    |_Var(target).CategoryID  
    |_=  
    |_10  
```  
  
 <span data-ttu-id="f7717-192">샘플 공급자는 다음과 같은 저장소 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7717-192">The following store command is produced by the sample provider:</span></span>  
  
```  
delete [dbo].[Categories]  
where ([CategoryID] = @p0)  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7717-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7717-193">See Also</span></span>  
 [<span data-ttu-id="f7717-194">Entity Framework 데이터 공급자 작성</span><span class="sxs-lookup"><span data-stu-id="f7717-194">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
