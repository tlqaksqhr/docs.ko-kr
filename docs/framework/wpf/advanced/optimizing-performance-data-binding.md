---
title: "성능 최적화: 데이터 바인딩 | Microsoft Docs"
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
  - "데이터 바인딩, 성능"
  - "데이터 바인딩, 성능"
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 성능 최적화: 데이터 바인딩
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩은 응용 프로그램에서 데이터를 표시하고 데이터와 상호 작용하는 간단하고 편리한 방법입니다.  다양한 데이터 소스에서 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 및 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]의 형태로 데이터에 요소를 바인딩할 수 있습니다.  
  
 이 항목에서는 데이터 바인딩과 관련된 성능 권장 사항을 제공합니다.  
  
   
  
<a name="HowDataBindingReferencesAreResolved"></a>   
## 데이터 바인딩 참조를 확인하는 방법  
 데이터 바인딩 성능 문제를 다루기 전에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩 엔진에서 바인딩의 개체 참조를 확인하는 방법을 살펴보는 것이 도움이 됩니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩의 소스는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체일 수 있습니다.  [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체의 속성, 하위 속성 또는 인덱서에 바인딩할 수 있습니다.  바인딩 참조는 [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] 리플렉션이나 <xref:System.ComponentModel.ICustomTypeDescriptor>를 사용하여 확인합니다.  다음은 바인딩의 개체 참조를 확인하는 세 가지 방법입니다.  
  
 첫 번째 방법에서는 리플렉션을 사용합니다.  이 경우 <xref:System.Reflection.PropertyInfo> 개체를 사용하여 속성의 특성을 검색하고 속성 메타데이터에 대한 액세스를 제공합니다.  <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스를 사용할 경우 데이터 바인딩 엔진은 이 인터페이스를 통해 속성 값에 액세스합니다.  <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스는 개체에 정적 속성 집합이 없는 경우에 특히 유용합니다.  
  
 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하거나 <xref:System.ComponentModel.TypeDescriptor>에 연결된 변경 알림을 사용하여 속성 변경 알림을 제공할 수 있습니다.  그러나 속성 변경 알림을 구현하는 더 나은 전략은 <xref:System.ComponentModel.INotifyPropertyChanged>를 사용하는 것입니다.  
  
 소스 개체가 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체이고 소스 속성이 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성이 경우 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩 엔진에서는 먼저 소스 개체에 대해 리플렉션을 사용하여 <xref:System.ComponentModel.TypeDescriptor>를 가져온 다음 <xref:System.ComponentModel.PropertyDescriptor>에 대해 쿼리해야 합니다.  이러한 일련의 리플렉션 작업은 너무 많은 시간을 소비할 수 있으므로 성능 면에서 좋지 않습니다.  
  
 개체 참조를 확인하는 두 번째 방법에서는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 소스 개체와 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성인 소스 속성을 사용합니다.  이 경우 데이터 바인딩 엔진에서는 소스 형식에 대해 직접 리플렉션을 사용하여 필요한 속성을 가져옵니다.  이 또한 최적의 방법은 아니지만 첫 번째 방법보다 작업 집합 요구 사항이 적어 비용이 적게 듭니다.  
  
 개체 참조를 확인하는 세 번째 방법에서는 <xref:System.Windows.DependencyObject>인 소스 개체와 <xref:System.Windows.DependencyProperty>인 소스 속성을 사용합니다.  이 경우 데이터 바인딩 엔진에서 리플렉션을 사용할 필요가 없습니다.  대신 속성 엔진과 데이터 바인딩 엔진이 함께 속성 참조를 독립적으로 확인합니다.  이것이 데이터 바인딩에서 사용되는 개체 참조를 확인하는 최적의 방법입니다.  
  
 아래 표에서는 이러한 세 가지 방법을 사용하여 <xref:System.Windows.Controls.TextBlock> 요소 1000개의 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성에 데이터를 바인딩할 때 속도를 비교합니다.  
  
|**TextBlock의 Text 속성을 다음에 바인딩**|**바인딩 시간\(ms\)**|**바인딩 시간을 포함한 렌더링 시간\(ms\)**|  
|-------------------------------------|----------------------|----------------------------------|  
|[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체의 속성|115|314|  
|<xref:System.ComponentModel.INotifyPropertyChanged>를 구현하는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체의 속성|115|305|  
|<xref:System.Windows.DependencyObject>의 <xref:System.Windows.DependencyProperty>|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## 대형 CLR 개체에 바인딩  
 수천 개의 속성이 포함된 단일 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체에 데이터 바인딩하는 경우 성능에 상당한 영향을 미칩니다.  이 단일 개체를 적은 수의 속성을 포함하는 여러 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체로 나누어 이러한 영향을 최소화할 수 있습니다.  아래 표에서는 하나의 큰 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체와 여러 개의 작은 개체에 데이터 바인딩할 때의 바인딩 시간과 렌더링 시간을 비교해서 보여 줍니다.  
  
|**1000개의 TextBlock 개체를 다음에 바인딩**|**바인딩 시간\(ms\)**|**바인딩 시간을 포함한 렌더링 시간\(ms\)**|  
|--------------------------------------|----------------------|----------------------------------|  
|1000개의 속성이 있는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체|950|1200|  
|하나의 속성이 있는 1000개의 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## ItemsSource에 바인딩  
 <xref:System.Windows.Controls.ListBox>에 표시할 직원 목록이 저장된 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> 개체가 있다고 가정합니다.  이 두 개체 간의 대응 관계를 만들려면 직원 목록을 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성에 바인딩할 수 있습니다.  그런데 그룹에 새 직원이 입사했다고 가정합니다.  이 새 직원을 바인딩된 <xref:System.Windows.Controls.ListBox> 값에 삽입하려는 경우 이 직원을 직원 목록에 추가하기만 하면 데이터 바인딩 엔진에서 이 변경 사항을 자동으로 인식할 것으로 생각할 수도 있습니다.  이 가정은 잘못된 것입니다. 실제로는 변경 사항이 <xref:System.Windows.Controls.ListBox>에 자동으로 반영되지 않습니다.  이는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> 개체에서 컬렉션 변경 이벤트를 자동으로 발생시키지 않기 때문입니다.  <xref:System.Windows.Controls.ListBox>에서 변경 내용을 반영하게 하려면 직원 목록을 새로 만들어 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성에 다시 연결해야 합니다.  이 솔루션은 효과는 있지만 성능에 큰 영향을 줍니다.  <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 다시 할당할 때마다 <xref:System.Windows.Controls.ListBox>에서는 먼저 이전 항목을 버리고 전체 목록을 다시 생성합니다.  <xref:System.Windows.Controls.ListBox>가 복잡한 <xref:System.Windows.DataTemplate>에 매핑되어 있는 경우에는 성능 영향이 더 커집니다.  
  
 이 문제에 대한 효율적인 솔루션은 직원 목록을 <xref:System.Collections.ObjectModel.ObservableCollection%601>으로 만드는 것입니다.  <xref:System.Collections.ObjectModel.ObservableCollection%601> 개체에서는 데이터 바인딩 엔진에서 수신할 수 있는 변경 알림을 발생시킵니다.  이 이벤트는 전체 목록을 다시 생성하지 않고 <xref:System.Windows.Controls.ItemsControl>의 항목을 추가하거나 제거합니다.  
  
 아래 표에서는 한 항목을 추가할 때 <xref:System.Windows.Controls.ListBox> 업데이트에 걸리는 시간을 보여 줍니다\(UI 시각화 해제한 경우\).  첫 행의 숫자는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> 개체를 <xref:System.Windows.Controls.ListBox> 요소의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>에 바인딩하는 경우 경과된 시간을 나타냅니다.  둘째 행의 숫자는 <xref:System.Collections.ObjectModel.ObservableCollection%601>을 <xref:System.Windows.Controls.ListBox> 요소의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>에 바인딩하는 경우 경과된 시간을 나타냅니다.  <xref:System.Collections.ObjectModel.ObservableCollection%601> 데이터 바인딩 전략을 사용하면 상당한 시간이 절약됨을 알 수 있습니다.  
  
|**ItemsSource를 다음에 데이터 바인딩**|**1개 항목의 업데이트 시간\(ms\)**|  
|----------------------------------|------------------------------|  
|[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> 개체|1656|  
|<xref:System.Collections.ObjectModel.ObservableCollection%601> 개체|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## IList를 IEnumerable이 아니라 ItemsControl에 바인딩  
 <xref:System.Windows.Controls.ItemsControl> 개체에 <xref:System.Collections.Generic.IList%601> 또는 <xref:System.Collections.IEnumerable> 중에서 무엇을 바인딩할지 선택해야 하는 경우 <xref:System.Collections.Generic.IList%601> 개체를 선택하는 것이 좋습니다.  <xref:System.Collections.IEnumerable>을 <xref:System.Windows.Controls.ItemsControl>에 바인딩하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 래퍼 <xref:System.Collections.Generic.IList%601> 개체를 만듭니다. 따라서 두 번째 개체의 불필요한 오버헤드로 인해 성능에 영향을 줍니다.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## 데이터 바인딩만을 위해 CLR 개체를 XML로 변환하지 마십시오  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 콘텐츠에 데이터바인딩할 수 있지만 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 콘텐츠의 데이터 바인딩은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체의 데이터 바인딩보다 느립니다.  데이터 바인딩만을 위해서는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 데이터를 XML로 변환하지 마십시오.  
  
## 참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [연습: WPF 응용 프로그램에서 응용 프로그램 데이터 캐싱](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)