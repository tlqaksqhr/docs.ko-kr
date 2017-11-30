---
title: "연습: BatchBlock 및 BatchedJoinBlock을 사용하여 효율성 향상"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, improving efficiency
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bc74b4acc5b29395c05e7c8302caefeb51718282
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-using-batchblock-and-batchedjoinblock-to-improve-efficiency"></a><span data-ttu-id="6a405-102">연습: BatchBlock 및 BatchedJoinBlock을 사용하여 효율성 향상</span><span class="sxs-lookup"><span data-stu-id="6a405-102">Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency</span></span>
<span data-ttu-id="6a405-103">TPL 데이터 흐름 라이브러리가 제공는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> 클래스를 수신 하 고 하나 이상의 소스에서 데이터를 버퍼링 하 고 다음 하나의 컬렉션으로 버퍼링 된 해당 데이터를 전파 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-103">The TPL Dataflow Library provides the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=nameWithType> classes so that you can receive and buffer data from one or more sources and then propagate out that buffered data as one collection.</span></span> <span data-ttu-id="6a405-104">이 일괄 처리 메커니즘 하나 이상의 소스에서 데이터를 수집 하 고 다음 일괄 처리로 여러 데이터 요소를 처리 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-104">This batching mechanism is useful when you collect data from one or more sources and then process multiple data elements as a batch.</span></span> <span data-ttu-id="6a405-105">예를 들어 데이터 흐름을 사용 하 여 데이터베이스에 레코드를 삽입 하는 응용 프로그램을 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-105">For example, consider an application that uses dataflow to insert records into a database.</span></span> <span data-ttu-id="6a405-106">이 작업은 여러 항목을 한 번에 하나씩 대신 한 번에 순차적 삽입 하는 경우 보다 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-106">This operation can be more efficient if multiple items are inserted at the same time instead of one at a time sequentially.</span></span> <span data-ttu-id="6a405-107">이 문서에 사용 하는 방법에 설명 된 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 이러한 데이터베이스의 효율성을 개선 하기 위해 클래스 삽입 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-107">This document describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to improve the efficiency of such database insert operations.</span></span> <span data-ttu-id="6a405-108">사용 하는 방법에 대해서도 설명는 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 결과 프로그램이 데이터베이스에서 읽는 경우 발생 하는 모든 예외를 캡처하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-108">It also describes how to use the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to capture both the results and any exceptions that occur when the program reads from a database.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="6a405-109">TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-109">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="6a405-110">설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-110">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6a405-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6a405-111">Prerequisites</span></span>  
  
1.  <span data-ttu-id="6a405-112">블록 조인 섹션을 읽어는 [데이터 흐름](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) 이 연습을 시작 하기 전에 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-112">Read the Join Blocks section in the [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) document before you start this walkthrough.</span></span>  
  
2.  <span data-ttu-id="6a405-113">컴퓨터에서 사용할 수 있는 Northwind.sdf Northwind 데이터베이스의 복사본을가지고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-113">Ensure that you have a copy of the Northwind database, Northwind.sdf, available on your computer.</span></span> <span data-ttu-id="6a405-114">이 파일은 % Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples 폴더에에서 있습니다 일반적으로\\합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-114">This file is typically located in the folder %Program Files%\Microsoft SQL Server Compact Edition\v3.5\Samples\\.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6a405-115">일부 버전의 Windows에서 연결할 수 없으면 Northwind.sdf 경우 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 관리자가 아닌 모드로 실행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-115">In some versions of Windows, you cannot connect to Northwind.sdf if [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] is running in a non-administrator mode.</span></span> <span data-ttu-id="6a405-116">시작 Northwind.sdf 연결할 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 또는 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 의 명령 프롬프트는 **관리자 권한으로 실행** 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-116">To connect to Northwind.sdf, start [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or a [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] command prompt in the **Run as administrator** mode.</span></span>  
  
 <span data-ttu-id="6a405-117">이 연습에는 다음과 같은 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-117">This walkthrough contains the following sections:</span></span>  
  
