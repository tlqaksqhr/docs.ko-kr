---
title: '성능 최적화: 데이터 바인딩'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4b21089ea3f3aef8a934c78187b30f2576b8d39b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="optimizing-performance-data-binding"></a>성능 최적화: 데이터 바인딩
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩은 응용 프로그램이 데이터를 제공하고 상호 작용할 수 있는 간단하고 일관된 방법을 제공합니다. 다양한 데이터 소스에서 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 및 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]의 형태로 데이터에 요소를 바인딩할 수 있습니다.  
  
 이 항목에서는 데이터 바인딩과 관련된 성능 권장 사항을 제공합니다.  
  

  
<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>데이터 바인딩 참조를 확인하는 방법  
 데이터 바인딩 성능 문제를 다루기 전에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩 엔진에서 바인딩의 개체 참조를 확인하는 방법을 살펴보는 것이 좋습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩의 소스는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체일 수 있습니다. [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체의 속성, 하위 속성 또는 인덱서에 바인딩할 수 있습니다. Microsoft.NET Framework 리플렉션 중 하나를 사용 하 여 바인딩 참조는 확인 또는 <xref:System.ComponentModel.ICustomTypeDescriptor>합니다. 다음은 바인딩의 개체 참조를 확인하는 세 가지 방법입니다.  
  
 첫 번째 방법에서는 리플렉션을 사용합니다. 이 경우에 <xref:System.Reflection.PropertyInfo> 개체 속성의 특성을 검색 하는 데 사용 하 고 속성 메타 데이터에 대 한 액세스를 제공 합니다. 사용 하는 경우는 <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스, 데이터 바인딩 엔진은이 인터페이스를 속성 값에 액세스 합니다. <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스 개체에는 정적 속성 집합이 없는 경우에 특히 유용 합니다.  
  
 구현 하거나 속성 변경 알림의 제공할 수 있습니다는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스 또는 연결 된 변경 알림을 사용 하 여는 <xref:System.ComponentModel.TypeDescriptor>합니다. 속성 변경 알림을 구현 하기 위한 기본 전략은 사용 하는 반면 <xref:System.ComponentModel.INotifyPropertyChanged>합니다.  
  
 소스 개체가 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 및 source 속성은 한 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성을는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 먼저 리플렉션을 사용 하는 원본 개체를 가져오려는 데이터 바인딩 엔진에는 <xref:System.ComponentModel.TypeDescriptor>, 고 다음에 대 한 쿼리는 <xref:System.ComponentModel.PropertyDescriptor>합니다. 이러한 일련의 리플렉션 작업은 너무 많은 시간을 소비할 수 있으므로 성능 면에서 좋지 않습니다.  
  
 개체 참조를 확인 하기 위한 두 번째 방법은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 구현 하는 원본 개체는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스와 소스 속성을는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성입니다. 이 경우 데이터 바인딩 엔진에서는 소스 형식에 대해 직접 리플렉션을 사용하여 필요한 속성을 가져옵니다. 이 또한 최적의 방법은 아니지만 첫 번째 방법보다 작업 집합 요구 사항이 적어 비용이 적게 듭니다.  
  
 개체 참조를 확인 하기 위한 세 번째 방법은 소스 개체는 <xref:System.Windows.DependencyObject> 및 소스 속성을는 <xref:System.Windows.DependencyProperty>합니다. 이 경우 데이터 바인딩 엔진에서 리플렉션을 사용할 필요가 없습니다. 대신 속성 엔진과 데이터 바인딩 엔진이 함께 속성 참조를 독립적으로 확인합니다. 이것이 데이터 바인딩에서 사용되는 개체 참조를 확인하는 최적의 방법입니다.  
  
 아래 표에서 데이터 바인딩의 속도 비교는 <xref:System.Windows.Controls.TextBlock.Text%2A> 1 천 속성 <xref:System.Windows.Controls.TextBlock> 이러한 세 가지 방법을 사용 하 여 요소입니다.  
  
|**TextBlock의 Text 속성 바인딩 대상**|**바인딩 시간(ms)**|**렌더링 시간 -- 바인딩 시간 포함(ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체의 속성|115|314|  
|속성에는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 구현 하는 개체 <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|에 <xref:System.Windows.DependencyProperty> 의 <xref:System.Windows.DependencyObject>합니다.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>대형 CLR 개체에 바인딩  
 수천 개의 속성이 포함된 단일 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체에 데이터 바인딩하는 경우 성능에 상당한 영향을 미칩니다. 이 단일 개체를 적은 수의 속성을 포함하는 여러 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체로 나누어 이러한 영향을 최소화할 수 있습니다. 아래 표에서는 하나의 큰 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체와 여러 개의 작은 개체에 데이터 바인딩할 때의 바인딩 시간과 렌더링 시간을 비교해서 보여 줍니다.  
  
|**1000개의 TextBlock 개체 데이터 바인딩 대상**|**바인딩 시간(ms)**|**렌더링 시간 -- 바인딩 시간 포함(ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|1000개의 속성이 있는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체|950|1200|  
|하나의 속성이 있는 1000개의 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>ItemsSource에 바인딩  
 있는 경우를 생각해 볼는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> 에 표시 하려고 하는 직원의 목록을 보유 하는 개체는 <xref:System.Windows.Controls.ListBox>합니다. 이 두 개체 간의 관계를 만들려면 직원 목록에 바인딩할 수 있습니다는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 속성은 <xref:System.Windows.Controls.ListBox>합니다. 그런데 그룹에 새 직원이 가입했다고 가정합니다. 바인딩된에이 새 사용자를 삽입 하려면를으로 생각할 수 있습니다 <xref:System.Windows.Controls.ListBox> 값을 단순히 직원 목록에이 사용자를 추가 하 고이 변경 사항을 자동으로 데이터 바인딩 엔진에서 인식할 수 있습니다. 해당 가정은 잘못; 실제로 평면은에 변경 내용을 반영 되지 것입니다는 <xref:System.Windows.Controls.ListBox> 자동으로 합니다. 때문에 이것이 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> 개체 컬렉션 변경 이벤트를 자동으로 발생 하지 않습니다. 가져오려면는 <xref:System.Windows.Controls.ListBox> 을 직원 목록을 다시 만든 다음에 다시 연결 해야 변경 내용을 포착 하는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성은 <xref:System.Windows.Controls.ListBox>합니다. 이 솔루션은 효과는 있지만 성능에 큰 영향을 줍니다. 다시 할당할 때마다는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 의 <xref:System.Windows.Controls.ListBox> 새 개체에는 <xref:System.Windows.Controls.ListBox> 먼저 이전 항목 버리고 하 고 전체 목록을 다시 생성 합니다. 경우 성능에 영향이 확대 됩니다 프로그램 <xref:System.Windows.Controls.ListBox> 복잡 한 매핑됩니다 <xref:System.Windows.DataTemplate>합니다.  
  
 이 문제를 더 효율적이 지 방법은 직원 목록을 확인 하는 프로그램 <xref:System.Collections.ObjectModel.ObservableCollection%601>합니다. <xref:System.Collections.ObjectModel.ObservableCollection%601> 개체에 데이터 바인딩 엔진에서 수신할 수 있는 변경 알림을 발생 시킵니다. 이벤트를 추가 하거나에서 항목을 제거는 <xref:System.Windows.Controls.ItemsControl> 목록 전체를 다시 생성 하지 않아도 됩니다.  
  
 업데이트 하는 데 걸리는 시간을 보여 줍니다 아래 표는 <xref:System.Windows.Controls.ListBox> (해제 하는 UI 가상화)로 항목을 하나 추가 된 경우. 첫 번째 행의 번호 경과 시간을 나타내는 경우는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> 개체가 바인딩된 <xref:System.Windows.Controls.ListBox> 요소의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>합니다. 두 번째 행의 번호는 경과 시간을 나타냅니다 때는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 바인딩되는 <xref:System.Windows.Controls.ListBox> 요소의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>합니다. 사용 하 여 상당한 시간이 절약 참고는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 데이터 바인딩 전략입니다.  
  
|**ItemsSource 데이터 바인딩 대상**|**1개 항목의 업데이트 시간(ms)**|  
|--------------------------------------|---------------------------------------|  
|에 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] <xref:System.Collections.Generic.List%601> 개체|1656|  
|에 <xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>IList를 IEnumerable이 아닌 ItemsControl에 바인딩  
 바인딩 중 하나를 선택 해야 하는 경우는 <xref:System.Collections.Generic.IList%601> 또는 <xref:System.Collections.IEnumerable> 에 <xref:System.Windows.Controls.ItemsControl> 개체, 선택는 <xref:System.Collections.Generic.IList%601> 개체입니다. 바인딩 <xref:System.Collections.IEnumerable> 에 <xref:System.Windows.Controls.ItemsControl> 강제로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼를 만들려면 <xref:System.Collections.Generic.IList%601> 개체를 두 번째 개체의 불필요 한 오버 헤드가 성능 영향을 받습니다.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>데이터 바인딩만을 위해 CLR 개체를 XML로 변환 안 함  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 콘텐츠에 데이터 바인딩할 수 있지만 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 콘텐츠의 데이터 바인딩은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체의 데이터 바인딩보다 느립니다. 데이터 바인딩만을 위해 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체 데이터를 XML로 변환하지 마세요.  
  
## <a name="see-also"></a>참고 항목  
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
