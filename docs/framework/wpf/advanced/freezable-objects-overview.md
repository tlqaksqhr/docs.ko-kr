---
title: "Freezable 개체 개요 | Microsoft Docs"
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
  - "클래스, Freezable"
  - "Freezable 개체, description"
  - "Freezable 개체 고정 취소"
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Freezable 개체 개요
이 항목에서는 응용 프로그램 성능을 개선하는 데 도움이 되는 특수 기능을 제공하는 <xref:System.Windows.Freezable> 개체를 효율적으로 사용하고 만드는 방법에 대해 설명합니다.  Freezable 개체의 예로는 브러시, 펜, 변환, 기하 도형, 애니메이션 등이 있습니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="whatisafreezable"></a>   
## Freezable이란?  
 <xref:System.Windows.Freezable>은 고정되지 않음과 고정이라는 두 가지 상태를 가지는 특수한 개체 형식입니다.  고정되지 않은 <xref:System.Windows.Freezable>은 다른 개체처럼 동작합니다.  고정된 <xref:System.Windows.Freezable>은 더 이상 수정할 수 없습니다.  
  
 <xref:System.Windows.Freezable>에서는 관찰자에게 개체에 대한 수정 사항을 알려 주기 위한 <xref:System.Windows.Freezable.Changed> 이벤트를 제공합니다.  <xref:System.Windows.Freezable>을 고정하면 변경 알림에 더 이상 리소스를 사용할 필요가 없으므로 성능을 개선할 수 있습니다.  고정된 <xref:System.Windows.Freezable>은 스레드 간에 공유할 수도 있지만 고정되지 않은 <xref:System.Windows.Freezable>은 그럴 수 없습니다.  
  
 <xref:System.Windows.Freezable> 클래스는 다양한 용도로 사용되지만 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 <xref:System.Windows.Freezable> 개체는 대부분 그래픽 하위 시스템과 관련이 있습니다.  
  
 <xref:System.Windows.Freezable> 클래스를 사용하면 특정 그래픽 시스템 개체를 사용하기 쉽게 만들고 응용 프로그램 성능을 개선할 수 있습니다.  <xref:System.Windows.Freezable>에서 상속되는 형식의 예에는 <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform> 및 <xref:System.Windows.Media.Geometry> 클래스가 있습니다.  이러한 클래스는 관리되지 않는 리소스를 포함하므로 시스템에서는 이러한 개체의 수정 사항을 모니터링하고 원래 개체가 변경되는 경우 해당하는 관리되지 않는 리소스를 업데이트해야 합니다.  그래픽 시스템 개체가 실제로 수정되지 않더라도 시스템에서는 변경되는 경우를 대비하여 개체를 모니터링하기 위해 일부 리소스를 계속 사용해야 합니다.  
  
 예를 들어 <xref:System.Windows.Media.SolidColorBrush> 브러시를 만들고 이를 사용하여 단추의 배경을 그린다고 가정합니다.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 단추를 렌더링할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 하위 시스템에서는 사용자가 지정하는 정보를 사용하여 단추 모양을 형성하는 픽셀 그룹을 그립니다.  사용자가 단색 브러시를 사용하여 단추를 그리는 방법을 지정하더라도 실제로는 이 단색 브러시로 그리지 않습니다.  그래픽 하위 시스템에서 단추와 브러시에 대해 빠른 하위 수준 개체를 생성하고 실제로 이러한 개체가 화면에 표시됩니다.  
  
 브러시를 수정하는 경우 이러한 하위 수준 개체를 다시 생성해야 합니다.  Freezable 클래스는 브러시에서 해당하는 생성된 하위 수준 개체를 찾고 변경되는 경우 이 개체를 업데이트할 수 있는 기능을 제공합니다.  이 기능을 사용하는 경우 브러시를 "고정되지 않은" 브러시라고 합니다.  
  
 Freezable의 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 사용하면 이러한 자동 업데이트 기능을 사용하지 않도록 설정할 수 있습니다.  이 메서드를 사용하여 브러시를 "고정"되게 또는 수정할 수 없게 만들 수 있습니다.  
  
> [!NOTE]
>  일부 Freezable 개체는 고정할 수 없습니다.  <xref:System.InvalidOperationException>이 throw되지 않게 하려면 Freezable 개체의 <xref:System.Windows.Freezable.CanFreeze%2A> 속성 값을 확인하여 이 개체를 고정하기 전에 개체가 고정될 수 있는지를 확인합니다.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Freezable을 더 이상 수정할 필요가 없는 경우 고정하여 성능을 높일 수 있습니다.  이 예제에서 브러시를 고정하면 그래픽 시스템에서 브러시의 변경 사항을 더 이상 모니터링하지 않아도 됩니다.  또한 그래픽 시스템에서는 브러시가 변경되지 않을 것을 알기 때문에 다른 최적화도 수행할 수 있습니다.  
  
