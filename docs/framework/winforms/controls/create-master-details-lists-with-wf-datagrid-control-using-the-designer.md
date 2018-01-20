---
title: "방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f1526a6e54078ea3dc0500c39a8fc2feda44d901
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a><span data-ttu-id="03fa7-102">방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 마스터-세부 목록 만들기</span><span class="sxs-lookup"><span data-stu-id="03fa7-102">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="03fa7-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="03fa7-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03fa7-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="03fa7-105">경우에 <xref:System.Data.DataSet> 계열이 관련된 테이블의 두 사용할 수 있습니다 <xref:System.Windows.Forms.DataGrid> 마스터-세부 형식으로 데이터를 표시 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master-detail format.</span></span> <span data-ttu-id="03fa7-106">하나의 <xref:System.Windows.Forms.DataGrid> 는 마스터 데이터에 지정 된을 두 번째 세부 정보 표에서 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="03fa7-107">목록에 항목을 선택 하면 관련된 자식 항목 모두 세부 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="03fa7-108">예를 들어 경우 프로그램 <xref:System.Data.DataSet> Customers 테이블 및 관련된 Orders 테이블을 포함 하는 마스터 데이터 Customers 테이블과 Orders 테이블에는 세부 정보 창 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="03fa7-109">마스터 모눈에서 고객을 선택 하면 Orders 테이블에서 해당 고객과 관련 된 주문의 모든 세부 정보 창에 표시 될.</span><span class="sxs-lookup"><span data-stu-id="03fa7-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
 <span data-ttu-id="03fa7-110">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="03fa7-110">The following procedure requires a **Windows Application** project.</span></span> <span data-ttu-id="03fa7-111">이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-111">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03fa7-112">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="03fa7-113">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="03fa7-114">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03fa7-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a><span data-ttu-id="03fa7-115">디자이너에서 마스터-세부 목록을 만들려면</span><span class="sxs-lookup"><span data-stu-id="03fa7-115">To create a master-details list in the designer</span></span>  
  
1.  <span data-ttu-id="03fa7-116">두 개의 추가 <xref:System.Windows.Forms.DataGrid> 폼에 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-116">Add two <xref:System.Windows.Forms.DataGrid> controls to the form.</span></span> <span data-ttu-id="03fa7-117">자세한 내용은 참조 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-117">For more information, see [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="03fa7-118">[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> 내에 **도구 상자** 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-118">In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="03fa7-119">자세한 내용은 참조 [하는 방법: 도구 상자에 항목 추가](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-119">For more information, see [How to: Add Items to the Toolbox](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="03fa7-120">다음 단계에 해당 하지 않는 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]를 사용 하는 **데이터 원본** 디자인 타임 데이터 바인딩에 대 한 창.</span><span class="sxs-lookup"><span data-stu-id="03fa7-120">The following steps are not applicable to [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], which uses the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="03fa7-121">자세한 내용은 참조 [Visual Studio에서 데이터에 컨트롤 바인딩](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) 및 [하는 방법: Windows Forms 응용 프로그램에 관련 데이터 표시](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-121">For more information, see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) and [How to: Display Related Data in a Windows Forms Application](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).</span></span>  
  
2.  <span data-ttu-id="03fa7-122">두 개 이상의 테이블을 끌어 **서버 탐색기** 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-122">Drag two or more tables from **Server Explorer** to the form.</span></span>  
  
3.  <span data-ttu-id="03fa7-123">**데이터** 메뉴 선택 **데이터 집합 생성**합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-123">From the **Data** menu, select **Generate DataSet**.</span></span>  
  
4.  <span data-ttu-id="03fa7-124">XML 디자이너를 사용 하 여 테이블 간의 관계를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-124">Set the relationships between the tables using the XML Designer.</span></span> <span data-ttu-id="03fa7-125">세부 정보를 참조 하십시오. "하는 방법:-다 만들 XML 스키마 및 데이터 집합의 관계" msdn 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-125">For details, see "How to: Create One-to-Many Relationships in XML Schemas and Datasets" on MSDN.</span></span>  
  
5.  <span data-ttu-id="03fa7-126">관계를 선택 하 여 저장 **모두 저장** 에서 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="03fa7-126">Save the relationships by selecting **Save All** from the **File** menu.</span></span>  
  
6.  <span data-ttu-id="03fa7-127">구성의 <xref:System.Windows.Forms.DataGrid> 컨트롤에는 마스터 데이터를 다음과 같이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-127">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the master grid, as follows:</span></span>  
  
    1.  <span data-ttu-id="03fa7-128">선택 된 <xref:System.Data.DataSet> 드롭 다운 목록에서는 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-128">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>  
  
    2.  <span data-ttu-id="03fa7-129">마스터 테이블 (예를 들어 "Customers")에서 드롭 다운 목록에서 선택 된 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-129">Select the master table (for example, "Customers") from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span>  
  
7.  <span data-ttu-id="03fa7-130">구성의 <xref:System.Windows.Forms.DataGrid> 컨트롤에는 세부 정보 창에 다음과 같이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-130">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the details grid, as follows:</span></span>  
  
    1.  <span data-ttu-id="03fa7-131">선택 된 <xref:System.Data.DataSet> 드롭 다운 목록에서는 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-131">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>  
  
    2.  <span data-ttu-id="03fa7-132">드롭다운 목록에서 마스터 및 세부 테이블 간의 관계 (예: "Customers.CustOrd")를 선택는 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-132">Select the relationship (for example, "Customers.CustOrd") between the master and detail tables from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span> <span data-ttu-id="03fa7-133">관계를 확인 하려면 더하기에서을 클릭 하 여 노드를 확장 (**+**) 드롭 다운 목록에서 마스터 테이블에 기호를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fa7-133">In order to see the relationship, expand the node by clicking on the plus (**+**) sign next to the master table in the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03fa7-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03fa7-134">See Also</span></span>  
 [<span data-ttu-id="03fa7-135">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="03fa7-135">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="03fa7-136">DataGrid 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="03fa7-136">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="03fa7-137">방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="03fa7-137">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [<span data-ttu-id="03fa7-138">Visual Studio에서 데이터에 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="03fa7-138">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
