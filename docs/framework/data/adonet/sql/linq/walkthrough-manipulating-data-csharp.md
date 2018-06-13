---
title: '연습: 데이터 조작(C#)'
ms.date: 03/30/2017
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
ms.openlocfilehash: b9b19d4f9a1fb56ddabbf3584c1fb7bb29cd6d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357662"
---
# <a name="walkthrough-manipulating-data-c"></a><span data-ttu-id="8614a-102">연습: 데이터 조작(C#)</span><span class="sxs-lookup"><span data-stu-id="8614a-102">Walkthrough: Manipulating Data (C#)</span></span>
<span data-ttu-id="8614a-103">이 연습에서는 데이터베이스의 데이터를 추가, 수정 및 삭제하기 위한 기본 종단 간 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="8614a-104">Northwind 샘플 데이터베이스의 복사본을 사용하여 고객을 추가하고, 고객의 이름을 변경하고, 주문을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="8614a-105">이 연습은 Visual C# 개발 설정을 사용하여 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-105">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8614a-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="8614a-106">Prerequisites</span></span>  
 <span data-ttu-id="8614a-107">이 연습에서는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-107">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="8614a-108">이 연습에서는 파일을 보유하기 위해 전용 폴더("c:\linqtest6")가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-108">This walkthrough uses a dedicated folder ("c:\linqtest6") to hold files.</span></span> <span data-ttu-id="8614a-109">연습을 시작하기 전에 먼저 이 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-109">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="8614a-110">Northwind 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="8614a-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="8614a-111">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 사이트에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="8614a-112">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-112">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="8614a-113">이 데이터베이스를 다운로드한 후 northwnd.mdf 파일을 c:\linqtest6 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest6 folder.</span></span>  
  
-   <span data-ttu-id="8614a-114">Northwind 데이터베이스에서 생성된 C# 코드 파일</span><span class="sxs-lookup"><span data-stu-id="8614a-114">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="8614a-115">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 또는 SQLMetal을 사용하여 이 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-115">You can generate this file by using either the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] or the SQLMetal tool.</span></span> <span data-ttu-id="8614a-116">이 연습은 다음 명령줄을 사용하여 SQLMetal 도구를 통해 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="8614a-117">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="8614a-117">**sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="8614a-118">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8614a-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="8614a-119">개요</span><span class="sxs-lookup"><span data-stu-id="8614a-119">Overview</span></span>  
 <span data-ttu-id="8614a-120">이 연습은 다음과 같은 여섯 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-120">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="8614a-121">만들기는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Visual Studio에서 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="8614a-122">데이터베이스 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="8614a-122">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="8614a-123">새 Customer 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="8614a-123">Creating a new customer object.</span></span>  
  
-   <span data-ttu-id="8614a-124">고객의 연락처 이름 수정</span><span class="sxs-lookup"><span data-stu-id="8614a-124">Modifying the contact name of a customer.</span></span>  
  
-   <span data-ttu-id="8614a-125">주문 삭제</span><span class="sxs-lookup"><span data-stu-id="8614a-125">Deleting an order.</span></span>  
  
-   <span data-ttu-id="8614a-126">이러한 변경 내용을 Northwind 데이터베이스로 전송</span><span class="sxs-lookup"><span data-stu-id="8614a-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="8614a-127">LINQ to SQL 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="8614a-127">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="8614a-128">이 첫 번째 작업에서 빌드 및 실행 하는 데 필요한 참조가 포함 된 Visual Studio 솔루션을 만들는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="8614a-128">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="8614a-129">LINQ to SQL 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="8614a-129">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="8614a-130">Visual Studio에서 **파일** 메뉴에서 **새로**, 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-130">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="8614a-131">에 **프로젝트 형식** 창에는 **새 프로젝트** 대화 상자를 클릭 **Visual C#** 합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-131">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="8614a-132">**템플릿** 창에서 **콘솔 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4.  <span data-ttu-id="8614a-133">에 **이름** 상자에서 입력 **LinqDataManipulationApp**합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5.  <span data-ttu-id="8614a-134">에 **위치** 상자, 프로젝트 파일을 저장할 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-134">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6.  <span data-ttu-id="8614a-135">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-135">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="8614a-136">LINQ 참조 및 지시문 추가</span><span class="sxs-lookup"><span data-stu-id="8614a-136">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="8614a-137">이 연습에서는 프로젝트에 기본적으로 설치되어 있지 않을 수 있는 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-137">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="8614a-138">System.Data.Linq가 프로젝트에 참조로 나열되지 않은 경우 다음 단계에 설명된 대로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-138">If System.Data.Linq is not listed as a reference in your project, add it, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="8614a-139">System.Data.Linq를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="8614a-139">To add System.Data.Linq</span></span>  
  
