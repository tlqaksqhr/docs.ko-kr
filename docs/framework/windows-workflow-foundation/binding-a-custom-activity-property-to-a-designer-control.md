---
title: "사용자 지정 작업 속성을 디자이너 컨트롤에 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e8061ea-10f5-407c-a31f-d0d74ce12f27
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 07a39983d0e561fdad4c09e641912b0d15aa4033
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a><span data-ttu-id="27c2a-102">사용자 지정 작업 속성을 디자이너 컨트롤에 바인딩</span><span class="sxs-lookup"><span data-stu-id="27c2a-102">Binding a custom activity property to a designer control</span></span>
<span data-ttu-id="27c2a-103">텍스트 상자 디자이너 컨트롤을 작업 인수에 바인딩하는 작업은 비교적 간단하지만 복잡한 디자이너 컨트롤(예: 콤보 상자)을 작업 인수에 바인딩하는 작업은 까다로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-103">Binding a text box designer control to an activity argument is fairly straightforward; binding a complex designer control (such as a combo box) to an activity argument may present challenges, however.</span></span> <span data-ttu-id="27c2a-104">이 항목에서는 사용자 지정 작업 디자이너에서 작업 인수를 콤보 상자 컨트롤에 바인딩하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-104">This topic discusses how to bind an activity argument to a combo box control on a custom activity designer.</span></span>  
  
#### <a name="creating-the-combo-box-item-converter"></a><span data-ttu-id="27c2a-105">콤보 상자 항목 변환기 만들기</span><span class="sxs-lookup"><span data-stu-id="27c2a-105">Creating the combo box item converter</span></span>  
  
1.  <span data-ttu-id="27c2a-106">Visual Studio에서 CustomProperty라는 빈 솔루션을 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-106">Create a new empty solution in Visual Studio called CustomProperty.</span></span>  
  
2.  <span data-ttu-id="27c2a-107">ComboBoxItemConverter라는 새 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-107">Create a new class called ComboBoxItemConverter.</span></span> <span data-ttu-id="27c2a-108">System.Windows.Data에 대한 참조를 추가하고 클래스가 <xref:System.Windows.Data.IValueConverter>에서 파생되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-108">Add a reference to System.Windows.Data, and have the class derive from <xref:System.Windows.Data.IValueConverter>.</span></span> <span data-ttu-id="27c2a-109">Visual Studio에서 `Convert` 및 `ConvertBack`에 대한 스텁을 생성하는 인터페이스를 구현하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-109">Have Visual Studio implement the interface to generate stubs for `Convert` and `ConvertBack`.</span></span>  
  
3.  <span data-ttu-id="27c2a-110">`Convert` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-110">Add the following code to the `Convert` method.</span></span> <span data-ttu-id="27c2a-111">이 코드는 작업의 <xref:System.Activities.InArgument%601> 형식 <xref:System.String>를 디자이너에 배치할 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-111">This code converts the activity's <xref:System.Activities.InArgument%601> of type <xref:System.String> to the value to be placed in the designer.</span></span>  
  
    ```  
    ModelItem modelItem = value as ModelItem;  
    if (value != null)  
    {  
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;  
  
        if (inArgument != null)  
        {  
            Activity<string> expression = inArgument.Expression;  
            VisualBasicValue<string> vbexpression = expression as VisualBasicValue<string>;  
            Literal<string> literal = expression as Literal<string>;  
  
            if (literal != null)  
            {  
                return "\"" + literal.Value + "\"";  
            }  
            else if (vbexpression != null)  
            {  
                return vbexpression.ExpressionText;  
            }  
        }  
    }  
    return null;  
    ```  
  
     <span data-ttu-id="27c2a-112">위의 코드 조각에서 <xref:Microsoft.CSharp.Activities.CSharpValue%601> 대신 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>을 사용하여 식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-112">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>  
  
    ```  
    ModelItem modelItem = value as ModelItem;  
    if (value != null)  
    {  
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;  
  
        if (inArgument != null)  
        {  
            Activity<string> expression = inArgument.Expression;  
            CSharpValue<string> csexpression = expression as CSharpValue<string>;  
            Literal<string> literal = expression as Literal<string>;  
  
            if (literal != null)  
            {  
                return "\"" + literal.Value + "\"";  
            }  
            else if (csexpression != null)  
            {  
                return csexpression.ExpressionText;  
            }  
        }  
    }  
    return null;  
    ```  
  
4.  <span data-ttu-id="27c2a-113">`ConvertBack` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-113">Add the following code to the `ConvertBack` method.</span></span> <span data-ttu-id="27c2a-114">이 코드는 들어오는 콤보 상자 항목을 <xref:System.Activities.InArgument%601>로 다시 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-114">This code converts the incoming combo box item back to an <xref:System.Activities.InArgument%601>.</span></span>  
  
    ```  
    // Convert combo box value to InArgument<string>  
                string itemContent = (string)((ComboBoxItem)value).Content;  
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);  
                InArgument<string> inArgument = new InArgument<string>(vbArgument);  
                return inArgument;  
    ```  
  
     <span data-ttu-id="27c2a-115">위의 코드 조각에서 <xref:Microsoft.CSharp.Activities.CSharpValue%601> 대신 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>을 사용하여 식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-115">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>  
  
    ```  
    // Convert combo box value to InArgument<string>  
                string itemContent = (string)((ComboBoxItem)value).Content;  
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);  
                InArgument<string> inArgument = new InArgument<string>(csArgument);  
                return inArgument;  
    ```  
  
