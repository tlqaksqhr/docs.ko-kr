---
title: "방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 텍스트 설정 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 캡션 설정"
  - "Windows Forms, 표시되는 텍스트 설정"
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 텍스트 설정
Windows Forms 컨트롤은 일반적으로 컨트롤의 기본 기능과 관련된 텍스트를 표시합니다.  예를 들어, <xref:System.Windows.Forms.Button> 컨트롤은 보통 해당 단추가 클릭될 경우 수행할 작업을 나타내는 캡션을 표시합니다.  모든 컨트롤에 대해 <xref:System.Windows.Forms.Control.Text%2A> 속성을 사용하여 텍스트를 설정하거나 반환할 수 있습니다.  <xref:System.Windows.Forms.Control.Font%2A> 속성을 사용하여 글꼴을 변경할 수 있습니다.  
  
### 디자이너를 사용하여 텍스트와 글꼴을 설정하려면  
  
1.  속성 창에서 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 적합한 문자열로 설정합니다.  
  
     밑줄이 그어진 바로 가기 키를 만들려면 바로 가기 키로 사용할 문자 앞에 앰퍼샌드\(&\)를 포함합니다.  
  
2.  속성 창에서 <xref:System.Windows.Forms.Control.Font%2A> 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭합니다.  
  
     표준 글꼴 대화 상자에서 원하는 글꼴, 글꼴 스타일, 크기, 효과\(취소선 또는 밑줄\) 및 첨자를 선택합니다.  
  
## 참고 항목  
 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)