1.  <span data-ttu-id="8614a-140">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **참조**, 클릭 하 고 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-140">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="8614a-141">에 **참조 추가** 대화 상자를 클릭 **.NET**System.Data.Linq 어셈블리를 클릭 한 다음 클릭, **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-141">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="8614a-142">어셈블리가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-142">The assembly is added to the project.</span></span>  
  
3.  <span data-ttu-id="8614a-143">Program.cs 맨 위에 다음 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-143">Add the following directives at the top of Program.cs:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="8614a-144">Northwind 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="8614a-144">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="8614a-145">이 단계에서는 SQLMetal 도구를 사용하여 Northwind 샘플 데이터베이스에서 코드 파일을 생성했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-145">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="8614a-146">자세한 내용은 이 연습 앞부분의 사전 요구 사항 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8614a-146">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="8614a-147">northwind 코드 파일을 프로젝트에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="8614a-147">To add the northwind code file to the project</span></span>  
  
1.  <span data-ttu-id="8614a-148">에 **프로젝트** 메뉴를 클릭 하 여 **기존 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-148">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2.  <span data-ttu-id="8614a-149">에 **기존 항목 추가** 대화 상자에서 c:\linqtest6\northwind.cs로 이동한 다음 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-149">In the **Add Existing Item** dialog box, navigate to c:\linqtest6\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="8614a-150">northwind.cs 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-150">The northwind.cs file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="8614a-151">데이터베이스 연결 설정</span><span class="sxs-lookup"><span data-stu-id="8614a-151">Setting Up the Database Connection</span></span>  
 <span data-ttu-id="8614a-152">먼저 데이터베이스에 대한 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-152">First, test your connection to the database.</span></span> <span data-ttu-id="8614a-153">특히 데이터베이스 이름 Northwnd에 i 문자가 없는 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-153">Note especially that the database, Northwnd, has no i character.</span></span> <span data-ttu-id="8614a-154">다음 단계에서 오류를 생성하는 경우 northwind.cs 파일을 검토하여 Northwind partial 클래스의 맞춤법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-154">If you generate errors in the next steps, review the northwind.cs file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="8614a-155">데이터베이스 연결을 설정하고 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="8614a-155">To set up and test the database connection</span></span>  
  
1.  <span data-ttu-id="8614a-156">Program 클래스의 `Main` 메서드에 다음 코드를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-156">Type or paste the following code into the `Main` method in the Program class:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2.  <span data-ttu-id="8614a-157">이때 F5 키를 눌러 응용 프로그램을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-157">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="8614a-158">A **콘솔** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-158">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="8614a-159">Enter 키를 눌러 응용 프로그램을 닫을 수 있습니다는 **콘솔** 창을 클릭 하 여 **디버깅 중지** Visual Studio에서 **디버그** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="8614a-159">You can close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the Visual Studio **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="8614a-160">새 엔터티 만들기</span><span class="sxs-lookup"><span data-stu-id="8614a-160">Creating a New Entity</span></span>  
 <span data-ttu-id="8614a-161">새 엔터티를 만드는 과정은 단순합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-161">Creating a new entity is straightforward.</span></span> <span data-ttu-id="8614a-162">`Customer` 키워드를 사용하여 개체(예: `new`)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-162">You can create objects (such as `Customer`) by using the `new` keyword.</span></span>  
  
 <span data-ttu-id="8614a-163">이 단원과 다음 단원에서는 로컬 캐시만 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-163">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="8614a-164">이 연습의 끝에서 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출할 때까지 변경 내용이 데이터베이스로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-164">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="8614a-165">새 Customer 엔터티 개체를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="8614a-165">To add a new Customer entity object</span></span>  
  
