---
title: "방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d734a7f17f8843ff284ac0854ac41d4a5b9f5584
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>방법: XAML의 바인딩에 사용할 수 있는 데이터 만들기
이 항목에는 여러 가지 방법을 사용할 수 있게 만드는 데이터에 대 한 바인딩에서는 설명 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]응용 프로그램의 필요에 따라 합니다.  
  
## <a name="example"></a>예제  
 있는 경우는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체에서 바인딩할 원하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 사용할 수 있게 만드는 개체 바인딩 리소스로 정의 하 고 지정 하는 것 방법 중 하나는 `x:Key`합니다. 다음 예제는 `Person` 라는 문자열 속성이 있는 개체 `PersonName`합니다. `Person` 개체가 라는 네임 스페이스에 정의 된 `SDKSample`합니다.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 개체에 바인딩할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]다음 예제에 나온 것 처럼 합니다.  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 사용할 수 있습니다는 <xref:System.Windows.Data.ObjectDataProvider> 다음 예제와 같이 클래스입니다.  
  
 [!code-xaml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 바인딩을 정의 동일한 방식으로:  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 이 예의 경우 결과: 있는 <xref:System.Windows.Controls.TextBlock> 텍스트 콘텐츠로 `Joe`합니다. 그러나는 <xref:System.Windows.Data.ObjectDataProvider> 클래스 메서드의 결과에 바인딩할 수와 같은 기능을 제공 합니다. 사용 하도록 선택할 수는 <xref:System.Windows.Data.ObjectDataProvider> 클래스 제공 하는 기능이 필요 합니다.  
  
 그러나 이미 만들어져 있는 개체에 바인딩하는 경우 설정 해야는 `DataContext` 다음 예제와 같이 코드에서.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 에 액세스 하려면 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 바인딩 사용에 대 한 데이터는 <xref:System.Windows.Data.XmlDataProvider> 클래스를 참조 하십시오. [XMLDataProvider 및 XPath 쿼리가 사용 하 여 XML 데이터에 바인딩할](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)합니다. 에 액세스 하려면 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 바인딩 사용에 대 한 데이터는 <xref:System.Windows.Data.ObjectDataProvider> 클래스를 참조 하십시오. [XML 쿼리 결과 대 한 XDocument, XElement, 또는 LINQ를 바인딩할](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)합니다.  
  
 바인딩하는 데이터를 지정할 수 있는 다양 한 방법에 대 한 내용은 참조 하십시오. [바인딩 소스를 지정할](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)합니다. 어떤 유형의 데이터를 바인딩할 수 있습니다 또는 자체적으로 구현 하는 방법에 대 한 내용은 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 바인딩에 대 한 개체 참조 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
