---
title: "방법: GruopBox 템플릿 정의 | Microsoft Docs"
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
  - "컨트롤, GroupBox"
  - "GroupBox 컨트롤, 템플릿 만들기"
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: GruopBox 템플릿 정의
이 예제에서는 <xref:System.Windows.Controls.GroupBox> 컨트롤의 템플릿을 만드는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 레이아웃으로 <xref:System.Windows.Controls.Grid> 컨트롤을 사용하여 <xref:System.Windows.Controls.GroupBox> 컨트롤 템플릿을 정의합니다.  템플릿에서는 <xref:System.Windows.Controls.BorderGapMaskConverter>를 사용하여 <xref:System.Windows.Controls.GroupBox>의 테두리를 정의하기 때문에 테두리가 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 콘텐츠를 가리지 않습니다.  
  
 [!code-xml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.GroupBox>   
 [GroupBox How\-to Topics](http://msdn.microsoft.com/ko-kr/7692e155-a4c6-428c-b7e0-64b3740daca7)