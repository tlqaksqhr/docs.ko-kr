---
title: "데이터 바인딩 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data conversion for binding [WPF]
- binding data [WPF], about data binding
- data binding [WPF], about data binding
- conversion for data binding [WPF]
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
caps.latest.revision: "78"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fbf731504022cb25e0cdeff5e0a557b67b987fd4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="data-binding-overview"></a>데이터 바인딩 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩은 응용 프로그램이 데이터를 제공하고 상호 작용할 수 있는 간단하고 일관된 방법을 제공합니다. 다양한 데이터 소스에서 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체 및 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]의 형태로 데이터에 요소를 바인딩할 수 있습니다. <xref:System.Windows.Controls.ContentControl>와 같은 s <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.ItemsControl>같은 <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ListView> 단일 데이터 항목의 스타일을 유연한 또는 데이터 항목의 컬렉션을 사용 하도록 기능이 기본 제공 합니다. 데이터를 기반으로 정렬, 필터 및 그룹 보기를 생성할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 데이터 바인딩 기능은 기본적으로 데이터 바인딩을 지원하는 광범위한 속성, 데이터의 유연한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 표현 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 비즈니스 논리의 분명한 분리와 같은 기존 모델에 비해 여러 가지 이점이 있습니다.  
  
 이 항목에서는 먼저 대 한 핵심 개념을 설명 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 및의 사용에는 다음이 되는 <xref:System.Windows.Data.Binding> 클래스 및 기타 기능 데이터 바인딩.  
  
  
<a name="what_is_data_binding"></a>   
## <a name="what-is-data-binding"></a>데이터 바인딩이란?  
 데이터 바인딩은 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와 비즈니스 논리를 연결하는 프로세스입니다. 바인딩 설정이 올바르고 데이터가 적절한 알림을 제공하는 경우에는 데이터의 값이 변경될 때 데이터에 바인딩된 요소에 변경 내용이 자동으로 반영됩니다. 또한 요소에서 데이터의 외부 표현이 변경되면 내부 데이터가 자동으로 업데이트되어 변경 내용이 반영될 수 있습니다. 예를 들어, 값을 편집 하는 사용자는 <xref:System.Windows.Controls.TextBox> 기본 데이터 값을 사용 하는 요소는 해당 변경 내용을 반영 하도록 자동으로 업데이트 됩니다.  
  
 데이터 바인딩은 일반적으로 서버 또는 로컬 구성 데이터를 폼이나 기타 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤에 배치하는 데 사용됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 이 개념은 광범위한 속성을 다양한 데이터 소스에 바인딩하는 기능을 포함하도록 확장됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 요소의 종속성 속성은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체([!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] 개체 또는 웹 서비스와 웹 속성에 연결된 개체 포함) 및 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 바인딩될 수 있습니다.  
  
 데이터 바인딩의 예는 [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703)(데이터 바인딩 데모)에서 다음 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 살펴보세요.  
  
 ![데이터 바인딩 샘플 스크린샷](../../../../docs/framework/wpf/data/media/databinding-databindingdemo.png "DataBinding_DataBindingDemo")  
  
 위 그림은 작업 항목 목록을 표시하는 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]입니다. 응용 프로그램은 데이터 바인딩의 다음 기능을 보여 줍니다.  
  
-   콘텐츠는 <xref:System.Windows.Controls.ListBox> 의 컬렉션에 바인딩된 *AuctionItem* 개체입니다. *AuctionItem* 개체에는 *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* 등의 속성이 있습니다.  
  
