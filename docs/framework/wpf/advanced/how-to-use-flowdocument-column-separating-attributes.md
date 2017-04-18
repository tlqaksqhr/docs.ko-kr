---
title: "방법: FlowDocument 열 구분 속성 사용 | Microsoft Docs"
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
  - "열 구분 특성"
  - "문서, FlowDocument 열 구분 특성"
  - "FlowDocument 열 구분 특성"
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: FlowDocument 열 구분 속성 사용
이 예제에서는 <xref:System.Windows.Documents.FlowDocument>의 열 구분 기능을 사용하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.FlowDocument>를 정의하고 <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> 및 <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> 특성을 설정합니다.  <xref:System.Windows.Documents.FlowDocument>에는 샘플 콘텐츠의 단일 단락이 포함되어 있습니다.  
  
 [!code-xml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 다음 그림에서는 렌더링된 <xref:System.Windows.Documents.FlowDocument>에서 <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A> 및 <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> 특성의 효과를 보여 줍니다.  
  
 ![스크린 샷: FlowDocument 내부 열](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")