> [!NOTE]
>  사용 편의를 위해 Freezable 개체는 명시적으로 고정하지 않는 한 고정되지 않은 상태로 유지됩니다.  
  
<a name="frozenfreezables"></a>   
## Freezable 사용  
 고정되지 않은 Freezable은 다른 형식의 개체처럼 사용합니다.  다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush>를 사용하여 단추의 배경을 그린 후 그 색을 노랑에서 빨강으로 변경합니다.  그래픽 시스템이 내부적으로 작동하여 다음에 화면이 새로 고쳐질 때 단추 색을 자동으로 노랑에서 빨강으로 변경합니다.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### Freezable 고정  
 <xref:System.Windows.Freezable>을 수정할 수 없게 만들려면 해당 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 호출합니다.  Freezable 개체를 포함하는 개체를 고정하면 포함된 Freezable 개체도 고정됩니다.  예를 들어 <xref:System.Windows.Media.PathGeometry>를 고정하면 여기에 포함된 그림과 세그먼트도 고정됩니다.  
  
 다음에 해당하는 경우 Freezable을 고정할 수 **없습니다**.  
  
-   애니메이션이 적용되거나 데이터가 바인딩된 속성이 있습니다.  
  
-   동적 리소스로 설정된 속성이 있습니다.  동적 리소스에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
-   고정할 수 없는 <xref:System.Windows.Freezable> 하위 개체가 포함되어 있습니다.  
  
 이러한 조건에 해당되지 않고 <xref:System.Windows.Freezable>을 수정하지 않으려는 경우에는 앞에서 설명한 것처럼 성능 향상을 위해 개체를 고정해야 합니다.  
  
 Freezable의 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 호출하면 이 개체를 더 이상 수정할 수 없습니다.  고정된 개체를 수정하려고 하면 <xref:System.InvalidOperationException>이 throw됩니다.  다음 코드에서는 브러시를 고정한 후 수정하려고 하기 때문에 예외가 throw됩니다.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 이 예외가 throw되지 않도록 하려면 <xref:System.Windows.Freezable.IsFrozen%2A> 메서드를 사용하여 <xref:System.Windows.Freezable>가 고정되어 있는지 여부를 확인합니다.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 앞의 코드 예제에서는 <xref:System.Windows.Freezable.Clone%2A> 메서드를 사용하여 고정된 개체의 수정 가능한 복사본을 만들었습니다.  다음 단원에서는 복제에 대해 더 자세히 설명합니다.  
  
 **참고** 고정된 Freezable에는 애니메이션 효과를 적용할 수 없으므로 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 이 개체에 애니메이션 효과를 주려고 하면 애니메이션 시스템에서 자동으로 고정된 <xref:System.Windows.Freezable> 개체의 수정 가능한 복제본을 만듭니다.  복제로 인한 성능 오버헤드를 제거하려면 개체에 애니메이션 효과를 적용하려는 경우에는 개체를 고정되지 않은 상태로 둡니다.  Storyboard를 사용하여 애니메이션 효과를 적용하는 방법에 대한 자세한 내용은 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하십시오.  
  
