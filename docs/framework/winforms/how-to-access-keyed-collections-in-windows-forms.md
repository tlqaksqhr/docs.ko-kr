---
title: "방법: Windows Forms에서 키 컬렉션 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컬렉션, 키를 사용하여 액세스"
  - "키 컬렉션[Windows Forms]"
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: Windows Forms에서 키 컬렉션 액세스
-   키로 개별 컬렉션 항목에 액세스할 수 있습니다.  Windows Forms 응용 프로그램에서 일반적으로 사용되는 여러 컬렉션 클래스에 이 기능이 추가되었습니다.  다음 목록에서는 액세스할 수 있는 키 컬렉션이 있는 일부 컬렉션 클래스를 보여 줍니다.  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 컬렉션의 항목과 연결된 키는 일반적으로 항목의 이름입니다.  다음 절차에서는 컬렉션 클래스를 사용하여 일반적인 작업을 수행하는 방법을 보여 줍니다.  
  
### 컨트롤 컬렉션에서 중첩된 컨트롤을 찾고 해당 컨트롤로 포커스를 이동하려면  
  
-   <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> 및 <xref:System.Windows.Forms.Control.Focus%2A> 메서드를 사용하여, 찾아서 포커스를 이동하려는 컨트롤의 이름을 지정합니다.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### 이미지 컬렉션의 이미지에 액세스하려면  
  
-   <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> 속성을 사용하여 액세스할 이미지의 이름을 지정합니다.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### 탭 페이지를 선택된 탭으로 설정하려면  
  
-   <xref:System.Windows.Forms.TabControl.SelectedTab%2A> 속성과 <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> 속성을 함께 사용하여 선택된 탭으로 설정할 탭 페이지의 이름을 지정합니다.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## 참고 항목  
 [Windows Forms 시작](../../../docs/framework/winforms/getting-started-with-windows-forms.md)   
 [방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)