-   데이터 (*AuctionItem* 개체)에 표시 되는 <xref:System.Windows.Controls.ListBox> 한 각 항목에 대 한 설명과 현재 가격이 표시 됩니다. 이렇게 사용 하는 <xref:System.Windows.DataTemplate>합니다. 또한 각 항목의 모양은 표시되는 *AuctionItem*의 *SpecialFeatures* 값에 따라 달라집니다. *AuctionItem*의 *SpecialFeatures* 값이 *Color*이면 항목에는 파란색 테두리가 포함됩니다. *Highlight* 값이면 항목에는 주황색 테두리와 별모양이 포함됩니다. [데이터 템플릿](#data_templating) 섹션에서는 데이터 템플릿을 살펴봅니다.  
  
-   사용자 그룹, 필터링 하거나, 사용 하 여 데이터를 정렬할 수는 <xref:System.Windows.Controls.CheckBox>es 제공 합니다. 위, 이미지 "그룹 범주별" 및 "범주와 날짜 기준 정렬" <xref:System.Windows.Controls.CheckBox>es 선택 됩니다. 데이터가 제품 범주에 따라 그룹화되고 범주 이름이 사전순으로 표시되어 있음을 알 수 있습니다. 그림에서 확인하기는 어렵지만 항목은 각 범주 내에서 시작 날짜별로 정렬됩니다. 이 작업에는 *컬렉션 뷰*가 사용됩니다. [컬렉션에 바인딩](#binding_to_collections) 섹션에서는 컬렉션 뷰를 살펴봅니다.  
  
-   사용자가 항목을 선택 된 <xref:System.Windows.Controls.ContentControl> 선택한 항목의 세부 정보가 표시 됩니다. 이를 *마스터-세부 시나리오*라고 합니다. [마스터-세부 시나리오Scenario](#master_detail_scenario) 섹션에서는 바인딩 시나리오 유형을 살펴봅니다.  
  
-   유형의 *StartDate* 속성은 <xref:System.DateTime>을 밀리초 단위로 시간을 포함 하는 날짜를 반환 하는 합니다. 이 응용 프로그램에는 더 짧은 날짜 문자열이 표시되도록 사용자 지정 변환기가 사용되었습니다. [데이터 변환](#data_conversion) 섹션에서는 변환기를 살펴봅니다.  
  
 사용자가 *Add Product* 단추를 클릭하면 다음과 같이 표시됩니다.  
  
 ![제품 목록 추가 페이지](../../../../docs/framework/wpf/data/media/databinding-demo-addproductlisting.png "DataBinding_Demo_AddProductListing")  
  
 사용자는 폼에 있는 필드를 편집하고, 짧은 미리 보기와 더 자세한 미리 보기 창을 사용하여 제품 목록을 미리 보고, *submit*을 클릭하여 새 제품 목록을 추가할 수 있습니다. 기존 그룹화, 필터링 및 정렬 기능이 새 항목에 적용됩니다. 이 경우 위 그림에 입력된 항목은 *Computer* 범주에서 두 번째 항목으로 표시됩니다.  
  
 이 이미지에 표시 되지 않음은에서 제공 하는 유효성 검사 논리는 *시작 날짜* <xref:System.Windows.Controls.TextBox>합니다. 사용자가 잘못 된 입력 날짜 (잘못 된 서식 지정 또는 과거 날짜)와 사용자 알림이 표시 됩니다는 <xref:System.Windows.Controls.ToolTip> 및 옆에 빨간색 느낌표가 <xref:System.Windows.Controls.TextBox>합니다. [데이터 유효성 검사](#data_validation) 섹션에서는 유효성 검사 논리를 만드는 방법을 설명합니다.  
  
 위에서 간략히 설명한 데이터 바인딩의 다른 기능을 살펴보기 전에 먼저 다음 섹션에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 이해에 필수적인 기본 개념을 설명합니다.  
  
## <a name="basic-data-binding-concepts"></a>기본 데이터 바인딩 개념  
  
 바인딩할 요소 및 데이터 소스의 특성에 관계없이 각 바인딩은 항상 다음 그림에 나와 있는 모델을 따릅니다.  
  
 ![기본 데이터 바인딩 다이어그램](../../../../docs/framework/wpf/data/media/databindingmostbasic.png "DataBindingMostBasic")  
  
 위 그림과 같이 데이터 바인딩은 기본적으로 바인딩 대상과 바인딩 소스를 연결합니다. 그림에서는 다음 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 개념을 보여 줍니다.  
  
-   일반적으로 각 바인딩에는 네 가지 구성 요소인 바인딩 대상 개체, 대상 속성, 바인딩 소스 및 사용할 바인딩 소스의 값 경로가 있습니다. 콘텐츠를 바인딩할 경우 등는 <xref:System.Windows.Controls.TextBox> 에 *이름* 속성은 *직원* 대상 개체는 개체는 <xref:System.Windows.Controls.TextBox>, target 속성이 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 사용 하 여 값은 *이름*, 원본 개체와 *직원* 개체입니다.  
  
-   대상 속성은 종속성 속성이어야 합니다. 대부분 <xref:System.Windows.UIElement> 속성은 종속성 속성 및 읽기 전용 것을 제외한 대부분의 종속성 속성을 기본적으로 데이터 바인딩을 지원 합니다. (만 <xref:System.Windows.DependencyObject> 종속성 속성 및 모든 형식을 정의할 수 <xref:System.Windows.UIElement>에서 파생 <xref:System.Windows.DependencyObject>.)  
  
-   그림에는 지정되지 않았지만 바인딩 소스 개체는 사용자 지정 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체로 제한되지 않습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 및 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 형식의 데이터를 지원합니다. 바인딩 소스 몇 가지 예를 제공 하는 것을 <xref:System.Windows.UIElement>, 목록 개체는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 연결 된 개체에 [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] 데이터 또는 웹 서비스 또는 들어 있는 XmlNode 프로그램 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터입니다. 자세한 내용은 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)를 참조하세요.  
  
 다른 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] 항목을 읽을 때 바인딩을 설정하고 있다면 바인딩 소스*에* 바인딩 대상을 바인딩하고 있다는 것을 기억하세요. 예를 들어, 일부 내부 표시 하는 경우 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 의 데이터는 <xref:System.Windows.Controls.ListBox> 바인딩하는 데이터 바인딩을 사용 하 여, 프로그램 <xref:System.Windows.Controls.ListBox> 에 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터입니다.  
  
 사용 하면 바인딩을 설정 하는 <xref:System.Windows.Data.Binding> 개체입니다. 이 항목의 나머지 부분에서는 다양 한 관련 된 개념 및 일부 속성 및 사용에 설명 된 <xref:System.Windows.Data.Binding> 개체입니다.  
  
<a name="direction_of_data_flow"></a>   
### <a name="direction-of-the-data-flow"></a>데이터 흐름 방향  
 바인딩 소스에 바인딩 대상에서 바인딩 데이터 흐름 이동할 수 설명한 것 처럼 및 위 그림에 화살표로 표시 됨 (사용자의 값을 편집 하는 경우이 소스 값이 변경 되는 예를 들어 한 <xref:System.Windows.Controls.TextBox>) 및/또는 바인딩 소스에서 바인딩 대상 (예를 들어 프로그램 <xref:System.Windows.Controls.TextBox> 콘텐츠 바인딩 소스에서 변경 내용으로 업데이트) 하 여 바인딩 소스에 적절 한 알림을 제공 하는 경우.  
  
 응용 프로그램에서 사용자가 데이터를 변경하고 다시 소스 개체에 전파할 수 있도록 해야 할 수 있습니다. 또는 사용자가 소스 데이터를 업데이트할 수 없도록 해야 할 수 있습니다. 설정 하 여이 제어할 수 있습니다는 <xref:System.Windows.Data.Binding.Mode%2A> 속성의 프로그램 <xref:System.Windows.Data.Binding> 개체입니다. 다음 그림은 다양한 유형의 데이터 흐름을 보여 줍니다.  
  
 ![데이터 바인딩 데이터 흐름](../../../../docs/framework/wpf/data/media/databinding-dataflow.png "DataBinding_DataFlow")  
  
-   <xref:System.Windows.Data.BindingMode.OneWay>바인딩에서는 변경 내용이 자동으로 대상 속성을 업데이트 하려면 소스 속성에 있지만 대상 속성에 대 한 변경 내용을 원본 속성에 다시 전파 되지 않습니다. 이 바인딩 유형은 바인드되는 컨트롤이 암시적으로 읽기 전용인 경우에 적합합니다. 예를 들어 주식 시세표시기와 같은 원본에 바인드할 수 있거나 대상 속성에는 테이블의 데이터 바인딩된 배경색과 같이 변경을 위해 제공된 컨트롤 인터페이스가 없을 수 있습니다. 대상 속성의 변경 내용을 모니터링할 필요가 없는 경우 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩 모드를 사용하면 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 모드의 오버헤드가 방지됩니다.  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay>바인딩에서는 원본 속성 또는 자동으로 다른 업데이트에 대 한 대상 속성을 변경 합니다. 이 바인딩 유형은 편집 가능한 폼이나 기타 완전한 대화형 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오에 적합합니다. 대부분의 속성을 기본값 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩, 하지만 일부 종속성 속성 (일반적으로 같은 사용자가 편집 가능한 컨트롤의 속성을는 <xref:System.Windows.Controls.TextBox.Text%2A> 의 속성 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> 의 속성 <xref:System.Windows.Controls.CheckBox>) 기본값으로<xref:System.Windows.Data.BindingMode.TwoWay> 바인딩. 종속성 속성이 기본적으로 단방향 또는 양방향으로 바인드되는지를 프로그래밍 방식으로 결정하려면 <xref:System.Windows.DependencyProperty.GetMetadata%2A>를 사용하여 속성의 속성 메타데이터를 가져온 후 <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A> 속성의 부울 값을 확인합니다.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource>반대 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩; 원본 속성이 업데이트 대상 속성이 변경 될 때입니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에서 소스 값을 다시 평가하면 되는 경우가 한 가지 예제 시나리오입니다.  
  
-   그림에서 설명 하지는 <xref:System.Windows.Data.BindingMode.OneTime> 바인딩 대상 속성을 초기화 한 source 속성 때문에 있지만 후속 변경 내용이 전파 되지 않습니다. 이는 데이터 컨텍스트가 변경되고 있거나 데이터 컨텍스트의 개체가 변경될 경우 변경 내용이 대상 속성에 반영되지 않습니다. 이 바인딩 유형은 현재 상태의 스냅숏이 사용하기에 적절하거나 데이터가 실제로 정적인 상황에서 데이터를 사용하는 경우에 적합합니다. 또한 이 바인딩 유형은 원본 속성의 일부 값으로 대상 속성을 초기화하려고 하며 데이터 컨텍스트가 사전에 알려지지 않은 경우에도 유용합니다. 이는 기본적으로 원본 값이 변경되지 않은 경우에 더 나은 성능을 제공하는 <xref:System.Windows.Data.BindingMode.OneWay> 바인딩의 더 간단한 형태입니다.  
  
 소스 변경 내용을 검색 하려면 해당 (적용할 <xref:System.Windows.Data.BindingMode.OneWay> 및 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩), 소스와 같은 적절 한 속성 변경 알림 메커니즘을 구현 해야 <xref:System.ComponentModel.INotifyPropertyChanged>합니다. 참조 [속성 변경 알림을 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) 의 예는 <xref:System.ComponentModel.INotifyPropertyChanged> 구현 합니다.  
  
 <xref:System.Windows.Data.Binding.Mode%2A> 속성 페이지에서는 바인딩 모드와 바인딩 방향을 지정 하는 방법의 예에 대 한 자세한 정보를 제공 합니다.  
  
<a name="what_triggers_source_updates"></a>   
### <a name="what-triggers-source-updates"></a>소스 업데이트를 트리거하는 항목  
 바인딩 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 대상 속성에 대 한 변경 내용을 수신 대기 하 고 소스 전파 합니다. 이를 소스 업데이트라고 합니다. 예를 들어 TextBox의 텍스트를 편집하여 기본 소스 값을 변경할 수 있습니다. 데이터 흐름의 방향을 값에 의해 결정 됩니다 마지막 섹션에서 설명한는 <xref:System.Windows.Data.Binding.Mode%2A> 바인딩의 속성입니다.  
  
 하지만 텍스트를 편집하는 동안이나 텍스트 편집을 마치고 마우스를 TextBox 외부로 이동한 후 소스 값이 업데이트될까요? <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 바인딩의 속성 원본의 업데이트를 트리거할 항목을 결정 합니다. 다음 그림에서 오른쪽 화살표의 점의 역할을 보여 줍니다.는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성:  
  
 ![UpdateSourceTrigger 다이어그램](../../../../docs/framework/wpf/data/media/databindingupdatesourcetrigger.png "DataBindingUpdateSourceTrigger")  
  
 경우는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값은 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, 값에 의해 가리킵니다의 오른쪽 화살표 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩 대상 속성이 변경 되는 즉시 업데이트 됩니다. 그러나 경우는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값은 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, 후 해당 값만 가져옵니다 업데이트 새 값으로 대상 속성 포커스를 잃을 때.  
  
 비슷합니다는 <xref:System.Windows.Data.Binding.Mode%2A> 속성을 다른 종속성 속성에는 서로 다른 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값입니다. 대부분의 종속성 속성에 대한 기본값이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>인 반면 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>입니다. 즉, 소스 업데이트 될 때마다 수행 하는 이것으로 충분 하는 대상 속성이 변경 <xref:System.Windows.Controls.CheckBox>es 및 다른 단순 컨트롤입니다. 하지만 텍스트 필드의 경우 키 입력이 있을 때마다 업데이트하면 성능이 저하될 수 있고 새 값으로 커밋하기 전에 사용자가 백스페이스 키를 누르고 입력 오류를 수정할 수 있는 기회가 사라집니다. 바로 이러한 이유로 <xref:System.Windows.Controls.TextBox.Text%2A> 속성의 기본값은 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> 대신 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>합니다.  
  
 참조는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 기본값을 확인 하는 방법에 대 한 정보에 대 한 속성 페이지 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 종속성 속성의 값입니다.  
  
 다음 표에서 각각에 대 한 예제 시나리오에서는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 를 사용 하 여 값의 <xref:System.Windows.Controls.TextBox> 예:  
  
|UpdateSourceTrigger 값|소스 값이 업데이트될 때|TextBox의 예제 시나리오|  
|-------------------------------|----------------------------------------|----------------------------------|  
|LostFocus (에 대 한 기본 <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>)|TextBox 컨트롤이 포커스를 잃을 때|A <xref:System.Windows.Controls.TextBox> 유효성 검사 논리와 연결 된 (데이터 유효성 검사 섹션 참조)|  
|PropertyChanged|에 입력으로<xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.TextBox>대화방 창에서 컨트롤|  
|명시적 방법|응용 프로그램 호출 하는 경우<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|<xref:System.Windows.Controls.TextBox>(제출 단추를 클릭할 때에 소스 값을 업데이트) 편집 가능한 폼의 컨트롤|  
  
 예제를 보려면 [TextBox 텍스트의 소스를 업데이트하는 시점 제어](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)를 참조하세요.  
  
<a name="creating_a_binding"></a>   
## <a name="creating-a-binding"></a>바인딩 만들기  
  
 이전 섹션에 설명 된 개념 중 일부를 만들며, 바인딩 사용 설정에서 <xref:System.Windows.Data.Binding> 개체 및 각 바인딩에 일반적으로 4 구성: 대상, 대상 속성, 바인딩 소스 및 경로 사용 하려면 소스 값에 바인딩. 이 섹션에서는 바인딩을 설정하는 방법을 설명합니다.  
  
 바인딩 소스 개체가 *SDKSample* 네임스페이스에 정의된 *MyData* 클래스인 다음 예제를 살펴볼 수 있습니다. 설명을 위해 *MyData* 클래스에는 값이 "Red"로 설정된 *ColorName* 문자열 속성이 있습니다. 따라서 이 예제에서는 빨간색 배경이 있는 단추를 생성합니다.  
  
 [!code-xaml[BindNonTextProperty#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 바인딩 선언 구문에 대한 자세한 설명과 코드에서 바인딩을 설정하는 방법의 예제는 [바인딩 선언 개요](../../../../docs/framework/wpf/data/binding-declarations-overview.md)를 참조하세요.  
  
 이 예제를 기본 다이어그램에 적용하면 결과 그림은 다음과 같이 표시됩니다. 이 한 <xref:System.Windows.Data.BindingMode.OneWay> Background 속성을 지원 하기 때문에 바인딩 <xref:System.Windows.Data.BindingMode.OneWay> 기본적으로 바인딩.  
  
 ![데이터 바인딩 다이어그램](../../../../docs/framework/wpf/data/media/databindingbuttonbackgroundexample.png "DataBindingButtonBackgroundExample")  
  
 작동 하는 이유가 하더라도 궁금할는 *ColorName* 하는 동안 형식 문자열의 속성은는 <xref:System.Windows.Controls.Control.Background%2A> 속성은 형식이 <xref:System.Windows.Media.Brush>합니다. 기본 형식 변환이 작동하기 때문이고 이 기능은 [데이터 변환](#data_conversion) 섹션에서 설명합니다.  
  
<a name="specifying_the_binding_source"></a>   
### <a name="specifying-the-binding-source"></a>바인딩 소스 지정  
 이전 예제에서 바인딩 소스로 설정 하 여 지정 됩니다는 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성에는 <xref:System.Windows.Controls.DockPanel> 요소입니다. <xref:System.Windows.Controls.Button> 다음 상속는 <xref:System.Windows.FrameworkElement.DataContext%2A> 에서 값의 <xref:System.Windows.Controls.DockPanel>, 부모 요소는 합니다. 다시 말하지만, 바인딩 소스 개체는 바인딩의 네 가지 필수 구성 요소 중 하나입니다. 따라서 바인딩 소스 개체를 지정하지 않으면 바인딩은 아무 작업도 하지 않습니다.  
  
 바인딩 소스 개체를 지정하는 여러 가지 방법이 있습니다. 사용 하 여 <xref:System.Windows.FrameworkElement.DataContext%2A> 부모 요소에 대해 속성은 여러 속성 동일한 소스에 바인딩하는 경우 유용 합니다. 하지만 개별 바인딩 선언에서 바인딩 소스를 지정하는 방법이 더 적절한 경우도 있습니다. 이전 예제를 사용 하는 대신는 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 설정 하 여 바인딩 소스를 지정할 수 있습니다는 <xref:System.Windows.Data.Binding.Source%2A> 다음 예제와 같이 단추의 바인딩 선언에서 직접 속성:  
  
 [!code-xaml[BindNonTextProperty#BackgroundBindingCompact](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 아닌 다른 설정의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성 요소에 직접, 상속 하는 <xref:System.Windows.FrameworkElement.DataContext%2A> (예: 단추 첫 번째 예제에서)를 상위 항목에서 값 및 명시적으로 설정 하 여 바인딩 소스를 지정 하는 <xref:System.Windows.Data.Binding.Source%2A> 는 속성<xref:System.Windows.Data.Binding> (예: 단추 마지막 예제)를 사용할 수도 있습니다는 <xref:System.Windows.Data.Binding.ElementName%2A> 속성 또는 <xref:System.Windows.Data.Binding.RelativeSource%2A> 속성을 바인딩 소스를 지정 합니다. <xref:System.Windows.Data.Binding.ElementName%2A> 속성은 단추의 너비를 조정 하려면 슬라이더를 사용할 경우 같은 응용 프로그램에서 다른 요소에 바인딩하는 경우 유용 합니다. <xref:System.Windows.Data.Binding.RelativeSource%2A> 에 바인딩이 지정 되는 경우 속성이 유용 합니다.는 <xref:System.Windows.Controls.ControlTemplate> 또는 <xref:System.Windows.Style>합니다. 자세한 내용은 [바인딩 소스 지정](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)을 참조하세요.  
  
<a name="specifying_the_path_to_the_value"></a>   
### <a name="specifying-the-path-to-the-value"></a>값 경로 지정  
 사용 하 여 바인딩 소스 개체 이면의 <xref:System.Windows.Data.Binding.Path%2A> 속성을 통해 바인딩에 사용할 값을 지정 합니다. 바인딩하는 경우 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 사용 데이터는 <xref:System.Windows.Data.Binding.XPath%2A> 속성 값을 지정 합니다. 경우에 따라 사용 하도록 적용할 수는 <xref:System.Windows.Data.Binding.Path%2A> 속성 데이터를 가져온 경우에 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]합니다. 예를 들어 XPath 쿼리) (결과로 반환 된 XmlNode의 Name 속성에 액세스 하려는 경우 사용 해야는 <xref:System.Windows.Data.Binding.Path%2A> 속성 외에 <xref:System.Windows.Data.Binding.XPath%2A> 속성입니다.  
  
 구문 정보 및 예제에 대 한 참조는 <xref:System.Windows.Data.Binding.Path%2A> 및 <xref:System.Windows.Data.Binding.XPath%2A> 속성 페이지.  
  
 강조 했지만 하지만 <xref:System.Windows.Data.Binding.Path%2A> 사용할 값에는 전체 개체에 바인딩하려는 경우에는 바인딩의 4 개의 필수 구성 요소 중 하나 이면 사용할 값을는 바인딩 소스 개체와 동일 합니다. 이 경우 지정 하지에 적용 됩니다는 <xref:System.Windows.Data.Binding.Path%2A>합니다. 다음 예제를 참조하세요.  
  
 [!code-xaml[MasterDetail#EmptyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 위의 예제에서는 빈 바인딩 구문인 {Binding}을 사용합니다. 이 경우에 <xref:System.Windows.Controls.ListBox> DataContext (이 예제에 표시 되지 않음) 부모 DockPanel 요소 로부터 상속 받습니다. 경로를 지정하지 않으면 기본적으로 전체 개체에 바인딩됩니다. 즉,이 예제에서는 경로 생략 되었습니다 바인딩하는 것 때문에 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 전체 개체 속성입니다. 자세한 내용은 [컬렉션에 바인딩](#binding_to_collections) 섹션을 참조하세요.  
  
 컬렉션에 바인딩 외에 개체의 단일 속성만이 아닌 전체 개체에 바인딩하려는 경우에도 이 시나리오가 유용합니다. 예를 들면 소스 개체가 문자열 형식이고 문자열 자체에 바인딩하려는 경우입니다. 또 다른 일반적인 시나리오는 여러 속성이 있는 개체에 요소를 바인딩하려는 경우입니다.  
  
 바인딩된 대상 속성에서 데이터가 의미를 가지려면 사용자 지정 논리를 적용해야 할 수 있습니다. 사용자 지정 논리는 사용자 지정 변환기 형식일 수 있습니다(기본 형식 변환이 없는 경우). 변환기에 대한 자세한 내용은 [데이터 변환](#data_conversion)을 참조하세요.  
  
<a name="binding_bindingexpression"></a>   
### <a name="binding-and-bindingexpression"></a>Binding 및 BindingExpression  
 다른 기능 및 데이터 바인딩 사용을 가져오기 전에 소개 하기 위한 유용한 것은 <xref:System.Windows.Data.BindingExpression> 클래스입니다. 이전 섹션에서 설명한 것 처럼는 <xref:System.Windows.Data.Binding> 클래스는 바인딩; 선언에 대 한 높은 수준의 클래스는 <xref:System.Windows.Data.Binding> 클래스 바인딩 특성을 지정할 수 있는 여러 속성을 제공 합니다. 관련된 클래스 <xref:System.Windows.Data.BindingExpression>, 원본과 대상 간의 연결을 유지 하는 기본 개체입니다. 바인딩에는 여러 바인딩 식에서 공유될 수 있는 모든 정보가 포함됩니다. A <xref:System.Windows.Data.BindingExpression> 공유할 수 없는 인스턴스 식의 모든 인스턴스 정보를 포함 하는 <xref:System.Windows.Data.Binding>합니다.  
  
 예를 들어 다음을 있는 *myDataObject* 의 인스턴스가 *MyData* 클래스 *myBinding* 원본인 <xref:System.Windows.Data.Binding> 개체 및 *MyData* 클래스는 문자열 속성을 포함 하는 정의 된 클래스 *MyDataProperty*합니다. 텍스트 내용을 바인딩하는이 예제 *mytext*, 인스턴스의 <xref:System.Windows.Controls.TextBlock>을 *MyDataProperty*합니다.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 같은 *myBinding* 개체를 사용하여 다른 바인딩을 만들 수 있습니다. 예를 들어 *myBinding* 개체를 사용하여 확인란의 텍스트 컨텍스트를 *MyDataProperty*에 바인딩할 수 있습니다. 이 시나리오의 두 인스턴스 됩니다 <xref:System.Windows.Data.BindingExpression> 공유는 *myBinding* 개체입니다.  
  
 A <xref:System.Windows.Data.BindingExpression> 호출의 반환 값을 통해 개체를 가져올 수 <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> 데이터 바인딩된 개체에 있습니다. 다음 항목에서는 설명의 사용 중 일부는 <xref:System.Windows.Data.BindingExpression> 클래스:  
  
-   [바인딩된 대상 속성에서 바인딩 개체 가져오기](../../../../docs/framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
-   [TextBox 텍스트의 소스를 업데이트하는 시점 제어](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## <a name="data-conversion"></a>데이터 변환  
 이전 예에서 단추는 빨간색 때문에 해당 <xref:System.Windows.Controls.Control.Background%2A> 속성 값이 "Red"는 문자열 속성에 바인딩되어 있습니다. 에 형식 변환기가 하므로이 작업이 <xref:System.Windows.Media.Brush> 문자열 값을 변환할 대상 형식은 <xref:System.Windows.Media.Brush>합니다.  
  
 [바인딩 만들기](#creating_a_binding) 섹션의 그림에 이 정보를 추가하려는 경우 다이어그램은 다음과 같이 표시됩니다.  
  
 ![데이터 바인딩 다이어그램](../../../../docs/framework/wpf/data/media/databindingbuttondefaultconversion.png "DataBindingButtonDefaultConversion")  
  
 그러나,이 경우 어떻게 하는 대신 바인딩 소스 개체에 형식 문자열의 속성을 *색* 형식의 속성이 <xref:System.Windows.Media.Color>? 이 경우 작동 하도록 바인딩을 위해 해야 처음 설정 하는 *색* 항목으로 속성 값 하는 <xref:System.Windows.Controls.Control.Background%2A> 속성은 허용 합니다. 사용자 지정 변환기를 구현 하 여 만들 해야는 <xref:System.Windows.Data.IValueConverter> 다음 예제와 같이 인터페이스:  
  
 [!code-csharp[ColorPicker_snip#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 <xref:System.Windows.Data.IValueConverter> 참조 페이지는 자세한 정보를 제공 합니다.  
  
 이제 기본 변환 대신 사용자 지정 변환기가 사용되고 다이어그램이 다음과 같이 표시됩니다.  
  
 ![데이터 바인딩 다이어그램](../../../../docs/framework/wpf/data/media/databindingconvertercolorexample.png "DataBindingConverterColorExample")  
  
 다시 말하지만, 바인딩되는 형식에 있는 형식 변환기 때문에 기본 변환을 사용할 수 있습니다. 이 동작은 대상에서 사용할 수 있는 형식 변환기에 따라 결정됩니다. 확실하지 않으면 사용자 지정 변환기를 만듭니다.  
  
 데이터 변환기를 구현하는 것이 좋은 몇 가지 일반적인 시나리오는 다음과 같습니다.  
  
-   데이터를 문화권에 따라 다르게 표시해야 하는 경우. 예를 들어 특정 문화권에서 사용되는 값 또는 표준에 따라 통화 변환기 또는 달력 날짜/시간 변환기를 구현해야 할 수 있습니다.  
  
-   사용되는 데이터가 반드시 속성의 텍스트 값을 변경하는 데 사용될 필요는 없지만, 이미지의 소스 또는 표시 텍스트의 색이나 스타일과 같은 몇 가지 다른 값을 변경하는 데 사용되는 경우. 텍스트 필드를 표 셀의 Background 속성에 바인딩하는 것과 같이 적절해 보이지 않는 속성의 바인딩을 변환하는 방식으로 이 인스턴스에서 변환기를 사용할 수 있습니다.  
  
-   두 개 이상의 컨트롤 또는 컨트롤의 여러 속성이 같은 데이터에 바인딩됩니다. 이 경우 기본 바인딩은 텍스트만 표시할 수 있는 반면, 기타 바인딩은 특정 표시 문제를 처리하지만 소스 정보와 같은 바인딩을 사용합니다.  
  
-   지금까지 하지 아직 설명한 <xref:System.Windows.Data.MultiBinding>, 대상 속성에 바인딩의 컬렉션이 있습니다. 경우에 <xref:System.Windows.Data.MultiBinding>, 사용자 지정을 사용 하 여 <xref:System.Windows.Data.IMultiValueConverter> 바인딩의 값의 최종 값을 생성 합니다. 예를 들어 빨간색, 파란색 및 녹색 값을 기준으로 색을 계산할 수 있고 이러한 값은 같거나 다른 바인딩 소스 개체의 값일 수 있습니다. 참조는 <xref:System.Windows.Data.MultiBinding> 예제와 정보에 대 한 클래스 페이지입니다.  
  
<a name="binding_to_collections"></a>   
## <a name="binding-to-collections"></a>컬렉션에 바인딩  
  
 바인딩 소스는 속성에 데이터가 포함된 단일 개체로 처리되거나 종종 함께 그룹화되는 다형 개체의 데이터 컬렉션(예: 데이터베이스에 대한 쿼리의 결과)으로 처리될 수 있습니다. 지금까지 단일 개체에 대한 바인딩만 설명했지만 일반적인 시나리오는 데이터 컬렉션에 대한 바인딩입니다. 일반적인 시나리오를 사용 하는 예를 들어는 <xref:System.Windows.Controls.ItemsControl> 와 같은 한 <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView>, 또는 <xref:System.Windows.Controls.TreeView> 에 표시 된 응용 프로그램에서 같은 데이터 컬렉션을 표시 하는 [데이터 바인딩의?](#what_is_data_binding) 섹션.  
  
 다행히도 기본 다이어그램이 적용됩니다. 바인딩하는 경우는 <xref:System.Windows.Controls.ItemsControl> 를 컬렉션에 다이어그램은 다음과 같습니다.  
  
 ![데이터 바인딩 ItemsControl 다이어그램](../../../../docs/framework/wpf/data/media/databindingitemscontrol.png "DataBindingItemsControl")  
  
 바인딩할이 다이어그램에 나와 있는 것 처럼는 <xref:System.Windows.Controls.ItemsControl> 컬렉션 개체에 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성은 사용 하는 속성입니다. 생각할 수 있으며 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성의 내용으로는 <xref:System.Windows.Controls.ItemsControl>합니다. 바인딩은 참고 <xref:System.Windows.Data.BindingMode.OneWay> 때문에 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성은 지원 <xref:System.Windows.Data.BindingMode.OneWay> 기본적으로 바인딩.  
  
<a name="how_to_implement_collections"></a>   
### <a name="how-to-implement-collections"></a>컬렉션을 구현하는 방법  
 구현 하는 컬렉션을 열거할 수는 <xref:System.Collections.IEnumerable> 인터페이스입니다. 그러나 삽입 또는 삭제 컬렉션에서 업데이트할 수 있도록 동적 바인딩을 설정 하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컬렉션은 자동으로 구현 해야 합니다는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스입니다. 이 인터페이스는 기본 컬렉션이 변경될 때마다 발생해야 하는 이벤트를 노출합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]제공 된 <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스를 노출 하는 데이터 컬렉션을 구현 하는 기본 제공는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스입니다. 완전 하 게 지원 대상에 소스 개체의 현재 전송 데이터 값을 지 원하는 바인딩 가능한 속성 컬렉션에 있는 각 개체 구현 해야 참고는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스입니다. 자세한 내용은 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)를 참조하세요.  
  
 고유한 컬렉션을 구현 하기 전에 사용 하 여 것이 좋습니다 <xref:System.Collections.ObjectModel.ObservableCollection%601> 또는 같은 기존 컬렉션 중 하나가 클래스 <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, 및 <xref:System.ComponentModel.BindingList%601>, 다양 한 기타. 고급 시나리오에 있고 컬렉션을 직접 구현 하는 것이 좋습니다를 사용 하 여 <xref:System.Collections.IList>, 인덱스 및 최적의 성능을 개별적으로 액세스할 수 있는 개체의 제네릭이 아닌 컬렉션을 제공 하는 합니다.  
  
<a name="collection_views"></a>   
### <a name="collection-views"></a>컬렉션 뷰  
 한 번에 <xref:System.Windows.Controls.ItemsControl> 에 바인딩된 데이터 컬렉션을 정렬, 필터링 또는 데이터를 그룹화 하는 것이 좋습니다. 컬렉션 뷰를 구현 하는 클래스를 사용 하는 작업을 수행 하는 <xref:System.ComponentModel.ICollectionView> 인터페이스입니다.  
  
  
#### <a name="what-are-collection-views"></a>컬렉션 뷰란?  
 컬렉션 뷰는 기본 소스 컬렉션 자체를 변경할 필요 없이 정렬, 필터 및 그룹화 쿼리에 따라 소스 컬렉션을 탐색하고 표시할 수 있는 바인딩 소스 컬렉션의 최상위에 있는 레이어입니다. 컬렉션 뷰에서는 컬렉션의 현재 항목에 대한 포인터도 유지 관리합니다. 소스 컬렉션에서 구현 하는 경우는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스에 의해 발생 한 변경 내용을 <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> 이벤트 보기에 전파 됩니다.  
  
 뷰는 기본 소스 컬렉션을 변경하지 않으므로 각 소스 컬렉션에는 연결된 여러 뷰가 있을 수 있습니다. 예를 들어 *Task* 개체의 컬렉션이 있을 수 있습니다. 뷰를 사용하여 같은 데이터를 다양한 방식으로 표시할 수 있습니다. 예를 들어 페이지 왼쪽에는 우선 순위별로 정렬된 작업을 표시하고 오른쪽에는 영역별로 그룹화된 작업을 표시해야 할 수 있습니다.  
  
<a name="how_to_create_a_view"></a>   
#### <a name="how-to-create-a-view"></a>뷰를 만드는 방법  
 뷰를 만들고 사용하는 한 가지 방법은 뷰 개체를 인스턴스화하고 이를 바인딩 소스로 사용하는 것입니다. 예를 들어 [데이터 바인딩이란?](#what_is_data_binding) 섹션에 나와 있는 [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703)(데이터 바인딩 데모) 응용 프로그램을 살펴보겠습니다. 구현 된 되도록는 <xref:System.Windows.Controls.ListBox> 직접 데이터 수집 하는 대신 데이터 컬렉션에 대 한 뷰를 바인딩합니다. 다음 예제는 [Data Binding Demo](http://go.microsoft.com/fwlink/?LinkID=163703)(데이터 바인딩 데모) 응용 프로그램에서 추출됩니다. <xref:System.Windows.Data.CollectionViewSource> 클래스는는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 에서 상속 되는 클래스의 프록시 <xref:System.Windows.Data.CollectionView>합니다. 이 특정 예제는 <xref:System.Windows.Data.CollectionViewSource.Source%2A> 뷰의 바인딩된는 *AuctionItems* 컬렉션 (형식의 <xref:System.Collections.ObjectModel.ObservableCollection%601>) 현재 응용 프로그램 개체입니다.  
  
 [!code-xaml[DataBindingLab#WindowResources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xaml[DataBindingLab#CollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xaml[DataBindingLab#WindowResources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 리소스 *listingDataView* 등 역할 요소는 응용 프로그램에 대 한 바인딩 소스로 <xref:System.Windows.Controls.ListBox>:  
  
 [!code-xaml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 동일한 컬렉션에 대 한 다른 보기를 만들려면 다른 만들 수 있습니다 <xref:System.Windows.Data.CollectionViewSource> 인스턴스 하 고 다른 `x:Key` 이름입니다.  
  
 다음 표에서 뷰 데이터 형식을 기본 컬렉션 뷰로 또는 만들어집니다 <xref:System.Windows.Data.CollectionViewSource> 소스 컬렉션 형식을 기반으로 합니다.  
  
|소스 컬렉션 형식|컬렉션 뷰 형식|참고|  
|----------------------------|--------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|내부 형식에 따라<xref:System.Windows.Data.CollectionView>|항목을 그룹화할 수 없습니다.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|가장 빠릅니다.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### <a name="using-a-default-view"></a>기본 뷰 사용  
 컬렉션 뷰를 만들고 사용하는 한 가지 방법은 컬렉션 뷰를 바인딩 소스로 지정하는 것입니다. WPF에서도 바인딩 소스로 사용되는 모든 컬렉션에 대한 기본 컬렉션 뷰를 만듭니다. 컬렉션에 직접 바인딩할 경우 WPF는 기본 뷰에 바인딩됩니다. 같은 컬렉션에 대한 모든 바인딩이 이 기본 뷰를 공유하므로 하나의 바인딩된 컨트롤이나 코드(예: 뒷부분에 설명되는 현재 항목 포인터에 대한 정렬 또는 변경)를 통해 기본 뷰에 적용된 변경 내용은 같은 컬렉션에 대한 모든 다른 바인딩에 반영됩니다.  
  
 사용 하면 기본 보기를 가져오려면는 <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> 메서드. 예제를 보려면 [데이터 수집의 기본 뷰 가져오기](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)를 참조하세요.  
  
##### <a name="collection-views-with-adonet-datatables"></a>ADO.NET DataTable이 있는 컬렉션 뷰  
 성능을 향상 시키기 위해 ADO.NET에 대 한 컬렉션 뷰 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataView> 개체 정렬 및 필터링을 대리자는 <xref:System.Data.DataView>합니다. 이렇게 하면 정렬 및 필터링이 데이터 소스의 모든 컬렉션 뷰에서 공유됩니다. 정렬 하 고 독립적으로 필터링 컬렉션 뷰를 사용 하도록 설정 하는 자체 컬렉션 뷰를 초기화 <xref:System.Data.DataView> 개체입니다.  
  
#### <a name="sorting"></a>정렬  
 앞에서 설명한 대로 뷰에서는 컬렉션에 정렬 순서를 적용할 수 있습니다. 기본 컬렉션에 있는 데이터에는 관련 상속 순서가 있거나 없을 수도 있습니다. 컬렉션에 대한 뷰를 통해 제공한 비교 기준에 따라 순서를 적용하거나 기본 순서를 변경할 수 있습니다. 이는 데이터의 클라이언트 기반 뷰이므로 일반적으로 열과 일치하는 값에 따라 표 형식 데이터의 열을 정렬해야 할 수 있습니다. 뷰를 사용하면 기본 컬렉션을 변경하거나 컬렉션 콘텐츠를 다시 쿼리할 필요 없이 이 사용자 기반 정렬을 적용할 수 있습니다. 예제를 보려면 [머리글을 클릭할 때 GridView 열 정렬](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)을 참조하세요.  
  
 다음 예제에서는 "Sort 범주 및 날짜"의 정렬 논리 <xref:System.Windows.Controls.CheckBox> 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 에 [데이터 바인딩의?](#what_is_data_binding) 섹션:  
  
 [!code-csharp[DataBindingLab#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
#### <a name="filtering"></a>필터링  
 컬렉션에 필터를 적용할 수도 있습니다. 이는 항목이 컬렉션에 있을 수 있지만 이 특정 뷰는 전체 컬렉션의 특정 하위 집합만 표시하는 데 사용됨을 의미합니다. 데이터에서 조건에 따라 필터링할 수 있습니다. 예를 들어, 응용 프로그램에서 단원의 [데이터 바인딩의?](#what_is_data_binding) 섹션 "표시만 세우고" <xref:System.Windows.Controls.CheckBox> 하 여 가격이 $25 개 이상의 항목을 필터링 하기 위한 논리가 포함 합니다. 설정 하려면 다음 코드를 실행 하는 *ShowOnlyBargainsFilter* 로 <xref:System.Windows.Data.CollectionViewSource.Filter> 이벤트 처리기 때는 <xref:System.Windows.Controls.CheckBox> 선택:  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 *ShowOnlyBargainsFilter* 이벤트 처리기에는 다음과 같은 구현이 있습니다.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 중 하나를 사용 하는 경우는 <xref:System.Windows.Data.CollectionView> 직접 대신의 클래스 <xref:System.Windows.Data.CollectionViewSource>를 사용 하 여는 <xref:System.Windows.Data.CollectionView.Filter%2A> 속성을 통해는 콜백을 지정 합니다. 예제를 보려면 [뷰에서 데이터 필터링](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)을 참조하세요.  
  
#### <a name="grouping"></a>그룹화  
 내부 클래스를 제외 하 고는 <xref:System.Collections.IEnumerable> 컬렉션, 모든 컬렉션 뷰를 논리 그룹으로 컬렉션 뷰에서의 컬렉션을 분할할 수 있도록 그룹화의 기능을 지원 합니다. 그룹은 사용자가 그룹 목록을 제공하는 경우 명시적 그룹이고 데이터에 따라 그룹이 동적으로 생성되는 경우 암시적 그룹입니다.  
  
 다음 예제에서는 "범주별 그룹"의 논리를 보여 줍니다. <xref:System.Windows.Controls.CheckBox>:  
  
 [!code-csharp[DataBindingLab#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 다른 그룹화 예제를 보려면 [GridView를 구현하는 ListView의 항목 그룹화](../../../../docs/framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md)를 참조하세요.  
  
#### <a name="current-item-pointers"></a>현재 항목 포인터  
 뷰는 현재 항목의 개념도 지원합니다. 컬렉션 뷰에서 개체를 탐색할 수 있습니다. 탐색할 때 컬렉션의 특정 위치에 있는 개체를 검색할 수 있는 항목 포인터를 이동합니다. 예제를 보려면 [데이터 수집 뷰의 개체 탐색](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md)을 참조하세요.  
  
 WPF는 뷰(지정한 뷰 또는 컬렉션의 기본 뷰)를 통해 컬렉션에 바인딩되므로 컬렉션에 대한 모든 바인딩에는 현재 항목 포인터가 포함됩니다. 뷰에 바인딩할 때 `Path` 값의 슬래시("/") 문자는 뷰의 현재 항목을 지정합니다. 다음 예제에서 데이터 컨텍스트는 컬렉션 뷰입니다. 첫 줄은 컬렉션에 바인딩됩니다. 두 번째 줄은 컬렉션의 현재 항목에 바인딩됩니다. 세 번째 줄은 컬렉션에 있는 현재 항목의 `Description` 속성에 바인딩됩니다.  
  
```xaml  
<Button Content="{Binding }" />  
<Button Content="{Binding Path=/}" />  
<Button Content="{Binding Path=/Description}" />   
```  
  
 컬렉션 계층 구조를 트래버스하도록 슬래시와 속성 구문을 쌓을 수도 있습니다. 다음 예제에서는 소스 컬렉션의 현재 항목 속성인 `Offices`라는 컬렉션의 현재 항목에 바인딩합니다.  
  
```xaml  
<Button Content="{Binding /Offices/}" />  
```  
  
 컬렉션에 적용되는 정렬이나 필터링이 현재 항목 포인터에 영향을 미칠 수 있습니다. 정렬은 현재 항목 포인터를 선택된 마지막 항목에 유지하지만 이제 컬렉션 뷰는 포인터를 중심으로 재구성됩니다. 이전에는 선택된 항목이 목록의 시작 부분에 있었을 수 있지만 이제 선택된 항목이 가운데 부분에 있을 수 있습니다. 필터링은 필터링한 후 선택 항목이 뷰에 남아 있으면 선택된 항목을 유지합니다. 남아 있지 않으면 현재 항목 포인터는 필터링된 컬렉션 뷰의 첫 번째 항목으로 설정됩니다.  
  
<a name="master_detail_scenario"></a>   
#### <a name="master-detail-binding-scenario"></a>마스터-세부 바인딩 시나리오  
 현재 항목의 개념은 컬렉션에서 항목을 탐색하는 경우뿐 아니라 마스터-세부 바인딩 시나리오에도 유용합니다. 다시 [데이터 바인딩이란?](#what_is_data_binding) 섹션의 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 살펴보겠습니다. 해당 응용 프로그램 내에서 선택 영역에에서는 <xref:System.Windows.Controls.ListBox> 결정에 표시 되는 콘텐츠는 <xref:System.Windows.Controls.ContentControl>합니다. 또 다른 방법은에 배치할 때는 <xref:System.Windows.Controls.ListBox> 항목을 선택 하면는 <xref:System.Windows.Controls.ContentControl> 선택한 항목의 세부 정보를 표시 합니다.  
  
 간단히 두 개 이상의 컨트롤을 같은 뷰에 바인딩하여 마스터-세부 시나리오를 구현할 수 있습니다. 다음 예제는 [데이터 바인딩 데모](http://go.microsoft.com/fwlink/?LinkID=163703) 의 태그를 보여 줍니다.는 <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ContentControl> 응용 프로그램에 참조 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 에 [데이터 바인딩의?](#what_is_data_binding) 섹션:  
  
 [!code-xaml[DataBindingLab#Master1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xaml[DataBindingLab#Detail](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 컨트롤이 둘 다 같은 소스인 *listingDataView* 정적 리소스에 바인딩되어 있습니다([뷰를 만드는 방법 섹션](#how_to_create_a_view)에서 이 리소스의 정의 참조). 하므로이 작업이 singleton 개체 (의 <xref:System.Windows.Controls.ContentControl> 이 예제의) 바인딩된 컬렉션 뷰에 자동으로에 바인딩되기는 <xref:System.Windows.Data.CollectionView.CurrentItem%2A> 보기의 합니다. <xref:System.Windows.Data.CollectionViewSource> 개체는 통화 및 선택 영역에 자동으로 동기화 합니다. 목록 컨트롤에 바인딩되지 않은 경우는 <xref:System.Windows.Data.CollectionViewSource> 설정 해야 하는 다음이 예제와 같이 개체 해당 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true` 이 수행 합니다.  
  
 다른 예제를 보려면 [선택에 따라 수집 및 표시 정보에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) 및 [계층적 데이터에 마스터-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)을 참조하세요.  
  
 위 예제에서는 템플릿을 사용합니다. 실제로 데이터가 표시 되지 않는 서식 파일을 사용 하지 않고도 원하는 대로 (에서 명시적으로 사용 하는 <xref:System.Windows.Controls.ContentControl> 및 암시적으로 사용 되는 것은 <xref:System.Windows.Controls.ListBox>). 이제 다음 섹션에서 데이터 템플릿을 살펴보겠습니다.  
  
<a name="data_templating"></a>   
## <a name="data-templating"></a>데이터 템플릿  
 데이터 템플릿을 사용하지 않으면 [데이터 바인딩이란?](#what_is_data_binding) 섹션의 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 다음과 같이 표시됩니다.  
  
 ![데이터 템플릿을 사용하지 않는 데이터 바인딩 데모](../../../../docs/framework/wpf/data/media/databindingdemotemplates.png "DataBindingDemoTemplates")  
  
 이전 섹션의 예제에 나와 있는 것 처럼 모두는 <xref:System.Windows.Controls.ListBox> 제어 및 <xref:System.Windows.Controls.ContentControl> 의 전체 컬렉션 개체 (또는 보다 구체적으로, 컬렉션 개체에 대해 보기)에 바인딩된 *AuctionItem*s입니다. 데이터 컬렉션을 표시 하는 방법에 특정 한 지침이 없으면는 <xref:System.Windows.Controls.ListBox> 기본 컬렉션의 각 개체의 문자열 표현을 표시 및 <xref:System.Windows.Controls.ContentControl> 에 바인딩되는 개체의 문자열 표현을 표시 합니다.  
  
 이러한 문제를 해결 하기 위해 응용 프로그램 정의 <xref:System.Windows.DataTemplate>s입니다. 이전 섹션의 예제에 나와 있는 것 처럼는 <xref:System.Windows.Controls.ContentControl> 명시적으로 사용 하 여는 *detailsProductListingTemplate*<xref:System.Windows.DataTemplate>합니다. <xref:System.Windows.Controls.ListBox> 컨트롤이 암시적으로 사용 하 여 다음 <xref:System.Windows.DataTemplate> 표시할 때의 *AuctionItem* 컬렉션의 개체:  
  
 [!code-xaml[DataBindingLab#AuctionItemDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 이 두를 사용 하 여 <xref:System.Windows.DataTemplate>s, UI에 표시 된 것은는 [데이터 바인딩의?](#what_is_data_binding) 섹션. 해당 스크린 샷 알 수 있듯이 있을 뿐만 아니라 데이터의에서 넣으면 컨트롤 <xref:System.Windows.DataTemplate>s를 사용 하면 데이터에 대 한 매력적인 시각적 개체를 정의할 수 있습니다. 예를 들어 <xref:System.Windows.DataTrigger> 는 위의 <xref:System.Windows.DataTemplate> 에서 사용되므로 *HighLight* 값이 *SpecialFeatures*인 *AuctionItem*에는 주황색 테두리와 별모양이 함께 표시됩니다.  
  
 데이터 템플릿에 대한 자세한 내용은 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)를 참조하세요.  
  
<a name="data_validation"></a>   
## <a name="data-validation"></a>데이터 유효성 검사  
  
 사용자 입력을 사용하는 대부분 응용 프로그램에는 사용자가 필요한 정보를 입력했는지 확인할 수 있는 유효성 검사 논리가 있어야 합니다. 유효성 검사는 형식, 범위, 서식 또는 기타 응용 프로그램별 요구 사항에 따라 달라질 수 있습니다. 이 섹션에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 데이터 유효성 검사를 사용하는 방법을 설명합니다.  
  
### <a name="associating-validation-rules-with-a-binding"></a>유효성 검사 규칙과 바인딩 연결  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 데이터 바인딩 모델에 연결할 수 있습니다. <xref:System.Windows.Data.Binding.ValidationRules%2A> 와 프로그램 <xref:System.Windows.Data.Binding> 개체입니다. 예를 들어 다음 예제에서는 <xref:System.Windows.Controls.TextBox> 라는 속성을 `StartPrice` 추가 <xref:System.Windows.Controls.ExceptionValidationRule> 개체는 <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> 속성입니다.  
  
 [!code-xaml[DataBindingLab#DefaultValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 A <xref:System.Windows.Controls.ValidationRule> 개체 속성의 값이 유효한 지 확인 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 다음 두 가지 유형의 기본 제공 <xref:System.Windows.Controls.ValidationRule> 개체:  
  
-   A <xref:System.Windows.Controls.ExceptionValidationRule> 바인딩 소스 속성을 업데이트 하는 동안 throw 된 예외를 확인 합니다. 이전 예제에서 `StartPrice`는 정수 형식입니다. 사용자가 정수로 변환될 수 없는 값을 입력하면 예외가 throw되어 바인딩이 잘못된 것으로 표시됩니다. 설정 하는 대체 구문은 <xref:System.Windows.Controls.ExceptionValidationRule> 명시적으로 설정 하는 것은 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성을 `true` 에 프로그램 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체입니다.  
  
-   A <xref:System.Windows.Controls.DataErrorValidationRule> 구현 하는 개체에 의해 발생 하는 오류를 확인 하는 개체는 <xref:System.ComponentModel.IDataErrorInfo> 인터페이스입니다. 이 유효성 검사 규칙을 사용 하 여 예제를 보려면 <xref:System.Windows.Controls.DataErrorValidationRule>합니다. 설정 하는 대체 구문은 <xref:System.Windows.Controls.DataErrorValidationRule> 명시적으로 설정 하는 것은 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 속성을 `true` 에 프로그램 <xref:System.Windows.Data.Binding> 또는 <xref:System.Windows.Data.MultiBinding> 개체입니다.  
  
 파생 하 여 고유한 유효성 검사 규칙을 만들 수도 있습니다는 <xref:System.Windows.Controls.ValidationRule> 클래스 및 구현 된 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드. 다음 예제에서 사용 하는 규칙을 보여 줍니다.는 *제품 목록 추가* "시작 날짜" <xref:System.Windows.Controls.TextBox> 에서 [데이터 바인딩의?](#what_is_data_binding) 섹션:  
  
 [!code-csharp[DataBindingLab#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> 이 사용 하 여 *FutureDateRule*다음 예제에 나온 것 처럼:  
  
 [!code-xaml[DataBindingLab#CustomValidation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 되므로 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값은 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, 바인딩 엔진에서 모든 규칙 즉 것도 검사 페이지가 활성화 소스 값이 업데이트는 <xref:System.Windows.Data.Binding.ValidationRules%2A> 이기 합니다. 이 내용은 유효성 검사 프로세스 섹션에서 자세히 설명합니다.  
  
<a name="invalidation_feedback"></a>   
### <a name="providing-visual-feedback"></a>시각적 피드백 제공  
 사용자가 잘못된 값을 입력할 경우 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 오류에 대한 피드백을 표시해야 할 수 있습니다. 설정 하는 이러한 의견을 제공 하는 한 가지 방법은 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> 연결 된 속성을 사용자 지정 <xref:System.Windows.Controls.ControlTemplate>합니다. 이전 하위 섹션에 나와 있는 것 처럼는 *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> 사용 하 여 프로그램 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 호출 *validationTemplate*합니다. 다음 예제에서는 *validationTemplate*의 정의를 보여 줍니다.  
  
 [!code-xaml[DataBindingLab#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 <xref:System.Windows.Controls.AdornedElementPlaceholder> 요소 장식 되는 컨트롤을 배치할 위치를 지정 합니다.  
  
 또한 사용할 수도 있습니다는 <xref:System.Windows.Controls.ToolTip> 오류 메시지를 표시 합니다. 두는 *StartDateEntryForm* 및 *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>es 스타일을 사용 하 여 *textStyleTextBox*, 만듦는 <xref:System.Windows.Controls.ToolTip> 하 오류 메시지를 표시 합니다. 다음 예제에서는 *textStyleTextBox*의 정의를 보여 줍니다. 연결 된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 은 `true` 바인딩된 요소의 속성에는 바인딩 중 하나 이상이 있는 경우 오류입니다.  
  
 [!code-xaml[DataBindingLab#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 사용자 지정 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 <xref:System.Windows.Controls.ToolTip>, *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> 유효성 검사 오류가 있을 때 다음과 같은:  
  
 ![데이터 바인딩 유효성 검사 오류](../../../../docs/framework/wpf/data/media/databindingdemo-validation.PNG "DataBindingDemo_Validation")  
  
 경우에 <xref:System.Windows.Data.Binding> 유효성 검사 규칙에 연결 된 지정 하지 않으면는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 바인딩된 컨트롤을 기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 유효성 검사 오류가 있을 때 사용자가 알리는 데 사용 됩니다. 기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 빨간색 테두리가 표시기 계층에서 정의 하는 컨트롤 서식 파일입니다. 기본 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 <xref:System.Windows.Controls.ToolTip>, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 의 *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> 유효성 검사 오류가 있을 때 다음과 같은:  
  
 ![데이터 바인딩 유효성 검사 오류](../../../../docs/framework/wpf/data/media/databindingdemo-validationdefault.PNG "DataBindingDemo_ValidationDefault")  
  
 대화 상자에서 모든 컨트롤의 유효성을 검사하는 논리를 제공하는 방법의 예제를 보려면 [대화 상자 개요](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)에서 사용자 지정 대화 상자 섹션을 참조하세요.  
  
### <a name="validation-process"></a>유효성 검사 프로세스  
 유효성 검사는 대개 대상 값이 바인딩 소스 속성에 전송될 때 수행됩니다. 으로 수행 <xref:System.Windows.Data.BindingMode.TwoWay> 및 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩. 다시 말해,의 값에 따라 소스 업데이트가 발생 원인는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성에 설명 된 대로 [트리거 소스 업데이트 항목](#what_triggers_source_updates) 섹션.  
  
 *유효성 검사* 프로세스에 대한 설명은 다음과 같습니다. 이 프로세스 중에 유효성 검사 오류나 기타 오류가 발생하면 프로세스가 중단됩니다.  
  
1.  바인딩 엔진에 사용자 지정 되어 있는지 확인 <xref:System.Windows.Controls.ValidationRule> 개체는 정의 된 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 로 설정 된 <xref:System.Windows.Controls.ValidationStep.RawProposedValue> 해당 <xref:System.Windows.Data.Binding>를 호출 하는 경우는 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 각 메서드 <xref:System.Windows.Controls.ValidationRule> 오류 중 하나가 실행 될 때까지 되거나 모두 통과 합니다.  
  
2.  그런 다음 바인딩 엔진은 변환기를 호출합니다(있는 경우).  
  
3.  바인딩 엔진에는 사용자 지정 되어 있는지 확인 하는 변환기에 성공 하면 <xref:System.Windows.Controls.ValidationRule> 개체는 정의 된 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 로 설정 된 <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> 해당 <xref:System.Windows.Data.Binding>를 호출 하는 경우는 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 각 메서드 <xref:System.Windows.Controls.ValidationRule> 있는 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 로 설정 <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> 모두 통과 하거나 해당 개체 중 하나는 동안 오류가 발생 될 때까지 합니다.  
  
4.  바인딩 엔진은 소스 속성을 설정합니다.  
  
5.  바인딩 엔진에 사용자 지정 되어 있는지 확인 <xref:System.Windows.Controls.ValidationRule> 개체는 정의 된 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 로 설정 되어 <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 해당 <xref:System.Windows.Data.Binding>를 호출 하는 경우는 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 각 메서드 <xref:System.Windows.Controls.ValidationRule> 올려진 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 로 설정 <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 모두 통과 하거나 해당 개체 중 하나는 동안 오류가 발생 될 때까지 합니다. 경우는 <xref:System.Windows.Controls.DataErrorValidationRule> 는 바인딩과 연결 된 및 해당 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 기본값으로 설정 되어 <xref:System.Windows.Controls.ValidationStep.UpdatedValue>, <xref:System.Windows.Controls.DataErrorValidationRule> 이 시점에서 확인 됩니다. 지점 이기도 때 포함 된 바인딩이 <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> 로 설정 `true` 확인 됩니다.  
  
6.  바인딩 엔진에 사용자 지정 되어 있는지 확인 <xref:System.Windows.Controls.ValidationRule> 개체는 정의 된 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 로 설정 되어 <xref:System.Windows.Controls.ValidationStep.CommittedValue> 해당 <xref:System.Windows.Data.Binding>를 호출 하는 경우는 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 각 메서드 <xref:System.Windows.Controls.ValidationRule> 올려진 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 로 설정 <xref:System.Windows.Controls.ValidationStep.CommittedValue> 모두 통과 하거나 해당 개체 중 하나는 동안 오류가 발생 될 때까지 합니다.  
  
 경우는 <xref:System.Windows.Controls.ValidationRule> 통과 하지 못하면이 프로세스 전체에서 언제 든 바인딩 엔진을 만듭니다는 <xref:System.Windows.Controls.ValidationError> 개체에 추가 합니다는 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 바인딩된 요소의 컬렉션입니다. 엔진이 실행 되는 바인딩 전에 <xref:System.Windows.Controls.ValidationRule> 제거 된 지정된 된 단계에서 개체 <xref:System.Windows.Controls.ValidationError> 추가 된는 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 해당 단계에서 연결 된 바인딩된 요소의 속성입니다. 예를 들어 경우는 <xref:System.Windows.Controls.ValidationRule> 인 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 로 설정 된 <xref:System.Windows.Controls.ValidationStep.UpdatedValue> 실패, 유효성 검사 프로세스가 발생 바인딩 엔진을 제거 하는 다음에 <xref:System.Windows.Controls.ValidationError> 하나를 호출 하기 전에 즉시 <xref:System.Windows.Controls.ValidationRule> 올려진 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> 로 설정 <xref:System.Windows.Controls.ValidationStep.UpdatedValue>.  
  
 때 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 비어 있지 않으면는 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 요소의 연결된 속성이로 설정 되어 `true`합니다. 또한 경우는 <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> 속성의는 <xref:System.Windows.Data.Binding> 로 설정 되어 `true`, 바인딩 엔진에서 발생 한 후의 <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> 요소에서 연결 된 이벤트입니다.  
  
 유효한 값을 전송 (원본이 나 대상에는 원본 또는 대상) 어느 방향으로든에서 지웁니다 참고도는 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 연결 된 속성입니다.  
  
 바인딩에 중 하나는 다음과 같은 경우는 <xref:System.Windows.Controls.ExceptionValidationRule> 연관 되거나는 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> 속성이 `true` 바인딩 엔진이 소스를 설정 하는 경우 예외가 throw 됩니다, 바인딩 엔진 확인 하는 경우 및는 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>합니다. 사용 하는 옵션이 고 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> 예외를 처리 하기 위한 사용자 지정 처리기를 제공 하는 콜백 합니다. 경우는 <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> 에 지정 되어 있지는 <xref:System.Windows.Data.Binding>, 바인딩 엔진을 만듭니다는 <xref:System.Windows.Controls.ValidationError> 예외와에 추가 <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> 바인딩된 요소의 컬렉션입니다.  
  
## <a name="debugging-mechanism"></a>디버깅 메커니즘  
 연결 된 속성을 설정할 수 있습니다 <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> 특정 바인딩 상태에 대 한 정보를 받을 바인딩 관련 개체에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.DataErrorValidationRule>  
 [WPF 버전 4.5의 새로운 기능](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [LINQ 쿼리 결과에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [데이터 바인딩 데모](http://go.microsoft.com/fwlink/?LinkID=163703)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [ADO.NET 데이터 소스 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)
