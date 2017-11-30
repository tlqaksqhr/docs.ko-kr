---
title: "Freezable 개체 개요"
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
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49778dc9551652ee4a4d36426b4b396652b9dcd2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="freezable-objects-overview"></a>Freezable 개체 개요
이 항목에서는 효과적으로 사용 하 고 만드는 방법을 설명 <xref:System.Windows.Freezable> 응용 프로그램의 성능을 향상 시킬 수 있는 특별 한 기능을 제공 하는 개체입니다. Freezable 개체의 예로 브러시, 펜, 변환, 기 하 도형 및 애니메이션을 들 수 있습니다.  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a>Freezable 이란?  
 A <xref:System.Windows.Freezable> 는 특수 한 유형의 두 가지 상태를 가진 개체를: 고정 해제 하 고 고정 합니다. 고정 되지 않은 한 <xref:System.Windows.Freezable> 다른 개체 처럼 동작 하 게 나타납니다. 고정 경우는 <xref:System.Windows.Freezable> 더 이상 수정할 수 없습니다.  
  
 A <xref:System.Windows.Freezable> 제공는 <xref:System.Windows.Freezable.Changed> 관찰자는 개체에 대 한 수정에 알리는 이벤트를 합니다. 고정 된 <xref:System.Windows.Freezable> 하기 때문에 더 이상 변경 알림을에 리소스를 소비 성능을 향상 시킬 수 없습니다. 고정 된 <xref:System.Windows.Freezable> 고정 되지 않은 동안 스레드 간에 공유할 수도 <xref:System.Windows.Freezable> 수 없습니다.  
  
 하지만 <xref:System.Windows.Freezable> 클래스는 다양 한 용도로 가장 <xref:System.Windows.Freezable> 개체 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 그래픽 하위 시스템과 관련 된 합니다.  
  
 <xref:System.Windows.Freezable> 클래스 쉽게 특정 그래픽 시스템 개체를 사용 하 고 응용 프로그램의 성능을 향상 시킬 수 있습니다. 상속 하는 형식의 예 <xref:System.Windows.Freezable> 포함는 <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, 및 <xref:System.Windows.Media.Geometry> 클래스입니다. 관리 되지 않는 리소스를 포함 하기 때문에 시스템의 수정 사항 이러한 개체를 모니터링 하 고 원래 개체에 변경 될 때 해당 관리 되지 않는 리소스를 업데이트 해야 합니다. 그래픽 시스템 개체를 실제로 수정 하지 않는 경우에 시스템을 계속 사용 해야 일부 리소스 모니터링 개체를 변경 하는 경우.  
  
 예를 들어 다음과 같이 가정는 <xref:System.Windows.Media.SolidColorBrush> 브러시 및 단추의 배경을 칠하는 데 사용 합니다.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 단추를 렌더링할 때는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 하위 시스템 그룹 단추의 모양을 형성 하는 픽셀을 그립니다 사용자가 제공한 정보를 사용 합니다. 단색 브러시를 사용 하는 단추를 그리는 방법을 설명 하기 위해 있지만 단색 브러시 실제로 그리기를 수행 하지 않습니다. 단추와 브러시를 신속 하 고 하위 수준 개체를 생성 하는 그래픽 시스템 아니며 개체는 실제로 화면에 표시 합니다.  
  
 브러시를 수정 하는 경우, 이러한 하위 수준 개체를 다시 생성 해야 합니다. Freezable 클래스는 해당 생성 된, 하위 수준 개체를 찾을 수 고를 변경할 때이 정보도 업데이트 권한을 브러시를 제공 합니다. 이 기능을 사용 하는 경우 브러시 라고 없습니다 "고정" 합니다.  
  
 Freezable의 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 사용 하면 이러한 자동 업데이트 기능을 사용 하지 않도록 설정 합니다. "고정" 또는 수정할 수 없게 되는 브러시를 조정 하려면이 메서드를 사용할 수 있습니다.  
  
> [!NOTE]
>  모든 Freezable 개체를 고정할 수 있습니다. Throw 되지 않도록 하려면는 <xref:System.InvalidOperationException>, Freezable 개체의 값을 확인 <xref:System.Windows.Freezable.CanFreeze%2A> 고정 하기 전에 고정 가능 여부를 결정 하는 속성입니다.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Freezable 수정 해야 하는 더 이상, 고정 성능 이점을 제공 합니다. 이 예에서 브러시를 고정 하는 경우, 그래픽 시스템 변경에 대 한 모니터링은 더 이상 해야 합니다. 그래픽 시스템 브러시 변경 되지 않는 것을 알고 있으므로 다른 최적화를 축소할 수 있습니다.  
  
