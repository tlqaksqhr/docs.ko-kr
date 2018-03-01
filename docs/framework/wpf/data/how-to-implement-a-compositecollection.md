---
title: "방법: CompositeCollection 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b33e3a61b91c2f9e2362a270216038d61770b815
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-a-compositecollection"></a>방법: CompositeCollection 구현
## <a name="example"></a>예  
 다음 예제에서는 여러 컬렉션 및 항목을 사용 하 여 하나의 목록으로 표시 하는 방법을 보여 줍니다는 <xref:System.Windows.Data.CompositeCollection> 클래스입니다. 이 예제에서는 `GreekGods` 는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 의 `GreekGod` 사용자 지정 개체입니다. 데이터 템플릿이 정의 되어 있도록 `GreekGod` 개체 및 `GreekHero` 개체 각각 녹청 전경색은와 함께 표시 합니다.  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.CollectionContainer>  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>  
 <xref:System.Windows.Data.XmlDataProvider>  
 <xref:System.Windows.DataTemplate>  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
