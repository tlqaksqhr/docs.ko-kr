---
title: "방법: Windows Forms ListView 컨트롤에 열 추가 | Microsoft Docs"
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
  - "열[Windows Forms], ListView 컨트롤에 추가"
  - "목록 보기, 열 추가"
  - "ListView 컨트롤[Windows Forms], 열 머리글 추가"
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms ListView 컨트롤에 열 추가
자세히 보기에서 <xref:System.Windows.Forms.ListView> 컨트롤은 각 목록 항목에 대해 여러 개의 열을 표시할 수 있습니다.  여러 개의 열을 사용하면 각 목록 항목에 대한 여러 유형의 정보를 사용자에게 표시할 수 있습니다.  예를 들어, 파일 목록에 파일 이름, 파일 형식, 파일 크기 및 파일을 마지막으로 수정한 날짜를 표시할 수 있습니다.  만들어진 열을 채우는 방법에 대한 자세한 내용은 [방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)를 참조하십시오.  
  
### 프로그래밍 방식으로 열을 추가하려면  
  
1.  컨트롤의 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View>로 설정합니다.  
  
2.  목록 보기에 있는 <xref:System.Windows.Forms.ListView.Columns%2A> 속성의 <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> 메서드를 사용합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListView>   
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)