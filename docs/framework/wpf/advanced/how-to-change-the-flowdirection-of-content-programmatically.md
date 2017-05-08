---
title: "방법: 프로그래밍 방식으로 콘텐츠의 FlowDirection 변경 | Microsoft Docs"
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
  - "문서, 프로그래밍 방식으로 FlowDirection 속성 변경"
  - "FlowDirection 속성, 프로그래밍 방식으로 변경"
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 프로그래밍 방식으로 콘텐츠의 FlowDirection 변경
이 예제에서는 <xref:System.Windows.Controls.FlowDocumentReader>의 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 프로그래밍 방식으로 변경하는 방법을 보여 줍니다.  
  
## 예제  
 각각 <xref:System.Windows.FlowDirection>의 가능한 값 중 하나를 나타내는 두 <xref:System.Windows.Controls.Button> 요소가 만들어집니다.  단추를 클릭하면 연결된 속성 값이 `tf1`이라는 <xref:System.Windows.Controls.FlowDocumentReader>의 콘텐츠에 적용됩니다.  속성 값은 `txt1`이라는 <xref:System.Windows.Controls.TextBlock>에도 기록됩니다.  
  
 [!code-xml[FlowDirectionSnippets#_FlowDirectionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## 예제  
 위에 정의된 단추 클릭과 연결된 이벤트는 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 코드 숨김 파일에서 처리됩니다.  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]