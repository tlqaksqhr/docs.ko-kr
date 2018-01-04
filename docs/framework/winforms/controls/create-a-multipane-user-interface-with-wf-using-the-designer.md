---
title: "방법: 디자이너를 사용하여 Windows Forms으로 다중 창 사용자 인터페이스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6cfd9f258aa7c43f4c98e475c40af7fe7d9c286b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms으로 다중 창 사용자 인터페이스 만들기
다음 절차에서는 Microsoft Outlook으로 사용 되는 비슷한 다중 창 사용자 인터페이스 만들어집니다는 **폴더** 목록은 **메시지** 창 및 **미리보기** 창. 이 정렬은 주로 폼에 컨트롤을 도킹을 통해 얻습니다.  
  
 컨트롤을 고정 하면 부모 컨테이너의 가장자리 컨트롤을 고정은 확인할 수 있습니다. 따라서 설정 하는 경우는 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Right>, 컨트롤의 오른쪽 가장자리 부모 컨트롤의 오른쪽 가장자리에 도킹 됩니다. 또한 컨트롤의 도킹된 가장자리는 컨테이너 컨트롤에 맞게 크기가 조정 됩니다. 방식에 대 한 자세한 내용은 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성은 참조 [하는 방법: Windows Forms에 컨트롤 도킹](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)합니다.  
  
 정렬에 중점을 두고이 절차는 <xref:System.Windows.Forms.SplitContainer> 및 기타 컨트롤이 폼에서가 아니라를 모방 Microsoft Outlook 응용 프로그램으로 설정 하는 기능을 추가 합니다.  
  
 내에서 모든 컨트롤을 배치 하면이 사용자 인터페이스를 만들려면는 <xref:System.Windows.Forms.SplitContainer> 포함 되는 제어는 <xref:System.Windows.Forms.TreeView> 왼쪽 패널에서 제어 합니다. 오른쪽 패널은 <xref:System.Windows.Forms.SplitContainer> 두 번째 컨트롤에 포함 되어 <xref:System.Windows.Forms.SplitContainer> 보호로 <xref:System.Windows.Forms.ListView> 컨트롤 위의 <xref:System.Windows.Forms.RichTextBox> 제어 합니다. 이러한 <xref:System.Windows.Forms.SplitContainer> 독립 폼에서 다른 컨트롤의 크기를 조정 컨트롤을 사용 합니다. 자신만의 사용자 지정 사용자 인터페이스를 파악 하려면이 절차에 설명 된 기술을 적용할 수도 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>디자인 타임에 Outlook 스타일 사용자 인터페이스를 만들려면  
  
1.  새 Windows 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.  
  
2.  끌어서는 <xref:System.Windows.Forms.SplitContainer> 에서 제어는 **도구 상자** 양식입니다. 에 **속성** 창에서 설정 된 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>합니다.  
  
3.  끌어서는 <xref:System.Windows.Forms.TreeView> 에서 제어는 **도구 상자** 의 왼쪽 패널에는 <xref:System.Windows.Forms.SplitContainer> 제어 합니다. 에 **속성** 창에서 설정 된 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Left> 아래쪽 화살표를 클릭할 때 표시 되는 값 편집기의 왼쪽 패널을 클릭 하 여 합니다.  
  
4.  다른 <xref:System.Windows.Forms.SplitContainer> 에서 제어는 **도구 상자**;의 오른쪽 패널에는 <xref:System.Windows.Forms.SplitContainer> 컨트롤이 폼에 추가 합니다. 에 **속성** 창에서 설정 된 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill> 및 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성을 <xref:System.Windows.Forms.Orientation.Horizontal>합니다.  
  
5.  끌어서는 <xref:System.Windows.Forms.ListView> 에서 제어는 **도구 상자** 두 번째의 위쪽 패널에 <xref:System.Windows.Forms.SplitContainer> 컨트롤이 폼에 추가 합니다. <xref:System.Windows.Forms.ListView> 컨트롤의 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.  
  
6.  끌어서는 <xref:System.Windows.Forms.RichTextBox> 에서 제어는 **도구 상자** 두 번째의 아래쪽 패널에 <xref:System.Windows.Forms.SplitContainer> 제어 합니다. <xref:System.Windows.Forms.RichTextBox> 컨트롤의 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.  
  
     이 시점에서 f5 키를 눌러 응용 프로그램을 실행 하는 양식은 Microsoft Outlook의 것과 비슷한 세 부분으로 구성 사용자 인터페이스를 표시 합니다.  
  
    > [!NOTE]
    >  내에서 분할자 중 하나 위에 마우스 포인터를 만들었을 때의 <xref:System.Windows.Forms.SplitContainer> 컨트롤 내부 크기를 조정할 수 있습니다.  
  
     이 시점에서 응용 프로그램 개발 시 정교한 사용자 인터페이스를 트 했습니다. 다음 단계는 응용 프로그램 자체에서 프로그래밍 작업을 통해 계속 아마도 연결 하 여는 <xref:System.Windows.Forms.TreeView> 컨트롤 및 <xref:System.Windows.Forms.ListView> 컨트롤을 데이터 원본의 특정 종류입니다. 데이터에 컨트롤을 연결 하는 방법에 대 한 자세한 내용은 참조 [데이터 바인딩 및 Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer 컨트롤](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
