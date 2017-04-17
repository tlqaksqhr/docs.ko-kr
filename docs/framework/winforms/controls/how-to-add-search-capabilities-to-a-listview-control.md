---
title: "방법: ListView 컨트롤에 검색 기능 추가 | Microsoft Docs"
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
  - "목록 보기, 검색 사용"
  - "목록, 검색 사용"
  - "ListView 컨트롤[Windows Forms], 검색 기능 추가"
  - "검색, ListView 컨트롤에 검색 기능 추가"
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: ListView 컨트롤에 검색 기능 추가
<xref:System.Windows.Forms.ListView> 컨트롤에서 대용량 항목 목록을 자주 사용하여 작업하는 경우 사용자에게 검색 기능을 제공할 수 있습니다.  <xref:System.Windows.Forms.ListView> 컨트롤은 텍스트 일치 방법과 위치 검색 방법으로 이 기능을 제공합니다.  
  
 검색 문자열과 선택적 시작 및 끝 인덱스가 제공될 경우 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드를 사용하여 목록 또는 자세히 보기의 <xref:System.Windows.Forms.ListView>에서 텍스트를 검색할 수 있습니다.  반대로 X 좌표, Y 좌표 및 검색 방향이 지정된 경우 <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드를 사용하여 아이콘 또는 Tile 보기의 <xref:System.Windows.Forms.ListView>에서 항목을 찾을 수 있습니다.  
  
### 텍스트를 사용하여 항목을 찾으려면  
  
1.  <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View> 또는 <xref:System.Windows.Forms.View>로 설정하여 <xref:System.Windows.Forms.ListView>를 만든 다음 <xref:System.Windows.Forms.ListView>에 항목을 채웁니다.  
  
2.  <xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드를 호출하여 찾을 항목의 텍스트를 전달합니다.  
  
3.  다음 코드 예제에서는 기본 <xref:System.Windows.Forms.ListView>를 만들고 항목을 채운 다음 사용자가 입력한 텍스트를 사용하여 목록에서 항목을 찾는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### X 좌표와 Y 좌표를 사용하여 항목을 찾으려면  
  
1.  <xref:System.Windows.Forms.View> 속성을 <xref:System.Windows.Forms.View> 또는 <xref:System.Windows.Forms.View>으로 설정하여 <xref:System.Windows.Forms.ListView>를 만든 다음 <xref:System.Windows.Forms.ListView>에 항목을 채웁니다.  
  
2.  <xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드를 호출하여 원하는 X 및 Y 좌표와 검색 방향을 전달합니다.  
  
3.  다음 코드 예제에서는 기본 아이콘 <xref:System.Windows.Forms.ListView>를 만들고 항목을 채운 다음 <xref:System.Windows.Forms.Control.MouseDown> 이벤트를 캡처하여 위쪽 방향으로 가장 가까운 항목을 찾는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A>   
 <xref:System.Windows.Forms.ListView.FindNearestItem%2A>   
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)