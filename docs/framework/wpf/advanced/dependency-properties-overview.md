---
title: "종속성 속성 개요 | Microsoft Docs"
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
  - "연결된 속성"
  - "데이터 바인딩(data binding)"
  - "종속성 속성"
  - "속성, 연결됨"
  - "속성, 개요"
  - "리소스, 참조"
  - "스타일"
ms.assetid: d119d00c-3afb-48d6-87a0-c4da4f83dee5
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# 종속성 속성 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성의 기능을 확장하는 데 사용할 수 있는 서비스 집합을 제공합니다.  이러한 서비스를 통칭하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템이라고 합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템의 지원을 받는 속성은 [종속성 속성](GTMT)이라고 합니다. 이 개요에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템 및 [종속성 속성](GTMT)의 기능에 대해 설명합니다. 또한 XAML 및 코드에서 기존 [종속성 속성](GTMT)을 사용하는 방법도 설명합니다.  이 개요 부분에서는 종속성 메타데이터와 같은 종속성 속성의 특징 및 사용자 지정 클래스에 사용자 고유의 종속성 속성을 만드는 방법도 소개합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 독자가 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 및 개체 지향 프로그래밍에 대한 기본적인 지식을 갖고 있다고 가정합니다.  이 항목의 예제를 실행하려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 이해하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 작성 방법을 알고 있어야 합니다.  자세한 내용은 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)를 참조하십시오.  
  
<a name="why_dependency_properties"></a>   
## 종속성 속성 및 CLR 속성  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 속성이 일반적으로 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성으로 노출됩니다.  가장 기본적인 수준에서는 이러한 속성과 직접 상호 작용하면서도 속성이 [종속성 속성](GTMT)으로 구현된 사실을 모를 수 있습니다.  그러나 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템의 기능을 활용하려면 이러한 기능 전체 또는 일부에 익숙해져야 합니다.  
  
 [종속성 속성](GTMT)은 다른 입력 값을 기준으로 속성 값을 계산하기 위한 용도로 사용됩니다.  여기서 다른 입력 값에는 테마 및 사용자 기본 설정 같은 시스템 속성, 데이터 바인딩 및 애니메이션\/Storyboard 같은 Just\-In\-Time 속성 결정 메커니즘, 리소스 및 스타일 같은 다용도 템플릿, 요소 트리에서 다른 요소와의 부모\-자식 관계를 통해 알 수 있는 값 등이 포함될 수 있습니다.  또한 [종속성 속성](GTMT)을 구현하여 독립적인 유효성 검사, 기본값, 다른 속성에 대한 변경 내용을 모니터링하는 콜백 및 런타임 정보를 기준으로 속성 값을 강제 변환할 수 있는 시스템을 제공할 수도 있습니다.  파생된 클래스에서도 구현되어 있는 기존 속성을 재정의하거나 새 속성을 만드는 대신 종속성 속성 메타데이터를 재정의하여 기존 속성의 일부 특징을 변경할 수 있습니다.  
  
 SDK 참조서에서 속성의 관리되는 참조 페이지에 종속성 속성 정보 섹션이 있는지 여부를 검사하여 해당 속성의 종속성 속성 여부를 확인할 수 있습니다.  종속성 속성 정보 섹션에는 해당 종속성 속성의 <xref:System.Windows.DependencyProperty> 식별자 필드에 대한 링크 및 해당 속성에 대해 설정된 메타데이터 옵션 목록, 클래스별 재정의 정보 및 기타 세부 정보가 들어 있습니다.  
  
<a name="back_dependency_properties"></a>   
## CLR 속성을 지원하는 종속성 속성  
 [종속성 속성](GTMT)과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템은 전용 필드를 사용하여 속성을 지원하는 표준 방식 대신 속성을 지원하는 형식을 제공하여 속성의 기능을 확장합니다.  이 형식의 이름은 <xref:System.Windows.DependencyProperty>입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템을 정의하는 또 하나의 중요한 형식은 <xref:System.Windows.DependencyObject>입니다. <xref:System.Windows.DependencyObject>는 [종속성 속성](GTMT)을 등록하고 소유할 수 있는 기본 클래스를 정의합니다.  
  
 다음은 이 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] 설명서에서 [종속성 속성](GTMT)을 설명하는 데 사용되는 용어 정의입니다.  
  
-   **종속성 속성:** <xref:System.Windows.DependencyProperty>로 지원되는 속성입니다.  
  
