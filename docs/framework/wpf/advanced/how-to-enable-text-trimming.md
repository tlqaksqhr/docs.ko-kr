---
title: "방법: 텍스트 잘라내기 사용 | Microsoft Docs"
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
  - "문서, 텍스트 트리밍"
  - "텍스트, 제거"
  - "텍스트 트리밍"
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 텍스트 잘라내기 사용
이 예제에서는 <xref:System.Windows.TextTrimming> 열거형에서 사용할 수 있는 값의 사용 및 효과를 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> 특성 집합과 함께 <xref:System.Windows.Controls.TextBlock> 요소를 정의합니다.  
  
 [!code-xml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## 예제  
 다음 코드에서는 해당 <xref:System.Windows.TextTrimming> 속성을 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 텍스트 잘라내기에는 현재 세 가지 옵션인 **CharacterEllipsis**, **WordEllipsis** 및 **None**이 있습니다.  
  
 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A>이 **CharacterEllipsis**로 설정되면 텍스트가 잘리고 잘리는 가장자리에서 가장 가까운 문자에 줄임표가 사용됩니다.  이 설정은 잘리는 경계에 좀 더 가깝게 맞추어 텍스트를 잘라내기 때문에 단어가 부분적으로 잘릴 수 있습니다.  다음 그림에서는 위의 정의와 유사한 <xref:System.Windows.Controls.TextBlock>으로 이 설정의 효과를 보여 줍니다.  
  
 ![예제: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming\_Character")  
  
 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A>이 **WordEllipsis**로 설정되면 텍스트가 잘리고 잘리는 가장자리에서 가장 가까운 첫 번째 전체 단어 끝에서 줄임표가 사용됩니다.  이 설정은 부분적으로 잘라낸 단어를 표시하지 않고, **CharacterEllipsis** 설정처럼 잘라낸 가장자리와 가깝게 텍스트를 잘라내지도 않습니다.  다음 그림에서는 위에 정의된 <xref:System.Windows.Controls.TextBlock>으로 이 설정의 효과를 보여 줍니다.  
  
 ![예제: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming\_Word")  
  
 <xref:System.Windows.Controls.TextBlock.TextTrimming%2A>이 **None**으로 설정되면 텍스트가 잘리지 않습니다.  이 경우 텍스트가 부모 텍스트 컨테이너의 경계로 잘릴 뿐입니다.  다음 그림에서는 위의 정의와 유사한 <xref:System.Windows.Controls.TextBlock>으로 이 설정의 효과를 보여 줍니다.  
  
 ![예제: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming\_None")