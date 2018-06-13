---
title: 질문과 대답
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 5f556c46823bd867709e8c53b59f7ac53201d242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365490"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="03da7-102">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="03da7-102">Frequently Asked Questions</span></span>
<span data-ttu-id="03da7-103">다음 단원에서는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]를 구현할 때 발생할 수 있는 일반적인 문제에 대한 해결 방법을 제시합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-103">The following sections answer some common issues that you might encounter when you implement [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="03da7-104">추가 문제를 해결 [문제 해결](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-104">Additional issues are addressed in [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).</span></span>  
  
## <a name="cannot-connect"></a><span data-ttu-id="03da7-105">연결할 수 없음</span><span class="sxs-lookup"><span data-stu-id="03da7-105">Cannot Connect</span></span>  
 <span data-ttu-id="03da7-106">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-106">Q.</span></span> <span data-ttu-id="03da7-107">데이터베이스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-107">I cannot connect to my database.</span></span>  
  
 <span data-ttu-id="03da7-108">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-108">A.</span></span> <span data-ttu-id="03da7-109">연결 문자열이 올바르고 SQL Server 인스턴스가 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-109">Make sure your connection string is correct and that your SQL Server instance is running.</span></span> <span data-ttu-id="03da7-110">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하려면 명명된 파이프 프로토콜도 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-110">Note also that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requires the Named Pipes protocol to be enabled.</span></span> <span data-ttu-id="03da7-111">자세한 내용은 참조 [연습으로 학습](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-111">For more information, see [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
## <a name="changes-to-database-lost"></a><span data-ttu-id="03da7-112">데이터베이스 변경 내용 손실</span><span class="sxs-lookup"><span data-stu-id="03da7-112">Changes to Database Lost</span></span>  
 <span data-ttu-id="03da7-113">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-113">Q.</span></span> <span data-ttu-id="03da7-114">데이터베이스의 데이터를 변경했는데 응용 프로그램을 다시 실행했더니 변경 내용이 없어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-114">I made a change to data in the database, but when I reran my application, the change was no longer there.</span></span>  
  
 <span data-ttu-id="03da7-115">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-115">A.</span></span> <span data-ttu-id="03da7-116"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하여 결과를 데이터베이스에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-116">Make sure that you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> to save results to the database.</span></span>  
  
## <a name="database-connection-open-how-long"></a><span data-ttu-id="03da7-117">데이터베이스 연결: 연결 시간</span><span class="sxs-lookup"><span data-stu-id="03da7-117">Database Connection: Open How Long?</span></span>  
 <span data-ttu-id="03da7-118">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-118">Q.</span></span> <span data-ttu-id="03da7-119">데이터베이스는 얼마 동안 연결된 상태로 유지됩니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-119">How long does my database connection remain open?</span></span>  
  
 <span data-ttu-id="03da7-120">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-120">A.</span></span> <span data-ttu-id="03da7-121">일반적으로 연결은 쿼리 결과를 사용할 때까지 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-121">A connection typically remains open until you consume the query results.</span></span> <span data-ttu-id="03da7-122">모든 결과를 처리하는 데 시간이 많이 걸릴 것으로 예상되고 결과를 캐시해도 상관 없다면 쿼리에 <xref:System.Linq.Enumerable.ToList%2A>를 적용하세요.</span><span class="sxs-lookup"><span data-stu-id="03da7-122">If you expect to take time to process all the results and are not opposed to caching the results, apply <xref:System.Linq.Enumerable.ToList%2A> to the query.</span></span> <span data-ttu-id="03da7-123">각 개체를 한 번만 처리하는 일반적인 시나리오에서는 `DataReader` 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 모두에서 스트리밍 모델을 사용하는 것이 더 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-123">In common scenarios where each object is processed only one time, the streaming model is superior in both `DataReader` and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="03da7-124">세부적인 연결 사용은 다음에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-124">The exact details of connection usage depend on the following:</span></span>  
  
-   <span data-ttu-id="03da7-125">연결 개체를 사용하여 <xref:System.Data.Linq.DataContext>를 만든 경우의 연결 상태</span><span class="sxs-lookup"><span data-stu-id="03da7-125">Connection status if the <xref:System.Data.Linq.DataContext> is constructed with a connection object.</span></span>  
  
-   <span data-ttu-id="03da7-126">연결 문자열 설정(예: MARS(Multiple Active Result Sets) 사용).</span><span class="sxs-lookup"><span data-stu-id="03da7-126">Connection string settings (for example, enabling Multiple Active Result Sets (MARS).</span></span> <span data-ttu-id="03da7-127">자세한 내용은 [MARS(여러 활성 결과 집합)](../../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03da7-127">For more information, see [Multiple Active Result Sets (MARS)](../../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md).</span></span>  
  
## <a name="updating-without-querying"></a><span data-ttu-id="03da7-128">쿼리하지 않고 업데이트</span><span class="sxs-lookup"><span data-stu-id="03da7-128">Updating Without Querying</span></span>  
 <span data-ttu-id="03da7-129">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-129">Q.</span></span> <span data-ttu-id="03da7-130">데이터베이스를 먼저 쿼리하지 않고 테이블 데이터를 업데이트할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-130">Can I update table data without first querying the database?</span></span>  
  
 <span data-ttu-id="03da7-131">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-131">A.</span></span> <span data-ttu-id="03da7-132">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에는 설정 기반의 업데이트 명령이 없지만 다음 기술 중 하나를 사용하여 쿼리 없이 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-132">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not have set-based update commands, you can use either of the following techniques to update without first querying:</span></span>  
  
-   <span data-ttu-id="03da7-133"><xref:System.Data.Linq.DataContext.ExecuteCommand%2A>를 사용하여 SQL 코드를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-133">Use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to send SQL code.</span></span>  
  
-   <span data-ttu-id="03da7-134">개체의 새 인스턴스를 만든 후 업데이트에 영향을 주는 현재 값(필드)을 모두 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-134">Create a new instance of the object and initialize all the current values (fields) that affect the update.</span></span> <span data-ttu-id="03da7-135">그런 다음 <xref:System.Data.Linq.DataContext>를 사용하여 개체를 <xref:System.Data.Linq.Table%601.Attach%2A>에 연결하고 변경할 필드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-135">Then attach the object to the <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.Table%601.Attach%2A> and modify the field you want to change.</span></span>  
  
## <a name="unexpected-query-results"></a><span data-ttu-id="03da7-136">예기치 않은 쿼리 결과</span><span class="sxs-lookup"><span data-stu-id="03da7-136">Unexpected Query Results</span></span>  
 <span data-ttu-id="03da7-137">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-137">Q.</span></span> <span data-ttu-id="03da7-138">쿼리가 예기치 않은 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-138">My query is returning unexpected results.</span></span> <span data-ttu-id="03da7-139">무슨 문제가 있는지 어떻게 확인합니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-139">How can I inspect what is occurring?</span></span>  
  
 <span data-ttu-id="03da7-140">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-140">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="03da7-141">에는 생성된 SQL 코드를 검사할 수 있는 도구가 여러 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-141"> provides several tools for inspecting the SQL code it generates.</span></span> <span data-ttu-id="03da7-142">그 중에서도 <xref:System.Data.Linq.DataContext.Log%2A>가 가장 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-142">One of the most important is <xref:System.Data.Linq.DataContext.Log%2A>.</span></span> <span data-ttu-id="03da7-143">자세한 내용은 참조 [디버깅 지원](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-143">For more information, see [Debugging Support](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).</span></span>  
  
## <a name="unexpected-stored-procedure-results"></a><span data-ttu-id="03da7-144">예기치 않은 저장 프로시저 결과</span><span class="sxs-lookup"><span data-stu-id="03da7-144">Unexpected Stored Procedure Results</span></span>  
 <span data-ttu-id="03da7-145">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-145">Q.</span></span> <span data-ttu-id="03da7-146">`MAX()`를 사용하여 반환 값을 계산하는 저장 프로시저를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-146">I have a stored procedure whose return value is calculated by `MAX()`.</span></span> <span data-ttu-id="03da7-147">저장 프로시저를 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 화면으로 끌어 오면 반환 값이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-147">When I drag the stored procedure to the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] surface, the return value is not correct.</span></span>  
  
 <span data-ttu-id="03da7-148">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-148">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="03da7-149">에서는 다음과 같은 두 가지 방법으로 데이터베이스에서 생성된 값을 저장 프로시저를 통해 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-149"> provides two ways to return database-generated values by way of stored procedures:</span></span>  
  
-   <span data-ttu-id="03da7-150">출력 결과에 이름을 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="03da7-150">By naming the output result.</span></span>  
  
-   <span data-ttu-id="03da7-151">출력 매개 변수를 명시적으로 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="03da7-151">By explicitly specifying an output parameter.</span></span>  
  
 <span data-ttu-id="03da7-152">다음은 잘못된 출력의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-152">The following is an example of incorrect output.</span></span> <span data-ttu-id="03da7-153">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 결과를 매핑할 수 없기 때문에 항상 0을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-153">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot map the results, it always returns 0:</span></span>  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select max(i) from t where name like 'hello'`  
  
 `end`  
  
 <span data-ttu-id="03da7-154">다음은 출력 매개 변수를 사용하여 얻은 올바른 출력의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-154">The following is an example of correct output by using an output parameter:</span></span>  
  
 `create procedure proc2`  
  
 `@result int OUTPUT`  
  
 `as`  
  
 `select @result = MAX(i) from t where name like 'hello'`  
  
 `go`  
  
 <span data-ttu-id="03da7-155">다음은 출력 결과에 이름을 지정하여 얻은 올바른 출력의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-155">The following is an example of correct output by naming the output result:</span></span>  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select nax(i) AS MaxResult from t where name like 'hello'`  
  
 `end`  
  
 <span data-ttu-id="03da7-156">자세한 내용은 참조 [사용자 지정 작업에서 사용 하 여 저장 프로시저](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-156">For more information, see [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md).</span></span>  
  
## <a name="serialization-errors"></a><span data-ttu-id="03da7-157">Serialization 오류</span><span class="sxs-lookup"><span data-stu-id="03da7-157">Serialization Errors</span></span>  
 <span data-ttu-id="03da7-158">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-158">Q.</span></span> <span data-ttu-id="03da7-159">다음 오류를 serialize 하려고 할 때 습: "입력 'standardchangetracker... serializable로 표시 되어 있지 않습니다."</span><span class="sxs-lookup"><span data-stu-id="03da7-159">When I try to serialize, I get the following error: "Type 'System.Data.Linq.ChangeTracker+StandardChangeTracker' ... is not marked as serializable."</span></span>  
  
 <span data-ttu-id="03da7-160">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-160">A.</span></span> <span data-ttu-id="03da7-161">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 코드 생성은 <xref:System.Runtime.Serialization.DataContractSerializer> serialization을 지원하지만</span><span class="sxs-lookup"><span data-stu-id="03da7-161">Code generation in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports <xref:System.Runtime.Serialization.DataContractSerializer> serialization.</span></span> <span data-ttu-id="03da7-162"><xref:System.Xml.Serialization.XmlSerializer> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-162">It does not support <xref:System.Xml.Serialization.XmlSerializer> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="03da7-163">자세한 내용은 [Serialization](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03da7-163">For more information, see [Serialization](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md).</span></span>  
  
## <a name="multiple-dbml-files"></a><span data-ttu-id="03da7-164">여러 DBML 파일</span><span class="sxs-lookup"><span data-stu-id="03da7-164">Multiple DBML Files</span></span>  
 <span data-ttu-id="03da7-165">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-165">Q.</span></span> <span data-ttu-id="03da7-166">여러 DBML 파일에서 일부 테이블을 공유할 경우 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-166">When I have multiple DBML files that share some tables in common, I get a compiler error.</span></span>  
  
 <span data-ttu-id="03da7-167">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-167">A.</span></span> <span data-ttu-id="03da7-168">설정의 **컨텍스트 Namespace** 및 **엔터티 Namespace** 속성에서는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 각 DBML 파일에 대 한 고유 값입니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-168">Set the **Context Namespace** and **Entity Namespace** properties from the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to a distinct value for each DBML file.</span></span> <span data-ttu-id="03da7-169">이렇게 하면 이름/네임스페이스 충돌이 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-169">This approach eliminates the name/namespace collision.</span></span>  
  
## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a><span data-ttu-id="03da7-170">삽입 또는 업데이트 시 데이터베이스에서 생성된 값을 명시적으로 설정해야 하는 문제 방지</span><span class="sxs-lookup"><span data-stu-id="03da7-170">Avoiding Explicit Setting of Database-Generated Values on Insert or Update</span></span>  
 <span data-ttu-id="03da7-171">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-171">Q.</span></span> <span data-ttu-id="03da7-172">데이터베이스 테이블에 SQL `DateCreated`를 기본값으로 사용하는 `Getdate()` 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-172">I have a database table with a `DateCreated` column that defaults to SQL `Getdate()`.</span></span> <span data-ttu-id="03da7-173">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하여 새 레코드를 삽입하려고 하면 값이 `NULL`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-173">When I try to insert a new record by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the value gets set to `NULL`.</span></span> <span data-ttu-id="03da7-174">데이터베이스의 기본값이 설정되어야 하지 않나요?</span><span class="sxs-lookup"><span data-stu-id="03da7-174">I would expect it to be set to the database default.</span></span>  
  
 <span data-ttu-id="03da7-175">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-175">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="03da7-176">은 ID(자동 증분)와 rowguidcol(데이터베이스에서 생성된 GUID) 및 타임스탬프 열에 대해서만 이와 같이 기본값을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-176"> handles this situation automatically for identity (auto-increment) and rowguidcol (database-generated GUID) and timestamp columns.</span></span> <span data-ttu-id="03da7-177">다른 경우에 직접 설정 해야 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> = `true` 및 <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> = <xref:System.Data.Linq.Mapping.AutoSync.Always> / <xref:System.Data.Linq.Mapping.AutoSync.OnInsert> / <xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-177">In other cases, you should manually set <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` and <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> properties.</span></span>  
  
## <a name="multiple-dataloadoptions"></a><span data-ttu-id="03da7-178">여러 DataLoadOptions</span><span class="sxs-lookup"><span data-stu-id="03da7-178">Multiple DataLoadOptions</span></span>  
 <span data-ttu-id="03da7-179">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-179">Q.</span></span> <span data-ttu-id="03da7-180">첫 번째 로드 옵션을 덮어쓰지 않고 다른 로드 옵션을 지정할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-180">Can I specify additional load options without overwriting the first?</span></span>  
  
 <span data-ttu-id="03da7-181">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-181">A.</span></span> <span data-ttu-id="03da7-182">예.</span><span class="sxs-lookup"><span data-stu-id="03da7-182">Yes.</span></span> <span data-ttu-id="03da7-183">다음 예제에서처럼 첫 번째 로드 옵션을 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-183">The first is not overwritten, as in the following example:</span></span>  
  
```vb  
Dim dlo As New DataLoadOptions()  
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)  
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)  
```  
  
```csharp  
DataLoadOptions dlo = new DataLoadOptions();  
dlo.LoadWith<Order>(o => o.Customer);  
dlo.LoadWith<Order>(o => o.OrderDetails);  
```  
  
## <a name="errors-using-sql-compact-35"></a><span data-ttu-id="03da7-184">SQL Compact 3.5 사용 오류</span><span class="sxs-lookup"><span data-stu-id="03da7-184">Errors Using SQL Compact 3.5</span></span>  
 <span data-ttu-id="03da7-185">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-185">Q.</span></span> <span data-ttu-id="03da7-186">[!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] 데이터베이스에서 테이블을 끌어 오면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-186">I get an error when I drag tables out of a [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] database.</span></span>  
  
 <span data-ttu-id="03da7-187">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-187">A.</span></span> <span data-ttu-id="03da7-188">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서는 [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] 런타임과 달리 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-188">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)], although the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime does.</span></span> <span data-ttu-id="03da7-189">이 경우에는 고유 엔터티 클래스를 만들어 적절한 특성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-189">In this situation, you must create your own entity classes and add the appropriate attributes.</span></span>  
  
## <a name="errors-in-inheritance-relationships"></a><span data-ttu-id="03da7-190">상속 관계 오류</span><span class="sxs-lookup"><span data-stu-id="03da7-190">Errors in Inheritance Relationships</span></span>  
 <span data-ttu-id="03da7-191">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-191">Q.</span></span> <span data-ttu-id="03da7-192">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서 도구 상자의 상속 모양을 사용하여 두 엔터티를 연결했는데 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-192">I used the toolbox inheritance shape in the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to connect two entities, but I get errors.</span></span>  
  
 <span data-ttu-id="03da7-193">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-193">A.</span></span> <span data-ttu-id="03da7-194">관계를 만드는 것만으로는 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-194">Creating the relationship is not enough.</span></span> <span data-ttu-id="03da7-195">판별자 열, 기본 클래스 판별자 값 및 파생 클래스 판별자 값 등의 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-195">You must provide information such as the discriminator column, base class discriminator value, and derived class discriminator value.</span></span>  
  
## <a name="provider-model"></a><span data-ttu-id="03da7-196">공급자 모델</span><span class="sxs-lookup"><span data-stu-id="03da7-196">Provider Model</span></span>  
 <span data-ttu-id="03da7-197">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-197">Q.</span></span> <span data-ttu-id="03da7-198">사용할 수 있는 공용 공급자 모델이 있습니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-198">Is a public provider model available?</span></span>  
  
 <span data-ttu-id="03da7-199">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-199">A.</span></span> <span data-ttu-id="03da7-200">아니요, 사용할 수 있는 공용 공급자 모델은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-200">No public provider model is available.</span></span> <span data-ttu-id="03da7-201">이때 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] SQL Server 지원 및 [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] 만 합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-201">At this time, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports SQL Server and [!INCLUDE[ssEW](../../../../../../includes/ssew-md.md)] only.</span></span>  
  
## <a name="sql-injection-attacks"></a><span data-ttu-id="03da7-202">SQL 삽입 공격</span><span class="sxs-lookup"><span data-stu-id="03da7-202">SQL-Injection Attacks</span></span>  
 <span data-ttu-id="03da7-203">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-203">Q.</span></span> <span data-ttu-id="03da7-204">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 SQL 삽입 공격으로부터 어떻게 보호됩니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-204">How is [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] protected from SQL-injection attacks?</span></span>  
  
 <span data-ttu-id="03da7-205">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-205">A.</span></span> <span data-ttu-id="03da7-206">사용자 입력을 연결하여 만든 기존 SQL 쿼리의 경우에는 SQL 삽입 공격이 상당히 큰 위협 요소였습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-206">SQL injection has been a significant risk for traditional SQL queries formed by concatenating user input.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="03da7-207">에서는 쿼리에 <xref:System.Data.SqlClient.SqlParameter>를 사용하여 이러한 삽입 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-207"> avoids such injection by using <xref:System.Data.SqlClient.SqlParameter> in queries.</span></span> <span data-ttu-id="03da7-208">즉, 사용자 입력은 매개 변수 값으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-208">User input is turned into parameter values.</span></span> <span data-ttu-id="03da7-209">이 방법을 사용하면 사용자 입력을 통해 악의적인 명령이 사용되는 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-209">This approach prevents malicious commands from being used from customer input.</span></span>  
  
## <a name="changing-read-only-flag-in-dbml-files"></a><span data-ttu-id="03da7-210">DBML 파일에서 읽기 전용 플래그 변경</span><span class="sxs-lookup"><span data-stu-id="03da7-210">Changing Read-only Flag in DBML Files</span></span>  
 <span data-ttu-id="03da7-211">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-211">Q.</span></span> <span data-ttu-id="03da7-212">DBML 파일에서 개체 모델을 만들 때 일부 속성의 setter를 어떻게 제거합니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-212">How do I eliminate setters from some properties when I create an object model from a DBML file?</span></span>  
  
 <span data-ttu-id="03da7-213">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-213">A.</span></span> <span data-ttu-id="03da7-214">이와 같은 고급 시나리오에서는 다음과 같은 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="03da7-214">Take the following steps for this advanced scenario:</span></span>  
  
1.  <span data-ttu-id="03da7-215">.dbml 파일에서 <xref:System.Data.Linq.ITable.IsReadOnly%2A> 플래그를 `True`로 변경하여 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-215">In the .dbml file, modify the property by changing the <xref:System.Data.Linq.ITable.IsReadOnly%2A> flag to `True`.</span></span>  
  
2.  <span data-ttu-id="03da7-216">부분 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-216">Add a partial class.</span></span> <span data-ttu-id="03da7-217">읽기 전용 멤버에 대해 매개 변수가 있는 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-217">Create a constructor with parameters for the read-only members.</span></span>  
  
3.  <span data-ttu-id="03da7-218">기본 <xref:System.Data.Linq.Mapping.UpdateCheck> 값(<xref:System.Data.Linq.Mapping.UpdateCheck.Never>)을 검토하여 응용 프로그램에 사용할 수 있는 올바른 값인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-218">Review the default <xref:System.Data.Linq.Mapping.UpdateCheck> value (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) to determine whether that is the correct value for your application.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="03da7-219">사용 하는 경우는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Visual Studio에서 변경 내용을 덮어쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-219">If you are using the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] in Visual Studio, your changes might be overwritten.</span></span>  
  
## <a name="aptca"></a><span data-ttu-id="03da7-220">APTCA</span><span class="sxs-lookup"><span data-stu-id="03da7-220">APTCA</span></span>  
 <span data-ttu-id="03da7-221">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-221">Q.</span></span> <span data-ttu-id="03da7-222">부분적으로 신뢰할 수 있는 코드에서 System.Data.Linq를 사용할 수 있습니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-222">Is System.Data.Linq marked for use by partially trusted code?</span></span>  
  
 <span data-ttu-id="03da7-223">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-223">A.</span></span> <span data-ttu-id="03da7-224">예, System.Data.Linq.dll 어셈블리도 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 특성이 표시된 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 어셈블리 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-224">Yes, the System.Data.Linq.dll assembly is among those [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="03da7-225">[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]에서 이 특성이 표시되지 않은 어셈블리는 완전히 신뢰할 수 있는 코드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-225">Without this marking, assemblies in the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] are intended for use only by fully trusted code.</span></span>  
  
 <span data-ttu-id="03da7-226">주 시나리오에는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 호출자는가 수 있도록 신뢰할 수 있는 부분적으로 허용에 대해는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 어셈블리에 웹 응용 프로그램에서 액세스할 수 있는 *신뢰* 구성은 보통 합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-226">The principal scenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] for allowing partially trusted callers is to enable the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly to be accessed from Web applications, where the *trust* configuration is Medium.</span></span>  
  
## <a name="mapping-data-from-multiple-tables"></a><span data-ttu-id="03da7-227">여러 테이블의 데이터 매핑</span><span class="sxs-lookup"><span data-stu-id="03da7-227">Mapping Data from Multiple Tables</span></span>  
 <span data-ttu-id="03da7-228">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-228">Q.</span></span> <span data-ttu-id="03da7-229">사용하는 엔터티의 데이터를 여러 테이블에서 가져오는데</span><span class="sxs-lookup"><span data-stu-id="03da7-229">The data in my entity comes from multiple tables.</span></span> <span data-ttu-id="03da7-230">이러한 데이터를 어떻게 매핑합니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-230">How do I map it?</span></span>  
  
 <span data-ttu-id="03da7-231">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-231">A.</span></span> <span data-ttu-id="03da7-232">데이터베이스에 뷰를 만들어 엔터티를 해당 뷰에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-232">You can create a view in a database and map the entity to the view.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="03da7-233">에서는 테이블과 마찬가지로 뷰에 대해서도 동일한 SQL을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-233"> generates the same SQL for views as it does for tables.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03da7-234">그러나 이 시나리오에서는 뷰 사용이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-234">The use of views in this scenario has limitations.</span></span> <span data-ttu-id="03da7-235">이 방법은 기본 뷰에서 <xref:System.Data.Linq.Table%601>에 대해 수행되는 작업을 지원하는 경우에 가장 안전하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-235">This approach works most safely when the operations performed on <xref:System.Data.Linq.Table%601> are supported by the underlying view.</span></span> <span data-ttu-id="03da7-236">수행하려는 작업은 사용자 자신만이 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-236">Only you know which operations are intended.</span></span> <span data-ttu-id="03da7-237">예를 들어 대부분의 응용 프로그램은 읽기 전용 및 다른 많은 수 수행 `Create` / `Update` / `Delete` 작업을 사용 하 여 뷰에 대해 저장 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-237">For example, most applications are read-only, and another sizeable number perform `Create`/`Update`/`Delete` operations only by using stored procedures against views.</span></span>  
  
## <a name="connection-pooling"></a><span data-ttu-id="03da7-238">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="03da7-238">Connection Pooling</span></span>  
 <span data-ttu-id="03da7-239">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-239">Q.</span></span> <span data-ttu-id="03da7-240"><xref:System.Data.Linq.DataContext> 풀링에 도움이 되는 생성자가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="03da7-240">Is there a construct that can help with <xref:System.Data.Linq.DataContext> pooling?</span></span>  
  
 <span data-ttu-id="03da7-241">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-241">A.</span></span> <span data-ttu-id="03da7-242"><xref:System.Data.Linq.DataContext>의 인스턴스는 다시 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="03da7-242">Do not try to reuse instances of <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="03da7-243">각 <xref:System.Data.Linq.DataContext>는 하나의 특정 편집/쿼리 세션에 대한 상태(ID 캐시 포함)를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-243">Each <xref:System.Data.Linq.DataContext> maintains state (including an identity cache) for one particular edit/query session.</span></span> <span data-ttu-id="03da7-244">데이터베이스의 현재 상태를 기반으로 새 인스턴스를 사용하려면 새 <xref:System.Data.Linq.DataContext>를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="03da7-244">To obtain new instances based on the current state of the database, use a new <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="03da7-245">기본 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 연결 풀링은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-245">You can still use underlying [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] connection pooling.</span></span> <span data-ttu-id="03da7-246">자세한 내용은 [SQL Server 연결 풀링(ADO.NET)](../../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03da7-246">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
## <a name="second-datacontext-is-not-updated"></a><span data-ttu-id="03da7-247">두 번째 DataContext가 업데이트되지 않음</span><span class="sxs-lookup"><span data-stu-id="03da7-247">Second DataContext Is Not Updated</span></span>  
 <span data-ttu-id="03da7-248">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-248">Q.</span></span> <span data-ttu-id="03da7-249"><xref:System.Data.Linq.DataContext>의 인스턴스 하나를 사용하여 데이터베이스에 값을 저장했습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-249">I used one instance of <xref:System.Data.Linq.DataContext> to store values in the database.</span></span> <span data-ttu-id="03da7-250">그런데 동일한 데이터베이스에 대한 두 번째 <xref:System.Data.Linq.DataContext>에 업데이트된 값이 반영되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-250">However, a second <xref:System.Data.Linq.DataContext> on the same database does not reflect the updated values.</span></span> <span data-ttu-id="03da7-251">두 번째 <xref:System.Data.Linq.DataContext> 인스턴스가 캐시된 값을 반환하는 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-251">The second <xref:System.Data.Linq.DataContext> instance seems to return cached values.</span></span>  
  
 <span data-ttu-id="03da7-252">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-252">A.</span></span> <span data-ttu-id="03da7-253">이 동작은 설계 시 의도된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-253">This behavior is by design.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="03da7-254">은 첫 번째 인스턴스와 동일한 인스턴스/값을 계속해서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-254"> continues to return the same instances/values that you saw in the first instance.</span></span> <span data-ttu-id="03da7-255">데이터를 업데이트할 경우에는 낙관적 동시성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-255">When you make updates, you use optimistic concurrency.</span></span> <span data-ttu-id="03da7-256">이 경우 현재 데이터베이스 상태를 원래 데이터와 비교하여 데이터가 변경되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-256">The original data is used to check against the current database state to assert that it is in fact still unchanged.</span></span> <span data-ttu-id="03da7-257">데이터가 변경된 경우 충돌이 발생하고 응용 프로그램에서는 이 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-257">If it has changed, a conflict occurs and your application must resolve it.</span></span> <span data-ttu-id="03da7-258">응용 프로그램에서는 한 가지 옵션으로 원래 상태를 현재 데이터베이스 상태로 다시 설정한 후 업데이트를 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-258">One option of your application is to reset the original state to the current database state and to try the update again.</span></span> <span data-ttu-id="03da7-259">자세한 내용은 참조 [하는 방법: 변경 내용 충돌 관리](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-259">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
 <span data-ttu-id="03da7-260"><xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 false로 설정하여 캐싱 및 변경 추적을 해제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-260">You can also set <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to false, which turns off caching and change tracking.</span></span> <span data-ttu-id="03da7-261">이렇게 하면 쿼리할 때마다 최신 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-261">You can then retrieve the latest values every time that you query.</span></span>  
  
## <a name="cannot-call-submitchanges-in-read-only-mode"></a><span data-ttu-id="03da7-262">읽기 전용 모드에서 SubmitChanges를 호출할 수 없음</span><span class="sxs-lookup"><span data-stu-id="03da7-262">Cannot Call SubmitChanges in Read-only Mode</span></span>  
 <span data-ttu-id="03da7-263">질문.</span><span class="sxs-lookup"><span data-stu-id="03da7-263">Q.</span></span> <span data-ttu-id="03da7-264">읽기 전용 모드에서 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-264">When I try to call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in read-only mode, I get an error.</span></span>  
  
 <span data-ttu-id="03da7-265">대답:</span><span class="sxs-lookup"><span data-stu-id="03da7-265">A.</span></span> <span data-ttu-id="03da7-266">읽기 전용 모드에서는 컨텍스트에서 변경 내용을 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03da7-266">Read-only mode turns off the ability of the context to track changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03da7-267">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03da7-267">See Also</span></span>  
 [<span data-ttu-id="03da7-268">참조</span><span class="sxs-lookup"><span data-stu-id="03da7-268">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="03da7-269">문제 해결</span><span class="sxs-lookup"><span data-stu-id="03da7-269">Troubleshooting</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)  
 [<span data-ttu-id="03da7-270">LINQ to SQL의 보안</span><span class="sxs-lookup"><span data-stu-id="03da7-270">Security in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md)
