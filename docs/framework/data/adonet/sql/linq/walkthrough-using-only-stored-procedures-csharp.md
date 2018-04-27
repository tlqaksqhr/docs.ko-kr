---
title: '연습: 저장 프로시저만 사용(C#)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 4c13e4c12abf17f995bb819ddd7d6337407e3b28
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-using-only-stored-procedures-c"></a><span data-ttu-id="9d4b4-102">연습: 저장 프로시저만 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="9d4b4-102">Walkthrough: Using Only Stored Procedures (C#)</span></span>
<span data-ttu-id="9d4b4-103">이 연습에서는 저장 프로시저만 실행하여 데이터에 액세스하기 위한 기본 종단 간 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-103">This walkthrough provides a basic end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario for accessing data by executing stored procedures only.</span></span> <span data-ttu-id="9d4b4-104">일반적으로 데이터베이스 관리자는 데이터 저장소에 액세스하는 방법을 제한하기 위해 이 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-104">This approach is often used by database administrators to limit how the datastore is accessed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d4b4-105">또한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램에서 저장 프로시저를 사용하여 특히 `Create`, `Update` 및 `Delete` 프로세스의 경우에 기본 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-105">You can also use stored procedures in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications to override default behavior, especially for `Create`, `Update`, and `Delete` processes.</span></span> <span data-ttu-id="9d4b4-106">자세한 내용은 참조 [사용자 지정 Insert, Update 및 Delete 작업](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
  
 <span data-ttu-id="9d4b4-107">이 연습에서는 Northwind 샘플 데이터베이스인 CustOrdersDetail 및 CustOrderHist의 저장 프로시저에 매핑된 두 개의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-107">For purposes of this walkthrough, you will use two methods that have been mapped to stored procedures in the Northwind sample database: CustOrdersDetail and CustOrderHist.</span></span> <span data-ttu-id="9d4b4-108">SqlMetal 명령줄 도구를 실행하여 C# 파일을 생성할 경우 매핑이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-108">The mapping occurs when you run the SqlMetal command-line tool to generate a C# file.</span></span> <span data-ttu-id="9d4b4-109">자세한 내용은 이 연습 뒷부분의 사전 요구 사항 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-109">For more information, see the Prerequisites section later in this walkthrough.</span></span>  
  
 <span data-ttu-id="9d4b4-110">이 연습에서는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에 의존하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-110">This walkthrough does not rely on the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span></span> <span data-ttu-id="9d4b4-111">Visual Studio를 사용 하는 개발자 ´ ï ´는 [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 저장된 프로시저 기능을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-111">Developers using Visual Studio can also use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to implement stored procedure functionality.</span></span> <span data-ttu-id="9d4b4-112">참조 [LINQ to SQL 도구 Visual Studio에서](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-112">See [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="9d4b4-113">이 연습은 Visual C# 개발 설정을 사용하여 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-113">This walkthrough was written by using Visual C# Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9d4b4-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="9d4b4-114">Prerequisites</span></span>  
 <span data-ttu-id="9d4b4-115">이 연습에서는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-115">This walkthrough requires the following:</span></span>  
  
-   <span data-ttu-id="9d4b4-116">이 연습에서는 파일을 보유하기 위해 전용 폴더("c:\linqtest7")가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-116">This walkthrough uses a dedicated folder ("c:\linqtest7") to hold files.</span></span> <span data-ttu-id="9d4b4-117">연습을 시작하기 전에 먼저 이 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-117">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="9d4b4-118">Northwind 샘플 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="9d4b4-118">The Northwind sample database.</span></span>  
  
     <span data-ttu-id="9d4b4-119">이 데이터베이스가 개발 컴퓨터에 없는 경우 Microsoft 다운로드 사이트에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-119">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="9d4b4-120">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-120">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="9d4b4-121">이 데이터베이스를 다운로드한 후 northwnd.mdf 파일을 c:\linqtest7 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-121">After you have downloaded the database, copy the northwnd.mdf file to the c:\linqtest7 folder.</span></span>  
  
-   <span data-ttu-id="9d4b4-122">Northwind 데이터베이스에서 생성된 C# 코드 파일</span><span class="sxs-lookup"><span data-stu-id="9d4b4-122">A C# code file generated from the Northwind database.</span></span>  
  
     <span data-ttu-id="9d4b4-123">이 연습은 다음 명령줄을 사용하여 SqlMetal 도구를 통해 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-123">This walkthrough was written by using the SqlMetal tool with the following command line:</span></span>  
  
     <span data-ttu-id="9d4b4-124">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span><span class="sxs-lookup"><span data-stu-id="9d4b4-124">**sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**</span></span>  
  
     <span data-ttu-id="9d4b4-125">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-125">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="9d4b4-126">개요</span><span class="sxs-lookup"><span data-stu-id="9d4b4-126">Overview</span></span>  
 <span data-ttu-id="9d4b4-127">이 연습은 다음과 같은 여섯 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-127">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="9d4b4-128">설정 된 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Visual Studio에서 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-128">Setting up the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="9d4b4-129">System.Data.Linq 어셈블리를 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="9d4b4-129">Adding the System.Data.Linq assembly to the project.</span></span>  
  
-   <span data-ttu-id="9d4b4-130">데이터베이스 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="9d4b4-130">Adding the database code file to the project.</span></span>  
  
-   <span data-ttu-id="9d4b4-131">데이터베이스와 연결 만들기</span><span class="sxs-lookup"><span data-stu-id="9d4b4-131">Creating a connection with the database.</span></span>  
  
-   <span data-ttu-id="9d4b4-132">사용자 인터페이스 설정</span><span class="sxs-lookup"><span data-stu-id="9d4b4-132">Setting up the user interface.</span></span>  
  
-   <span data-ttu-id="9d4b4-133">응용 프로그램 실행 및 테스트</span><span class="sxs-lookup"><span data-stu-id="9d4b4-133">Running and testing the application.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="9d4b4-134">LINQ to SQL 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="9d4b4-134">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="9d4b4-135">이 첫 번째 작업에서 빌드 및 실행 하는 데 필요한 참조가 포함 된 Visual Studio 솔루션을 만들는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-135">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="9d4b4-136">LINQ to SQL 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9d4b4-136">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="9d4b4-137">Visual Studio에서 **파일** 메뉴에서 **새로**, 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-137">On the Visual Studio **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="9d4b4-138">에 **프로젝트 형식** 창에는 **새 프로젝트** 대화 상자를 클릭 **Visual C#** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-138">In the **Project types** pane in the **New Project** dialog box, click **Visual C#**.</span></span>  
  
3.  <span data-ttu-id="9d4b4-139">**템플릿** 창에서 **Windows Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-139">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="9d4b4-140">에 **이름** 상자에서 입력 **SprocOnlyApp**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-140">In the **Name** box, type **SprocOnlyApp**.</span></span>  
  
5.  <span data-ttu-id="9d4b4-141">에 **위치** 상자, 프로젝트 파일을 저장할 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-141">In the **Location** box, verify where you want to store your project files.</span></span>  
  
6.  <span data-ttu-id="9d4b4-142">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-142">Click **OK**.</span></span>  
  
     <span data-ttu-id="9d4b4-143">Windows Forms 디자이너가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-143">The Windows Forms Designer opens.</span></span>  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a><span data-ttu-id="9d4b4-144">LINQ to SQL 어셈블리 참조 추가</span><span class="sxs-lookup"><span data-stu-id="9d4b4-144">Adding the LINQ to SQL Assembly Reference</span></span>  
 <span data-ttu-id="9d4b4-145">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 어셈블리는 표준 Windows Forms 응용 프로그램 템플릿에 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-145">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly is not included in the standard Windows Forms Application template.</span></span> <span data-ttu-id="9d4b4-146">다음 단계에 설명된 대로 이 어셈블리를 직접 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-146">You will have to add the assembly yourself, as explained in the following steps:</span></span>  
  
#### <a name="to-add-systemdatalinqdll"></a><span data-ttu-id="9d4b4-147">System.Data.Linq.dll을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="9d4b4-147">To add System.Data.Linq.dll</span></span>  
  
1.  <span data-ttu-id="9d4b4-148">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **참조**, 클릭 하 고 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-148">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="9d4b4-149">에 **참조 추가** 대화 상자를 클릭 **.NET**System.Data.Linq 어셈블리를 클릭 한 다음 클릭, **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-149">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="9d4b4-150">어셈블리가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-150">The assembly is added to the project.</span></span>  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a><span data-ttu-id="9d4b4-151">Northwind 코드 파일을 프로젝트에 추가</span><span class="sxs-lookup"><span data-stu-id="9d4b4-151">Adding the Northwind Code File to the Project</span></span>  
 <span data-ttu-id="9d4b4-152">이 단계에서는 SqlMetal 도구를 사용하여 Northwind 샘플 데이터베이스에서 코드 파일을 생성했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-152">This step assumes that you have used the SqlMetal tool to generate a code file from the Northwind sample database.</span></span> <span data-ttu-id="9d4b4-153">자세한 내용은 이 연습 앞부분의 사전 요구 사항 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-153">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a><span data-ttu-id="9d4b4-154">northwind 코드 파일을 프로젝트에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="9d4b4-154">To add the northwind code file to the project</span></span>  
  
1.  <span data-ttu-id="9d4b4-155">에 **프로젝트** 메뉴를 클릭 하 여 **기존 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-155">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
2.  <span data-ttu-id="9d4b4-156">에 **기존 항목 추가** 대화 상자에서 c:\linqtest7\northwind.cs로 이동한 다음 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-156">In the **Add Existing Item** dialog box, move to c:\linqtest7\northwind.cs, and then click **Add**.</span></span>  
  
     <span data-ttu-id="9d4b4-157">northwind.cs 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-157">The northwind.cs file is added to the project.</span></span>  
  
## <a name="creating-a-database-connection"></a><span data-ttu-id="9d4b4-158">데이터베이스 연결 만들기</span><span class="sxs-lookup"><span data-stu-id="9d4b4-158">Creating a Database Connection</span></span>  
 <span data-ttu-id="9d4b4-159">이 단계에서는 Northwind 샘플 데이터베이스에 대한 연결을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-159">In this step, you define the connection to the Northwind sample database.</span></span> <span data-ttu-id="9d4b4-160">"c:\linqtest7\northwnd.mdf"가 이 연습에서 경로로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-160">This walkthrough uses "c:\linqtest7\northwnd.mdf" as the path.</span></span>  
  
#### <a name="to-create-the-database-connection"></a><span data-ttu-id="9d4b4-161">데이터베이스 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9d4b4-161">To create the database connection</span></span>  
  
1.  <span data-ttu-id="9d4b4-162">**솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Form1.cs**, 클릭 하 고 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-162">In **Solution Explorer**, right-click **Form1.cs**, and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="9d4b4-163">다음 코드를 `Form1` 클래스에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-163">Type the following code into the `Form1` class:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## <a name="setting-up-the-user-interface"></a><span data-ttu-id="9d4b4-164">사용자 인터페이스 설정</span><span class="sxs-lookup"><span data-stu-id="9d4b4-164">Setting up the User Interface</span></span>  
 <span data-ttu-id="9d4b4-165">이 작업에서는 사용자가 저장 프로시저를 실행하여 데이터베이스의 데이터에 액세스할 수 있도록 인터페이스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-165">In this task you set up an interface so that users can execute stored procedures to access data in the database.</span></span> <span data-ttu-id="9d4b4-166">이 연습을 사용하여 개발하는 응용 프로그램에서 사용자는 응용 프로그램에 포함된 저장 프로시저를 통해서만 데이터베이스의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-166">In the applications that you are developing with this walkthrough, users can access data in the database only by using the stored procedures embedded in the application.</span></span>  
  
#### <a name="to-set-up-the-user-interface"></a><span data-ttu-id="9d4b4-167">사용자 인터페이스를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9d4b4-167">To set up the user interface</span></span>  
  
1.  <span data-ttu-id="9d4b4-168">반환이는 windows Forms 디자이너 (**Form1.cs[Design]**).</span><span class="sxs-lookup"><span data-stu-id="9d4b4-168">Return to the Windows Forms Designer (**Form1.cs[Design]**).</span></span>  
  
2.  <span data-ttu-id="9d4b4-169">**보기** 메뉴에서 **도구 상자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-169">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="9d4b4-170">도구 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-170">The toolbox opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9d4b4-171">클릭는 **AutoHide** 압정을 나머지를 수행 하는 동안 도구 상자를 열어이 섹션의 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-171">Click the **AutoHide** pushpin to keep the toolbox open while you perform the remaining steps in this section.</span></span>  
  
3.  <span data-ttu-id="9d4b4-172">두 개의 단추, 두 개의 텍스트 상자 및 두 개의 레이블을 도구 상자에서 끌어 **Form1**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-172">Drag two buttons, two text boxes, and two labels from the toolbox onto **Form1**.</span></span>  
  
     <span data-ttu-id="9d4b4-173">함께 나와 있는 그림과 같이 컨트롤을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-173">Arrange the controls as in the accompanying illustration.</span></span> <span data-ttu-id="9d4b4-174">확장 **Form1** 컨트롤을 쉽게 맞출 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-174">Expand **Form1** so that the controls fit easily.</span></span>  
  
4.  <span data-ttu-id="9d4b4-175">마우스 오른쪽 단추로 클릭 **label1**, 클릭 하 고 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-175">Right-click **label1**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="9d4b4-176">변경 된 **텍스트** 속성 **label1** 를 **Enter OrderID:** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-176">Change the **Text** property from **label1** to **Enter OrderID:**.</span></span>  
  
6.  <span data-ttu-id="9d4b4-177">에 대해 같은 방식 **label2**, 변경의 **텍스트** 속성 **label2** 를 **Enter CustomerID:** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-177">In the same way for **label2**, change the **Text** property from **label2** to **Enter CustomerID:**.</span></span>  
  
7.  <span data-ttu-id="9d4b4-178">동일한 방식으로 변경 된 **텍스트** 속성에 대 한 **button1** 를 **Order Details**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-178">In the same way, change the **Text** property for **button1** to **Order Details**.</span></span>  
  
8.  <span data-ttu-id="9d4b4-179">변경 된 **텍스트** 속성에 대 한 **button2** 를 **Order History**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-179">Change the **Text** property for **button2** to **Order History**.</span></span>  
  
     <span data-ttu-id="9d4b4-180">모든 텍스트를 볼 수 있도록 단추 컨트롤을 넓힙니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-180">Widen the button controls so that all the text is visible.</span></span>  
  
#### <a name="to-handle-button-clicks"></a><span data-ttu-id="9d4b4-181">단추 클릭을 처리하려면</span><span class="sxs-lookup"><span data-stu-id="9d4b4-181">To handle button clicks</span></span>  
  
1.  <span data-ttu-id="9d4b4-182">두 번 클릭 **Order Details** 에 **Form1** 를 button1 이벤트 처리기 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-182">Double-click **Order Details** on **Form1** to open the button1 event handler in the code editor.</span></span>  
  
2.  <span data-ttu-id="9d4b4-183">다음 코드를 `button1` 처리기에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-183">Type the following code into the `button1` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3.  <span data-ttu-id="9d4b4-184">이제 두 번 클릭 **button2** 에 **Form1** 열려는 `button2` 처리기</span><span class="sxs-lookup"><span data-stu-id="9d4b4-184">Now double-click **button2** on **Form1** to open the `button2` handler</span></span>  
  
4.  <span data-ttu-id="9d4b4-185">다음 코드를 `button2` 처리기에 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-185">Type the following code into the `button2` handler:</span></span>  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="9d4b4-186">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="9d4b4-186">Testing the Application</span></span>  
 <span data-ttu-id="9d4b4-187">이제 응용 프로그램을 테스트할 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-187">Now it is time to test your application.</span></span> <span data-ttu-id="9d4b4-188">데이터 저장소와의 연결은 두 개의 저장 프로시저가 수행할 수 있는 작업으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-188">Note that your contact with the datastore is limited to whatever actions the two stored procedures can take.</span></span> <span data-ttu-id="9d4b4-189">이러한 작업은 입력한 orderID에 대한 포함된 제품을 반환하거나 입력한 CustomerID에 대한 주문된 제품의 기록을 반환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-189">Those actions are to return the products included for any orderID you enter, or to return a history of products ordered for any CustomerID you enter.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="9d4b4-190">응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="9d4b4-190">To test the application</span></span>  
  
1.  <span data-ttu-id="9d4b4-191">F5 키를 눌러 디버깅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-191">Press F5 to start debugging.</span></span>  
  
     <span data-ttu-id="9d4b4-192">Form1이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-192">Form1 appears.</span></span>  
  
2.  <span data-ttu-id="9d4b4-193">에 **Enter OrderID** 상자에 입력 합니다 `10249`, 클릭 하 고 **Order Details**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-193">In the **Enter OrderID** box, type `10249`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="9d4b4-194">메시지 상자에는 주문 10249에 포함된 제품이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-194">A message box lists the products included in order 10249.</span></span>  
  
     <span data-ttu-id="9d4b4-195">클릭 **확인** 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-195">Click **OK** to close the message box.</span></span>  
  
3.  <span data-ttu-id="9d4b4-196">에 **Enter CustomerID** 상자에 입력 합니다 `ALFKI`, 클릭 하 고 **Order History**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-196">In the **Enter CustomerID** box, type `ALFKI`, and then click **Order History**.</span></span>  
  
     <span data-ttu-id="9d4b4-197">고객 ALFKI에 대한 주문 기록이 나열된 메시지 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-197">A message box appears that lists the order history for customer ALFKI.</span></span>  
  
     <span data-ttu-id="9d4b4-198">클릭 **확인** 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-198">Click **OK** to close the message box.</span></span>  
  
4.  <span data-ttu-id="9d4b4-199">에 **Enter OrderID** 상자에 입력 합니다 `123`, 클릭 하 고 **Order Details**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-199">In the **Enter OrderID** box, type `123`, and then click **Order Details**.</span></span>  
  
     <span data-ttu-id="9d4b4-200">"No results"가 표시된 메시지 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-200">A message box appears that displays "No results."</span></span>  
  
     <span data-ttu-id="9d4b4-201">클릭 **확인** 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-201">Click **OK** to close the message box.</span></span>  
  
5.  <span data-ttu-id="9d4b4-202">에 **디버그** 메뉴를 클릭 하 여 **디버깅을 중지**합니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-202">On the **Debug** menu, click **Stop debugging**.</span></span>  
  
     <span data-ttu-id="9d4b4-203">디버그 세션이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-203">The debug session closes.</span></span>  
  
6.  <span data-ttu-id="9d4b4-204">실험이 끝나면 경우 클릭할 수 있는 **프로젝트 닫기** 에 **파일** 메뉴에서 메시지가 표시 되는 경우 프로젝트를 저장 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-204">If you have finished experimenting, you can click **Close Project** on the **File** menu, and save your project when you are prompted.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9d4b4-205">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9d4b4-205">Next Steps</span></span>  
 <span data-ttu-id="9d4b4-206">약간의 변경을 통해 이 프로젝트를 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-206">You can enhance this project by making some changes.</span></span> <span data-ttu-id="9d4b4-207">예를 들어 목록 상자에 사용 가능한 저장 프로시저를 나열하고 사용자가 실행할 프로시저를 선택하도록 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-207">For example, you could list available stored procedures in a list box and have the user select which procedures to execute.</span></span> <span data-ttu-id="9d4b4-208">또한 보고서의 출력을 텍스트 파일에 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d4b4-208">You could also stream the output of the reports to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d4b4-209">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d4b4-209">See Also</span></span>  
 [<span data-ttu-id="9d4b4-210">연습으로 학습</span><span class="sxs-lookup"><span data-stu-id="9d4b4-210">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="9d4b4-211">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="9d4b4-211">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
