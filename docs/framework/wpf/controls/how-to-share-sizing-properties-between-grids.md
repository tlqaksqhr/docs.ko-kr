---
title: "방법: 모눈 간 크기 조정 속성 공유 | Microsoft Docs"
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
  - "Grid 컨트롤, 열 크기 조정 데이터 공유"
  - "Grid 컨트롤, 행 크기 조정 데이터 공유"
  - "Grid 컨트롤의 크기 조정 데이터"
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 모눈 간 크기 조정 속성 공유
이 예제에서는 <xref:System.Windows.Controls.Grid> 요소 간에 열과 행의 크기 조정 데이터를 공유하여 크기가 일관되게 조정되도록 유지하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 두 개의 <xref:System.Windows.Controls.Grid> 요소를 부모 <xref:System.Windows.Controls.DockPanel>의 자식 요소로 사용합니다.  <xref:System.Windows.Controls.Grid>의 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> [연결된 속성](GTMT)은 부모 <xref:System.Windows.Controls.DockPanel>에서 정의됩니다.  
  
 이 예제에서는 각 요소가 부울 속성 값 중 하나를 나타내는 <xref:System.Windows.Controls.Button> 요소 두 개를 사용하여 속성 값을 조작합니다.  <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> 속성 값이 `true`로 설정되어 있으면 <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A>의 열 또는 행 멤버 각각이 행 또는 열의 콘텐츠에 관계없이 크기 조정 정보를 공유합니다.  
  
 [!code-xml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 다음 코드 숨김 예제에서는 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 발생시키는 메서드를 처리합니다.  이 예제에서는 관련 get 메서드를 사용하는 <xref:System.Windows.Controls.TextBlock> 요소에 이러한 메서드 호출의 결과를 작성하여 새 속성 값을 문자열로 출력합니다.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)