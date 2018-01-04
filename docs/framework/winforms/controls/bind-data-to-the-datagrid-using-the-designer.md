---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 데이터 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a31b407360467f37c2e60b1a3f4f4c72e80e13a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="3629c-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="3629c-102">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="3629c-103">디자이너를 사용 하 여 연결할 수는 <xref:System.Windows.Forms.DataGridView> 데이터베이스, 비즈니스 개체 또는 웹 서비스를 포함 하는 여러 다른 종류의 데이터 원본에 대 한 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-103">You can use the designer to connect a <xref:System.Windows.Forms.DataGridView> control to data sources of several different varieties, including databases, business objects, or Web services.</span></span> <span data-ttu-id="3629c-104">컨트롤에 자동으로 바인딩되어 디자이너를 사용 하 여 데이터 소스에 컨트롤을 바인딩하는 경우는 <xref:System.Windows.Forms.BindingSource> 데이터 원본을 나타내는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-104">When you bind the control to a data source using the designer, the control is automatically bound to a <xref:System.Windows.Forms.BindingSource> component that represents the data source.</span></span> <span data-ttu-id="3629c-105">또한 열은 데이터 소스에서 제공하는 스키마 정보와 일치하는 컨트롤에 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-105">Additionally, columns are automatically generated in the control to match the schema information provided by the data source.</span></span>  
  
 <span data-ttu-id="3629c-106">열을 생성한 후에 사용자 요구에 맞게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-106">After columns have been generated, you can modify them to meet your needs.</span></span> <span data-ttu-id="3629c-107">예를 들어 표시하지 않아도 되는 열을 제거하거나 숨길 수 있습니다. 열을 다시 정렬하거나 열 형식을 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-107">For example, you can remove or hide columns you are not interested in displaying, you can rearrange the columns, or you can modify the column types.</span></span> <span data-ttu-id="3629c-108">열을 수정하는 방법에 대한 자세한 내용은 [참고 항목] 섹션에 나열된 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3629c-108">For more information about modifying columns, see the topics listed in the See Also section.</span></span>  
  
 <span data-ttu-id="3629c-109">여러 바인딩할 수도 있습니다 <xref:System.Windows.Forms.DataGridView> 마스터/세부 관계를 만들기 위해 관련된 테이블에는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-109">You can also bind multiple <xref:System.Windows.Forms.DataGridView> controls to related tables to create master/detail relationships.</span></span> <span data-ttu-id="3629c-110">이 구성에서 하나의 컨트롤은 부모 테이블을 표시하고 다른 컨트롤은 부모 테이블에 있는 현재 행에 관련된 자식 테이블의 해당 행만을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-110">In this configuration, one control displays a parent table and another control displays only those rows from a child table that are related to the current row in the parent table.</span></span> <span data-ttu-id="3629c-111">자세한 내용은 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3629c-111">For more information, see [How to: Display Related Data in a Windows Forms Application](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).</span></span>  
  
 <span data-ttu-id="3629c-112">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 하는 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGridView> 컨트롤 또는 마스터/세부 관계에 대 한 컨트롤을 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-112">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.DataGridView> control or two controls for a master/detail relationship.</span></span> <span data-ttu-id="3629c-113">이러한 프로젝트를 시작하는 방법에 대한 정보는 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3629c-113">For information about starting such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3629c-114">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-114">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3629c-115">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-115">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3629c-116">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3629c-116">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-bind-the-control-to-a-data-source"></a><span data-ttu-id="3629c-117">데이터 소스에 컨트롤을 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="3629c-117">To bind the control to a data source</span></span>  
  
1.  <span data-ttu-id="3629c-118">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 오른쪽 위 모서리에는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-118">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
2.  <span data-ttu-id="3629c-119">**데이터 소스 선택** 옵션에서 드롭다운 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-119">Click the drop-down arrow for the **Choose Data Source** option.</span></span>  
  
