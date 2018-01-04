---
title: "방법: Windows Forms BindingSource 구성 요소를 사용하여 조회 테이블 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lookup tables
- tables [Windows Forms], creating lookup tables
- BindingSource component [Windows Forms], creating a lookup table
- BindingSource component [Windows Forms], examples
ms.assetid: 622fce80-879d-44be-abbf-8350ec22ca2b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 324e4ed290b98d2268dd82fa55b81deaeb849770
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-lookup-table-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="315a1-102">방법: Windows Forms BindingSource 구성 요소를 사용하여 조회 테이블 만들기</span><span class="sxs-lookup"><span data-stu-id="315a1-102">How to: Create a Lookup Table with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="315a1-103">조회 테이블은 관련 테이블의 레코드에서 데이터를 표시하는 열이 포함된 데이터 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-103">A lookup table is a table of data that has a column that displays data from records in a related table.</span></span> <span data-ttu-id="315a1-104">다음 절차에서는 <xref:System.Windows.Forms.ComboBox> 컨트롤을 사용하여 부모에서 자식 테이블로의 외래 키 관계로 필드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-104">In the following procedures, a <xref:System.Windows.Forms.ComboBox> control is used to display the field with the foreign-key relationship from the parent to the child table.</span></span>  
  
 <span data-ttu-id="315a1-105">이러한 두 테이블과 해당 관계를 쉽게 표시하기 위해 아래의 부모 및 자식 테이블 예제를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-105">To help visualize these two tables and this relationship, here is an example of a parent and child table:</span></span>  
  
 <span data-ttu-id="315a1-106">CustomersTable(부모 테이블)</span><span class="sxs-lookup"><span data-stu-id="315a1-106">CustomersTable (parent table)</span></span>  
  
|<span data-ttu-id="315a1-107">CustomerID</span><span class="sxs-lookup"><span data-stu-id="315a1-107">CustomerID</span></span>|<span data-ttu-id="315a1-108">CustomerName</span><span class="sxs-lookup"><span data-stu-id="315a1-108">CustomerName</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="315a1-109">712</span><span class="sxs-lookup"><span data-stu-id="315a1-109">712</span></span>|<span data-ttu-id="315a1-110">Paul Koch</span><span class="sxs-lookup"><span data-stu-id="315a1-110">Paul Koch</span></span>|  
|<span data-ttu-id="315a1-111">713</span><span class="sxs-lookup"><span data-stu-id="315a1-111">713</span></span>|<span data-ttu-id="315a1-112">Tamara Johnston</span><span class="sxs-lookup"><span data-stu-id="315a1-112">Tamara Johnston</span></span>|  
  
 <span data-ttu-id="315a1-113">OrdersTable(자식 테이블)</span><span class="sxs-lookup"><span data-stu-id="315a1-113">OrdersTable (child table)</span></span>  
  
|<span data-ttu-id="315a1-114">OrderID</span><span class="sxs-lookup"><span data-stu-id="315a1-114">OrderID</span></span>|<span data-ttu-id="315a1-115">OrderDate</span><span class="sxs-lookup"><span data-stu-id="315a1-115">OrderDate</span></span>|<span data-ttu-id="315a1-116">CustomerID</span><span class="sxs-lookup"><span data-stu-id="315a1-116">CustomerID</span></span>|  
|-------------|---------------|----------------|  
|<span data-ttu-id="315a1-117">903</span><span class="sxs-lookup"><span data-stu-id="315a1-117">903</span></span>|<span data-ttu-id="315a1-118">2004년 2월 12일</span><span class="sxs-lookup"><span data-stu-id="315a1-118">February 12, 2004</span></span>|<span data-ttu-id="315a1-119">712</span><span class="sxs-lookup"><span data-stu-id="315a1-119">712</span></span>|  
|<span data-ttu-id="315a1-120">904</span><span class="sxs-lookup"><span data-stu-id="315a1-120">904</span></span>|<span data-ttu-id="315a1-121">2004년 2월 13일</span><span class="sxs-lookup"><span data-stu-id="315a1-121">February 13, 2004</span></span>|<span data-ttu-id="315a1-122">713</span><span class="sxs-lookup"><span data-stu-id="315a1-122">713</span></span>|  
  
 <span data-ttu-id="315a1-123">이 시나리오의 테이블 중 하나인 CustomersTable에는 표시 및 저장할 실제 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-123">In this scenario, one table, CustomersTable, stores the actual information you want to display and save.</span></span> <span data-ttu-id="315a1-124">그러나 여기서는 공간 절약을 위해 명확성에 도움이 되는 일부 데이터를 제외했습니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-124">But to save space, the table leaves out data that adds clarity.</span></span> <span data-ttu-id="315a1-125">또 하나의 테이블인 OrdersTables에는 주문 날짜 및 주문 ID에 해당하는 고객 ID 번호에 대한 표시 관련 정보만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-125">The other table, OrdersTable, contains only appearance-related information about which customer ID number is equivalent to which order date and order ID.</span></span> <span data-ttu-id="315a1-126">고객 이름은 언급되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-126">There is no mention of the customers' names.</span></span>  
  
 <span data-ttu-id="315a1-127">조회 테이블을 만들기 위해 [ComboBox 컨트롤](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md) 컨트롤에는 4가지 주요 속성이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-127">Four important properties are set on the [ComboBox Control](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md) control to create the lookup table.</span></span>  
  
