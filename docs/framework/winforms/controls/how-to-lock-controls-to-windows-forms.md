---
title: "방법: Windows Forms에 컨트롤 고정 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 잠금"
  - "Windows Forms 컨트롤, 잠금"
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms에 컨트롤 고정
Windows 응용 프로그램의 UI\(사용자 인터페이스\)를 디자인할 때 컨트롤의 위치를 올바르게 지정한 다음 컨트롤을 잠그면 다른 속성을 설정할 때 실수로 컨트롤이 이동되거나 크기가 변경되지 않도록 할 수 있습니다.  
  
 또한 폼에 있는 모든 컨트롤을 한 번에 잠그거나 잠금을 해제할 수도 있습니다. 이 기능은 폼에 많은 컨트롤이 있는 경우 유용하며 개별적으로 컨트롤의 잠금을 해제할 수도 있습니다.  폼에서 모든 컨트롤을 원하는 위치에 배치한 다음 모두 잠그면 실수로 이동하는 것을 방지할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤을 잠그려면  
  
1.  **속성** 창에서 **Locked** 속성을 클릭한 다음 `true`를 선택합니다.  이름을 두 번 클릭하면 true\/false를 전환합니다.  
  
     또는 컨트롤을 마우스 오른쪽 단추로 클릭하고 **컨트롤 잠그기**를 선택합니다.  
  
    > [!NOTE]
    >  컨트롤을 잠그면 디자인 화면에서 해당 컨트롤을 끌어 크기를 조정하거나 위치를 변경할 수 없습니다.  그러나 **속성** 창이나 코드를 통해서는 컨트롤의 크기나 위치를 변경할 수 있습니다.  
  
### 폼의 모든 컨트롤을 잠그려면  
  
1.  **서식** 메뉴에서 **컨트롤 잠그기**를 선택합니다.  
  
    > [!NOTE]
    >  폼도 컨트롤이기 때문에 이 명령은 폼의 크기까지 함께 잠급니다.  
  
### 폼에 있는 모든 컨트롤의 잠금을 해제하려면  
  
1.  **서식** 메뉴에서 **컨트롤 잠그기**를 선택합니다.  
  
     폼에서 이전에 잠근 컨트롤의 잠금이 모두 해제됩니다.  
  
### 개별적으로 컨트롤의 잠금을 해제하려면  
  
1.  **속성** 창에서 **Locked** 속성을 클릭한 다음 `false`를 선택합니다.  이름을 두 번 클릭하면 true\/false를 전환합니다.  
  
## 참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)   
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)