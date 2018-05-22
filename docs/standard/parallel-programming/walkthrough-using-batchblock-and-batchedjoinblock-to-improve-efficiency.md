---
title: '연습: BatchBlock 및 BatchedJoinBlock을 사용하여 효율성 향상'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcd12d5c3cfe341b22a5421930a22c272878006b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a><span data-ttu-id="20676-102">연습: BatchBlock 및 BatchedJoinBlock을 사용하여 효율성 향상</span><span class="sxs-lookup"><span data-stu-id="20676-102">Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency</span></span>
<span data-ttu-id="20676-103">TPL 데이터 흐름 라이브러리는 하나 이상의 소스에서 데이터를 검색 및 버퍼링한 다음, 해당 버퍼링된 데이터를 하나의 컬렉션으로 전파할 수 있도록 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-103">The TPL Dataflow Library provides the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> classes so that you can receive and buffer data from one or more sources and then propagate out that buffered data as one collection.</span></span> <span data-ttu-id="20676-104">이 일괄 처리 메커니즘은 하나 이상의 소스에서 데이터를 수집한 다음, 여러 데이터 요소를 일괄 처리할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-104">This batching mechanism is useful when you collect data from one or more sources and then process multiple data elements as a batch.</span></span> <span data-ttu-id="20676-105">예를 들어 데이터 흐름을 사용하여 레코드를 데이터베이스에 삽입하는 응용 프로그램을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-105">For example, consider an application that uses dataflow to insert records into a database.</span></span> <span data-ttu-id="20676-106">이 작업은 순차적으로 한 번에 하나가 아니라 동시에 여러 항목이 삽입되는 경우 더 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20676-106">This operation can be more efficient if multiple items are inserted at the same time instead of one at a time sequentially.</span></span> <span data-ttu-id="20676-107">이 문서에서는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스를 사용하여 이러한 데이터베이스 삽입 작업의 효율성을 개선하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-107">This document describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to improve the efficiency of such database insert operations.</span></span> <span data-ttu-id="20676-108">또한 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 클래스를 사용하여 프로그램이 데이터베이스에서 읽을 때 발생하는 모든 예외와 결과를 둘 다 캡처하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-108">It also describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to capture both the results and any exceptions that occur when the program reads from a database.</span></span>

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="prerequisites"></a><span data-ttu-id="20676-109">전제 조건</span><span class="sxs-lookup"><span data-stu-id="20676-109">Prerequisites</span></span>  
  
1.  <span data-ttu-id="20676-110">이 연습을 시작하기 전에 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 문서의 조인 블록 섹션을 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="20676-110">Read the Join Blocks section in the [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) document before you start this walkthrough.</span></span>  
  
2.  <span data-ttu-id="20676-111">컴퓨터에서 Northwind 데이터베이스 복사본인 Northwind.sdf를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="20676-111">Ensure that you have a copy of the Northwind database, Northwind.sdf, available on your computer.</span></span> <span data-ttu-id="20676-112">이 파일은 일반적으로 %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\ 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20676-112">This file is typically located in the folder %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="20676-113">일부 Windows 버전에서는 Visual Studio가 비관리자 모드로 실행 중인 경우 Northwind.sdf에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="20676-113">In some versions of Windows, you cannot connect to Northwind.sdf if Visual Studio is running in a non-administrator mode.</span></span> <span data-ttu-id="20676-114">Northwind.sdf에 연결하거나 Visual Studio 또는 Visual Studio 명령 프롬프트를 **관리자 권한으로 실행** 모드에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-114">To connect to Northwind.sdf, start Visual Studio or a Visual Studio command prompt in the **Run as administrator** mode.</span></span>  
  
 <span data-ttu-id="20676-115">이 연습에는 다음과 같은 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20676-115">This walkthrough contains the following sections:</span></span>  
  
