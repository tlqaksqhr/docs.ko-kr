---
title: "바인딩 소스 개요 | Microsoft Docs"
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
  - "데이터 바인딩, 바인딩 소스"
  - "바인딩 소스"
  - "데이터 바인딩(data binding), 바인딩 소스(binding source)"
ms.assetid: 2df2cd11-6aac-4bdf-ab7b-ea5f464cd5ca
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# 바인딩 소스 개요
데이터 바인딩에서 [바인딩 소스](GTMT) 개체는 데이터를 가져온 개체를 참조합니다.  이 항목에서는 바인딩 소스로 사용할 수 있는 개체 형식에 대해 설명합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="binding_sources"></a>   
## 바인딩 소스 형식  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩에서는 다음과 같은 [바인딩 소스](GTMT) 형식을 지원합니다.  
  
|바인딩 소스|설명|  
|------------|--------|  
|[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체|모든 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체의 공용 속성, 하위 속성 및 인덱서를 바인딩할 수 있습니다.  바인딩 엔진에서는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 리플렉션을 사용하여 속성 값을 가져옵니다.  또는 <xref:System.ComponentModel.ICustomTypeDescriptor>를 구현하거나 <xref:System.ComponentModel.TypeDescriptionProvider>를 등록한 개체를 바인딩 엔진에서 사용할 수도 있습니다.<br /><br /> 바인딩 소스 개체로 사용할 수 있는 클래스를 구현하는 방법에 대한 자세한 내용은 이 항목의 뒷부분에 나오는 [바인딩 소스 클래스 구현](#classes)을 참조하십시오.|  
|동적 개체|<xref:System.Dynamic.IDynamicMetaObjectProvider> 인터페이스를 구현하는 개체의 사용 가능한 속성 및 인덱서에 바인딩할 수 있습니다.  코드에서 멤버에 액세스할 수 있으면 해당 멤버에 바인딩할 수 있습니다.  예를 들어 동적 개체를 사용할 경우 코드에서 `someObjet.AProperty`를 통해 멤버에 액세스할 수 있으면 `AProperty`에 대한 바인딩 경로를 설정하여 해당 멤버에 바인딩할 수 있습니다.|  
|[!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] 개체|<xref:System.Data.DataTable>과 같은 [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)] 개체에 바인딩할 수 있습니다. [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)] <xref:System.Data.DataView>는 바인딩 엔진이 수신하는 변경 알림을 제공하는 <xref:System.ComponentModel.IBindingList> 인터페이스를 구현합니다.|  
|[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 개체|<xref:System.Xml.XmlNode>, <xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XmlElement>에서 `XPath` 쿼리를 바인딩하고 실행할 수 있습니다.  태그에서 [바인딩 소스](GTMT)인 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 간편하게 액세스할 수 있는 방법은 <xref:System.Windows.Data.XmlDataProvider> 개체를 사용하는 것입니다.  자세한 내용은 [XMLData Provider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)을 참조하십시오.<br /><br /> 또는 <xref:System.Xml.Linq.XElement>나 <xref:System.Xml.Linq.XDocument>에 바인딩하거나, LINQ to XML을 사용하여 이러한 형식의 개체에 대해 실행한 쿼리 결과에 바인딩할 수도 있습니다.  LINQ to XML을 사용하여 태그에서 바인딩 소스인 XML 데이터에 간편하게 액세스하려면 <xref:System.Windows.Data.ObjectDataProvider> 개체를 사용하는 것이 좋습니다.  자세한 내용은 [XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)을 참조하십시오.|  
|<xref:System.Windows.DependencyObject> 개체|모든 <xref:System.Windows.DependencyObject>의 [종속성 속성](GTMT)에 바인딩할 수 있습니다.  예제를 보려면 [두 컨트롤의 속성 바인딩](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md)을 참조하십시오.|  
  
<a name="classes"></a>   
## 바인딩 소스 클래스 구현  
 사용자의 고유한 바인딩 소스를 만들 수 있습니다.  이 단원에서는 바인딩 소스 개체로 사용할 클래스를 구현하는 경우 알아야 하는 사항에 대해 설명합니다.  
  
### 변경 알림 제공  
 <xref:System.Windows.Data.BindingMode> 또는 <xref:System.Windows.Data.BindingMode> 바인딩을 사용하는 경우\(바인딩 소스 속성이 동적으로 변경될 때 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 업데이트하려는 경우\) 적절한 속성 변경 알림 메커니즘을 구현해야 합니다.  권장 메커니즘은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 또는 동적 클래스로 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하는 것입니다.  자세한 내용은 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조하십시오.  
  
 <xref:System.ComponentModel.INotifyPropertyChanged>를 구현하지 않는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체를 만들면 바인딩에 사용되는 데이터를 최신 상태로 유지하는 고유한 알림 시스템을 배치해야 합니다.  변경 알림을 제공할 각 속성에 대해 `PropertyChanged` 패턴을 지원하여 변경 알림을 제공할 수 있습니다.  이 패턴을 지원하려면 각 속성에 대해 *PropertyName*Changed 이벤트를 정의해야 합니다. 여기서 *PropertyName*은 속성의 이름입니다.  속성이 변경될 때마다 이 이벤트를 발생시킵니다.  
  
 바인딩 소스가 이러한 알림 메커니즘 중 하나를 구현하면 대상이 자동으로 업데이트됩니다.  하지만 어떤 이유로 바인딩 소스에서 올바른 속성 변경 알림을 제공하지 않는 경우 <xref:System.Windows.Data.BindingExpression.UpdateTarget%2A> 메서드를 사용하여 대상 속성을 명시적으로 업데이트할 수도 있습니다.  
  
### 기타 특성  
 다음 목록에서는 다른 중요한 주의 사항에 대해 설명합니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 개체를 만들려면 클래스에 기본 생성자가 있어야 합니다.  [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 같은 일부 [!INCLUDE[TLA2#tla_net](../../../../includes/tla2sharptla-net-md.md)] 언어에서는 기본 생성자를 제공합니다.  
  
-   바인딩의 바인딩 소스 속성으로 사용할 속성은 클래스의 공용 속성이어야 합니다.  명시적으로 정의된 인터페이스 속성은 바인딩 용도로 액세스할 수 없으며 기본 구현이 없는 보호, 전용 및 내부 또는 가상 속성도 바인딩 용도로 액세스할 수 없습니다.  
  
-   공용 필드에는 바인딩할 수 없습니다.  
  
-   클래스에 선언된 속성의 형식이 바인딩에 전달되는 형식입니다.  하지만 바인딩에 최종적으로 사용되는 형식은 바인딩 소스 속성의 형식이 아니라 [바인딩 대상](GTMT) 속성의 형식에 따라 달라집니다.  형식에 차이가 있는 경우에는 사용자 지정 속성이 처음 바인딩에 전달되는 방식을 처리하는 변환기를 작성할 수 있습니다.  자세한 내용은 <xref:System.Windows.Data.IValueConverter>를 참조하십시오.  
  
<a name="objects"></a>   
## 전체 개체를 바인딩 소스로 사용  
 전체 개체를 바인딩 소스로 사용할 수 있습니다.  <xref:System.Windows.Data.Binding.Source%2A> 또는 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 사용하여 바인딩 소스를 지정한 다음 빈 바인딩 선언\(`{Binding}`\)을 제공하면 됩니다.  이 기능이 유용한 시나리오로는 문자열 형식의 개체에 바인딩하거나, 관심 속성이 여러 개인 개체에 바인딩하거나, 컬렉션 개체에 바인딩하는 경우를 들 수 있습니다.  전체 컬렉션 개체에 바인딩하는 경우의 예제를 보려면 [계층적 데이터에 마스터\-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)을 참조하십시오.  
  
 바인딩된 대상 속성에서 데이터가 의미를 갖게 하기 위해 사용자 지정 논리를 적용해야 하는 경우가 있습니다.  사용자 지정 논리는 사용자 지정 변환기\(기본 형식 변환기가 없는 경우\)의 형태나 <xref:System.Windows.DataTemplate>이 될 수 있습니다.  변환기에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)의 데이터 변환 단원을 참조하십시오.  데이터 템플릿에 대한 자세한 내용은 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)를 참조하십시오.  
  
<a name="collections"></a>   
## 컬렉션 개체를 바인딩 소스로 사용  
 바인딩 소스로 사용하려는 개체가 사용자 지정 개체 컬렉션인 경우가 종종 있습니다.  이 경우 각 개체는 반복되는 바인딩의 특정 인스턴스에 대한 소스로 사용됩니다.  예를 들어 `CustomerOrder` 개체로 구성된 `CustomerOrders` 컬렉션이 있을 수 있습니다. 이 경우 응용 프로그램에서는 해당 컬렉션을 반복 처리하여 주문의 수와 각 주문에 포함된 데이터를 확인할 수 있습니다.  
  
 <xref:System.Collections.IEnumerable> 인터페이스를 구현하는 모든 컬렉션을 열거할 수 있습니다.  그러나 컬렉션에서 삽입이나 삭제를 수행할 때 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]가 자동으로 업데이트되도록 동적 바인딩을 설정하려면 컬렉션에서 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 구현해야 합니다.  이 인터페이스는 내부 컬렉션이 변경될 때마다 발생해야 하는 이벤트를 노출합니다.  
  
 <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스를 노출하는 데이터 컬렉션에 대한 기본 제공 구현입니다.  컬렉션 내의 개별 데이터 개체는 앞의 단원에 설명된 요구 사항에 맞아야 합니다.  예제를 보려면 [ObservableCollection 만들기 및 바인딩](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)을 참조하십시오.  컬렉션을 직접 구현하는 대신 <xref:System.Collections.ObjectModel.ObservableCollection%601>을 사용하거나 <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601> 및 <xref:System.ComponentModel.BindingList%601>를 비롯한 기존 컬렉션 클래스 중 하나를 사용하는 것이 좋습니다.  
  
 WPF는 컬렉션에 직접 바인딩되지 않습니다.  바인딩 소스로 컬렉션을 지정하면 WPF는 컬렉션의 기본 뷰에 바인딩됩니다.  기본 뷰에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
 고급 시나리오에 따라 고유한 컬렉션을 구현하려면 <xref:System.Collections.IList> 인터페이스를 사용하는 것이 좋습니다.  <xref:System.Collections.IList>는 인덱스에 따라 개별적으로 액세스할 수 있는 개체의 제네릭이 아닌 컬렉션을 제공하여 성능을 향상시킬 수 있습니다.  
  
<a name="permissions"></a>   
## 데이터 바인딩의 권한 요구 사항  
 데이터 바인딩을 수행할 경우 응용 프로그램의 신뢰 수준을 고려해야 합니다.  다음 표에서는 완전 신뢰 또는 부분 신뢰 상황에서 실행되는 응용 프로그램에 바인딩할 수 있는 속성 형식을 요약하여 보여 줍니다.  
  
|속성 형식<br /><br /> \(모든 액세스 한정자\)|동적 개체 속성|동적 개체 속성|CLR 속성|CLR 속성|종속성 속성|종속성 속성|  
|------------------------------|--------------|--------------|------------|------------|------------|------------|  
|**신뢰 수준**|**완전 신뢰**|**부분 신뢰**|**완전 신뢰**|**부분 신뢰**|**완전 신뢰**|**부분 신뢰**|  
|Public 클래스|예|예|예|예|예|예|  
|비공용 클래스|예|아니요|예|아니요|예|예|  
  
 이 표에서는 다음과 같이 데이터 바인딩의 중요한 권한 요구 사항에 대해 설명합니다.  
  
-   [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성의 경우 데이터 바인딩은 바인딩 엔진에서 리플렉션을 사용하여 바인딩 소스 속성에 액세스할 수 있는 한은 계속해서 작동합니다.  그렇지 않은 경우에는 바인딩 엔진에서 속성을 찾을 수 없어 대체\(fallback\) 값이나 기본값\(사용할 수 있는 경우\)을 사용한다는 경고 메시지가 표시됩니다.  
  
-   컴파일 타임 또는 런타임에 정의되는 동적 개체의 속성에 바인딩할 수 있습니다.  
  
-   [종속성 속성](GTMT)에는 항상 바인딩할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 바인딩에 대한 권한 요구 사항은 데이터 바인딩에 대한 권한 요구 사항과 유사합니다. 부분 신뢰 샌드박스에서 지정된 데이터에 액세스할 수 있는 권한이 없으면 <xref:System.Windows.Data.XmlDataProvider>가 실패합니다.  
  
 무명 형식의 개체는 내부 개체입니다.  완전 신뢰 수준에서 실행되는 경우에만 무명 형식의 속성에 바인딩할 수 있습니다.  익명 형식에 대한 자세한 내용은 [익명 형식\(C\# 프로그래밍 가이드\)](../Topic/Anonymous%20Types%20\(C%23%20Programming%20Guide\).md) 또는 [익명 형식\(Visual Basic\)](../Topic/Anonymous%20Types%20\(Visual%20Basic\).md)\(Visual Basic\)을 참조하십시오.  
  
 부분 신뢰 보안에 대한 자세한 내용은 [WPF 부분 신뢰 보안](../../../../docs/framework/wpf/wpf-partial-trust-security.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Data.ObjectDataProvider>   
 <xref:System.Windows.Data.XmlDataProvider>   
 [바인딩 소스 지정](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [LINQ to XML을 사용한 WPF 데이터 바인딩 개요](../Topic/WPF%20Data%20Binding%20with%20LINQ%20to%20XML%20Overview.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)