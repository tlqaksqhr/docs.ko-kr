---
title: "방법: ToolStrip 컨트롤에 설정/해제 단추 만들기 | Microsoft Docs"
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
  - "예제[Windows Forms], 도구 모음"
  - "설정/해제 단추, 만들기"
  - "ToolStrip 컨트롤[Windows Forms], 설정/해제 단추 만들기"
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: ToolStrip 컨트롤에 설정/해제 단추 만들기
설정\/해제 단추를 클릭하면 오목하게 표시되고 이 단추를 다시 클릭할 때까지 그 모양이 유지됩니다.  
  
### 설정\/해제되는 ToolStripButton을 만들려면  
  
-   다음 코드 예제와 같은 코드를 사용합니다.  이 코드에서는 폼에 <xref:System.Windows.Forms.ToolStrip> 컨트롤이 포함되어 있고, <xref:System.Windows.Forms.ToolStrip.Items%2A> 컬렉션에 `toolStripButton1`이라는 <xref:System.Windows.Forms.ToolStripButton>이 포함되어 있다고 가정합니다.  또한 `toolStripButton1_CheckedChanged`라는 이벤트 처리기가 있다고 가정합니다.  
  
     \[Visual Basic\]  
  
    ```  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
  
    ```  
  
     \[C\#\]  
  
    ```  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStripButton>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)