> [!NOTE]
>  편의 위해 명시적으로 고정 하지 않는 한 freezable 개체 고정 되지 않은 유지 합니다.  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a>Freezable을 사용 하 여  
 고정 되지 않은 사용 하 여 freezable 비슷합니다 다른 형식의 개체를 사용 하 여 합니다. 다음 예제에서는 색을는 <xref:System.Windows.Media.SolidColorBrush> 단추의 배경을 칠하는 데 사용 된 후 빨간색으로 노랑에서 변경 합니다. 그래픽 시스템으로 자동 변경 하 고 단추 노랑에서 빨강으로 다음에 화면 새로 고칠 때 내부적으로 작동 합니다.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a>Freezable 고정  
 있도록는 <xref:System.Windows.Freezable> 호출 수정할 수 없는, 해당 <xref:System.Windows.Freezable.Freeze%2A> 메서드. Freezable 개체를 포함 하는 개체를 중지 하면 해당 개체도 고정 됩니다. 예를 들어, 고정 하면는 <xref:System.Windows.Media.PathGeometry>, 그림 및 포함 된 세그먼트 고정 됩니다.  
  
 Freezable **없습니다** 다음 중 하나에 해당할 경우 고정할 수 있습니다.  
  
-   애니메이션이 적용 또는 데이터 바인딩된 속성입니다.  
  
-   동적 리소스에서 설정 하는 속성이 있습니다. (참조는 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md) 동적 리소스에 대 한 자세한 내용은.)  
  
-   포함 된 <xref:System.Windows.Freezable> 고정할 수 없는 하위 개체입니다.  
  
 이러한 조건은 false 및 수정 하지 않으려는 경우는 <xref:System.Windows.Freezable>, 앞에서 설명한 성능을 향상 시키는 것을 고정 해야 합니다.  
  
 Freezable의 호출한 후 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 수정할 수 없습니다. 고정 된 수정 하려고 하면 개체는 <xref:System.InvalidOperationException> throw 됩니다. 다음 코드는 고정 된 후 브러시를 수정 하려고 하기 때문에 예외를 throw 합니다.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 이 예외가 throw를 방지 하려면 사용할 수 있습니다는 <xref:System.Windows.Freezable.IsFrozen%2A> 확인 하 여부는 <xref:System.Windows.Freezable> 고정 되어 있습니다.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 이전 코드 예제에서 사용 하 여 고정 된 개체의 수정 가능한 복사본 했습니다는 <xref:System.Windows.Freezable.Clone%2A> 메서드. 다음 섹션에서 자세히 복제를 설명 합니다.  
  
 **참고** 때문에 고정 된 freezable 없습니다 애니메이션 효과 줄, 애니메이션 시스템에서의 수정 가능한 복제본을 자동으로 만듭니다 고정 <xref:System.Windows.Freezable> 를 사용 하 여 애니메이션을 적용 하려고 할 때 개체는 <xref:System.Windows.Media.Animation.Storyboard>합니다. 성능 복제로 인 한 오버 헤드를 방지 하려면 애니메이션을 적용 하려는 경우 고정 해제 하는 개체를 둡니다. 스토리 보드가 있는 애니메이션을 적용 하는 방법에 대 한 자세한 내용은 참조는 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