3.  <span data-ttu-id="3629c-120">프로젝트에 데이터 소스가 아직 없는 경우 **프로젝트 데이터 소스 추가**를 클릭하고 마법사에 의해 표시된 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-120">If your project does not already have a data source, click **Add Project Data Source** and follow the steps indicated by the wizard.</span></span>  
  
     <span data-ttu-id="3629c-121">자세한 내용은 [데이터 소스 구성 마법사](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3629c-121">For more information, see [Data Source Configuration Wizard](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f).</span></span> <span data-ttu-id="3629c-122">새 데이터 소스은 **데이터 소스 선택** 드롭다운 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-122">Your new data source will appear in the **Choose Data Source** drop-down window.</span></span> <span data-ttu-id="3629c-123">새 데이터 소스에 단일 데이터베이스 테이블과 같은 하나의 구성원만이 포함되는 경우 컨트롤은 해당 구성원에 자동으로 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-123">If your new data source contains only one member, such as a single database table, the control will automatically bind to that member.</span></span> <span data-ttu-id="3629c-124">그렇지 않으면 다음 단계를 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-124">Otherwise, continue to the next step.</span></span>  
  
4.  <span data-ttu-id="3629c-125">**기타 데이터 소스** 및 **프로젝트 데이터 소스** 노드가 아직 확장되지 않은 경우 확장한 다음 컨트롤을 바인딩할 데이터 소스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-125">Expand the **Other Data Sources** and **Project Data Sources** nodes if they are not already expanded, and then select the data source to bind the control to.</span></span>  
  
5.  <span data-ttu-id="3629c-126">데이터 소스에 두 개 이상의 멤버, 예: if 만든 경우는 <xref:System.Data.DataSet?displayProperty=nameWithType> 여러 테이블을 포함 하, 데이터 소스를 확장 한 다음에 바인딩할 특정 멤버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-126">If your data source contains more than one member, such as if you have created a <xref:System.Data.DataSet?displayProperty=nameWithType> that contains multiple tables, expand the data source, and then select the specific member to bind to.</span></span>  
  
6.  <span data-ttu-id="3629c-127">마스터/세부 관계를 만들려면는 **데이터 소스 선택** 두 번째에 대 한 드롭다운 창 <xref:System.Windows.Forms.DataGridView> 컨트롤을 확장 하 고는 <xref:System.Windows.Forms.BindingSource> 부모 테이블에 대해 생성 한 다음 목록에서 관련된 자식 테이블을 선택 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-127">To create a master/detail relationship, in the **Choose Data Source** drop-down window for a second <xref:System.Windows.Forms.DataGridView> control, expand the <xref:System.Windows.Forms.BindingSource> created for the parent table, and then select the related child table from the list shown.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3629c-128">프로젝트에 데이터 소스가 이미 있으면 **데이터 소스** 창을 사용하여 데이터 양식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3629c-128">If your project already has a data source, you can also use the **Data Sources** window to create a data form.</span></span> <span data-ttu-id="3629c-129">자세한 내용은 [데이터 소스 창](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3629c-129">For more information, see [Data Sources Window](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3629c-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3629c-130">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="3629c-131">방법: 데이터베이스의 데이터에 연결</span><span class="sxs-lookup"><span data-stu-id="3629c-131">How to: Connect to Data in a Database</span></span>](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [<span data-ttu-id="3629c-132">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="3629c-132">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="3629c-133">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="3629c-133">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="3629c-134">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경</span><span class="sxs-lookup"><span data-stu-id="3629c-134">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [<span data-ttu-id="3629c-135">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="3629c-135">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="3629c-136">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="3629c-136">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="3629c-137">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="3629c-137">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="3629c-138">방법: Windows 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="3629c-138">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="3629c-139">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="3629c-139">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="3629c-140">데이터 소스 창</span><span class="sxs-lookup"><span data-stu-id="3629c-140">Data Sources Window</span></span>](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [<span data-ttu-id="3629c-141">방법: Windows Forms 응용 프로그램에서 관련 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="3629c-141">How to: Display Related Data in a Windows Forms Application</span></span>](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
