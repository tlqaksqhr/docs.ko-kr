---
title: "방법: XAML로 표 정의 | Microsoft Docs"
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
  - "문서, XAML로 테이블 정의"
  - "테이블, XAML로 정의"
  - "XAML, 테이블 디자인"
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: XAML로 표 정의
다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 <xref:System.Windows.Documents.Table>을 정의하는 방법을 보여 줍니다.  예제 테이블에는 데이터를 비롯하여 제목, 머리글 및 바닥글 정보를 포함하는 4개의 열\(<xref:System.Windows.Documents.TableColumn> 요소로 표시\)과 여러 개의 행\(<xref:System.Windows.Documents.TableRow> 요소로 표시\)이 있습니다.  행은 <xref:System.Windows.Documents.TableRowGroup> 요소에 포함되어야 합니다.  테이블의 각 행은 하나 이상의 셀\(<xref:System.Windows.Documents.TableCell> 요소로 표시\)로 구성됩니다.  테이블 셀의 콘텐츠는 <xref:System.Windows.Documents.Block> 요소에 포함되어야 합니다. 이 경우 <xref:System.Windows.Documents.Paragraph> 요소가 사용됩니다.  또한 테이블은 바닥글 행에서 하이퍼링크\(<xref:System.Windows.Documents.Hyperlink> 요소로 표시\)를 호스팅합니다.  
  
## 예제  
 [!code-xml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 다음 그림에서는 이 예제에 정의된 테이블이 렌더링되는 방법을 보여 줍니다.  
  
 ![렌더링된 표](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")