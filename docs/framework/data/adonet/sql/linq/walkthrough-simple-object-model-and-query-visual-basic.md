---
title: '연습: 간단한 개체 모델 및 쿼리(Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: c878e457-f715-46e4-a136-ff14d6c86018
ms.openlocfilehash: f2df0dfa039fa37fd9d9b471d28b2a03f06b3037
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365737"
---
# <a name="walkthrough-simple-object-model-and-query-visual-basic"></a><span data-ttu-id="b42ab-102">연습: 간단한 개체 모델 및 쿼리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b42ab-102">Walkthrough: Simple Object Model and Query (Visual Basic)</span></span>
<span data-ttu-id="b42ab-103">이 연습에서는 간단한 기본 종단 간 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="b42ab-104">샘플 Northwind 데이터베이스의 Customers 테이블을 모델링하는 엔터티 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-104">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="b42ab-105">그런 다음 단순 쿼리를 만들어 London에 있는 고객을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-105">You will then create a simple query to list customers who are located in London.</span></span>  
  
 <span data-ttu-id="b42ab-106">이 연습은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 개념을 보여 주기 위한 코드를 중심으로 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-106">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="b42ab-107">일반적으로 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]를 사용하여 개체 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-107">Normally speaking, you would use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="b42ab-108">이 연습은 Visual Basic 개발 설정을 사용하여 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-108">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b42ab-109">전제 조건</span><span class="sxs-lookup"><span data-stu-id="b42ab-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="b42ab-110">이 연습에서는 파일을 저장하기 위해 전용 폴더("c:\linqtest")가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-110">This walkthrough uses a dedicated folder ("c:\linqtest") to hold files.</span></span> <span data-ttu-id="b42ab-111">연습을 시작하기 전에 먼저 이 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-111">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="b42ab-112">이 연습을 수행하려면 Northwind 샘플 데이터베이스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-112">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="b42ab-113">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 사이트에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-113">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="b42ab-114">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-114">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="b42ab-115">이 데이터베이스를 다운로드한 후 파일을 c:\linqtest 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-115">After you have downloaded the database, copy the file to the c:\linqtest folder.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="b42ab-116">개요</span><span class="sxs-lookup"><span data-stu-id="b42ab-116">Overview</span></span>  
 <span data-ttu-id="b42ab-117">이 연습은 다음과 같은 여섯 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-117">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="b42ab-118">만들기는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Visual Studio에서 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-118">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="b42ab-119">데이터베이스 테이블에 클래스 매핑</span><span class="sxs-lookup"><span data-stu-id="b42ab-119">Mapping a class to a database table.</span></span>  
  
-   <span data-ttu-id="b42ab-120">데이터베이스 열을 나타내도록 클래스의 속성 지정</span><span class="sxs-lookup"><span data-stu-id="b42ab-120">Designating properties on the class to represent database columns.</span></span>  
  
-   <span data-ttu-id="b42ab-121">Northwind 데이터베이스에 대한 연결 지정</span><span class="sxs-lookup"><span data-stu-id="b42ab-121">Specifying the connection to the Northwind database.</span></span>  
  
-   <span data-ttu-id="b42ab-122">데이터베이스에 대해 실행할 단순 쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="b42ab-122">Creating a simple query to run against the database.</span></span>  
  
-   <span data-ttu-id="b42ab-123">쿼리 실행 및 결과 검토</span><span class="sxs-lookup"><span data-stu-id="b42ab-123">Executing the query and observing the results.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="b42ab-124">LINQ to SQL 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="b42ab-124">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="b42ab-125">이 첫 번째 작업에서 빌드 및 실행 하는 데 필요한 참조가 포함 된 Visual Studio 솔루션을 만들는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="b42ab-125">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="b42ab-126">LINQ to SQL 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b42ab-126">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="b42ab-127">**파일** 메뉴에서 **새 프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-127">On the **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="b42ab-128">에 **프로젝트 형식** 의 창은 **새 프로젝트** 대화 상자를 클릭 **Visual Basic**합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-128">In the **Project types** pane of the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3.  <span data-ttu-id="b42ab-129">**템플릿** 창에서 **콘솔 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-129">In the **Templates** pane, click **Console Application**.</span></span>  
  
4.  <span data-ttu-id="b42ab-130">에 **이름** 상자에서 입력 **LinqConsoleApp**합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-130">In the **Name** box, type **LinqConsoleApp**.</span></span>  
  
5.  <span data-ttu-id="b42ab-131">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-131">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="b42ab-132">LINQ 참조 및 지시문 추가</span><span class="sxs-lookup"><span data-stu-id="b42ab-132">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="b42ab-133">이 연습에서는 프로젝트에 기본적으로 설치되어 있지 않을 수 있는 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-133">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="b42ab-134">경우 `System.Data.Linq` 프로젝트에 대 한 참조로 나열 되지 않은 (클릭 **모든 파일 표시** 에 **솔루션 탐색기** 확장는 **참조** 노드)에 설명 된 대로 추가 다음 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-134">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="b42ab-135">System.Data.Linq를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="b42ab-135">To add System.Data.Linq</span></span>  
  