#### <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a><span data-ttu-id="27c2a-116">작업의 사용자 지정 디자이너에 ComboBoxItemConverter 추가</span><span class="sxs-lookup"><span data-stu-id="27c2a-116">Adding the ComboBoxItemConverter to the custom designer of an activity</span></span>  
  
1.  <span data-ttu-id="27c2a-117">프로젝트에 새 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-117">Add a new item to the project.</span></span> <span data-ttu-id="27c2a-118">새 항목 대화 상자에서 워크플로 노드를 선택한 다음 새 항목의 형식으로 작업 디자이너를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-118">In the New Item dialog, select the Workflow node and select Activity Designer as the type of the new item.</span></span> <span data-ttu-id="27c2a-119">항목의 이름을 CustomPropertyDesigner로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-119">Name the item CustomPropertyDesigner.</span></span>  
  
2.  <span data-ttu-id="27c2a-120">새 디자이너에 콤보 상자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-120">Add a Combo Box to the new designer.</span></span> <span data-ttu-id="27c2a-121">Items 속성에서 Content 값을 "Item1" 및 'Item2"로 지정하여 항목 두 개를 콤보 상자에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-121">In the Items property, add a couple of items to the combo box, with Content values of "Item1" and 'Item2".</span></span>  
  
3.  <span data-ttu-id="27c2a-122">콤보 상자의 XAML을 수정하여 콤보 상자에 사용할 항목 변환기로 새 항목 변환기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-122">Modify the XAML of the combo box to add the new item converter as the item converter to be used for the combo box.</span></span> <span data-ttu-id="27c2a-123">변환기가 ActivityDesigner.Resources 세그먼트에 리소스로 추가되고 <xref:System.Windows.Controls.ComboBox>에 대한 Converter 특성의 변환기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-123">The converter is added as a resource in the ActivityDesigner.Resources segment, and specifies the converter in the Converter attribute for the <xref:System.Windows.Controls.ComboBox>.</span></span> <span data-ttu-id="27c2a-124">프로젝트의 네임스페이스는 작업 디자이너의 네임스페이스 특성에서 지정됩니다. 다른 프로젝트에서 디자이너를 사용하려는 경우 이 네임스페이스를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-124">Note that the namespace of the project is specified in the namespaces attributes for the activity designer; if the designer is to be used in a different project, this namespace will need to be changed.</span></span>  
  
    ```  
    <sap:ActivityDesigner x:Class="CustomProperty.CustomPropertyDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:c="clr-namespace:CustomProperty"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
  
        <sap:ActivityDesigner.Resources>  
            <ResourceDictionary>  
                <c:ComboBoxItemConverter x:Key="comboBoxItemConverter"/>  
            </ResourceDictionary>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ComboBox SelectedValue="{Binding Path=ModelItem.Text, Mode=TwoWay, Converter={StaticResource comboBoxItemConverter}}"  Height="23" HorizontalAlignment="Left" Margin="132,5,0,0" Name="comboBox1" VerticalAlignment="Top" Width="120" ItemsSource="{Binding}">  
                <ComboBoxItem>item1</ComboBoxItem>  
                <ComboBoxItem>item2</ComboBoxItem>  
            </ComboBox>  
        </Grid>  
    </sap:ActivityDesigner>  
    ```  
  
4.  <span data-ttu-id="27c2a-125"><xref:System.Activities.CodeActivity> 형식의 새 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-125">Create a new item of type <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="27c2a-126">이 예제에는 IDE에서 작업에 대해 만드는 기본 코드만으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-126">The default code created by the IDE for the activity will be sufficient for this example.</span></span>  
  
5.  <span data-ttu-id="27c2a-127">클래스 정의에 다음 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-127">Add the following attribute to the class definition:</span></span>  
  
    ```  
    [Designer(typeof(CustomPropertyDesigner))]  
    ```  
  
     <span data-ttu-id="27c2a-128">이 줄에서는 새 디자이너를 새 클래스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-128">This line associates the new designer with the new class.</span></span>  
  
 <span data-ttu-id="27c2a-129">이제 새 작업이 디자이너에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-129">The new activity should now be associated with the designer.</span></span> <span data-ttu-id="27c2a-130">새 작업을 테스트하려면 워크플로에 작업을 추가하고 콤보 상자를 두 개의 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-130">To test the new activity, add it to a workflow, and set the combo box to the two values.</span></span> <span data-ttu-id="27c2a-131">속성 창이 업데이트되어 콤보 상자 값을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="27c2a-131">The properties window should update to reflect the combo box value.</span></span>