-   **종속성 속성 식별자:** [종속성 속성](GTMT)을 등록할 때 반환 값으로 반환된 후 클래스의 정적 멤버로 저장되는 <xref:System.Windows.DependencyProperty> 인스턴스입니다.  이 식별자는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템과 상호 작용하는 대부분의 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]에 매개 변수로 사용됩니다.  
  
-   **CLR "래퍼":** 속성에 대한 실제 get\/set 구현입니다.  이러한 구현은 종속성 속성 식별자를 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 호출에 사용하여 통합함으로써 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템을 통한 속성 지원 기능을 제공합니다.  
  
 다음 예제에서는 `IsSpinning` [종속성 속성](GTMT)을 정의하고 <xref:System.Windows.DependencyProperty> 식별자 및 이 식별자가 지원하는 속성 사이의 관계를 보여 줍니다.  
  
 [!code-csharp[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
 [!code-vb[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
[!code-csharp[PropertiesOvwSupport#DPFormBasic2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic2)]  
  
 속성과 지원 <xref:System.Windows.DependencyProperty> 필드의 명명 규칙은 매우 중요합니다.  필드 이름은 항상 속성 이름에 `Property` 접미사를 추가한 형식입니다.  이 규칙과 규칙을 사용하는 이유에 대한 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하십시오.  
  
<a name="setting_property_values"></a>   
## 속성 값 설정  
 속성은 코드 또는 XAML에서 설정할 수 있습니다.  
  
<a name="local_property_values"></a>   
### XAML에서 속성 값 설정  
 다음 XAML 예제에서는 단추의 배경색을 빨강으로 지정합니다.  이 예제는 생성된 코드에서 WPF XAML 파서가 XAML 특성의 간단한 문자열 값 형식을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 형식으로 변환하는 것을 보여 줍니다. 여기서는 <xref:System.Windows.Media.Color>를 사용하여 <xref:System.Windows.Media.SolidColorBrush>로 변환합니다.  
  
 [!code-xml[PropertiesOvwSupport#MostBasicProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]  
  
 XAML에서는 다양한 형식의 구문을 사용하여 속성을 설정할 수 있습니다.  특정 속성에 사용할 구문은 해당 속성이 사용하는 값 형식뿐만 아니라 형식 변환기가 있는지 여부와 같은 다른 요인에 따라 달라집니다.  속성 설정에 사용하는 XAML 구문에 대한 자세한 내용은 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 및 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)를 참조하십시오.  
  
 다음 XAML 예제에서는 특성을 사용하지 않는 구문의 예로 다른 단추 배경을 보여 줍니다.  이 경우에는 간단한 단색을 설정하는 대신 이미지를 나타내는 요소를 사용하고 해당 이미지의 소스를 중첩된 요소의 특성으로 지정하여 이미지를 배경으로 설정합니다.  이 예제는 속성 요소 구문의 예제입니다.  
  
 [!code-xml[PropertiesOvwSupport#PESyntaxProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]  
  
<a name="setting_properties_code"></a>   
### 코드에서 속성 설정  
 코드에서 [종속성 속성](GTMT) 값을 설정하는 것은 일반적으로 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] "래퍼"를 통해 노출되는 set 구현을 호출하는 것입니다.  
  
 [!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]  
  
 속성 값을 가져오는 것도 사실상 get "래퍼" 구현을 호출하는 것입니다.  
  
 [!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]  
  
 속성 시스템 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]의 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A>를 직접 호출할 수도 있습니다.  기존 속성을 사용하는 경우에는 래퍼가 더 편리하고 속성을 개발자 도구에 노출하는 데 더 유용하기 때문에 대개 이 방법을 사용하지 않아도 되지만 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 직접 호출하는 것이 더 적절한 시나리오도 있습니다.  
  
 속성을 XAML에서 설정한 후 나중에 코드 숨김을 통해 코드에서 액세스할 수도 있습니다.  자세한 내용은 [WPF의 코드 숨김 및 XAML](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)을 참조하십시오.  
  
<a name="functionality"></a>   
## 종속성 속성이 제공하는 속성 기능  
 필드에서 지원되는 속성과 달리 종속성 속성은 속성의 기능을 확장하는 기능을 제공합니다.  일반적으로 이러한 각 기능은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 전체 기능 집합 중에서 다음과 같은 특정 기능을 나타내거나 지원합니다.  
  
-   [리소스](#setting_properties_resources)  
  
-   [데이터 바인딩](#setting_properties_data_binding)  
  
-   [스타일](#setting_properties_styles)  
  
-   [애니메이션](#animations)  
  
-   [메타데이터 재정의](#metadata)  
  
-   [속성 값 상속](#setting_properties_inheritance)  
  
-   [WPF Designer 통합](#vs2008_integration)  
  
<a name="setting_properties_resources"></a>   
### 리소스  
 종속성 속성 값은 리소스 참조를 통해 설정될 수 있습니다.  일반적으로 리소스는 페이지 루트 요소 또는 응용 프로그램의 `Resources` 속성으로 지정되며, 이 두 위치는 리소스에 가장 편리하게 액세스할 수 있는 위치입니다.  다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush> 리소스를 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[PropertiesOvwSupport#ResourcesResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]  
  
 리소스를 정의한 후에는 다음과 같이 해당 리소스를 참조하고, 리소스를 사용하여 속성 값을 제공할 수 있습니다.  
  
 [!code-xml[PropertiesOvwSupport#ResourcesReference](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]  
  
 이 특정 리소스는 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)으로 참조됩니다. particular resource에서는 정적 또는 동적 리소스 참조를 사용할 수 있습니다.  동적 리소스 참조를 사용하려면 종속성 속성에 참조를 설정해야 하므로 이러한 동적 리소스 참조는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템에서 활성화됩니다.  자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
> [!NOTE]
>  리소스는 로컬 값으로 처리되므로 다른 로컬 값을 설정하면 리소스 참조가 제거됩니다.  자세한 내용은 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)를 참조하십시오.  
  
<a name="setting_properties_data_binding"></a>   
### 데이터 바인딩  
 종속성 속성은 데이터 바인딩을 통해 값을 참조할 수 있습니다.  데이터 바인딩은 XAML의 특정 태그 확장 구문 또는 코드의 <xref:System.Windows.Data.Binding> 개체를 통해 작동합니다.  데이터 바인딩을 사용할 경우 속성의 최종 값은 데이터 소스로부터 값을 가져오는 런타임에 결정됩니다.  
  
 다음 예제에서는 XAML에 선언된 바인딩을 사용하여 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 설정합니다.  이 경우 바인딩에는 상속된 데이터 컨텍스트와 <xref:System.Windows.Data.XmlDataProvider> 데이터 소스\(이 예제에서는 보여 주지 않음\)가 사용됩니다.  바인딩 자체는 데이터 소스 내의 <xref:System.Windows.Data.Binding.XPath%2A>를 통해 원하는 소스 속성을 지정합니다.  
  
 [!code-xml[PropertiesOvwSupport#BasicInlineBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]  
  
> [!NOTE]
>  바인딩은 로컬 값으로 처리되므로 다른 로컬 값을 설정하면 바인딩이 제거됩니다.  자세한 내용은 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)를 참조하십시오.  
  
 종속성 속성\(또는 <xref:System.Windows.DependencyObject> 클래스\)은 데이터 바인딩 작업 시 <xref:System.Windows.DependencyObject> 소스 속성 값의 변경에 대한 알림을 생성하는 목적으로 사용되는 <xref:System.ComponentModel.INotifyPropertyChanged>를 기본적으로 지원하지 않습니다.  데이터 바인딩 시 데이터 바인딩 대상에 변경 내용을 보고하는 데 사용할 수 있는 속성을 만드는 방법에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
<a name="setting_properties_styles"></a>   
### 스타일  
 스타일과 템플릿은 종속성 속성을 사용하는 두 가지 주요 시나리오입니다.  특히 스타일은 응용 프로그램 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]를 정의하는 속성을 설정할 때 유용합니다.  일반적으로 스타일은 XAML에서 리소스로 정의됩니다.  스타일은 주로 특정 속성의 "setter"뿐만 아니라 다른 속성의 실시간 값을 기준으로 속성 값을 변경하는 "트리거"를 포함하기 때문에 속성 시스템과 상호 작용합니다.  
  
 다음 예제에서는 아주 간단한 스타일\(여기에 나와 있지는 않지만 <xref:System.Windows.FrameworkElement.Resources%2A> 사전에 정의되어 있을 수 있음\)을 만든 후 이 스타일을 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.FrameworkElement.Style%2A> 속성에 직접 적용합니다.  스타일에 포함된 setter는 스타일이 지정된 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A> 속성을 녹색으로 설정합니다.  
  
 [!code-xml[PropertiesOvwSupport#SimpleStyleDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]  
  
 [!code-xml[PropertiesOvwSupport#SimpleStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]  
  
 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.  
  
<a name="animations"></a>   
### 애니메이션  
 종속성 속성에는 애니메이션 효과를 줄 수 있습니다.  애니메이션 효과를 적용하고 실행할 경우, 애니메이션 효과 값은 속성의 다른 모든 값\(예: 로컬 값\)보다 우선 순위가 높습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 속성의 <xref:System.Windows.Controls.Control.Background%2A>에 애니메이션 효과를 줍니다. 기술적으로 설명하면 속성 요소 구문을 사용하여 빈 <xref:System.Windows.Media.SolidColorBrush>를 <xref:System.Windows.Controls.Control.Background%2A>로 지정한 다음 이 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성에 직접 애니메이션 효과를 주는 방법으로 <xref:System.Windows.Controls.Control.Background%2A>에 애니메이션 효과를 적용합니다.  
  
 [!code-xml[PropertiesOvwSupport#MiniAnimate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]  
  
 속성에 애니메이션 효과를 주는 방법에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 및 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하십시오.  
  
<a name="metadata"></a>   
### 메타데이터 재정의  
 [종속성 속성](GTMT)을 등록하는 원래 클래스에서 속성을 파생시킬 때 해당 속성의 메타데이터를 재정의하여 [종속성 속성](GTMT)의 특정 동작을 변경할 수 있습니다.  메타데이터를 재정의하려면 <xref:System.Windows.DependencyProperty> 식별자가 필요합니다.  메타데이터를 재정의하기 위해 속성을 다시 구현할 필요는 없습니다.  메타데이터 변경 내용은 기본적으로 속성 시스템에서 처리합니다. 즉, 각 클래스는 기본 클래스에서 상속된 모든 속성에 대한 개별 메타데이터를 형식별로 보유합니다.  
  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> 종속성 속성의 메타데이터를 재정의합니다.  이 종속성 속성 메타데이터를 재정의하는 것은 테마의 기본 스타일을 사용할 수 있는 컨트롤을 만드는 구현 패턴의 일부입니다.  
  
 [!code-csharp[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
 [!code-vb[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]  
  
 속성 메타데이터를 겹쳐쓰거나 얻는 방법에 대한 자세한 내용은 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 참조하십시오.  
  
<a name="setting_properties_inheritance"></a>   
### 속성 값 상속  
 요소는 개체 트리의 부모로부터 종속성 속성의 값을 상속할 수 있습니다.  
  
> [!NOTE]
>  상속 계산 시간은 성능에 영향을 줄 수 있기 때문에 속성 값 상속 동작은 모든 종속성 속성에 대해 전체적으로 사용할 수 없습니다.  일반적으로 속성 값 상속은 속성 값을 상속해야 하는 특정 시나리오에서만 허용됩니다.  종속성 속성이 상속되는지 여부는 SDK 참조서에서 해당 종속성 속성의 **종속성 속성 정보** 섹션을 통해 확인할 수 있습니다.  
  
 다음 예제에서는 바인딩을 보여 주고 앞에서 설명한 바인딩 예제에서는 보여 주지 않았던 바인딩 소스를 지정하는 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 설정합니다.  자식 개체의 모든 이후 바인딩은 소스를 지정할 필요가 없으며 부모 <xref:System.Windows.Controls.StackPanel> 개체의 <xref:System.Windows.FrameworkElement.DataContext%2A>에서 상속된 값을 사용할 수 있습니다.  또는 자식 개체가 <xref:System.Windows.Data.Binding>에서 자체 <xref:System.Windows.FrameworkElement.DataContext%2A> 또는 <xref:System.Windows.Data.Binding.Source%2A>를 직접 지정하고 바인딩의 데이터 컨텍스트에 대한 상속된 값을 의도적으로 사용하지 않도록 선택할 수 있습니다.  
  
 [!code-xml[PropertiesOvwSupport#InheritanceContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]  
  
 자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하십시오.  
  
<a name="vs2008_integration"></a>   
### WPF Designer 통합  
 종속성 속성으로 구현된 속성을 가진 사용자 지정 컨트롤에는 적절한 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] 기능을 사용할 수 있습니다.  한 가지 예를 들자면 연결된 종속성 속성 및 일반 종속성 속성을 **속성** 창에서 편집할 수 있습니다.  자세한 내용은 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
<a name="value_determination"></a>   
## 종속성 속성 값 우선 순위  
 [종속성 속성](GTMT)의 값을 가져오는 것은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템에 참여하는 다른 속성 기반 입력 중 하나를 통해 해당 속성에 설정된 값을 가져오는 것입니다.  종속성 속성 값의 우선 순위는 속성 값을 가져오는 다양한 시나리오 사이의 상호 작용을 예측하는 데 필요합니다.  
  
 다음 예제를 살펴보십시오.  이 예제에서는 모든 단추와 해당 <xref:System.Windows.Controls.Control.Background%2A> 속성에 하나의 스타일을 적용한 후 <xref:System.Windows.Controls.Control.Background%2A> 값이 로컬로 설정된 단추도 하나 지정합니다.  
  
> [!NOTE]
>  SDK 설명서에서는 종속성 속성을 설명할 때 "로컬 값" 또는 "로컬로 설정된 값"이라는 용어가 사용되는데  로컬로 설정된 값은 코드에서 개체 인스턴스에 직접 설정하거나 XAML에서 요소의 특성으로 설정한 속성 값을 의미합니다.  
  
 원칙적으로 이 예제에서 첫 번째 단추에 대해서는 속성이 두 번 설정되었지만 우선 순위가 높은 값 하나만 적용됩니다.  로컬로 설정된 값이 우선 순위가 가장 높기 때문에 첫 번째 단추의 배경에는 스타일 setter 값 대신 로컬로 설정된 값이 사용됩니다. 이 예제에는 애니메이션이 없어서 상관없지만 애니메이션을 실행할 경우에는 애니메이션의 우선 순위가 가장 높습니다.  두 번째 단추에는 로컬 값\(또는 스타일 setter보다 우선 순위가 높은 값\)이 없기 때문에 스타일 setter에서 단추의 배경을 가져옵니다.  
  
 [!code-xml[PropertiesOvwSupport#MiniPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  
  
### 종속성 속성의 우선 순위가 존재하는 이유  
 일반적으로 스타일이 항상 적용되어 개별 요소에 대해 로컬로 설정된 값도 덮어쓰도록 하면 스타일이나 요소를 일반적으로 사용하는 데 많은 문제가 생길 수 있습니다.  이러한 이유 때문에 스타일에서 가져온 값은 로컬로 설정된 값보다 우선 순위가 낮습니다.  종속성 속성 및 종속성 속성의 유효 값에 대한 자세한 목록을 보려면 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)를 참조하십시오.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소에는 종속성 속성이 아닌 다른 여러 속성도 정의되어 있습니다.  전반적으로 속성은 데이터 바인딩, 스타일 지정, 애니메이션, 기본값 지원, 상속, 연결된 속성 또는 무효화와 같이 속성 시스템에서 지원하는 시나리오 중 적어도 하나를 지원해야 하는 경우에만 종속성 속성으로 구현됩니다.  
  
<a name="dp_implement_roadmap"></a>   
## 종속성 속성에 대해 자세히 알아보기  
  
-   [연결된 속성](GTMT)은 XAML에서 특수화된 구문을 지원하는 속성의 형식입니다.  연결된 속성은 대개 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성과 일대일로 대응되지 않으며 [종속성 속성](GTMT)이 아닐 수도 있습니다.  일반적으로 [연결된 속성](GTMT)의 용도는 특정 속성이 부모 요소와 자식 요소의 클래스 멤버 목록에 공통적으로 들어 있지 않더라도 자식 요소에서 해당 속성 값을 부모 요소에 보고할 수 있도록 하는 것입니다.  연결된 속성을 사용하는 한 가지 주요 시나리오는 자식 요소가 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 표시되는 방법을 부모에 알릴 수 있도록 하는 경우입니다. 예제를 보려면 <xref:System.Windows.Controls.DockPanel.Dock%2A> 또는 <xref:System.Windows.Controls.Canvas.Left%2A>를 참조하십시오.  자세한 내용은 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)를 참조하십시오.  
  
-   구성 요소 개발자나 응용 프로그램 개발자는 고유한 [종속성 속성](GTMT)을 만들어 데이터 바인딩이나 스타일 지원 또는 무효화와 값 강제 변환과 같은 기능을 사용할 수 있습니다.  자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하십시오.  
  
-   일반적으로 종속성 속성은 인스턴스에 액세스할 수 있는 모든 호출자가 액세스하거나 최소한 검색할 수 있는 공용 속성으로 간주해야 합니다.  자세한 내용은 [종속성 속성 보안](../../../../docs/framework/wpf/advanced/dependency-property-security.md)을 참조하십시오.  
  
## 참고 항목  
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [읽기 전용 종속성 속성](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [WPF 아키텍처](../../../../docs/framework/wpf/advanced/wpf-architecture.md)