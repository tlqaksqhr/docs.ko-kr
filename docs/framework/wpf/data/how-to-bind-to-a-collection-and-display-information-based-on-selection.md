---
title: "방법: 선택에 따라 수집 및 표시 정보에 바인딩 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), 컬렉션에 바인딩"
  - "데이터 바인딩(data binding), 데이터 컬렉션의 뷰 만들기"
  - "데이터 바인딩(data binding), 뷰에 대해 데이터 선택"
  - "데이터 컬렉션, 뷰에 대해 데이터 선택"
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 선택에 따라 수집 및 표시 정보에 바인딩
간단한 마스터\-세부 시나리오에서는 <xref:System.Windows.Controls.ListBox>와 같은 데이터 바인딩된 <xref:System.Windows.Controls.ItemsControl>을 사용합니다.  사용자가 선택하는 내용에 따라 선택된 항목에 대한 추가 정보를 표시합니다.  이 예제에서는 이 시나리오를 구현하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서 `People`은 `Person` 클래스의 <xref:System.Collections.ObjectModel.ObservableCollection%601>입니다.  이 `Person` 클래스에는 `FirstName`, `LastName`, `HomeTown`의 세 가지 속성이 있으며 모두 `string` 형식입니다.  
  
 [!code-xml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <xref:System.Windows.Controls.ContentControl>은 `Person`의 정보가 제공되는 방식을 정의하는 다음 <xref:System.Windows.DataTemplate>을 사용합니다.  
  
 [!code-xml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 다음은 예제에서 생성하는 사항의 스크린 샷입니다.  <xref:System.Windows.Controls.ContentControl>은 선택된 사람의 다른 속성을 보여 줍니다.  
  
 ![컬렉션에 바인딩](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding\_CollectionBindingSample")  
  
 이 예제에서 주목해야 할 두 가지 내용은 다음과 같습니다.  
  
1.  <xref:System.Windows.Controls.ListBox>와 <xref:System.Windows.Controls.ContentControl>은 같은 소스에 바인딩됩니다.  두 컨트롤 모두 전체 컬렉션 개체에 대한 바인딩이므로 두 바인딩의 <xref:System.Windows.Data.Binding.Path%2A> 속성은 지정되지 않습니다.  
  
2.  이 시나리오가 제대로 작동하기 위해서는 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 속성을 `true`로 설정해야 합니다.  이 속성을 설정하면 선택한 항목이 항상 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>으로 설정됩니다.  <xref:System.Windows.Controls.ListBox>가 <xref:System.Windows.Data.CollectionViewSource>에서 데이터를 가져오는 경우에는 선택 항목과 통화가 자동으로 동기화됩니다.  
  
 `Person` 클래스는 다음과 같은 방법으로 `ToString` 메서드를 재정의합니다.  기본적으로 <xref:System.Windows.Controls.ListBox>는 `ToString`을 호출하고 바인딩된 컬렉션에 있는 각 개체의 문자열 표현을 표시합니다.  따라서 각 `Person`이 <xref:System.Windows.Controls.ListBox>에 이름으로 나타납니다.  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## 참고 항목  
 [계층적 데이터에 마스터\-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)   
 [계층적 XML 데이터에 마스터\-세부 패턴 사용](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)