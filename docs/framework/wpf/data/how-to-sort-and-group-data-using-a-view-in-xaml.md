---
title: "방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c219def87e258a2c9fc1bf4f4867287e6156c59a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화
데이터 컬렉션의 보기를 만드는 방법을 보여 주는이 예제 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. 그룹화, 정렬, 필터링의 기능 및 현재 항목의 개념에 대 한 뷰를 통해.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정적 리소스 이름이 *배치* 의 컬렉션으로 정의 *위치* 각 개체 *위치* 도시 이름으로 구성 된 개체 및 상태입니다. 접두사 *src* 네임 스페이스에 매핑되어 있는 데이터 원본 *위치* 정의 됩니다. 접두사 *scm* 매핑됩니다 `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` 및 *dat* 매핑됩니다 `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`합니다.  
  
 다음 예에서는 도시 이름을 기준으로 정렬 되며 상태에 따라 그룹화 된 데이터 컬렉션의 뷰를 만듭니다.  
  
 [!code-xaml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 다음 예제와 같이 바인딩 소스 뷰 될 수 있습니다.  
  
 [!code-xaml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 에 정의 된 XML 데이터에 대 한 바인딩의 <xref:System.Windows.Data.XmlDataProvider> 리소스를 XML 이름 앞에 @ 기호입니다.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.CollectionViewSource>  
 [데이터 수집의 기본 뷰 가져오기](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
