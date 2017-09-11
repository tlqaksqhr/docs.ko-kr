---
title: "연습: DataRepeater 컨트롤 (Visual Studio)의 데이터 표시 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b795b8f3bb42aecdbdfade62f4943239fec6eac4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="a8585-102">연습: DataRepeater 컨트롤의 데이터 표시(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="a8585-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="a8585-103">이 연습에서는의 바인딩된 데이터를 표시 하기 위한 기본 시작 후 완료 시나리오를 제공 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="a8585-104">필수 조건</span><span class="sxs-lookup"><span data-stu-id="a8585-104">Prerequisite</span></span>  
 <span data-ttu-id="a8585-105">이 연습을 수행하려면 Northwind 샘플 데이터베이스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="a8585-106">이 데이터베이스가 개발 컴퓨터에 없는 경우 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-106">If you do not have this database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088).</span></span> <span data-ttu-id="a8585-107">자세한 내용은 [샘플 데이터베이스 다운로드](https://msdn.microsoft.com/library/bb399411)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a8585-108">개요</span><span class="sxs-lookup"><span data-stu-id="a8585-108">Overview</span></span>  
 <span data-ttu-id="a8585-109">이 연습의 첫 번째 부분은 다음과 같은 네 가지 주요 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="a8585-110">솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="a8585-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="a8585-111">추가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="a8585-112">데이터 소스 추가</span><span class="sxs-lookup"><span data-stu-id="a8585-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="a8585-113">데이터 바인딩된 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="a8585-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="a8585-114">DataRepeater 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="a8585-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="a8585-115">첫 번째 단계에서는 프로젝트 및 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="a8585-116">DataRepeater 솔루션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="a8585-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="a8585-117">Visual Studio의 **파일** 메뉴에서 **새 프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="a8585-118">**새 프로젝트** 대화 상자의 **프로젝트 형식** 창에서 **Visual Basic**을 확장하고 **Windows**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="a8585-119">**템플릿** 창에서 **Windows Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="a8585-120">**이름** 상자에 `DataRepeaterApp`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="a8585-121">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="a8585-122">Windows Forms 디자이너가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="a8585-123">Windows Forms 디자이너에서 폼을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="a8585-124">**속성** 창에서 **Size** 속성을 `800, 700`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="a8585-125">DataRepeater 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="a8585-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="a8585-126">이 단계에서는 추가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>컨트롤을 폼.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="a8585-127">DataRepeater 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a8585-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="a8585-128">**보기** 메뉴에서 **도구 상자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="a8585-129">**도구 상자** 가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="a8585-130">**Visual Basic PowerPacks** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="a8585-131">끌기는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>컨트롤을 끌어와 **Form1**.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="a8585-132">속성 창에서 **Location** 속성을 `0, 25`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="a8585-133">**Size** 속성을 `460, 600`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="a8585-134">데이터 소스 추가</span><span class="sxs-lookup"><span data-stu-id="a8585-134">Adding a Data Source</span></span>  
 <span data-ttu-id="a8585-135">에 대 한 데이터 원본을 추가 하면이 단계는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="a8585-136">데이터 소스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a8585-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="a8585-137">**데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="a8585-138">**데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="a8585-139">**데이터 소스 형식 선택** 페이지에서 **데이터베이스** 를 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a8585-140">**데이터 연결 선택** 페이지에서 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="a8585-141">Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="a8585-142">또는</span><span class="sxs-lookup"><span data-stu-id="a8585-142">-or-</span></span>  
  
    -   <span data-ttu-id="a8585-143">**새 연결** 을 클릭하여 새 데이터 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="a8585-144">자세한 내용은 참조 [하는 방법: SQL Server 데이터베이스에 대 한 연결 만들기](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d)합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-144">For more information, see [How to: Create Connections to SQL Server Databases](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span></span>  
  
