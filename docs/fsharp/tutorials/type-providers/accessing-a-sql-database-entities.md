---
title: '연습: 형식 공급자 및 엔터티를 사용하여 SQL Database에 액세스(F#)'
description: 'F # 3.0의 ADO.NET 엔터티 데이터 모델에 따라 SQL 데이터베이스에 대 한 형식화 된 데이터에 액세스 하는 방법을 알아봅니다.'
keywords: visual f#, f#, 함수형 프로그래밍
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 153050f27ade0152741bdc2d77ab85eefa8418e9
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a><span data-ttu-id="bfbee-104">연습: 형식 공급자 및 엔터티를 사용하여 SQL Database에 액세스</span><span class="sxs-lookup"><span data-stu-id="bfbee-104">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>

> [!NOTE]
<span data-ttu-id="bfbee-105">이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="bfbee-106">최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](https://fsharp.github.io/FSharp.Data/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfbee-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="bfbee-107">API 참조 링크 MSDN을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="bfbee-108">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="bfbee-109">F# 3.0에 대한 이 연습에서는 ADO.NET 엔터티 데이터 모델을 기반으로 SQL 데이터베이스에 대해 형식화된 데이터에 액세스하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-109">This walkthrough for F# 3.0 shows you how to access typed data for a SQL database based on the ADO.NET Entity Data Model.</span></span> <span data-ttu-id="bfbee-110">이 연습에서는 SQL 데이터베이스와 함께 사용할 F# `SqlEntityConnection` 형식 공급자를 설정하는 방법, 데이터에 대해 쿼리를 작성하는 방법, 데이터베이스에서 저장 프로시저를 호출하는 방법, ADO.NET Entity Framework 형식 및 메서드 중 일부를 사용하여 데이터베이스를 업데이트하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-110">This walkthrough shows you how to set up the F# `SqlEntityConnection` type provider for use with a SQL database, how to write queries against the data, how to call stored procedures on the database, as well as how to use some of the ADO.NET Entity Framework types and methods to update the database.</span></span>

<span data-ttu-id="bfbee-111">이 연습에서는 다음 작업을 설명하는데, 연습을 성공적으로 수행하려면 이 순서대로 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-111">This walkthrough illustrates the following tasks, which you should perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="bfbee-112">School 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-112">Create the School database</span></span>
<br />

- <span data-ttu-id="bfbee-113">F# 프로젝트를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-113">Create and configure an F# project</span></span>
<br />

- <span data-ttu-id="bfbee-114">형식 공급자를 구성 하 고 엔터티 데이터 모델에 연결</span><span class="sxs-lookup"><span data-stu-id="bfbee-114">Configure the type provider and connect to the Entity Data Model</span></span>
<br />

- <span data-ttu-id="bfbee-115">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="bfbee-115">Query the database</span></span>
<br />

- <span data-ttu-id="bfbee-116">데이터베이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="bfbee-116">Updating the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="bfbee-117">전제 조건</span><span class="sxs-lookup"><span data-stu-id="bfbee-117">Prerequisites</span></span>
<span data-ttu-id="bfbee-118">이러한 단계를 완료하려면 데이터베이스를 만들 수 있는 SQL Server를 실행하는 서버에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-118">You must have access to a server that's running SQL Server where you can create a database to complete these steps.</span></span>

## <a name="create-the-school-database"></a><span data-ttu-id="bfbee-119">School 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-119">Create the School database</span></span>
<span data-ttu-id="bfbee-120">관리자 액세스 권한을 가진 SQL Server를 실행하는 서버에 School 데이터베이스를 만들거나 LocalDB를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-120">You can create the School database on any server that's running SQL Server to which you have administrative access, or you can use LocalDB.</span></span>


#### <a name="to-create-the-school-database"></a><span data-ttu-id="bfbee-121">School 데이터베이스 만들려면</span><span class="sxs-lookup"><span data-stu-id="bfbee-121">To create the School database</span></span>

1. <span data-ttu-id="bfbee-122">**서버 탐색기**에 대 한 바로 가기 메뉴를 열고는 **데이터 연결** 노드를 선택한 후 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-122">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and then choose **Add Connection**.</span></span>
<br />  <span data-ttu-id="bfbee-123">**연결 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-123">The **Add Connection** dialog box appears.</span></span>
<br />

2. <span data-ttu-id="bfbee-124">에 **서버 이름** 상자를 관리 액세스 권한이 있는 SQL Server 인스턴스의 이름을 지정 하거나 서버에 액세스할 수 없는 경우 (localdb\v11.0)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-124">In the **Server name** box, specify the name of an instance of SQL Server to which you have administrative access, or specify (localdb\v11.0) if you don't have access to a server.</span></span>
<br />  <span data-ttu-id="bfbee-125">SQL Server Express LocalDB는 사용자 컴퓨터에서 개발 및 테스트를 위한 간단한 데이터베이스 서버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-125">SQL Server Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="bfbee-126">LocalDB에 대 한 자세한 내용은 참조 [연습: Visual Studio에서 로컬 데이터베이스 파일 만들기](https://msdn.microsoft.com/library/ms233763.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-126">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>
<br />  <span data-ttu-id="bfbee-127">새 노드가 만들어집니다 **서버 탐색기** 아래 **데이터 연결**합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-127">A new node is created in **Server Explorer** under **Data Connections**.</span></span>
<br />

3. <span data-ttu-id="bfbee-128">새 연결 노드의 바로 가기 메뉴를 연 다음 선택 **새 쿼리**합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-128">Open the shortcut menu for the new connection node, and then choose **New Query**.</span></span>
<br />

4. <span data-ttu-id="bfbee-129">열기 [School 샘플 데이터베이스 만들기](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) Microsoft 웹 사이트 및 다음 복사 및 붙여넣기에서 데이터베이스 스크립트를 만드는 School 데이터베이스 편집기 창에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-129">Open [Creating the School Sample Database](https://msdn.microsoft.com/library/bb399731(v=vs.100).aspx) on the Microsoft website, and then copy and paste the database script that creates the School database into the editor window.</span></span>
<br />


## <span data-ttu-id="bfbee-130"><a name="BKMK_CreateConfigFSProj"> </a></span><span class="sxs-lookup"><span data-stu-id="bfbee-130"><a name="BKMK_CreateConfigFSProj"> </a></span></span>

## <a name="create-and-configure-an-f-project"></a><span data-ttu-id="bfbee-131">F# 프로젝트를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-131">Create and configure an F# project</span></span>
<span data-ttu-id="bfbee-132">이 단계에서 형식 공급자를 사용하려면 프로젝트를 만들고 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-132">In this step, you create a project and set it up to use a type provider.</span></span>


#### <a name="to-create-and-configure-an-f-project"></a><span data-ttu-id="bfbee-133">F# 프로젝트를 만들고 구성하려면</span><span class="sxs-lookup"><span data-stu-id="bfbee-133">To create and configure an F# project</span></span>

1. <span data-ttu-id="bfbee-134">이전에 만든 프로젝트를 닫고 다른 프로젝트를 만들고 이름을 **SchoolEDM**합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-134">Close the previous project, create another project, and name it **SchoolEDM**.</span></span>
<br />

2. <span data-ttu-id="bfbee-135">**솔루션 탐색기**, 바로 가기 메뉴를 열고 **참조**를 선택한 후 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-135">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="bfbee-136">선택 된 **프레임 워크** 노드를 선택한 다음는 **프레임 워크** 목록에서 선택 **System.Data**, **System.Data.Entity**, 및 **System.Data.Linq**합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-136">Choose the **Framework** node, and then, in the **Framework** list, choose **System.Data**, **System.Data.Entity**,  and **System.Data.Linq**.</span></span>
<br />

4. <span data-ttu-id="bfbee-137">선택은 **확장** 노드를에 대 한 참조를 추가 [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) 어셈블리를 선택한 후는 **확인** 단추 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-137">Choose the **Extensions** node, add a reference to the [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) assembly, and then choose the **OK** button to dismiss the dialog box.</span></span>
<br />

5. <span data-ttu-id="bfbee-138">다음 코드를 추가하여 내부 모듈을 정의하고 적절한 네임스페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-138">Add the following code to define an internal module and open appropriate namespaces.</span></span> <span data-ttu-id="bfbee-139">형식 공급자는 형식을 개인 또는 내부 네임스페이스로만 주입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-139">The type provider can inject types only into a private or internal namespace.</span></span>
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. <span data-ttu-id="bfbee-140">로 컴파일된 프로그램 대신 스크립트 대화형으로이 연습에서 코드를 실행 하려면를 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 **새 항목 추가**, F # 스크립트 파일을 추가 하 고 스크립트에 코드의 각 단계를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-140">To run the code in this walkthrough interactively as a script instead of as a compiled program, open the shortcut menu for the project node, choose **Add New Item**, add an F# script file, and then add the code in each step to the script.</span></span> <span data-ttu-id="bfbee-141">어셈블리 참조를 로드하려면 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-141">To load the assembly references, add the following lines.</span></span>
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. <span data-ttu-id="bfbee-142">코드 블록을 추가할 때 각 블록을 강조 표시하고 F# Interactive에서 Alt + Enter 키를 눌러 강조 표시한 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-142">Highlight each block of code as you add it, and choose the Alt + Enter keys to run it in F# Interactive.</span></span>
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="bfbee-143">형식 공급자를 구성하고 엔터티 데이터 모델에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-143">Configure the type provider, and connect to the Entity Data Model</span></span>
<span data-ttu-id="bfbee-144">이 단계에서 데이터 연결을 사용하여 형식 공급자를 설정하고 데이터로 작업할 수 있는 데이터 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-144">In this step, you set up a type provider with a data connection and obtain a data context that allows you to work with data.</span></span>


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a><span data-ttu-id="bfbee-145">형식 공급자를 구성하고 엔터티 데이터 모델에 연결하려면</span><span class="sxs-lookup"><span data-stu-id="bfbee-145">To configure the type provider, and connect to the Entity Data Model</span></span>

1. <span data-ttu-id="bfbee-146">다음 코드를 입력하여 이전에 사용자가 만든 엔터티 데이터 모델을 기반으로 F# 형식을 생성하는 `SqlEntityConnection` 형식 공급자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-146">Enter the following code to configure the `SqlEntityConnection` type provider that generates F# types based on the Entity Data Model that you created previously.</span></span> <span data-ttu-id="bfbee-147">전체 EDMX 연결 문자열 대신 SQL 연결 문자열만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-147">Instead of the full EDMX connection string, use only the SQL connection string.</span></span>
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  <span data-ttu-id="bfbee-148">이 작업을 통해 앞에서 만든 데이터베이스 연결로 형식 공급자를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-148">This action sets up a type provider with the database connection that you created earlier.</span></span> <span data-ttu-id="bfbee-149">`MultipleActiveResultSets` 속성을 통해 한 연결로 데이터베이스에서 비동기적으로 여러 명령을 실행할 수 있고 ADO.NET Entity Framework 코드에서 이런 일이 자주 발생할 수 있기 때문에, ADO.NET Entity Framework를 사용할 때 이 속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-149">The property `MultipleActiveResultSets` is needed when you use the ADO.NET Entity Framework because this property allows multiple commands to execute asynchronously on the database in one connection, which can occur frequently in ADO.NET Entity Framework code.</span></span> <span data-ttu-id="bfbee-150">자세한 내용은 [MARS(여러 활성 결과 집합)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfbee-150">For more information, see [Multiple Active Result Sets (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).</span></span>
<br />

2. <span data-ttu-id="bfbee-151">데이터베이스 테이블을 속성으로 포함하고 데이터베이스 저장 프로시저와 함수를 메서드로 포함하는 개체인 데이터 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-151">Get the data context, which is an object that contains the database tables as properties and the database stored procedures and functions as methods.</span></span>
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a><span data-ttu-id="bfbee-152">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="bfbee-152">Querying the database</span></span>
<span data-ttu-id="bfbee-153">이 단계에서는 F# 쿼리 식을 사용하여 데이터베이스에서 다양한 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-153">In this step, you use F# query expressions to execute various queries on the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="bfbee-154">데이터를 쿼리하려면</span><span class="sxs-lookup"><span data-stu-id="bfbee-154">To query the data</span></span>

- <span data-ttu-id="bfbee-155">엔터티 데이터 모델에서 데이터를 쿼리하려면 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-155">Enter the following code to query the data from the entity data model.</span></span> <span data-ttu-id="bfbee-156">데이터베이스 테이블 Course를 Courses로, Person을 People로 변경하는 Pluralize = true의 효과에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="bfbee-156">Note the effect of Pluralize = true, which changes the database table Course to Courses and Person to People.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a><span data-ttu-id="bfbee-157">데이터베이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="bfbee-157">Updating the database</span></span>
<span data-ttu-id="bfbee-158">데이터베이스를 업데이트하려면 Entity Framework 클래스와 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-158">To update the database, you use the Entity Framework classes and methods.</span></span> <span data-ttu-id="bfbee-159">두 가지 형식의 데이터 컨텍스트를 SQLEntityConnection 형식 공급자와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-159">You can use two types of data context with the SQLEntityConnection type provider.</span></span> <span data-ttu-id="bfbee-160">첫째, `ServiceTypes.SimpleDataContextTypes.EntityContainer`는 데이터베이스 테이블과 열을 나타내는 제공된 속성만 포함하는 단순화된 데이터 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-160">First, `ServiceTypes.SimpleDataContextTypes.EntityContainer` is the simplified data context, which includes only the provided properties that represent database tables and columns.</span></span> <span data-ttu-id="bfbee-161">둘째, 전체 데이터 컨텍스트는 데이터베이스에 행을 추가하기 위해 `System.Data.Objects.ObjectContext` 메서드를 포함하는 Entity Framework 클래스 `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)`의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-161">Second, the full data context is an instance of the Entity Framework class `System.Data.Objects.ObjectContext`, which contains the method `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` to add rows to the database.</span></span> <span data-ttu-id="bfbee-162">Entity Framework는 테이블과 이 테이블 사이의 관계를 인식하므로 데이터베이스 일관성이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-162">The Entity Framework recognizes the tables and the relationships between them, so it enforces database consistency.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="bfbee-163">데이터베이스를 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="bfbee-163">To update the database</span></span>

1. <span data-ttu-id="bfbee-164">프로그램에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-164">Add the following code to your program.</span></span> <span data-ttu-id="bfbee-165">이 예제에서 관계가 있는 두 개체를 추가하고 강사 및 사무실 할당을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-165">In this example, you add two objects with a relationship between them, and you add an instructor and an office assignment.</span></span> <span data-ttu-id="bfbee-166">`OfficeAssignments` 테이블에는 `InstructorID` 테이블의 `PersonID` 열을 참조하는 `Person` 열이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-166">The table `OfficeAssignments` contains the `InstructorID` column, which references the `PersonID` column in the `Person` table.</span></span>
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

<span data-ttu-id="bfbee-167">`System.Data.Objects.ObjectContext.SaveChanges`를 호출할 때까지 데이터베이스에서 변경된 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-167">Nothing is changed in the database until you call `System.Data.Objects.ObjectContext.SaveChanges`.</span></span>
<br />

2. <span data-ttu-id="bfbee-168">이제 추가한 개체를 삭제하여 데이터베이스를 이전 상태로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-168">Now restore the database to its earlier state by deleting the objects that you added.</span></span>
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
<span data-ttu-id="bfbee-169">쿼리 식을 사용하는 경우 쿼리에서 평가가 지연될 수 있음을 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-169">When you use a query expression, you must remember that the query is subject to lazy evaluation.</span></span> <span data-ttu-id="bfbee-170">따라서 데이터베이스는 각 쿼리 식 다음에 lambda 식 블록에서처럼 연결된 평가 중에 읽을 수 있도록 계속 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-170">Therefore, the database is still open for reading during any chained evaluations, such as in the lambda expression blocks after each query expression.</span></span> <span data-ttu-id="bfbee-171">명시적 또는 묵시적으로 트랜잭션을 사용하는 데이터베이스 작업은 읽기 작업이 완료된 후에 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-171">Any database operation that explicitly or implicitly uses a transaction must occur after the read operations have completed.</span></span>


## <a name="next-steps"></a><span data-ttu-id="bfbee-172">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bfbee-172">Next Steps</span></span>
<span data-ttu-id="bfbee-173">사용할 수 있는 쿼리 연산자를 검토 하 여 다른 쿼리 옵션을 탐색할 [쿼리 식은](../../language-reference/query-expressions.md)도 검토 하 고는 [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) 어떤 기능을 사용할 수를 이해 하려면 이 형식 공급자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbee-173">Explore other query options by reviewing the query operators available in [Query Expressions](../../language-reference/query-expressions.md), and also review the [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) to understand what functionality is available to you when you use this type provider.</span></span>


## <a name="see-also"></a><span data-ttu-id="bfbee-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfbee-174">See Also</span></span>
[<span data-ttu-id="bfbee-175">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="bfbee-175">Type Providers</span></span>](index.md)  
[<span data-ttu-id="bfbee-176">SqlEntityConnection 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="bfbee-176">SqlEntityConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)  
[<span data-ttu-id="bfbee-177">연습: EDMX 스키마 파일에서 F # 형식 생성</span><span class="sxs-lookup"><span data-stu-id="bfbee-177">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>](generating-fsharp-types-from-edmx.md)  
[<span data-ttu-id="bfbee-178">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="bfbee-178">ADO.NET Entity Framework</span></span>](https://msdn.microsoft.com/library/bb399572)  
[<span data-ttu-id="bfbee-179">.edmx 파일 개요</span><span class="sxs-lookup"><span data-stu-id="bfbee-179">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
[<span data-ttu-id="bfbee-180">EDM 생성기 &#40;EdmGen.exe&#41;</span><span class="sxs-lookup"><span data-stu-id="bfbee-180">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)  
