---
title: "방법: RowGroups 속성을 통한 표의 행 그룹 조작 | Microsoft Docs"
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
  - "문서, RowGroups 속성을 통해 행 그룹 조작"
  - "속성, RowGroups, 행 그룹 조작"
  - "행 그룹, RowGroups 속성을 통해 조작"
  - "RowGroups 속성, 행 그룹 조작"
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: RowGroups 속성을 통한 표의 행 그룹 조작
이 예제에서는 <xref:System.Windows.Documents.Table.RowGroups%2A> 속성을 통해 테이블의 행 그룹에서 수행할 수 있는 보다 일반적인 작업 중 몇 가지를 보여 줍니다.  
  
## 예제  
 다음 예제에서는 새 테이블을 만들고 <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> 메서드를 사용하여 열을 테이블의 <xref:System.Windows.Documents.Table.RowGroups%2A> 컬렉션에 추가합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## 예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.TableRowGroup>을 삽입합니다.  새 열이 인덱스 위치 0에 삽입되어 해당 열은 테이블의 첫 번째 새 행 그룹이 됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableRowGroupCollection> 컬렉션은 0부터 시작하는 표준 인덱스를 사용합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## 예제  
 다음 예제에서는 테이블의 특정 <xref:System.Windows.Documents.TableRowGroup>\(인덱스로 지정\)에 여러 행을 추가합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## 예제  
 다음 예제에서는 테이블의 첫 번째 행 그룹에 있는 행에서 몇 가지 임의의 속성에 액세스합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## 예제  
 다음 예제에서는 테이블의 특정 <xref:System.Windows.Documents.TableRow>\(인덱스로 지정\)에 여러 셀을 추가합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## 예제  
 다음 예제에서는 첫 번째 행 그룹의 첫 번째 행에 있는 셀에서 몇 가지 임의의 메서드와 속성에 액세스합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## 예제  
 다음 예제에서는 테이블에서 호스팅하는 <xref:System.Windows.Documents.TableRowGroup> 요소의 숫자를 반환합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## 예제  
 다음 예제에서는 참조를 사용하여 특정 행 그룹을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## 예제  
 다음 예제에서는 인덱스를 사용하여 특정 행 그룹을 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## 예제  
 다음 예제에서는 테이블의 행 그룹 컬렉션에서 행 그룹을 모두 제거합니다.  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## 참고 항목  
 [How\-to: Manipulate Flow Content Elements through the Inlines Property](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Blocks 속성을 통한 FlowDocument 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Columns 속성을 통해 표의 열 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)