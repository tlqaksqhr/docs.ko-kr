---
title: "방법: ListBox의 스크롤 성능 개선 | Microsoft Docs"
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
  - "ListBox 컨트롤[WPF], 스크롤 성능 향상"
  - "ListBox 컨트롤[WPF], 항목 컨테이너 다시 사용"
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: ListBox의 스크롤 성능 개선
<xref:System.Windows.Controls.ListBox>에 항목이 여러 개 포함되어 있으면 사용자가 마우스 휠을 사용하거나 스크롤 막대의 엄지 단추를 끌어 <xref:System.Windows.Controls.ListBox>를 스크롤할 때 사용자 인터페이스 응답이 느릴 수 있습니다.  <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> 연결된 속성을 <xref:System.Windows.Controls.VirtualizationMode>으로 설정하면 사용자가 스크롤할 때의 <xref:System.Windows.Controls.ListBox> 성능을 높일 수 있습니다.  
  
## 예제  
  
## 설명  
 다음 예제에서는 <xref:System.Windows.Controls.ListBox>를 만들고 <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName>를 <xref:System.Windows.Controls.VirtualizationMode>으로 설정하여 스크롤 성능을 높입니다.  
  
## 코드  
 [!code-xml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 다음 예제에서는 이전 예제에서 사용한 데이터를 보여 줍니다.  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]