-   <span data-ttu-id="315a1-128"><xref:System.Windows.Forms.ComboBox.DataSource%2A> 속성은 테이블 이름을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-128">The <xref:System.Windows.Forms.ComboBox.DataSource%2A> property contains the name of the table.</span></span>  
  
-   <span data-ttu-id="315a1-129"><xref:System.Windows.Forms.ListControl.DisplayMember%2A> 속성은 컨트롤 텍스트(고객 이름)에 대해 표시할 해당 테이블의 데이터 열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-129">The <xref:System.Windows.Forms.ListControl.DisplayMember%2A> property contains the data column of that table that you want to display for the control text (the customer's name).</span></span>  
  
-   <span data-ttu-id="315a1-130"><xref:System.Windows.Forms.ListControl.ValueMember%2A> 속성은 저장된 정보(부모 테이블의 ID 번호)가 포함된 해당 테이블의 데이터 열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-130">The <xref:System.Windows.Forms.ListControl.ValueMember%2A> property contains the data column of that table with the stored information (the ID number in the parent table).</span></span>  
  
-   <span data-ttu-id="315a1-131"><xref:System.Windows.Forms.ListControl.SelectedValue%2A> 속성은 <xref:System.Windows.Forms.ListControl.ValueMember%2A>를 기준으로 자식 테이블에 대한 조회 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-131">The <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property provides the lookup value for the child table, based on the <xref:System.Windows.Forms.ListControl.ValueMember%2A>.</span></span>  
  
 <span data-ttu-id="315a1-132">아래 절차에서는 폼을 조회 테이블로 배치하고 해당 폼의 컨트롤에 데이터를 바인딩하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-132">The procedures below show you how to lay out your form as a lookup table and bind data to the controls on it.</span></span> <span data-ttu-id="315a1-133">이 절차를 올바르게 완료하려면 위에서 설명한 것처럼 외래 키 관계가 적용된 부모 및 자식 테이블을 포함하는 데이터 소스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-133">To successfully complete the procedures, you must have a data source with parent and child tables that have a foreign-key relationship, as mentioned previously.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="315a1-134">사용자 인터페이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="315a1-134">To create the user interface</span></span>  
  
1.  <span data-ttu-id="315a1-135">**도구 상자**를 끌어 한 <xref:System.Windows.Forms.ComboBox> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-135">From the **ToolBox**, drag a <xref:System.Windows.Forms.ComboBox> control onto the form.</span></span>  
  
     <span data-ttu-id="315a1-136">이 컨트롤에는 부모 테이블의 열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-136">This control will display the column from parent table.</span></span>  
  
2.  <span data-ttu-id="315a1-137">다른 컨트롤을 끌어 자식 테이블의 세부 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-137">Drag other controls to display details from the child table.</span></span> <span data-ttu-id="315a1-138">테이블의 데이터 형식에 맞는 컨트롤을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-138">The format of the data in the table should determine which controls you choose.</span></span> <span data-ttu-id="315a1-139">자세한 내용은 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="315a1-139">For more information, see [Windows Forms Controls by Function](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md).</span></span>  
  
3.  <span data-ttu-id="315a1-140"><xref:System.Windows.Forms.BindingNavigator> 컨트롤을 폼으로 끌어 옵니다. 그러면 자식 테이블의 데이터를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-140">Drag a <xref:System.Windows.Forms.BindingNavigator> control onto the form; this will allow you to navigate the data in the child table.</span></span>  
  
### <a name="to-connect-to-the-data-and-bind-it-to-controls"></a><span data-ttu-id="315a1-141">데이터에 연결하여 컨트롤에 데이터를 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="315a1-141">To connect to the data and bind it to controls</span></span>  
  
1.  <span data-ttu-id="315a1-142"><xref:System.Windows.Forms.ComboBox>를 선택하고 스마트 작업 문자 모양을 클릭하여 스마트 작업 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-142">Select the <xref:System.Windows.Forms.ComboBox> and click the Smart Task glyph to display the Smart Task dialog box.</span></span>  
  
2.  <span data-ttu-id="315a1-143">**데이터 바인딩된 항목 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-143">Select **Use data bound items**.</span></span>  
  
