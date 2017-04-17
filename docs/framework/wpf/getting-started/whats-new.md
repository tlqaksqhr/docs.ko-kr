---
title: "WPF 버전 4.5의 새로운 기능 | Microsoft Docs"
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
  - "Windows Presentation Foundation, 새로운 기능"
  - "WPF, 새로운 기능"
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
caps.latest.revision: 55
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 55
---
# WPF 버전 4.5의 새로운 기능
<a name="introduction"></a> 이 항목에서는 새로운 기능과 향상 된 기능에 대 한 설명 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 버전 4.5.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [리본 컨트롤](#ribbon_control)  
  
-   [그룹화 된 데이터 집합을 크게 표시 하면 성능 향상된](#grouped_virtualization)  
  
-   [VirtualizingPanel 위한 새 기능](#VirtualizingPanel)  
  
-   [정적 속성에 바인딩](#static_properties)  
  
-   [에 비\-UI 스레드에서 컬렉션에 액세스](#xthread_access)  
  
-   [동기적 및 비동기적으로 데이터 유효성 검사](#INotifyDataErrorInfo)  
  
-   [데이터 바인딩 소스가 자동으로 업데이트](#delay)  
  
-   [해당 구현 ICustomTypeProvider 형식에 바인딩](#ICustomTypeProvider)  
  
-   [바인딩 식에서 데이터 바인딩 정보를 검색합니다.](#binding_state)  
  
-   [유효한 DataContext 개체를 검사합니다.](#DisconnectedSource)  
  
-   [\(세공 라이브\) 데이터의 값을 변경할 때 데이터 위치 변경](#live_shaping)  
  
-   [이벤트에 대 한 약한 참조를 위한 향상 된 지원](#weak_event_pattern)  
  
-   [Dispatcher 클래스에 대 한 새 메서드](#async)  
  
-   [이벤트에 대 한 태그 확장](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## 리본 컨트롤  
 WPF 4.5 출시에 <xref:System.Windows.Controls.Ribbon.Ribbon> 호스트 응용 프로그램 메뉴에서 빠른 액세스 도구 모음, 탭 컨트롤 합니다.  자세한 내용은 [리본 개요](../Topic/Ribbon%20Overview.md)를 참조하십시오.  
  
<a name="grouped_virtualization"></a>   
## 그룹화 된 데이터 집합을 크게 표시 하면 성능 향상된  
 UI 가상화 발생 하는 하위 집합을 사용할 때 사용자 인터페이스 \(UI\)에 많은 수의 데이터 항목을 화면에 표시 되는 항목에 따라 요소가 생성 됩니다.  <xref:System.Windows.Controls.VirtualizingPanel> 정의 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> 연결 된 그룹화 된 데이터에 대 한 UI 가상화를 사용 하는 속성입니다.  데이터 그룹화에 대 한 자세한 내용은 방법: 정렬 및 그룹 데이터를 사용 하는 xaml에서 보기.  가상화에 대 한 자세한 내용은 데이터 그룹화에 대 한 참조는 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> 연결 된 속성입니다.  
  
<a name="VirtualizingPanel"></a>   
## VirtualizingPanel 위한 새 기능  
  
1.  지정할 수 있습니다 여부는 <xref:System.Windows.Controls.VirtualizingPanel>, 등의 <xref:System.Windows.Controls.VirtualizingStackPanel>, 일부 항목을 사용 하 여 표시는 <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> 연결 속성.  경우 <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> 설정 <xref:System.Windows.Controls.ScrollUnit>, <xref:System.Windows.Controls.VirtualizingPanel> 만 완전히 표시 되는 항목을 표시 합니다.  경우 <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> 설정 <xref:System.Windows.Controls.ScrollUnit>, <xref:System.Windows.Controls.VirtualizingPanel> 부분적으로 항목을 표시할 수 있습니다.  
  
2.  뷰포트 전후 캐시의 크기를 지정할 수 있습니다 때의 <xref:System.Windows.Controls.VirtualizingPanel> 를 사용 하 여 가상화 된는 <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> 연결 속성.  캐시 위나 아래 뷰포트의 항목에서 않습니다 가상화 하는 공간의 크기입니다.  캐시를 사용 하 여 뷰로 스크롤할 하는 대로 UI 요소를 생성 하지 않으려면 성능을 향상 시킬 수 있습니다.  응용 프로그램 작업 하는 동안 응답 하지 않을 수 있도록 낮은 우선 순위로 캐시를 채웁니다.  <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=fullName> 속성을 사용 하 여 측정 단위를 결정 <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=fullName>.  
  
<a name="static_properties"></a>   
## 정적 속성에 바인딩  
 정적 속성의 데이터 바인딩 원본으로 사용할 수 있습니다.  정적 이벤트가 발생 하는 경우 속성의 값을 변경 하면 데이터 바인딩 엔진을 인식 합니다.  예를 들어, 경우 클래스 `SomeClass` 라는 정적 속성 정의 `MyProperty`, `SomeClass` 되는 정적 이벤트를 정의 될 때 발생 값의 `MyProperty` 변경.  정적 이벤트는 다음 시그니처 중 하나를 사용할 수 있습니다.  
  
-   `public static event EventHandler MyPropertyChanged;`  
  
-   `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 첫 번째 경우 라는 정적 이벤트 클래스를 노출 하는 참고  *PropertyName*`Changed` 는 전달 <xref:System.EventArgs> 이벤트 처리기입니다.  두 번째 경우에는 클래스 라는 정적 이벤트 노출 `StaticPropertyChanged` 는 전달 <xref:System.ComponentModel.PropertyChangedEventArgs> 이벤트 처리기.  정적 속성을 구현 하는 클래스 메서드 중 하나를 사용 하 여 속성 변경 알림을 발생 시킬 수 있습니다.  
  
<a name="xthread_access"></a>   
## 에 비\-UI 스레드에서 컬렉션에 액세스  
 WPF를 사용 하 여 액세스 하 고 데이터 컬렉션을 컬렉션을 만든 다른 스레드에서 수정할 수 있습니다.  이 백그라운드 스레드를 사용 하 여 데이터베이스와 같은 외부 원본에서 데이터를 수신 하 고 UI 스레드에서 데이터를 표시 하는 수 있습니다.  다른 스레드에서 컬렉션을 수정 하 여 사용자 인터페이스를 사용자 상호 작용에 응답 유지 됩니다.  
  
<a name="INotifyDataErrorInfo"></a>   
## 동기적 및 비동기적으로 데이터 유효성 검사  
 <xref:System.ComponentModel.INotifyDataErrorInfo> 인터페이스 데이터 엔터티 클래스를 사용 하 여 사용자 지정 유효성 검사 규칙을 구현 하 고 유효성 검사 결과 비동기적으로 노출할 수 있습니다.  이 인터페이스 사용자 지정 오류 개체, 속성, 속성 간 오류 및 엔터티 수준 오류 당 여러 오류도 지원합니다.  자세한 내용은 <xref:System.ComponentModel.INotifyDataErrorInfo>을 참조하십시오.  
  
<a name="delay"></a>   
## 데이터 바인딩 소스가 자동으로 업데이트  
 데이터 바인딩을 사용 하 여 데이터 원본을 업데이트 하는 경우 사용할 수 있는 <xref:System.Windows.Data.BindingBase.Delay%2A> 대상 원본 업데이트 하기 전에 속성 변경 후 전달 하는 시간을 지정 하는 속성.  하면 예를 들어는 <xref:System.Windows.Controls.Slider> 있는 해당 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 양방향 속성 데이터 바인딩된 데이터 개체의 속성을 및 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성을 설정 <xref:System.Windows.Data.UpdateSourceTrigger>.  이동할 때이 예제에서는 <xref:System.Windows.Controls.Slider>, 각 픽셀에 대 한 원본 업데이트는의 <xref:System.Windows.Controls.Slider> 이동.  슬라이더의 값 소스 객체를 일반적으로 필요한 경우에만 슬라이더의 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 변경 중지 합니다.  소스를 너무 자주 업데이트 하지 않으려면 사용 <xref:System.Windows.Data.BindingBase.Delay%2A> 엄지 이동 중지 후 일정 시간이 경과 될 때까지 업데이트 되도록 않는 소스를 지정 합니다.  
  
<a name="ICustomTypeProvider"></a>   
## 해당 구현 ICustomTypeProvider 형식에 바인딩  
 WPF 데이터 바인딩을 구현 하는 개체를 지 원하는 <xref:System.Reflection.ICustomTypeProvider>, 사용자 지정 형식이 라고도 합니다.  다음과 같은 경우에 사용자 지정 형식을 사용할 수 있습니다.  
  
1.  로 <xref:System.Windows.PropertyPath> 에 데이터 바인딩.  예를 들어,는 <xref:System.Windows.Data.Binding.Path%2A> 속성에는 <xref:System.Windows.Data.Binding> 형식의 사용자 지정 속성을 참조할 수 있습니다.  
  
2.  값으로는 <xref:System.Windows.DataTemplate.DataType%2A> 속성.  
  
3.  자동으로 생성 된 열을 결정 하는 형식으로는 <xref:System.Windows.Controls.DataGrid>.  
  
<a name="binding_state"></a>   
## 바인딩 식에서 데이터 바인딩 정보를 검색합니다.  
 얻게 되는 특정 한 경우에는 <xref:System.Windows.Data.BindingExpression> 의 <xref:System.Windows.Data.Binding> 바인딩 원본과 대상 개체에 대 한 정보가 필요 하 고.  소스 또는 대상 개체 또는 연결 된 속성을 가져올 수 있도록 새로운 Api 추가 되었습니다.  경우는 <xref:System.Windows.Data.BindingExpression>, 다음 Api를 사용 하 여 대상 및 원본에 대 한 정보를 얻을 수 있습니다.  
  
|이 값에 바인딩|이 API를 사용 합니다.|  
|--------------|--------------------|  
|대상 개체|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=fullName>|  
|대상 속성|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=fullName>|  
|원본 개체|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=fullName>|  
|소스 속성|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=fullName>|  
|여부는 <xref:System.Windows.Data.BindingExpression> 에 속해 있는<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=fullName>|  
|소유자는<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## 유효한 DataContext 개체를 검사합니다.  
 경우가 위치는 <xref:System.Windows.FrameworkElement.DataContext%2A> 항목 컨테이너에 <xref:System.Windows.Controls.ItemsControl> 연결이 됩니다.  항목 컨테이너 UI 요소 항목에 표시 되는 <xref:System.Windows.Controls.ItemsControl>.  경우는 <xref:System.Windows.Controls.ItemsControl> 데이터 컬렉션에 바인딩된 각 항목에 대 한 항목 컨테이너 생성 됩니다.  경우에 따라서는 항목 컨테이너 시각적 트리에서 제거 됩니다.  항목 컨테이너 제거는 두 가지 일반적인 경우는 내부 컬렉션에서 항목이 제거 되는 경우 및 가상화에 사용 하는 경우는 <xref:System.Windows.Controls.ItemsControl>.  이러한 경우에는 <xref:System.Windows.FrameworkElement.DataContext%2A> 항목 컨테이너의 속성을 반환 하는 센티널 개체에 설정할 수는 <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=fullName> 정적 속성.  확인 해야 하는지 여부는 <xref:System.Windows.FrameworkElement.DataContext%2A> 같지는 <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> 개체에 액세스 하기 전에 <xref:System.Windows.FrameworkElement.DataContext%2A> 항목 컨테이너의.  
  
<a name="live_shaping"></a>   
## \(세공 라이브\) 데이터의 값을 변경할 때 데이터 위치 변경  
 데이터 컬렉션을 그룹화, 정렬, 하거나 필터링 할 수 있습니다.  4.5 WPF 데이터를 데이터가 수정 될 때 다시 정렬할 수 있습니다.  예를 들어, 응용 프로그램에서 사용 하는 가정은 <xref:System.Windows.Controls.DataGrid> 목록에 주식 시장에서 주식 및 주식 주식 값으로 정렬 됩니다.  주식 실시간 정렬을 사용 하는 경우 <xref:System.Windows.Data.CollectionView>, 주가 위치는 <xref:System.Windows.Controls.DataGrid> 값 보다 작으면 다른 주식 또는 주식 값 커지면 이동 합니다.  자세한 내용은 <xref:System.ComponentModel.ICollectionViewLiveShaping> 인터페이스를 참조하십시오.  
  
<a name="weak_event_pattern"></a>   
## 이벤트에 대 한 약한 참조를 위한 향상 된 지원  
 구독자에 이벤트를 추가 인터페이스를 구현 하지 않고 참여할 수 있기 때문에 약한 이벤트 패턴을 구현 이제 쉽습니다.  일반 <xref:System.Windows.WeakEventManager> 클래스에도 구독자에 전용 경우 약한 이벤트 패턴에 참여할 수 있습니다 <xref:System.Windows.WeakEventManager> 에 대 한 이벤트는 존재 하지 않습니다.  자세한 내용은 [약한 이벤트 패턴](../../../../docs/framework/wpf/advanced/weak-event-patterns.md)을 참조하십시오.  
  
<a name="async"></a>   
## Dispatcher 클래스에 대 한 새 메서드  
 Dispatcher 클래스는 동기 및 비동기 작업에 대 한 새 메서드를 정의합니다.  동기는 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 메서드를 사용 하는 오버 로드를 정의 <xref:System.Action> 또는 <xref:System.Func%601> 매개 변수.  새 비동기 메서드를 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, 사용도 <xref:System.Action> 또는 <xref:System.Func%601> 콜백 매개 변수 및 반환은 <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>.  <xref:System.Windows.Threading.DispatcherOperation> 및 <xref:System.Windows.Threading.DispatcherOperation%601> 클래스 정의 <xref:System.Threading.Tasks.Task> 속성.  호출 하면 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>를 사용할 수 있습니다는 `await` 키워드로 하나는 <xref:System.Windows.Threading.DispatcherOperation> 또는 연결 된 <xref:System.Threading.Tasks.Task>.  동기적으로 기다려야 할 경우는 <xref:System.Threading.Tasks.Task> 에서 반환 되는 <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>, 호출의 <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> 확장 메서드.  호출 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=fullName> 호출 스레드에서 대기 작업 하는 경우 교착 상태를 발생 합니다.  사용에 대 한 자세한 정보는 <xref:System.Threading.Tasks.Task> 비동기 작업 수행을 참조 하십시오. [작업 병렬 처리\(작업 병렬 라이브러리\)](../../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>   
## 이벤트에 대 한 태그 확장  
 4.5 WPF 태그 확장에 대 한 이벤트를 지원합니다.  WPF 이벤트에 사용 되는 태그 확장을 정의 하지 않는 동안 타사 이벤트와 함께 사용할 수 있는 태그 확장을 만들 수 있습니다.  
  
## 참고 항목  
 [.NET Framework의 새로운 기능](../../../../docs/framework/whats-new/index.md)