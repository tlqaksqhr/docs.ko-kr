---
title: "방법: 여러 줄 TextBox 컨트롤 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 244eb38ea47bbd7376c2f8c6f5b2609fbd9c4330
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-multiline-textbox-control"></a>방법: 여러 줄 TextBox 컨트롤 만들기
사용 하는 방법을 보여 주는이 예제 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 <xref:System.Windows.Controls.TextBox> 컨트롤을 여러 줄의 텍스트를 수용 하기 위해 자동으로 확장 됩니다.  
  
## <a name="example"></a>예제  
 설정의 <xref:System.Windows.Controls.TextBox.TextWrapping%2A> 특성을 **줄 바꿈** 입력 한 텍스트를 배치할 새 하면 경우 줄의 가장자리는 <xref:System.Windows.Controls.TextBox> 컨트롤은에 도달 하면 자동으로 확장 되는 <xref:System.Windows.Controls.TextBox> 경우 새 줄을 위한 공간을 포함 하도록 컨트롤 필요 합니다.  
  
 설정의 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> 특성을 **true** 다시 한 번 자동으로 확장 되 RETURN 키를 누를 때 삽입할 새 줄의 <xref:System.Windows.Controls.TextBox> 필요 하면 새 줄을 위한 공간을 포함 합니다.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> 스크롤 막대를 추가 하는 특성은 <xref:System.Windows.Controls.TextBox>되도록의 내용을 <xref:System.Windows.Controls.TextBox> if 스크롤할 수는 <xref:System.Windows.Controls.TextBox> 프레임 또는 포함 하는 창의 크기를 넘어 확장 합니다.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.TextWrapping>  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
