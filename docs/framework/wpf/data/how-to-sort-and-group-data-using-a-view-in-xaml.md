---
title: "방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), XAML의 뷰에서 데이터 그룹화"
  - "데이터 바인딩(data binding), XAML의 뷰에서 데이터 정렬"
  - "XAML의 뷰에서 데이터 그룹화"
  - "XAML의 뷰에서 데이터 정렬"
  - "뷰, 데이터 그룹화"
  - "뷰, 데이터 정렬"
  - "XAML, 뷰에서 데이터 그룹화"
  - "XAML, 뷰에서 데이터 정렬"
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화
이 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 데이터 수집의 뷰를 만드는 방법을 보여 줍니다.  뷰에서는 그룹화, 정렬 및 필터링 기능과 현재 항목이라는 개념을 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서 *places*라는 정적 리소스는 각 *Place* 개체가 도시 이름 및 주 이름으로 구성된 *Place* 개체 컬렉션으로 정의됩니다.  *src* 접두사는 데이터 소스인 *Places*가 정의된 네임스페이스에 매핑됩니다.  *scm* 및 *dat* 접두사는 각각 `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` 및 `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`에 매핑됩니다.  
  
 다음 예제에서는 도시 이름별로 정렬되고 주 이름별로 그룹화된 데이터 수집의 뷰를 만듭니다.  
  
 [!code-xml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 그러면 뷰는 다음 예제와 같이 바인딩 소스가 될 수 있습니다.  
  
 [!code-xml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <xref:System.Windows.Data.XmlDataProvider> 리소스에 정의된 XML 데이터에 대한 바인딩의 경우 XML 이름 앞에 @ 기호를 추가합니다.  
  
 [!code-xml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## 참고 항목  
 <xref:System.Windows.Data.CollectionViewSource>   
 [데이터 수집의 기본 뷰 가져오기](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)