### <a name="freezing-from-markup"></a>태그에서 고정  
 고정 하려면는 <xref:System.Windows.Freezable> 사용 하면 태그에 선언 된 개체는 `PresentationOptions:Freeze` 특성입니다. 다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush> 페이지 리소스로 선언 되 고 고정 합니다. 다음 단추의 배경색을 설정 하는 데 사용 됩니다.  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 사용 하는 `Freeze` 특성을 매핑해야 옵션 네임 스페이스: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`합니다. `PresentationOptions`이 네임 스페이스를 매핑하기 위한 권장된 접두사:  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 일부 XAML 판독기에서이 특성을 인식 하기 때문에 것이 좋습니다를 사용 하는 [mc: Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) 표시 하는 `Presentation:Freeze` 특성을 무시할 수:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 자세한 내용은 참조는 [mc: Ignorable 특성](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) 페이지.  
  
### <a name="unfreezing-a-freezable"></a>"고정 해제" Freezable  
 하지만 고정 하면는 <xref:System.Windows.Freezable> 없습니다 수정 하거나 고정 해제; 수 사용 하는 고정 되지 않은 복제본을 만들 수는 <xref:System.Windows.Freezable.Clone%2A> 또는 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드.  
  
 다음 예제에서는 단추의 배경을 브러시로 설정 되 고 고정 되는 브러시입니다. 고정 되지 않은 복사본을 사용 하 여 브러시는 <xref:System.Windows.Freezable.Clone%2A> 메서드. 복제를 수정 하 고 노란색 배경이 빨강으로 변경 하는 데 있습니다.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  복제 방법을 사용 하 여 애니메이션에 새 복사 되지 않습니다 <xref:System.Windows.Freezable>합니다.  
  
 <xref:System.Windows.Freezable.Clone%2A> 및 <xref:System.Windows.Freezable.CloneCurrentValue%2A> 메서드는 freezable의 전체 복사본을 생성 합니다. 들어 있는 경우는 freezable 다른 고정 freezable 개체도 복제 되며 수정할 수 있게 됩니다. 예를 들어, 고정 된 복제 하면 <xref:System.Windows.Media.PathGeometry> 수정 가능 하 포함 된 세그먼트와도 복사 되어 수정할 수 있게 합니다.  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a>사용자 고유의 Freezable 클래스 만들기  
 파생 되는 클래스 <xref:System.Windows.Freezable> 다음과 같은 기능이 있습니다.  
  
-   특수 상태: 읽기 전용 (고정) 및 쓰기 가능 상태가 됩니다.  
  
-   스레드로부터의 안전성: 고정 된 <xref:System.Windows.Freezable> 스레드 간에 공유할 수 있습니다.  
  
-   자세한 변경 알림: 다릅니다 <xref:System.Windows.DependencyObject>s, Freezable 개체 변경 알림을 제공 하위 속성 값을 변경 합니다.  
  
-   손쉬운 복제: Freezable 클래스 이미 전체 복제를 생성 하는 여러 메서드를 구현 합니다.  
  
 A <xref:System.Windows.Freezable> 의 형식인 <xref:System.Windows.DependencyObject>, 종속성 속성 시스템을 사용 합니다. 클래스 속성이 종속성 속성을 쓸 필요가 없습니다 있지만 종속성 속성을 사용 하 여 쓰기 때문에 해야 하는 코드의 양을 줄일 됩니다는 <xref:System.Windows.Freezable> 클래스 종속성 속성을 염두에서에 두고 설계 되었습니다. 종속성 속성 시스템에 대 한 자세한 내용은 참조는 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)합니다.  
  
 모든 <xref:System.Windows.Freezable> 하위 클래스에서 재정의 해야 합니다는 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 메서드. 모든 데이터에 대 한 종속성 속성을 사용 하는 클래스를 하는 경우 완료 합니다.  
  
 비 종속성 속성 데이터 멤버를 포함 하는 클래스를 하는 경우 다음 방법 재정의 해야 합니다.  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 또한 액세스 하 고 쓰기는 종속성 속성이 아닌 데이터 멤버에 대 한 다음 규칙을 준수 해야 합니다.  
  
-   시작 부분에서 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] 비 종속성 속성 데이터 멤버를 읽는, 호출 된 <xref:System.Windows.Freezable.ReadPreamble%2A> 메서드.  
  
-   비 종속성 속성 데이터 멤버를 작성 하는 모든 API의 시작 부분에서 호출 된 <xref:System.Windows.Freezable.WritePreamble%2A> 메서드. (호출한 후 <xref:System.Windows.Freezable.WritePreamble%2A> 에 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]은 추가 호출을 확인 하지 않아도 <xref:System.Windows.Freezable.ReadPreamble%2A> 비 종속성 속성 데이터 멤버를 읽은 경우.)  
  
-   호출 된 <xref:System.Windows.Freezable.WritePostscript%2A> 비 종속성 속성 데이터 멤버에 작성 하는 메서드를 종료 하기 전에 메서드.  
  
 클래스 종속성 비 속성 데이터 멤버를 포함 하는 경우 <xref:System.Windows.DependencyObject> 도 호출 해야 개체는 <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> 메서드 컨트롤는 멤버를 설정 하는 경우에 해당 값의에서 변경할 때마다 `null`합니다.  
  
> [!NOTE]
>  각각를 시작 하는 것이 중요 <xref:System.Windows.Freezable> 메서드를 기본 구현에 대 한 호출으로 재정의 합니다.  
  
 사용자 지정에 대 한 예제 <xref:System.Windows.Freezable> 클래스를 참조 하십시오.는 [사용자 지정 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=159981)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Freezable>  
 [사용자 지정 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=159981)  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
