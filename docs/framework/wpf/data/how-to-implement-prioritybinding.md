---
title: "방법: PriorityBinding 구현"
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
helpviewer_keywords: data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e6ab8826f2298a8660a85d739fbe3456374b476
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-implement-prioritybinding"></a>방법: PriorityBinding 구현
<xref:System.Windows.Data.PriorityBinding>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 바인딩의 목록을 지정 하 여 작동 합니다. 바인딩 목록은 가장 낮은 우선 순위를 높은 우선 순위에서 정렬 됩니다. 우선 순위가 높은 바인딩이 값을 반환 하는 경우 성공적으로 처리 될 때 다음는 없습니다 목록에 다른 바인딩을 처리할 필요가 있습니다. 우선 순위가 높은 바인딩이 평가할 오랜 시간이 걸리는 경우 수, 다음 우선 순위가 가장 높은 값을 성공적으로 반환 하는 더 높은 우선 순위의 바인딩 값을 성공적으로 반환 될 때까지 사용 됩니다.  
  
## <a name="example"></a>예  
 설명 하기 위해 어떻게 <xref:System.Windows.Data.PriorityBinding> 작동는 `AsyncDataSource` 다음 세 가지 속성을 가진 개체가 생성 되었음을: `FastDP`, `SlowerDP`, 및 `SlowestDP`합니다.  
  
 get 접근자 `FastDP` 의 값을 반환 된 `_fastDP` 데이터 멤버입니다.  
  
 get 접근자 `SlowerDP` 의 값을 반환 하기 전에 3 초 동안 대기는 `_slowerDP` 데이터 멤버입니다.  
  
 get 접근자 `SlowestDP` 의 값을 반환 하기 전에 5 초 동안 대기는 `_slowestDP` 데이터 멤버입니다.  
  
> [!NOTE]
>  이 예제는 예시용입니다. [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 지침 속성 필드 집합 보다 더 느린 대량 주문 인을 정의 하는 것이 좋습니다. 자세한 내용은 참조 [NIB: 메서드와 속성 사이의 선택](http://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af)합니다.  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성이 바인딩됩니다 위의 `AsyncDS` 를 사용 하 여 <xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 바인딩 엔진에서 처리 하는 경우는 <xref:System.Windows.Data.Binding> 개체를 처음으로 시작 <xref:System.Windows.Data.Binding>에 바인딩된는 `SlowestDP` 속성입니다. 때이 <xref:System.Windows.Data.Binding> 은 처리를 반환 하지 않습니다 값을 성공적으로 대기 하기 5 초 동안 하므로 다음 때문에 <xref:System.Windows.Data.Binding> 요소가 처리 됩니다. 다음 <xref:System.Windows.Data.Binding> 값 반환 하지 않습니다는 성공적으로 3 초 동안 대기 하기 때문에 있습니다. 바인딩 엔진에 있는 다음 다음 이동 <xref:System.Windows.Data.Binding> 에 바인딩되는 요소는 `FastDP` 속성입니다. 이 <xref:System.Windows.Data.Binding> "빠른" 값을 반환 합니다. <xref:System.Windows.Controls.TextBlock> 이제 "빠른" 값을 표시 합니다.  
  
 3 초 경과 된 `SlowerDP` 속성 "느린 Value" 값을 반환 합니다. <xref:System.Windows.Controls.TextBlock> "느린" 값을 표시 합니다.  
  
 5 초 동안 경과 된 `SlowestDP` 속성 "가장 느린 Value" 값을 반환 합니다. 해당 바인딩을 첫 번째로 나열 되어 있으므로 가장 높은 우선 순위를 갖습니다. <xref:System.Windows.Controls.TextBlock> 이제 "가장 느린" 값을 표시 합니다.  
  
 참조 <xref:System.Windows.Data.PriorityBinding> 간주 되는 바인딩에서 성공적인 반환 값에 대 한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
