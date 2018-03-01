---
title: "방법: ContextMenuOpening 이벤트 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5eec8646a48f94fb9ffdcad14849416732618a06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>방법: ContextMenuOpening 이벤트 처리
<xref:System.Windows.FrameworkElement.ContextMenuOpening> 는 기존 상황에 맞는 메뉴 표시 하기 전에를 설정 하 여 표시 되는 메뉴를 표시 하지 않는 조정 하거나 응용 프로그램에서 이벤트를 처리할 수 있습니다는 <xref:System.Windows.RoutedEventArgs.Handled%2A> 속성을 `true` 이벤트 데이터에서입니다. 설정에 대 한 일반적인 이유 <xref:System.Windows.RoutedEventArgs.Handled%2A> 를 `true` 새으로 완전 하 게 메뉴를 바꾸려면 데이터는 이벤트 <xref:System.Windows.Controls.ContextMenu> 개체, 경우에 따라 작업을 취소 하 고 새 열기를 시작 해야 합니다. 에 대 한 처리기를 작성 하는 경우는 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 이벤트를 알고 있어야 간의 타이밍 문제는 <xref:System.Windows.Controls.ContextMenu> 컨트롤과 열고 일반적 컨트롤에 대 한 상황에 맞는 메뉴의 위치를 지정 하는 일을 담당 하는 서비스입니다. 이 항목 열기 시나리오는 다양 한 상황에 맞는 메뉴에 대 한 코드 기술 중 일부를 보여 및 타이밍 문제에 제공 된 위치 하는 경우를 보여 줍니다.  
  
 처리를 위해 일부 시나리오는 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 이벤트:  
  
-   먼저 호출한 다음 표시 메뉴 항목을 조정할 수 있습니다.  
  
-   전체 메뉴 표시 하기 전에 교체 합니다.  
  
-   완전히 기존 상황에 맞는 메뉴를 억제 하 고 상황에 맞는 메뉴 표시 합니다.  
  
## <a name="example"></a>예  
  
## <a name="adjusting-the-menu-items-before-display"></a>먼저 호출한 다음 표시 메뉴 항목을 조정합니다.  
 기존 메뉴 항목을 조정은 매우 단순 하 고 아마도 가장 일반적인 시나리오입니다. 추가 하거나 응용 프로그램의 현재 상태 정보 또는 상황에 맞는 메뉴 요청 된 개체의 속성으로 사용할 수 있는 특정 상태 정보에 대 한 응답에서 상황에 맞는 메뉴 옵션 빼려는 하기 위해 이렇게 할 수 있습니다.  
  
 일반적인 방법은 하는 특정 컨트롤을 마우스 오른쪽 단추로 클릭 된 이벤트의 소스는 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 에서 속성입니다. 여부를 확인 하려면 일반적으로 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션 이미의 메뉴에 다음을 추가 하거나 제거 적절 한 새 컨텍스트 메뉴 항목을 <xref:System.Windows.Controls.MenuItem> 컬렉션에서 항목을 합니다.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>전체 메뉴 표시 하기 전에 교체합니다.  
 다른 시나리오는 전체 상황에 맞는 메뉴를 교체 하려면. 물론 앞의 코드에서의 변형 기존 상황에 맞는 메뉴의 모든 항목을 제거 하 고 항목 0부터 시작 하는 새 값을 추가 하려면도 사용할 수 있습니다. 상황에 맞는 메뉴에 있는 모든 항목을 교체 하는 보다 직관적인 방법을 새로 만들 수는 있지만 <xref:System.Windows.Controls.ContextMenu>고 항목을 채우고 다음 설정의 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> 을 새 컨트롤의 속성 <xref:System.Windows.Controls.ContextMenu>합니다.  
  
 다음은 대체 하기 위해 간단한 처리기 코드는 <xref:System.Windows.Controls.ContextMenu>합니다. 코드는 사용자 지정 참조 `BuildMenu` 분산 되어 있는 호출 되기 때문에 둘 이상의 예제 처리기에서 메서드.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 그러나이 스타일에 대 한 처리기를 사용 하는 경우 <xref:System.Windows.FrameworkElement.ContextMenuOpening>, 하는 경우 타이밍 문제를 잠재적으로 노출할 수 있습니다 설정 하는 개체는 <xref:System.Windows.Controls.ContextMenu> 기존 상황에 맞는 메뉴에는 없습니다. 사용자 컨트롤을 마우스 오른쪽 단추로 클릭할 때 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 발생 하는 경우에 기존 <xref:System.Windows.Controls.ContextMenu> 비어 있거나 null입니다. 하지만 경우는 새 <xref:System.Windows.Controls.ContextMenu> 원본에 설정 요소 표시할 너무 늦게 도착 합니다. 또한 사용자를 두 번째로 마우스 오른쪽 단추로 클릭을 경우. 이때 새 <xref:System.Windows.Controls.ContextMenu> 나타나면 값이 null이 아닌 한 제대로 처리기 바꾸고 메뉴 처리기를 두 번 실행 될 때 표시 됩니다. 이 인해 두 가지 가능한 해결 방법:  
  