1.  <span data-ttu-id="b42ab-136">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **참조**, 클릭 하 고 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-136">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="b42ab-137">에 **참조 추가** 대화 상자를 클릭 **.NET**System.Data.Linq 어셈블리를 클릭 한 다음 클릭, **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-137">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b42ab-138">어셈블리가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-138">The assembly is added to the project.</span></span>  
  
3.  <span data-ttu-id="b42ab-139">또한는 **참조 추가** 대화 상자를 클릭 **.NET**, 스크롤하여 및 System.Windows.Forms를 클릭 한 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-139">Also in the **Add Reference** dialog box, click **.NET**, scroll to and click System.Windows.Forms, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b42ab-140">연습에서 메시지 상자를 지원하는 어셈블리가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-140">This assembly, which supports the message box in the walkthrough, is added to the project.</span></span>  
  
4.  <span data-ttu-id="b42ab-141">`Module1` 위에 다음 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-141">Add the following directives above `Module1`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#1)]  
  
## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="b42ab-142">데이터베이스 테이블에 클래스 매핑</span><span class="sxs-lookup"><span data-stu-id="b42ab-142">Mapping a Class to a Database Table</span></span>  
 <span data-ttu-id="b42ab-143">이 단계에서는 클래스를 생성하여 데이터베이스 테이블에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-143">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="b42ab-144">이러한 클래스 라고는 *엔터티 클래스*합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-144">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="b42ab-145">매핑을 수행하려면 <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-145">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="b42ab-146"><xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> 속성은 데이터베이스의 테이블 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-146">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>  
  
#### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="b42ab-147">엔터티 클래스를 만들어 데이터베이스 테이블에 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="b42ab-147">To create an entity class and map it to a database table</span></span>  
  
-   <span data-ttu-id="b42ab-148">다음 코드를 `Sub Main` 바로 위에 있는 Module1.vb에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-148">Type or paste the following code into Module1.vb immediately above `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#2)]  
  
## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="b42ab-149">데이터베이스 열을 나타내도록 클래스의 속성 지정</span><span class="sxs-lookup"><span data-stu-id="b42ab-149">Designating Properties on the Class to Represent Database Columns</span></span>  
 <span data-ttu-id="b42ab-150">이 단계에서는 다음과 같은 몇 가지 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-150">In this step, you accomplish several tasks.</span></span>  
  
-   <span data-ttu-id="b42ab-151"><xref:System.Data.Linq.Mapping.ColumnAttribute> 특성을 사용하여 데이터베이스 테이블의 열을 나타내도록 엔터티 클래스의 `CustomerID` 및 `City` 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-151">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>  
  
-   <span data-ttu-id="b42ab-152">데이터베이스의 기본 키 열을 나타내도록 `CustomerID` 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-152">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>  
  
-   <span data-ttu-id="b42ab-153">전용 저장소에 `_CustomerID` 및 `_City` 필드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-153">You designate `_CustomerID` and `_City` fields for private storage.</span></span> <span data-ttu-id="b42ab-154">그러면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 비즈니스 논리가 포함된 공용 접근자를 사용하는 대신 값을 직접 저장하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-154">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>  
  
#### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="b42ab-155">두 데이터베이스 열의 특징을 나타내려면</span><span class="sxs-lookup"><span data-stu-id="b42ab-155">To represent characteristics of two database columns</span></span>  
  
-   <span data-ttu-id="b42ab-156">다음 코드를 `End Class` 바로 앞의 Module1.vb에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-156">Type or paste the following code into Module1.vb just before `End Class`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#3)]  
  
## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="b42ab-157">Northwind 데이터베이스에 대한 연결 지정</span><span class="sxs-lookup"><span data-stu-id="b42ab-157">Specifying the Connection to the Northwind Database</span></span>  
 <span data-ttu-id="b42ab-158">이 단계에서는 <xref:System.Data.Linq.DataContext> 개체를 사용하여 코드 기반 데이터 구조체와 데이터베이스 자체 간의 연결을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-158">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="b42ab-159"><xref:System.Data.Linq.DataContext>는 데이터베이스에서 개체를 검색하고 변경 내용을 전송할 때 사용하는 기본 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-159">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>  
  
 <span data-ttu-id="b42ab-160">또한 `Table(Of Customer)`이 데이터베이스의 Customers 테이블에 대한 쿼리에 대해 형식화된 논리적 테이블로 사용되도록 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-160">You also declare a `Table(Of Customer)` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="b42ab-161">이후 단계에서 이러한 쿼리를 만들고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-161">You will create and execute these queries in later steps.</span></span>  
  
#### <a name="to-specify-the-database-connection"></a><span data-ttu-id="b42ab-162">데이터베이스 연결을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="b42ab-162">To specify the database connection</span></span>  
  
