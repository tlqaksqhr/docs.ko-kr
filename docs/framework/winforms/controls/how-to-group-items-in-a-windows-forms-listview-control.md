---
title: "방법: Windows Forms ListView 컨트롤에서 항목 그룹화 | Microsoft Docs"
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
  - "그룹화"
  - "그룹"
  - "그룹, Windows Forms 컨트롤"
  - "목록 보기, 항목 그룹화"
  - "목록, 항목 그룹화"
  - "ListView 컨트롤[Windows Forms], 항목 그룹화"
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: Windows Forms ListView 컨트롤에서 항목 그룹화
<xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 기능을 사용하여 관련 항목 집합을 그룹으로 표시할 수 있습니다.  이러한 그룹은 그룹 제목이 포함된 가로 그룹 헤더에 의해 화면에서 분리됩니다.  <xref:System.Windows.Forms.ListView> 그룹을 사용하면 사전순, 날짜순 또는 기타 논리적 그룹화 기준으로 항목을 그룹화하여 긴 목록을 쉽게 탐색할 수 있습니다.  다음 이미지는 그룹화된 일부 항목을 보여 줍니다.  
  
 ![ListView 그룹](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
ListView의 그룹화된 항목  
  
 그룹화를 사용하려면 먼저 하나 이상의 그룹을 디자이너에서 또는 프로그래밍 방식으로 만들어야 합니다.  그룹을 정의한 다음에는 <xref:System.Windows.Forms.ListView> 항목을 그룹에 할당할 수 있습니다.  또한 프로그래밍 방식으로 항목을 특정 그룹에서 다른 그룹으로 이동할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> 그룹은 응용 프로그램에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> 메서드를 호출할 때 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]에서만 사용할 수 있습니다.  이전 버전의 운영 체제에서는 그룹 관련 코드가 영향을 주지 않으며 그룹도 표시되지 않습니다.  자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>를 참조하십시오.  
  
### 그룹을 추가하려면  
  
1.  <xref:System.Windows.Forms.ListView.Groups%2A> 컬렉션의 <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 메서드를 사용합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### 그룹을 제거하려면  
  
1.  <xref:System.Windows.Forms.ListView.Groups%2A> 컬렉션의 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 또는 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드를 사용합니다.  
  
     <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 메서드는 그룹 하나를 제거하며 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드는 목록에 있는 그룹을 모두 제거합니다.  
  
    > [!NOTE]
    >  그룹을 제거해도 그룹 내에 있는 항목은 제거되지 않습니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### 항목을 그룹에 할당하거나 그룹 간에 항목을 이동하려면  
  
1.  개별 항목의 <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=fullName> 속성을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ListViewGroup>   
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ko-kr/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)