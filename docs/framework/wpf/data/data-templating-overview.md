---
title: 데이터 템플릿 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
ms.openlocfilehash: 7aed418fe5e2c7d8a217f3016655f39c99300d53
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="data-templating-overview"></a>데이터 템플릿 개요
WPF 데이터 템플릿 모델을 사용하면 데이터 표시를 매우 유연하게 정의할 수 있습니다. WPF 컨트롤에는 데이터 표시의 사용자 지정을 지원하는 기본 제공 기능이 있습니다. 이 항목에는 먼저 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.DataTemplate> 하 고 다음 사용자 지정 논리 및 계층적 데이터의 표시에 대 한 지원에 따라 템플릿 선택과 같은 다른 데이터 템플릿 기능을 소개 합니다.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 데이터 템플릿 기능을 집중적으로 살펴보고 데이터 바인딩 개념은 소개하지 않습니다. 기본 데이터 바인딩 개념에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.  
  
 <xref:System.Windows.DataTemplate> 에 대 한 데이터의 표현을 이며 WPF 스타일 및 템플릿 모델에서 제공 하는 많은 기능 중 하나입니다. 대 한 WPF 스타일 및 템플릿 등 모델을 사용 하는 방법의 개요는 <xref:System.Windows.Style> 컨트롤에서 속성을 설정 하려면 참조는 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md) 항목입니다.  
  
 또한 이해 하는 `Resources`, 하는 기본적으로 개체와 같은 있게 <xref:System.Windows.Style> 및 <xref:System.Windows.DataTemplate> 재사용 가능 합니다. 리소스에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하세요.  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>데이터 템플릿 기본 사항  
  
 그 이유를 설명 하기 위해 <xref:System.Windows.DataTemplate> 중요 한 데이터 바인딩 예제를 살펴보겠습니다. 이 예제에는 한 <xref:System.Windows.Controls.ListBox> 목록은에 바인딩된 `Task` 개체입니다. 각 `Task` 개체에는 `TaskName`(string), `Description`(string), `Priority`(int)와 함께 값이 `Home` 및 `Work`인 `Enum`을 나타내는 `TaskType` 형식 속성이 있습니다.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>DataTemplate 사용 안 함  
 없이 <xref:System.Windows.DataTemplate>, 우리의 <xref:System.Windows.Controls.ListBox> 모양이 다음과 같습니다.  
  
 ![데이터 템플릿 샘플 스크린샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 특정 지침, 없이 거는 <xref:System.Windows.Controls.ListBox> 기본 호출에 의해 `ToString` 컬렉션에 개체를 표시 하려고 할 때입니다. 따라서 경우는 `Task` 재정의 개체는 `ToString` 메서드를 하면 <xref:System.Windows.Controls.ListBox> 기본 컬렉션의 각 원본 개체의 문자열 표현을 표시 합니다.  
  
 예를 들어 `Task` 클래스가 이 방식으로 `ToString` 메서드를 재정의하면 `name`은 `TaskName` 속성에 대한 필드입니다.  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 그런 다음 <xref:System.Windows.Controls.ListBox> 은 다음과 같습니다.  
  
 ![데이터 템플릿 샘플 스크린샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 하지만 이 방법은 제한적이고 유연하지 않습니다. 또한 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 바인딩할 경우 `ToString`을 재정의할 수 없습니다.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>간단한 DataTemplate 정의  
 솔루션 정의 하는 것을 <xref:System.Windows.DataTemplate>합니다. 작업을 수행 하는 한 가지 방법은 설정 하는 것은 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성의는 <xref:System.Windows.Controls.ListBox> 에 <xref:System.Windows.DataTemplate>합니다. 지정 하 여 <xref:System.Windows.DataTemplate> 데이터 개체의 표시 구조가 됩니다. 다음 <xref:System.Windows.DataTemplate> 은 매우 단순 합니다. 세 개의 각 항목에 나타나는 지침 하 게 조정할 <xref:System.Windows.Controls.TextBlock> 내의 요소는 <xref:System.Windows.Controls.StackPanel>합니다. 각 <xref:System.Windows.Controls.TextBlock> 요소가의 속성에 바인딩된는 `Task` 클래스입니다.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 이 항목의 예제에서 기본 데이터는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체의 컬렉션입니다. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 바인딩할 경우 기본 개념은 같지만 약간의 구문적 차이점이 있습니다. 대신 예를 들어 `Path=TaskName`, 설정한 <xref:System.Windows.Data.Binding.XPath%2A> 를 `@TaskName` (경우 `TaskName` 의 특성은 프로그램 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 노드).  
  
 이제 우리 <xref:System.Windows.Controls.ListBox> 은 다음과 같습니다.  
  
 ![데이터 템플릿 샘플 스크린샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>DataTemplate을 리소스로 만들기  
 위의 예에서 정의 <xref:System.Windows.DataTemplate> 인라인 합니다. 더 일반적인 방법은 다음 예제와 같이 재사용 가능한 개체가 될 수 있도록 리소스 섹션에서 데이터 템플릿을 정의하는 것입니다.  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 이제 다음 예제와 같이 `myTaskTemplate`을 리소스로 사용할 수 있습니다.  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 때문에 `myTaskTemplate` 리소스에는 이제 사용 하는 속성을 가진 다른 컨트롤에 사용할 수는 <xref:System.Windows.DataTemplate> 유형입니다. 표시 된 대로 위에서 대 한 <xref:System.Windows.Controls.ItemsControl> 와 같은 개체는 <xref:System.Windows.Controls.ListBox>, 이기는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성입니다. 에 대 한 <xref:System.Windows.Controls.ContentControl> 개체는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성입니다.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>DataType 속성  
 <xref:System.Windows.DataTemplate> 클래스에는 <xref:System.Windows.DataTemplate.DataType%2A> 매우 비슷하지만 속성은 <xref:System.Windows.Style.TargetType%2A> 의 속성은 <xref:System.Windows.Style> 클래스입니다. 따라서 지정 하는 대신는 `x:Key` 에 대 한는 <xref:System.Windows.DataTemplate> 위의 예에는 다음을 수행할 수 있습니다.  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 이 <xref:System.Windows.DataTemplate> 모두에 게 자동으로 적용 `Task` 개체입니다. 이 경우 `x:Key`는 암시적으로 설정됩니다. 따라서이 할당 하는 경우 <xref:System.Windows.DataTemplate> 는 `x:Key` 값을 암시적으로 재정의 하는 `x:Key` 및 <xref:System.Windows.DataTemplate> 자동으로 적용 합니다.  
  
 바인딩하는 경우는 <xref:System.Windows.Controls.ContentControl> 의 컬렉션에 `Task` 개체는 <xref:System.Windows.Controls.ContentControl> 위의 사용 하지 않는 <xref:System.Windows.DataTemplate> 자동으로 합니다. 때문에 대 한 바인딩은 <xref:System.Windows.Controls.ContentControl> 는 전체 컬렉션 또는 개별 개체에 바인딩할 인지 구분 하기 위해 더 많은 정보가 필요 합니다. 경우에 <xref:System.Windows.Controls.ContentControl> 의 선택 영역 추적는 <xref:System.Windows.Controls.ItemsControl> 설정할 수 있습니다 형식은 <xref:System.Windows.Data.Binding.Path%2A> 속성의는 <xref:System.Windows.Controls.ContentControl> 에 바인딩 "`/`" 현재 항목에 관심이 나타내기 위해 합니다. 예제를 보려면 [선택에 따라 수집 및 표시 정보에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)을 참조하세요. 지정 하면 그렇지 않은 경우는 <xref:System.Windows.DataTemplate> 명시적으로 설정 하 여는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성입니다.  
  
 <xref:System.Windows.DataTemplate.DataType%2A> 속성은 경우에 특히 유용는 <xref:System.Windows.Data.CompositeCollection> 여러 유형의 데이터 개체입니다. 예제를 보려면 [CompositeCollection 구현](../../../../docs/framework/wpf/data/how-to-implement-a-compositecollection.md)을 참조하세요.  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>DataTemplate에 자세히 추가  
 현재 데이터에는 필요한 정보가 함께 표시되지만 분명히 개선의 여지가 있습니다. 추가 하 여에 프레젠테이션을 개선 보겠습니다는 <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Grid>, 및 일부 <xref:System.Windows.Controls.TextBlock> 표시 되는 데이터를 설명 하는 요소입니다.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 다음 스크린 샷에 표시 된 <xref:System.Windows.Controls.ListBox> 수정이 <xref:System.Windows.DataTemplate>:  
  
 ![데이터 템플릿 샘플 스크린샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 설정할 수 있습니다 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 를 <xref:System.Windows.HorizontalAlignment.Stretch> 에 <xref:System.Windows.Controls.ListBox> 항목의 너비 전체 공간을 차지 하 고 있는지 확인 하려면:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 와 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 속성이로 설정 <xref:System.Windows.HorizontalAlignment.Stretch>, <xref:System.Windows.Controls.ListBox> 모양이 다음과 같습니다.  
  
 ![데이터 템플릿 샘플 스크린샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>DataTrigger를 사용하여 속성 값 적용  
 현재 표시로는 `Task`가 홈 작업 또는 사무실 작업인지 알 수 없습니다. 다시 말하지만, `Task` 개체에는 값이 `Home` 및 `Work`인 열거형을 나타내는 `TaskType` 형식의 `TaskType` 속성이 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.DataTrigger> 설정는 <xref:System.Windows.Controls.Border.BorderBrush%2A> 라는 요소의 `border` 를 `Yellow` 경우는 `TaskType` 속성은 `TaskType.Home`합니다.  
  
 [!code-xaml[DataTemplatingIntro#DT](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 이제 응용 프로그램은 다음과 같이 표시됩니다. 홈 작업에는 노란색 테두리가 표시되고 사무실 작업에는 바다색 테두리가 표시됩니다.  
  
 ![데이터 템플릿 샘플 스크린샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 이 예제는 <xref:System.Windows.DataTrigger> 사용 하 여 한 <xref:System.Windows.Setter> 속성 값을 설정 합니다. 트리거 클래스에서 <xref:System.Windows.TriggerBase.EnterActions%2A> 및 <xref:System.Windows.TriggerBase.ExitActions%2A> 일련의 애니메이션과 같은 작업을 시작할 수 있도록 하는 속성입니다. 또한 이기도 한 <xref:System.Windows.MultiDataTrigger> 여러 데이터 바인딩된 속성 값을 기반으로 하는 변경 내용을 적용할 수 있는 클래스입니다.  
  
 동일한 결과 얻을 수도에 바인딩하는 것은 <xref:System.Windows.Controls.Border.BorderBrush%2A> 속성을는 `TaskType` 속성 및 사용에 따라 색을 반환 하는 값 변환기는 `TaskType` 값입니다. 변환기를 사용하여 위 효과를 만드는 방법이 성능 면에서 약간 더 효율적입니다. 또한 자체 변환기를 만들면 자체 논리를 제공할 수 있으므로 더 유연하게 작업할 수 있습니다. 결국 선택하는 방법은 시나리오와 기본 설정에 따라 결정됩니다. 변환기를 작성 하는 방법에 대 한 정보를 참조 하십시오. <xref:System.Windows.Data.IValueConverter>합니다.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>DataTemplate은 무엇으로 구성되나요?  

앞의 예에서 트리거 내에서 배치는 <xref:System.Windows.DataTemplate> 를 사용 하는 <xref:System.Windows.DataTemplate>합니다.<xref:System.Windows.DataTemplate.Triggers%2A> 속성입니다. <xref:System.Windows.Setter> 트리거의 요소 속성의 값을 설정 (의 <xref:System.Windows.Controls.Border> 요소) 내에서 <xref:System.Windows.DataTemplate>합니다. 그러나 경우 속성 하는 프로그램 `Setters` 고려 하는 현재 내에 있는 요소의 속성 <xref:System.Windows.DataTemplate>, 사용 하 여 속성을 설정 하려면 더 적합할 수 있습니다는 <xref:System.Windows.Style> 위한는 <xref:System.Windows.Controls.ListBoxItem> 클래스 (하는 경우는 바인딩할 컨트롤은 한 <xref:System.Windows.Controls.ListBox>). 예를 들어, 원하는 프로그램 <xref:System.Windows.Trigger> 애니메이션 효과를 줄의 <xref:System.Windows.UIElement.Opacity%2A> 값 항목의 마우스의 항목을 가리킬 때 트리거를 정의 내에서 <xref:System.Windows.Controls.ListBoxItem> 스타일입니다. 예제를 보려면 [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(스타일 지정 및 템플릿 샘플 소개)을 참조하세요.
  
 일반적으로 한다는 점에 유의 하는 <xref:System.Windows.DataTemplate> 생성 된 각 적용 되 고 <xref:System.Windows.Controls.ListBoxItem> (적용 실제로 방법과 위치에 대 한 자세한 내용은 참조는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 페이지입니다.). 프로그램 <xref:System.Windows.DataTemplate> 프레젠테이션 및 데이터 개체의 모양을 관련 됩니다. 대부분의 경우 어떤 항목이 같은 표현의 다른 모든 측면 같이 선택 방법을 <xref:System.Windows.Controls.ListBox> 에 항목이 배치의 정의에 속하지 않는 <xref:System.Windows.DataTemplate>합니다. 예제를 보려면 [ItemsControl 스타일 지정 및 템플릿 만들기](#DataTemplating_ItemsControl) 섹션을 참조하세요.  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>데이터 개체의 속성에 따라 DataTemplate 선택  
 [DataType 속성](#Styling_DataType) 섹션에서 다양한 데이터 개체에 대한 서로 다른 데이터 템플릿을 정의할 수 있음을 설명했습니다. 있는 경우 특히 유용는 <xref:System.Windows.Data.CompositeCollection> 서로 다른 형식이 나 다른 형식의 항목을 사용 하 여 컬렉션의 합니다. 에 [적용 속성 값을 사용 하 여 Datatrigger](#DataTrigger_to_Apply_Property_Values) 섹션을 보여 주었습니다 같은 종류의 데이터 개체의 컬렉션을 사용할 경우 만들 수 있습니다는 <xref:System.Windows.DataTemplate> 다음 트리거를 사용 하 여의 속성 값에 따라 변경 내용을 적용 하려면 각 데이터 개체입니다. 그러나 트리거를 사용하여 속성 값을 적용하거나 애니메이션을 시작할 수 있지만 트리거는 데이터 개체의 구조를 재구성할 수 있는 유연성이 없습니다. 일부 시나리오는 서로 다른 해야 할 수 있습니다 <xref:System.Windows.DataTemplate> 데이터에 대 한 개체에 동일한 형식은 같지만 서로 다른 속성입니다.  
  
 예를 들어 `Task` 개체의 `Priority` 값이 `1`일 경우 스스로 주의할 수 있도록 완전히 다른 모양을 지정해야 할 수 있습니다. 만들 경우에 <xref:System.Windows.DataTemplate> 높은 우선 순위를 표시 하기 위한 `Task` 개체입니다. 다음을 추가 해 보겠습니다 <xref:System.Windows.DataTemplate> 리소스 섹션에:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 이 예제에서는 <xref:System.Windows.DataTemplate>합니다.<xref:System.Windows.FrameworkTemplate.Resources%2A> 속성입니다. 내의 요소에서 공유 섹션에 정의 된 리소스는 <xref:System.Windows.DataTemplate>합니다.  
  
 선택할 수는 논리를 제공 <xref:System.Windows.DataTemplate> 에 따라 사용 하는 `Priority` 값 데이터 개체의 서브 클래스를 만든 <xref:System.Windows.Controls.DataTemplateSelector> 재정의 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 메서드. 다음 예제에서는 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 의 값에 따라 적절 한 템플릿을 반환 하는 논리를 제공 하는 메서드는 `Priority` 속성입니다. 반환할 템플릿의 상위 리소스 참조는 <xref:System.Windows.Window> 요소입니다.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 그런 다음 `TaskListDataTemplateSelector`를 리소스로 선언할 수 있습니다.  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 템플릿 선택기 리소스를 사용 하려면에 할당 된 <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> 속성은 <xref:System.Windows.Controls.ListBox>합니다. <xref:System.Windows.Controls.ListBox> 호출은 <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> 의 메서드는 `TaskListDataTemplateSelector` 기본 컬렉션의 항목에는 각각에 대 한 합니다. 이 호출은 데이터 개체를 항목 매개 변수로 전달합니다. <xref:System.Windows.DataTemplate> 에서 반환 하는 메서드를 해당 데이터 개체에 적용 합니다.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 원위치에서 템플릿 선택기는 <xref:System.Windows.Controls.ListBox> 다음과 같이 표시 됩니다.  
  
 ![데이터 템플릿 샘플 스크린샷](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

이것으로 이 예제에 대한 설명을 마칩니다. 전체 샘플을 보려면 [Introduction to Data Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro)(데이터 템플릿 샘플 소개)을 참조하세요.

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>ItemsControl 스타일 지정 및 템플릿 만들기  
 경우에는 <xref:System.Windows.Controls.ItemsControl> 은 사용할 수 있는 유일한 컨트롤 형식이 아닙니다는 <xref:System.Windows.DataTemplate> 는 것은 매우 일반적인 시나리오에 바인딩하는 <xref:System.Windows.Controls.ItemsControl> 컬렉션에 있습니다. 에 [DataTemplate에 포함 되](#what_belongs_in_datatemplate) 논의 하는 섹션의 정의 <xref:System.Windows.DataTemplate> 관련 된 데이터의 표현을 있어야 합니다. 사용할 수 없는 경우를 확인 하기 위해는 <xref:System.Windows.DataTemplate> 제공한 다른 스타일 및 템플릿 속성을 이해 해야는 <xref:System.Windows.Controls.ItemsControl>합니다. 다음 예제는 이러한 각 속성의 기능을 설명하도록 디자인되어 있습니다. <xref:System.Windows.Controls.ItemsControl> 이 예에서 동일한에 바인딩된 `Tasks` 앞의 예와 수집 합니다. 설명을 위해 이 예제의 스타일 및 템플릿은 모두 인라인으로 선언됩니다.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 렌더링될 때 예제의 스크린샷은 다음과 같습니다.  
  
 ![ItemsControl 예제 스크린샷](../../../../docs/framework/wpf/data/media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 대신는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>를 사용할 수 있습니다는 <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>합니다. 예제를 보려면 이전 섹션을 참조하세요. 마찬가지로, 사용 하는 대신는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>를 사용 하는 옵션이 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>합니다.  
  
 다른 두 개의 스타일 관련 속성은 <xref:System.Windows.Controls.ItemsControl> 다음은 표시 되지 않습니다는 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> 및 <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>합니다.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>계층적 데이터 지원  
 지금까지는 단일 컬렉션에 바인딩하고 단일 컬렉션을 표시하는 방법만 살펴봤습니다. 경우에 따라 다른 컬렉션이 포함된 컬렉션이 있을 수 있습니다. <xref:System.Windows.HierarchicalDataTemplate> 클래스와 함께 사용할 수 있습니다는 <xref:System.Windows.Controls.HeaderedItemsControl> 이러한 데이터를 표시 하는 형식입니다. 다음 예제에서 `ListLeagueList`는 `League` 개체 목록입니다. 각 `League` 개체에는 `Name` 및 `Division` 개체 컬렉션이 포함됩니다. 각 `Division` 에는 `Name` 및 `Team` 개체 컬렉션이 포함되고 각 `Team` 개체에는 `Name`이 포함됩니다.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 예제를 사용 하 여 보여 줍니다 <xref:System.Windows.HierarchicalDataTemplate>, 다른 목록을 포함 하는 목록 데이터를 쉽게 표시할 수 있습니다. 예제 스크린샷은 다음과 같습니다.  
  
 ![HierarchicalDataTemplate 샘플 스크린샷](../../../../docs/framework/wpf/data/media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [DataTemplate에서 생성된 요소 찾기](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [GridView 열 머리글 스타일 및 템플릿 개요](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)
