---
title: "방법: ToolStripMenuItems 복사 | Microsoft Docs"
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
  - "메뉴 항목, 복사 및 붙여넣기"
  - "MenuStrip 컨트롤[Windows Forms], 항목 정렬"
  - "ToolStripMenuItems, 복사 및 붙여넣기"
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: ToolStripMenuItems 복사
디자인 타임에 최상위 메뉴 전체와 해당 하위 메뉴 항목을 <xref:System.Windows.Forms.MenuStrip>의 다른 위치로 복사할 수 있습니다. 최상위 메뉴 간에 개별 메뉴 항목을 복사하거나 메뉴 내에서 메뉴 항목의 위치를 변경할 수도 있습니다.  
  
### 최상위 메뉴와 해당 하위 메뉴 항목을 다른 최상위 위치로 복사하려면  
  
1.  복사하려는 메뉴를 마우스 왼쪽 단추로 클릭하고 Ctrl\+C를 누르거나, 메뉴를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **복사**를 선택합니다.  
  
2.  원하는 새 위치 뒤에 있는 최상위 메뉴를 마우스 왼쪽 단추로 클릭하고 Ctrl\+V를 누르거나, 원하는 새 위치 앞에 있는 최상위 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **붙여넣기**를 선택합니다.  
  
     복사한 메뉴가 선택한 최상위 메뉴 앞에 삽입됩니다.  
  
### 최상위 메뉴와 해당 하위 메뉴 항목을 드롭다운 위치에 복사하려면  
  
1.  이동하려는 메뉴를 마우스 왼쪽 단추로 클릭하고 Ctrl\+C를 누르거나, 메뉴를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **복사**를 선택합니다.  
  
2.  대상 최상위 메뉴에서 원하는 새 위치 위에 있는 하위 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 Ctrl\+V를 누르거나, 원하는 새 위치 위에 있는 하위 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **붙여넣기**를 선택합니다.  
  
     복사한 메뉴가 선택한 하위 메뉴 항목 앞에 삽입됩니다.  
  
### 다른 메뉴에 하위 메뉴 항목을 복사하려면  
  
1.  복사하려는 하위 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 Ctrl\+C를 누르거나, 하위 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **복사**를 선택합니다.  
  
2.  잘라낸 하위 메뉴 항목이 포함될 메뉴를 마우스 왼쪽 단추로 클릭합니다.  
  
3.  원하는 새 위치 앞에 있는 하위 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 Ctrl\+V를 누르거나, 원하는 새 위치 앞에 있는 하위 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **붙여넣기**를 선택합니다.  
  
     복사한 하위 메뉴 항목이 선택한 하위 메뉴 항목 앞에 삽입됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)