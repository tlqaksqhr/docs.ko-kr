---
title: "연습: 데이터 조작(Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 09b2c74673b0126865a7536de77f99e250b3afec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-manipulating-data-visual-basic"></a><span data-ttu-id="87076-102">연습: 데이터 조작(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87076-102">Walkthrough: Manipulating Data (Visual Basic)</span></span>
<span data-ttu-id="87076-103">이 연습에서는 데이터베이스의 데이터를 추가, 수정 및 삭제하기 위한 기본 종단 간 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for adding, modifying, and deleting data in a database.</span></span> <span data-ttu-id="87076-104">Northwind 샘플 데이터베이스의 복사본을 사용하여 고객을 추가하고, 고객의 이름을 변경하고, 주문을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-104">You will use a copy of the sample Northwind database to add a customer, change the name of a customer, and delete an order.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="87076-105">이 연습은 Visual Basic 개발 설정을 사용하여 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-105">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="87076-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="87076-106">Prerequisites</span></span>  
 <span data-ttu-id="87076-107">이 연습에서는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-107">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="87076-108">이 연습에서는 전용 폴더("c:\linqtest2")를 사용하여 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-108">This walkthrough uses a dedicated folder ("c:\linqtest2") to hold files.</span></span> <span data-ttu-id="87076-109">연습을 시작하기 전에 먼저 이 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="87076-109">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="87076-110">Northwind 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="87076-110">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="87076-111">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 사이트에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-111">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="87076-112">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-112">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="87076-113">이 데이터베이스를 다운로드한 후 northwnd.mdf 파일을 c:\linqtest2 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-113">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest2 folder.</span></span>  
  
-   <span data-ttu-id="87076-114">Northwind 데이터베이스에서 생성된 Visual Basic 코드 파일</span><span class="sxs-lookup"><span data-stu-id="87076-114">A Visual Basic code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="87076-115">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 또는 SQLMetal을 사용하여 이 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-115">You can generate this file by using either the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] or the SQLMetal tool.</span></span> <span data-ttu-id="87076-116">이 연습은 다음 명령줄을 사용하여 SQLMetal 도구를 통해 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-116">This walkthrough was written by using the SQLMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="87076-117">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span><span class="sxs-lookup"><span data-stu-id="87076-117">**sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**</span></span>  
  
     <span data-ttu-id="87076-118">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87076-118">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="87076-119">개요</span><span class="sxs-lookup"><span data-stu-id="87076-119">Overview</span></span>  
 <span data-ttu-id="87076-120">이 연습은 다음과 같은 여섯 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="87076-120">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="87076-121">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="87076-121">Creating the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="87076-122">데이터베이스 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="87076-122">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="87076-123">새 Customer 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="87076-123">Creating a new customer object.</span></span>  
  
-   <span data-ttu-id="87076-124">고객의 연락처 이름 수정</span><span class="sxs-lookup"><span data-stu-id="87076-124">Modifying the contact name of a customer.</span></span>  
  
-   <span data-ttu-id="87076-125">주문 삭제</span><span class="sxs-lookup"><span data-stu-id="87076-125">Deleting an order.</span></span>  
  
-   <span data-ttu-id="87076-126">이러한 변경 내용을 Northwind 데이터베이스로 전송</span><span class="sxs-lookup"><span data-stu-id="87076-126">Submitting these changes to the Northwind database.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="87076-127">LINQ to SQL 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="87076-127">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="87076-128">이 첫 번째 작업에서는 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 프로젝트를 빌드하고 실행하는 데 필요한 참조가 들어 있는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="87076-128">In this first task, you create a [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="87076-129">LINQ to SQL 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="87076-129">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="87076-130">에 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **파일** 메뉴를 클릭 하 여 **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-130">On the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="87076-131">에 **프로젝트 형식** 창에는 **새 프로젝트** 대화 상자를 클릭 **Visual Basic**합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-131">In the **Project types** pane in the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3.  <span data-ttu-id="87076-132">**템플릿** 창에서 **콘솔 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-132">In the **Templates** pane, click **Console Application**.</span></span>  
  
4.  <span data-ttu-id="87076-133">에 **이름** 상자에서 입력 **LinqDataManipulationApp**합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-133">In the **Name** box, type **LinqDataManipulationApp**.</span></span>  
  
5.  <span data-ttu-id="87076-134">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-134">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="87076-135">LINQ 참조 및 지시문 추가</span><span class="sxs-lookup"><span data-stu-id="87076-135">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="87076-136">이 연습에서는 프로젝트에 기본적으로 설치되어 있지 않을 수 있는 어셈블리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-136">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="87076-137">경우 `System.Data.Linq` 프로젝트에 대 한 참조로 나열 되지 않은 (클릭 **모든 파일 표시** 에 **솔루션 탐색기** 확장는 **참조** 노드)에 설명 된 대로 추가 다음 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="87076-137">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="87076-138">System.Data.Linq를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="87076-138">To add System.Data.Linq</span></span>  
  
1.  <span data-ttu-id="87076-139">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **참조**, 클릭 하 고 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-139">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="87076-140">에 **참조 추가** 대화 상자를 클릭 **.NET**System.Data.Linq 어셈블리를 클릭 한 다음 클릭, **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-140">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="87076-141">어셈블리가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="87076-141">The assembly is added to the project.</span></span>  
  
3.  <span data-ttu-id="87076-142">코드 편집기에서 위에 다음 지시문을 추가 **Module1**:</span><span class="sxs-lookup"><span data-stu-id="87076-142">In the code editor, add the following directives above **Module1**:</span></span>  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="87076-143">Northwind 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="87076-143">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="87076-144">이 단계에서는 SQLMetal 도구를 사용하여 Northwind 샘플 데이터베이스에서 코드 파일을 생성했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-144">These steps assume that you have used the SQLMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="87076-145">자세한 내용은 이 연습 앞부분의 사전 요구 사항 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87076-145">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="87076-146">northwind 코드 파일을 프로젝트에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="87076-146">To add the northwind code file to the project</span></span>  
  
1.  <span data-ttu-id="87076-147">에 **프로젝트** 메뉴를 클릭 하 여 **기존 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-147">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2.  <span data-ttu-id="87076-148">에 **기존 항목 추가** 대화 상자에서 c:\linqtest2\northwind.vb로 이동한 다음 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-148">In the **Add Existing Item** dialog box, navigate to c:\linqtest2\northwind.vb, and then click **Add**.</span></span>  
  
     <span data-ttu-id="87076-149">northwind.vb 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="87076-149">The northwind.vb file is added to the project.</span></span>  
  
## <a name="setting-up-the-database-connection"></a><span data-ttu-id="87076-150">데이터베이스 연결 설정</span><span class="sxs-lookup"><span data-stu-id="87076-150">Setting Up the Database Connection</span></span>  
 <span data-ttu-id="87076-151">먼저 데이터베이스에 대한 연결을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-151">First, test your connection to the database.</span></span> <span data-ttu-id="87076-152">특히 데이터베이스 이름 Northwnd에 i 문자가 없는 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-152">Note especially that the name of the database, Northwnd, has no i character.</span></span> <span data-ttu-id="87076-153">다음 단계에서 오류를 생성하는 경우 northwind.vb 파일을 검토하여 Northwind partial 클래스의 맞춤법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-153">If you generate errors in the next steps, review the northwind.vb file to determine how the Northwind partial class is spelled.</span></span>  
  
#### <a name="to-set-up-and-test-the-database-connection"></a><span data-ttu-id="87076-154">데이터베이스 연결을 설정하고 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="87076-154">To set up and test the database connection</span></span>  
  
1.  <span data-ttu-id="87076-155">`Sub Main`에 다음 코드를 입력하거나 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-155">Type or paste the following code into `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2.  <span data-ttu-id="87076-156">이때 F5 키를 눌러 응용 프로그램을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-156">Press F5 to test the application at this point.</span></span>  
  
     <span data-ttu-id="87076-157">A **콘솔** 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="87076-157">A **Console** window opens.</span></span>  
  
     <span data-ttu-id="87076-158">Enter 키를 눌러 응용 프로그램을 닫습니다는 **콘솔** 창을 클릭 하 여 **디버깅 중지** 에 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **디버그** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="87076-158">Close the application by pressing Enter in the **Console** window, or by clicking **Stop Debugging** on the [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] **Debug** menu.</span></span>  
  
## <a name="creating-a-new-entity"></a><span data-ttu-id="87076-159">새 엔터티 만들기</span><span class="sxs-lookup"><span data-stu-id="87076-159">Creating a New Entity</span></span>  
 <span data-ttu-id="87076-160">새 엔터티를 만드는 과정은 단순합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-160">Creating a new entity is straightforward.</span></span> <span data-ttu-id="87076-161">`Customer` 키워드를 사용하여 개체(예: `New`)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-161">You can create objects (such as `Customer`) by using the `New` keyword.</span></span>  
  
 <span data-ttu-id="87076-162">이 단원과 다음 단원에서는 로컬 캐시만 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-162">In this and the following sections, you are making changes only to the local cache.</span></span> <span data-ttu-id="87076-163">이 연습의 끝에서 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출할 때까지 변경 내용이 데이터베이스로 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-163">No changes are sent to the database until you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> toward the end of this walkthrough.</span></span>  
  
#### <a name="to-add-a-new-customer-entity-object"></a><span data-ttu-id="87076-164">새 Customer 엔터티 개체를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="87076-164">To add a new Customer entity object</span></span>  
  
1.  <span data-ttu-id="87076-165">`Customer`의 `Console.ReadLine` 앞에 다음 코드를 추가하여 새 `Sub Main`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="87076-165">Create a new `Customer` by adding the following code before `Console.ReadLine` in `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2.  <span data-ttu-id="87076-166">F5 키를 눌러 솔루션을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-166">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="87076-167">콘솔 창에 표시되는 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-167">The results that are shown in the console window are as follows:</span></span>  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     <span data-ttu-id="87076-168">새 행이 결과에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-168">Note that the new row does not appear in the results.</span></span> <span data-ttu-id="87076-169">새 데이터가 아직 데이터베이스로 전송되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-169">The new data has not yet been submitted to the database.</span></span>  
  
3.  <span data-ttu-id="87076-170">Enter 키를 **콘솔** 창 디버깅을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-170">Press Enter in the **Console** window to stop debugging.</span></span>  
  
## <a name="updating-an-entity"></a><span data-ttu-id="87076-171">엔터티 업데이트</span><span class="sxs-lookup"><span data-stu-id="87076-171">Updating an Entity</span></span>  
 <span data-ttu-id="87076-172">다음 단계에서는 `Customer` 개체를 검색하고 해당 속성 중 하나를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-172">In the following steps, you will retrieve a `Customer` object and modify one of its properties.</span></span>  
  
#### <a name="to-change-the-name-of-a-customer"></a><span data-ttu-id="87076-173">Customer 이름을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="87076-173">To change the name of a Customer</span></span>  
  
-   <span data-ttu-id="87076-174">`Console.ReadLine()` 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-174">Add the following code above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a><span data-ttu-id="87076-175">엔터티 삭제</span><span class="sxs-lookup"><span data-stu-id="87076-175">Deleting an Entity</span></span>  
 <span data-ttu-id="87076-176">동일한 Customer 개체를 사용하여 첫 번째 주문을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-176">Using the same customer object, you can delete the first order.</span></span>  
  
 <span data-ttu-id="87076-177">다음 코드에서는 행 간의 관계를 끊는 방법과 데이터베이스에서 행을 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87076-177">The following code demonstrates how to sever relationships between rows, and how to delete a row from the database.</span></span>  
  
#### <a name="to-delete-a-row"></a><span data-ttu-id="87076-178">행을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="87076-178">To delete a row</span></span>  
  
-   <span data-ttu-id="87076-179">`Console.ReadLine()` 바로 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-179">Add the following code just above `Console.ReadLine()`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a><span data-ttu-id="87076-180">변경 내용을 데이터베이스로 전송</span><span class="sxs-lookup"><span data-stu-id="87076-180">Submitting Changes to the Database</span></span>  
 <span data-ttu-id="87076-181">개체를 만들고 업데이트 및 삭제하는 데 필요한 첫 번째 단계는 실제로 변경 내용을 데이터베이스로 전송하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87076-181">The final step required for creating, updating, and deleting objects is to actually submit the changes to the database.</span></span> <span data-ttu-id="87076-182">이 단계를 수행하지 않으면 변경 내용은 로컬에만 적용되고 쿼리 결과에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-182">Without this step, your changes are only local and will not appear in query results.</span></span>  
  
#### <a name="to-submit-changes-to-the-database"></a><span data-ttu-id="87076-183">변경 내용을 데이터베이스로 전송하려면</span><span class="sxs-lookup"><span data-stu-id="87076-183">To submit changes to the database</span></span>  
  
1.  <span data-ttu-id="87076-184">`Console.ReadLine` 바로 위에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-184">Insert the following code just above `Console.ReadLine`:</span></span>  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2.  <span data-ttu-id="87076-185">`SubmitChanges` 뒤에 다음 코드를 삽입하여 변경 내용 전송 전후의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87076-185">Insert the following code (after `SubmitChanges`) to show the before and after effects of submitting the changes:</span></span>  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3.  <span data-ttu-id="87076-186">F5 키를 눌러 솔루션을 디버깅합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-186">Press F5 to debug the solution.</span></span>  
  
     <span data-ttu-id="87076-187">콘솔 창이 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="87076-187">The console window appears as follows:</span></span>  
  
    ```  
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4.  <span data-ttu-id="87076-188">Enter 키를 **콘솔** 창 디버깅을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-188">Press Enter in the **Console** window to stop debugging.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87076-189">변경 내용을 전송하여 새 고객을 추가한 후에는 동일한 고객을 있는 그대로 다시 추가할 수 없으므로 이 솔루션을 있는 그대로 다시 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87076-189">After you have added the new customer by submitting the changes, you cannot execute this solution again as is, because you cannot add the same customer again as is.</span></span> <span data-ttu-id="87076-190">솔루션을 다시 실행하려면 추가할 고객 ID의 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="87076-190">To execute the solution again, change the value of the customer ID to be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87076-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87076-191">See Also</span></span>  
 [<span data-ttu-id="87076-192">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="87076-192">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
