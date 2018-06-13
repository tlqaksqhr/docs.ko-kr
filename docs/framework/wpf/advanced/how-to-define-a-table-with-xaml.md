---
title: '방법: XAML로 테이블 정의'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 2a35a27567d962fc125cb3c408ccab95afa222af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543103"
---
# <a name="how-to-define-a-table-with-xaml"></a>방법: XAML로 테이블 정의
다음 예제에서는 정의 하는 <xref:System.Windows.Documents.Table> 를 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.  예제 테이블에 4 개의 열 (나타내는 <xref:System.Windows.Documents.TableColumn> 요소) 및 여러 행 (나타내는 <xref:System.Windows.Documents.TableRow> 요소) 뿐만 데이터가 포함 된 제목, 머리글 및 바닥글 정보.  행에 포함 되어야 합니다는 <xref:System.Windows.Documents.TableRowGroup> 요소입니다.  테이블의 각 행은 하나 이상의 셀의 구성 (나타내는 <xref:System.Windows.Documents.TableCell> 요소).  표 셀의 내용에 포함 되어야 합니다는 <xref:System.Windows.Documents.Block> 요소;이 경우 <xref:System.Windows.Documents.Paragraph> 요소를 사용 합니다.  테이블에 하이퍼링크도 호스팅합니다 (나타내는 <xref:System.Windows.Documents.Hyperlink> 요소) 바닥글 행에 있습니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 다음 그림에서는 이 예제에 정의된 테이블이 렌더링되는 방법을 보여 줍니다.  
  
 ![렌더링된 테이블.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")
