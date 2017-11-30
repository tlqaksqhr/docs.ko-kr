---
title: "방법: 계층적 XML 데이터에 마스터-세부 패턴 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b28a2220b5fc86654fe054deb9180450025f72f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>방법: 계층적 XML 데이터에 마스터-세부 패턴 사용
사용 하 여 마스터-세부 정보 시나리오를 구현 하는 방법을 보여 주는이 예제 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터입니다.  
  
## <a name="example"></a>예제  
 이 예제는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터 버전의 예제에서 설명한 [마스터-세부 패턴을 사용 하 여 계층적 데이터로](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)합니다. 이 예제에서는 파일에서 데이터는 `League.xml`합니다. 참고 어떻게 세 번째 <xref:System.Windows.Controls.ListBox> 컨트롤의 두 번째에서 선택을 변경 내용을 추적 <xref:System.Windows.Controls.ListBox> 에 바인딩하여 해당 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 속성입니다.  
  
 [!code-xaml[MasterDetailXml#HowTo1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
