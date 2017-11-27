---
title: "방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4bc4f53c404e3767b9f98ca5ab46b19db31f9c6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="cf91f-102">방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가</span><span class="sxs-lookup"><span data-stu-id="cf91f-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="cf91f-103"><xref:System.Windows.Forms.BindingNavigator> 컨트롤은 특수 한 용도의 <xref:System.Windows.Forms.ToolStrip> 탐색 하 고 데이터에 바인딩되는 양식에서 컨트롤을 조작 하는 데 사용 되는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="cf91f-104">이기 때문에 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 <xref:System.Windows.Forms.BindingNavigator> 사용자에 대 한 추가 또는 대체 명령을 포함 하도록 구성 요소를 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="cf91f-105">다음 절차에는 <xref:System.Windows.Forms.TextBox> 컨트롤이 데이터 바인딩되어 및 <xref:System.Windows.Forms.ToolStrip> 폼에 추가 되는 컨트롤 및 취소 단추를 로드, 저장, 포함 하도록 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="cf91f-106">부하를 추가 하려면 저장 및 취소 단추 BindingNavigator 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cf91f-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1.  <span data-ttu-id="cf91f-107">폼에 <xref:System.Windows.Forms.TextBox> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2.  <span data-ttu-id="cf91f-108">에 바인딩합니다는 <xref:System.Windows.Forms.BindingSource>, 데이터 소스에 바인딩된 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="cf91f-109">이 예는 <xref:System.Windows.Forms.BindingSource> 데이터베이스에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3.  <span data-ttu-id="cf91f-110">데이터 집합 및 테이블 어댑터를 생성 한 후 끌어서는 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4.  <span data-ttu-id="cf91f-111">설정의 <xref:System.Windows.Forms.BindingNavigator> 컨트롤의 <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 속성을는 <xref:System.Windows.Forms.BindingSource> 컨트롤에 바인딩된 폼에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5.  <span data-ttu-id="cf91f-112"><xref:System.Windows.Forms.BindingNavigator> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6.  <span data-ttu-id="cf91f-113">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 하므로 **BindingNavigator 작업** 대화 상자가 나타나고 선택 **항목편집**.</span><span class="sxs-lookup"><span data-stu-id="cf91f-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="cf91f-114">**항목 컬렉션 편집기** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-114">The **Items Collection Editor** appears.</span></span>  
  
7.  <span data-ttu-id="cf91f-115">에 **항목 컬렉션 편집기**, 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1.  <span data-ttu-id="cf91f-116">추가 <xref:System.Windows.Forms.ToolStripSeparator> 및 세 개의 <xref:System.Windows.Forms.ToolStripButton> 적절 한 유형을 선택 하 여 항목 <xref:System.Windows.Forms.ToolStripItem> 클릭 하 고는 **추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2.  <span data-ttu-id="cf91f-117">설정의 <xref:System.Windows.Forms.ToolStripItem.Name%2A> 속성에 있는 단추의**LoadButton**,**저장 단추**, 및**CancelButton**각각.</span><span class="sxs-lookup"><span data-stu-id="cf91f-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to**LoadButton**,**SaveButton**, and**CancelButton**, respectively.</span></span>  
  
    3.  <span data-ttu-id="cf91f-118">설정의 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성에 있는 단추의**부하** `,` **저장**, 및**취소**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to**Load**`,` **Save**, and**Cancel**.</span></span>  
  
    4.  <span data-ttu-id="cf91f-119">설정의 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 각 단추에 대 한 속성**텍스트**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to**Text**.</span></span> <span data-ttu-id="cf91f-120">이 속성 설정할 수 있습니다 또는**이미지**또는**ImageAndText**에 표시할 이미지를 설정 하 고는 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="cf91f-120">Alternatively, you can set this property to**Image**or**ImageAndText**and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5.  <span data-ttu-id="cf91f-121">클릭 **확인** 대화 상자를 닫습니다. 단추에 추가 되는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8.  <span data-ttu-id="cf91f-122">폼을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="cf91f-123">코드 편집기에서 데이터 테이블 어댑터를 로드 하는 코드 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="cf91f-124">이 코드는 2 단계에서 데이터 바인딩을를 설정할 때 생성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="cf91f-125">코드는 다음과 비슷해야: `TableAdapterName.Fill(DataSetName.TableName)`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="cf91f-126">양식의에 포함 될 가능성이 <xref:System.Windows.Forms.Form.Load> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="cf91f-127">에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트는**부하** <xref:System.Windows.Forms.ToolStripButton> 앞에서 만든 하 고이 데이터 로드 코드 테이블로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Load**<xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="cf91f-128">코드 이제 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-128">Your code should now look similar to the following:</span></span>  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. <span data-ttu-id="cf91f-129">에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트는 **저장** <xref:System.Windows.Forms.ToolStripButton> 앞에서 만든 고에 바인딩된 테이블 컨트롤 내에서 데이터를 업데이트 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cf91f-130">일부 경우에는 <xref:System.Windows.Forms.BindingNavigator> 구성 요소는 이미는**저장** Windows Forms 디자이너에서 됩니다 생성 단추를 하지만 코드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a**Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="cf91f-131">이 경우에 앞의 코드를 배치할 수 있습니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 에 새 단추를 만드는 하는 것이 아니라 해당 단추에 대 한 이벤트 처리기는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="cf91f-132">로 설정 해야 단추가 기본적으로 비활성화 하는 반면는 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 단추의 속성 `true` 단추 함수를 올바르게 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>  
  
12. <span data-ttu-id="cf91f-133">에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트는**취소** <xref:System.Windows.Forms.ToolStripButton> 앞에서 만든 하 고 표시 되는 데이터 레코드에 변경 내용을 취소 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Cancel**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cf91f-134"><xref:System.Windows.Forms.BindingSource.CancelEdit%2A> 메서드는 데이터의 행으로 범위가 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="cf91f-135">다음 레코드로 이동 하기 전에 해당 개별 레코드를 보고 하는 동안 변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf91f-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf91f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf91f-136">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="cf91f-137">BindingNavigator 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cf91f-137">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="cf91f-138">BindingSource 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="cf91f-138">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
