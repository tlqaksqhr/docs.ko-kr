---
title: "방법: 단락 사이 간격 조정 | Microsoft Docs"
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
  - "문서, 단락 사이 간격 조정"
  - "단락, 간격"
  - "단락 사이 간격"
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 단락 사이 간격 조정
이 예제에서는 유동 콘텐츠의 단락 사이 간격을 조정하거나 제거하는 방법을 보여 줍니다.  
  
 유동 콘텐츠에서 단락 사이에 나타나는 여유 간격은 이러한 단락에 설정된 여백 때문이므로 해당 단락의 여백을 조정하여 단락 사이의 간격을 제어할 수 있습니다.  두 단락 사이의 여유 간격을 모두 제거하려면 단락의 여백을 **0**으로 설정합니다.  전체 <xref:System.Windows.Documents.FlowDocument>에서 단락 사이의 간격을 균일하게 하려면 <xref:System.Windows.Documents.FlowDocument>의 모든 단락에 대해 균일한 여백 값을 설정하는 스타일을 사용합니다.  
  
 인접한 두 단락의 여백은 두 배가 되는 것이 아니라 두 여백 중에서 더 큰 여백으로 "축소"됩니다.  즉, 인접한 두 단락의 여백이 각각 20픽셀과 40픽셀인 경우 단락 사이의 간격은 두 개의 여백 값 중 더 큰 값인 40픽셀이 됩니다.  
  
## 예제  
 다음 예제에서는 스타일을 사용하여 <xref:System.Windows.Documents.FlowDocument>에 있는 모든 <xref:System.Windows.Documents.Paragraph> 요소에 대한 여백을 **0**으로 설정합니다. 이 값은 <xref:System.Windows.Documents.FlowDocument>에 있는 단락 사이의 여유 간격을 효과적으로 제거합니다.  
  
 [!code-xml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]