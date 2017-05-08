---
title: "방법: CompositeCollection 구현 | Microsoft Docs"
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
  - "클래스, CompositeCollection"
  - "데이터 바인딩(data binding), CompositeCollection 클래스"
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: CompositeCollection 구현
## 예제  
 다음 예제에서는 <xref:System.Windows.Data.CompositeCollection> 클래스를 사용하여 여러 컬렉션 및 항목을 하나의 목록으로 표시하는 방법을 보여 줍니다.  이 예제에서 `GreekGods`는 `GreekGod` 사용자 지정 개체의 <xref:System.Collections.ObjectModel.ObservableCollection%601>입니다.  `GreekGod` 개체와 `GreekHero` 개체가 황금색 및 녹청 전경색으로 각각 나타나도록 데이터 템플릿이 정의됩니다.  
  
 [!code-xml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## 참고 항목  
 <xref:System.Windows.Data.CollectionContainer>   
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>   
 <xref:System.Windows.Data.XmlDataProvider>   
 <xref:System.Windows.DataTemplate>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)