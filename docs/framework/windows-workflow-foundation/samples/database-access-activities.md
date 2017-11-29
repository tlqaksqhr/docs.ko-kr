---
title: Database Access Activities
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 10066c1d5e6bd0d03d91337a2fed987c881b23b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="database-access-activities"></a><span data-ttu-id="f8a48-102">Database Access Activities</span><span class="sxs-lookup"><span data-stu-id="f8a48-102">Database Access Activities</span></span>
<span data-ttu-id="f8a48-103">데이터베이스 액세스 활동을 사용하여 워크플로 내에서 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-103">Database access activities allow you to access a database within a workflow.</span></span> <span data-ttu-id="f8a48-104">이러한 활동을 검색 하거나 정보를 수정 하 고 사용 하 여 데이터베이스에 액세스 허용 [ADO.NET](http://go.microsoft.com/fwlink/?LinkId=166081) 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-104">These activities allow accessing databases to retrieve or modify information and use [ADO.NET](http://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8a48-105">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f8a48-106">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f8a48-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8a48-107">이 디렉터리가 없으면 다운로드 페이지로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="f8a48-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8a48-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`  
  
## <a name="database-activities"></a><span data-ttu-id="f8a48-109">데이터베이스 활동</span><span class="sxs-lookup"><span data-stu-id="f8a48-109">Database Activities</span></span>  
 <span data-ttu-id="f8a48-110">다음 단원에서는 이 샘플에 포함된 활동 목록에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-110">The following sections detail the list of activities included in this sample.</span></span>  
  
## <a name="dbupdate"></a><span data-ttu-id="f8a48-111">DbUpdate</span><span class="sxs-lookup"><span data-stu-id="f8a48-111">DbUpdate</span></span>  
 <span data-ttu-id="f8a48-112">데이터베이스의 내용을 수정(삽입, 업데이트, 삭제 등)하는 SQL 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-112">Executes a SQL query that produces a modification in the database (insert, update, delete, and other modifications).</span></span>  
  
 <span data-ttu-id="f8a48-113">이 클래스는 <xref:System.Activities.AsyncCodeActivity>에서 파생되어 비동기 기능을 사용하므로 작업을 비동기적으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-113">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity> and uses its asynchronous capabilities).</span></span>  
  
 <span data-ttu-id="f8a48-114">공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 응용 프로그램 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-114">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="f8a48-115">실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-115">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="f8a48-116">`DbUpdate`가 실행된 후에는 영향을 받은 레코드의 수가 `AffectedRecords` 속성에서 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-116">After `DbUpdate` is executed, the number of affected records is returned in the `AffectedRecords` property.</span></span>  
  
```  
Public class DbUpdate: AsyncCodeActivity  
{  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [DependsOn("Parameters")]  
    public OutArgument<int> AffectedRecords { get; set; }       
}  
```  
  
|<span data-ttu-id="f8a48-117">인수</span><span class="sxs-lookup"><span data-stu-id="f8a48-117">Argument</span></span>|<span data-ttu-id="f8a48-118">설명</span><span class="sxs-lookup"><span data-stu-id="f8a48-118">Description</span></span>|  
|-|-|  
|<span data-ttu-id="f8a48-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="f8a48-119">ProviderName</span></span>|<span data-ttu-id="f8a48-120">ADO.NET 공급자 고정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-120">ADO.NET provider invariant name.</span></span> <span data-ttu-id="f8a48-121">이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-121">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="f8a48-122">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="f8a48-122">ConnectionString</span></span>|<span data-ttu-id="f8a48-123">데이터베이스에 연결할 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-123">Connection string to connect to the database.</span></span> <span data-ttu-id="f8a48-124">이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-124">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="f8a48-125">ConfigName</span><span class="sxs-lookup"><span data-stu-id="f8a48-125">ConfigName</span></span>|<span data-ttu-id="f8a48-126">연결 정보가 저장된 구성 파일 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-126">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="f8a48-127">이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-127">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="f8a48-128">CommandType</span><span class="sxs-lookup"><span data-stu-id="f8a48-128">CommandType</span></span>|<span data-ttu-id="f8a48-129">실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-129">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="f8a48-130">Sql</span><span class="sxs-lookup"><span data-stu-id="f8a48-130">Sql</span></span>|<span data-ttu-id="f8a48-131">실행할 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-131">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="f8a48-132">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8a48-132">Parameters</span></span>|<span data-ttu-id="f8a48-133">SQL 쿼리의 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-133">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="f8a48-134">AffectedRecords</span><span class="sxs-lookup"><span data-stu-id="f8a48-134">AffectedRecords</span></span>|<span data-ttu-id="f8a48-135">마지막 작업의 영향을 받은 레코드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-135">Number of records affected by the last operation.</span></span>|  
  
## <a name="dbqueryscalar"></a><span data-ttu-id="f8a48-136">DbQueryScalar</span><span class="sxs-lookup"><span data-stu-id="f8a48-136">DbQueryScalar</span></span>  
 <span data-ttu-id="f8a48-137">데이터베이스에서 단일 값을 검색하는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-137">Executes a query that retrieves a single value from the database.</span></span>  
  
 <span data-ttu-id="f8a48-138">이 클래스는 <xref:System.Activities.AsyncCodeActivity%601>에서 파생되어 비동기 기능을 사용하므로 작업을 비동기적으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-138">This class performs its work asynchronously (it derives from <xref:System.Activities.AsyncCodeActivity%601> and uses its asynchronous capabilities).</span></span>  
  
 <span data-ttu-id="f8a48-139">공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 응용 프로그램 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-139">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="f8a48-140">실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-140">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="f8a48-141">후 `DbQueryScalar` 은 실행에서 스칼라가 반환 되는 `Result``out` 인수 (형식의 `TResult`, 즉 기본 클래스에 정의 된 <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="f8a48-141">After `DbQueryScalar` is executed, the scalar is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>  
  
```  
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>  
{  
    // public arguments  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
}  
```  
  
|<span data-ttu-id="f8a48-142">인수</span><span class="sxs-lookup"><span data-stu-id="f8a48-142">Argument</span></span>|<span data-ttu-id="f8a48-143">설명</span><span class="sxs-lookup"><span data-stu-id="f8a48-143">Description</span></span>|  
|-|-|  
|<span data-ttu-id="f8a48-144">ProviderName</span><span class="sxs-lookup"><span data-stu-id="f8a48-144">ProviderName</span></span>|<span data-ttu-id="f8a48-145">ADO.NET 공급자 고정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-145">ADO.NET provider invariant name.</span></span> <span data-ttu-id="f8a48-146">이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-146">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="f8a48-147">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="f8a48-147">ConnectionString</span></span>|<span data-ttu-id="f8a48-148">데이터베이스에 연결할 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-148">Connection string to connect to the database.</span></span> <span data-ttu-id="f8a48-149">이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-149">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="f8a48-150">ConfigName</span><span class="sxs-lookup"><span data-stu-id="f8a48-150">ConfigName</span></span>|<span data-ttu-id="f8a48-151">연결 정보가 저장된 구성 파일 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-151">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="f8a48-152">이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-152">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="f8a48-153">CommandType</span><span class="sxs-lookup"><span data-stu-id="f8a48-153">CommandType</span></span>|<span data-ttu-id="f8a48-154">실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-154">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="f8a48-155">Sql</span><span class="sxs-lookup"><span data-stu-id="f8a48-155">Sql</span></span>|<span data-ttu-id="f8a48-156">실행할 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-156">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="f8a48-157">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8a48-157">Parameters</span></span>|<span data-ttu-id="f8a48-158">SQL 쿼리의 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-158">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="f8a48-159">결과</span><span class="sxs-lookup"><span data-stu-id="f8a48-159">Result</span></span>|<span data-ttu-id="f8a48-160">쿼리가 실행된 후에 얻은 스칼라입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-160">Scalar that is obtained after the query is executed.</span></span> <span data-ttu-id="f8a48-161">이 인수는 `TResult` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-161">This argument is of type `TResult`.</span></span>|  
  
## <a name="dbquery"></a><span data-ttu-id="f8a48-162">DbQuery</span><span class="sxs-lookup"><span data-stu-id="f8a48-162">DbQuery</span></span>  
 <span data-ttu-id="f8a48-163">개체 목록을 검색하는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-163">Executes a query that retrieves a list of objects.</span></span> <span data-ttu-id="f8a48-164">매핑 함수가 실행 되는 쿼리를 실행 한 후 (수 <xref:System.Func%601> < `DbDataReader`, `TResult`> 또는 <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>).</span><span class="sxs-lookup"><span data-stu-id="f8a48-164">After the query is executed, a mapping function is executed (it can be <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>).</span></span> <span data-ttu-id="f8a48-165">이 매핑 함수는 `DbDataReader`에서 레코드를 가져오고 이를 반환할 개체에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-165">This mapping function gets a record in a `DbDataReader` and maps it to the object to be returned.</span></span>  
  
 <span data-ttu-id="f8a48-166">공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 응용 프로그램 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-166">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="f8a48-167">실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-167">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="f8a48-168">SQL 쿼리의 결과는 `DbDataReader`를 사용하여 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-168">The results of the SQL query are retrieved using a `DbDataReader`.</span></span> <span data-ttu-id="f8a48-169">활동에서는 `DbDataReader`를 반복하고 `DbDataReader`의 행을 `TResult`의 인스턴스에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-169">The activity iterates through the `DbDataReader` and maps the rows in the `DbDataReader` to an instance of `TResult`.</span></span> <span data-ttu-id="f8a48-170">사용자의 `DbQuery` 매핑 코드 및이 작업을 수행 하려면 두 가지 방법으로 제공 해야 하는:를 사용 하는 <xref:System.Func%601> < `DbDataReader`, `TResult`> 또는 <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-170">The user of `DbQuery` has to provide the mapping code and this can be done in two ways: using a <xref:System.Func%601><`DbDataReader`, `TResult`> or an <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>.</span></span> <span data-ttu-id="f8a48-171">첫 번째의 경우에는 단일 실행 펄스에서 매핑이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-171">In the first case, the map is done in a single pulse of execution.</span></span> <span data-ttu-id="f8a48-172">따라서 속도가 더 빠르지만 매핑이 XAML로 serialize될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-172">Therefore, it is faster, but this cannot be serialized to XAML.</span></span> <span data-ttu-id="f8a48-173">두 번째의 경우에는 매핑이 여러 펄스에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-173">In the last case, the map is performed in multiple pulses.</span></span> <span data-ttu-id="f8a48-174">따라서 속도가 더 느릴 수 있지만, 매핑이 XAML로 serialize되고 선언적으로 작성될 수 있으며 기존 활동이 매핑에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-174">Therefore, it might be slower but can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>  
  
```  
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class  
{  
    // public arguments  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [OverloadGroup("DirectMapping")]  
    [DefaultValue(null)]  
    public Func<DbDataReader, TResult> Mapper { get; set; }  
  
    [OverloadGroup("MultiplePulseMapping")]  
    [DefaultValue(null)]  
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }  
}  
```  
  
|<span data-ttu-id="f8a48-175">인수</span><span class="sxs-lookup"><span data-stu-id="f8a48-175">Argument</span></span>|<span data-ttu-id="f8a48-176">설명</span><span class="sxs-lookup"><span data-stu-id="f8a48-176">Description</span></span>|  
|-|-|  
|<span data-ttu-id="f8a48-177">ProviderName</span><span class="sxs-lookup"><span data-stu-id="f8a48-177">ProviderName</span></span>|<span data-ttu-id="f8a48-178">ADO.NET 공급자 고정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-178">ADO.NET provider invariant name.</span></span> <span data-ttu-id="f8a48-179">이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-179">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="f8a48-180">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="f8a48-180">ConnectionString</span></span>|<span data-ttu-id="f8a48-181">데이터베이스에 연결할 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-181">Connection string to connect to the database.</span></span> <span data-ttu-id="f8a48-182">이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-182">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="f8a48-183">ConfigName</span><span class="sxs-lookup"><span data-stu-id="f8a48-183">ConfigName</span></span>|<span data-ttu-id="f8a48-184">연결 정보가 저장된 구성 파일 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-184">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="f8a48-185">이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-185">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="f8a48-186">CommandType</span><span class="sxs-lookup"><span data-stu-id="f8a48-186">CommandType</span></span>|<span data-ttu-id="f8a48-187">실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-187">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="f8a48-188">Sql</span><span class="sxs-lookup"><span data-stu-id="f8a48-188">Sql</span></span>|<span data-ttu-id="f8a48-189">실행할 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-189">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="f8a48-190">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8a48-190">Parameters</span></span>|<span data-ttu-id="f8a48-191">SQL 쿼리의 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-191">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="f8a48-192">Mapper</span><span class="sxs-lookup"><span data-stu-id="f8a48-192">Mapper</span></span>|<span data-ttu-id="f8a48-193">매핑 함수 (<xref:System.Func%601><`DbDataReader`, `TResult`>)의 레코드를 받아 하는 `DataReader` 형식의 개체의 인스턴스를 반환 하는 쿼리 실행 결과로 얻은 `TResult` 는 에추가할수`Result` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-193">Mapping function (<xref:System.Func%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="f8a48-194">이 경우 매핑은 단일 실행 펄스에서 수행되지만 디자이너를 사용하여 선언적으로 작성될 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-194">In this case, mapping is done in a single pulse of execution, but it cannot be authored declaratively using the designer.</span></span>|  
|<span data-ttu-id="f8a48-195">MapperFunc</span><span class="sxs-lookup"><span data-stu-id="f8a48-195">MapperFunc</span></span>|<span data-ttu-id="f8a48-196">매핑 함수 (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>)의 레코드를 받아 하는 `DataReader` 형식의 개체의 인스턴스를 반환 하는 쿼리 실행 결과로 얻은 `TResult` 는 에추가할수`Result` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-196">Mapping function (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>) that takes a record in the `DataReader` obtained as result of executing the query and returns an instance of an object of type `TResult` to be added to the `Result` collection.</span></span><br /><br /> <span data-ttu-id="f8a48-197">이 경우에는 여러 실행 펄스에서 매핑이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-197">In this case, the mapping is done in multiple pulses of execution.</span></span> <span data-ttu-id="f8a48-198">이 함수는 XAML로 serialize되고 선언적으로 작성될 수 있으며 기존 활동이 매핑에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-198">This function can be serialized to XAML and authored declaratively (any existing activity can participate in the mapping).</span></span>|  
|<span data-ttu-id="f8a48-199">결과</span><span class="sxs-lookup"><span data-stu-id="f8a48-199">Result</span></span>|<span data-ttu-id="f8a48-200">쿼리를 실행하고 `DataReader`의 각 레코드에 대해 매핑 함수를 실행한 결과로 얻은 개체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-200">List of objects obtained as result of executing the query and executing the mapping function for each record in the `DataReader`.</span></span>|  
  
## <a name="dbquerydataset"></a><span data-ttu-id="f8a48-201">DbQueryDataSet</span><span class="sxs-lookup"><span data-stu-id="f8a48-201">DbQueryDataSet</span></span>  
 <span data-ttu-id="f8a48-202"><xref:System.Data.DataSet>을 반환하는 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-202">Executes a query that returns a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f8a48-203">이 클래스는 작업을 비동기적으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-203">This class performs its work asynchronously.</span></span> <span data-ttu-id="f8a48-204">파생 <xref:System.Activities.AsyncCodeActivity> < `TResult`> 비동기 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-204">It derives from <xref:System.Activities.AsyncCodeActivity><`TResult`> and uses its asynchronous capabilities.</span></span>  
  
 <span data-ttu-id="f8a48-205">공급자 고정 이름(`ProviderName`)과 연결 문자열(`ConnectionString`)을 설정하거나 응용 프로그램 구성 파일의 연결 문자열 구성 이름(`ConfigFileSectionName`)만 사용하여 연결 정보를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-205">The connection information can be configured by setting a provider invariant name (`ProviderName`) and the connection string (`ConnectionString`) or just using a connection string configuration name (`ConfigFileSectionName`) from the application configuration file.</span></span>  
  
 <span data-ttu-id="f8a48-206">실행할 쿼리는 `Sql` 속성에서 구성하며 매개 변수는 `Parameters` 컬렉션을 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-206">The query to be executed is configured in its `Sql` property and the parameters are passed through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="f8a48-207">후는 `DbQueryDataSet` 실행 되는 `DataSet` 에 반환 되는 `Result``out` 인수 (형식의 `TResult`, 즉 기본 클래스에 정의 된 <xref:System.Activities.AsyncCodeActivity%601>).</span><span class="sxs-lookup"><span data-stu-id="f8a48-207">After the `DbQueryDataSet` is executed the `DataSet` is returned in the `Result``out` argument (of type `TResult`, that is defined in the base class <xref:System.Activities.AsyncCodeActivity%601>).</span></span>  
  
```  
public class DbQueryDataSet : AsyncCodeActivity<DataSet>  
{  
    // public arguments  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
}  
```  
  
|<span data-ttu-id="f8a48-208">인수</span><span class="sxs-lookup"><span data-stu-id="f8a48-208">Argument</span></span>|<span data-ttu-id="f8a48-209">설명</span><span class="sxs-lookup"><span data-stu-id="f8a48-209">Description</span></span>|  
|-|-|  
|<span data-ttu-id="f8a48-210">ProviderName</span><span class="sxs-lookup"><span data-stu-id="f8a48-210">ProviderName</span></span>|<span data-ttu-id="f8a48-211">ADO.NET 공급자 고정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-211">ADO.NET provider invariant name.</span></span> <span data-ttu-id="f8a48-212">이 인수를 설정할 경우 `ConnectionString`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-212">If this argument is set, then the `ConnectionString` must also be set.</span></span>|  
|<span data-ttu-id="f8a48-213">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="f8a48-213">ConnectionString</span></span>|<span data-ttu-id="f8a48-214">데이터베이스에 연결할 연결 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-214">Connection string to connect to the database.</span></span> <span data-ttu-id="f8a48-215">이 인수를 설정할 경우 `ProviderName`도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-215">If this argument is set, then `ProviderName` must also be set.</span></span>|  
|<span data-ttu-id="f8a48-216">ConfigName</span><span class="sxs-lookup"><span data-stu-id="f8a48-216">ConfigName</span></span>|<span data-ttu-id="f8a48-217">연결 정보가 저장된 구성 파일 섹션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-217">Name of the configuration file section where the connection information is stored.</span></span> <span data-ttu-id="f8a48-218">이 인수를 설정할 경우 `ProviderName` 및 `ConnectionString`은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-218">When this argument is set `ProviderName` and `ConnectionString` are not required.</span></span>|  
|<span data-ttu-id="f8a48-219">CommandType</span><span class="sxs-lookup"><span data-stu-id="f8a48-219">CommandType</span></span>|<span data-ttu-id="f8a48-220">실행할 <xref:System.Data.Common.DbCommand>의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-220">Type of the <xref:System.Data.Common.DbCommand> to be executed.</span></span>|  
|<span data-ttu-id="f8a48-221">Sql</span><span class="sxs-lookup"><span data-stu-id="f8a48-221">Sql</span></span>|<span data-ttu-id="f8a48-222">실행할 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-222">The SQL command to be executed.</span></span>|  
|<span data-ttu-id="f8a48-223">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8a48-223">Parameters</span></span>|<span data-ttu-id="f8a48-224">SQL 쿼리의 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-224">Collection of the parameters of the SQL query.</span></span>|  
|<span data-ttu-id="f8a48-225">결과</span><span class="sxs-lookup"><span data-stu-id="f8a48-225">Result</span></span>|<span data-ttu-id="f8a48-226">쿼리가 실행된 후에 얻은 <xref:System.Data.DataSet>입니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-226"><xref:System.Data.DataSet> that is obtained after the query is executed.</span></span>|  
  
## <a name="configuring-connection-information"></a><span data-ttu-id="f8a48-227">연결 정보 구성</span><span class="sxs-lookup"><span data-stu-id="f8a48-227">Configuring Connection Information</span></span>  
 <span data-ttu-id="f8a48-228">모든 DbActivity는 동일한 구성 매개 변수를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-228">All DbActivities share the same configuration parameters.</span></span> <span data-ttu-id="f8a48-229">다음과 같은 두 가지 방법으로 DbActivity를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-229">They can be configured in two ways:</span></span>  
  
-   <span data-ttu-id="f8a48-230">`ConnectionString + InvariantName`: ADO.NET 공급자 고정 이름과 연결 문자열을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-230">`ConnectionString + InvariantName`: Set the ADO.NET provider invariant name and connection string.</span></span>  
  
    ```  
    Activity dbSelectCount = new DbQueryScalar<DateTime>()  
    {  
        ProviderName = "System.Data.SqlClient",  
        ConnectionString = @"Data Source=.\SQLExpress;  
                             Initial Catalog=DbActivitiesSample;  
                             Integrated Security=True",  
        Sql = "SELECT GetDate()"  
    };  
    ```  
  
-   <span data-ttu-id="f8a48-231">`ConfigName`: 연결 정보를 포함하는 구성 파일 섹션의 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-231">`ConfigName`: Set the name of the configuration section that contains the connection information.</span></span>  
  
    ```xml  
    <connectionStrings>      
        <add name="DbActivitiesSample"  
             providerName="System.Data.SqlClient"  
             connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>  
      </connectionStrings>  
    ```  
  
-   <span data-ttu-id="f8a48-232">활동에서는 다음과 같이 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-232">In the activity:</span></span>  
  
    ```  
    Activity dbSelectCount = new DbQueryScalar<int>()  
    {                  
        ConfigName = "DbActivitiesSample",  
        Sql = "SELECT COUNT(*) FROM Roles"  
    };  
    ```  
  
## <a name="running-this-sample"></a><span data-ttu-id="f8a48-233">샘플 실행</span><span class="sxs-lookup"><span data-stu-id="f8a48-233">Running this sample</span></span>  
  
### <a name="setup-instructions"></a><span data-ttu-id="f8a48-234">설치 지침</span><span class="sxs-lookup"><span data-stu-id="f8a48-234">Setup instructions</span></span>  
 <span data-ttu-id="f8a48-235">이 샘플에서는 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-235">This sample uses a database.</span></span> <span data-ttu-id="f8a48-236">샘플과 함께 설치 및 로드 스크립트(Setup.cmd)가 제공되며,</span><span class="sxs-lookup"><span data-stu-id="f8a48-236">A set-up and load script (Setup.cmd) is provided with the sample.</span></span> <span data-ttu-id="f8a48-237">이 파일은 명령 프롬프트를 사용하여 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-237">You must execute that file using the command prompt.</span></span>  
  
 <span data-ttu-id="f8a48-238">Setup.cmd 스크립트는 다음을 수행하는 SQL 명령이 포함된 CreateDb.sql 스크립트 파일을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-238">The Setup.cmd script invokes the CreateDb.sql script file, which contains SQL commands that do the following:</span></span>  
  
-   <span data-ttu-id="f8a48-239">DbActivitiesSample이라는 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-239">Creates a database called DbActivitiesSample.</span></span>  
  
-   <span data-ttu-id="f8a48-240">Roles 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-240">Creates the Roles table.</span></span>  
  
-   <span data-ttu-id="f8a48-241">Employees 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-241">Creates Employees table.</span></span>  
  
-   <span data-ttu-id="f8a48-242">Roles 테이블에 3개의 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-242">Inserts three records into the Roles table.</span></span>  
  
-   <span data-ttu-id="f8a48-243">Employees 테이블에 12개의 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-243">Inserts twelve records into the Employees table.</span></span>  
  
##### <a name="to-run-setupcmd"></a><span data-ttu-id="f8a48-244">Setup.cmd를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f8a48-244">To run Setup.cmd</span></span>  
  
1.  <span data-ttu-id="f8a48-245">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-245">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="f8a48-246">DbActivities 샘플 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-246">Go to the DbActivities sample folder.</span></span>  
  
3.  <span data-ttu-id="f8a48-247">"Setup.cmd"를 입력 하 고 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-247">Type "setup.cmd" and press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8a48-248">Setup.cmd에서는 로컬 컴퓨터의 SqlExpress 인스턴스에 샘플을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-248">Setup.cmd attempts to install the sample in your local machine SqlExpress instance.</span></span> <span data-ttu-id="f8a48-249">다른 SQL 서버 인스턴스에 샘플을 설치하려면 Setup.cmd를 새 인스턴스 이름으로 편집하세요.</span><span class="sxs-lookup"><span data-stu-id="f8a48-249">If you want to install it in other SQL server instance, edit Setup.cmd with the new instance name.</span></span>  
  
##### <a name="to-uninstall-the-sample-database"></a><span data-ttu-id="f8a48-250">샘플 데이터베이스를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="f8a48-250">To uninstall the sample database</span></span>  
  
1.  <span data-ttu-id="f8a48-251">명령 프롬프트에서 샘플 폴더로 이동하여 Cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-251">Run Cleanup.cmd from the sample folder in a command prompt.</span></span>  
  
##### <a name="to-run-the-sample"></a><span data-ttu-id="f8a48-252">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f8a48-252">To run the sample</span></span>  
  
1.  <span data-ttu-id="f8a48-253">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-253">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]</span></span>  
  
2.  <span data-ttu-id="f8a48-254">Ctrl+Shift+B를 눌러 솔루션을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-254">To compile the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f8a48-255">Ctrl+F5를 눌러 샘플을 디버깅하지 않고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-255">To run the sample without debugging, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8a48-256">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-256">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f8a48-257">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f8a48-257">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8a48-258">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="f8a48-258">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8a48-259">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8a48-259">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
