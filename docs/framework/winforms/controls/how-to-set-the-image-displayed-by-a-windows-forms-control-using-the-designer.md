---
title: "방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 이미지 설정 | Microsoft Docs"
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
  - "Button 컨트롤[Windows Forms], 이미지"
  - "컨트롤[Windows Forms], 이미지"
  - "예제[Windows Forms], 컨트롤"
  - "이미지[Windows Forms], Windows Forms 컨트롤"
  - "이미지 설정, Windows Forms 컨트롤"
  - "Windows Forms 컨트롤, 이미지"
ms.assetid: ae80d07a-e469-4251-90ca-df71f5852454
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 디자이너를 사용하여 Windows Forms 컨트롤에 표시되는 이미지 설정
몇몇 Windows Forms 컨트롤에서는 이미지를 표시할 수 있습니다.  단추에 있는 디스크 아이콘이 **저장** 명령을 나타내는 것처럼 이미지가 컨트롤의 목적을 명확하게 설명하는 아이콘이 될 수 있습니다.  또는 아이콘이 해당 컨트롤에 원하는 모양을 부여하는 배경 이미지가 될 수도 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤에 표시되는 이미지를 설정하려면  
  
1.  **속성** 창에서 컨트롤의 **Image** 또는 **BackgroundImage** 속성을 선택한 다음 줄임표 단추\(  
  
     ![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")  
  
     \)를 클릭하여 **리소스 선택** 대화 상자를 표시합니다.  
  
2.  표시할 이미지를 선택합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Image.FromFile%2A>   
 <xref:System.Drawing.Image>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>   
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)