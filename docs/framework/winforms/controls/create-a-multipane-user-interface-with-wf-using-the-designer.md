---
title: "방법: 디자이너를 사용하여 Windows Forms으로 다중 창 사용자 인터페이스 만들기 | Microsoft Docs"
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
  - "다중 창 사용자 인터페이스"
  - "SplitContainer 컨트롤[Windows Forms], 디자이너 사용"
  - "사용자 인터페이스, 다중 창"
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 디자이너를 사용하여 Windows Forms으로 다중 창 사용자 인터페이스 만들기
다음 프로시저에서는 Microsoft Outlook의 사용자 인터페이스와 비슷하게 **폴더** 목록, **메시지** 창 및 **미리 보기** 창이 있는 다중 창 사용자 인터페이스를 만듭니다.  이 배열은 주로 폼에 컨트롤을 도킹하여 만듭니다.  
  
 컨트롤을 도킹할 때는 컨트롤이 고정될 부모 컨테이너의 가장자리를 결정해야 합니다.  따라서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정하면 컨트롤의 오른쪽 가장자리가 부모 컨트롤의 오른쪽 가장자리에 도킹됩니다.  또한 컨트롤의 도킹된 가장자리는 컨테이너 컨트롤에 맞게 크기가 조정됩니다.  <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성의 작동 방식에 대한 자세한 내용은 [방법: Windows Forms에 컨트롤 도킹](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)을 참조하십시오.  
  
 이 절차에서는 응용 프로그램을 Microsoft Outlook과 유사하게 만들기 위해 기능을 추가하는 것이 아니라 <xref:System.Windows.Forms.SplitContainer> 및 다른 컨트롤을 폼에 배열하는 방법에 초점을 맞춥니다.  
  
 이 사용자 인터페이스를 만들려면 모든 컨트롤을 <xref:System.Windows.Forms.SplitContainer> 컨트롤에 배열합니다. 이 컨트롤의 왼쪽 패널에 <xref:System.Windows.Forms.TreeView> 컨트롤이 포함됩니다.  <xref:System.Windows.Forms.SplitContainer> 컨트롤의 오른쪽 패널에는 <xref:System.Windows.Forms.RichTextBox> 컨트롤 위에 <xref:System.Windows.Forms.ListView> 컨트롤이 있는 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤이 포함됩니다.  이 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 사용하여 폼에 있는 나머지 컨트롤의 크기를 독립적으로 조정할 수 있습니다.  여기서 고유의 사용자 인터페이스를 만드는 기술을 적용할 수도 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에 Outlook 스타일의 사용자 인터페이스를 만들려면  
  
1.  Windows 응용 프로그램 프로젝트를 새로 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  <xref:System.Windows.Forms.SplitContainer> 컨트롤을 **도구 상자**에서 폼으로 끌어 옵니다.  **속성** 창에서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
3.  <xref:System.Windows.Forms.TreeView> 컨트롤을 **도구 상자**에서 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 왼쪽 패널로 끌어 옵니다.  **속성** 창에서 아래쪽 화살표를 클릭하면 표시되는 값 편집기의 왼쪽 패널을 클릭하여 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
4.  **도구 상자**의 다른 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 끌어 옵니다. 이 컨트롤은 폼에 추가한 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 오른쪽 패널에 배치합니다.  **속성** 창에서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정하고 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성을 <xref:System.Windows.Forms.Orientation>로 설정합니다.  
  
5.  **도구 상자**의 <xref:System.Windows.Forms.ListView> 컨트롤을 폼에 추가된 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 위쪽 패널로 끌어 옵니다.  <xref:System.Windows.Forms.ListView> 컨트롤의 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
6.  **도구 상자**의 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 아래쪽 패널로 끌어 옵니다.  <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정합니다.  
  
     이 때 F5 키를 눌러 응용 프로그램을 실행하면 폼에 Microsoft Outlook와 비슷한 세 부분으로 구성된 사용자 인터페이스가 표시됩니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.SplitContainer> 컨트롤 내에 있는 두 분할자 중 하나에 마우스 포인터를 놓으면 내부 크기를 조정할 수 있습니다.  
  
     응용 프로그램 개발 중 이 단계에서 정교한 사용자 인터페이스가 만들어집니다.  다음 단계에서는 <xref:System.Windows.Forms.TreeView> 컨트롤과 <xref:System.Windows.Forms.ListView> 컨트롤을 특정 종류의 데이터 소스에 연결하는 등의 작업을 통해 응용 프로그램 자체의 프로그래밍을 수행합니다.  컨트롤을 데이터에 연결하는 방법에 대한 자세한 내용은 [데이터 바인딩 및 Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer 컨트롤](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)