---
title: "미리 보기 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Preview events [WPF]
- suppressing events [WPF]
- events [WPF], Preview
- events [WPF], suppressing
ms.assetid: b5032308-aa9c-4d02-af11-630ecec8df7e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 04bdf32ea329ff25fd62255b4512d8a9d5703b8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="preview-events"></a>미리 보기 이벤트
이벤트를 터널링이 라고도 하는 미리 보기 이벤트는 라우트된 이벤트에서 이벤트를 발생 하 고 이벤트 데이터의 원본으로 보고 하는 요소에 대해 응용 프로그램 루트 경로 방향 전송 되는 위치입니다. 일부 이벤트 시나리오를 지원 하거나 미리 보기 이벤트; 요구 이 항목에서는 미리 보기 이벤트 있는, 응용 프로그램 또는 구성 요소 처리 방법을, 상황 및 사용자 지정 구성 요소 또는 클래스에서 미리 보기 이벤트를 만들 수 있는 적절 한 경우에 설명 합니다.  
  
## <a name="preview-events-and-input"></a>미리 보기 이벤트 및 입력  
 이벤트는 일반적으로 대해 주의 해야 하는 미리 보기를 처리 하는 경우 이벤트는 이벤트에서 처리 데이터입니다. 이외의 모든 요소에 대해 미리 보기 이벤트 처리 (이벤트 데이터에서 원본으로 보고 되는 요소) 발생 하는 요소는 효과가 발생 하는 이벤트를 처리 하는 요소를 제공 하지 합니다. 경우에 따라 해당 요소는 컨트롤의 관계에 존재 하는 경우에 특히 원하는 결과입니다.  
  
 입력된 이벤트에 대 한 구체적으로, 미리 보기 이벤트 또한 공유할 이벤트 데이터 인스턴스에 해당 하는 버블링 이벤트. 입력된 이벤트를 처리를 표시 하는 미리 보기 이벤트 클래스 처리기를 사용 하는 경우 버블링 입력된 이벤트 클래스 처리기가 호출 되지 않습니다. 또는 미리 보기 이벤트 인스턴스 처리기를 사용 하 여 처리 이벤트를 표시 하는 경우 버블링 이벤트에 대 한 처리기 일반적으로 호출 되지 않습니다. 클래스 처리기 또는 인스턴스를 등록 하거나 기술은 일반적으로 사용 되지 않습니다 이지만 해당 이벤트 처리, 됨으로 표시 되는 경우에 호출 되는 옵션과 함께 연결 수 있습니다.  
  
 클래스 처리 및 미리 보기 이벤트의 관계에 대 한 자세한 내용은 참조 [표시 라우트된 이벤트로 클래스를 처리 하 고,](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)합니다.  
  
### <a name="working-around-event-suppression-by-controls"></a>컨트롤에서 억제하는 이벤트 문제 해결  
 미리 보기 이벤트 일반적으로 사용 되는 한 가지 시나리오는 입력된 이벤트 처리 하는 복합 컨트롤입니다. 경우에 따라 컨트롤의 작성자가 컨트롤에서 자세한 정보를 전달 하거나 보다 구체적인 동작 하는 구성 요소에서 정의한 이벤트를 대체 하기 위해 원래 특정 이벤트를 표시 하지 않습니다. 예를 들어, 한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> 표시 하지 않습니다 <xref:System.Windows.UIElement.MouseLeftButtonDown> 및 <xref:System.Windows.UIElement.MouseLeftButtonDown> 버블링에서 발생 한 이벤트는 <xref:System.Windows.Controls.Button> 또는 마우스를 캡처 및 발생 시키기 위해 복합 요소는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 항상에 의해 발생 하는 이벤트는 <xref:System.Windows.Controls.Button> 자체입니다. 이벤트 및 해당 데이터는 경로 따라 계속 있지만 때문에 <xref:System.Windows.Controls.Button> 으로 이벤트 데이터를 표시 <xref:System.Windows.RoutedEventArgs.Handled%2A>를 특별히에서 작동 해야를 표시 하는 이벤트에 대 한 처리기만는 `handledEventsToo` 경우 호출 됩니다.  사용 하 여 코드의 처리기를 연결 하 한 대체 항목은 다른 응용 프로그램의 루트 요소에는 여전히 컨트롤 억제 이벤트를 처리할 수 있도록 하려면, 경우 `handledEventsToo` 로 지정 된 `true`합니다. 하지만 더 간단한 방법을 처리 하도록 입력된 이벤트의 미리 보기에 해당 하는 라우팅 방향을 변경 하는 경우가 많습니다. 예를 들어, 컨트롤 억제 하는 경우 <xref:System.Windows.UIElement.MouseLeftButtonDown>에 대 한 처리기를 연결 해 보십시오 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> 대신 합니다. 이 기술은 대해서만 작동의 입력된 이벤트와 같은 <xref:System.Windows.UIElement.MouseLeftButtonDown>합니다. 이러한 입력된 이벤트 터널/거품형 쌍을 사용 하 고 두 이벤트를 발생 시키고 이벤트 데이터를 공유 합니다.  
  
 이러한 기술은 각각의 부작용 또는 제한 사항 중 하나입니다. 미리 보기 이벤트를 처리의 부작용은 해당 시점 이벤트를 처리 하 고 버블링 이벤트를 처리 해야 하는 처리기를 비활성화할 수 있습니다 및 따라서 제한은 하다는 일반적으로 하지는 Previ에는 이벤트를 표시 하는 것이 좋습니다. 우 부분 경로입니다. 에 대 한 제한은 `handledEventsToo` 방법은 지정할 수 없습니다는 `handledEventsToo` 처리기 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 를 특성으로 등록 해야 이벤트 처리기 코드에서를 연결할 수는 처리기가 있는 요소에 대 한 개체 참조를 받은 후 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
