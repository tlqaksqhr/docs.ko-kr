---
title: "방법: Grid를 사용하여 표준 UI 대화 상자 빌드 | Microsoft Docs"
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
  - "대화 상자, 만들기"
  - "Grid 컨트롤, 만들기, 대화 상자"
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Grid를 사용하여 표준 UI 대화 상자 빌드
이 예제에서는 <xref:System.Windows.Controls.Grid> 요소를 사용하여 표준 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 대화 상자를 만드는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 운영 체제의 **실행** 대화 상자와 같은 대화 상자를 만듭니다.  
  
 이 예제에서는 <xref:System.Windows.Controls.Grid>를 만들고 <xref:System.Windows.Controls.ColumnDefinition> 및 <xref:System.Windows.Controls.RowDefinition> 클래스를 사용하여 다섯 개의 열과 네 개의 행을 정의합니다.  
  
 그런 다음 <xref:System.Windows.Controls.Image>, `RunIcon.png`를 추가하고 배치하여 대화 상자의 이미지를 나타냅니다.  이미지는 <xref:System.Windows.Controls.Grid>의 첫 번째 열과 행\(왼쪽 위 모퉁이\)에 배치됩니다.  
  
 다음으로, 첫 번째 열에 <xref:System.Windows.Controls.TextBlock> 요소를 추가하여 첫 번째 행의 나머지 열까지 포함하고,  다른 <xref:System.Windows.Controls.TextBlock> 요소를 첫 번째 열의 두 번째 행에 추가하여 **열기** 텍스트 상자를 나타냅니다.  뒤를 이어 데이터 입력 영역을 나타내는 <xref:System.Windows.Controls.TextBlock>을 하나 더 추가합니다.  
  
 최종적으로 **확인**, **취소** 및 **찾아보기** 이벤트를 각각 나타내는 세 개의 <xref:System.Windows.Controls.Button> 요소를 마지막 행에 추가합니다.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.GridUnitType>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)