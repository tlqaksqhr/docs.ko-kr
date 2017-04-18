---
title: "방법: 계층적 XML 데이터에 마스터-세부 패턴 사용 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), 마스터-세부 데이터 패러다임"
  - "마스터-세부 데이터 패러다임"
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 계층적 XML 데이터에 마스터-세부 패턴 사용
이 예제에서는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터를 사용하여 마스터\-세부 시나리오를 구현하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제는 [계층적 데이터에 마스터\-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)에서 설명한 예제의 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 버전입니다.  이 예제에서는 데이터가 `League.xml` 파일에 있습니다.  세 번째 <xref:System.Windows.Controls.ListBox> 컨트롤이 두 번째 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 속성에 바인딩하여 해당 컨트롤에서의 선택 변경을 추적하는 방식을 확인하십시오.  
  
 [!code-xml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## 참고 항목  
 <xref:System.Windows.HierarchicalDataTemplate>   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)