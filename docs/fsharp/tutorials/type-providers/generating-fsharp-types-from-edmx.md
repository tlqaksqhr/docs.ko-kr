---
title: "연습: EDMX 스키마 파일에서 F# 형식 생성(F#)"
description: "F #으로 데이터 모델 EDM (엔터티) F # 3.0에서는.edmx 파일에는 스키마가 지정 하는 표시 된 데이터에 대 한 유형을 만드는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 5c59911f5f880493080ef1838bc015045ce4336a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a><span data-ttu-id="fc7bb-104">연습: EDMX 스키마 파일에서 F# 형식 생성</span><span class="sxs-lookup"><span data-stu-id="fc7bb-104">Walkthrough: Generating F# Types from an EDMX Schema File</span></span>

> [!NOTE]
<span data-ttu-id="fc7bb-105">이 가이드는 F # 3.0 용으로 작성 된 하 고 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="fc7bb-106">최신 크로스 플랫폼 형식 공급자에 대해서는 [FSharp.Data](http://fsharp.github.io/FSharp.Data/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-106">See [FSharp.Data](http://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="fc7bb-107">API 참조 링크 MSDN을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="fc7bb-108">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="fc7bb-109">F# 3.0에 대한 이 연습에서는 .edmx 파일에 지정된 스키마인 EDM(엔터티 데이터 모델)으로 표시하는 데이터 형식을 만드는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-109">This walkthrough for F# 3.0 shows you how to create types for data that is represented by the Entity Data Model (EDM), the schema for which is specified in an .edmx file.</span></span> <span data-ttu-id="fc7bb-110">또한 이 연습에서는 EdmxFile 형식 공급자를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-110">This walkthrough also shows how to use the EdmxFile type provider.</span></span> <span data-ttu-id="fc7bb-111">시작하기 전에 SqlEntityConnection 형식 공급자가 보다 적절한 형식 공급자 옵션인지 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-111">Before you begin, consider whether a SqlEntityConnection type provider is a more appropriate type provider option.</span></span> <span data-ttu-id="fc7bb-112">SqlEntityConnection 형식 공급자는 프로젝트 개발 단계 동안 연결할 수 있는 라이브 데이터베이스가 있는 시나리오에 가장 적합하며 컴파일 시간에 연결 문자열을 지정해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-112">The SqlEntityConnection type provider works best for scenarios where you have a live database that you can connect to during the development phase of your project, and you do not mind specifying the connection string at compile time.</span></span> <span data-ttu-id="fc7bb-113">그러나 이 형식 공급자는 EdmxFile 형식 공급자만큼 많은 데이터베이스 기능을 노출하지 않는다는 제한도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-113">However, this type provider is also limited in that it doesn't expose as much database functionality as the EdmxFile type provider.</span></span> <span data-ttu-id="fc7bb-114">또한 엔터티 데이터 모델을 사용하는 데이터베이스 프로젝트에 대한 라이브 데이터베이스 연결이 없는 경우 .edmx 파일을 사용하여 데이터베이스를 코딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-114">Also, if you don't have a live database connection for a database project that uses the Entity Data Model, you can use the .edmx file to code against the database.</span></span> <span data-ttu-id="fc7bb-115">EdmxFile 형식 공급자를 사용하면 F# 컴파일러에서 EdmGen.exe를 실행하여 여기에서 제공하는 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-115">When you use the EdmxFile type provider, the F# compiler runs EdmGen.exe to generate the types that it provides.</span></span>

<span data-ttu-id="fc7bb-116">이 연습에서는 다음 작업을 설명하는데, 연습을 성공적으로 수행하려면 이 순서대로 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-116">This walkthrough illustrates the following tasks, which you must perform in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="fc7bb-117">EDMX 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="fc7bb-117">Creating an EDMX file</span></span>
<br />

- <span data-ttu-id="fc7bb-118">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="fc7bb-118">Creating the project</span></span>
<br />

