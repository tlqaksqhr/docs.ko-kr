---
title: "방법: 바인딩 방향 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9944ff214a9dfe12b21e005c4e1998c249bf72b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>방법: 바인딩 방향 지정
이 예제에서는 바인딩으로 바인딩 대상(대상) 속성만 업데이트되는지, 바인딩 소스(소스) 속성만 업데이트되는지 아니면 대상 속성과 소스 속성이 모두 업데이트되는지 여부를 지정하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 사용 된 <xref:System.Windows.Data.Binding.Mode%2A> 바인딩의 방향을 지정 하는 속성입니다. 다음 열거 목록에서는 바인딩 업데이트에 사용할 수 있는 옵션을 보여 줍니다.  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay>대상 속성 또는 원본 속성이 변경 될 때마다 대상 속성 또는 속성을 업데이트 합니다.  
  
-   <xref:System.Windows.Data.BindingMode.OneWay>source 속성을 변경 하는 경우에 대상 속성을 업데이트 합니다.  
  
-   <xref:System.Windows.Data.BindingMode.OneTime>응용 프로그램을 시작 하는 경우에 되거나 대상 속성 업데이트는 <xref:System.Windows.FrameworkElement.DataContext%2A> 가 변경 합니다.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource>대상 속성이 변경 될 때 원본 속성을 업데이트 합니다.  
  
-   <xref:System.Windows.Data.BindingMode.Default>그러면 기본 <xref:System.Windows.Data.Binding.Mode%2A> 대상 속성 값을 사용할 수 있습니다.  
  
 자세한 내용은 <xref:System.Windows.Data.BindingMode> 열거형을 참조하세요.  
  
 다음 예제에서는 <xref:System.Windows.Data.Binding.Mode%2A> 속성을 설정하는 방법을 보여 줍니다.  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 소스 변경 내용을 검색 하려면 (적용할 <xref:System.Windows.Data.BindingMode.OneWay> 및 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩), 소스와 같은 적절 한 속성 변경 알림 메커니즘을 구현 해야 <xref:System.ComponentModel.INotifyPropertyChanged>합니다. 참조 [속성 변경 알림을 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) 의 예는 <xref:System.ComponentModel.INotifyPropertyChanged> 구현 합니다.  
  
 에 대 한 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩 소스 업데이트의 타이밍을 설정 하 여 제어할 수 있습니다는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성입니다. 자세한 내용은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.Binding>  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