5.  <span data-ttu-id="a8585-145">데이터베이스에 암호가 필요하면 중요한 데이터를 포함하는 옵션을 선택하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a8585-146">대화 상자가 나타나는 경우 **예** 를 클릭하여 프로젝트에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="a8585-147">**응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="a8585-148">**데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="a8585-149">**Customers** 및 **Orders** 테이블 옆의 확인란을 선택한 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="a8585-150">**NorthwindDataSet** 가 프로젝트에 추가되고 **Customers** 및 **Orders** 테이블이 **데이터 소스** 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="a8585-151">데이터 바인딩된 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="a8585-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="a8585-152">이 단계에서는 데이터 바인딩된 컨트롤에 추가한 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="a8585-153">데이터 바인딩된 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a8585-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="a8585-154">**데이터 소스** 창에서 **Customers** 테이블의 최상위 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="a8585-155">테이블 노드의 드롭다운 목록에서 **자세히** 를 클릭하여 테이블의 놓기 형식을 **자세히** 로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="a8585-156">선택 된 **고객** 노드 테이블의 항목 템플릿 영역 (위쪽 영역)으로 끌어와 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="a8585-157">A <xref:System.Windows.Forms.BindingNavigator>폼에 컨트롤이 추가 되 고 **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, 및 **CustomersBindingNavigator** 구성 요소가 구성 요소 트레이에 추가 됩니다.</xref:System.Windows.Forms.BindingNavigator></span><span class="sxs-lookup"><span data-stu-id="a8585-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="a8585-158">모든 필드와 해당 레이블을 선택하고 항목 템플릿 영역 왼쪽 가장자리 근처에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="a8585-159">마지막 다섯 개의 필드(**Region**, **Postal Code**, **Country**, **Phone**및 **Fax**)와 해당 레이블을 선택하고 첫 번째 여섯 개 필드의 오른쪽 위로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="a8585-160">항목 템플릿(컨트롤의 위쪽 영역)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="a8585-161">속성 창에서 **Size** 속성을 `427, 170`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="a8585-162">이 시점에서 작동 중인 응용 프로그램에서는 고객의 반복 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="a8585-163">F5 키를 눌러 응용 프로그램을 실행하고, 데이터를 변경하고, 고객 레코드를 추가 또는 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="a8585-164">다음 단계에서 사용자 지정 하는 방법을 배우게 됩니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="a8585-165">다음 단계(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a8585-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="a8585-166">이 연습 부분은 다음과 같은 네 가지 선택적인 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="a8585-167">모양을 변경 하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="a8585-168">사용자가 레코드를 추가하거나 삭제하지 못하도록 지정</span><span class="sxs-lookup"><span data-stu-id="a8585-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="a8585-169">에 검색 기능 추가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="a8585-170">마스터 / 세부 테이블을 추가 하는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="a8585-171">DataRepeater 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="a8585-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="a8585-172">이 선택적 단계에서 변경 된 `BackColor` 의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>디자인 타임에 컨트롤.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="a8585-173">또한 행을 다른 색으로 표시하고 조건에 따라 레이블의 `ForeColor` 를 변경하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="a8585-174">컨트롤의 모양을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="a8585-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="a8585-175">Windows Forms 디자이너에서의 주 (아래쪽) 영역을 선택 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="a8585-176">속성 창에서 `BackColor` 속성을 흰색으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="a8585-177">두 번 클릭 하 여 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>코드 편집기를 엽니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="a8585-178">코드 편집기의 이벤트 드롭다운 목록에서 **DrawItem**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="a8585-179">에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>이벤트 처리기에 다음 코드를 추가 `BackColor`:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem></span><span class="sxs-lookup"><span data-stu-id="a8585-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     <span data-ttu-id="a8585-180">[!code-cs[#1 VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8585-180">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]</span></span>  
  
