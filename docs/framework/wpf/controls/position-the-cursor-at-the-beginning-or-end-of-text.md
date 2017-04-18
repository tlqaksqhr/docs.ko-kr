---
title: "방법: TextBox 컨트롤의 텍스트 시작 또는 끝 위치에 커서 놓기 | Microsoft Docs"
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
  - "커서 위치 지정"
  - "TextBox 컨트롤을 커서 위치 지정"
  - "커서의 위치 지정"
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: TextBox 컨트롤의 텍스트 시작 또는 끝 위치에 커서 놓기
시작과 끝의 텍스트 내용 중에 커서를 배치 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox> 제어 합니다.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드에 설명 된 <xref:System.Windows.Controls.TextBox> 제어 하 고 이름을 할당 합니다.  
  
 [!code-xml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>예제  
 내용의 시작 부분에 커서를 배치 하는 <xref:System.Windows.Controls.TextBox> 제어 하 고, 호출는 <xref:System.Windows.Controls.TextBox.Select%2A> 메서드 선택 시작 선택 길이를 0 및 0의 위치를 지정 합니다.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>예제  
 내용의 끝에 커서를 놓습니다는 <xref:System.Windows.Controls.TextBox> 제어 하 고, 호출는 <xref:System.Windows.Controls.TextBox.Select%2A> 메서드 하 고 콘텐츠를 텍스트의 길이 선택 길이를 0 선택 시작 위치를 지정 합니다.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)