---
title: "스타일러스에서 입력 가로채기"
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
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5fde62e2e1ab17b26c91051f68b7d4225450c60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="intercepting-input-from-the-stylus"></a>스타일러스에서 입력 가로채기
<xref:System.Windows.Input.StylusPlugIns> 통해 수준이 낮은 제어를 구현 하기 위한 메커니즘을 제공 하는 아키텍처 <xref:System.Windows.Input.Stylus> 입력을 디지털 잉크 만들 <xref:System.Windows.Ink.Stroke> 개체입니다. <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스는 사용자 지정 동작을 구현 하 고 최적의 성능을 위해 스타일러스 장치에서 가져온 데이터의 스트림에 적용 메커니즘을 제공 합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
-   [아키텍처](#Architecture)  
  
-   [스타일러스 플러그 인을 구현합니다.](#ImplementingStylusPlugins)  
  
-   [InkCanvas에 플러그 인 추가](#AddingYourPluginToAnInkCanvas)  
  
-   [결론](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>아키텍처  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에서 향상 된는 [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) 에 설명 된 Api [액세스 및 조작 펜 입력](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)에 [Microsoft Windows XP Tablet PC Edition 소프트웨어 개발 키트 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409)합니다.  
  
 각 <xref:System.Windows.UIElement> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 않는 속성이 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>합니다. 추가할 수 있습니다는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 요소를 <xref:System.Windows.UIElement.StylusPlugIns%2A> 조작 하는 속성 <xref:System.Windows.Input.StylusPoint> 그대로 데이터를 생성 합니다. <xref:System.Windows.Input.StylusPoint>데이터를 포함 하 여 시스템 디지타이저에서 지 원하는 모든 속성의 구성에서 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 포인트 데이터와 <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> 데이터입니다.  
  
 프로그램 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체가에서 가져온 데이터의 스트림으로 직접 삽입 되는 <xref:System.Windows.Input.Stylus> 추가할 때 장치는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성입니다. 플러그 인에 추가 되는 순서는 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션 받게 됩니다 순서가 결정 <xref:System.Windows.Input.StylusPoint> 데이터입니다. 예를 들어 특정 지역에 대 한 입력을 제한 하는 필터 플러그 인을 추가 하 고 작성 된 대로 제스처를 인식 하는 플러그 인을 추가 하는 경우 제스처를 인식 하는 플러그 인 받습니다 필터링 된 <xref:System.Windows.Input.StylusPoint> 데이터입니다.  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>스타일러스 플러그 인을 구현합니다.  
 플러그 인을 구현 하려면에서 클래스를 파생 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>합니다. 제공 하는 대로이 클래스는 스트림에 적용된 데이터는 <xref:System.Windows.Input.Stylus>합니다. 이 클래스에서의 값을 수정할 수는 <xref:System.Windows.Input.StylusPoint> 데이터입니다.  
  
> [!CAUTION]
>  경우는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throw 되거나 응용 프로그램이 종료 되므로 예외가 발생 합니다. 사용 하는 컨트롤을 철저히 테스트 해야는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 없을 경우에 컨트롤을 사용 하 고는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 예외를 throw 하지 것입니다.  
  
 다음 예제를 수정 하 여 스타일러스 입력을 제한 하는 플러그 인은 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 값에 <xref:System.Windows.Input.StylusPoint> 에서 나오는 데이터를는 <xref:System.Windows.Input.Stylus> 장치.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>InkCanvas에 플러그 인 추가  
 InkCanvas에서 파생 되는 클래스를 구현에 추가 하는 사용자 지정 플러그 인을 사용 하는 가장 쉬운 방법은 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성입니다.  
  
 다음 예제에서는 사용자 지정 <xref:System.Windows.Controls.InkCanvas> 잉크를 필터링 하 합니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 추가 하는 경우는 `FilterInkCanvas` 응용 프로그램을 실행 하려면를 알게 될 사용자가 스트로크를 완료 한 후 잉크 될 때까지 지역으로 제한 없음을 합니다. ¿¡´는 <xref:System.Windows.Controls.InkCanvas> 에 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 속성, 즉는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 소속 되어는 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션입니다. 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 추가 하는 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션 받는 <xref:System.Windows.Input.StylusPoint> 후 데이터 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 데이터를 수신 합니다. 결과적으로 <xref:System.Windows.Input.StylusPoint> 데이터는 사용자가 스트로크를 종료 하려면 펜 뗄 후까지 필터링 되지 것입니다. 삽입 해야 사용자가 그리는 처럼 잉크를 필터링 하려면는 `FilterPlugin` 하기 전에 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>합니다.  
  
 다음 C# 코드에서는 사용자 지정 <xref:System.Windows.Controls.InkCanvas> 를 그릴 때 잉크를 필터링 하 합니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>결론  
 직접 파생 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스와에 삽입 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 컬렉션, 디지털 잉크의 동작을 크게 향상 시킬 수 있습니다. 에 액세스할 수 있는 <xref:System.Windows.Input.StylusPoint> 으로 사용자 지정할 수 있도록 데이터를 생성 되는 <xref:System.Windows.Input.Stylus> 입력 합니다. 이러한 하위 수준 액세스를 갖고 있으므로 <xref:System.Windows.Input.StylusPoint> 데이터를 응용 프로그램에 대 한 잉크 컬렉션 및 최적의 성능으로 렌더링을 구현할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [고급 잉크 처리](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [액세스 및 조작을 펜 입력](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