-   [<span data-ttu-id="6a405-118">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="6a405-118">Creating the Console Application</span></span>](#creating)  
  
-   [<span data-ttu-id="6a405-119">직원 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="6a405-119">Defining the Employee Class</span></span>](#employeeClass)  
  
-   [<span data-ttu-id="6a405-120">직원 데이터베이스 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-120">Defining Employee Database Operations</span></span>](#operations)  
  
-   [<span data-ttu-id="6a405-121">직원 데이터를 버퍼링을 사용 하지 않고 데이터베이스에 추가</span><span class="sxs-lookup"><span data-stu-id="6a405-121">Adding Employee Data to the Database without Using Buffering</span></span>](#nonBuffering)  
  
-   [<span data-ttu-id="6a405-122">버퍼링을 사용 하 여 직원 데이터는 데이터베이스를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="6a405-122">Using Buffering to Add Employee Data to the Database</span></span>](#buffering)  
  
-   [<span data-ttu-id="6a405-123">버퍼링 된 Join을 사용 하 여 데이터베이스에서 직원 데이터를 읽을 수</span><span class="sxs-lookup"><span data-stu-id="6a405-123">Using Buffered Join to Read Employee Data from the Database</span></span>](#bufferedJoin)  
  
-   [<span data-ttu-id="6a405-124">전체 예제</span><span class="sxs-lookup"><span data-stu-id="6a405-124">The Complete Example</span></span>](#complete)  
  
<a name="creating"></a>   
## <a name="creating-the-console-application"></a><span data-ttu-id="6a405-125">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="6a405-125">Creating the Console Application</span></span>  
  
<a name="consoleApp"></a>   
1.  <span data-ttu-id="6a405-126">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], Visual C# 또는 Visual Basic 만들 **콘솔 응용 프로그램** 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="6a405-126">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], create a Visual C# or Visual Basic **Console Application** project.</span></span> <span data-ttu-id="6a405-127">이 문서에서 프로젝트 이름은 `DataflowBatchDatabase`입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-127">In this document, the project is named `DataflowBatchDatabase`.</span></span>  
  
2.  <span data-ttu-id="6a405-128">프로젝트에서 System.Threading.Tasks.Dataflow.dll에 대 한 참조 및 System.Data.SqlServerCe.dll에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-128">In your project, add a reference to System.Data.SqlServerCe.dll and a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
3.  <span data-ttu-id="6a405-129">확인 해당 Form1.cs (Form1.vb [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])는 다음이 포함 `using` (`Imports` 에 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-129">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) statements.</span></span>  
  
     [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
     [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]  
  
4.  <span data-ttu-id="6a405-130">`Program` 클래스에 다음 데이터 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-130">Add the following data members to the `Program` class.</span></span>  
  
     [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
     [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]  
  
<a name="employeeClass"></a>   
## <a name="defining-the-employee-class"></a><span data-ttu-id="6a405-131">직원 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="6a405-131">Defining the Employee Class</span></span>  
 <span data-ttu-id="6a405-132">에 추가 된 `Program` 클래스는 `Employee` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-132">Add to the `Program` class the `Employee` class.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
 [!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]  
  
 <span data-ttu-id="6a405-133">`Employee` 세 가지 속성을 포함 하는 클래스 `EmployeeID`, `LastName`, 및 `FirstName`합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-133">The `Employee` class contains three properties, `EmployeeID`, `LastName`, and `FirstName`.</span></span> <span data-ttu-id="6a405-134">이러한 속성에 해당 하는 `Employee ID`, `Last Name`, 및 `First Name` 열에는 `Employees` Northwind 데이터베이스의 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-134">These properties correspond to the `Employee ID`, `Last Name`, and `First Name` columns in the `Employees` table in the Northwind database.</span></span> <span data-ttu-id="6a405-135">이 데모에서는 `Employee` 클래스도 정의 `Random` 을 만드는 메서드는 `Employee` 해당 속성에 대 한 임의 값을 가진 개체를 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-135">For this demonstration, the `Employee` class also defines the `Random` method, which creates an `Employee` object that has random values for its properties.</span></span>  
  
<a name="operations"></a>   
## <a name="defining-employee-database-operations"></a><span data-ttu-id="6a405-136">직원 데이터베이스 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-136">Defining Employee Database Operations</span></span>  
 <span data-ttu-id="6a405-137">에 추가 된 `Program` 클래스는 `InsertEmployees`, `GetEmployeeCount`, 및 `GetEmployeeID` 메서드.</span><span class="sxs-lookup"><span data-stu-id="6a405-137">Add to the `Program` class the `InsertEmployees`, `GetEmployeeCount`, and `GetEmployeeID` methods.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
 [!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]  
  
 <span data-ttu-id="6a405-138">`InsertEmployees` 메서드는 새 직원 레코드가 데이터베이스에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-138">The `InsertEmployees` method adds new employee records to the database.</span></span> <span data-ttu-id="6a405-139">`GetEmployeeCount` 에 있는 항목의 수를 검색 하는 메서드는 `Employees` 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-139">The `GetEmployeeCount` method retrieves the number of entries in the `Employees` table.</span></span> <span data-ttu-id="6a405-140">`GetEmployeeID` 메서드는 제공 된 이름이 있는 첫 번째 직원의 식별자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-140">The `GetEmployeeID` method retrieves the identifier of the first employee that has the provided name.</span></span> <span data-ttu-id="6a405-141">Northwind 데이터베이스에 연결 문자열을 사용 하 고에서 기능을 사용 하 여 이러한 각 방법의 `System.Data.SqlServerCe` 네임 스페이스는 데이터베이스와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-141">Each of these methods takes a connection string to the Northwind database and uses functionality in the `System.Data.SqlServerCe` namespace to communicate with the database.</span></span>  
  
<a name="nonBuffering"></a>   
## <a name="adding-employee-data-to-the-database-without-using-buffering"></a><span data-ttu-id="6a405-142">직원 데이터를 버퍼링을 사용 하지 않고 데이터베이스에 추가</span><span class="sxs-lookup"><span data-stu-id="6a405-142">Adding Employee Data to the Database Without Using Buffering</span></span>  
 <span data-ttu-id="6a405-143">에 추가 된 `Program` 클래스는 `AddEmployees` 및 `PostRandomEmployees` 메서드.</span><span class="sxs-lookup"><span data-stu-id="6a405-143">Add to the `Program` class the `AddEmployees` and `PostRandomEmployees` methods.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
 [!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]  
  
 <span data-ttu-id="6a405-144">`AddEmployees` 메서드에서 데이터베이스에 데이터 흐름을 사용 하 여 무작위 직원 데이터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-144">The `AddEmployees` method adds random employee data to the database by using dataflow.</span></span> <span data-ttu-id="6a405-145">만듭니다는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 호출 하는 개체는 `InsertEmployees` 메서드는 데이터베이스에 직원 항목을 추가 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-145">It creates an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object that calls the `InsertEmployees` method to add an employee entry to the database.</span></span> <span data-ttu-id="6a405-146">`AddEmployees` 메서드를 호출는 `PostRandomEmployees` 메서드 여러 게시를 `Employee` 개체는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-146">The `AddEmployees` method then calls the `PostRandomEmployees` method to post multiple `Employee` objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="6a405-147">`AddEmployees` 메서드는 다음 모든 삽입 작업 완료에 대 한 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-147">The `AddEmployees` method then waits for all insert operations to finish.</span></span>  
  
<a name="buffering"></a>   
## <a name="using-buffering-to-add-employee-data-to-the-database"></a><span data-ttu-id="6a405-148">버퍼링을 사용 하 여 직원 데이터는 데이터베이스를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="6a405-148">Using Buffering to Add Employee Data to the Database</span></span>  
 <span data-ttu-id="6a405-149">에 추가 된 `Program` 클래스는 `AddEmployeesBatched` 메서드.</span><span class="sxs-lookup"><span data-stu-id="6a405-149">Add to the `Program` class the `AddEmployeesBatched` method.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
 [!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]  
  
 <span data-ttu-id="6a405-150">이 메서드가 유사한 `AddEmployees`사용 하 여 제외 하 고는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 여러 버퍼링 할 클래스 `Employee` 해당 개체를 보내기 전에 개체는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-150">This method resembles `AddEmployees`, except that it also uses the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class to buffer multiple `Employee` objects before it sends those objects to the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object.</span></span> <span data-ttu-id="6a405-151">때문에 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 클래스 요소를 여러 컬렉션으로 전파는 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체의 배열에 대해 작동 하도록 수정 됩니다 `Employee` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-151">Because the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> class propagates out multiple elements as a collection, the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object is modified to act on an array of `Employee` objects.</span></span> <span data-ttu-id="6a405-152">그러나와 같이 `AddEmployees` 메서드를 `AddEmployeesBatched` 호출은 `PostRandomEmployees` 메서드 여러 게시를 `Employee` 개체이 고, `AddEmployeesBatched` 이러한 개체를 게시는 <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-152">As in the `AddEmployees` method, `AddEmployeesBatched` calls the `PostRandomEmployees` method to post multiple `Employee` objects; however, `AddEmployeesBatched` posts these objects to the <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> object.</span></span> <span data-ttu-id="6a405-153">`AddEmployeesBatched` 메서드는 또한 모든 삽입 작업 완료에 대 한 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-153">The `AddEmployeesBatched`  method also waits for all insert operations to finish.</span></span>  
  
<a name="bufferedJoin"></a>   
## <a name="using-buffered-join-to-read-employee-data-from-the-database"></a><span data-ttu-id="6a405-154">버퍼링 된 Join을 사용 하 여 데이터베이스에서 직원 데이터를 읽을 수</span><span class="sxs-lookup"><span data-stu-id="6a405-154">Using Buffered Join to Read Employee Data from the Database</span></span>  
 <span data-ttu-id="6a405-155">에 추가 된 `Program` 클래스는 `GetRandomEmployees` 메서드.</span><span class="sxs-lookup"><span data-stu-id="6a405-155">Add to the `Program` class the `GetRandomEmployees` method.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
 [!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]  
  
 <span data-ttu-id="6a405-156">이 메서드는 콘솔에 무작위 직원에 대 한 정보를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-156">This method prints information about random employees to the console.</span></span> <span data-ttu-id="6a405-157">만들 여러 임의 `Employee` 개체와 호출은 `GetEmployeeID` 각 개체에 대 한 고유 식별자를 검색 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-157">It creates several random `Employee` objects and calls the `GetEmployeeID` method to retrieve the unique identifier for each object.</span></span> <span data-ttu-id="6a405-158">때문에 `GetEmployeeID` 메서드에서 지정 된 첫 번째 및 마지막 이름으로 일치 하는 직원이 없는 경우 예외가 throw는 `GetRandomEmployees` 메서드는 <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 저장할 수 있도록 클래스 `Employee` 개체에 대 한 성공적인 호출 `GetEmployeeID` 및 <xref:System.Exception?displayProperty=nameWithType> 대 한 호출에 실패 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-158">Because the `GetEmployeeID` method throws an exception if there is no matching employee with the given first and last names, the `GetRandomEmployees` method uses the <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> class to store `Employee` objects for successful calls to `GetEmployeeID` and <xref:System.Exception?displayProperty=nameWithType> objects for calls that fail.</span></span> <span data-ttu-id="6a405-159"><xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 이 예제는 개체에 작업을 수행는 <xref:System.Tuple%602> 목록을 보유 하는 개체 `Employee` 개체 및 목록이 <xref:System.Exception> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-159">The <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object in this example acts on a <xref:System.Tuple%602> object that holds a list of `Employee` objects and a list of <xref:System.Exception> objects.</span></span> <span data-ttu-id="6a405-160"><xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> 개체가이 데이터 전파 때 받은 총 `Employee` 및 <xref:System.Exception> 개체 수와 동일한 일괄 처리 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-160">The <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> object propagates out this data when the sum of the received `Employee` and <xref:System.Exception> object counts equals the batch size.</span></span>  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a><span data-ttu-id="6a405-161">전체 예제</span><span class="sxs-lookup"><span data-stu-id="6a405-161">The Complete Example</span></span>  
 <span data-ttu-id="6a405-162">다음 예제에서는 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-162">The following example shows the complete code.</span></span> <span data-ttu-id="6a405-163">`Main` 메서드 데이터베이스 비 일괄 처리 삽입 하는 데 시간 및 일괄 처리 된 데이터베이스 삽입 하는 데 필요한 시간을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-163">The `Main` method compares the time that is required to perform batched database insertions versus the time to perform non-batched database insertions.</span></span> <span data-ttu-id="6a405-164">또한 데이터베이스에서 직원 데이터를 읽고 오류를 보고할 수도 버퍼링 된 조인의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a405-164">It also demonstrates the use of buffered join to read employee data from the database and also report errors.</span></span>  
  
 [!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
 [!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="6a405-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a405-165">See Also</span></span>  
 [<span data-ttu-id="6a405-166">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="6a405-166">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
