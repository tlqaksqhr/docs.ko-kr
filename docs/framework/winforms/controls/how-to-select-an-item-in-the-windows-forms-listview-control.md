---
title: "방법: Windows Forms ListView 컨트롤에서 항목 선택 | Microsoft Docs"
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
  - "목록 보기, 항목 선택"
  - "목록, 항목 선택"
  - "ListView 컨트롤[Windows Forms], 항목 선택"
  - "선택, 목록 보기"
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: Windows Forms ListView 컨트롤에서 항목 선택
이 예제에서는 Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤에서 프로그래밍 방식으로 항목을 선택하는 방법을 보여 줍니다.  프로그래밍 방식으로 항목을 선택하면 <xref:System.Windows.Forms.ListView> 컨트롤에 대한 포커스가 자동으로 바뀌지 않습니다.  따라서 항목을 선택할 때 해당 항목에 포커스가 오도록 설정하려는 것이 일반적입니다.  
  
## 예제  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   항목이 최소한 하나 이상 포함되어 있고 이름이 `listView1`인 <xref:System.Windows.Forms.ListView> 컨트롤  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 네임스페이스에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=fullName>