---
title: Windows Forms 컨트롤 개발 기본 사항
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: b455912468376d2f5de0ac1f30b4fcab5bb93309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-control-development-basics"></a>Windows Forms 컨트롤 개발 기본 사항
Windows Forms 컨트롤에서 직접 또는 간접적으로 파생 되는 클래스는 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다. 다음 목록에서는 Windows Forms 컨트롤 개발 하기 위한 일반적인 시나리오를 설명 합니다.  
  
-   결합 기존 복합 컨트롤을 만드는 제어 합니다.  
  
     복합 컨트롤 컨트롤로 다시 사용할 수 있는 사용자 인터페이스를 캡슐화 합니다. 합성 컨트롤의 예로 텍스트 상자 및 다시 설정으로 구성 된 컨트롤입니다. 비주얼 디자이너에는 복합 컨트롤을 만들기 위한 풍부한 지원을 제공 합니다. 파생 되는 복합 컨트롤을 작성 하려면 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>합니다. 기본 클래스 <xref:System.Windows.Forms.UserControl> 자식 컨트롤과 자식 컨트롤을 그룹으로 작업할 수 있도록에 대 한 키보드 라우팅을 제공 합니다. 자세한 내용은 [Windows Forms 복합 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)을 참조하세요.  
  
-   사용자 지정 하거나 해당 기능을 추가 하는 기존 컨트롤을 확장 합니다.  
  
     색을 변경할 수 없습니다 단추 및가 클릭 횟수를 추적 하는 추가 속성이 있는 확장 된 컨트롤의 예입니다. 파생 하 고 재정의 하거나 속성, 메서드 및 이벤트를 추가 하 여 Windows Forms 컨트롤을 사용자 지정할 수 있습니다.  
  
-   결합 되지 않거나 기존 컨트롤을 확장 하는 컨트롤을 제작 합니다.  
  
     이 시나리오에서는 기본 클래스에서 컨트롤을 파생 <xref:System.Windows.Forms.Control>합니다. 재정의 속성, 메서드 및 기본 클래스의 이벤트 수 있을 뿐만 아니라 추가할 수 있습니다. 시작 하려면 참조 [하는 방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)합니다.  
  
 Windows Forms 컨트롤에 대 한 기본 클래스 <xref:System.Windows.Forms.Control>, 클라이언트 측 Windows 기반 응용 프로그램의 시각적 표시에 필요한 연결이 제공 합니다. <xref:System.Windows.Forms.Control> 창 핸들, 메시지 라우팅을 처리와 마우스 및 키보드 이벤트 뿐만 아니라 여러 가지 사용자 인터페이스 이벤트를 제공 합니다. 고급 레이아웃을 제공 하 고 같은 시각적 표시는 관련 된 속성을 주지 <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, 및 다른 많은 요인을 합니다. 또한 보안을 스레딩 지원 및 ActiveX 컨트롤의 상호 운용성을 제공 합니다. 인프라의 상당 부분이 기본 클래스에서 제공되므로 비교적 쉽게 사용자 고유의 Windows Forms 컨트롤을 개발할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [합성 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
