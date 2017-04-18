---
title: "방법: 이벤트 처리기에서 소스 요소 찾기 | Microsoft Docs"
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
  - "이벤트 처리기, 소스 요소 찾기"
  - "이벤트 처리기의 소스 요소"
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 이벤트 처리기에서 소스 요소 찾기
이 예제에서는 이벤트 처리기에서 소스 요소를 찾는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 코드 숨김 파일에서 선언되는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기를 보여 줍니다.  처리기가 연결된 단추를 사용자가 클릭하면 처리기가 속성 값을 변경합니다.  처리기 코드는 이벤트 인수에서 보고되는 라우트된 이벤트 데이터의 <xref:System.Windows.RoutedEventArgs.Source%2A> 속성을 사용하여 <xref:System.Windows.RoutedEventArgs.Source%2A> 요소에서 <xref:System.Windows.FrameworkElement.Width%2A> 속성 값을 변경합니다.  
  
 [!code-xml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## 참고 항목  
 <xref:System.Windows.RoutedEventArgs>   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)