---
title: '방법: 바인딩 업데이트 알림 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: 896ce103361590dceecccf8534fd330aabe18086
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-up-notification-of-binding-updates"></a>방법: 바인딩 업데이트 알림 설정
이 예제에서는 바인딩의 바인딩 대상(대상) 또는 바인딩 소스(소스) 속성이 업데이트될 경우 알림을 받도록 설정하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]은 바인딩 소스 또는 대상이 업데이트될 때마다 데이터 업데이트 이벤트를 발생시킵니다. 내부적으로 이 이벤트는 바인딩된 데이터가 변경되었기 때문에 업데이트 작업을 수행해야 함을 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 알리는 데 사용됩니다. 작동 하도록 하는 이러한 이벤트에 대 한 한도 제대로 작동 하려면 단방향 또는 양방향 바인딩이, 할 경우 사용 하 여 데이터 클래스를 구현 하는 참고는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스입니다. 자세한 내용은 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조하세요.  
  
 설정의 <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> 또는 <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> 를 속성 (또는 둘 다) `true` 바인딩에 합니다. 이 이벤트를 수신하기 위해 제공하는 처리기는 변경 내용에 대한 알림을 받을 요소에 직접 연결하거나, 컨텍스트의 내용이 변경되었는지 여부를 알고 싶은 경우 전체 데이터 컨텍스트에 연결해야 합니다.  
  
 다음 예제에서는 대상 속성이 업데이트될 경우 알림을 받도록 설정하는 방법을 보여 줍니다.  
  
 [!code-xaml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 그런 다음 EventHandler\<T> 대리자(이 예제에서는 *OnTargetUpdated*)를 기반으로 처리기를 할당하여 이벤트를 처리할 수 있습니다.  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 이벤트의 매개 변수를 사용하여 변경된 속성에 대한 정보(둘 이상의 요소에 같은 처리기가 연결된 경우 형식 또는 특정 요소)를 확인할 수 있습니다. 이는 단일 요소에 바인딩된 속성이 여러 개 있는 경우 유용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