6.  <span data-ttu-id="a8585-181">에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>이벤트 처리기를 변경 하려면 다음 코드를 추가 `ForeColor` 조건에 따라 레이블:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem></span><span class="sxs-lookup"><span data-stu-id="a8585-181">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     <span data-ttu-id="a8585-182">[!code-cs[#2 VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8585-182">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]</span></span>  
  
7.  <span data-ttu-id="a8585-183">F5 키를 눌러 응용 프로그램을 실행하고 사용자 지정 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-183">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="a8585-184">사용자가 레코드를 추가하거나 삭제하지 못하도록 지정</span><span class="sxs-lookup"><span data-stu-id="a8585-184">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="a8585-185">이 선택적 단계를 추가 하거나 레코드를 삭제 하지 못하도록 하는 코드 추가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-185">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="a8585-186">사용자가 레코드를 추가하거나 삭제하지 못하도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="a8585-186">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="a8585-187">Windows Forms 디자이너에서 폼을 두 번 클릭하여 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-187">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="a8585-188">`Form_Load` 이벤트에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-188">Add the following code to the `Form_Load` event:</span></span>  
  
     <span data-ttu-id="a8585-189">[!code-cs[#3 VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8585-189">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]</span></span>  
  
3.  <span data-ttu-id="a8585-190">클래스 이름 드롭다운 목록에서 **BindingNavigatorDeleteItem**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-190">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="a8585-191">메서드 이름 드롭다운 목록에서 **EnabledChanged**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-191">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="a8585-192">다음 코드를 `BindingNavigatorDeleteItem_EnabledChanged` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-192">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     <span data-ttu-id="a8585-193">[!code-cs[#4 VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8585-193">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a8585-194">이 단계는 필요 하기 때문에 <xref:System.Windows.Forms.BindingSource>하면는 **DeleteItem** 현재 레코드가 변경 될 때마다 단추.</xref:System.Windows.Forms.BindingSource></span><span class="sxs-lookup"><span data-stu-id="a8585-194">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="a8585-195">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-195">Press F5 to run the application.</span></span> <span data-ttu-id="a8585-196">**DeleteItem** 단추가 비활성화되므로 사용자가 Delete 키를 눌러 항목을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-196">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="a8585-197">DataRepeater 컨트롤에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="a8585-197">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="a8585-198">이 선택적 단계에서 값을 검색 하는 기능을 구현는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-198">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="a8585-199">검색 문자열이 발견되면 컨트롤에서 값을 포함하는 항목을 선택하고 항목을 뷰로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-199">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="a8585-200">검색 기능을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a8585-200">To add search capability</span></span>  
  
1.  <span data-ttu-id="a8585-201">끌기는 <xref:System.Windows.Forms.TextBox>에서 제어는 **도구 상자** 포함 된 양식에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>컨트롤.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="a8585-201">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="a8585-202">아래에 배치 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-202">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="a8585-203">속성 창에서 **Name** 속성을 **SearchTextBox**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-203">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="a8585-204">끌기는 <xref:System.Windows.Forms.Button>에서 제어는 **도구 상자** 포함 된 양식에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>컨트롤.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="a8585-204">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="a8585-205">아래에 배치 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-205">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="a8585-206">속성 창에서 **Name** 속성을 **SearchButton**으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-206">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="a8585-207">**Text** 속성을 **Search**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-207">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="a8585-208">두 번 클릭은 <xref:System.Windows.Forms.Button>코드 편집기를 열려면 제어 하 고 다음 코드를 추가 하는 `SearchButton_Click` 이벤트 처리기입니다.</xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="a8585-208">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     <span data-ttu-id="a8585-209">[!code-cs[#5 VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough&#5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8585-209">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]</span></span>  
  
6.  <span data-ttu-id="a8585-210">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-210">Press F5 to run the application.</span></span> <span data-ttu-id="a8585-211">**SearchTextBox** 에 고객 ID를 입력하고 **Search** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-211">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="a8585-212">DataRepeater에 마스터 및 세부 테이블 추가</span><span class="sxs-lookup"><span data-stu-id="a8585-212">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="a8585-213">이 선택적 단계에서는 두 번째 추가 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>컨트롤을 각 고객에 대 한 관련된 주문을 표시 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-213">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="a8585-214">마스터 및 세부 테이블을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="a8585-214">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="a8585-215">초를 끌어 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 양식에.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-215">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="a8585-216">속성 창에서 **Location** 속성을 `465, 25`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-216">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="a8585-217">**Size** 속성을 `315, 600`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-217">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="a8585-218">**데이터 소스** 창에서 **Customers** 테이블 노드를 확장하고 **Orders** 테이블에 대한 상세 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-218">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="a8585-219">테이블 노드의 드롭다운 목록에서 자세히를 클릭하여 이 **Orders** 테이블의 놓기 형식을 **자세히** 로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-219">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="a8585-220">이 끌어 **주문** 테이블 노드를 두 번째 항목 템플릿 영역 (위쪽 영역)로 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-220">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="a8585-221">**OrdersBindingSource** 구성 요소 및 **OrdersTableAdapter** 구성 요소가 구성 요소 트레이에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-221">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="a8585-222">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8585-222">Press F5 to run the application.</span></span> <span data-ttu-id="a8585-223">첫 번째에서 각 고객을 선택 하면 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>컨트롤 주문이 두 번째에 표시 되는 해당 고객 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>제어 합니다.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="a8585-223">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8585-224">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8585-224">See Also</span></span>  
 <span data-ttu-id="a8585-225">[DataRepeater 컨트롤 소개](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a8585-225">[Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="a8585-226"> [방법: DataRepeater 컨트롤의 바인딩된 데이터 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a8585-226"> [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="a8585-227"> [방법: 바인딩되지 않은 DataRepeater 컨트롤의 컨트롤 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a8585-227"> [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="a8585-228"> [방법: DataRepeater 컨트롤의 레이아웃 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a8585-228"> [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="a8585-229"> [방법: DataRepeater 컨트롤의 항목 머리글 표시](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a8585-229"> [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="a8585-230"> [방법: DataRepeater 컨트롤의 데이터 검색](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a8585-230"> [How to: Search Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="a8585-231"> [방법: 두 DataRepeater 컨트롤 (Visual Studio)를 사용 하 여 마스터/세부 폼 만들기](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span><span class="sxs-lookup"><span data-stu-id="a8585-231"> [How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span></span>  
<span data-ttu-id="a8585-232"> [방법: DataRepeater 컨트롤의 모양 변경](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a8585-232"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="a8585-233"> [방법: DataRepeater 항목 추가 및 삭제 사용 안 함](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="a8585-233"> [How to: Disable Adding and Deleting DataRepeater Items](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md) </span></span>  
<span data-ttu-id="a8585-234"> [DataRepeater 컨트롤 문제 해결](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="a8585-234"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