1.  <span data-ttu-id="8614a-166">`Customer` 메서드의 `Console.ReadLine();` 앞에 다음 코드를 추가하여 새 `Main`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-166">Create a new `Customer` by adding the following code before `Console.ReadLine();` in the `Main` method:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2.  <span data-ttu-id="8614a-167">F5 키를 눌러 솔루션을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-167">Press F5 to debug the solution.</span></span>  
  
3.  <span data-ttu-id="8614a-168">Enter 키를 **콘솔** 창 디버깅을 중지 하 고 연습을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-168">Press Enter in the **Console** window to stop debugging and continue the walkthrough.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="8614a-169">엔터티 업데이트</span><span class="sxs-lookup"><span data-stu-id="8614a-169">Updating an Entity</span></span>  
 <span data-ttu-id="8614a-170">다음 단계에서는 `Customer` 개체를 검색하고 해당 속성 중 하나를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-170">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="8614a-171">Customer 이름을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="8614a-171">To change the name of a Customer</span></span>  
  
-   <span data-ttu-id="8614a-172">`Console.ReadLine();` 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-172">Add the following code above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="8614a-173">엔터티 삭제</span><span class="sxs-lookup"><span data-stu-id="8614a-173">Deleting an Entity</span></span>  
 <span data-ttu-id="8614a-174">동일한 Customer 개체를 사용하여 첫 번째 주문을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-174">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="8614a-175">다음 코드에서는 행 간의 관계를 끊는 방법과 데이터베이스에서 행을 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-175">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span> <span data-ttu-id="8614a-176">`Console.ReadLine` 앞에 다음 코드를 추가하여 개체 삭제 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-176">Add the following code before `Console.ReadLine` to see how objects can be deleted:</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="8614a-177">행을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="8614a-177">To delete a row</span></span>  
  
-   <span data-ttu-id="8614a-178">`Console.ReadLine();` 바로 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-178">Add the following code just above `Console.ReadLine();`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="8614a-179">변경 내용을 데이터베이스로 전송</span><span class="sxs-lookup"><span data-stu-id="8614a-179">Submitting Changes to the Database</span></span>  
 <span data-ttu-id="8614a-180">개체를 만들고 업데이트 및 삭제하는 데 필요한 첫 번째 단계는 실제로 변경 내용을 데이터베이스로 전송하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-180">The final step required for creating, updating, and deleting objects, is to actually submit the changes to the database.</span></span> <span data-ttu-id="8614a-181">이 단계를 수행하지 않으면 변경 내용은 로컬에만 적용되고 쿼리 결과에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-181">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="8614a-182">변경 내용을 데이터베이스로 전송하려면</span><span class="sxs-lookup"><span data-stu-id="8614a-182">To submit changes to the database</span></span>  
  
1.  <span data-ttu-id="8614a-183">`Console.ReadLine` 바로 위에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-183">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2.  <span data-ttu-id="8614a-184">`SubmitChanges` 뒤에 다음 코드를 삽입하여 변경 내용 전송 전후의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-184">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3.  <span data-ttu-id="8614a-185">F5 키를 눌러 솔루션을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-185">Press F5 to debug the solution.</span></span>  
  
4.  <span data-ttu-id="8614a-186">Enter 키를 **콘솔** 응용 프로그램을 닫으려면 창.</span><span class="sxs-lookup"><span data-stu-id="8614a-186">Press Enter in the **Console** window to close the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8614a-187">변경 내용을 전송하여 새 고객을 추가한 후에는 이 솔루션을 있는 그대로 다시 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-187">After you have added the new customer by submitting the changes, you cannot execute this solution again as is.</span></span> <span data-ttu-id="8614a-188">솔루션을 다시 실행하려면 추가할 고객의 이름과 고객 ID를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8614a-188">To execute the solution again, change the name of the customer and customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8614a-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8614a-189">See Also</span></span>  
 [<span data-ttu-id="8614a-190">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="8614a-190">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
