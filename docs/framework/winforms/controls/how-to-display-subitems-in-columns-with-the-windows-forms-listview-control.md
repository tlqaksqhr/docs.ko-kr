---
title: "방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시 | Microsoft Docs"
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
  - "자세히 보기"
  - "목록 항목"
  - "ListView 컨트롤[Windows Forms], ListSubItems 추가"
  - "하위 항목"
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤을 사용하여 자세히 보기의 각 항목에 대해 추가 텍스트 또는 하위 항목을 표시할 수 있습니다.  첫째 열에는 직원 번호와 같은 항목 텍스트를 표시하고  둘째, 셋째 및 다음 열에는 첫째, 둘째 및 다음 열과 관련된 하위 항목을 표시합니다.  
  
### 목록 항목에 하위 항목을 추가하려면  
  
1.  필요한 열을 추가합니다.  첫째 열에는 항목의 <xref:System.Windows.Forms.ListView.Text%2A> 속성이 표시되므로 총 하위 항목 수보다 열이 하나 더 필요합니다.  열을 추가하는 데 대한 자세한 내용은 [방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)를 참조하십시오.  
  
2.  항목의 <xref:System.Windows.Forms.ListViewItem.SubItems%2A> 속성에서 반환된 컬렉션의 <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> 메서드를 호출합니다.  아래 코드 예제에서는 목록 항목에 대해 직원 이름과 부서를 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## 참고 항목  
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [방법: Windows Forms ListView 컨트롤의 아이콘 표시](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가\(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)