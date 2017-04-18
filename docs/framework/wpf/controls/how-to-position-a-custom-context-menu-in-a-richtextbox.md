---
title: "방법: RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정 | Microsoft Docs"
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
  - "사용자 지정 상황에 맞는 메뉴 위치 지정"
  - "사용자 지정 상황에 맞는 메뉴 위치 지정"
  - "RichTextBox 컨트롤을 사용자 지정 상황에 맞는 메뉴 위치 지정"
  - "상황에 맞는 메뉴 위치 지정"
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: RichTextBox에서 사용자 지정 상황에 맞는 메뉴의 위치 지정
에 대 한 사용자 지정 상황에 맞는 메뉴를 배치 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
 에 대 한 사용자 지정 상황에 맞는 메뉴를 구현 하는 경우는 **RichTextBox**, 상황에 맞는 메뉴의 위치도 책임이 있습니다.  기본적으로 사용자 지정 상황에 맞는 메뉴의 중심이 열릴는 **RichTextBox**합니다.  
  
## <a name="example"></a>예제  
 기본 배치 동작을 재정의 하려면 추가 대 한 수신기는 <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> 이벤트입니다.  다음 예제에서는이 작업을 프로그래밍 방식으로 수행 하는 방법을 보여 줍니다.  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 해당 구현을 <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> 이벤트 수신기입니다.  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a>참고 항목  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)