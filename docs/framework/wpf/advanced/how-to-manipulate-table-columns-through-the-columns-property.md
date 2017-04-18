---
title: "방법: Columns 속성을 통해 표의 열 조작 | Microsoft Docs"
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
  - "Columns 속성"
  - "문서, 표 열 조작"
  - "속성, 열, 표 열 조작"
  - "테이블, 열 조작"
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: Columns 속성을 통해 표의 열 조작
이 예제에서는 <xref:System.Windows.Documents.Table.Columns%2A> 속성을 통해 테이블의 열에서 수행할 수 있는 보다 일반적인 작업 중 몇 가지를 보여 줍니다.  
  
## 예제  
 다음 예제에서는 새 테이블을 만들고 <xref:System.Windows.Documents.TableColumnCollection.Add%2A> 메서드를 사용하여 열을 테이블의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션에 추가합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## 예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.TableColumn>을 삽입합니다.  새 열이 인덱스 위치 0에 삽입되어 해당 열은 테이블의 첫 번째 새 열이 됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableColumnCollection> 컬렉션은 0부터 시작하는 표준 인덱스를 사용합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## 예제  
 다음 예제에서는 인덱스로 특정 열을 참조하여 <xref:System.Windows.Documents.TableColumnCollection> 컬렉션의 열에 있는 몇 가지 임의의 속성에 액세스합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## 예제  
 다음 예제에서는 테이블에 의해 현재 호스팅되는 열의 수를 가져옵니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## 예제  
 다음 예제에서는 참조를 사용하여 특정 열을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## 예제  
 다음 예제에서는 인덱스를 사용하여 특정 열을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## 예제  
 다음 예제에서는 테이블의 열 컬렉션에서 열을 모두 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## 참고 항목  
 [표 개요](../../../../docs/framework/wpf/advanced/table-overview.md)   
 [XAML로 표 정의](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)   
 [프로그래밍 방식으로 표 작성](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)   
 [RowGroups 속성을 통한 표의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Blocks 속성을 통한 FlowDocument 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [RowGroups 속성을 통한 표의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)