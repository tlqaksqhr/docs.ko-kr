---
title: "데이터 바인딩 개요 | Microsoft Docs"
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
  - "데이터 바인딩, 데이터 바인딩 정보"
  - "데이터 바인딩을 위한 변환"
  - "데이터 바인딩(data binding), 데이터 바인딩 정보"
  - "바인딩을 위한 데이터 변환"
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
caps.latest.revision: 78
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 75
---
# 데이터 바인딩 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩은 응용 프로그램에서 데이터를 표시하고 데이터와 상호 작용하는 간단하고 편리한 방법입니다.  다양한 데이터 소스에서 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체 및 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]의 형태로 데이터에 요소를 바인딩할 수 있습니다.  <xref:System.Windows.Controls.ContentControl>\(예: <xref:System.Windows.Controls.Button>\) 및 <xref:System.Windows.Controls.ItemsControl>\(예: <xref:System.Windows.Controls.ListBox>와 <xref:System.Windows.Controls.ListView>\)에는 데이터 항목 컬렉션이나 단일 데이터 항목에 유연하게 스타일을 지정할 수 있도록 기본 제공되는 기능이 있습니다.  데이터를 기반으로 정렬, 필터 및 그룹 보기를 생성할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 데이터 바인딩 기능에는 데이터 바인딩을 지원하는 다양한 속성, 데이터의 유연한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 표현 및 비즈니스 논리와 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 명확한 분리와 같은 기존 모델보다 향상된 여러 가지 기능이 있습니다.  
  
 이 항목에서는 먼저 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩에 대한 핵심 개념을 살펴본 다음 <xref:System.Windows.Data.Binding> 클래스 및 기타 데이터 바인딩 기능을 사용하는 방법에 대해 살펴봅니다.  
  
   
  
<a name="what_is_data_binding"></a>   
## 데이터 바인딩의 정의  
 데이터 바인딩은 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 비즈니스 논리를 서로 연결하는 프로세스입니다.  바인딩 설정이 올바르고 데이터가 적절한 알림을 제공하는 경우에는 데이터의 값이 변경될 때 데이터에 바인딩된 요소에 변경 내용이 자동으로 반영됩니다.  또한 요소에서 데이터의 외부 표현이 변경되면 내부 데이터가 자동으로 업데이트되어 변경 내용이 반영됩니다.  예를 들어 사용자가 <xref:System.Windows.Controls.TextBox> 요소의 값을 편집하면 해당 변경에 따라 내부 데이터 값이 자동으로 업데이트됩니다.  
  
 데이터 바인딩의 일반적인 용도는 서버 또는 로컬 구성 데이터를 폼이나 기타 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤에 배치하는 것입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 이 개념이 더욱 확장되어 다양한 속성을 여러 가지 데이터 소스에 바인딩할 수 있게 되었습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 요소의 [종속성 속성](GTMT)을 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체\([!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] 개체 또는 웹 서비스 및 웹 속성과 연결된 개체 포함\) 및 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 바인딩할 수 있습니다.  
  
 데이터 바인딩의 예로 [Data Binding 데모](http://go.microsoft.com/fwlink/?LinkID=163703)에서 다음 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 살펴보겠습니다.  
  
 ![데이터 바인딩 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/databinding-databindingdemo.png "DataBinding\_DataBindingDemo")  
  
 위 그림은 경매 항목의 목록을 표시하는 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]입니다.  이 응용 프로그램은 데이터 바인딩의 다음 기능을 보여 줍니다.  
  
-   <xref:System.Windows.Controls.ListBox>의 콘텐츠가 *AuctionItem* 개체의 컬렉션에 바인딩됩니다.  *AuctionItem* 개체에는 *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* 등의 속성이 있습니다.  
  
