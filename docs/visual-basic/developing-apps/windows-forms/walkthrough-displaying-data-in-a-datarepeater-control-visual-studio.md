---
title: "연습: DataRepeater 컨트롤의 데이터 표시(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 93072bf30c8ee2a4a44c4862de0882072c298f8b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="37f8e-102">연습: DataRepeater 컨트롤의 데이터 표시(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="37f8e-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="37f8e-103">이 연습에서는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 바인딩된 데이터를 표시하는 작업을 처음부터 끝까지 보여 주는 기본 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="37f8e-104">필수 조건</span><span class="sxs-lookup"><span data-stu-id="37f8e-104">Prerequisite</span></span>  
 <span data-ttu-id="37f8e-105">이 연습을 수행하려면 Northwind 샘플 데이터베이스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="37f8e-106">이 데이터베이스가 개발 컴퓨터에 없는 경우 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-106">If you do not have this database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088).</span></span> <span data-ttu-id="37f8e-107">자세한 내용은 [샘플 데이터베이스 다운로드](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-107">For instructions, see [Downloading Sample Databases](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="37f8e-108">개요</span><span class="sxs-lookup"><span data-stu-id="37f8e-108">Overview</span></span>  
 <span data-ttu-id="37f8e-109">이 연습의 첫 번째 부분은 다음과 같은 네 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="37f8e-110">솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="37f8e-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="37f8e-111"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="37f8e-112">데이터 소스 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="37f8e-113">데이터 바인딩된 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="37f8e-114">DataRepeater 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="37f8e-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="37f8e-115">첫 번째 단계에서는 프로젝트 및 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="37f8e-116">DataRepeater 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="37f8e-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="37f8e-117">Visual Studio의 **파일** 메뉴에서 **새 프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="37f8e-118">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Visual Basic**을 확장하고 **Windows**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="37f8e-119">**템플릿** 창에서 **Windows Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="37f8e-120">**이름** 상자에 `DataRepeaterApp`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="37f8e-121">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="37f8e-122">Windows Forms 디자이너가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="37f8e-123">Windows Forms 디자이너에서 폼을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="37f8e-124">**속성** 창에서 **Size** 속성을 `800, 700`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="37f8e-125">DataRepeater 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="37f8e-126">이 단계에서는 폼에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="37f8e-127">DataRepeater 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="37f8e-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="37f8e-128">**보기** 메뉴에서 **도구 상자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="37f8e-129">**도구 상자** 가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="37f8e-130">**Visual Basic PowerPacks** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="37f8e-131"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 **Form1**로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="37f8e-132">속성 창에서 **Location** 속성을 `0, 25`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="37f8e-133">**Size** 속성을 `460, 600`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="37f8e-134">데이터 소스 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-134">Adding a Data Source</span></span>  
 <span data-ttu-id="37f8e-135">이 단계에서는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 대한 데이터 소스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="37f8e-136">데이터 소스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="37f8e-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="37f8e-137">**데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="37f8e-138">**데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="37f8e-139">**데이터 소스 형식 선택** 페이지에서 **데이터베이스** 를 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="37f8e-140">**데이터 연결 선택** 페이지에서 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="37f8e-141">Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="37f8e-142">또는</span><span class="sxs-lookup"><span data-stu-id="37f8e-142">-or-</span></span>  
  
    -   <span data-ttu-id="37f8e-143">**새 연결** 을 클릭하여 새 데이터 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="37f8e-144">자세한 내용은 참조 [새 연결 추가](/visualstudio/data-tools/add-new-connections)합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-144">For more information, see [Add new connections](/visualstudio/data-tools/add-new-connections).</span></span>  
  
5.  <span data-ttu-id="37f8e-145">데이터베이스에 암호가 필요하면 중요한 데이터를 포함하는 옵션을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37f8e-146">대화 상자가 나타나는 경우 **예** 를 클릭하여 프로젝트에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="37f8e-147">**응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="37f8e-148">**데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="37f8e-149">**Customers** 및 **Orders** 테이블 옆의 확인란을 선택한 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="37f8e-150">**NorthwindDataSet** 가 프로젝트에 추가되고 **Customers** 및 **Orders** 테이블이 **데이터 소스** 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="37f8e-151">데이터 바인딩된 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="37f8e-152">이 단계에서는 데이터 바인딩된 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="37f8e-153">데이터 바인딩된 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="37f8e-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="37f8e-154">**데이터 소스** 창에서 **Customers** 테이블의 최상위 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="37f8e-155">테이블 노드의 드롭다운 목록에서 **자세히** 를 클릭하여 테이블의 놓기 형식을 **자세히** 로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="37f8e-156">**Customers** 테이블 노드를 선택하고 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 항목 템플릿 영역(위쪽 영역)으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="37f8e-157"><xref:System.Windows.Forms.BindingNavigator> 컨트롤이 폼에 추가되고 **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**및 **CustomersBindingNavigator** 구성 요소가 구성 요소 트레이에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="37f8e-158">모든 필드와 해당 레이블을 선택하고 항목 템플릿 영역 왼쪽 가장자리 근처에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="37f8e-159">마지막 다섯 개의 필드(**Region**, **Postal Code**, **Country**, **Phone**및 **Fax**)와 해당 레이블을 선택하고 첫 번째 여섯 개 필드의 오른쪽 위로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="37f8e-160">항목 템플릿(컨트롤의 위쪽 영역)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="37f8e-161">속성 창에서 **Size** 속성을 `427, 170`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="37f8e-162">이 시점에서 작동 중인 응용 프로그램에서는 고객의 반복 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="37f8e-163">F5 키를 눌러 응용 프로그램을 실행하고, 데이터를 변경하고, 고객 레코드를 추가 또는 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="37f8e-164">다음 선택적 단계에서는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 사용자 지정하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="37f8e-165">다음 단계(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="37f8e-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="37f8e-166">이 연습 부분은 다음과 같은 네 가지 선택적인 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="37f8e-167"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 모양 변경</span><span class="sxs-lookup"><span data-stu-id="37f8e-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="37f8e-168">사용자가 레코드를 추가하거나 삭제하지 못하도록 지정</span><span class="sxs-lookup"><span data-stu-id="37f8e-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="37f8e-169"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="37f8e-170"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 마스터 및 세부 테이블 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="37f8e-171">DataRepeater 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="37f8e-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="37f8e-172">이 선택적 단계에서는 디자인 타임에 `BackColor` 컨트롤의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="37f8e-173">또한 행을 다른 색으로 표시하고 조건에 따라 레이블의 `ForeColor` 를 변경하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="37f8e-174">컨트롤의 모양을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="37f8e-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="37f8e-175">Windows Forms 디자이너에서 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 주(아래쪽) 영역을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="37f8e-176">속성 창에서 `BackColor` 속성을 흰색으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="37f8e-177"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 를 두 번 클릭하여 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="37f8e-178">코드 편집기의 이벤트 드롭다운 목록에서 **DrawItem**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="37f8e-179"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트 처리기에서 `BackColor`를 대체하는 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  <span data-ttu-id="37f8e-180"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 이벤트 처리기에서 조건에 따라 레이블의 `ForeColor` 를 변경하는 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-180">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  <span data-ttu-id="37f8e-181">F5 키를 눌러 응용 프로그램을 실행하고 사용자 지정 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-181">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="37f8e-182">사용자가 레코드를 추가하거나 삭제하지 못하도록 지정</span><span class="sxs-lookup"><span data-stu-id="37f8e-182">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="37f8e-183">이 선택적 단계에서는 사용자가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 레코드를 추가하거나 삭제하지 못하도록 지정하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-183">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="37f8e-184">사용자가 레코드를 추가하거나 삭제하지 못하도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="37f8e-184">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="37f8e-185">Windows Forms 디자이너에서 폼을 두 번 클릭하여 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-185">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="37f8e-186">`Form_Load` 이벤트에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-186">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  <span data-ttu-id="37f8e-187">클래스 이름 드롭다운 목록에서 **BindingNavigatorDeleteItem**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-187">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="37f8e-188">메서드 이름 드롭다운 목록에서 **EnabledChanged**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-188">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="37f8e-189">다음 코드를 `BindingNavigatorDeleteItem_EnabledChanged` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-189">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="37f8e-190"><xref:System.Windows.Forms.BindingSource> 로 인해 현재 레코드가 변경될 때마다 **DeleteItem** 단추가 활성화되므로 이 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-190">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="37f8e-191">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-191">Press F5 to run the application.</span></span> <span data-ttu-id="37f8e-192">**DeleteItem** 단추가 비활성화되므로 사용자가 Delete 키를 눌러 항목을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-192">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="37f8e-193">DataRepeater 컨트롤에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-193">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="37f8e-194">이 선택적 단계에서는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에서 값을 검색하는 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-194">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="37f8e-195">검색 문자열이 발견되면 컨트롤에서 값을 포함하는 항목을 선택하고 항목을 뷰로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-195">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="37f8e-196">검색 기능을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="37f8e-196">To add search capability</span></span>  
  
1.  <span data-ttu-id="37f8e-197"><xref:System.Windows.Forms.TextBox> 도구 상자 **에서** 컨트롤이 포함된 폼으로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-197">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="37f8e-198">이 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 아래에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-198">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="37f8e-199">속성 창에서 **Name** 속성을 **SearchTextBox**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-199">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="37f8e-200"><xref:System.Windows.Forms.Button> 도구 상자 **에서** 컨트롤이 포함된 폼으로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-200">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="37f8e-201">이 컨트롤을 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤 아래에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-201">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="37f8e-202">속성 창에서 **Name** 속성을 **SearchButton**으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-202">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="37f8e-203">**Text** 속성을 **Search**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-203">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="37f8e-204"><xref:System.Windows.Forms.Button> 컨트롤을 두 번 클릭하여 코드 편집기를 열고 `SearchButton_Click` 이벤트 처리기에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-204">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  <span data-ttu-id="37f8e-205">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-205">Press F5 to run the application.</span></span> <span data-ttu-id="37f8e-206">**SearchTextBox** 에 고객 ID를 입력하고 **Search** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-206">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="37f8e-207">DataRepeater에 마스터 및 세부 테이블 추가</span><span class="sxs-lookup"><span data-stu-id="37f8e-207">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="37f8e-208">이 선택적 단계에서는 각 고객에 대한 관련 주문을 표시하는 두 번째 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-208">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="37f8e-209">마스터 및 세부 테이블을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="37f8e-209">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="37f8e-210"><xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 도구 상자 **의** Visual Basic PowerPacks **탭에서 폼으로 두 번째** 컨트롤을 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-210">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="37f8e-211">속성 창에서 **Location** 속성을 `465, 25`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-211">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="37f8e-212">**Size** 속성을 `315, 600`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-212">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="37f8e-213">**데이터 소스** 창에서 **Customers** 테이블 노드를 확장하고 **Orders** 테이블에 대한 상세 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-213">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="37f8e-214">테이블 노드의 드롭다운 목록에서 자세히를 클릭하여 이 **Orders** 테이블의 놓기 형식을 **자세히** 로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-214">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="37f8e-215">이 **Orders** 테이블 노드를 두 번째 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤의 항목 템플릿 영역(위쪽 영역)으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-215">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="37f8e-216">**OrdersBindingSource** 구성 요소 및 **OrdersTableAdapter** 구성 요소가 구성 요소 트레이에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-216">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="37f8e-217">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-217">Press F5 to run the application.</span></span> <span data-ttu-id="37f8e-218">F5 키를 눌러 응용 프로그램을 실행합니다. 첫 번째 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에서 각 고객을 선택하면 해당 고객에 대한 주문이 두 번째 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 컨트롤에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37f8e-218">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f8e-219">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37f8e-219">See Also</span></span>  
 [<span data-ttu-id="37f8e-220">DataRepeater 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="37f8e-220">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="37f8e-221">방법: DataRepeater 컨트롤의 바인딩된 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="37f8e-221">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="37f8e-222">방법: DataRepeater 컨트롤의 바인딩되지 않은 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="37f8e-222">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="37f8e-223">방법: DataRepeater 컨트롤의 레이아웃 변경</span><span class="sxs-lookup"><span data-stu-id="37f8e-223">How to: Change the Layout of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="37f8e-224">방법: DataRepeater 컨트롤의 항목 머리글 표시</span><span class="sxs-lookup"><span data-stu-id="37f8e-224">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="37f8e-225">방법: DataRepeater 컨트롤의 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="37f8e-225">How to: Search Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="37f8e-226">방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터/세부 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="37f8e-226">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="37f8e-227">방법: DataRepeater 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="37f8e-227">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="37f8e-228">방법: DataRepeater 항목 추가 및 삭제 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="37f8e-228">How to: Disable Adding and Deleting DataRepeater Items</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [<span data-ttu-id="37f8e-229">DataRepeater 컨트롤 문제 해결</span><span class="sxs-lookup"><span data-stu-id="37f8e-229">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
