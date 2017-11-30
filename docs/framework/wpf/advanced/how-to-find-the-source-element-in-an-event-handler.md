---
title: "방법: 이벤트 처리기에서 소스 요소 찾기"
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
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e9746683ec5b7ad142591c2b419f9af21be8d69c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>방법: 이벤트 처리기에서 소스 요소 찾기
이 예제에는 이벤트 처리기에서 원본 요소를 찾는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 코드 숨김 파일에 선언 된 이벤트 처리기입니다. 처리기에 연결 되어 있는 단추를 클릭 처리기 속성 값을 변경 합니다. 처리기 코드를 사용 하 여는 <xref:System.Windows.RoutedEventArgs.Source%2A> 변경 하는 이벤트 인수에서 보고 되는 라우트된 이벤트 데이터의 <xref:System.Windows.FrameworkElement.Width%2A> 속성 값에는 <xref:System.Windows.RoutedEventArgs.Source%2A> 요소입니다.  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.RoutedEventArgs>  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
