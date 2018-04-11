---
title: '연습: DBML 파일에서 F# 형식 생성(F#)'
description: '.Dbml 파일에 인코딩된 스키마 정보가 있는 경우 F # 3.0의 데이터베이스에서 데이터에 대 한 F # 형식을 만드는 방법에 알아봅니다.'
keywords: visual f#, f#, 함수형 프로그래밍
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: 3cd8df9becac0d1a8842eb22e2f772eee6307acf
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a><span data-ttu-id="0bd0a-104">연습: DBML 파일에서 F# 형식 생성</span><span class="sxs-lookup"><span data-stu-id="0bd0a-104">Walkthrough: Generating F# Types from a DBML File</span></span>

> [!NOTE]
<span data-ttu-id="0bd0a-105">이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="0bd0a-106">최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](https://fsharp.github.io/FSharp.Data/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="0bd0a-107">API 참조 링크 MSDN을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="0bd0a-108">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="0bd0a-109">이 연습에서는 F # 3.0에 대 한 스키마 정보 인코딩된.dbml 파일에 있는 경우 데이터베이스에서 데이터에 대 한 종류를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-109">This walkthrough for F# 3.0 describes how to create types for data from a database when you have schema information encoded in a .dbml file.</span></span> <span data-ttu-id="0bd0a-110">LINQ to SQL 데이터베이스 스키마를 나타내기 위해이 파일 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-110">LINQ to SQL uses this file format to represent database schema.</span></span> <span data-ttu-id="0bd0a-111">개체 관계 (O/R) 디자이너를 사용 하 여 Visual Studio에서 LINQ to SQL 스키마 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-111">You can generate a LINQ to SQL schema file in Visual Studio by using the Object Relational (O/R) Designer.</span></span> <span data-ttu-id="0bd0a-112">자세한 내용은 참조 [O/R 디자이너 개요](https://msdn.microsoft.com/library/bb384511.aspx) 및 [LINQ to SQL에서에서 코드 생성](../../../../docs/framework/data/adonet/sql/linq/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-112">For more information, see [O/R Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) and [Code Generation in LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>

<span data-ttu-id="0bd0a-113">데이터베이스 태그 언어 (DBML) 형식 공급자를 사용 하면 컴파일 타임에 정적 연결 문자열을 지정 하지 않아도 데이터베이스 스키마에 따라 형식을 사용 하는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-113">The Database Markup Language (DBML) type provider allows you to write code that uses types based on a database schema without requiring you to specify a static connection string at compile time.</span></span> <span data-ttu-id="0bd0a-114">다른 데이터베이스, 다른 자격 증명 또는 응용 프로그램을 개발 하는 데 1 보다 다양 한 연결 문자열은 최종 응용 프로그램과 사용 합니다 가능성에 대 한 허용 해야 하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-114">That can be useful if you need to allow for the possibility that the final application will use a different database, different credentials, or a different connection string than the one you use to develop the application.</span></span> <span data-ttu-id="0bd0a-115">컴파일 타임에 사용할 수 있는 데이터베이스를 직접 연결 하는 경우이 동일한 데이터베이스와 결국 빌드된 응용 프로그램에서 사용할 자격 증명도 SQLDataConnection 형식 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-115">If you have a direct database connection that you can use at compile time and this is the same database and credentials that you will eventually use in your built application, you can also use the SQLDataConnection type provider.</span></span> <span data-ttu-id="0bd0a-116">자세한 내용은 참조 [연습: 형식 공급자를 사용 하 여 SQL 데이터베이스에 액세스](accessing-a-sql-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-116">For more information, see [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>

<span data-ttu-id="0bd0a-117">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-117">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="0bd0a-118">이 연습을 완료 하려면이 순서 대로 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-118">They should be completed in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="0bd0a-119">.Dbml 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="0bd0a-119">Creating a .dbml file</span></span>
<br />

- <span data-ttu-id="0bd0a-120">만들기 및 F # 프로젝트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-120">Creating and setting up an F# project</span></span>
<br />

- <span data-ttu-id="0bd0a-121">형식 공급자를 구성 하 고 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-121">Configuring the type provider and generating the types</span></span>
<br />

- <span data-ttu-id="0bd0a-122">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="0bd0a-122">Querying the database</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="0bd0a-123">전제 조건</span><span class="sxs-lookup"><span data-stu-id="0bd0a-123">Prerequisites</span></span>

## <a name="creating-a-dbml-file"></a><span data-ttu-id="0bd0a-124">.Dbml 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="0bd0a-124">Creating a .dbml file</span></span>
<span data-ttu-id="0bd0a-125">데이터베이스에서 테스트를 없는 경우 아래쪽의 지침에 따라 하나를 만들 [연습: 형식 공급자를 사용 하 여 SQL 데이터베이스에 액세스](accessing-a-sql-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-125">If you do not have a database to test on, create one by following the instructions at the bottom of [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span> <span data-ttu-id="0bd0a-126">다음이 지침을 따를 경우 몇 가지 간단한 테이블 및 저장된 프로시저 SQL Server에 포함 된 MyDatabase 라는 데이터베이스를 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-126">If you follow these instructions, you will create a database called MyDatabase that contains a few simple tables and stored procedures on your SQL Server.</span></span>

<span data-ttu-id="0bd0a-127">.Dbml 파일을 이미 보유 하는 경우 섹션으로 건너뛸 수 있습니다 **만들고는 F # 프로젝트 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-127">If you already have a .dbml file, you can skip to the section, **Create and Set Up an F# Project**.</span></span> <span data-ttu-id="0bd0a-128">그렇지 않으면 기존 SQL 데이터베이스를 지정 하는.dbml 파일을 만들 수 있으며 명령줄을 사용 하 여 SqlMetal.exe 도구.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-128">Otherwise, you can create a .dbml file given an existing SQL database and by using the command-line tool SqlMetal.exe.</span></span>


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a><span data-ttu-id="0bd0a-129">SqlMetal.exe를 사용 하 여.dbml 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="0bd0a-129">To create a .dbml file by using SqlMetal.exe</span></span>

1. <span data-ttu-id="0bd0a-130">열기는 **개발자 명령 프롬프트**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-130">Open a **Developer Command Prompt**.</span></span>
<br />

2. <span data-ttu-id="0bd0a-131">입력 하 여 SqlMetal.exe에 액세스할 수 있는지 확인 하십시오. `SqlMetal.exe /?` 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-131">Ensure that you have access to SqlMetal.exe by entering `SqlMetal.exe /?` at the command prompt.</span></span> <span data-ttu-id="0bd0a-132">SqlMetal.exe 아래에 일반적으로 설치 되는 **Microsoft Sdk** 폴더에 **Program Files** 또는 **Program Files (x86)**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-132">SqlMetal.exe is typically installed under the **Microsoft SDKs** folder in **Program Files** or **Program Files (x86)**.</span></span>
<br />

3. <span data-ttu-id="0bd0a-133">다음 명령줄 옵션으로 SqlMetal.exe를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-133">Run SqlMetal.exe with the following command-line options.</span></span> <span data-ttu-id="0bd0a-134">대신 적절 한 경로 대체 `c:\destpath` .dbml 파일을 만들고 데이터베이스 서버에 대 한 적절 한 값을 삽입 하려면 인스턴스 이름과 데이터베이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-134">Substitute an appropriate path in place of `c:\destpath` to create the .dbml file, and insert appropriate values for the database server, instance name, and database name.</span></span>
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
<span data-ttu-id="0bd0a-135">SqlMetal.exe 권한 문제로 인해 파일을 만드는 데 문제가 있으면 현재 디렉터리에 대 한 쓰기 권한이 있는 폴더로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-135">If SqlMetal.exe has trouble creating the file due to permissions issues, change the current directory to a folder that you have write access to.</span></span>


4. <span data-ttu-id="0bd0a-136">다른 사용 가능한 명령줄 옵션을 살펴볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-136">You can also look at the other available command-line options.</span></span> <span data-ttu-id="0bd0a-137">예를 들어, 보기 및 생성된 된 형식에 포함 된 SQL 함수를 사용할 수 있는 옵션 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-137">For example, there are options you can use if you want views and SQL functions included in the generated types.</span></span> <span data-ttu-id="0bd0a-138">자세한 내용은 참조 [SqlMetal.exe &#40;코드 생성 도구&#41;](https://msdn.microsoft.com/library/bb386987)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-138">For more information, see [SqlMetal.exe &#40;Code Generation Tool&#41;](https://msdn.microsoft.com/library/bb386987).</span></span>
<br />


## <a name="creating-and-setting-up-an-f-project"></a><span data-ttu-id="0bd0a-139">만들기 및 F # 프로젝트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-139">Creating and setting up an F# project</span></span>
<span data-ttu-id="0bd0a-140">이 단계에서는 프로젝트를 만들고 DBML 형식 공급자를 사용 하려면 적절 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-140">In this step, you create a project and add appropriate references to use the DBML type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="0bd0a-141">F# 프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="0bd0a-141">To create and set up an F# project</span></span>

1. <span data-ttu-id="0bd0a-142">새 F # 콘솔 응용 프로그램 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-142">Add a new F# Console Application project to your solution.</span></span>
<br />

2. <span data-ttu-id="0bd0a-143">**솔루션 탐색기**, 바로 가기 메뉴를 열고 **참조**를 선택한 후 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-143">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="0bd0a-144">에 **어셈블리** 영역에서 선택 된 **프레임 워크** 노드를 사용할 수 있는 어셈블리의 목록에서 선택 합니다는 **System.Data** 및 **System.Data.Linq**  어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-144">In the **Assemblies** area, choose the **Framework** node, and then, in the list of available assemblies, choose the **System.Data** and **System.Data.Linq** assemblies.</span></span>
<br />

4. <span data-ttu-id="0bd0a-145">에 **어셈블리** 영역에서 선택 **확장**, 한 다음 사용할 수 있는 어셈블리의 목록에서 선택 **FSharp.Data.TypeProviders**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-145">In the **Assemblies** area, choose **Extensions**, and then, in the list of available assemblies, choose **FSharp.Data.TypeProviders**.</span></span>
<br />

5. <span data-ttu-id="0bd0a-146">선택 된 **확인** 단추를 프로젝트에 이러한 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-146">Choose the **OK** button to add references to these assemblies to your project.</span></span>
<br />

6. <span data-ttu-id="0bd0a-147">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="0bd0a-147">(Optional).</span></span> <span data-ttu-id="0bd0a-148">이전 단계에서 만든.dbml 파일을 복사한 프로젝트에 대 한 기본 폴더에 파일을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-148">Copy the .dbml file that you created in the previous step, and paste the file in the main folder for your project.</span></span> <span data-ttu-id="0bd0a-149">이 폴더는 프로젝트 파일 (.fsproj) 및 코드 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-149">This folder contains the project file (.fsproj) and code files.</span></span> <span data-ttu-id="0bd0a-150">메뉴 모음에서 **프로젝트**, **기존 항목 추가**, 프로젝트에 추가 하려면.dbml 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-150">On the menu bar, choose **Project**, **Add Existing Item**, and then specify the .dbml file to add it to your project.</span></span> <span data-ttu-id="0bd0a-151">이러한 단계를 완료 하는 경우 다음 단계에서 ResolutionFolder static 매개 변수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-151">If you complete these steps, you can omit the ResolutionFolder static parameter in the next step.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="0bd0a-152">형식 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="0bd0a-152">Configuring the type provider</span></span>
<span data-ttu-id="0bd0a-153">이 섹션에서는 형식 공급자를 만들고.dbml 파일에 설명 되어 있는 스키마에서 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-153">In this section, you create a type provider and generate types from the schema that’s described in the .dbml file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a><span data-ttu-id="0bd0a-154">형식 공급자 구성 하는 형식을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-154">To configure the type provider and generate the types</span></span>

- <span data-ttu-id="0bd0a-155">열립니다는 코드를 추가 **TypeProviders** 네임 스페이스를 사용 하려면.dbml 파일에 대 한 형식 공급자를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-155">Add code that opens the **TypeProviders** namespace and instantiates the type provider for the .dbml file that you want to use.</span></span> <span data-ttu-id="0bd0a-156">프로젝트에.dbml 파일을 추가한 경우 ResolutionFolder static 매개 변수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-156">If you added the .dbml file to your project, you can omit the ResolutionFolder static parameter.</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

<span data-ttu-id="0bd0a-157">DataContext 형식의 생성 된 모든 형식에 액세스할 수 있고에서 상속 `System.Data.Linq.DataContext`합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-157">The DataContext type provides access to all the generated types and inherits from `System.Data.Linq.DataContext`.</span></span> <span data-ttu-id="0bd0a-158">DbmlFile 형식 공급자가 설정할 수 있는 다양 한 정적 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-158">The DbmlFile type provider has various static parameters that you can set.</span></span> <span data-ttu-id="0bd0a-159">DataContext 형식에 다른 이름을 지정 하 여 사용할 수는 예를 들어 `DataContext=MyDataContext`합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-159">For example, you can use a different name for the DataContext type by specifying `DataContext=MyDataContext`.</span></span> <span data-ttu-id="0bd0a-160">이 경우 코드에는 다음 예제를 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-160">In that case, your code resembles the following example:</span></span>
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a><span data-ttu-id="0bd0a-161">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="0bd0a-161">Querying the database</span></span>
<span data-ttu-id="0bd0a-162">이 섹션에서는 F # 쿼리 식을 사용 하 여 데이터베이스를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-162">In this section, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="0bd0a-163">데이터를 쿼리하려면</span><span class="sxs-lookup"><span data-stu-id="0bd0a-163">To query the data</span></span>

- <span data-ttu-id="0bd0a-164">데이터베이스를 쿼리 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-164">Add code to query the database.</span></span>
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a><span data-ttu-id="0bd0a-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0bd0a-165">Next Steps</span></span>
<span data-ttu-id="0bd0a-166">다른 쿼리 식을 사용 하 여 또는 데이터베이스 연결에서 데이터 컨텍스트를 가져오고 일반 ADO.NET 데이터 작업을 수행할 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-166">You can proceed to use other query expressions, or get a database connection from the data context and perform normal ADO.NET data operations.</span></span> <span data-ttu-id="0bd0a-167">추가 단계에 대 한 섹션을 참조 "의 데이터 쿼리" 후에 [연습: 형식 공급자를 사용 하 여 SQL 데이터베이스에 액세스](accessing-a-sql-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd0a-167">For additional steps, see the sections after "Query the Data" in [Walkthrough: Accessing a SQL Database by Using Type Providers](accessing-a-sql-database.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="0bd0a-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bd0a-168">See Also</span></span>
[<span data-ttu-id="0bd0a-169">DbmlFile 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="0bd0a-169">DbmlFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="0bd0a-170">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="0bd0a-170">Type Providers</span></span>](index.md)

[<span data-ttu-id="0bd0a-171">연습: 형식 공급자를 사용하여 SQL Database에 액세스</span><span class="sxs-lookup"><span data-stu-id="0bd0a-171">Walkthrough: Accessing a SQL Database by Using Type Providers</span></span>](accessing-a-sql-database.md)

[<span data-ttu-id="0bd0a-172">SqlMetal.exe &#40;코드 생성 도구&#41;</span><span class="sxs-lookup"><span data-stu-id="0bd0a-172">SqlMetal.exe &#40;Code Generation Tool&#41;</span></span>](https://msdn.microsoft.com/library/bb386987)

[<span data-ttu-id="0bd0a-173">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="0bd0a-173">Query Expressions</span></span>](../../language-reference/query-expressions.md)