-   <span data-ttu-id="b42ab-163">다음 코드를 `Sub Main` 메서드에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-163">Type or paste the following code into the `Sub Main` method.</span></span>  
  
     <span data-ttu-id="b42ab-164">`northwnd.mdf` 파일은 linqtest 폴더 내에 있는 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-164">Note that the `northwnd.mdf` file is assumed to be in the linqtest folder.</span></span> <span data-ttu-id="b42ab-165">자세한 내용은 이 연습 앞부분의 사전 요구 사항 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b42ab-165">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
     [!code-vb[DLinqWalk1VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#4)]  
  
## <a name="creating-a-simple-query"></a><span data-ttu-id="b42ab-166">단순 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="b42ab-166">Creating a Simple Query</span></span>  
 <span data-ttu-id="b42ab-167">이 단계에서는 데이터베이스 Customers 테이블에서 London에 있는 고객을 찾는 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-167">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="b42ab-168">이 단계의 쿼리 코드는 쿼리를 설명하기만 하고</span><span class="sxs-lookup"><span data-stu-id="b42ab-168">The query code in this step just describes the query.</span></span> <span data-ttu-id="b42ab-169">실행하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-169">It does not execute it.</span></span> <span data-ttu-id="b42ab-170">이 방법은 라고 *지연 된 실행*합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-170">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="b42ab-171">자세한 내용은 [LINQ 쿼리 소개(C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b42ab-171">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="b42ab-172">또한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 생성하는 SQL 명령을 보여 주는 로그 출력을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-172">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="b42ab-173"><xref:System.Data.Linq.DataContext.Log%2A>를 사용하는 이 로깅 기능은 디버깅할 때와 데이터베이스로 전송되는 명령이 쿼리를 정확히 나타내는지 확인할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-173">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="b42ab-174">단순 쿼리를 작성하려면</span><span class="sxs-lookup"><span data-stu-id="b42ab-174">To create a simple query</span></span>  
  
-   <span data-ttu-id="b42ab-175">다음 코드를 `Sub Main` 선언 뒤의 `Table(Of Customer)` 메서드에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-175">Type or paste the following code into the `Sub Main` method after the `Table(Of Customer)` declaration:</span></span>  
  
     [!code-vb[DLinqWalk1AVB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#5)]  
  
## <a name="executing-the-query"></a><span data-ttu-id="b42ab-176">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="b42ab-176">Executing the Query</span></span>  
 <span data-ttu-id="b42ab-177">이 단계에서는 실제로 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-177">In this step, you actually execute the query.</span></span> <span data-ttu-id="b42ab-178">앞의 단계에서 만든 쿼리 식은 결과가 필요할 때까지 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-178">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="b42ab-179">`For Each` 반복을 시작하면 데이터베이스에 대해 SQL 명령이 실행되고 개체가 구체화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-179">When you begin the `For Each` iteration, a SQL command is executed against the database and objects are materialized.</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="b42ab-180">쿼리를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b42ab-180">To execute the query</span></span>  
  
1.  <span data-ttu-id="b42ab-181">다음 코드를 쿼리 설명 뒤 `Sub Main` 메서드의 끝에 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-181">Type or paste the following code at the end of the `Sub Main` method (after the query description):</span></span>  
  
     [!code-vb[DLinqWalk1AVB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#6)]  
  
2.  <span data-ttu-id="b42ab-182">F5 키를 눌러 응용 프로그램을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-182">Press F5 to debug the application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b42ab-183">응용 프로그램에서 런타임 오류를 생성할 경우의 문제 해결 섹션을 참조 하세요. [연습으로 학습](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-183">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
     <span data-ttu-id="b42ab-184">메시지 상자에 여섯 명의 고객이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-184">The message box displays a list of six customers.</span></span> <span data-ttu-id="b42ab-185">콘솔 창에 생성된 SQL 코드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-185">The Console window displays the generated SQL code.</span></span>  
  
3.  <span data-ttu-id="b42ab-186">클릭 **확인** 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-186">Click **OK** to dismiss the message box.</span></span>  
  
     <span data-ttu-id="b42ab-187">응용 프로그램을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-187">The application closes.</span></span>  
  
4.  <span data-ttu-id="b42ab-188">에 **파일** 메뉴를 클릭 하 여 **모두 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-188">On the **File** menu, click **Save All**.</span></span>  
  
     <span data-ttu-id="b42ab-189">다음 연습을 계속하려면 이 응용 프로그램이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-189">You will need this application if you continue with the next walkthrough.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b42ab-190">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b42ab-190">Next Steps</span></span>  
 <span data-ttu-id="b42ab-191">[연습: 관계 간 쿼리 (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) 항목 계속 해 서이 연습에서는 완료할 합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-191">The [Walkthrough: Querying Across Relationships (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="b42ab-192">관계 간 쿼리 연습에서는 방법을 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 테이블, 유사한 쿼리 *조인* 관계형 데이터베이스에서입니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-192">The Querying Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>  
  
 <span data-ttu-id="b42ab-193">관계 간 쿼리 연습을 수행하려면 지금까지 완료한 연습에 대한 솔루션을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b42ab-193">If you want to do the Querying Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b42ab-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b42ab-194">See Also</span></span>  
 [<span data-ttu-id="b42ab-195">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="b42ab-195">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
