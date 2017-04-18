---
title: "방법: Windows Forms ListView 컨트롤의 아이콘 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "아이콘, ListView 컨트롤에 표시"
  - "ImageList 구성 요소[Windows Forms], ListView 컨트롤 사용"
  - "목록 보기, 아이콘 표시"
  - "목록, 아이콘 표시"
  - "ListView 컨트롤[Windows Forms], 아이콘 표시"
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Forms ListView 컨트롤의 아이콘 표시
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤을 사용하여 세 가지 이미지 목록의 아이콘을 표시할 수 있습니다.  목록, 자세히 및 작은 아이콘 보기는 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성에 지정된 이미지 목록에서 이미지를 표시하고  큰 아이콘 보기는 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 속성에 지정된 이미지 목록에서 이미지를 표시합니다.  또한 목록 뷰는 <xref:System.Windows.Forms.ListView.StateImageList%2A> 속성에 설정된 추가 아이콘 집합을 큰 아이콘 또는 작은 아이콘 옆에 표시할 수도 있습니다.  이미지 목록에 대한 자세한 내용은 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 및 [방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 참조하십시오.  
  
### 목록 뷰에 이미지를 표시하려면  
  
1.  사용할 기존 <xref:System.Windows.Forms.ImageList> 구성 요소를 <xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A> 또는 <xref:System.Windows.Forms.ListView.StateImageList%2A> 속성에 설정합니다.  
  
     이러한 속성은 디자이너의 속성 창을 사용하거나 코드를 통해 설정할 수 있습니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  아이콘이 연결되어 있는 각 목록 항목에 대해 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 또는 <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> 속성을 설정합니다.  
  
     이러한 속성은 **ListViewItem 컬렉션 편집기**를 사용하거나 코드를 통해 설정할 수 있습니다.  **ListViewItem 컬렉션 편집기**를 열려면 **속성** 창에서 <xref:System.Windows.Forms.ListView.Items%2A> 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭하십시오.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## 참고 항목  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가\(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)