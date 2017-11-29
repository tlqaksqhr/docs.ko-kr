---
title: "연습: 형식 공급자를 사용하여 SQL Database에 액세스(F#)"
description: "F # 3.0에서 SqlDataConnection (LINQ to SQL) 형식 공급자를 사용 하 여 라이브 데이터베이스에 연결 하는 경우 SQL 데이터베이스에 대 한 형식을 생성 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: c99afc1121b4f0d6d05ef82681a32437ede06e42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a><span data-ttu-id="47e3b-104">연습: 형식 공급자를 사용하여 SQL Database에 액세스</span><span class="sxs-lookup"><span data-stu-id="47e3b-104">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="47e3b-105">이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="47e3b-106">최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](http://fsharp.github.io/FSharp.Data/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47e3b-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="47e3b-107">API 참조 링크 MSDN을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="47e3b-108">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="47e3b-109">이 연습에서는 데이터베이스에 라이브 연결을 사용 하는 경우 SQL 데이터베이스에서 데이터에 대 한 형식을 생성 하려면 F # 3.0에서 사용할 수 있는 SqlDataConnection (LINQ to SQL) 형식 공급자를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-109">This walkthrough explains how to use the SqlDataConnection (LINQ to SQL) type provider that is available in F# 3.0 to generate types for data in a SQL database when you have a live connection to a database.</span></span> <span data-ttu-id="47e3b-110">참조 데이터베이스에 라이브 연결 되어 있지 않으면 LINQ to SQL 스키마 파일 (DBML 파일) 권한이 표시 되지만 [연습: DBML 파일에서 생성 F # 형식](generating-fsharp-types-from-dbml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-110">If you do not have a live connection to a database, but you do have a LINQ to SQL schema file (DBML file), see [Walkthrough: Generating F# Types from a DBML File](generating-fsharp-types-from-dbml.md).</span></span>

<span data-ttu-id="47e3b-111">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-111">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="47e3b-112">이 연습을 완료 하려면이 순서 대로 이러한 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-112">These tasks must be performed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="47e3b-113">테스트 데이터베이스를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-113">Preparing a test database</span></span>

- <span data-ttu-id="47e3b-114">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="47e3b-114">Creating the project</span></span>

- <span data-ttu-id="47e3b-115">형식 공급자를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-115">Setting up a type provider</span></span>

- <span data-ttu-id="47e3b-116">데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="47e3b-116">Querying the data</span></span>

- <span data-ttu-id="47e3b-117">Nullable 필드 작업</span><span class="sxs-lookup"><span data-stu-id="47e3b-117">Working with nullable fields</span></span>

- <span data-ttu-id="47e3b-118">저장 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="47e3b-118">Calling a stored procedure</span></span>

- <span data-ttu-id="47e3b-119">데이터베이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="47e3b-119">Updating the database</span></span>

- <span data-ttu-id="47e3b-120">Transact SQL 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-120">Executing Transact-SQL code</span></span>

- <span data-ttu-id="47e3b-121">전체 데이터 컨텍스트를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="47e3b-121">Using the full data context</span></span>

- <span data-ttu-id="47e3b-122">데이터 삭제</span><span class="sxs-lookup"><span data-stu-id="47e3b-122">Deleting data</span></span>

- <span data-ttu-id="47e3b-123">필요에 따라 테스트 데이터베이스를 만듭니다</span><span class="sxs-lookup"><span data-stu-id="47e3b-123">Create a test database (as needed)</span></span>

