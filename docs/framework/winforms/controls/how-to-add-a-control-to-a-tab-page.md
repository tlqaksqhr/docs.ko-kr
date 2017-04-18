---
title: "방법: 탭 페이지에 컨트롤 추가 | Microsoft Docs"
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
  - "tab 컨트롤, 탭 순서"
  - "탭 페이지, 컨트롤 추가"
  - "TabPage 컨트롤"
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: 탭 페이지에 컨트롤 추가
Windows Forms <xref:System.Windows.Forms.TabControl>을 사용하면 체계적인 방식으로 다른 컨트롤을 표시할 수 있습니다.  다음 절차에서는 첫 번째 탭에 단추를 추가하는 방법을 보여 줍니다.  탭 페이지의 레이블 부분에 아이콘을 추가하는 방법에 대한 자세한 내용은 [방법: Windows Forms TabControl의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)을 참조하십시오.  
  
### 프로그래밍 방식으로 컨트롤을 추가하려면  
  
1.  <xref:System.Windows.Forms.TabPage>의 <xref:System.Windows.Forms.Control.Controls%2A> 속성에서 반환된 컬렉션의 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> 메서드를 사용합니다.  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## 참고 항목  
 [TabControl 컨트롤](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)   
 [TabControl 컨트롤 개요](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [방법: Windows Forms TabControl의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)   
 [방법: 탭 페이지 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)