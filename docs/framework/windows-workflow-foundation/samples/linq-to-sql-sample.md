---
title: LINQ to SQL 샘플
ms.date: 03/30/2017
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
ms.openlocfilehash: 3cfcaf3de1a22b8bb5505083f127a9888b99dbd8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="linq-to-sql-sample"></a><span data-ttu-id="f1e7d-102">LINQ to SQL 샘플</span><span class="sxs-lookup"><span data-stu-id="f1e7d-102">LINQ to SQL Sample</span></span>
<span data-ttu-id="f1e7d-103">이 샘플에서는 SQL Server 데이터베이스의 테이블에 있는 LINQ to SQL 쿼리 엔터티를 사용하는 활동을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-103">This sample demonstrates how to create an activity to use LINQ to SQL query entities from tables in SQL Server databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f1e7d-104">WCF 샘플 컴퓨터에 이미 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-104">The WCF samples may already be installed on your machine.</span></span> <span data-ttu-id="f1e7d-105">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  <span data-ttu-id="f1e7d-106">이 디렉터리가 없으면 이 페이지의 맨 위에 있는 다운로드 샘플 링크를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-106">If this directory does not exist, click the download sample link at the top of this page.</span></span> <span data-ttu-id="f1e7d-107">이 링크 다운로드 되 고 모든 설치의 [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, 및 [!INCLUDE[infocard](../../../../includes/infocard-md.md)] 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-107">Note that this link downloads and installs all of the [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, and [!INCLUDE[infocard](../../../../includes/infocard-md.md)] samples.</span></span> <span data-ttu-id="f1e7d-108">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a><span data-ttu-id="f1e7d-109">FindInSqlTable의 활동 세부 정보</span><span class="sxs-lookup"><span data-stu-id="f1e7d-109">Activity details for FindInSqlTable</span></span>  
 <span data-ttu-id="f1e7d-110">이 활동을 사용하면 사용자가 LINQ to SQL을 사용하여 데이터베이스에 있는 테이블의 엔터티를 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-110">This activity allows users to query entities from tables in a database using LINQ to SQL.</span></span> <span data-ttu-id="f1e7d-111">활동 사용자가 람다 식 형식의 LINQ 조건자를 제공하여 결과를 필터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-111">Users of the activity can also provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="f1e7d-112">조건자를 제공하지 않으면 전체 테이블이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-112">If no predicate is provided, the entire table is returned.</span></span> <span data-ttu-id="f1e7d-113">다음 표에서는 활동의 속성 및 반환 값에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-113">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="f1e7d-114">속성 또는 반환 값</span><span class="sxs-lookup"><span data-stu-id="f1e7d-114">Property or Return Value</span></span>|<span data-ttu-id="f1e7d-115">설명</span><span class="sxs-lookup"><span data-stu-id="f1e7d-115">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="f1e7d-116">`Collection` 속성</span><span class="sxs-lookup"><span data-stu-id="f1e7d-116">`Collection` property</span></span>|<span data-ttu-id="f1e7d-117">소스 컬렉션을 지정하는 필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-117">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="f1e7d-118">`Predicate` 속성</span><span class="sxs-lookup"><span data-stu-id="f1e7d-118">`Predicate` property</span></span>|<span data-ttu-id="f1e7d-119">람다 식 형식으로 컬렉션의 필터를 지정하는 필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-119">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="f1e7d-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="f1e7d-120">Return Value</span></span>|<span data-ttu-id="f1e7d-121">필터링된 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-121">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="f1e7d-122">사용자 지정 활동을 사용하는 코드 샘플</span><span class="sxs-lookup"><span data-stu-id="f1e7d-122">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="f1e7d-123">다음 코드 예제에서는 `FindInSqlTable` 사용자 지정 활동을 사용하여 `Employee`라는 SQL Server 테이블에서 `Role` 열이 `SDE`인 모든 행을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-123">The following code example uses the `FindInSqlTable` custom activity to find all rows in a SQL Server table named `Employee` where the `Role` column is equal to `SDE`.</span></span>  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f1e7d-124">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="f1e7d-124">To use this sample</span></span>  
  
1.  <span data-ttu-id="f1e7d-125">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-125">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="f1e7d-126">이 샘플이 들어 있는 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-126">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="f1e7d-127">Setup.cmd 명령 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-127">Run the Setup.cmd command file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f1e7d-128">Setup.cmd 스크립트가 로컬 컴퓨터 SQL Server Express에 샘플 데이터베이스를 설치하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-128">The Setup.cmd script attempts to install the sample database in your local machine SQL Server Express.</span></span> <span data-ttu-id="f1e7d-129">다른 SQL Server 인스턴스에 설치하려면 Setup.cmd를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-129">If you want to install it in other SQL server instance, edit Setup.cmd.</span></span>  
  
     <span data-ttu-id="f1e7d-130">Setup.cmd 스크립트가 다음 동작을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-130">The Setup.cmd script does the following actions.:</span></span>  
  
    -   <span data-ttu-id="f1e7d-131">LinqToSqlSample이라는 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-131">Creates a database called LinqToSqlSample.</span></span>  
  
    -   <span data-ttu-id="f1e7d-132">Roles 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-132">Creates a Roles table.</span></span>  
  
    -   <span data-ttu-id="f1e7d-133">Employees 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-133">Creates an Employees table.</span></span>  
  
    -   <span data-ttu-id="f1e7d-134">Roles 테이블에 세 개의 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-134">Inserts 3 records into the Roles table.</span></span>  
  
    -   <span data-ttu-id="f1e7d-135">Employees 테이블에 12개의 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-135">Inserts 12 records into the Employees table.</span></span>  
  
4.  <span data-ttu-id="f1e7d-136">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 LinqToSQL.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-136">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToSQL.sln solution file.</span></span>  
  
5.  <span data-ttu-id="f1e7d-137">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-137">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="f1e7d-138">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-138">To run the solution, press F5.</span></span>  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a><span data-ttu-id="f1e7d-139">LinqToSql 샘플 데이터베이스를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="f1e7d-139">To uninstall the LinqToSql sample database</span></span>  
  
1.  <span data-ttu-id="f1e7d-140">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-140">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="f1e7d-141">이 샘플이 들어 있는 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-141">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="f1e7d-142">Cleanup.cmd 명령 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-142">Run the Cleanup.cmd command file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f1e7d-143">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f1e7d-144">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f1e7d-145">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f1e7d-146">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e7d-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a><span data-ttu-id="f1e7d-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1e7d-147">See Also</span></span>  
 [<span data-ttu-id="f1e7d-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f1e7d-148">LINQ to SQL</span></span>](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [<span data-ttu-id="f1e7d-149">시작 (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="f1e7d-149">Getting Started (LINQ to SQL)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150377)
