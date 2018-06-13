---
title: 바인딩 소스 개요
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 2df2cd11-6aac-4bdf-ab7b-ea5f464cd5ca
ms.openlocfilehash: bd397bfad26863e302b0f69c3aa57155f0d62b79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558137"
---
# <a name="binding-sources-overview"></a>바인딩 소스 개요
데이터 바인딩에서 바인딩 소스 개체는 데이터를 가져오는 개체를 의미합니다. 이 항목에서는 바인딩 소스로 사용할 수 있는 개체 형식에 대해 설명합니다.  
  
  
  
<a name="binding_sources"></a>   
## <a name="binding-source-types"></a>바인딩 소스 형식  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩은 다음 바인딩 소스 형식을 지원합니다.  
  
|바인딩 소스|설명|  
|--------------------|-----------------|  
|[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체|모든 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체의 공용 속성, 하위 속성 및 인덱서에 바인딩할 수 있습니다. 바인딩 엔진은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 리플렉션을 사용하여 속성의 값을 가져옵니다. 또한 구현 하는 개체 <xref:System.ComponentModel.ICustomTypeDescriptor> 를 등록 한 또는 <xref:System.ComponentModel.TypeDescriptionProvider> 바인딩 엔진 에서도 작동 합니다.<br /><br /> 바인딩 소스로 사용할 수 있는 클래스를 구현하는 방법은 이 항목 뒷부분의 [바인딩 소스에 대한 클래스 구현](#classes)을 참조하세요.|  
|동적 개체|구현 하는 개체의 사용 가능한 속성 및 인덱서를 바인딩할 수 있습니다는 <xref:System.Dynamic.IDynamicMetaObjectProvider> 인터페이스입니다. 코드의 멤버에 액세스할 수 있는 경우 바인딩할 수 있습니다. 예를 들어 동적 개체를 사용하여 `someObjet.AProperty`를 통해 코드의 멤버에 액세스할 수 있는 경우 바인딩 경로를 `AProperty`로 설정하여 바인딩할 수 있습니다.|  
|[!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] 개체|바인딩할 수 [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)] 와 같은 개체 <xref:System.Data.DataTable>합니다. [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)] <xref:System.Data.DataView> 구현 하는 <xref:System.ComponentModel.IBindingList> 바인딩 엔진에 대 한 수신 대기 하는 변경 알림을 제공 하는 인터페이스입니다.|  
|[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 개체|바인딩할 하 고 실행할 수 있습니다 `XPath` 에 대 한 쿼리는 <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlDocument>, 또는 <xref:System.Xml.XmlElement>합니다. 에 액세스 하는 편리한 방법은 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 바인딩 소스에 태그를 사용 하는 것는 <xref:System.Windows.Data.XmlDataProvider> 개체입니다. 자세한 내용은 [XMLDataProvider 및 XPath 쿼리를 사용하여 XML 데이터에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)을 참조하세요.<br /><br /> 바인딩할 수 있습니다는 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument>, 또는 LINQ to XML 사용 하 여 이러한 종류의 개체에서 실행 하는 쿼리 결과에 바인딩합니다. LINQ to XML 사용 하 여 바인딩 소스 태그에 있는 XML 데이터에 액세스 하는 편리한 방법을 사용 하는 것는 <xref:System.Windows.Data.ObjectDataProvider> 개체입니다. 자세한 내용은 [XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)을 참조하세요.|  
|<xref:System.Windows.DependencyObject> 개체|모든 종속성 속성에 바인딩할 수 <xref:System.Windows.DependencyObject>합니다. 예제는 [두 컨트롤의 속성 바인딩](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md)을 참조하세요.|  
  
<a name="classes"></a>   
## <a name="implementing-a-class-for-the-binding-source"></a>바인딩 소스에 대한 클래스 구현  
 고유한 바인딩 소스를 만들 수 있습니다. 이 섹션에서는 바인딩 소스로 사용할 클래스를 구현하는 경우 알아야 할 내용을 설명합니다.  
  
### <a name="providing-change-notifications"></a>변경 알림 제공  
 중 하나를 사용 하는 경우 <xref:System.Windows.Data.BindingMode.OneWay> 또는 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 (하려고 하기 때문에 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 바인딩 소스 속성을 동적으로 변경 될 때 업데이트 하려면)를 적절 한 속성 변경 알림 메커니즘을 구현 해야 합니다. 에 대 한 권장 되는 메커니즘은는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 또는 동적 클래스를 구현 하는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스입니다. 자세한 내용은 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조하세요.  
  
 만드는 경우는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 구현 하지 않는 개체 <xref:System.ComponentModel.INotifyPropertyChanged>, 된 바인딩에 사용 되는 데이터 현재 유지 되는지 확인 하려면 해당 하는 알림 시스템에 대 한 정리 해야 합니다. 변경 알림의 각 속성에 대해 `PropertyChanged` 패턴을 지원하여 변경 알림을 제공할 수 있습니다. 이 패턴을 지원하려면 각 속성에 대해 *PropertyName*Changed 이벤트를 정의합니다. 여기서 *PropertyName*은 속성의 이름입니다. 속성이 변경될 때마다 이 이벤트를 발생시킵니다.  
  
 바인딩 소스가 이러한 알림 메커니즘 중 하나를 구현하는 경우 대상 업데이트가 자동으로 수행됩니다. 사용할 수 있는 옵션이 있는 바인딩 소스 적절 한 속성을 제공 하지 않는 어떤 이유로 변경 된 경우 알림은 <xref:System.Windows.Data.BindingExpression.UpdateTarget%2A> 메서드를 명시적으로 대상 속성을 업데이트 합니다.  
  
### <a name="other-characteristics"></a>기타 특성  
 다음은 고려해야 할 기타 중요 사항의 목록입니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 개체를 만들려는 경우 클래스에 기본 생성자가 있어야 합니다. 일부 [!INCLUDE[TLA2#tla_net](../../../../includes/tla2sharptla-net-md.md)] C#과 같은 언어 기본 생성자는 만들 수 있습니다.  
  
-   바인딩의 바인딩 소스 속성으로 사용하는 속성은 클래스의 공용 속성이어야 합니다. 명시적으로 정의된 인터페이스 속성은 바인딩 용도로 액세스할 수 없으며, 기본 구현이 없는 보호, 전용, 내부 또는 가상 속성이 될 수 없습니다.  
  
-   공용 필드에 바인딩할 수 없습니다.  
  
-   클래스에서 선언된 속성의 형식은 바인딩에 전달되는 형식입니다. 그러나 궁극적으로 바인딩에서 사용되는 형식은 바인딩 소스 속성의 형식이 아니라 바인딩 대상 속성의 형식에 따라 달라집니다. 형식이 다른 경우 사용자 지정 속성이 처음 바인딩에 전달되는 방법을 처리하는 변환기를 작성하는 것이 좋습니다. 자세한 내용은 <xref:System.Windows.Data.IValueConverter>을 참조하세요.  
  
<a name="objects"></a>   
## <a name="using-entire-objects-as-a-binding-source"></a>전체 개체를 바인딩 소스로 사용  
 전체 개체를 바인딩 소스로 사용할 수 있습니다. 사용 하 여 바인딩 소스를 지정할 수 있습니다는 <xref:System.Windows.Data.Binding.Source%2A> 또는 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성을 선택한 다음 빈 바인딩 선언 제공: `{Binding}`합니다. 이 방법이 유용한 시나리오의 예로는 문자열 형식 개체에 대한 바인딩, 관심 있는 속성이 여러 개 포함된 개체에 대한 바인딩 또는 컬렉션 개체에 대한 바인딩이 있습니다. 전체 컬렉션 개체에 대한 바인딩의 예제는 [계층적 데이터에 마스터-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)을 참조하세요.  
  
 바인딩된 대상 속성에서 데이터가 의미를 가지려면 사용자 지정 논리를 적용해야 할 수 있습니다. 사용자 지정 논리는 (기본 형식 변환이 존재 하지 않음) 하는 경우 사용자 지정 변환기의 형태일에서 수 있습니다 또는 <xref:System.Windows.DataTemplate>합니다. 변환기에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)의 데이터 변환 섹션을 참조하세요. 데이터 템플릿에 대한 자세한 내용은 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)를 참조하세요.  
  
<a name="collections"></a>   
## <a name="using-collection-objects-as-a-binding-source"></a>컬렉션 개체를 바인딩 소스로 사용  
 바인딩 소스로 사용하려는 개체가 사용자 지정 개체의 컬렉션인 경우가 종종 있습니다. 각 개체는 반복되는 바인딩의 단일 인스턴스에 대한 소스로 사용됩니다. 예를 들어 `CustomerOrder` 개체로 구성된 `CustomerOrders` 컬렉션이 있고, 응용 프로그램이 컬렉션에 대해 주문 수와 각 주문에 포함된 데이터를 반복적으로 확인할 수 있습니다.  
  
 구현 하는 컬렉션을 열거할 수는 <xref:System.Collections.IEnumerable> 인터페이스입니다. 그러나 삽입 또는 삭제 컬렉션에서 업데이트할 수 있도록 동적 바인딩을 설정 하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컬렉션은 자동으로 구현 해야 합니다는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스입니다. 이 인터페이스는 기본 컬렉션이 변경될 때마다 발생해야 하는 이벤트를 노출합니다.  
  
 <xref:System.Collections.ObjectModel.ObservableCollection%601> 클래스를 노출 하는 데이터 컬렉션의 기본 제공 구현인는 <xref:System.Collections.Specialized.INotifyCollectionChanged> 인터페이스입니다. 컬렉션 내의 개별 데이터 개체는 이전 섹션에 설명된 요구 사항을 충족해야 합니다. 예제는 [ObservableCollection 만들기 및 바인딩](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)을 참조하세요. 고유한 컬렉션을 구현 하기 전에 사용 하 여 것이 좋습니다 <xref:System.Collections.ObjectModel.ObservableCollection%601> 또는 같은 기존 컬렉션 중 하나가 클래스 <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, 및 <xref:System.ComponentModel.BindingList%601>, 다양 한 기타.  
  
 WPF는 컬렉션에 직접 바인딩되지 않습니다. 바인딩 소스로 컬렉션을 지정하면 WPF가 실제로 컬렉션의 기본 뷰에 바인딩됩니다. 기본 뷰에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.  
  
 고급 시나리오에 있고 컬렉션을 직접 구현 하려는 경우 사용 하 여 고려는 <xref:System.Collections.IList> 인터페이스입니다. <xref:System.Collections.IList> 성능을 향상 시킬 수 있는 인덱스에서 개별적으로 액세스할 수 있는 개체의 제네릭이 아닌 컬렉션을 제공 합니다.  
  
<a name="permissions"></a>   
## <a name="permission-requirements-in-data-binding"></a>데이터 바인딩의 사용 권한 요구 사항  
 데이터 바인딩 시 응용 프로그램의 신뢰 수준을 고려해야 합니다. 다음 표에는 완전 신뢰 또는 부분 신뢰 상태에서 실행되는 응용 프로그램에 바인딩할 수 있는 속성 형식이 요약되어 있습니다.  
  
|속성 형식<br /><br /> (모든 액세스 한정자)|동적 개체 속성|동적 개체 속성|CLR 속성|CLR 속성|종속성 속성|종속성 속성|  
|------------------------------------------------|-----------------------------|-----------------------------|------------------|------------------|-------------------------|-------------------------|  
|**신뢰 수준**|**완전 신뢰**|**부분 신뢰**|**완전 신뢰**|**부분 신뢰**|**완전 신뢰**|**부분 신뢰**|  
|Public 클래스|예|예|예|예|예|예|  
|Public이 아닌 클래스|예|아니요|예|아니요|예|예|  
  
 이 표에서는 데이터 바인딩의 사용 권한 요구 사항에 대한 다음 중요 사항을 설명합니다.  
  
-   [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성의 경우 바인딩 엔진이 리플렉션을 사용하여 바인딩 소스 속성에 액세스할 수 있는 한 데이터 바인딩이 작동됩니다. 그렇지 않은 경우 바인딩 엔진이 속성을 찾을 수 없다는 경고를 생성하고 대체 값 또는 기본값(사용 가능한 경우)을 사용합니다.  
  
-   컴파일 타임 또는 런타임에 정의된 동적 개체의 속성에 바인딩할 수 있습니다.  
  
-   항상 종속성 속성에 바인딩할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 바인딩에 대한 사용 권한 요구 사항은 비슷합니다. 부분 신뢰 샌드박스에서 <xref:System.Windows.Data.XmlDataProvider> 지정 된 데이터에 액세스할 수 있는 권한이 없는 경우 실패 합니다.  
  
 익명 형식 개체는 내부 개체입니다. 완전 신뢰 상태에서 실행 중인 경우에만 익명 형식의 속성에 바인딩할 수 있습니다. 익명 형식에 대한 자세한 내용은 [익명 형식(C# 프로그래밍 가이드)](~/docs/csharp/programming-guide/classes-and-structs/anonymous-types.md) 또는 [익명 형식(Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)(Visual Basic)을 참조하세요.  
  
 부분 신뢰 보안에 대한 자세한 내용은 [WPF 부분 신뢰 보안](../../../../docs/framework/wpf/wpf-partial-trust-security.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.ObjectDataProvider>  
 <xref:System.Windows.Data.XmlDataProvider>  
 [바인딩 소스 지정](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [LINQ to XML로 WPF 데이터 바인딩 개요](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
