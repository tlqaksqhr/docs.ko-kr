---
title: "방법: ToolStripMenuItems 이동 | Microsoft Docs"
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
  - "메뉴 항목, 잘라내기 및 붙여넣기"
  - "메뉴 항목, 끌어서 놓기"
  - "메뉴 항목, 이동"
  - "메뉴, 항목 정렬"
  - "MenuStrip 컨트롤[Windows Forms], 항목 정렬"
  - "ToolStripMenuItems, 잘라내기 및 붙여넣기"
  - "ToolStripMenuItems, 끌어서 놓기"
  - "ToolStripMenuItems, 이동"
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: ToolStripMenuItems 이동
디자인 타임에 최상위 메뉴 전체와 해당 메뉴 항목을 <xref:System.Windows.Forms.MenuStrip>의 다른 위치로 이동할 수 있습니다.  또한 최상위 메뉴 사이에 개별 메뉴 항목을 이동하거나 메뉴 내에서 메뉴 항목의 위치를 변경할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 최상위 메뉴 및 해당 메뉴 항목을 다른 최상위 위치로 이동하려면  
  
1.  이동하려는 메뉴를 마우스 왼쪽 단추로 클릭하고 누르고 있습니다.  
  
2.  삽입 지점을 원하는 새 위치의 앞에 있는 최상위 메뉴로 끌어 온 다음 마우스 왼쪽 단추를 놓습니다.  
  
     선택된 메뉴가 삽입 지점 오른쪽으로 이동합니다.  
  
### 최상위 메뉴 및 해당 메뉴 항목을 드롭다운 위치로 이동하려면  
  
1.  이동하려는 메뉴를 마우스 왼쪽 단추로 클릭하고 Ctrl\+X를 누르거나 메뉴를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **잘라내기**를 선택합니다.  
  
2.  대상 최상위 메뉴에서 원하는 새 위치 위에 있는 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 Ctrl\+V를 누르거나 원하는 새 위치 위에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **붙여넣기**를 선택합니다.  
  
     선택한 메뉴 항목 뒤에 잘라낸 메뉴가 삽입됩니다.  
  
### 항목 컬렉션 편집기를 사용하여 메뉴 내에서 메뉴 항목을 이동하려면  
  
1.  이동하려는 메뉴가 포함된 메뉴를 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **Edit DropDownItems**를 선택합니다.  
  
3.  **항목 컬렉션 편집기**에서 이동하려는 메뉴 항목을 마우스 왼쪽 단추로 클릭합니다.  
  
4.  위쪽 화살표와 아래쪽 화살표를 클릭하여 메뉴 내에서 메뉴 항목을 이동합니다.  
  
5.  **확인**을 클릭합니다.  
  
### 키보드를 사용하여 메뉴 내에서 메뉴 항목을 이동하려면  
  
1.  Alt 키를 누른 상태로 있습니다.  
  
2.  이동하려는 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 누르고 있습니다.  
  
3.  메뉴 항목을 새 위치로 끌어 온 다음 마우스 왼쪽 단추를 놓습니다.  
  
### 메뉴 항목을 다른 메뉴로 이동하려면  
  
1.  이동하려는 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 Ctrl\+X를 누르거나 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **잘라내기**를 선택합니다.  
  
2.  잘라낸 메뉴 항목이 포함될 메뉴를 마우스 왼쪽 단추로 클릭합니다.  
  
3.  원하는 새 위치 앞에 있는 메뉴 항목을 마우스 왼쪽 단추로 클릭하고 Ctrl\+V를 누르거나 원하는 새 위치 앞에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **붙여넣기**를 선택합니다.  
  
     선택한 메뉴 항목 뒤에 잘라낸 메뉴 항목이 삽입됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)