1.  시킬 수 있도록 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 항상 최소 하나의 자리 표시자를 가진 컨트롤에 대해 실행 되는 처리기 <xref:System.Windows.Controls.ContextMenu> 를 사용할 수 처리기 코드로 대체 하는 데 있습니다. 이 경우 이전 예제에 표시 된 처리기를 여전히 사용할 수 있지만 일반적으로 자리 표시자를 할당 하려면 <xref:System.Windows.Controls.ContextMenu> 초기 태그에서:  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2.  가정 초기 <xref:System.Windows.Controls.ContextMenu> 값 null 일 수 일부 예비 논리를 기반 합니다. 할 수 있는지 확인 <xref:System.Windows.Controls.ContextMenu> null 또는 처리기 지 여부를 확인 하기 위해 코드에 플래그를 사용 하 여에 대 한 한 번 이상를 실행 합니다. 한다고 가정 하기 때문에 <xref:System.Windows.Controls.ContextMenu> 다음을 설정 하는 방법에 대 한 수를 표시, 처리기 <xref:System.Windows.RoutedEventArgs.Handled%2A> 를 `true` 이벤트 데이터에서입니다. 에 <xref:System.Windows.Controls.ContextMenuService> 상황에 맞는 메뉴 표시를 담당 하는 한 `true` 에 대 한 값 <xref:System.Windows.RoutedEventArgs.Handled%2A> 이벤트 데이터 컨트롤 이벤트를 발생 시킨 조합 / 상황에 맞는 메뉴에 대 한 표시 취소 요청을 나타냅니다.  
  
 다음 단계 새 대시보드를 제공 하는 잠재적으로 의심 스러운 상황에 맞는 메뉴, 압축 했으므로 표시 합니다. 하나는 기본적으로 이전 처리기와 동일 하 게 새 설정: 새 빌드할 <xref:System.Windows.Controls.ContextMenu> 컨트롤 소스를 설정 하 고 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> 와 합니다. 추가 단계는 상황에 맞는 메뉴의 표시를 강제로 이제 해야 첫 번째 시도 억제 되기 때문입니다. 설정 표시를 강제로 표시 하려면는 <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> 속성을 `true` 처리기 내에서. 이렇게 하면 때문에 기해야 발생 처리기에서 상황에 맞는 메뉴를 열고는 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 이벤트 다시 합니다. 처리기를 다시 입력 됩니다 무한 재귀. 이 때문에 대 한 확인 해야 하는 항상 `null` 하거나 내에서 상황에 맞는 메뉴를 열면 플래그를 사용 하 여 한 <xref:System.Windows.FrameworkElement.ContextMenuOpening> 이벤트 처리기입니다.  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>모든 기존 상황에 맞는 메뉴를 표시 하지 않는 및 상황에 맞는 메뉴 표시  
 메뉴를 완전히을 억제 하는 처리기를 작성 하는 마지막 시나리오가 않습니다. 제공 된 컨트롤의 상황에 맞는 메뉴를 표시 하지 않는, 경우에이 보장 하기 보다는 사용자가 요청할 때 메뉴를 억제 하 여 보다 적합할 가지가 있습니다. 처리기를 상황에 맞는 메뉴를 표시 하지 않고 아무것도 표시에 사용 하려는 경우 처리기 설정 해야 하지만 <xref:System.Windows.RoutedEventArgs.Handled%2A> 를 `true` 이벤트 데이터에서입니다. <xref:System.Windows.Controls.ContextMenuService> 하는 상황에 맞는 메뉴를 표시 하는 확인 컨트롤에서 발생 하는 이벤트의 이벤트 데이터에 대해 책임이 있습니다. 이벤트로 표시 되어 있으면 <xref:System.Windows.RoutedEventArgs.Handled%2A> 위치 경로 따르는 다음 이벤트를 시작한 상황에 맞는 메뉴 열기 작업 표시 되지 않습니다.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>  
 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [ContextMenu 개요](../../../../docs/framework/wpf/controls/contextmenu-overview.md)
