---
title: "방법: 텍스트 입력 체계 변경 | Microsoft Docs"
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
  - "Typography 특성 설정"
  - "Typography 특성, 설정"
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# 방법: 텍스트 입력 체계 변경
다음 예제에서는 <xref:System.Windows.Documents.Paragraph>를 예제 요소로 사용하여 <xref:System.Windows.Documents.TextElement.Typography%2A> 특성을 설정하는 방법을 보여 줍니다.  
  
## 예제  
 [!code-xml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 다음 그림에서는 이 예제가 렌더링되는 방법을 보여 줍니다.  
  
 ![스크린 샷: 입력 체계가 변경된 텍스트](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement\_Typog")  
  
 한편 다음 그림에서는 비슷한 예제에서 기본 입력 체계 속성을 사용할 때 렌더링되는 모습을 보여 줍니다.  
  
 ![스크린 샷: 입력 체계가 변경된 텍스트](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement\_Typog\_Default")  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.TextBox.Typography%2A> 속성을 프로그래밍 방식으로 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## 참고 항목  
 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)