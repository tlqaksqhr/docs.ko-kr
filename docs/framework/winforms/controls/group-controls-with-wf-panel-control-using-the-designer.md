---
title: "방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1d4a49f36ac294199871075a04b7e682bd5613b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 다른 컨트롤을 그룹화 하는 데 사용 됩니다. 컨트롤을 그룹화 하는 방법은 세 가지가 있습니다. 하나는 시각적으로 관련 된 일반 사용자 인터페이스;에 대 한 폼 요소 그룹화 프로그래밍 방식으로 그룹화, 라디오 단추의 예를 들어 다른 스냅숏이 마지막은 디자인 타임에 컨트롤을 한 단위로 이동입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-create-a-group-of-controls"></a>컨트롤의 그룹을 만들려면  
  
1.  끌어서는 <xref:System.Windows.Forms.Panel> 에서 제어는 **Windows Forms** 폼으로 도구 상자 탭 합니다.  
  
2.  패널 내부 각 그리기 패널에 다른 컨트롤을 추가 합니다.  
  
     패널에 포함 하려는 기존 컨트롤을 사용 하는 경우에 모든 컨트롤에 선택 클립보드에 잘라낸 수 있습니다는 <xref:System.Windows.Forms.Panel> 컨트롤을 선택한 다음 패널에 붙여 넣습니다. 패널에 직접를 끌어 올 수도 있습니다.  
  
3.  (선택 사항) 패널에 테두리를 추가 하려면 설정 해당 <xref:System.Windows.Forms.BorderStyle> 속성입니다. 장소: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, 및 <xref:System.Windows.Forms.BorderStyle.None>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Panel 컨트롤](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [방법: 패널의 배경 설정](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