- <span data-ttu-id="fc7bb-119">엔터티 데이터 모델 연결 문자열 찾기 또는 만들기</span><span class="sxs-lookup"><span data-stu-id="fc7bb-119">Finding or creating the entity data model connection string</span></span>
<br />

- <span data-ttu-id="fc7bb-120">형식 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="fc7bb-120">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="fc7bb-121">데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="fc7bb-121">Querying the data</span></span>
<br />

- <span data-ttu-id="fc7bb-122">저장 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="fc7bb-122">Calling a stored procedure</span></span>
<br />


## <a name="prerequisites"></a><span data-ttu-id="fc7bb-123">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fc7bb-123">Prerequisites</span></span>

## <a name="creating-an-edmx-file"></a><span data-ttu-id="fc7bb-124">EDMX 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="fc7bb-124">Creating an EDMX file</span></span>
<span data-ttu-id="fc7bb-125">EDMX 파일이 이미 있는 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-125">If you already have an EDMX file, you can skip this step.</span></span>


#### <a name="to-create-an-edmx-file"></a><span data-ttu-id="fc7bb-126">EDMX 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="fc7bb-126">To create an EDMX file</span></span>

- <span data-ttu-id="fc7bb-127">EDMX 파일이 없는 경우 단계에서이 연습의 끝에 있는 지침을 따라 수 있습니다 [엔터티 데이터 모델 구성](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-127">If you don't already have an EDMX file, you can follow the instructions at the end of this walkthrough in the step [Configuring the Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).</span></span>
<br />

## <a name="creating-the-project"></a><span data-ttu-id="fc7bb-128">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="fc7bb-128">Creating the project</span></span>
<span data-ttu-id="fc7bb-129">이 단계에서 EDMX 형식 공급자를 사용하려면 프로젝트를 만들고 이 프로젝트에 적절한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-129">In this step, you create a project and add appropriate references to it to use the EDMX type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="fc7bb-130">F# 프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="fc7bb-130">To create and set up an F# project</span></span>

1. <span data-ttu-id="fc7bb-131">이전 프로젝트를 닫고 SchoolEDM이라는 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-131">Close the previous project, create another project, and name it SchoolEDM.</span></span>
<br />

2. <span data-ttu-id="fc7bb-132">**솔루션 탐색기**, 바로 가기 메뉴를 열고 **참조**를 선택한 후 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-132">In **Solution Explorer**, open the shortcut menu for **References**, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="fc7bb-133">에 **어셈블리** 영역에서 선택 된 **프레임 워크** 노드.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-133">In the **Assemblies** area, choose the **Framework** node.</span></span>
<br />

4. <span data-ttu-id="fc7bb-134">사용할 수 있는 어셈블리의 목록에서 선택은 **System.Data.Entity** 및 **System.Data.Linq** 어셈블리를 선택한 후는 **추가** 이러한에 대 한 참조를 추가 하려면 단추 프로젝트에 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-134">In the list of available assemblies, choose the **System.Data.Entity** and **System.Data.Linq** assemblies, and then choose the **Add** button to add references to these assemblies to your project.</span></span>
<br />

5. <span data-ttu-id="fc7bb-135">에 **어셈블리** 영역 선택 하는 **확장** 노드.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-135">In the **Assemblies** area, select the **Extensions** node.</span></span>
<br />

6. <span data-ttu-id="fc7bb-136">사용 가능한 확장명 목록에서 FSharp.Data.TypeProviders 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-136">In the  list of available extensions, add a reference to the FSharp.Data.TypeProviders assembly.</span></span>
<br />

7. <span data-ttu-id="fc7bb-137">다음 코드를 추가하여 적절한 네임스페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-137">Add the following code to open the appropriate namespaces.</span></span>
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="fc7bb-138">엔터티 데이터 모델에 대한 연결 문자열 찾기 또는 만들기</span><span class="sxs-lookup"><span data-stu-id="fc7bb-138">Finding or creating the connection string for the Entity Data Model</span></span>
<span data-ttu-id="fc7bb-139">엔터티 데이터 모델에 대한 연결 문자열(EDMX 연결 문자열)에는 데이터베이스 공급자 연결 문자열뿐 아니라 추가 정보도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-139">The connection string for the Entity Data Model (EDMX connection string) includes not only the connection string for the database provider but also additional information.</span></span> <span data-ttu-id="fc7bb-140">예를 들어, 간단한 SQL Server 데이터베이스에 대한 EDMX 연결 문자열은 다음 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-140">For example, EDMX connection string for a simple SQL Server database resembles the following code.</span></span>

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

<span data-ttu-id="fc7bb-141">EDMX 연결 문자열에 대 한 자세한 내용은 참조 [연결 문자열](https://msdn.microsoft.com/library/ms254494.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-141">For more information about EDMX connection strings, see [Connection Strings](https://msdn.microsoft.com/library/ms254494.aspx).</span></span>


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a><span data-ttu-id="fc7bb-142">엔터티 데이터 모델에 대한 연결 문자열을 찾거나 만들려면</span><span class="sxs-lookup"><span data-stu-id="fc7bb-142">To find or create the connection string for the Entity Data Model</span></span>

1. <span data-ttu-id="fc7bb-143">EDMX 연결 문자열을 직접 생성하는 것은 어려울 수 있으므로 프로그래밍 방식으로 생성하여 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-143">EDMX connection strings can be difficult to generate by hand, so you can save time by generating it programmatically.</span></span> <span data-ttu-id="fc7bb-144">EDMX 연결 문자열을 알고 있는 경우 이 단계를 건너뛰고 다음 단계에서 단순히 해당 연결 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-144">If you know your EDMX connection string, you can bypass this step and simply use that string in the next step.</span></span> <span data-ttu-id="fc7bb-145">그렇지 않으면 다음 코드를 사용하여 사용자가 제공하는 데이터베이스 연결 문자열에서 EDMX 연결 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-145">If not, use the following code to generate the EDMX connection string from a database connection string that you provide.</span></span>
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a><span data-ttu-id="fc7bb-146">형식 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="fc7bb-146">Configuring the type provider</span></span>
<span data-ttu-id="fc7bb-147">이 단계에서는 EDMX 연결 문자열로 형식 공급자를 만들고 구성하며 .edmx 파일에 정의된 스키마에 대해 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-147">In this step, you create and configure the type provider with the EDMX connection string, and you generate types for the schema that's defined in the .edmx file.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="fc7bb-148">형식 공급자를 구성하고 형식을 생성하려면</span><span class="sxs-lookup"><span data-stu-id="fc7bb-148">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="fc7bb-149">이 연습의 첫 번째 단계에서 생성한 .edmx 파일을 프로젝트 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-149">Copy the .edmx file that you generated in the first step of this walkthrough to your project folder.</span></span>
<br />

2. <span data-ttu-id="fc7bb-150">F # 프로젝트의 프로젝트 노드에 대 한 바로 가기 메뉴를 열고 선택 **기존 항목 추가**, 프로젝트에 추가할.edmx 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-150">Open the shortcut menu for the project node in your F# project, choose **Add Existing Item**, and then choose the .edmx file to add it to your project.</span></span>
<br />

3. <span data-ttu-id="fc7bb-151">.edmx 파일의 형식 공급자를 활성화하려면 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-151">Enter the following code to activate the type provider for your .edmx file.</span></span> <span data-ttu-id="fc7bb-152">대체 *서버*\*인스턴스 * SQL Server 이름과 해당 인스턴스를 실행 하 고이 연습에는 첫 번째 단계에서.edmx 파일의 이름을 사용 하는 서버의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-152">Replace *Server*\*Instance* with the name of your server that's running SQL Server and the name of your instance, and use the name of your .edmx file from the first step in this walkthrough.</span></span>
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a><span data-ttu-id="fc7bb-153">데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="fc7bb-153">Querying the data</span></span>
<span data-ttu-id="fc7bb-154">이 단계에서는 F# 쿼리 식을 사용하여 데이터베이스를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-154">In this step, you use F# query expressions to query the database.</span></span>


#### <a name="to-query-the-data"></a><span data-ttu-id="fc7bb-155">데이터를 쿼리하려면</span><span class="sxs-lookup"><span data-stu-id="fc7bb-155">To query the data</span></span>

- <span data-ttu-id="fc7bb-156">엔터티 데이터 모델의 데이터를 쿼리하려면 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-156">Enter the following code to query the data in the entity data model.</span></span>
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a><span data-ttu-id="fc7bb-157">저장 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="fc7bb-157">Calling a stored procedure</span></span>
<span data-ttu-id="fc7bb-158">EDMX 형식 공급자를 사용하여 저장 프로시저를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-158">You can call stored procedures by using the EDMX type provider.</span></span> <span data-ttu-id="fc7bb-159">다음 절차에서 School 데이터베이스 저장된 프로시저를 포함 **UpdatePerson**, 새 값 열에 대 한 레코드를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-159">In the following procedure, the School database contains a stored procedure, **UpdatePerson**, which updates a record, given new values for the columns.</span></span> <span data-ttu-id="fc7bb-160">DataContext 형식의 메서드로 노출되기 때문에 이 저장된 프로시저를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-160">You can use this stored procedure because it's exposed as a method on the DataContext type.</span></span>


#### <a name="to-call-a-stored-procedure"></a><span data-ttu-id="fc7bb-161">저장 프로시저를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="fc7bb-161">To call a stored procedure</span></span>

- <span data-ttu-id="fc7bb-162">다음 코드를 추가하여 레코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-162">Add the following code to update records.</span></span>
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

<span data-ttu-id="fc7bb-163">성공한다면 결과는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-163">The result is 1 if you succeed.</span></span> <span data-ttu-id="fc7bb-164">다음에 유의 **exactlyOne** 반환 되 고, 그렇지 않으면은 한 결과만, 예외가 throw 되는 쿼리 식에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-164">Notice that **exactlyOne** is used in the query expression to ensure that only one result is returned; otherwise, an exception is thrown.</span></span> <span data-ttu-id="fc7bb-165">또한 null 허용 값을 보다 쉽게 작업할 수 있습니다 사용할 간단한 **nullable** 일반 값에서 null 허용 값을 만드는 데이 코드에 정의 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-165">Also, to work with nullable values more easily, you can use the simple **nullable** function that's defined in this code to create a nullable value out of an ordinary value.</span></span>

<br />

## <a name="configuring-the-entity-data-model"></a><span data-ttu-id="fc7bb-166">엔터티 데이터 모델 구성</span><span class="sxs-lookup"><span data-stu-id="fc7bb-166">Configuring the Entity Data Model</span></span>
<span data-ttu-id="fc7bb-167">데이터베이스에서 전체 엔터티 데이터 모델을 생성하는 방법을 알고 싶고 테스트할 데이터베이스가 없는 경우에만 이 절차를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-167">You should complete this procedure only if you want to know how to generate a full Entity Data Model from a database and you don't have a database with which to test.</span></span>


#### <a name="to-configure-the-entity-data-model"></a><span data-ttu-id="fc7bb-168">엔터티 데이터 모델을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="fc7bb-168">To configure the Entity Data Model</span></span>

1. <span data-ttu-id="fc7bb-169">메뉴 모음에서 **SQL**, **TRANSACT-SQL 편집기**, **새 쿼리** 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-169">On the menu bar, choose **SQL**, **Transact-SQL Editor**, **New Query** to create a database.</span></span> <span data-ttu-id="fc7bb-170">메시지가 나타나면 데이터베이스 서버 및 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-170">If prompted, specify your database server and instance.</span></span>
<br />

2. <span data-ttu-id="fc7bb-171">에 설명 된 대로 학생 데이터베이스가 생성 하는 데이터베이스 스크립트의 내용을 복사한는 [Entity Framework 설명서](http://msdn.microsoft.com/data/JJ614587.aspx) 데이터 개발자 센터에서.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-171">Copy and paste the contents of the database script that creates the Student database, as described in the [Entity Framework documentation](http://msdn.microsoft.com/data/JJ614587.aspx) in the Data Developer Center.</span></span>
<br />

3. <span data-ttu-id="fc7bb-172">삼각형 기호 있는 도구 모음 단추를 선택 하거나 Ctrl + Q 키를 선택 하 여 SQL 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-172">Run the SQL script by choosing the toolbar button with the triangle symbol or choosing the Ctrl+Q keys.</span></span>
<br />

4. <span data-ttu-id="fc7bb-173">**서버 탐색기**, 바로 가기 메뉴를 열고 **데이터 연결**, 선택 **연결 추가**, 인스턴스 이름의 이름 데이터베이스 서버의 이름을 입력 합니다 및 School 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-173">In **Server Explorer**, open the shortcut menu for **Data Connections**, choose **Add Connection**, and then enter the name of the database server, the name of the instance name, and the School database.</span></span>
<br />

5. <span data-ttu-id="fc7bb-174">C# 또는 Visual Basic 콘솔 응용 프로그램 프로젝트 만들기, 해당 바로 가기 메뉴를 열고, 선택 **새 항목 추가**를 선택한 후 **ADO.NET 엔터티 데이터 모델**합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-174">Create a C# or Visual Basic Console Application project, open its shortcut menu, choose **Add New Item**, and then choose **ADO.NET Entity Data Model**.</span></span>
<br />  <span data-ttu-id="fc7bb-175">엔터티 데이터 모델 마법사가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-175">The Entity Data Model Wizard opens.</span></span> <span data-ttu-id="fc7bb-176">이 마법사를 사용하면 엔터티 데이터 모델을 생성하는 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-176">By using this wizard, you can choose how you want to create the Entity Data Model.</span></span>
<br />

6. <span data-ttu-id="fc7bb-177">아래 **모델 콘텐츠 선택**, 선택는 **데이터베이스에서 생성** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-177">Under **Choose Model Contents**, select the **Generate from database** check box.</span></span>
<br />

7. <span data-ttu-id="fc7bb-178">다음 페이지에서 새로 만든 School 데이터베이스를 데이터 연결로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-178">On the next page, choose your newly created School database as the data connection.</span></span>
<br />  <span data-ttu-id="fc7bb-179">이 연결 비슷해야  **&lt;servername&gt;.&lt; instancename&gt;합니다. School.dbo**합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-179">This connection should resemble **&lt;servername&gt;.&lt;instancename&gt;.School.dbo**.</span></span>
<br />

8. <span data-ttu-id="fc7bb-180">엔터티 연결 문자열은 나중에 중요할 수 있으므로 클립보드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-180">Copy your entity connection string to the Clipboard because that string might be important later.</span></span>
<br />

9. <span data-ttu-id="fc7bb-181">엔터티 연결 문자열을 저장 하려면 확인란이 선택 되어 있는지 확인은 **App.Config** 파일을 선택 하 고 필요한 경우 나중에, 연결 문자열을 찾고 하는 데 도움이 되도록 하 고 텍스트 상자에서 문자열 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-181">Make sure the check box to save the entity connection string to the **App.Config** file is selected, and make note of the string value in the text box, which should help you locate the connection string later, if needed.</span></span>
<br />

10. <span data-ttu-id="fc7bb-182">다음 페이지에서 선택 **테이블** 및 **저장 프로시저 및 함수**합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-182">On the next page, choose **Tables** and **Stored Procedures and Functions**.</span></span>
<br />  <span data-ttu-id="fc7bb-183">이러한 최상위 노드를 선택하여 테이블, 저장 프로시저 및 함수를 모두 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-183">By choosing these top-level nodes, you choose all tables, stored procedures, and functions.</span></span> <span data-ttu-id="fc7bb-184">원할 경우 개별적으로 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-184">You can also choose these individually, if you want.</span></span>
<br />

11. <span data-ttu-id="fc7bb-185">다른 설정의 확인란이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-185">Make sure that the check boxes for the other settings are selected.</span></span>
<br />  <span data-ttu-id="fc7bb-186">첫 번째 **복수화 또는 생성 된 개체 이름을 단 수 화** 확인란 데이터베이스 테이블을 나타내는 명명 개체의 규칙과 일치 하도록 복수로, 단 수 양식을 변경 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-186">The first **Pluralize or singularize generated object names** check box indicates whether to change singular forms to plural to match conventions in naming objects that represent database tables.</span></span> <span data-ttu-id="fc7bb-187">**모델에 외래 키 열을 포함할** 확인란 목적은 데이터베이스 스키마에 대해 생성 된 개체 유형의 다른 필드에 조인 하려면 필드를 포함할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-187">The **Include foreign key columns in the model** check box determines whether to include fields for which the purpose is to join to other fields in the object types that are generated for the database schema.</span></span> <span data-ttu-id="fc7bb-188">세 번째 확인란은 모델에 저장 프로시저 및 함수를 포함하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-188">The third check box indicates whether to include stored procedures and functions in the model.</span></span>
<br />

12. <span data-ttu-id="fc7bb-189">선택 된 **마침** School 데이터베이스를 기반으로 하는 엔터티 데이터 모델을 포함 하는.edmx 파일을 생성 하는 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-189">Select the **Finish** button to generate an .edmx file that contains an Entity Data Model that's based on the School database.</span></span>
<br />  <span data-ttu-id="fc7bb-190">파일을 **Model1.edmx**, 프로젝트에 추가 데이터베이스 다이어그램이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-190">A file, **Model1.edmx**, is added to your project, and a database diagram appears.</span></span>
<br />

13. <span data-ttu-id="fc7bb-191">메뉴 모음에서 **보기**, **다른 창**, **엔터티 데이터 모델 브라우저** 모델의 모든 세부 정보를 보려면 또는 **엔터티 데이터 모델 매핑 정보**  생성 된 개체 모델을 데이터베이스 테이블 및 열에 매핑하는 방법을 보여 주는 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-191">On the menu bar, choose **View**, **Other Windows**, **Entity Data Model Browser** to view all the details of the model or **Entity Data Model Mapping Details** to open a window that shows how the generated object model maps onto database tables and columns.</span></span>
<br />


## <a name="next-steps"></a><span data-ttu-id="fc7bb-192">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fc7bb-192">Next Steps</span></span>
<span data-ttu-id="fc7bb-193">에 나열 된 사용 가능한 쿼리 연산자 확인 하 여 다른 쿼리를 탐색 [쿼리 식](../../language-reference/query-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bb-193">Explore other queries by looking at the available query operators as listed in [Query Expressions](../../language-reference/query-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="fc7bb-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc7bb-194">See Also</span></span>
[<span data-ttu-id="fc7bb-195">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="fc7bb-195">Type Providers</span></span>](index.md)

[<span data-ttu-id="fc7bb-196">EdmxFile 형식 공급자</span><span class="sxs-lookup"><span data-stu-id="fc7bb-196">EdmxFile Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[<span data-ttu-id="fc7bb-197">연습: 형식 공급자 및 엔터티를 사용하여 SQL Database에 액세스</span><span class="sxs-lookup"><span data-stu-id="fc7bb-197">Walkthrough: Accessing a SQL Database by Using Type Providers and Entities</span></span>](accessing-a-sql-database-entities.md)

[<span data-ttu-id="fc7bb-198">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="fc7bb-198">Entity Framework</span></span>](http://msdn.microsoft.com/data/ef)

[<span data-ttu-id="fc7bb-199">.edmx 파일 개요</span><span class="sxs-lookup"><span data-stu-id="fc7bb-199">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[<span data-ttu-id="fc7bb-200">EDM 생성기 &#40; EdmGen.exe &#41;</span><span class="sxs-lookup"><span data-stu-id="fc7bb-200">EDM Generator &#40;EdmGen.exe&#41;</span></span>](https://msdn.microsoft.com/library/bb387165)