-   [<span data-ttu-id="20676-116">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="20676-116">Creating the Console Application</span></span>](#creating)  
  
-   [<span data-ttu-id="20676-117">Employee 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="20676-117">Defining the Employee Class</span></span>](#employeeClass)  
  
-   [<span data-ttu-id="20676-118">직원 데이터베이스 작업 정의</span><span class="sxs-lookup"><span data-stu-id="20676-118">Defining Employee Database Operations</span></span>](#operations)  
  
-   [<span data-ttu-id="20676-119">버퍼링을 사용하지 않고 직원 데이터를 데이터베이스에 추가</span><span class="sxs-lookup"><span data-stu-id="20676-119">Adding Employee Data to the Database without Using Buffering</span></span>](#nonBuffering)  
  
-   [<span data-ttu-id="20676-120">버퍼링을 사용하여 직원 데이터를 데이터베이스에 추가</span><span class="sxs-lookup"><span data-stu-id="20676-120">Using Buffering to Add Employee Data to the Database</span></span>](#buffering)  
  
-   [<span data-ttu-id="20676-121">버퍼링된 조인을 사용하여 데이터베이스에서 직원 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="20676-121">Using Buffered Join to Read Employee Data from the Database</span></span>](#bufferedJoin)  
  
-   [<span data-ttu-id="20676-122">전체 예제</span><span class="sxs-lookup"><span data-stu-id="20676-122">The Complete Example</span></span>](#complete)  
  
<a name="creating"></a>   
## <a name="creating-the-console-application"></a><span data-ttu-id="20676-123">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="20676-123">Creating the Console Application</span></span>  
  
<a name="consoleApp"></a>   
1.  <span data-ttu-id="20676-124">Visual Studio에서 Visual C# 또는 Visual Basic **콘솔 응용 프로그램** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20676-124">In Visual Studio, create a Visual C# or Visual Basic **Console Application** project.</span></span> <span data-ttu-id="20676-125">이 문서에서 프로젝트 이름은 `DataflowBatchDatabase`입니다.</span><span class="sxs-lookup"><span data-stu-id="20676-125">In this document, the project is named `DataflowBatchDatabase`.</span></span>  
  
2.  <span data-ttu-id="20676-126">프로젝트에서 System.Data.SqlServerCe.dll에 대한 참조와 System.Threading.Tasks.Dataflow.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-126">In your project, add a reference to System.Data.SqlServerCe.dll and a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
3.  <span data-ttu-id="20676-127">Form1.cs(Visual Basic에서는 Form1.vb)에 다음 `using`(Visual Basic에서는 `Imports`) 명령문이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-127">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` (`Imports` in Visual Basic) statements.</span></span>  
  
     [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
     [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]  
  
4.  <span data-ttu-id="20676-128">`Program` 클래스에 다음 데이터 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-128">Add the following data members to the `Program` class.</span></span>  
  
     [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
     [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]  
  
<a name="employeeClass"></a>   
## <a name="defining-the-employee-class"></a><span data-ttu-id="20676-129">Employee 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="20676-129">Defining the Employee Class</span></span>  
 <span data-ttu-id="20676-130">`Program` 클래스에 `Employee` 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-130">Add to the `Program` class the `Employee` class.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
 [!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]  
  
 <span data-ttu-id="20676-131">`Employee` 클래스에는 세 가지 속성 `EmployeeID` , `LastName` 및 `FirstName`이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20676-131">The `Employee` class contains three properties, `EmployeeID`, `LastName`, and `FirstName`.</span></span> <span data-ttu-id="20676-132">이러한 속성은 Northwind 데이터베이스의 `Employees` 테이블에 있는 `Employee ID`, `Last Name` 및 `First Name` 열에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-132">These properties correspond to the `Employee ID`, `Last Name`, and `First Name` columns in the `Employees` table in the Northwind database.</span></span> <span data-ttu-id="20676-133">이 데모에서 `Employee` 클래스는 해당 속성에 대한 임의 값을 가지는 `Employee` 개체를 만드는 `Random` 메서드도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-133">For this demonstration, the `Employee` class also defines the `Random` method, which creates an `Employee` object that has random values for its properties.</span></span>  
  
<a name="operations"></a>   
## <a name="defining-employee-database-operations"></a><span data-ttu-id="20676-134">직원 데이터베이스 작업 정의</span><span class="sxs-lookup"><span data-stu-id="20676-134">Defining Employee Database Operations</span></span>  
 <span data-ttu-id="20676-135">`Program` 클래스에 `InsertEmployees`, `GetEmployeeCount` 및 `GetEmployeeID` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-135">Add to the `Program` class the `InsertEmployees`, `GetEmployeeCount`, and `GetEmployeeID` methods.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
 [!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]  
  
 <span data-ttu-id="20676-136">`InsertEmployees` 메서드는 새 직원 레코드를 데이터베이스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-136">The `InsertEmployees` method adds new employee records to the database.</span></span> <span data-ttu-id="20676-137">`GetEmployeeCount` 메서드는 `Employees` 테이블의 항목 수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-137">The `GetEmployeeCount` method retrieves the number of entries in the `Employees` table.</span></span> <span data-ttu-id="20676-138">`GetEmployeeID` 메서드는 제공된 이름이 있는 첫 번째 직원의 식별자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-138">The `GetEmployeeID` method retrieves the identifier of the first employee that has the provided name.</span></span> <span data-ttu-id="20676-139">이러한 각 메서드는 Northwind 데이터베이스에 대한 연결 문자열을 사용하고 `System.Data.SqlServerCe` 네임스페이스의 기능을 사용하여 데이터베이스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-139">Each of these methods takes a connection string to the Northwind database and uses functionality in the `System.Data.SqlServerCe` namespace to communicate with the database.</span></span>  
  
<a name="nonBuffering"></a>   
## <a name="adding-employee-data-to-the-database-without-using-buffering"></a><span data-ttu-id="20676-140">버퍼링을 사용하지 않고 직원 데이터를 데이터베이스에 추가</span><span class="sxs-lookup"><span data-stu-id="20676-140">Adding Employee Data to the Database Without Using Buffering</span></span>  
 <span data-ttu-id="20676-141">`Program` 클래스에 `AddEmployees` 및 `PostRandomEmployees` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-141">Add to the `Program` class the `AddEmployees` and `PostRandomEmployees` methods.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
 [!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]  
  
 <span data-ttu-id="20676-142">`AddEmployees` 메서드는 데이터 흐름을 사용하여 데이터베이스에 임의 직원 데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-142">The `AddEmployees` method adds random employee data to the database by using dataflow.</span></span> <span data-ttu-id="20676-143">데이터베이스에 직원 항목을 추가하기 위해 `InsertEmployees` 메서드를 호출하는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20676-143">It creates an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object that calls the `InsertEmployees` method to add an employee entry to the database.</span></span> <span data-ttu-id="20676-144">그런 다음, `AddEmployees` 메서드는 `PostRandomEmployees` 메서드를 호출하여 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체에 여러 `Employee` 개체를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-144">The `AddEmployees` method then calls the `PostRandomEmployees` method to post multiple `Employee` objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="20676-145">그런 다음, `AddEmployees` 메서드는 모든 삽입 작업이 완료될 때까지 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-145">The `AddEmployees` method then waits for all insert operations to finish.</span></span>  
  
<a name="buffering"></a>   
## <a name="using-buffering-to-add-employee-data-to-the-database"></a><span data-ttu-id="20676-146">버퍼링을 사용하여 직원 데이터를 데이터베이스에 추가</span><span class="sxs-lookup"><span data-stu-id="20676-146">Using Buffering to Add Employee Data to the Database</span></span>  
 <span data-ttu-id="20676-147">`Program` 클래스에 `AddEmployeesBatched` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-147">Add to the `Program` class the `AddEmployeesBatched` method.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
 [!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]  
  
 <span data-ttu-id="20676-148">이 메서드는 `AddEmployees`와 유사합니다. 단, 이 메서드는 해당 개체를 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체에 보내기 전에 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스를 사용하여 여러 `Employee` 개체를 버퍼링합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-148">This method resembles `AddEmployees`, except that it also uses the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to buffer multiple `Employee` objects before it sends those objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="20676-149"><xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스는 여러 요소를 컬렉션으로 전파하므로 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체는 `Employee` 개체 배열에서 작동하도록 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="20676-149">Because the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class propagates out multiple elements as a collection, the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object is modified to act on an array of `Employee` objects.</span></span> <span data-ttu-id="20676-150">`AddEmployees` 메서드처럼 `AddEmployeesBatched`는 `PostRandomEmployees` 메서드를 호출하여 여러 `Employee` 개체를 게시합니다. 그러나 `AddEmployeesBatched`는 이러한 개체를 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-150">As in the `AddEmployees` method, `AddEmployeesBatched` calls the `PostRandomEmployees` method to post multiple `Employee` objects; however, `AddEmployeesBatched` posts these objects to the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> object.</span></span> <span data-ttu-id="20676-151">또한 `AddEmployeesBatched` 메서드는 모든 삽입 작업이 완료될 때까지 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-151">The `AddEmployeesBatched`  method also waits for all insert operations to finish.</span></span>  
  
<a name="bufferedJoin"></a>   
## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a><span data-ttu-id="20676-152">버퍼링된 조인을 사용하여 데이터베이스에서 직원 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="20676-152">Using Buffered Join to Read Employee Data from the Database</span></span>  
 <span data-ttu-id="20676-153">`Program` 클래스에 `GetRandomEmployees` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-153">Add to the `Program` class the `GetRandomEmployees` method.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
 [!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]  
  
 <span data-ttu-id="20676-154">이 메서드는 임의 직원에 대한 정보를 콘솔에 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-154">This method prints information about random employees to the console.</span></span> <span data-ttu-id="20676-155">여러 개의 임의 `Employee` 개체를 만들고 `GetEmployeeID` 메서드를 호출하여 각 개체의 고유 식별자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-155">It creates several random `Employee` objects and calls the `GetEmployeeID` method to retrieve the unique identifier for each object.</span></span> <span data-ttu-id="20676-156">지정된 이름 및 성이 일치하는 직원이 없는 경우 `GetEmployeeID` 메서드가 예외를 throw하므로 `GetRandomEmployees` 메서드는 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 클래스를 사용하여 `GetEmployeeID` 호출 성공 시 `Employee` 개체를 저장하고 호출 실패 시 <xref:System.Exception?displayProperty=nameWithType> 개체를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-156">Because the `GetEmployeeID` method throws an exception if there is no matching employee with the given first and last names, the `GetRandomEmployees` method uses the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to store `Employee` objects for successful calls to `GetEmployeeID` and <xref:System.Exception?displayProperty=nameWithType> objects for calls that fail.</span></span> <span data-ttu-id="20676-157">이 예제의 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체는 `Employee` 개체 목록과 <xref:System.Exception> 개체 목록을 포함하는 <xref:System.Tuple%602> 개체에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-157">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object in this example acts on a <xref:System.Tuple%602> object that holds a list of `Employee` objects and a list of <xref:System.Exception> objects.</span></span> <span data-ttu-id="20676-158">수신된 `Employee` 및 <xref:System.Exception> 개체의 합계가 일괄 처리 크기와 같을 경우 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 개체는 이 데이터를 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-158">The <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> object propagates out this data when the sum of the received `Employee` and <xref:System.Exception> object counts equals the batch size.</span></span>  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a><span data-ttu-id="20676-159">전체 예제</span><span class="sxs-lookup"><span data-stu-id="20676-159">The Complete Example</span></span>  
 <span data-ttu-id="20676-160">다음 예제에서는 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20676-160">The following example shows the complete code.</span></span> <span data-ttu-id="20676-161">`Main` 메서드는 일괄 처리된 데이터베이스 삽입을 수행하는 데 필요한 시간과 일괄 처리되지 않은 데이터베이스 삽입을 수행하는 데 필요한 시간을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="20676-161">The `Main` method compares the time that is required to perform batched database insertions versus the time to perform non-batched database insertions.</span></span> <span data-ttu-id="20676-162">또한 버퍼링된 조인을 사용하여 데이터베이스에서 직원 데이터를 읽고 오류를 보고하는 작업도 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="20676-162">It also demonstrates the use of buffered join to read employee data from the database and also report errors.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
 [!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="20676-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20676-163">See Also</span></span>  
 [<span data-ttu-id="20676-164">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="20676-164">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