### 태그에서 고정  
 태그에서 선언한 <xref:System.Windows.Freezable> 개체를 고정하려면 `PresentationOptions:Freeze` 특성을 사용합니다.  다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush>를 페이지 리소스로 선언하고 고정합니다.  그런 다음 단추 배경을 설정하는 데 사용합니다.  
  
 [!code-xml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 `Freeze` 특성을 사용하려면 표시 옵션 네임스페이스 `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`에 매핑해야 합니다.  `PresentationOptions`는 이 네임스페이스 매핑을 위한 권장 접두사입니다.  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 일부 XAML 판독기에서는 이 특성을 인식하지 못하므로 다음과 같이 [mc:Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)을 사용하여 `Presentation:Freeze` 특성을 무시할 수 있도록 표시하는 것이 좋습니다.  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 자세한 내용은 [mc:Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) 페이지를 참조하십시오.  
  
### Freezable "고정 취소"  
 <xref:System.Windows.Freezable>을 고정하면 수정하거나 고정 취소할 수 없습니다. 그러나 <xref:System.Windows.Freezable.Clone%2A> 또는 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드를 사용하여 고정되지 않은 복제본 만들 수는 있습니다.  
  
 다음 예제에서는 단추의 배경을 브러시로 설정한 다음 해당 브러시를 고정합니다.  그리고 <xref:System.Windows.Freezable.Clone%2A> 메서드를 사용하여 브러시의 고정되지 않은 복사본을 만듭니다.  이 복제본을 수정 및 사용하여 단추의 배경을 노랑에서 빨강으로 변경합니다.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  어떤 복제 메서드를 사용하든 애니메이션은 새 <xref:System.Windows.Freezable>로 복사할 수 없습니다.  
  
 <xref:System.Windows.Freezable.Clone%2A> 및 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드는 Freezable의 전체 복사본을 만듭니다.  Freezable에 다른 고정된 Freezable 개체가 포함되어 있는 경우 포함된 Freezable 개체도 복제되어 수정할 수 있게 됩니다.  예를 들어 고정된 <xref:System.Windows.Media.PathGeometry>를 복제하여 수정할 수 있도록 만들면 여기에 포함된 그림과 세그먼트도 복사되어 수정할 수 있게 됩니다.  
  
<a name="createyourownfreezableclass"></a>   
## 사용자 고유의 Freezable 클래스 만들기  
 <xref:System.Windows.Freezable>에서 파생되는 클래스에는 다음과 같은 기능이 있습니다.  
  
-   특수 상태: 읽기 전용\(고정\) 상태와 쓰기 기능 상태가 있습니다.  
  
-   스레드 안전: 고정된 <xref:System.Windows.Freezable>은 스레드 간에 공유할 수 있습니다.  
  
-   자세한 변경 알림: 다른 <xref:System.Windows.DependencyObject>와 달리 Freezable 개체는 하위 속성 값이 변경될 때 변경 알림을 제공합니다.  
  
-   손쉬운 복제: Freezable 클래스에는 전체 복제를 만드는 몇 가지 메서드가 이미 구현되어 있습니다.  
  
 <xref:System.Windows.Freezable>은 <xref:System.Windows.DependencyObject> 형식이므로 종속성 속성 시스템을 사용합니다.  클래스 속성이 종속성 속성일 필요는 없지만 <xref:System.Windows.Freezable> 클래스는 종속성 속성을 염두에 두고 설계되었기 때문에 종속성 속성을 사용하면 작성해야 하는 코드 양이 줍니다.  종속성 속성 시스템에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  
  
 모든 <xref:System.Windows.Freezable> 서브클래스는 이 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 메서드를 재정의해야 합니다.  클래스에서 모든 데이터에 대해 종속성 속성을 사용하는 경우에는 추가 작업이 필요하지 않습니다.  
  
 클래스에 종속성 속성이 아닌 데이터 멤버가 포함되어 있는 경우 다음 메서드로 재정의해야 합니다.  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 또한 종속성 속성이 아닌 데이터 멤버에 액세스하고 쓰기 위해서는 다음 규칙을 따라야 합니다.  
  
-   비종속성 속성 데이터 멤버를 읽는 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]의 시작 부분에서 <xref:System.Windows.Freezable.ReadPreamble%2A> 메서드를 호출합니다.  
  
-   비종속성 속성 데이터 멤버를 쓰는 API의 시작 부분에서 <xref:System.Windows.Freezable.WritePreamble%2A> 메서드를 호출합니다.  [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]에서 <xref:System.Windows.Freezable.WritePreamble%2A>을 호출한 후에는 비종속성 속성 데이터 멤버를 읽은 경우 <xref:System.Windows.Freezable.ReadPreamble%2A>을 추가로 호출할 필요가 없습니다.  
  
-   비종속성 속성 데이터 멤버에 쓰는 기존 메서드 전에 <xref:System.Windows.Freezable.WritePostscript%2A> 메서드를 호출합니다.  
  
 클래스에 <xref:System.Windows.DependencyObject> 개체인 비종속성 속성 데이터 멤버가 포함되어 있는 경우 이 멤버를 `null`로 설정하는 경우에도 해당 값을 변경할 때마다 <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> 메서드도 호출해야 합니다.  
  
> [!NOTE]
>  재정의하는 각 <xref:System.Windows.Freezable> 메서드를 기본 구현에 대한 호출로 시작해야 합니다.  
  
 사용자 지정 <xref:System.Windows.Freezable> 클래스의 예제를 보려면 [Custom Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=159981)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Freezable>   
 [Custom Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=159981)   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)