## <a name="preparing-a-test-database"></a><span data-ttu-id="47e3b-124">테스트 데이터베이스를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-124">Preparing a Test Database</span></span>
<span data-ttu-id="47e3b-125">SQL Server를 실행 하는 서버에서 테스트 목적으로 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-125">On a server that's running SQL Server, create a database for testing purposes.</span></span> <span data-ttu-id="47e3b-126">데이터베이스를 사용할 수 섹션에서이 페이지의 맨 아래에 스크립트를 만들 [테스트 데이터베이스를 만드는](#creating-a-test-database) 에이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-126">You can use the database create script at the bottom of this page in the section [Creating a test database](#creating-a-test-database) to do this.</span></span>


#### <a name="to-prepare-a-test-database"></a><span data-ttu-id="47e3b-127">테스트 데이터베이스를 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-127">To prepare a test database</span></span>

<span data-ttu-id="47e3b-128">MyDatabase 작성 스크립트를 실행 하려면 열고는 **보기** 메뉴를 선택한 후 **SQL Server 개체 탐색기** 하거나 선택 하 고 Ctrl +\, Ctrl + S 키.</span><span class="sxs-lookup"><span data-stu-id="47e3b-128">To run the MyDatabase Create Script, open the **View** menu, and then choose **SQL Server Object Explorer** or choose the Ctrl+\, Ctrl+S keys.</span></span> <span data-ttu-id="47e3b-129">**SQL Server 개체 탐색기** 창에서 적절 한 인스턴스에 대 한 바로 가기 메뉴를 열고, 선택 **새 쿼리**이 페이지의 맨 아래에 스크립트를 복사 하 고 다음 스크립트를 편집기에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-129">In **SQL Server Object Explorer** window, open the shortcut menu for the appropriate instance, choose **New Query**, copy the script at the bottom of this page, and then paste the script into the editor.</span></span> <span data-ttu-id="47e3b-130">SQL 스크립트를 실행 하려면 삼각형 기호로 도구 모음 아이콘을 선택 하거나 Ctrl + Q 키를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-130">To run the SQL script, choose the toolbar icon with the triangular symbol, or choose the Ctrl+Q keys.</span></span> <span data-ttu-id="47e3b-131">에 대 한 자세한 내용은 **SQL Server 개체 탐색기**, 참조 [연결 된 데이터베이스 개발](https://msdn.microsoft.com/library/hh272679(VS.103).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-131">For more information about **SQL Server Object Explorer**, see [Connected Database Development](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).</span></span>


## <a name="creating-the-project"></a><span data-ttu-id="47e3b-132">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="47e3b-132">Creating the project</span></span>
<span data-ttu-id="47e3b-133">다음으로, F # 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-133">Next, you create an F# application project.</span></span>


#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="47e3b-134">프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-134">To create and set up the project</span></span>

1. <span data-ttu-id="47e3b-135">F # 응용 프로그램 프로젝트를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-135">Create a new F# Application project.</span></span>

2. <span data-ttu-id="47e3b-136">에 대 한 참조를 추가 [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3),으로 `System.Data`, 및 `System.Data.Linq`합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-136">Add references to [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), as well as `System.Data`, and `System.Data.Linq`.</span></span>

3. <span data-ttu-id="47e3b-137">F # 코드 파일 Program.fs의 맨 위에 다음 코드 줄을 추가 하 여 적절 한 네임 스페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-137">Open the appropriate namespaces by adding the following lines of code to the top of your F# code file Program.fs.</span></span>

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. <span data-ttu-id="47e3b-138">대부분의 F # 프로그램와 마찬가지로 컴파일된 프로그램으로이 연습에서 코드를 실행할 수 있습니다 또는 스크립트로 대화형으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-138">As with most F# programs, you can execute the code in this walkthrough as a compiled program, or you can run it interactively as a script.</span></span> <span data-ttu-id="47e3b-139">스크립트를 사용 하는 것을 선호 하는 경우 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 **새 항목 추가**, F # 스크립트 파일을 추가 하 고 각 단계에는 스크립트에 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-139">If you prefer to use scripts, open the shortcut menu for the project node, select **Add New Item**, add an F# script file, and add the code in each step to the script.</span></span> <span data-ttu-id="47e3b-140">어셈블리 참조를 로드할 파일 맨 위에 있는 다음 줄을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-140">You will need to add the following lines at the top of the file to load the assembly references.</span></span>

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  <span data-ttu-id="47e3b-141">그런 다음 추가 하 고 F # Interactive에서 실행 하려면 Alt + Enter를 눌러 코드의 각 블록을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-141">You can then select each block of code as you add it and press Alt+Enter to run it in F# Interactive.</span></span>

## <a name="setting-up-a-type-provider"></a><span data-ttu-id="47e3b-142">형식 공급자를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-142">Setting up a type provider</span></span>
<span data-ttu-id="47e3b-143">이 단계에서는 데이터베이스 스키마에 대 한 형식 공급자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-143">In this step, you create a type provider for your database schema.</span></span>


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a><span data-ttu-id="47e3b-144">데이터베이스를 직접 연결에서 형식 공급자를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-144">To set up the type provider from a direct database connection</span></span>

<span data-ttu-id="47e3b-145">형식 공급자를 사용 하 여 SQL 데이터베이스를 쿼리 하는 데 사용할 수 있는 형식을 만드는 데 필요한 코드의 두 가지 중요 한 줄 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-145">There are two critical lines of code that you need in order to create the types that you can use to query a SQL database using the type provider.</span></span> <span data-ttu-id="47e3b-146">첫째, 형식 공급자를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-146">First, you instantiate the type provider.</span></span> <span data-ttu-id="47e3b-147">이렇게 하려면 형식 약어에 대 한 모양을 만들는 `SqlDataConnection` 정적 제네릭 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-147">To do this, create what looks like a type abbreviation for a `SqlDataConnection` with a static generic parameter.</span></span> <span data-ttu-id="47e3b-148">`SqlDataConnection`SQL 형식 공급자는 및와 혼동 해서는 안 `SqlConnection` 즉 입력 ADO.NET 프로그래밍에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-148">`SqlDataConnection` is a SQL type provider, and should not be confused with `SqlConnection` type that is used in ADO.NET programming.</span></span> <span data-ttu-id="47e3b-149">형식 공급자를 호출할 수,에 연결 하려는 데이터베이스 있고 연결 문자열을 사용할 경우 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-149">If you have a database that you want to connect to, and have a connection string, use the following code to invoke the type provider.</span></span> <span data-ttu-id="47e3b-150">제공 된 예에서는 문자열에 대 한 사용자 지정 연결 문자열을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-150">Substitute your own connection string for the example string given.</span></span> <span data-ttu-id="47e3b-151">예를 들어 MYSERVER 및 데이터베이스 인스턴스는 인스턴스, 데이터베이스 이름, MyDatabase 이며 데이터베이스를 선택한 연결 문자열에 액세스 하려면 Windows 인증을 사용 하려면 서버도 되는 경우 다음 예제 코드에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-151">For example, if your server is MYSERVER and the database instance is INSTANCE, the database name is MyDatabase, and you want to use Windows Authentication to access the database, then the connection string would be as given in the following example code.</span></span>

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

<span data-ttu-id="47e3b-152">이제는 형식 `dbSchema`, 데이터베이스 테이블을 표시 하는 모든 생성 된 형식을 포함 하는 부모 형식인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-152">Now you have a type, `dbSchema`, which is a parent type that contains all the generated types that represent database tables.</span></span> <span data-ttu-id="47e3b-153">갖게 되는 개체로, `db`, 데이터베이스의 모든 테이블의 구성원으로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-153">You also have an object, `db`, which has as its members all the tables in the database.</span></span> <span data-ttu-id="47e3b-154">테이블 이름 속성에는 이러한 속성의 형식이 F # 컴파일러에 의해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-154">The table names are properties, and the type of these properties is generated by the F# compiler.</span></span> <span data-ttu-id="47e3b-155">형식 자체에서 중첩 된 형식으로 표시 `dbSchema.ServiceTypes`합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-155">The types themselves appear as nested types under `dbSchema.ServiceTypes`.</span></span> <span data-ttu-id="47e3b-156">따라서 이러한 테이블의 행에 대해 검색 된 모든 데이터는 해당 테이블에 대해 생성 된 적절 한 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-156">Therefore, any data retrieved for rows of these tables is an instance of the appropriate type that was generated for that table.</span></span> <span data-ttu-id="47e3b-157">형식의 이름은 `ServiceTypes.Table1`합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-157">The name of the type is `ServiceTypes.Table1`.</span></span>

<span data-ttu-id="47e3b-158">F # 언어 SQL 쿼리로 쿼리를 해석 하는 방법을 익히는 감사를 설정 하는 줄 검토는 `Log` 데이터 컨텍스트 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-158">To familiarize yourself with how the F# language interprets queries into SQL queries, review the line that sets the `Log` property on the data context.</span></span>

<span data-ttu-id="47e3b-159">형식 공급자에서 만든 형식을 탐색 하려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-159">To further explore the types created by the type provider, add the following code.</span></span>

```fsharp
let table1 = db.Table1
```

<span data-ttu-id="47e3b-160">위로 마우스를 가져가고 `table1` 해당 형식을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-160">Hover over `table1` to see its type.</span></span> <span data-ttu-id="47e3b-161">해당 형식이 `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` 과 같습니다. 제네릭 인수 각 행의 유형이 생성 된 형식 인지 `dbSchema.ServiceTypes.Table1`합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-161">Its type is `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` and the generic argument implies that the type of each row is the generated type, `dbSchema.ServiceTypes.Table1`.</span></span> <span data-ttu-id="47e3b-162">컴파일러는 데이터베이스의 각 테이블에 대해 비슷한 종류를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-162">The compiler creates a similar type for each table in the database.</span></span>

## <a name="querying-the-data"></a><span data-ttu-id="47e3b-163">데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="47e3b-163">Querying the data</span></span>
<span data-ttu-id="47e3b-164">이 단계에서는 F # 쿼리 식을 사용 하 여 쿼리를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-164">In this step, you write a query using F# query expressions.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="47e3b-165">데이터를 쿼리하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-165">To query the data</span></span>

1. <span data-ttu-id="47e3b-166">이제 데이터베이스에서 해당 테이블에 대 한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-166">Now create a query for that table in the database.</span></span> <span data-ttu-id="47e3b-167">다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-167">Add the following code.</span></span>

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  <span data-ttu-id="47e3b-168">단어의 모양을 `query` 비슷한 쿼리 결과를 일반적인 데이터베이스에 변수의 컬렉션을 생성 하는 계산 식의 형식을 쿼리 식 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-168">The appearance of the word `query` indicates that this is a query expression, a type of computation expression that generates a collection of results similar of a typical database query.</span></span> <span data-ttu-id="47e3b-169">쿼리를 가리키면 나타납니다의 인스턴스이면 [Linq.QueryBuilder 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), 쿼리 계산 식 정의 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-169">If you hover over query, you will see that it is an instance of [Linq.QueryBuilder Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), a type that defines the query computation expression.</span></span> <span data-ttu-id="47e3b-170">위로 가져가면 `query1`의 인스턴스이면 나타납니다 `System.Linq.IQueryable`합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-170">If you hover over `query1`, you will see that it is an instance of `System.Linq.IQueryable`.</span></span> <span data-ttu-id="47e3b-171">이름에서 알 수 있듯이 `System.Linq.IQueryable` 쿼리의 결과인 쿼리할 수 있는 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-171">As the name suggests, `System.Linq.IQueryable` represents data that may be queried, not the result of a query.</span></span> <span data-ttu-id="47e3b-172">쿼리 지연 평가 데이터베이스가을 의미 하는 쿼리가 평가 되는 경우 쿼리 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-172">A query is subject to lazy evaluation, which means that the database is only queried when the query is evaluated.</span></span> <span data-ttu-id="47e3b-173">통해 쿼리를 전달 하는 마지막 줄 `Seq.iter`합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-173">The final line passes the query through `Seq.iter`.</span></span> <span data-ttu-id="47e3b-174">쿼리는 열거 가능 하며 시퀀스와 같은 반복 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-174">Queries are enumerable and may be iterated like sequences.</span></span> <span data-ttu-id="47e3b-175">자세한 내용은 참조 [쿼리 식](../../language-reference/query-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-175">For more information, see [Query Expressions](../../language-reference/query-expressions.md).</span></span>

2. <span data-ttu-id="47e3b-176">이제 쿼리에 쿼리 연산자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-176">Now add a query operator to the query.</span></span> <span data-ttu-id="47e3b-177">더 복잡 한 쿼리를 구성 하는 데 사용할 수 있는 사용 가능한 쿼리 연산자의 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-177">There are a number of query operators available that you can use to construct more complex queries.</span></span> <span data-ttu-id="47e3b-178">또한이 예제에는 쿼리 변수를 제거 하 고 파이프라인 연산자를 대신 사용할 수 있는 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-178">This example also shows that you can eliminate the query variable and use a pipeline operator instead.</span></span>

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. <span data-ttu-id="47e3b-179">두 테이블의 조인으로 더 복잡 한 쿼리를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-179">Add a more complex query with a join of two tables.</span></span>

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. <span data-ttu-id="47e3b-180">실제 코드에 쿼리에 매개 변수는 일반적으로 값 또는 변수, 하지 컴파일 시간 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-180">In real-world code, the parameters in your query are usually values or variables, not compile-time constants.</span></span> <span data-ttu-id="47e3b-181">매개 변수를 사용 하 고 다음 값 10 해당 함수를 호출 하는 함수에는 쿼리를 래핑하는 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-181">Add the following code that wraps a query in a function that takes a parameter, and then calls that function with the value 10.</span></span>

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a><span data-ttu-id="47e3b-182">Nullable 필드 작업</span><span class="sxs-lookup"><span data-stu-id="47e3b-182">Working with nullable fields</span></span>
<span data-ttu-id="47e3b-183">데이터베이스에서 필드 종종 null 값을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-183">In databases, fields often allow null values.</span></span> <span data-ttu-id="47e3b-184">.NET 형식 시스템에서 null을 허용 하는 형식에 없기 때문에 가능한 값으로 null 데이터에 대 한 일반 숫자 데이터 형식과 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-184">In the .NET type system, you cannot use the ordinary numerical data types for data that allows nulls because those types do not have null as a possible value.</span></span> <span data-ttu-id="47e3b-185">따라서 이러한 값의 인스턴스로 표현 된 `System.Nullable` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-185">Therefore, these values are represented by instances of `System.Nullable` type.</span></span> <span data-ttu-id="47e3b-186">필드의 이름으로 직접 이러한 필드의 값에 액세스 하는 대신 추가 단계를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-186">Instead of accessing the value of such fields directly with the name of the field, you need to add some extra steps.</span></span> <span data-ttu-id="47e3b-187">사용할 수는 `System.Nullable.Value` nullable 형식의 기본 값에 액세스 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-187">You can use the `System.Nullable.Value` property to access the underlying value of a nullable type.</span></span> <span data-ttu-id="47e3b-188">`System.Nullable.Value` 속성 개체가 값 대신 null 인 경우 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-188">The `System.Nullable.Value` property throws an exception if the object is null rather than having a value.</span></span> <span data-ttu-id="47e3b-189">사용할 수는 `System.Nullable.HasValue` 부울 메서드는 값이 존재 하는지 확인 하거나 사용 하 여를 `System.Nullable.GetValueOrDefault()` 모든 경우에에서는 실제 값을 갖도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-189">You can use the `System.Nullable.HasValue` Boolean method to determine if a value exists, or use `System.Nullable.GetValueOrDefault()` to ensure that you have an actual value in all cases.</span></span> <span data-ttu-id="47e3b-190">사용 하는 경우 `System.Nullable.GetValueOrDefault()` 데이터베이스에는 null이 고 다음 대체 될 정수 계열 형식의 0 또는 0.0 부동 소수점 형식 문자열 형식에 대 한 빈 문자열 같은 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-190">If you use `System.Nullable.GetValueOrDefault()` and there is a null in the database, then it is replaced with a value such as an empty string for string types, 0 for integral types or 0.0 for floating point types.</span></span>

<span data-ttu-id="47e3b-191">Null 허용 값에 대해 같음 테스트 또는 비교를 수행 해야 하는 경우는 `where` 쿼리에서 절에 null 허용 연산자를 사용할 수 있습니다는 [Linq.NullableOperators 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-191">When you need to perform equality tests or comparisons on nullable values in a `where` clause in a query, you can use the nullable operators found in the [Linq.NullableOperators Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d).</span></span> <span data-ttu-id="47e3b-192">일반 비교 연산자 처럼 이들은 `=`, `>`, `<=`등의 물음표가 나타납니다 연산자의 오른쪽 또는 왼쪽에 null을 허용 하는 값이 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-192">These are like the regular comparison operators `=`, `>`, `<=`, and so on, except that a question mark appears on the left or right of the operator where the nullable values are.</span></span> <span data-ttu-id="47e3b-193">예를 들어 연산자 `>?` 는 큰-연산자 오른쪽의 값이 null을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-193">For example, the operator `>?` is a greater-than operator with a nullable value on the right.</span></span> <span data-ttu-id="47e3b-194">이러한 연산자는 작동 방식은 식의 어느 쪽이 null 이면 식으로 평가 되었음이 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-194">The way these operators work is that if either side of the expression is null, the expression evaluates to `false`.</span></span> <span data-ttu-id="47e3b-195">에 `where` 절, 일반적으로 의미는 null 필드가 포함 된 행을 선택 하지 않으며 쿼리 결과에 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-195">In a `where` clause, this generally means that the rows that contain null fields are not selected and not returned in the query results.</span></span>


#### <a name="to-work-with-nullable-fields"></a><span data-ttu-id="47e3b-196">Nullable 필드를 작성 하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-196">To work with nullable fields</span></span>

<span data-ttu-id="47e3b-197">다음 코드와 작업에 null 허용 값이 있습니다. 가정 **TestData1** null을 허용 하는 정수 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-197">The following code shows working with nullable values; assume that **TestData1** is an integer field that allows nulls.</span></span>

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="47e3b-198">저장 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="47e3b-198">Calling a stored procedure</span></span>
<span data-ttu-id="47e3b-199">F #에서 데이터베이스의 모든 저장된 프로시저를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-199">Any stored procedures on the database can be called from F#.</span></span> <span data-ttu-id="47e3b-200">Static 매개 변수를 설정 해야 `StoredProcedures` 를 `true` 의 형식 공급자 인스턴스화에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-200">You must set the static parameter `StoredProcedures` to `true` in the type provider instantiation.</span></span> <span data-ttu-id="47e3b-201">형식 공급자 `SqlDataConnection` 생성 되는 형식을 구성 하는 데 사용할 수 있는 몇 가지 정적 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-201">The type provider `SqlDataConnection` contains several static methods that you can use to configure the types that are generated.</span></span> <span data-ttu-id="47e3b-202">이러한 대 한 전체 설명은 참조 하세요. [SqlDataConnection 형식 공급자](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-202">For a complete description of these, see [SqlDataConnection Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d).</span></span> <span data-ttu-id="47e3b-203">데이터 컨텍스트 형식에 대해 메서드를 각 저장된 프로시저에 대해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-203">A method on the data context type is generated for each stored procedure.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="47e3b-204">저장 프로시저를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-204">To call a stored procedure</span></span>

<span data-ttu-id="47e3b-205">적절 한 전달 해야 하는 경우는 null을 허용 하는 매개 변수를 사용 하는 저장된 프로시저, `System.Nullable` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-205">If the stored procedures takes parameters that are nullable, you need to pass an appropriate `System.Nullable` value.</span></span> <span data-ttu-id="47e3b-206">스칼라 또는 테이블을 반환 하는 저장된 프로시저 메서드의 반환 값은 `System.Data.Linq.ISingleResult`, 반환 된 데이터에 액세스할 수 있도록 하는 속성을 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-206">The return value of a stored procedure method that returns a scalar or a table is `System.Data.Linq.ISingleResult`, which contains properties that enable you to access the returned data.</span></span> <span data-ttu-id="47e3b-207">에 대 한 형식 인수 `System.Data.Linq.ISingleResult` 특정 절차에 따라 달라 지 며 형식 공급자가 생성 된 형식 중 하나 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-207">The type argument for `System.Data.Linq.ISingleResult` depends on the specific procedure and is also one of the types that the type provider generates.</span></span> <span data-ttu-id="47e3b-208">라는 이름의 저장된 프로시저에 대 한 `Procedure1`, 형식이 `Procedure1Result`합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-208">For a stored procedure named `Procedure1`, the type is `Procedure1Result`.</span></span> <span data-ttu-id="47e3b-209">형식 `Procedure1Result` 이름이 포함 된 열에서 반환 된 테이블 또는 스칼라 값을 반환 하는 저장된 프로시저에 대 한 반환 값을 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-209">The type `Procedure1Result` contains the names of the columns in a returned table, or, for a stored procedure that returns a scalar value, it represents the return value.</span></span>

<span data-ttu-id="47e3b-210">다음 코드는 프로시저 라고 가정 `Procedure1` 에서는 두 개의 nullable 정수 매개 변수로 데이터베이스 라는 열을 반환 하는 쿼리 실행 `TestData1`, 정수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-210">The following code assumes that there is a procedure `Procedure1` on the database that takes two nullable integers as parameters, runs a query that returns a column named `TestData1`, and returns an integer.</span></span>

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a><span data-ttu-id="47e3b-211">데이터베이스 업데이트</span><span class="sxs-lookup"><span data-stu-id="47e3b-211">Updating the database</span></span>
<span data-ttu-id="47e3b-212">LINQ DataContext 형식을 보다 쉽게에 완벽 하 게 형식화 된 적절 하 게 생성된 된 형식으로의 트랜잭션된 데이터베이스 업데이트를 수행할 수 있도록 하는 메서드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-212">The LINQ DataContext type contains methods that make it easier to perform transacted database updates in a fully typed fashion with the generated types.</span></span>


#### <a name="to-update-the-database"></a><span data-ttu-id="47e3b-213">데이터베이스를 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-213">To update the database</span></span>

1. <span data-ttu-id="47e3b-214">다음 코드에서는 행이 여러 데이터베이스에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-214">In the following code, several rows are added to the database.</span></span> <span data-ttu-id="47e3b-215">행만 추가 하는 경우 사용할 수 있습니다 `System.Data.Linq.Table.InsertOnSubmit()` 새 행을 추가 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-215">If you are only adding a row, you can use `System.Data.Linq.Table.InsertOnSubmit()` to specify the new row to add.</span></span> <span data-ttu-id="47e3b-216">여러 행을 삽입 하는 경우 호출 및 컬렉션에 저장 해야 `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-216">If you are inserting multiple rows, you should put them into a collection and call `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`.</span></span> <span data-ttu-id="47e3b-217">이러한 방법 중 하나를 호출 하는 경우 데이터베이스 즉시 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-217">When you call either of these methods, the database is not immediately changed.</span></span> <span data-ttu-id="47e3b-218">호출 해야 `System.Data.Linq.DataContext.SubmitChanges` 실제로 변경 내용을 커밋 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-218">You must call `System.Data.Linq.DataContext.SubmitChanges` to actually commit the changes.</span></span> <span data-ttu-id="47e3b-219">기본적으로 호출 하기 전에 수행 하는 모든 `System.Data.Linq.DataContext.SubmitChanges` 는 암시적으로 동일한 트랜잭션의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-219">By default, everything that you do before you call `System.Data.Linq.DataContext.SubmitChanges` is implicitly part of the same transaction.</span></span>

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. <span data-ttu-id="47e3b-220">이제는 삭제 작업을 호출 하 여 행을 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-220">Now clean up the rows by calling a delete operation.</span></span>

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a><span data-ttu-id="47e3b-221">Transact SQL 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-221">Executing Transact-SQL code</span></span>
<span data-ttu-id="47e3b-222">TRANSACT-SQL를 사용 하 여 직접 지정할 수도 있습니다는 `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` 에서 메서드는 `DataContext` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-222">You can also specify Transact-SQL directly by using the `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` method on the `DataContext` class.</span></span>


#### <a name="to-execute-custom-sql-commands"></a><span data-ttu-id="47e3b-223">사용자 지정 SQL 명령을 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-223">To execute custom SQL commands</span></span>

<span data-ttu-id="47e3b-224">다음 코드를 테이블에 레코드를 삽입 하 고 테이블에서 레코드를 삭제 하는 SQL 명령을 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-224">The following code shows how to send SQL commands to insert a record into a table and also to delete a record from a table.</span></span>

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a><span data-ttu-id="47e3b-225">전체 데이터 컨텍스트를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="47e3b-225">Using the full data context</span></span>
<span data-ttu-id="47e3b-226">앞의 예에서 `GetDataContext` 메서드를 섞어 가져오는 데는 *단순화 된 데이터 컨텍스트* 데이터베이스 스키마에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-226">In the previous examples, the `GetDataContext` method was used to get what is called the *simplified data context* for the database schema.</span></span> <span data-ttu-id="47e3b-227">단순화 된 데이터 컨텍스트는 보다 쉽게 사용할 수 있는 많은 멤버 되지 않으므로 쿼리를 생성 하는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-227">The simplified data context is easier to use when you are constructing queries because there are not as many members available.</span></span> <span data-ttu-id="47e3b-228">따라서 IntelliSense에 속성을 검색할 때 테이블 및 저장된 프로시저와 같은 데이터베이스 구조에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-228">Therefore, when you browse the properties in IntelliSense, you can focus on the database structure, such as the tables and stored procedures.</span></span> <span data-ttu-id="47e3b-229">그러나 단순화 된 데이터 컨텍스트를 수행할 수 있는 작업에 대 한 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-229">However, there is a limit to what you can do with the simplified data context.</span></span> <span data-ttu-id="47e3b-230">다른 작업을 수행 하는 기능을 제공 하는 전체 데이터 컨텍스트.</span><span class="sxs-lookup"><span data-stu-id="47e3b-230">A full data context that provides the ability to perform other actions.</span></span> <span data-ttu-id="47e3b-231">도 사용할 수 있는 64 \는 `ServiceTypes` 의 이름이 고는 *DataContext* 제공 하면 static 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-231">is also available This is located in the `ServiceTypes` and has the name of the *DataContext* static parameter if you provided it.</span></span> <span data-ttu-id="47e3b-232">제공 하지 않은 경우 SqlMetal.exe 다른 입력을 기반으로 데이터 컨텍스트 형식 이름이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-232">If you did not provide it, the name of the data context type is generated for you by SqlMetal.exe based on the other input.</span></span> <span data-ttu-id="47e3b-233">상속 되는 전체 데이터 컨텍스트 `System.Data.Linq.DataContext` 와 같은 ADO.NET 데이터 형식에 대 한 참조를 포함 하는 기본 클래스의 멤버를 노출 하 고는 `Connection` 개체와 같은 메서드 `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` 및 `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` sql에서 쿼리를 작성 하는 데 사용할 수 있는 고도 명시적으로 트랜잭션을 사용 하는 수단입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-233">The full data context inherits from `System.Data.Linq.DataContext` and exposes the members of its base class, including references to ADO.NET data types such as the `Connection` object, methods such as `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` and `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` that you can use to write queries in SQL, and also a means to work with transactions explicitly.</span></span>


#### <a name="to-use-the-full-data-context"></a><span data-ttu-id="47e3b-234">전체 데이터 컨텍스트를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-234">To use the full data context</span></span>

<span data-ttu-id="47e3b-235">다음 코드 전체 데이터 컨텍스트 개체를 가져오고 사용 하 여 데이터베이스에 직접 명령을 실행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-235">The following code demonstrates getting a full data context object and using it to execute commands directly against the database.</span></span> <span data-ttu-id="47e3b-236">이 경우 두 명령은 동일한 트랜잭션의 일부로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-236">In this case, two commands are executed as part of the same transaction.</span></span>

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a><span data-ttu-id="47e3b-237">데이터 삭제</span><span class="sxs-lookup"><span data-stu-id="47e3b-237">Deleting data</span></span>
<span data-ttu-id="47e3b-238">이 단계에서는 데이터 테이블에서 행을 삭제 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-238">This step shows you how to delete rows from a data table.</span></span>


#### <a name="to-delete-rows-from-the-database"></a><span data-ttu-id="47e3b-239">데이터베이스에서 행을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-239">To delete rows from the database</span></span>

<span data-ttu-id="47e3b-240">이제 모든 정리 인스턴스의 지정된 된 테이블에서 행을 삭제 하는 함수를 작성 하 여 행 추가 `System.Data.Linq.Table` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-240">Now, clean up any added rows by writing a function that deletes rows from a specified table, an instance of the `System.Data.Linq.Table` class.</span></span> <span data-ttu-id="47e3b-241">그런 다음, 삭제 하려면 모든 행을 찾는 쿼리를 작성 하 고에 쿼리의 결과 `deleteRows` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-241">Then write a query to find all the rows that you want to delete, and pipe the results of the query into the `deleteRows` function.</span></span> <span data-ttu-id="47e3b-242">이 코드에서는 제공 함수 인수를 부분 적용 하는 기능을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-242">This code takes advantage of the ability to provide partial application of function arguments.</span></span>

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a><span data-ttu-id="47e3b-243">테스트 데이터베이스를 만드는 중</span><span class="sxs-lookup"><span data-stu-id="47e3b-243">Creating a test database</span></span>
<span data-ttu-id="47e3b-244">이 절이이 연습에서는 테스트 데이터베이스를 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-244">This section shows you how to set up the test database to use in this walkthrough.</span></span>

<span data-ttu-id="47e3b-245">참고 어떤 식으로든에서 데이터베이스를 변경 하는 경우 형식 공급자를 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-245">Note that if you alter the database in some way, you will have to reset the type provider.</span></span> <span data-ttu-id="47e3b-246">형식 공급자를 다시 설정 하려면 빌드하거나 형식 공급자를 포함 하는 프로젝트를 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-246">To reset the type provider, rebuild or clean the project that contains the type provider.</span></span>


#### <a name="to-create-the-test-database"></a><span data-ttu-id="47e3b-247">테스트 데이터베이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="47e3b-247">To create the test database</span></span>

1. <span data-ttu-id="47e3b-248">**서버 탐색기**에 대 한 바로 가기 메뉴를 열고는 **데이터 연결** 노드를 선택 하 고 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-248">In **Server Explorer**, open the shortcut menu for the **Data Connections** node, and choose **Add Connection**.</span></span> <span data-ttu-id="47e3b-249">**연결 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-249">The **Add Connection** dialog box appears.</span></span>

2. <span data-ttu-id="47e3b-250">에 **서버 이름** 상자에 관리 권한이 있는 SQL Server 인스턴스의 이름을 지정 하거나 서버에 액세스할 수 없는 경우 (localdb\v11.0)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-250">In the **Server name** box, specify the name of an instance of SQL Server that you have administrative access to, or if you do not have access to a server, specify (localdb\v11.0).</span></span> <span data-ttu-id="47e3b-251">SQL Express LocalDB는 컴퓨터에서 개발 및 테스트에 대 한 간단한 데이터베이스 서버를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-251">SQL Express LocalDB provides a lightweight database server for development and testing on your machine.</span></span> <span data-ttu-id="47e3b-252">새 노드가 만들어집니다 **서버 탐색기** 아래 **데이터 연결**합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-252">A new node is created in **Server Explorer** under **Data Connections**.</span></span> <span data-ttu-id="47e3b-253">LocalDB에 대 한 자세한 내용은 참조 [연습: Visual Studio에서 로컬 데이터베이스 파일 만들기](https://msdn.microsoft.com/library/ms233763.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-253">For more information about LocalDB, see [Walkthrough: Creating a Local Database File in Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).</span></span>

3. <span data-ttu-id="47e3b-254">새 연결 노드의 바로 가기 메뉴를 열고 선택 **새 쿼리**합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-254">Open the shortcut menu for the new connection node, and select **New Query**.</span></span>

4. <span data-ttu-id="47e3b-255">다음 SQL 스크립트를 복사, 쿼리 편집기에 붙여 넣고 다음 선택에서 **Execute** 도구 모음 단추 또는 Ctrl + Shift + E 키를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47e3b-255">Copy the following SQL script, paste it into the query editor, and then choose the **Execute** button on the toolbar or choose the Ctrl+Shift+E keys.</span></span>

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a><span data-ttu-id="47e3b-256">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47e3b-256">See Also</span></span>
[<span data-ttu-id="47e3b-257">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="47e3b-257">Type Providers</span></span>](index.md)

[<span data-ttu-id="47e3b-258">SqlDataConnection 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="47e3b-258">SqlDataConnection Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[<span data-ttu-id="47e3b-259">연습: DBML 파일에서 F # 형식 생성</span><span class="sxs-lookup"><span data-stu-id="47e3b-259">Walkthrough: Generating F# Types from a DBML File</span></span>](generating-fsharp-types-from-dbml.md)

[<span data-ttu-id="47e3b-260">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="47e3b-260">Query Expressions</span></span>](../../language-reference/query-expressions.md)

[<span data-ttu-id="47e3b-261">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="47e3b-261">LINQ to SQL</span></span>](https://msdn.microsoft.com/library/bb386976)

[<span data-ttu-id="47e3b-262">SqlMetal.exe &#40; 코드 생성 도구 &#41;</span><span class="sxs-lookup"><span data-stu-id="47e3b-262">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)
