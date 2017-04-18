---
title: "방법: Windows Form에 Windows 탐색기 스타일 인터페이스 만들기 | Microsoft Docs"
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
  - "폼, Windows 탐색기 형식"
  - "SplitContainer 컨트롤[Windows Forms], Explorer-style 인터페이스"
  - "Windows 탐색기, Windows Forms을 사용하여 만들기"
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: Windows Form에 Windows 탐색기 스타일 인터페이스 만들기
Windows 탐색기는 사용자가 쉽게 사용할 수 있으므로 응용 프로그램에 많이 사용되는 사용자 인터페이스입니다.  
  
 Windows 탐색기는 본질적으로 별도의 패널에 있는 <xref:System.Windows.Forms.TreeView> 컨트롤과 <xref:System.Windows.Forms.ListView> 컨트롤입니다.  패널의 크기는 분할자를 사용하여 조정할 수 있습니다.  이러한 컨트롤 배열은 정보을 표시하고 찾아보는 데 매우 효율적입니다.  
  
 다음은 Windows 탐색기 형태의 폼에 컨트롤을 배열하는 방법을 보여 주는 단계입니다.  Windows 탐색기 응용 프로그램의 파일 검색 기능을 추가하는 방법은 소개하지 않습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### Windows 탐색기 스타일의 Windows Form을 만들려면  
  
1.  Windows 응용 프로그램 프로젝트를 새로 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  **도구 상자**에서 다음과 같이 하십시오.  
  
    1.  <xref:System.Windows.Forms.SplitContainer> 컨트롤을 폼으로 끌어 옵니다.  
  
    2.  <xref:System.Windows.Forms.TreeView> 컨트롤을 **SplitterPanel1**\(**Panel1**로 표시된 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 패널\)로 끌어 옵니다.  
  
    3.  <xref:System.Windows.Forms.ListView> 컨트롤을 **SplitterPanel2**\(**Panel2**로 표시된 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 패널\)로 끌어 옵니다.  
  
3.  Ctrl 키를 누른 채 세 컨트롤을 차례로 클릭하여 컨트롤을 모두 선택합니다.  <xref:System.Windows.Forms.SplitContainer> 컨트롤을 선택할 때는 패널이 아니라 분할 막대를 클릭합니다.  
  
    > [!NOTE]
    >  **편집** 메뉴의 **모두 선택** 명령은 사용하지 마십시오.  이 명령을 사용하면 다음 단계에 필요한 속성이 **속성** 창에 나타나지 않습니다.  
  
4.  **속성** 창에서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
5.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
     Windows 탐색기의 사용자 인터페이스와 비슷한, 두 부분으로 구성된 사용자 인터페이스가 폼에 표시됩니다.  
  
    > [!NOTE]
    >  분할자를 끌면 패널 크기가 조정됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.SplitContainer>   
 [방법: Windows Forms으로 다중 창 사용자 인터페이스 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)   
 [방법: 분할 창에서 크기 조정 및 위치 지정 동작 정의](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)   
 [방법: 가로로 창 분할](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)   
 [SplitContainer 컨트롤](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)