-   <xref:System.Windows.Controls.ListBox>에 표시되는 데이터\(*AuctionItem* 개체\)는 템플릿으로 사용되어 각 항목에 대한 설명과 현재 가격을 표시합니다.  이는 <xref:System.Windows.DataTemplate>을 사용하여 수행됩니다.  또한 각 항목의 모양은 표시되는 *AuctionItem*의 *SpecialFeatures* 값에 따라 달라집니다.  *AuctionItem*의 *SpecialFeatures* 값이 *Color*이면 항목에 파란색 테두리가 표시됩니다.  값이 *Highlight*이면 항목에 주황색 테두리와 별이 표시됩니다.  데이터 템플릿에 대한 내용은 [데이터 템플릿](#data_templating) 단원에서 볼 수 있습니다.  
  
-   사용자는 제공된 <xref:System.Windows.Controls.CheckBox>를 사용하여 데이터를 그룹화하거나, 필터링하거나, 정렬할 수 있습니다.  위의 이미지에서는 "Group by category" 및 "Sort by category and date" <xref:System.Windows.Controls.CheckBox>가 선택되어 있습니다.  데이터가 제품 범주별로 그룹화되어 있으며 범주 이름은 사전순으로 정렬되어 있음을 볼 수 있습니다.  이미지에서 확인하기는 쉽지 않지만 항목은 각 범주 내에서 시작 날짜별로 정렬되어 있습니다.  이 기능은 *컬렉션 뷰*를 사용하여 수행됩니다.  컬렉션 뷰에 대한 내용은 [컬렉션에 바인딩](#binding_to_collections) 단원에서 다룹니다.  
  
-   사용자가 항목을 선택하면 <xref:System.Windows.Controls.ContentControl>이 선택된 항목의 세부 사항을 표시합니다.  이를 *마스터\-세부 시나리오*라고 합니다.  이러한 형식의 바인딩 시나리오에 대한 내용은 [마스터\-세부 시나리오](#master_detail_scenario) 단원에서 볼 수 있습니다.  
  
-   *StartDate* 속성의 형식은 밀리초 단위의 시간까지 포함된 날짜를 반환하는 <xref:System.DateTime>입니다.  이 응용 프로그램에서는 더 짧은 날짜 문자열을 표시하기 위해 사용자 지정 변환기를 사용합니다.  변환기에 대한 내용은 [데이터 변환](#data_conversion) 단원에서 볼 수 있습니다.  
  
 사용자가 *Add Product* 단추를 클릭하면 다음 폼이 나타납니다.  
  
 ![제품 목록 추가 페이지](../../../../docs/framework/wpf/data/media/databinding-demo-addproductlisting.png "DataBinding\_Demo\_AddProductListing")  
  
 사용자는 폼의 필드를 편집하고, 짧은 미리 보기와 더 자세한 미리 보기 창을 사용하여 제품 목록을 미리 볼 수 있으며 *submit*을 클릭하여 새 제품 목록을 추가할 수 있습니다.  기존의 모든 그룹화, 필터링 및 정렬 기능이 새 항목에 적용됩니다.  이 특별한 경우에서는 위의 이미지에 입력된 항목이 *Computer* 범주에서 두 번째 항목으로 표시됩니다.  
  
 이 이미지에 표시되지 않은 것은 *Start Date* <xref:System.Windows.Controls.TextBox>에 제공되는 유효성 검사 논리입니다.  사용자가 올바르지 않은 날짜\(형식이 올바르지 않은 날짜나 지난 날짜\)를 입력하면 <xref:System.Windows.Controls.ToolTip>이 표시되고 <xref:System.Windows.Controls.TextBox> 옆에 빨간색 느낌표가 나타납니다.  [데이터 유효성 검사](#data_validation) 단원에서는 유효성 검사 논리를 만드는 방법을 설명합니다.  
  
 위에서 개괄적으로 설명한 데이터 바인딩의 다른 기능을 살펴보기 전에 다음 단원에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 이해에 필수적인 기본 개념을 살펴보겠습니다.  
  
<a name="basic_data_binding_concepts"></a>   
## 기본 데이터 바인딩 개념  
   
  
 바인딩하려는 요소 및 데이터 소스의 특성에 관계없이 각 바인딩은 항상 다음 그림에 나타나는 모델을 따릅니다.  
  
 ![기본 데이터 바인딩 다이어그램](../../../../docs/framework/wpf/data/media/databindingmostbasic.png "DataBindingMostBasic")  
  
 위 그림에서 볼 수 있듯이, 데이터 바인딩은 기본적으로 [바인딩 대상](GTMT)과 [바인딩 소스](GTMT) 사이의 다리 역할을 합니다.  그림에서는 다음 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 개념을 보여 줍니다.  
  
-   일반적으로 각 바인딩에는 4가지 구성 요소인 [바인딩 대상](GTMT) 개체, 대상 속성, [바인딩 소스](GTMT) 및 사용할 [바인딩 소스](GTMT) 값에 대한 경로가 있습니다.  예를 들어 <xref:System.Windows.Controls.TextBox>의 내용을 *Employee* 개체의 *Name* 속성에 바인딩하려는 경우 대상 개체는 <xref:System.Windows.Controls.TextBox>이고 대상 속성은 <xref:System.Windows.Controls.TextBox.Text%2A> 속성이며 사용할 값은 *Name*, 소스 개체는 *Employee* 개체입니다.  
  
-   대상 속성은 [종속성 속성](GTMT)이어야 합니다.  <xref:System.Windows.UIElement> 속성 대부분은 [종속성 속성](GTMT)이며 읽기 전용 속성을 제외한 대부분의 [종속성 속성](GTMT)은 기본적으로 데이터 바인딩을 지원합니다.  <xref:System.Windows.DependencyObject> 형식만 [종속성 속성](GTMT)을 정의할 수 있으며 모든 <xref:System.Windows.UIElement>는 <xref:System.Windows.DependencyObject>에서 파생됩니다.  
  
-   그림에는 지정되어 있지 않지만 [바인딩 소스](GTMT) 개체는 사용자 지정 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체로 제한되지 않습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩에서는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 및 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 형식의 데이터를 지원합니다.  몇 가지 예제를 제공하기 위해 바인딩 소스는 <xref:System.Windows.UIElement>, 목록 개체, [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] 데이터나 웹 서비스와 연결된 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 또는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터가 들어 있는 XmlNode 중에 선택할 수 있습니다.  자세한 내용은 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)를 참조하십시오.  
  
 다른 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] 항목을 읽을 때 바인딩을 설정하는 것은 곧 [바인딩 대상](GTMT)*을* [바인딩 소스](GTMT)에 바인딩하는 것임을 기억하십시오.  예를 들어 데이터 바인딩을 사용하여 일부 내부 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터를 <xref:System.Windows.Controls.ListBox>에 표시하는 것은 곧 <xref:System.Windows.Controls.ListBox>를 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 바인딩하는 것입니다.  
  
 바인딩을 설정하려면 <xref:System.Windows.Data.Binding> 개체를 사용해야 합니다.  이 항목의 나머지 부분에서는 <xref:System.Windows.Data.Binding> 개체의 사용법과 몇 가지 속성 및 여러 가지 관련 개념을 설명합니다.  
  
<a name="direction_of_data_flow"></a>   
### 데이터 흐름의 방향  
 앞의 설명과 위 그림의 화살표에서 알 수 있듯이, 바인딩의 데이터 흐름은 [바인딩 대상](GTMT)에서 [바인딩 소스](GTMT)로\(예를 들어 사용자가 <xref:System.Windows.Controls.TextBox>의 값을 편집하면 소스 값이 변경됨\) 흐르거나 바인딩 소스가 적절한 알림을 제공하는 경우에는 [바인딩 소스](GTMT)에서 [바인딩 대상](GTMT)으로 흐를 수 있습니다\(예를 들어 [바인딩 소스](GTMT)가 변경되면 <xref:System.Windows.Controls.TextBox> 내용이 업데이트됨\).  
  
 사용자가 응용 프로그램에서 데이터를 변경했을 때 이 변경 내용이 소스 개체로 전파되어야 할 수 있습니다.  또는 사용자가 소스 데이터를 업데이트하지 못하도록 해야 할 수 있습니다.  <xref:System.Windows.Data.Binding> 개체의 <xref:System.Windows.Data.Binding.Mode%2A> 속성을 설정하여 이를 제어할 수 있습니다.  다음 그림에서는 여러 가지 형태의 데이터 흐름을 보여 줍니다.  
  
 ![데이터 바인딩 데이터 흐름](../../../../docs/framework/wpf/data/media/databinding-dataflow.png "DataBinding\_DataFlow")  
  
-   <xref:System.Windows.Data.BindingMode> 바인딩을 사용하면, 소스 속성이 변경된 경우 대상 속성이 자동으로 업데이트되지만 대상 속성이 변경된 경우에는 변경 내용이 소스 속성으로 전파되지 않습니다.  이 형식의 바인딩은 바인딩되는 컨트롤이 암시적으로 읽기 전용인 경우 적합합니다.  예를 들어 주식 시세 표시기와 같은 소스에 바인딩하거나 대상 속성에 테이블의 데이터 바인딩된 배경색과 같이 변경을 위해 제공된 컨트롤 인터페이스가 없을 수 있습니다.  대상 속성의 변경 내용을 모니터링할 필요가 없는 경우 <xref:System.Windows.Data.BindingMode> 바인딩 모드를 사용하면 <xref:System.Windows.Data.BindingMode> 바인딩 모드의 오버헤드를 줄일 수 있습니다.  
  
-   <xref:System.Windows.Data.BindingMode> 바인딩의 경우에는 소스 속성이 변경되면 자동으로 대상 속성이 업데이트되고, 대상 속성이 변경되면 자동으로 소스 속성이 업데이트됩니다.  이 형식의 바인딩은 편집 가능한 폼이나 기타 완전 대화형 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오에 적합합니다.  대부분의 속성은 <xref:System.Windows.Data.BindingMode> 바인딩을 기본값으로 사용하지만 일부 [종속성 속성](GTMT)\(일반적으로 <xref:System.Windows.Controls.TextBox>의 <xref:System.Windows.Controls.TextBox.Text%2A> 속성 및 <xref:System.Windows.Controls.CheckBox>의 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 속성\)은 <xref:System.Windows.Data.BindingMode> 바인딩을 기본값으로 사용합니다.  기본적으로 [종속성 속성](GTMT)이 단방향으로 바인딩되는지 아니면 양방향으로 바인딩되는지를 확인하는 프로그래밍 방식은 <xref:System.Windows.DependencyProperty.GetMetadata%2A>를 사용하여 속성의 속성 메타데이터를 가져온 다음 <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A> 속성의 Boolean 값을 확인하는 것입니다.  
  
-   <xref:System.Windows.Data.BindingMode>는 <xref:System.Windows.Data.BindingMode> 바인딩의 반대입니다. 즉, 대상 속성이 변경될 때 소스 속성을 업데이트합니다.  이에 대한 한 가지 예제 시나리오는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에서 소스 값을 다시 확인하기만 하면 되는 경우입니다.  
  
-   그림에는 표시되지 않았지만 <xref:System.Windows.Data.BindingMode> 바인딩의 경우에는 소스 속성이 대상 속성을 초기화하지만 이후 변경은 전파되지 않습니다.  즉, 데이터 컨텍스트가 변경되고 있거나 데이터 컨텍스트의 개체가 변경된 경우에도 변경이 대상 속성에 반영되지 않는다는 것을 의미합니다.  이 형식의 바인딩은 현재 상태의 스냅숏이 사용하기에 적합하거나 데이터가 정적인 상황에서 데이터를 사용하는 경우 적합합니다.  또한 이 형식의 바인딩은 소스 속성의 값으로 대상 속성을 초기화하려고 하고 데이터 컨텍스트가 미리 알려지지 않은 경우 유용합니다.  이것은 소스 값이 변경되지 않는 경우 향상된 성능을 제공하는 보다 간단한 형식의 <xref:System.Windows.Data.BindingMode> 바인딩입니다.  
  
 소스 변경 내용을 검색하려면\(<xref:System.Windows.Data.BindingMode> 및 <xref:System.Windows.Data.BindingMode> 바인딩에 적용 가능\) 소스에서 <xref:System.ComponentModel.INotifyPropertyChanged>와 같은 적절한 속성 변경 알림 메커니즘을 구현해야 합니다.  <xref:System.ComponentModel.INotifyPropertyChanged> 구현에 대한 예제를 보려면 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조하십시오.  
  
 <xref:System.Windows.Data.Binding.Mode%2A> 속성 페이지에서 바인딩 모드에 대한 자세한 내용과 바인딩의 방향을 지정하는 방법에 대한 예제를 제공합니다.  
  
<a name="what_triggers_source_updates"></a>   
### 소스 업데이트를 트리거하는 항목  
 <xref:System.Windows.Data.BindingMode> 또는 <xref:System.Windows.Data.BindingMode>인 바인딩은 대상 속성의 변경 내용을 수신하고 해당 변경 내용을 다시 소스로 전파합니다.  이 과정을 소스 업데이트라고 합니다.  예를 들어 TextBox의 텍스트를 편집하여 기본 소스 값을 변경할 수 있습니다.  이전 단원에서 설명한 것처럼, 데이터 흐름의 방향은 바인딩의 <xref:System.Windows.Data.Binding.Mode%2A> 속성 값에 따라 결정됩니다.  
  
 하지만 텍스트를 편집하고 있을 때나 텍스트 편집을 마치고 마우스를 TextBox 외부로 움직였을 때 소스 값이 업데이트될까요?  소스 업데이트를 트리거할 항목은 바인딩의 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성에 따라 결정됩니다.  다음 그림에서 오른쪽 화살표의 점은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성의 역할을 보여 줍니다.  
  
 ![UpdateSourceTrigger 다이어그램](../../../../docs/framework/wpf/data/media/databindingupdatesourcetrigger.png "DataBindingUpdateSourceTrigger")  
  
 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값이 <xref:System.Windows.Data.UpdateSourceTrigger>이면 대상 속성이 변경되는 즉시 <xref:System.Windows.Data.BindingMode> 바인딩 또는 <xref:System.Windows.Data.BindingMode> 바인딩의 오른쪽 화살표가 가리키는 값이 업데이트됩니다.  하지만 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값이 <xref:System.Windows.Data.UpdateSourceTrigger>이면 대상 속성이 포커스를 잃었을 때에만 해당 값이 새 값으로 업데이트됩니다.  
  
 <xref:System.Windows.Data.Binding.Mode%2A> 속성과 비슷하게 여러 [종속성 속성](GTMT)의 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값은 서로 다릅니다.  <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger>이지만, 대부분의 [종속성 속성](GTMT)의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger>입니다.  이는 대상 속성이 변경될 때마다 소스 업데이트가 수행된다는 것을 의미합니다. 이러한 특징은 <xref:System.Windows.Controls.CheckBox> 및 기타 간단한 컨트롤에 적합합니다.  하지만 텍스트 필드의 경우에는 키 입력이 있을 때마다 업데이트하면 성능이 떨어지고, 일반적으로 사용자가 새 값을 커밋하기 전에 백스페이스 키를 누르고 입력 오류를 수정할 수 있는 기회가 없어집니다.  이런 이유 때문에 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger>가 아닌 <xref:System.Windows.Data.UpdateSourceTrigger>입니다.  
  
 [종속성 속성](GTMT)의 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값을 찾는 방법에 대해서는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 페이지를 참조하십시오.  
  
 다음 표에서는 <xref:System.Windows.Controls.TextBox>를 예제로 사용하여 각 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값에 대한 예제 시나리오를 제공합니다.  
  
|UpdateSourceTrigger 값|소스 값이 업데이트될 때|TextBox에 대한 예제 시나리오|  
|---------------------------|-------------------|-------------------------|  
|LostFocus\(<xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=fullName>의 기본값\)|TextBox 컨트롤이 포커스를 잃을 때|유효성 검사 논리와 연결된 <xref:System.Windows.Controls.TextBox>\(데이터 유효성 검사 단원 참조\)|  
|PropertyChanged|<xref:System.Windows.Controls.TextBox>에 입력할 때|채팅방 창의 <xref:System.Windows.Controls.TextBox> 컨트롤|  
|Explicit|응용 프로그램에서 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>를 호출할 때|편집 가능한 폼의 <xref:System.Windows.Controls.TextBox> 컨트롤\(사용자가 제출 단추를 클릭할 때만 소스 값 업데이트\)|  
  
 예제를 보려면 [TextBox 텍스트의 소스를 업데이트하는 시점 제어](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)를 참조하십시오.  
  
<a name="creating_a_binding"></a>   
## 바인딩 만들기  
   
  
 이전 단원에서 설명한 개념을 다시 요약하면, <xref:System.Windows.Data.Binding> 개체를 사용하여 바인딩을 만들며 각 바인딩에는 일반적으로 바인딩 대상, 대상 속성, 바인딩 소스 및 사용할 소스 값에 대한 경로의 네 구성 요소가 있습니다.  이 단원에서는 바인딩을 설정하는 방법을 설명합니다.  
  
 바인딩 소스 개체가 *SDKSample* 네임스페이스에 정의된 *MyData*라는 클래스인 다음 예제를 생각해 볼 수 있습니다.  설명을 위해 *MyData* 클래스에는 값이 "Red"로 설정되는 *ColorName*이라는 문자열 속성이 있습니다.  따라서 이 예제에서는 배경이 빨간색인 단추를 생성합니다.  
  
 [!code-xml[BindNonTextProperty#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 바인딩 선언 구문에 대한 자세한 설명과 코드에서 바인딩을 설정하는 방법에 대한 예제를 보려면 [바인딩 선언 개요](../../../../docs/framework/wpf/data/binding-declarations-overview.md)를 참조하십시오.  
  
 이 예제를 기본 다이어그램에 적용한 결과 그림은 다음과 같습니다.  여기에서 Background 속성이 기본적으로 <xref:System.Windows.Data.BindingMode> 바인딩을 지원하므로 이 예제에서는 <xref:System.Windows.Data.BindingMode> 바인딩입니다.  
  
 ![데이터 바인딩 다이어그램](../../../../docs/framework/wpf/data/media/databindingbuttonbackgroundexample.png "DataBindingButtonBackgroundExample")  
  
 <xref:System.Windows.Controls.Control.Background%2A> 속성의 형식이 <xref:System.Windows.Media.Brush>인데 *ColorName* 속성이 문자열 형식이어도 작동하는 이유가 궁금할 것입니다.  기본 형식 변환이 작동하기 때문이며 이에 대해서는 [데이터 변환](#data_conversion) 단원에서 설명합니다.  
  
<a name="specifying_the_binding_source"></a>   
### 바인딩 소스 지정  
 이전 예제에서는 <xref:System.Windows.Controls.DockPanel> 요소에 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 설정하여 바인딩 소스를 지정합니다.  그러면 <xref:System.Windows.Controls.Button>은 부모 요소인 <xref:System.Windows.Controls.DockPanel>에서 <xref:System.Windows.FrameworkElement.DataContext%2A> 값을 상속합니다.  바인딩 소스 개체는 바인딩의 네 가지 필수 구성 요소 중 하나입니다.  따라서 바인딩 소스 개체를 지정하지 않으면 바인딩은 아무 작업도 수행하지 않습니다.  
  
 바인딩 소스 개체를 지정하는 방법에는 몇 가지가 있습니다.  여러 속성을 같은 소스에 바인딩할 때는 부모 요소에 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 사용하는 방법이 유용합니다.  하지만 개별 바인딩 선언에서 바인딩 소스를 지정하는 것이 더 적합할 경우도 있습니다.  이전 예제의 경우 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 사용하는 대신 다음 예제에서처럼 단추의 바인딩 선언에 직접 <xref:System.Windows.Data.Binding.Source%2A> 속성을 설정하여 바인딩 소스를 지정할 수 있습니다.  
  
 [!code-xml[BindNonTextProperty#BackgroundBindingCompact](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 요소에 직접 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 설정하고, 상위에서 <xref:System.Windows.FrameworkElement.DataContext%2A> 값을 상속하고\(첫 번째 예제의 단추에서처럼\), <xref:System.Windows.Data.Binding>에 <xref:System.Windows.Data.Binding.Source%2A> 속성을 설정하여 바인딩 소스를 명시적으로 지정하는 방법\(이전 예제의 단추에서처럼\) 이외에도, <xref:System.Windows.Data.Binding.ElementName%2A> 속성 또는 <xref:System.Windows.Data.Binding.RelativeSource%2A> 속성을 사용하여 바인딩 소스를 지정할 수도 있습니다.  <xref:System.Windows.Data.Binding.ElementName%2A> 속성은 슬라이더를 사용하여 단추 너비를 조정하는 경우처럼 응용 프로그램의 다른 요소에 바인딩할 때 유용합니다.  <xref:System.Windows.Data.Binding.RelativeSource%2A> 속성은 <xref:System.Windows.Controls.ControlTemplate> 또는 <xref:System.Windows.Style>에서 바인딩을 지정할 때 유용합니다.  자세한 내용은 [바인딩 소스 지정](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)을 참조하십시오.  
  
<a name="specifying_the_path_to_the_value"></a>   
### 값에 대한 경로 지정  
 바인딩 소스가 개체일 때는 <xref:System.Windows.Data.Binding.Path%2A> 속성을 사용하여 바인딩에 사용할 값을 지정합니다.  [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 바인딩할 때는 <xref:System.Windows.Data.Binding.XPath%2A> 속성을 사용하여 값을 지정합니다.  경우에 따라서는 데이터가 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]일 경우에도 <xref:System.Windows.Data.Binding.Path%2A> 속성을 사용하는 것이 적절할 수 있습니다.  예를 들어 반환된 XmlNode\(XPath 쿼리의 결과로\)의 Name 속성에 액세스하려면 <xref:System.Windows.Data.Binding.XPath%2A> 속성 이외에 <xref:System.Windows.Data.Binding.Path%2A> 속성도 사용해야 합니다.  
  
 구문 정보와 예제에 대해서는 <xref:System.Windows.Data.Binding.Path%2A> 및 <xref:System.Windows.Data.Binding.XPath%2A> 속성 페이지를 참조하십시오.  
  
 사용할 값에 대한 <xref:System.Windows.Data.Binding.Path%2A>가 바인딩의 네 가지 필수 구성 요소 중 하나임을 강조했지만, 전체 개체에 바인딩하려는 시나리오에서는 사용할 값이 [바인딩 소스](GTMT) 개체와 같습니다.  이런 경우에는 <xref:System.Windows.Data.Binding.Path%2A>를 지정하지 않는 편이 적절합니다.  다음 예제를 참조하십시오.  
  
 [!code-xml[MasterDetail#EmptyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 위의 예제에서는 빈 바인딩 구문 {Binding}을 사용합니다.  이 경우 <xref:System.Windows.Controls.ListBox>는 부모 DockPanel 요소에서 DataContext를 상속합니다\(이 예제에는 표시되지 않음\).  경로를 지정하지 않으면 기본적으로 전체 개체에 바인딩합니다.  달리 말하면, 이 예제에서는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 전체 개체에 바인딩하고 있으므로 경로를 비워둔 것입니다.  자세한 내용은 [컬렉션에 바인딩](#binding_to_collections) 단원을 참조하십시오.  
  
 이 시나리오는 컬렉션에 대한 바인딩 이외에 개체의 단일 속성만이 아니라 전체 개체에 바인딩할 때도 유용합니다.  소스 개체가 문자열 형식일 때 문자열 자체에만 바인딩하려는 경우를 예로 들 수 있습니다.  다른 일반적인 시나리오는 요소를 몇 개의 속성이 있는 개체에 바인딩하려는 경우입니다.  
  
 바인딩된 대상 속성에서 데이터가 의미를 갖게 하기 위해 사용자 지정 논리를 적용해야 하는 경우가 있습니다.  사용자 지정 논리는 사용자 지정 변환기\(기본 형식 변환이 없는 경우\)의 형태일 수 있습니다.  변환기에 대한 자세한 내용은 [데이터 변환](#data_conversion)을 참조하십시오.  
  
<a name="binding_bindingexpression"></a>   
### Binding 및 BindingExpression  
 데이터 바인딩의 다른 기능 및 사용 방법을 다루기 전에 <xref:System.Windows.Data.BindingExpression> 클래스를 살펴보면 도움이 될 것입니다.  이전 단원에서 보았듯이 <xref:System.Windows.Data.Binding> 클래스는 바인딩 선언의 고급 클래스입니다. 즉, <xref:System.Windows.Data.Binding> 클래스는 바인딩의 특성을 지정할 수 있는 여러 속성을 제공합니다.  관련 클래스인 <xref:System.Windows.Data.BindingExpression>은 소스와 대상 사이의 연결을 유지 관리하는 기본 개체입니다.  바인딩에는 여러 바인딩 식에서 공유될 수 있는 모든 정보가 포함됩니다.  <xref:System.Windows.Data.BindingExpression>은 공유할 수 없으며 <xref:System.Windows.Data.Binding>의 모든 인스턴스 정보를 포함하는 인스턴스 식입니다.  
  
 *myDataObject*가 *MyData* 클래스의 인스턴스이고, *myBinding*이 소스 <xref:System.Windows.Data.Binding> 개체이고, *MyData* 클래스가 *MyDataProperty*라는 문자열 속성을 포함하는 정의된 클래스인 다음 예제를 예로 들 수 있습니다.  이 예제에서는 <xref:System.Windows.Controls.TextBlock>의 인스턴스인 *mytext*의 텍스트 내용을 *MyDataProperty*에 바인딩합니다.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 동일한 *myBinding* 개체를 사용하여 다른 바인딩을 만들 수 있습니다.  예를 들어 *myBinding* 개체를 사용하여 확인란의 텍스트 내용을 *MyDataProperty*에 바인딩할 수 있습니다.  해당 시나리오에서는 *myBinding* 개체를 공유하는 <xref:System.Windows.Data.BindingExpression>의 인스턴스가 두 개 있습니다.  
  
 <xref:System.Windows.Data.BindingExpression> 개체는 데이터 바인딩 개체에 대한 <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> 호출의 반환 값을 통해 얻을 수 있습니다.  다음 항목에서는 <xref:System.Windows.Data.BindingExpression> 클래스의 몇 가지 사용법을 보여 줍니다.  
  
-   [바인딩된 대상 속성에서 바인딩 개체 가져오기](../../../../docs/framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
-   [TextBox 텍스트의 소스를 업데이트하는 시점 제어](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## 데이터 변환  
 앞의 예제에서 단추의 <xref:System.Windows.Controls.Control.Background%2A> 속성은 값이 "Red"인 문자열 속성에 바인딩되기 때문에 단추가 빨간색입니다.  <xref:System.Windows.Media.Brush> 형식에 문자열 값을 <xref:System.Windows.Media.Brush>로 변환하는 형식 변환기가 있기 때문에 이런 식으로 작동합니다.  
  
 이 정보를 [바인딩 만들기](#creating_a_binding) 단원의 그림에 추가하면 다이어그램은 다음과 같아집니다.  
  
 ![데이터 바인딩 다이어그램](../../../../docs/framework/wpf/data/media/databindingbuttondefaultconversion.png "DataBindingButtonDefaultConversion")  
  
 하지만 바인딩 소스 개체에 문자열 형식의 속성이 아니라 <xref:System.Windows.Media.Color> 형식의 *Color* 속성이 있으면 어떻게 될까요?  이러한 경우 바인딩이 동작하려면 먼저 *Color* 속성 값을 <xref:System.Windows.Controls.Control.Background%2A> 속성에 사용할 수 있는 무언가로 변환해야 합니다.  다음 예제에서처럼 <xref:System.Windows.Data.IValueConverter> 인터페이스를 구현하여 사용자 지정 변환기를 만들어야 합니다.  
  
 [!code-csharp[ColorPicker_snip#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 <xref:System.Windows.Data.IValueConverter> 참조 페이지에서 자세한 내용을 볼 수 있습니다.  
  
 이제 사용자 지정 변환기가 기본 변환 대신에 사용되며 다이어그램은 다음과 같아집니다.  
  
 ![데이터 바인딩 다이어그램](../../../../docs/framework/wpf/data/media/databindingconvertercolorexample.png "DataBindingConverterColorExample")  
  
 앞서 설명했듯이 바인딩하는 형식에 있는 형식 변환기 때문에 기본 변환을 사용할 수 있습니다.  이 동작은 대상에서 사용할 수 있는 형식 변환기에 따라 달라집니다.  확실하지 않은 경우 변환기를 직접 만들어 보십시오.  
  
 다음은 데이터 변환기를 구현하는 것이 적합한 몇 가지 일반적인 시나리오입니다.  
  
-   데이터를 문화권에 따라 다르게 표시해야 하는 경우.  예를 들어 특정 문화권에 사용되는 표준이나 값에 따라 통화 변환기 또는 달력 날짜\/시간 변환기를 구현할 수 있습니다.  
  
-   사용되는 데이터를 반드시 속성의 텍스트 값으로 변경할 필요는 없지만 이미지의 소스 또는 표시 텍스트의 색이나 스타일과 같은 다른 값으로 변경해야 하는 경우.  이러한 경우 텍스트 필드를 표 셀의 Background 속성에 바인딩하는 경우처럼 적합하지 않은 것처럼 보일 수 있는 속성의 바인딩을 변환하는 방법으로 변환기를 사용할 수 있습니다.  
  
-   둘 이상의 컨트롤 또는 컨트롤의 여러 속성을 같은 데이터에 바인딩하는 경우.  이러한 경우 기본 바인딩은 텍스트만 표시하고 다른 바인딩은 같은 바인딩을 소스 정보로 사용하면서 특정 표시 문제를 처리할 수 있습니다.  
  
-   대상 속성에 바인딩 컬렉션이 있는 <xref:System.Windows.Data.MultiBinding>에 대해서는 아직 살펴보지 않았습니다.  <xref:System.Windows.Data.MultiBinding>의 경우에는 사용자 지정 <xref:System.Windows.Data.IMultiValueConverter>를 사용하여 바인딩의 값에서 최종 값을 생성합니다.  예를 들어 빨간색, 파란색 및 녹색 값에 따라 색이 계산될 수 있으며, 이 값은 같거나 다른 바인딩 소스 개체의 값일 수 있습니다.  이에 대한 내용 및 예제를 보려면 <xref:System.Windows.Data.MultiBinding> 클래스 페이지를 참조하십시오.  
  
<a name="binding_to_collections"></a>   
## 컬렉션에 바인딩  
   
  
 바인딩 소스 개체는 속성에서 데이터를 포함하는 단일 개체 또는 함께 그룹화되는 경우가 많은\(예: 데이터베이스에 대한 쿼리 결과\) 다형성 개체의 데이터 컬렉션으로 취급될 수 있습니다.  지금까지 단일 개체에 대한 바인딩만 다뤘지만 대개는 데이터 컬렉션으로의 바인딩이 많이 사용됩니다.  예를 들어 일반적인 시나리오에서는 <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView> 또는 <xref:System.Windows.Controls.TreeView> 등의 <xref:System.Windows.Controls.ItemsControl>을 사용하여 [데이터 바인딩의 정의](#what_is_data_binding) 단원에 소개된 응용 프로그램 등에서 데이터 컬렉션을 표시합니다.  
  
 이 경우에도 앞에서 소개한 기본 다이어그램이 여전히 적용됩니다.  <xref:System.Windows.Controls.ItemsControl>을 컬렉션에 바인딩하면 다이어그램은 다음과 같아집니다.  
  
 ![데이터 바인딩 ItemsControl 다이어그램](../../../../docs/framework/wpf/data/media/databindingitemscontrol.png "DataBindingItemsControl")  
  
 이 다이어그램에서 볼 수 있듯이 <xref:System.Windows.Controls.ItemsControl>을 컬렉션 개체에 바인딩하려면 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 사용해야 합니다.  <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성은 <xref:System.Windows.Controls.ItemsControl>의 내용이라고 생각할 수 있습니다.  <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성이 <xref:System.Windows.Data.BindingMode> 바인딩을 기본적으로 지원하기 때문에 바인딩은 <xref:System.Windows.Data.BindingMode>라는 점에 유의하십시오.  
  
<a name="how_to_implement_collections"></a>   
### 컬렉션 구현 방법  
 <xref:System.Collections.IEnumerable> 인터페이스를 구현하는 모든 컬렉션을 열거할 수 있습니다.  그러나 컬렉션에서 삽입이나 삭제를 수행할 때 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 자동으로 업데이트되도록 동적 바인딩을 설정하려면 컬렉션에서 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 구현해야 합니다.  이 인터페이스는 내부 컬렉션이 변경될 때마다 발생해야 하는 이벤트를 노출합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 노출하는 데이터 컬렉션에 대한 기본 제공 구현인 <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스를 제공합니다.  데이터 값을 소스 개체에서 대상으로 전송하는 것을 완전하게 지원하려면 바인딩 가능한 속성을 지원하는 컬렉션의 각 개체도 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현해야 합니다.  자세한 내용은 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)를 참조하십시오.  
  
 컬렉션을 직접 구현하는 대신 <xref:System.Collections.ObjectModel.ObservableCollection%601>을 사용하거나 <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601> 및 <xref:System.ComponentModel.BindingList%601>를 비롯한 기존 컬렉션 클래스 중 하나를 사용하는 것이 좋습니다.  고급 시나리오에서 컬렉션을 직접 구현해야 하는 경우 인덱스에 따라 개별적으로 액세스할 수 있는 개체의 제네릭이 아닌 컬렉션을 제공하고 성능이 가장 높은 <xref:System.Collections.IList>를 사용하는 것이 좋습니다.  
  
<a name="collection_views"></a>   
### 컬렉션 뷰  
 <xref:System.Windows.Controls.ItemsControl>을 데이터 컬렉션에 바인딩한 뒤에는 데이터를 정렬하거나, 필터링하거나, 그룹화할 수 있습니다.  이렇게 하려면 <xref:System.ComponentModel.ICollectionView> 인터페이스를 구현하는 클래스인 컬렉션 뷰를 사용합니다.  
  
   
  
<a name="what_are_collection_views"></a>   
#### 컬렉션 뷰의 정의  
 컬렉션 뷰는 기본 소스 컬렉션 자체를 변경할 필요 없이 정렬, 필터 및 그룹화 쿼리를 기반으로 소스 컬렉션을 탐색하고 표시하는 데 사용할 수 있는 바인딩 소스 컬렉션의 최상위 계층입니다.  또한 컬렉션 뷰는 컬렉션의 현재 항목에 대한 포인터를 유지 관리합니다.  <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스가 소스 컬렉션에서 구현될 경우 <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> 이벤트에서 발생되는 변경 내용은 뷰로 전파됩니다.  
  
 뷰는 기본 소스 컬렉션을 변경하지 않으므로 각 소스 컬렉션에 여러 개의 뷰를 연결하여 사용할 수 있습니다.  예를 들어 *Task* 개체의 컬렉션을 사용할 수 있습니다.  또한 뷰를 사용하면 동일한 데이터를 여러 가지 다른 방식으로 표시할 수 있습니다.  예를 들어, 페이지 왼쪽에 우선 순위별로 정렬된 작업을 표시하고 오른쪽에 영역별로 그룹화된 작업을 표시할 수 있습니다.  
  
<a name="how_to_create_a_view"></a>   
#### 뷰를 만드는 방법  
 뷰를 만들고 사용하는 한 가지 방법은 뷰 개체를 직접 인스턴스화한 다음 이를 바인딩 소스로 사용하는 방법입니다.  예를 들어 [데이터 바인딩의 정의](#what_is_data_binding) 단원에 표시된 [Data Binding 데모](http://go.microsoft.com/fwlink/?LinkID=163703) 응용 프로그램을 고려해  응용 프로그램은 <xref:System.Windows.Controls.ListBox>가 직접 데이터 컬렉션에 바인딩하는 대신 해당 데이터 컬렉션에 대한 뷰에 바인딩하는 방식으로 구현됩니다.  다음 예제는 [Data Binding 데모](http://go.microsoft.com/fwlink/?LinkID=163703) 응용 프로그램에서 추출됩니다.  <xref:System.Windows.Data.CollectionViewSource> 클래스는 <xref:System.Windows.Data.CollectionView>에서 상속되는 클래스의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 프록시입니다.  이 예제에서는 뷰의 <xref:System.Windows.Data.CollectionViewSource.Source%2A>가 현재 응용 프로그램 개체의 *AuctionItems* 컬렉션\(<xref:System.Collections.ObjectModel.ObservableCollection%601> 형식\)에 바인딩됩니다.  
  
 [!code-xml[DataBindingLab#WindowResources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xml[DataBindingLab#CollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xml[DataBindingLab#WindowResources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 그런 다음 리소스 *listingDataView*가 <xref:System.Windows.Controls.ListBox>와 같은 응용 프로그램 요소에 대한 바인딩 소스의 역할을 합니다.  
  
 [!code-xml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 같은 컬렉션에 대한 다른 뷰를 만들려면 다른 <xref:System.Windows.Data.CollectionViewSource> 인스턴스를 만들고 다른 `x:Key` 이름을 지정할 수 있습니다.  
  
 다음 표에서는 기본 컬렉션 뷰로 만들어지거나 소스 컬렉션 형식을 기반으로 <xref:System.Windows.Data.CollectionViewSource>에서 만드는 뷰 데이터 형식을 보여 줍니다.  
  
|소스 컬렉션 형식|컬렉션 뷰 형식|참고|  
|---------------|--------------|--------|  
|<xref:System.Collections.IEnumerable>|<xref:System.Windows.Data.CollectionView>에 기반을 둔 내부 형식|항목을 그룹화할 수 없습니다.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|가장 빠릅니다.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### 기본 뷰 사용  
 컬렉션 뷰를 바인딩 소스로 지정하는 것은 컬렉션 뷰를 만들고 사용하는 다양한 방법 중 하나에 불과합니다.  WPF에서는 바인딩 소스로 사용되는 모든 컬렉션에 대해 기본 컬렉션 뷰를 만듭니다.  WPF에서 컬렉션에 직접 바인딩하면 컬렉션의 기본 뷰에 바인딩됩니다.  이 기본 뷰는 동일 컬렉션에 대한 모든 바인딩에서 공유하므로 바인딩된 컨트롤이나 코드 중 하나에 의해 기본 뷰가 변경되면 동일 컬렉션에 대한 모든 바인딩에 해당 변경 내용이 반영됩니다. 정렬이나 현재 항목 포인터의 변경을 예로 들 수 있으며 이에 대해서는 뒤에서 자세히 설명합니다.  
  
 기본 뷰를 가져오려면 <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> 메서드를 사용합니다.  예제를 보려면 [데이터 수집의 기본 뷰 가져오기](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)를 참조하십시오.  
  
##### ADO.NET DataTable이 포함된 컬렉션 뷰  
 성능 향상을 위해 ADO.NET <xref:System.Data.DataTable> 또는 <xref:System.Data.DataView> 개체에 대한 컬렉션 뷰는 정렬 및 필터링을 <xref:System.Data.DataView>에 위임합니다.  이렇게 하면 정렬 및 필터링이 데이터 소스의 모든 컬렉션 뷰에서 공유됩니다.  각 컬렉션 뷰를 독립적으로 정렬 및 필터링하려면 각 컬렉션 뷰의 <xref:System.Data.DataView> 개체를 사용하여 컬렉션 뷰를 초기화합니다.  
  
<a name="sorting"></a>   
#### 정렬  
 앞서 설명했듯이 뷰는 컬렉션에 정렬 순서를 적용할 수 있습니다.  기본 컬렉션에 존재하기 때문에 데이터에 적절한 기본 순서가 있거나 없을 수 있습니다.  컬렉션에 대한 뷰를 사용하면 지정한 비교 기준에 따라 기본 순서를 변경하거나 순서를 적용할 수 있습니다.  데이터의 클라이언트 기반 뷰이기 때문에 사용자는 열에 해당하는 값에 따라 표 형식 데이터의 열을 정렬할 수 있습니다.  뷰를 사용하면 기본 컬렉션을 변경하거나 컬렉션 내용을 다시 쿼리하지 않고 이렇게 사용자가 중심의 정렬을 적용할 수 있습니다.  예제를 보려면 [머리글을 클릭할 때 GridView 열 정렬](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)을 참조하십시오.  
  
 다음 예제에서는 [데이터 바인딩의 정의](#what_is_data_binding) 단원에서 소개한 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 있는 "Sort by category and date" <xref:System.Windows.Controls.CheckBox>의 정렬 논리를 보여 줍니다.  
  
 [!code-csharp[DataBindingLab#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
<a name="filtering"></a>   
#### 필터링  
 뷰는 컬렉션에 필터를 적용할 수도 있습니다.  즉, 컬렉션에 한 항목이 있어도 이 특정 뷰는 전체 컬렉션의 특정 하위 집합만 표시할 수 있습니다.  데이터에서 조건을 기준으로 필터링할 수 있습니다.  예를 들어 [데이터 바인딩의 정의](#what_is_data_binding) 단원의 응용 프로그램에서 "Show only bargains" <xref:System.Windows.Controls.CheckBox>에는 가격이 $25 이상인 항목을 필터링하는 논리가 들어 있습니다.  해당 <xref:System.Windows.Controls.CheckBox>를 선택하면 다음 코드가 실행되어 *ShowOnlyBargainsFilter*를 <xref:System.Windows.Data.CollectionViewSource.Filter> 이벤트 처리기로 설정합니다.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 *ShowOnlyBargainsFilter* 이벤트 처리기에는 다음과 같은 구현이 있습니다.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 <xref:System.Windows.Data.CollectionViewSource> 대신 <xref:System.Windows.Data.CollectionView> 클래스 중 하나를 직접 사용하는 경우에는 <xref:System.Windows.Data.CollectionView.Filter%2A> 속성을 사용하여 콜백을 지정합니다.  예제를 보려면 [뷰에서 데이터 필터링](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)을 참조하십시오.  
  
<a name="grouping"></a>   
#### 그룹화  
 <xref:System.Collections.IEnumerable> 컬렉션을 표시하는 내부 클래스를 제외한 모든 컬렉션 뷰는 그룹화 기능을 지원하며, 이를 통해 사용자는 컬렉션 뷰의 컬렉션을 논리 그룹으로 나눌 수 있습니다.  사용자가 그룹 목록을 제공할 경우 그룹은 명시적이며, 그룹이 데이터에 따라 동적으로 생성될 경우 그룹은 암시적입니다.  
  
 다음 예제에서는 "Group by category" <xref:System.Windows.Controls.CheckBox>의 논리를 보여 줍니다.  
  
 [!code-csharp[DataBindingLab#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 다른 그룹화 예제를 보려면 [GridView를 구현하는 ListView의 항목 그룹화](../../../../docs/framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md)를 참조하십시오.  
  
<a name="current_record_pointers"></a>   
#### 현재 항목 포인터  
 뷰는 현재 항목의 개념도 지원합니다.  컬렉션 뷰에서 개체를 탐색할 수 있습니다.  탐색할 때 항목 포인터를 이동하여 컬렉션의 특정 위치에 있는 개체를 검색할 수 있습니다.  예제를 보려면 [데이터 수집 뷰의 개체 탐색](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md)을 참조하십시오.  
  
 WPF에서는 뷰\(지정한 뷰 또는 컬렉션의 기본 뷰\)를 사용해서만 컬렉션에 바인딩하므로 컬렉션에 대한 모든 바인딩에는 현재 항목 포인터가 있습니다.  뷰에 바인딩하는 경우 `Path` 값에서 슬래시\("\/"\) 문자를 사용하여 뷰의 현재 항목을 지정합니다.  다음 예제에서는 데이터 컨텍스트가 컬렉션 뷰입니다.  첫 번째 줄은 컬렉션에 바인딩되고,  두 번째 줄은 컬렉션의 현재 항목에 바인딩되며,  세 번째 줄은 컬렉션에 있는 현재 항목의 `Description` 속성에 바인딩됩니다.  
  
```xaml  
<Button Content="{Binding }" />  
<Button Content="{Binding Path=/}" />  
<Button Content="{Binding Path=/Description}" />   
```  
  
 또한 컬렉션 계층을 트래버스하기 위해 슬래시와 속성 구문을 누적시킬 수 있습니다.  다음 예제에서는 `Offices`라는 컬렉션의 현재 항목에 바인딩합니다. 이 컬렉션은 소스 컬렉션에 있는 현재 항목의 속성입니다.  
  
```xaml  
<Button Content="{Binding /Offices/}" />  
```  
  
 현재 항목 포인터는 컬렉션에 적용되는 정렬이나 필터링으로 인해 변경될 수 있습니다.  정렬이 적용되는 경우에는 선택한 마지막 항목에 현재 항목 포인터가 유지되지만 해당 항목 주위에서 컬렉션 뷰가 재구성됩니다.  선택한 항목이 이전에는 목록의 시작 부분에 있었지만 지금은 중간 부분에 있을 수 있습니다. 필터링이 적용되는 경우에는 필터링 후 선택 영역이 뷰에 남아 있으면 선택한 항목이 유지됩니다.  그렇지 않으면 현재 항목 포인터가 필터링된 컬렉션 뷰의 첫 번째 항목으로 설정됩니다.  
  
<a name="master_detail_scenario"></a>   
#### 마스터\-세부 바인딩 시나리오  
 현재 항목의 개념은 컬렉션 항목의 탐색에 유용할 뿐만 아니라 마스터\-세부 바인딩 시나리오에도 유용합니다.  [데이터 바인딩의 정의](#what_is_data_binding) 단원에서 소개한 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 다시 예로 들어 보겠습니다.  이 응용 프로그램에서는 <xref:System.Windows.Controls.ListBox>에서의 선택한 내용에 따라 <xref:System.Windows.Controls.ContentControl>에 표시되는 내용이 결정됩니다.  이를 다른 방법으로 구현하면, <xref:System.Windows.Controls.ListBox> 항목을 선택했을 때 선택한 항목의 세부 사항을 <xref:System.Windows.Controls.ContentControl>에 표시할 수 있습니다.  
  
 둘 이상의 컨트롤을 같은 뷰에 바인딩하면 마스터\-세부 시나리오를 간단하게 구현할 수 있습니다.  [Data Binding 데모](http://go.microsoft.com/fwlink/?LinkID=163703)의 다음 예제에서는 [데이터 바인딩의 정의](#what_is_data_binding) 단원의 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 표시되는 <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ContentControl>의 태그를 보여 줍니다.  
  
 [!code-xml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xml[DataBindingLab#Detail](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 두 컨트롤 모두 같은 소스인 *listingDataView* 정적 리소스\([뷰를 만드는 방법](#how_to_create_a_view) 단원에서 이 리소스의 정의 참조\)에 바인딩됩니다.  singleton 개체\(이 경우 <xref:System.Windows.Controls.ContentControl>\)가 컬렉션 뷰에 바인딩되면 자동으로 뷰의 <xref:System.Windows.Data.CollectionView.CurrentItem%2A>에 바인딩되기 때문에 이런 방식으로 동작합니다.  <xref:System.Windows.Data.CollectionViewSource> 개체는 자동으로 통화와 선택 항목을 동기화합니다.  목록 컨트롤이 이 예제에서처럼 <xref:System.Windows.Data.CollectionViewSource> 개체에 바인딩되지 않는 경우에는 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true`로 설정해야 이렇게 동작합니다.  
  
 다른 예제를 보려면 [선택에 따라 수집 및 표시 정보에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) 및 [계층적 데이터에 마스터\-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)을 참조하십시오.  
  
 위의 예제에서는 템플릿을 사용하는 것을 알 수 있습니다.  사실 템플릿\(<xref:System.Windows.Controls.ContentControl>에서 명시적으로 사용된 템플릿과 <xref:System.Windows.Controls.ListBox>에서 암시적으로 사용하는 템플릿\)을 사용하지 않으면 데이터가 원하는 대로 표시되지 않습니다.  이제 다음 단원에서 데이터 템플릿을 살펴보겠습니다.  
  
<a name="data_templating"></a>   
## 데이터 템플릿  
 데이터 템플릿을 사용하지 않으면 [데이터 바인딩의 정의](#what_is_data_binding) 단원의 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 다음과 같이 표시됩니다.  
  
 ![데이터 템플릿을 사용하지 않는 데이터 바인딩 데모](../../../../docs/framework/wpf/data/media/databindingdemotemplates.png "DataBindingDemoTemplates")  
  
 이전 단원의 예제에서 볼 수 있듯이 <xref:System.Windows.Controls.ListBox> 컨트롤과 <xref:System.Windows.Controls.ContentControl>은 모두 *AuctionItem*의 전체 컬렉션 개체\(더 구체적으로는 컬렉션 개체에 대한 뷰\)에 바인딩됩니다.  데이터 컬렉션을 표시하는 방법에 대한 특정한 지침이 없으면 <xref:System.Windows.Controls.ListBox>에는 기본 컬렉션에 있는 각 개체의 문자열 표현이 표시되고 <xref:System.Windows.Controls.ContentControl>에는 바인딩된 개체의 문자열 표현이 표시됩니다.  
  
 이 문제를 해결하기 위해 응용 프로그램에서는 <xref:System.Windows.DataTemplate>을 정의합니다.  이전 단원의 예제에서처럼 <xref:System.Windows.Controls.ContentControl>에서는 *detailsProductListingTemplate* <xref:System.Windows.DataTemplate>을 명시적으로 사용합니다.  <xref:System.Windows.Controls.ListBox> 컨트롤은 컬렉션에서 *AuctionItem* 개체를 표시할 때 다음 <xref:System.Windows.DataTemplate>을 암시적으로 사용합니다.  
  
 [!code-xml[DataBindingLab#AuctionItemDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 이 두 개의 <xref:System.Windows.DataTemplate>을 사용하면 UI가 [데이터 바인딩의 정의](#what_is_data_binding) 단원에서 볼 수 있는 것과 같이 표시됩니다.  이 스크린 샷에서 볼 수 있듯이, <xref:System.Windows.DataTemplate>을 사용하면 데이터를 컨트롤에 넣을 수 있을 뿐만 아니라 데이터를 시각적으로 뛰어나게 표현할 수도 있습니다.  예를 들어 위의 <xref:System.Windows.DataTemplate>에서는 <xref:System.Windows.DataTrigger>가 사용되어 *SpecialFeatures* 값이 *HighLight*인 *AuctionItem*에 오렌지색 테두리와 별이 표시됩니다.  
  
 데이터 템플릿에 대한 자세한 내용은 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)를 참조하십시오.  
  
<a name="data_validation"></a>   
## 데이터 유효성 검사  
   
  
 사용자 입력을 받는 대부분의 응용 프로그램에는 사용자가 올바른 정보를 입력했는지 확인하기 위한 유효성 검사 논리가 필요합니다.  유효성 검사는 형식, 범위, 서식 또는 기타 응용 프로그램별 요구 사항을 기반으로 할 수 있습니다.  이 단원에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 데이터 유효성 검사가 작동하는 방식을 살펴봅니다.  
  
<a name="validation_rules"></a>   
### 유효성 검사 규칙을 바인딩과 연결  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 모델을 사용하면 <xref:System.Windows.Data.Binding.ValidationRules%2A>를 <xref:System.Windows.Data.Binding> 개체와 연결할 수 있습니다.  예를 들어 다음 예제에서는 <xref:System.Windows.Controls.TextBox>를 `StartPrice`라는 속성에 바인딩하고 <xref:System.Windows.Controls.ExceptionValidationRule> 개체를 <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=fullName> 속성에 추가합니다.  
  
 [!code-xml[DataBindingLab#DefaultValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 <xref:System.Windows.Controls.ValidationRule> 개체는 속성 값이 유효한지 여부를 확인합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 다음과 같은 두 가지 형식의 기본 제공 <xref:System.Windows.Controls.ValidationRule> 개체가 있습니다.  
  
-   <xref:System.Windows.Controls.ExceptionValidationRule>은 바인딩 소스 속성의 업데이트 도중 throw된 예외를 검사합니다.  이전 예제에서 `StartPrice`는 정수 형식입니다.  사용자가 정수로 변환할 수 없는 값을 입력하면 예외가 throw되어 바인딩이 유효하지 않은 것으로 표시됩니다.  <xref:System.Windows.Controls.ExceptionValidationRule>을 명시적으로 설정하는 대체 구문은 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체의 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성을 `true`로 설정합니다.  
  
-   <xref:System.Windows.Controls.DataErrorValidationRule> 개체는 <xref:System.ComponentModel.IDataErrorInfo> 인터페이스를 구현하는 개체에 의해 발생하는 오류를 검사합니다.  이 유효성 검사 규칙 사용에 대한 예제는 <xref:System.Windows.Controls.DataErrorValidationRule>을 참조하십시오.  <xref:System.Windows.Controls.DataErrorValidationRule>을 명시적으로 설정하는 대체 구문은 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체의 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 속성을 `true`로 설정합니다.  
  
 <xref:System.Windows.Controls.ValidationRule> 클래스에서 파생하고 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 구현하여 유효성 검사 규칙을 직접 만들 수도 있습니다.  다음 예제에서는 [데이터 바인딩의 정의](#what_is_data_binding) 단원의 *Add Product Listing* "Start Date" <xref:System.Windows.Controls.TextBox>에 사용되는 규칙을 보여 줍니다.  
  
 [!code-csharp[DataBindingLab#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 다음 예제에서처럼 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox>에서는 이 *FutureDateRule*을 사용합니다.  
  
 [!code-xml[DataBindingLab#CustomValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값이 <xref:System.Windows.Data.UpdateSourceTrigger>이기 때문에 바인딩 엔진은 키 입력이 있을 때마다 소스 값을 업데이트합니다. 즉, 키 입력이 있을 때마다 <xref:System.Windows.Data.Binding.ValidationRules%2A> 컬렉션의 모든 규칙을 검사합니다.  이에 대해서는 유효성 검사 프로세스 단원에서 자세히 다룹니다.  
  
<a name="invalidation_feedback"></a>   
### 시각적 피드백 제공  
 사용자가 잘못된 값을 입력하는 경우 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에서 오류에 대한 몇 가지 피드백을 제공할 수 있습니다.  이러한 피드백을 제공하는 한 가지 방법은 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=fullName> 연결된 속성을 사용자 지정 <xref:System.Windows.Controls.ControlTemplate>으로 설정하는 것입니다.  앞의 소단원에서 볼 수 있듯이 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox>에서는 *validationTemplate*이라는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>을 사용합니다.  다음 예제에서는 *validationTemplate*의 정의를 보여 줍니다.  
  
 [!code-xml[DataBindingLab#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 <xref:System.Windows.Controls.AdornedElementPlaceholder> 요소는 표시되는 컨트롤의 위치를 지정합니다.  
  
 <xref:System.Windows.Controls.ToolTip>을 사용하여 오류 메시지를 표시할 수도 있습니다.  *StartDateEntryForm* 및 *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> 모두 오류 메시지를 표시하는 <xref:System.Windows.Controls.ToolTip>을 만드는 스타일 *textStyleTextBox*를 사용합니다.  다음 예제에서는 *textStyleTextBox*의 정의를 보여 줍니다.  바인딩된 요소의 속성에서 하나 이상의 바인딩에 오류가 있을 때 [연결된 속성](GTMT) <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.  
  
 [!code-xml[DataBindingLab#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 사용자 지정 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 <xref:System.Windows.Controls.ToolTip>을 사용하면 유효성 검사 오류가 발생했을 때 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox>이 다음과 같이 표시됩니다.  
  
 ![데이터 바인딩 유효성 검사 오류](../../../../docs/framework/wpf/data/media/databindingdemo-validation.png "DataBindingDemo\_Validation")  
  
 <xref:System.Windows.Data.Binding>에 유효성 검사 규칙이 연결되어 있지만 바인딩된 컨트롤에 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>을 지정하지 않으면 유효성 검사 오류가 있을 때 기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>이 사용되어 사용자에게 알립니다.  기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>은 표시기\(Adorner\) 계층에 빨간색 테두리를 정의하는 컨트롤 템플릿입니다.  기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 <xref:System.Windows.Controls.ToolTip>을 사용하면 유효성 검사 오류가 있을 때 *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox>의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]는 다음과 같이 표시됩니다.  
  
 ![데이터 바인딩 유효성 검사 오류](../../../../docs/framework/wpf/data/media/databindingdemo-validationdefault.png "DataBindingDemo\_ValidationDefault")  
  
 대화 상자에 있는 모든 컨트롤의 유효성을 검사하기 위한 논리를 제공하는 방법에 대한 예제를 보려면 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)의 사용자 지정 대화 상자 단원을 참조하십시오.  
  
<a name="validation_process"></a>   
### 유효성 검사 프로세스  
 유효성 검사는 대개 대상의 값이 바인딩 소스 속성으로 전송될 때 수행됩니다.  이는 <xref:System.Windows.Data.BindingMode> 및 <xref:System.Windows.Data.BindingMode> 바인딩에서 발생합니다.  [소스 업데이트를 트리거하는 항목](#what_triggers_source_updates) 단원에서 설명한 것처럼 소스 업데이트가 수행되도록 하는 요소는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성의 값에 따라 달라집니다.  
  
 다음은 *유효성 검사* 프로세스에 대한 설명입니다.  이 과정에서 언제라도 유효성 검사 오류나 다른 유형의 오류가 발생하면 프로세스가 중단됩니다.  
  
1.  바인딩 엔진에서는 해당 <xref:System.Windows.Data.Binding>에 대해 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep>로 설정된 사용자 지정 <xref:System.Windows.Controls.ValidationRule> 개체가 정의되어 있는지 확인하고, 있는 경우 해당 개체 중 하나에서 오류가 발생하거나 모든 개체가 통과할 때까지 각 <xref:System.Windows.Controls.ValidationRule>의 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 호출합니다.  
  
2.  그런 다음 바인딩 엔진에서 변환기를 호출합니다\(있는 경우\).  
  
3.  변환기가 성공하면 바인딩 엔진에서는 해당 <xref:System.Windows.Data.Binding>에 대해 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep>로 설정된 사용자 지정 <xref:System.Windows.Controls.ValidationRule> 개체가 정의되어 있는지 확인하고, 있는 경우 해당 개체 중 하나에서 오류가 발생하거나 모든 개체가 통과할 때까지 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep>로 설정된 각 <xref:System.Windows.Controls.ValidationRule>에 대해 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 호출합니다.  
  
4.  바인딩 엔진에서 소스 속성을 설정합니다.  
  
5.  바인딩 엔진에서는 해당 <xref:System.Windows.Data.Binding>에 대해 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep>로 설정된 사용자 지정 <xref:System.Windows.Controls.ValidationRule> 개체가 정의되어 있는지 확인하고, 있는 경우 해당 개체 중 하나에서 오류가 발생하거나 모든 개체가 통과할 때까지 각 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep>로 설정된 각 <xref:System.Windows.Controls.ValidationRule>에 대해 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 호출합니다.  <xref:System.Windows.Controls.DataErrorValidationRule>이 바인딩과 연결되어 있고 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 기본값 <xref:System.Windows.Controls.ValidationStep>로 설정되어 있는 경우 <xref:System.Windows.Controls.DataErrorValidationRule>이 이 시점에서 확인됩니다.  이때 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>가 `true`로 설정된 바인딩도 확인됩니다.  
  
6.  바인딩 엔진에서는 해당 <xref:System.Windows.Data.Binding>에 대해 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep>로 설정된 사용자 지정 <xref:System.Windows.Controls.ValidationRule> 개체가 정의되어 있는지 확인하고, 있는 경우 해당 개체 중 하나에서 오류가 발생하거나 모든 개체가 통과할 때까지 각 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep>로 설정된 각 <xref:System.Windows.Controls.ValidationRule>에 대해 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 호출합니다.  
  
 <xref:System.Windows.Controls.ValidationRule>이 이 프로세스를 통과하지 못하면 바인딩 엔진에서는 <xref:System.Windows.Controls.ValidationError> 개체를 만들어 바인딩된 요소의 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> 컬렉션에 추가합니다.  바인딩 엔진은 지정된 단계에서 <xref:System.Windows.Controls.ValidationRule> 개체를 실행하기 전에 해당 단계 동안 바인딩된 요소의  <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> [연결된 속성](GTMT)에 추가된 모든 <xref:System.Windows.Controls.ValidationError>를 제거합니다.  예를 들어, <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep>로 설정된 <xref:System.Windows.Controls.ValidationRule>이 실패하는 경우 다음 번 유효성 검사 프로세스가 발생할 때 바인딩 엔진에서는 해당 <xref:System.Windows.Controls.ValidationError>를 즉시 제거한 후 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A>이 <xref:System.Windows.Controls.ValidationStep>로 설정된 <xref:System.Windows.Controls.ValidationRule>을 호출합니다.  
  
 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName>가 비어 있지 않으면 요소의 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName> [연결된 속성](GTMT)은 `true`로 설정됩니다.  또한 <xref:System.Windows.Data.Binding>의 <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> 속성이 `true`로 설정되어 있는 경우 바인딩 엔진은 요소에 대해 <xref:System.Windows.Controls.Validation.Error?displayProperty=fullName> [연결된 이벤트](GTMT)를 발생시킵니다.  
  
 대상에서 소스로 또는 소스에서 대상으로 유효한 값을 전송하면 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> [연결된 속성](GTMT)이 지워집니다.  
  
 바인딩에 <xref:System.Windows.Controls.ExceptionValidationRule>이 연결되어 있거나 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성이 `true`로 설정되어 있고 바인딩 엔진에서 소스를 설정할 때 예외가 throw되는 경우 바인딩 엔진은 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>가 있는지 확인합니다.  <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> 콜백을 사용하여 예외 처리를 위한 사용자 지정 처리기를 제공할 수 있습니다.  <xref:System.Windows.Data.Binding>에 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>가 지정되지 않은 경우 바인딩 엔진은 예외가 있는 <xref:System.Windows.Controls.ValidationError>를 만들어 바인딩된 요소의 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=fullName> 컬렉션에 추가합니다.  
  
<a name="debugging_mechanism"></a>   
## 디버깅 메커니즘  
 연결된 속성 <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=fullName>을 바인딩 관련 개체에 설정하여 특정 바인딩의 상태 정보를 받을 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Controls.DataErrorValidationRule>   
 [WPF 버전 4.5의 새로운 기능](../../../../docs/framework/wpf/getting-started/whats-new.md)   
 [LINQ 쿼리 결과에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Data Binding 데모](http://go.microsoft.com/fwlink/?LinkID=163703)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [ADO.NET 데이터 소스 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)