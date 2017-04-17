---
title: "방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거 | Microsoft Docs"
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
  - "목록 보기, 목록 항목 추가"
  - "ListView 컨트롤[Windows Forms], 목록 항목 추가"
  - "ListView 컨트롤[Windows Forms], 채우기"
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤에 항목을 추가하는 프로세스는 주로 항목을 지정하고 이 항목에 속성을 할당하는 프로세스로 구성됩니다.  언제든지 목록 항목을 추가하거나 제거할 수 있습니다.  
  
### 항목을 프로그래밍 방식으로 추가하려면  
  
1.  <xref:System.Windows.Forms.ListView.Items%2A> 속성의 <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> 메서드를 사용합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### 프로그래밍 방식으로 항목을 제거하려면  
  
1.  <xref:System.Windows.Forms.ListView.Items%2A> 속성의 <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> 또는 <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> 메서드를 사용합니다.  <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> 메서드는 항목 하나를 제거하며 <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> 메서드는 목록에 있는 항목을 모두 제거합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListView>   
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)