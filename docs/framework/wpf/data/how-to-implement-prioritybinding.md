---
title: "방법: PriorityBinding 구현 | Microsoft Docs"
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
  - "클래스, PriorityBinding"
  - "데이터 바인딩(data binding), PriorityBinding 클래스"
  - "PriorityBinding 클래스"
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: PriorityBinding 구현
바인딩의 목록을 지정하면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 <xref:System.Windows.Data.PriorityBinding>이 작동합니다.  바인딩 목록은 가장 높은 우선 순위에서 가장 낮은 우선 순위로 나열되어 있습니다.  가장 우선 순위가 높은 바인딩이 처리될 때 성공적으로 값이 반환되면 목록의 다른 바인딩을 처리할 필요가 없어집니다.  가장 우선 순위가 높은 바인딩이 계산되는 데 시간이 오래 걸리는 경우 다음으로 우선 순위가 높은 바인딩에서 성공적으로 값이 반환되면 가장 우선 순위가 높은 바인딩이 성공적으로 값이 반환될 때까지 이 바인딩이 사용됩니다.  
  
## 예제  
 <xref:System.Windows.Data.PriorityBinding>이 작동하는 방식을 보여 주기 위해 `FastDP`, `SlowerDP` 및 `SlowestDP` 속성을 사용하여 `AsyncDataSource` 개체를 만들었습니다.  
  
 `FastDP`의 get 접근자에서 `_fastDP` 데이터 멤버의 값을 반환합니다.  
  
 `SlowerDP`의 get 접근자는 `_slowerDP` 데이터 멤버의 값을 반환하기 전에 3초간 기다립니다.  
  
 `SlowestDP`의 get 접근자는 `_slowestDP` 데이터 멤버의 값을 반환하기 전에 5초간 기다립니다.  
  
> [!NOTE]
>  이 예제는 예시 목적으로만 제공됩니다.  필드 집합보다 더 느린 대량 주문인 속성을 정의하는 데 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 지침을 사용하는 것이 좋습니다.  자세한 내용은 [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/ko-kr/55825e8f-7e2e-448a-9505-7217cc91b1af)을 참조하십시오.  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성은 <xref:System.Windows.Data.PriorityBinding>을 사용하는 위의 `AsyncDS`에 바인딩됩니다.  
  
 [!code-xml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 바인딩 엔진이 <xref:System.Windows.Data.Binding> 개체를 처리할 때 `SlowestDP` 속성에 바인딩된 첫 번째 <xref:System.Windows.Data.Binding>에서 시작합니다.  이 <xref:System.Windows.Data.Binding>이 처리되면 5초 동안 대기하기 때문에 성공적으로 값이 반환되지 않으므로 다음 <xref:System.Windows.Data.Binding> 요소가 처리됩니다.  다음 <xref:System.Windows.Data.Binding>은 3초 동안 대기하기 때문에 값이 성공적으로 반환되지 않습니다.  그런 다음 바인딩 엔진은 `FastDP` 속성에 바인딩되어 있는 다음 <xref:System.Windows.Data.Binding> 요소로 이동합니다.  이 <xref:System.Windows.Data.Binding>은 "Fast Value" 값을 반환합니다.  이제 <xref:System.Windows.Controls.TextBlock>은 "Fast Value" 값을 표시합니다.  
  
 3초가 경과되면 `SlowerDP` 속성이 "Slower Value" 값을 반환합니다.  그런 다음 <xref:System.Windows.Controls.TextBlock>에서 "Slower Value" 값을 표시합니다.  
  
 5초가 경과되면 `SlowestDP` 속성이 "Slowest Value" 값을 반환합니다.  이 바인딩은 맨 처음에 나열되어 있기 때문에 가장 높은 우선 순위를 갖습니다.  이제 <xref:System.Windows.Controls.TextBlock>은 "Slowest Value" 값을 표시합니다.  
  
 바인딩에서 성공적인 반환 값으로 간주되는 내용에 대한 자세한 내용은 <xref:System.Windows.Data.PriorityBinding>을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=fullName>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)