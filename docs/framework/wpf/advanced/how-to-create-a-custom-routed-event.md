---
title: '방법: 사용자 지정 라우트된 이벤트 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: a8aa038008ed93cedfe49fde4e0269712b4fb19a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543708"
---
# <a name="how-to-create-a-custom-routed-event"></a>방법: 사용자 지정 라우트된 이벤트 만들기
이벤트 라우팅을 지원 하도록 사용자 지정 이벤트를 등록 해야는 <xref:System.Windows.RoutedEvent> 를 사용 하는 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> 메서드. 이 예제에서는 사용자 지정 라우트된 이벤트를 만드는 데 대한 기본 사항을 설명합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서와 같이 먼저를 등록 한 <xref:System.Windows.RoutedEvent> 를 사용 하 여는 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> 메서드. 일반적으로는 <xref:System.Windows.RoutedEvent> 정적 필드 이름을 접미사로 끝나야 ***이벤트***합니다. 이 예제에서는 이벤트 이름이 `Tap` 이벤트의 라우팅 전략은 및 <xref:System.Windows.RoutingStrategy.Bubble>합니다. 등록 호출 후에는 이벤트에 대한 추가 및 제거 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 이벤트 접근자를 제공할 수 있습니다.  
  
 이 예제에서는 `OnTap`이라는 가상 메서드를 통해 이벤트를 발생시키지만 이벤트를 발생시키는 방법 및 이벤트가 변경에 응답하는 방법은 필요에 맞게 설정할 수 있습니다.  
  
 이 예제에서는 기본적으로의 서브 클래스 전체를 구현도 참고 <xref:System.Windows.Controls.Button>; 별도 어셈블리로 해당 하위 클래스가 빌드되고 다음에 별도 사용자 지정 클래스로 인스턴스화됩니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지. 이는 다른 컨트롤로 구성된 트리에 서브클래싱된 컨트롤을 삽입할 수 있고, 이 경우 이러한 컨트롤의 사용자 지정 이벤트의 이벤트 라우팅 기능이 모든 네이티브 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 요소의 이벤트 라우팅 기능과 동일하다는 점을 보여 주기 위함입니다.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 터널링 이벤트가 만들어집니다 동일한 방식으로, 하지만 <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> 로 설정 <xref:System.Windows.RoutingStrategy.Tunnel> 에 등록 호출 합니다. 규칙에 따라 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 터널링 이벤트에는 “Preview”라는 접두사가 붙습니다.  
  
 버블링 이벤트 작동 방식에 대한 예제를 보려면 [라우트된 이벤트 처리](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)