3.  <span data-ttu-id="315a1-144">**데이터 소스** 드롭다운 상자 옆의 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-144">Click the arrow next to the **Data Source** drop-down box.</span></span> <span data-ttu-id="315a1-145">프로젝트 또는 폼에 대해 데이터 소스를 이전에 구성한 경우 해당 데이터 소스가 표시됩니다. 표시되지 않으면 다음 단계를 완료합니다. 이 예에서는 Northwind 샘플 데이터베이스의 Customers 및 Orders 테이블을 사용하며 괄호로 묶은 부분에서 이러한 테이블을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-145">If a data source has previously been configured for the project or form, it will appear; otherwise, complete the following steps (This example uses the Customers and Orders tables of the Northwind sample database and refers to them in parentheses).</span></span>  
  
    1.  <span data-ttu-id="315a1-146">**프로젝트 데이터 소스 추가**를 클릭하여 데이터에 연결한 다음 데이터 소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-146">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
    2.  <span data-ttu-id="315a1-147">**데이터 소스 구성 마법사** 시작 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-147">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
    3.  <span data-ttu-id="315a1-148">**데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-148">Select **Database** on the **Choose a Data Source Type** page.</span></span>  
  
    4.  <span data-ttu-id="315a1-149">**데이터 연결 선택** 페이지의 사용 가능한 연결 목록에서 데이터 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-149">Select a data connection from the list of available connections on the **Choose Your Data Connection** page.</span></span> <span data-ttu-id="315a1-150">원하는 데이터 연결을 사용할 수 없으면 **새 연결**을 선택하여 새 데이터 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-150">If your desired data connection is not available, select **New Connection** to create a new data connection.</span></span>  
  
    5.  <span data-ttu-id="315a1-151">**예, 연결을 저장합니다.**를 클릭하여 응용 프로그램 구성 파일에 연결 문자열을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-151">Click **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
    6.  <span data-ttu-id="315a1-152">응용 프로그램에 바인딩할 데이터베이스 개체를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-152">Select the database objects to bring into your application.</span></span> <span data-ttu-id="315a1-153">여기서는 외래 키 관계가 적용된 부모 테이블과 자식 테이블(예: Customers 및 Orders)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-153">In this case, select a parent table and child table (for example, Customers and Orders) with a foreign key relationship.</span></span>  
  
    7.  <span data-ttu-id="315a1-154">원하는 경우 기본 데이터베이스 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-154">Replace the default dataset name if you want.</span></span>  
  
    8.  <span data-ttu-id="315a1-155">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-155">Click **Finish**.</span></span>  
  
4.  <span data-ttu-id="315a1-156">**구성원 표시** 드롭다운 상자에서 콤보 상자에 표시할 ContactName 등의 열 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-156">In the **Display Member** drop-down box, select the column name (for example, ContactName) to be displayed in the combo box.</span></span>  
  
5.  <span data-ttu-id="315a1-157">**값 구성원** 드롭다운 상자에서 자식 테이블에서 조회 작업을 수행할 CustomerID 등의 열을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-157">In the **Value Member** drop-down box, select the column (for example, CustomerID) to perform the lookup operation in the child table.</span></span>  
  
6.  <span data-ttu-id="315a1-158">**선택한 값** 드롭다운 상자에서 **프로젝트 데이터 소스**로 이동한 다음 부모 및 자식 테이블이 포함된 방금 만든 데이터 집합으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-158">In the **Selected Value** drop-down box, navigate to **Project Data Sources** and the dataset you just created that contains the parent and child tables.</span></span> <span data-ttu-id="315a1-159">부모 테이블의 값 멤버인 자식 테이블의 동일 속성(예: Orders.CustomerID)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-159">Select the same property of the child table that is the Value Member of the parent table (for example, Orders.CustomerID).</span></span> <span data-ttu-id="315a1-160">해당하는 <xref:System.Windows.Forms.BindingSource>, 데이터 집합 및 테이블 어댑터 구성 요소가 작성되어 폼에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-160">The appropriate <xref:System.Windows.Forms.BindingSource> , data set, and table adapter components will be created and added to the form.</span></span>  
  
7.  <span data-ttu-id="315a1-161"><xref:System.Windows.Forms.BindingNavigator> 컨트롤을 자식 테이블의 <xref:System.Windows.Forms.BindingSource>(예: `OrdersBindingSource`)에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-161">Bind the <xref:System.Windows.Forms.BindingNavigator> control to the <xref:System.Windows.Forms.BindingSource> of the child table (for example, `OrdersBindingSource`).</span></span>  
  
8.  <span data-ttu-id="315a1-162"><xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.BindingNavigator> 컨트롤 이외의 컨트롤은 표시하려는 자식 테이블의 <xref:System.Windows.Forms.BindingSource>(예: `OrdersBindingSource`)의 세부 정보 필드에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="315a1-162">Bind the controls other than the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.BindingNavigator> control to the details fields from the child table's <xref:System.Windows.Forms.BindingSource> (for example, `OrdersBindingSource`) that you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="315a1-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="315a1-163">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="315a1-164">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="315a1-164">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="315a1-165">ComboBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="315a1-165">ComboBox Control</span></span>](../../../../docs/framework/winforms/controls/combobox-control-windows-forms.md)  
 [<span data-ttu-id="315a1-166">Visual Studio에서 데이터에 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="315a1-166">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
