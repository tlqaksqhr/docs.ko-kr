---
title: "데이터 템플릿 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "데이터 바인딩, 템플릿"
  - "데이터 바인딩 템플릿"
  - "데이터 템플릿"
  - "데이터 템플릿"
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# 데이터 템플릿 개요
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 템플릿 모델 데이터의 표시를 정의 하는 뛰어난 융통성을 제공 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]컨트롤의 데이터 표시 사용자 지정을 지원 하기 위해 기본 제공 기능이 있습니다. 이 항목에는 먼저 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.DataTemplate> 하 고 다음 사용자 지정 논리와 계층적 데이터의 표시에 대 한 지원에 따라 템플릿 선택과 같은 다른 데이터 템플릿 기능을 소개 합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목 데이터 템플릿 기능에 중점적으로 설명 하 고 데이터 바인딩 개념에는 다루지 않습니다. 기본 데이터 바인딩 개념에 대 한 내용은 참조는 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.  
  
 <xref:System.Windows.DataTemplate> 데이터의 표시에 대 한 이며 제공 하는 여러 기능 중 하나는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스타일 및 템플릿 모델입니다. 에 대 한 소개의는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스타일 및 템플릿 모델을 사용 하는 방법 등을 <xref:System.Windows.Style> 컨트롤에 속성을 설정 하려면 다음을 참조는 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md) 항목입니다.  
  
 또한 이해 하는 `Resources`는 기본적으로 활성화 하는 요소 개체와 같은 <xref:System.Windows.Style> 및 <xref:System.Windows.DataTemplate> 을 재사용 합니다. 리소스에 대 한 자세한 내용은 참조 하십시오. [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>데이터 템플릿 기본 사항  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
 그 이유를 설명 하기 위해 <xref:System.Windows.DataTemplate> 중요 한 데이터 바인딩 예제를 살펴보겠습니다. 이 예제에는 한 <xref:System.Windows.Controls.ListBox> 의 목록에 바인딩된 `Task` 개체입니다. 각 `Task` 개체에는 `TaskName` (string)는 `Description` (string)는 `Priority` (int) 및 형식의 속성 `TaskType`, 즉는 `Enum` 값으로 `Home` 및 `Work`.  
  
 [!code-xml[DataTemplatingIntro_snip#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xml[DataTemplatingIntro_snip#UI1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xml[DataTemplatingIntro_snip#UI2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>DataTemplate 없이  
 없이 <xref:System.Windows.DataTemplate>, <xref:System.Windows.Controls.ListBox> 모양이 다음과 같습니다.  
  
 ![데이터 템플릿 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 없이 모든 특정 지침을 참조 하는 작업이 고 <xref:System.Windows.Controls.ListBox> 기본 호출에 의해 `ToString` 컬렉션에서 개체를 표시 하려고 할 때입니다. 따라서 경우는 `Task` 재정의 개체는 `ToString` 메서드를 면 <xref:System.Windows.Controls.ListBox> 기본 컬렉션의 각 소스 개체의 문자열 표현을 표시 합니다.  
  
 예를 들어 하는 경우는 `Task` 재정의 `ToString` 메서드 이러한 방식으로 여기서 `name` 는 대 한 필드는 `TaskName` 속성:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 그런 다음 <xref:System.Windows.Controls.ListBox> 는 다음과 같습니다.  
  
 ![데이터 템플릿 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 그러나 제한 하 고 융통성있지 않습니다. 또한 바인딩하는 경우 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 수는 없습니다 재정의할 `ToString`합니다.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>간단한 DataTemplate을 정의합니다.  
 솔루션을 정의 하는 한 <xref:System.Windows.DataTemplate>합니다. 작업을 수행 하는 방법을 설정 하는 것은 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성은 <xref:System.Windows.Controls.ListBox> 에 <xref:System.Windows.DataTemplate>. 지정 하 여 <xref:System.Windows.DataTemplate> 데이터 개체의 표시 구조가 됩니다. 다음 <xref:System.Windows.DataTemplate> 은 매우 간단 합니다. 세 개의 각 항목에 나타나는 지침 지정 <xref:System.Windows.Controls.TextBlock> 내의 요소는 <xref:System.Windows.Controls.StackPanel>합니다. 각 <xref:System.Windows.Controls.TextBlock> 요소 속성에 바인딩되는 `Task` 클래스입니다.  
  
 [!code-xml[DataTemplatingIntro_snip#Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 이 항목의 예제에 대 한 기본 데이터의 컬렉션인 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체입니다. 바인딩하는 경우 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터를 기본 개념은 동일 하지만 구문이 약간 다릅니다. 필요 없이 예를 들어 `Path=TaskName`, 설정한 <xref:System.Windows.Data.Binding.XPath%2A> 를 `@TaskName` (경우 `TaskName` 의 특성은 프로그램 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 노드).  
  
 이제 우리 <xref:System.Windows.Controls.ListBox> 는 다음과 같습니다.  
  
 ![데이터 템플릿 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>DataTemplate 리소스 만들기  
 위의 예제에서 정의한는 <xref:System.Windows.DataTemplate> 인라인 합니다. 일반적으로 다음 예제와 같이 개체를 다시 사용할 수 있도록 리소스 섹션에 정의 합니다.  
  
 [!code-xml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xml[DataTemplatingIntro_snip#AsResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 에서는 이제 `myTaskTemplate` 다음 예제와 같이 리소스로:  
  
 [!code-xml[DataTemplatingIntro_snip#MyTaskTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 때문에 `myTaskTemplate` 는 리소스를 사용 하는 속성을 가진 다른 컨트롤에 사용할 수 있습니다는 <xref:System.Windows.DataTemplate> 유형입니다. 표시 된 것 처럼 위의 대 한 <xref:System.Windows.Controls.ItemsControl> 같은 개체는 <xref:System.Windows.Controls.ListBox>, 이기는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성입니다. 에 대 한 <xref:System.Windows.Controls.ContentControl> 는 개체는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성입니다.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>DataType 속성  
 <xref:System.Windows.DataTemplate> 클래스에는 <xref:System.Windows.DataTemplate.DataType%2A> 매우 유사한 속성은 <xref:System.Windows.Style.TargetType%2A> 속성은 <xref:System.Windows.Style> 클래스입니다. 따라서 지정 하는 대신는 `x:Key` 에 대 한는 <xref:System.Windows.DataTemplate> 위의 예에는 다음을 수행할 수 있습니다.  
  
 [!code-xml[DataTemplatingIntro_snip#DataType](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 이 <xref:System.Windows.DataTemplate> 모두 자동으로 적용 됩니다 `Task` 개체입니다. 이 경우 유의 `x:Key` 는 암시적으로 설정 합니다. 따라서이 할당 하는 경우 <xref:System.Windows.DataTemplate> 는 `x:Key` 값을 재정의 하는 암시적 `x:Key` 및 <xref:System.Windows.DataTemplate> 자동으로 적용 합니다.  
  
 바인딩하는 경우는 <xref:System.Windows.Controls.ContentControl> 의 컬렉션에 `Task` 개체는 <xref:System.Windows.Controls.ContentControl> 위의 사용 하지 않는 <xref:System.Windows.DataTemplate> 자동으로 합니다. 때문에 대 한 바인딩은 <xref:System.Windows.Controls.ContentControl> 전체 컬렉션 또는 개별 개체에 바인딩할 인지 구분 하기 위해 더 많은 정보가 필요 합니다. 경우에 <xref:System.Windows.Controls.ContentControl> 선택을 추적 하는 중는 <xref:System.Windows.Controls.ItemsControl> 형식을 설정할 수 있습니다는 <xref:System.Windows.Data.Binding.Path%2A> 속성의는 <xref:System.Windows.Controls.ContentControl> 에 바인딩 "`/`" 현재 항목에 관심이 나타내려면 합니다. 예를 들어 참조 [수집 및 표시 정보 선택에 따라 바인딩할](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)합니다. 지정 해야 하는 그렇지 않은 경우는 <xref:System.Windows.DataTemplate> 설정 하 여 명시적으로 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성입니다.  
  
 <xref:System.Windows.DataTemplate.DataType%2A> 속성은 경우에 특히 유용는 <xref:System.Windows.Data.CompositeCollection> 여러 유형의 데이터 개체입니다. 예를 들어 참조 [CompositeCollection 구현](../../../../docs/framework/wpf/data/how-to-implement-a-compositecollection.md)합니다.  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>DataTemplate에 더 추가  
 현재 데이터에서 필요한 정보를 함께 표시 하지만 분명히 개선의 여지가 있습니다. 보겠습니다 추가 하 여 개선에 <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Grid>, 일부 <xref:System.Windows.Controls.TextBlock> 표시 되는 데이터를 설명 하는 요소입니다.  
  
 [!code-xml[DataTemplatingIntro#AddingMore](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 다음 스크린 샷에 표시 된 <xref:System.Windows.Controls.ListBox> 수정이 <xref:System.Windows.DataTemplate>:  
  
 ![데이터 템플릿 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 설정할 수 있습니다 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 를 <xref:System.Windows.HorizontalAlignment> 에 <xref:System.Windows.Controls.ListBox> 항목의 너비는 전체 공간을 확인할 수 있도록 합니다.  
  
 [!code-xml[DataTemplatingIntro_snip#Stretch](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 와 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 속성으로 설정 <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.Controls.ListBox> 모양이 다음과 같습니다.  
  
 ![데이터 템플릿 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Datatrigger를 사용 하 여 속성 값에 적용할  
 현재 프레젠테이션을 않습니다 인지 알 수 있는지 여부는 `Task` 홈 작업 또는 사무실 작업 합니다. 유의 해야는 `Task` 개체에는 `TaskType` 형식의 속성 `TaskType`,이 값을 가진 열거형입니다 `Home` 및 `Work`합니다.  
  
 다음 예제에서는 <xref:System.Windows.DataTrigger> 설정 하는 <xref:System.Windows.Controls.Border.BorderBrush%2A> 라는 요소의 `border` 를 `Yellow` 경우는 `TaskType` 속성은 `TaskType.Home`합니다.  
  
 [!code-xml[DataTemplatingIntro#DT](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xml[DataTemplatingIntro#DataTrigger](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 이제 응용 프로그램은 다음과 같습니다. 홈 작업 노란색 테두리와 함께 표시 되 고 업무는 바다색 테두리가 표시:  
  
 ![데이터 템플릿 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 이 예제는 <xref:System.Windows.DataTrigger> 사용 하 여는 <xref:System.Windows.Setter> 속성 값을 설정 합니다. 트리거 클래스는 <xref:System.Windows.TriggerBase.EnterActions%2A> 및 <xref:System.Windows.TriggerBase.ExitActions%2A> 애니메이션 등의 작업 집합을 시작할 수 있도록 하는 속성입니다. 또한 있어는 <xref:System.Windows.MultiDataTrigger> 여러 데이터 바인딩된 속성 값을 기반으로 하는 변경 내용을 적용할 수 있는 클래스입니다.  
  
 다른 방법으로 동일한 결과 얻으려면에 바인딩하는 것은 <xref:System.Windows.Controls.Border.BorderBrush%2A> 속성을는 `TaskType` 속성을 사용 하 여 색을 반환 하는 값 변환기에 따라는 `TaskType` 값입니다. 변환기를 사용 하 여 위와 같은 효과 만드는 성능 측면에서 약간 더 효율적입니다. 또한 사용자 고유의 변환기 만들기 더 유연 고유의 논리를 제공할 수 있으므로 합니다. 궁극적으로 사용할 방법을 선택 하는 시나리오 및 기본 설정에 따라 다릅니다. 변환기를 작성 하는 방법에 대 한 정보를 참조 하십시오. <xref:System.Windows.Data.IValueConverter>합니다.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>DataTemplate에 어떠한 항목이 포함?  
 앞의 예제는 트리거 내에서 배치의 <xref:System.Windows.DataTemplate> 를 사용 하는 <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> 속성입니다. <xref:System.Windows.Setter> 트리거 요소의 속성의 값을 설정 (의 <xref:System.Windows.Controls.Border> 요소) 내에서 <xref:System.Windows.DataTemplate>합니다. 그러나 경우 속성 하는 프로그램 `Setters` 관심이 있는 속성은 현재 내에 있는 요소의 속성이 아닙니다 <xref:System.Windows.DataTemplate>를 사용 하 여 속성을 설정 하는 것이 적합할 수 있습니다는 <xref:System.Windows.Style> 이 <xref:System.Windows.Controls.ListBoxItem> 클래스 (컨트롤을 바인딩하는 경우는 <xref:System.Windows.Controls.ListBox>). 예를 들어, 원하는 경우 프로그램 <xref:System.Windows.Trigger> 애니메이션을 적용 하는 <xref:System.Windows.UIElement.Opacity%2A> 값 항목의 마우스의 항목을 가리킬 때 트리거를 정의 내에서 <xref:System.Windows.Controls.ListBoxItem> 스타일입니다. 예를 들어 참조는 [스타일 및 템플릿 샘플 소개](http://go.microsoft.com/fwlink/?LinkID=160010)합니다.  
  
 일반적으로 사항으로 <xref:System.Windows.DataTemplate> 생성 된 각 적용 되 고 <xref:System.Windows.Controls.ListBoxItem> (실제로 적용 되는 방법과 위치에 대 한 자세한 내용은 참조는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 페이지입니다.). 프로그램 <xref:System.Windows.DataTemplate> 프레젠테이션 및 데이터 개체의 모양을 관련 됩니다. 대부분의 경우에서 어떤 항목 등의 프레젠테이션의 다른 모든 측면 같습니다 선택 방법을 <xref:System.Windows.Controls.ListBox> 에 항목이 배치의 정의에 속하지 않는 <xref:System.Windows.DataTemplate>합니다. 예를 들어 참조는 [스타일 및 템플릿 ItemsControl](#DataTemplating_ItemsControl) 섹션입니다.  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>데이터 개체의 속성에 따라 DataTemplate을 선택 합니다.  
 [DataType 속성](#Styling_DataType) 섹션에서 설명한 다양 한 데이터 개체에 대 한 서로 다른 데이터 템플릿을 정의할 수 있습니다. 있는 경우 특히 유용는 <xref:System.Windows.Data.CompositeCollection> 서로 다른 형식이 나 다른 형식의 항목을 사용 하 여 컬렉션입니다. 에 [적용 속성 값을 사용 하 여 Datatrigger](#DataTrigger_to_Apply_Property_Values) 섹션 살펴보았습니다 같은 종류의 데이터 개체의 컬렉션을 사용할 경우 만들 수 있습니다는 <xref:System.Windows.DataTemplate> 다음 트리거를 사용 하 여 각 데이터 개체의 속성 값에 따라 변경 내용을 적용 합니다. 그러나 트리거를 사용 하면 속성 값을 적용 하거나 애니메이션을 시작할 수 있지만 데이터 개체의 구조를 다시 생성할 수 있는 유연성이 제공 하지 않습니다. 일부 시나리오를 만드는 다른 해야 할 수도 있습니다 <xref:System.Windows.DataTemplate> 데이터에 대 한 개체의 동일한 입력 하지만 다른 속성이 있습니다.  
  
 예를 들어,는 `Task` 개체에는 `Priority` 값 `1`, 자신에 대 한 알림을 제공 하는 완전히 다른 모양을 제공 하는 것이 좋습니다. 만들 경우에 <xref:System.Windows.DataTemplate> 높은 우선 순위를 표시 하기 위한 `Task` 개체입니다. 다음을 추가 해 보겠습니다 <xref:System.Windows.DataTemplate> (리소스) 섹션에 있습니다.  
  
 [!code-xml[DataTemplatingIntro_snip#ImportantTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 이 예제에서는 <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> 속성입니다. 요소 내에서 공유 섹션에 정의 된 리소스는 <xref:System.Windows.DataTemplate>합니다.  
  
 선택 하는 논리를 제공 <xref:System.Windows.DataTemplate> 에 따라 사용 하는 `Priority` 값 데이터 개체의 서브 클래스를 만든 <xref:System.Windows.Controls.DataTemplateSelector> 재정의 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 메서드. 다음 예제에서는 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 의 값에 따라 적절 한 템플릿을 반환 하는 논리를 제공 하는 메서드는 `Priority` 속성입니다. 반환할 템플릿의 상위 리소스 참조는 <xref:System.Windows.Window> 요소입니다.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 그런 다음 선언할 수는 `TaskListDataTemplateSelector` 리소스:  
  
 [!code-xml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xml[DataTemplatingIntro_snip#DTS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 템플릿 선택기 리소스를 사용 하려면에 할당 된 <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> 속성은 <xref:System.Windows.Controls.ListBox>합니다. <xref:System.Windows.Controls.ListBox> 호출의 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 의 메서드는 `TaskListDataTemplateSelector` 각각의 기본 컬렉션의 항목에 대 한 합니다. 항목 매개 변수로 데이터 개체를 전달 하는 호출 합니다. <xref:System.Windows.DataTemplate> 에서 반환 하는 메서드가 해당 데이터 개체에 적용 됩니다.  
  
 [!code-xml[DataTemplatingIntro_snip#ItemTemplateSelector](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 현재 위치에서 서식 파일 선택기는 <xref:System.Windows.Controls.ListBox> 이제 다음과 같이 표시 됩니다.  
  
 ![데이터 템플릿 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  
  
 이 예제에 대 한 설명을 완성 되었습니다. 전체 샘플을 참조 하십시오. [데이터 템플릿 샘플 소개](http://go.microsoft.com/fwlink/?LinkID=160009)합니다.  
  
<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>스타일 및 템플릿 ItemsControl  
 경우에는 <xref:System.Windows.Controls.ItemsControl> 은 사용할 수 있는 유일한 컨트롤 형식이 아닙니다는 <xref:System.Windows.DataTemplate> 는 것은 아주 일반적인 시나리오에 바인딩하는 <xref:System.Windows.Controls.ItemsControl> 컬렉션에 있습니다. 에 [DataTemplate에 어떠한 항목이 포함](#what_belongs_in_datatemplate) 는 지금까지 설명한 섹션의 정의 <xref:System.Windows.DataTemplate> 만 데이터의 표현과 넘지 않도록 해야 합니다. 사용할 수 없는 경우를 확인 하기 위해는 <xref:System.Windows.DataTemplate> 에서 제공 하는 다른 스타일 및 템플릿 속성을 이해 해야는 <xref:System.Windows.Controls.ItemsControl>합니다. 다음 예제는 이러한 각 속성의 기능을 설명 하기 위해 설계 됩니다. <xref:System.Windows.Controls.ItemsControl> 동일 하 게 바인딩된이 예에서 `Tasks` 이전 예제와 같이 컬렉션입니다. 데모에 대 한 용도, 스타일 및 템플릿이 예제의 모든 인라인으로 선언 된 됩니다.  
  
 [!code-xml[DataTemplatingIntro_snip#ItemsControlProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 다음은 렌더링 될 때 예의 스크린샷입니다.  
  
 ![ItemsControl 예제 스크린 샷](../../../../docs/framework/wpf/data/media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 사용 하는 대신에 유의 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>를 사용할 수는 <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>합니다. 예제는 이전 섹션을 참조 하십시오. 마찬가지로, 사용 하는 대신는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>를 사용 하는 옵션이 있습니다는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>합니다.  
  
 다른 두 개의 스타일 관련 속성은 <xref:System.Windows.Controls.ItemsControl> 다음은 표시 되지 않습니다 있는 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> 및 <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>합니다.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>계층적 데이터에 대 한 지원  
 지금까지 바인딩할 하 고 단일 컬렉션을 표시 하는 방법에 살펴본만 합니다. 다른 컬렉션을 포함 하는 컬렉션을 경우가 있습니다. <xref:System.Windows.HierarchicalDataTemplate> 클래스와 함께 사용할 수 있습니다는 <xref:System.Windows.Controls.HeaderedItemsControl> 이러한 데이터를 표시 하는 형식입니다. 다음 예에서 `ListLeagueList` 목록은 `League` 개체입니다. 각 `League` 개체에는 `Name` 컬렉션과 `Division` 개체입니다. 각 `Division` 에 `Name` 컬렉션과 `Team` 개체 및 각 `Team` 개체에는 `Name`합니다.  
  
 [!code-xml[HierarchicalDataTemplateSnippet#HDT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 예를 사용 하 여 보여 줍니다 <xref:System.Windows.HierarchicalDataTemplate>, 다른 목록을 포함 하는 목록 데이터를 쉽게 표시할 수 있습니다. 다음은 예제의 스크린샷입니다.  
  
 ![HierarchicalDataTemplate 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [DataTemplate에서 생성 된 요소 찾기](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)   
 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [GridView 열 머리글 스타일 및 템플릿 개요](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)