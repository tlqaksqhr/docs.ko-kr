---
title: "방법: Grid의 자식 요소 위치 지정 | Microsoft Docs"
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
  - "Grid 컨트롤, 자식 요소 위치 지정"
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Grid의 자식 요소 위치 지정
이 예제에서는 <xref:System.Windows.Controls.Grid>에 정의된 get 및 set 메서드를 사용하여 자식 요소의 위치를 지정하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 열과 행이 각각 세 개씩 있는 부모 <xref:System.Windows.Controls.Grid> 요소\(`grid1`\)를 정의합니다.  자식 <xref:System.Windows.Shapes.Rectangle> 요소\(`rect1`\)는 <xref:System.Windows.Controls.Grid>의 0열, 0행에 추가됩니다.  <xref:System.Windows.Controls.Button> 요소는 <xref:System.Windows.Controls.Grid> 내에서 <xref:System.Windows.Shapes.Rectangle> 요소의 위치를 다시 지정하기 위해 호출할 수 있는 메서드를 나타냅니다.  사용자가 단추를 클릭하면 관련 메서드가 활성화됩니다.  
  
 [!code-xml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 다음 코드 숨김 예제에서는 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 발생시키는 메서드를 처리합니다.  이 예제에서는 관련 get 메서드를 사용하는 <xref:System.Windows.Controls.TextBlock> 요소에 대해 이러한 메서드 호출을 작성하여 새 속성 값을 문자열로 출력합니다.  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Grid>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)