---
title: 사용자 지정 컨트롤의 종류
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], user controls
- controls [Windows Forms], types of
- composite controls [Windows Forms]
- extended controls [Windows Forms]
- controls [Windows Forms], extended
- user controls [Windows Forms]
- custom controls [Windows Forms]
- controls [Windows Forms], composite
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
ms.openlocfilehash: f35fdb0f82370ed3e40aeeda01b3c88f0a8c5ec0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541231"
---
# <a name="varieties-of-custom-controls"></a>사용자 지정 컨트롤의 종류
.NET Framework를 사용하여 새 컨트롤을 개발 및 구현할 수 있습니다. 상속을 통해서 기존 컨트롤 및 친숙한 사용자 정의 컨트롤의 기능을 확장할 수 있습니다. 또한 고유한 그리기를 수행하는 사용자 지정 컨트롤을 작성할 수도 있습니다.  
  
 만들 컨트롤 종류를 결정하기 어려울 수 있습니다. 이 항목에서는 상속할 수 있는 다양한 종류의 컨트롤 간의 차이점을 강조하고 프로젝트에 대한 특정 종류의 컨트롤을 선택하는 방법에 대한 정보를 제공합니다.  
  
> [!NOTE]
>  Web Forms에서 사용할 컨트롤 작성에 대한 자세한 내용은 [사용자 지정 ASP.NET 서버 컨트롤 개발](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef)을 참조하세요.  
  
## <a name="base-control-class"></a>기본 컨트롤 클래스  
 <xref:System.Windows.Forms.Control> Windows Forms 컨트롤에 대 한 기본 클래스입니다. Windows Forms 응용 프로그램에서 시각적 개체 표시에 필요한 인프라를 제공합니다.  
  
 <xref:System.Windows.Forms.Control> Windows Forms 응용 프로그램에서이 시각적 표시를 제공 하는 다음 작업을 수행 하는 클래스:  
  
-   창 핸들을 노출합니다.  
  
-   메시지 라우팅을 관리합니다.  
  
-   마우스 및 키보드 이벤트 및 다른 많은 사용자 인터페이스 이벤트를 제공합니다.  
  
-   고급 레이아웃 기능을 제공합니다.  
  
-   와 같은 시각적 표시는 관련 된 많은 속성을 포함 <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, 및 <xref:System.Windows.Forms.Control.Width%2A>합니다.  
  
-   Microsoft® ActiveX® 컨트롤 역할을 하는 Windows Forms 컨트롤에 필요한 보안 및 스레딩 지원을 제공합니다.  
  
 인프라의 상당 부분이 기본 클래스에서 제공되므로 비교적 쉽게 사용자 고유의 Windows Forms 컨트롤을 개발할 수 있습니다.  
  
## <a name="kinds-of-controls"></a>컨트롤의 종류  
 Windows Forms에서는 *복합*, *확장된* 및 *사용자 지정*으로 세 가지 종류의 사용자 정의 컨트롤을 지원합니다. 다음 섹션에서는 각 종류의 컨트롤을 설명하고 프로젝트에서 사용할 종류를 선택하기 위한 권장 사항을 제공합니다.  
  
### <a name="composite-controls"></a>복합 컨트롤  
 복합 컨트롤은 공용 컨테이너로 캡슐화된 Windows Forms 컨트롤의 컬렉션입니다. 이러한 종류의 컨트롤은 *사용자 정의 컨트롤*이라고도 합니다. 포함된 컨트롤은 *구성 요소 컨트롤*이라고 합니다.  
  
 복합 컨트롤은 포함된 각 Windows Forms 컨트롤과 연결된 고유 기능을 모두 포함하며 해당 속성을 선택적으로 노출하고 바인딩할 수 있게 해줍니다. 또한 복합 컨트롤은 사용자의 추가 개발 작업 없이 기능을 처리하는 다량의 기본 키보드를 제공합니다.  
  
 예를 들어 데이터베이스의 고객 주소 데이터를 표시하기 위해 복합 컨트롤을 빌드할 수 있습니다. 이 컨트롤에 포함 될 수는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터베이스 필드를 표시 한 <xref:System.Windows.Forms.BindingSource> 데이터 원본에 바인딩 처리 및 <xref:System.Windows.Forms.BindingNavigator> 레코드 간에 이동할 컨트롤입니다. 데이터 바인딩 속성을 선택적으로 노출할 수 있으며, 응용 프로그램 간에 전체 컨트롤을 패키징하고 다시 사용할 수 있습니다. 이러한 종류의 복합 컨트롤의 예는 [방법: Windows Forms 컨트롤에서 특성 적용](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)을 참조하세요.  
  
 파생 되는 복합 컨트롤을 작성 하는 <xref:System.Windows.Forms.UserControl> 클래스입니다. <xref:System.Windows.Forms.UserControl> 기본 클래스 키보드 라우팅을 자식 컨트롤과 자식 컨트롤을 그룹으로 작업할 수 있도록를 제공 합니다. 자세한 내용은 [Windows Forms 복합 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)을 참조하세요.  
  
 **권장 사항**  
  
 다음과 같은 경우 <xref:System.Windows.Forms.UserControl> 클래스에서 상속합니다.  
  
-   여러 Windows Forms 컨트롤의 기능을 다시 사용 가능한 단일 단위로 결합하려는 경우  
  
### <a name="extended-controls"></a>확장된 컨트롤  
 기존 Windows Forms 컨트롤에서 상속된 컨트롤을 파생시킬 수 있습니다. 이 접근 방식을 통해 Windows Forms 컨트롤의 고유 기능을 모두 유지한 다음 사용자 지정 속성, 메서드 또는 다른 기능을 추가하여 해당 기능을 확장할 수 있습니다. 이 옵션을 사용하여 기본 컨트롤의 그리기 논리를 재정의한 다음 모양을 변경하여 해당 사용자 인터페이스를 확장할 수 있습니다.  
  
 예를 들어에서 파생 된 컨트롤을 만들 수 있습니다는 <xref:System.Windows.Forms.Button> 사용자 횟수를 추적 하는 컨트롤에서 클릭 했습니다.  
  
 일부 컨트롤에서 있습니다 수 또한 사용자 지정에 모양을 추가할 컨트롤의 그래픽 사용자 인터페이스를 재정의 하 여는 <xref:System.Windows.Forms.Control.OnPaint%2A> 기본 클래스의 메서드. 번의 클릭을 추적 하는 확장된 단추에 대해 재정의할 수 있습니다는 <xref:System.Windows.Forms.Control.OnPaint%2A> 의 기본 구현을 호출 하는 메서드 <xref:System.Windows.Forms.Control.OnPaint%2A>를 선택한 다음 클릭 횟수의 한쪽에 그립니다는 <xref:System.Windows.Forms.Button> 컨트롤의 클라이언트 영역입니다.  
  
 **권장 사항**  
  
 다음과 같은 경우 Windows Forms 컨트롤에서 상속합니다.  
  
-   필요한 기능이 대부분 기존 Windows Forms 컨트롤에 이미 있는 것과 동일한 경우  
  
-   사용자 지정 그래픽 사용자 인터페이스가 필요하지 않거나 기존 컨트롤에 대한 새 그래픽 사용자 인터페이스를 디자인하려는 경우  
  
### <a name="custom-controls"></a>사용자 지정 컨트롤  
 다른 컨트롤을 만드는 방법은에서 상속 하 여 처음부터 새로 만드는 <xref:System.Windows.Forms.Control>합니다. <xref:System.Windows.Forms.Control> 클래스는 모든 마우스 및 키보드 이벤트, 처리 등의 컨트롤에 필요한 기본 기능 하지만 컨트롤별 기능이 나 그래픽 인터페이스를 제공 합니다.  
  
 상속 하 여 컨트롤을 만드는 <xref:System.Windows.Forms.Control> 훨씬 더 많은 노력과 보다에서 상속 하는 클래스에 필요한 <xref:System.Windows.Forms.UserControl> 또는 기존 Windows Forms 컨트롤입니다. 많은 구현이 남아 있으므로 사용자의 컨트롤은 복합 또는 확장된 컨트롤보다 더 큰 유연성을 가질 수 있으며 정확한 요구에 맞게 컨트롤을 만들 수 있습니다.  
  
 사용자 지정 컨트롤을 구현에 대 한 코드를 작성 해야는 <xref:System.Windows.Forms.Control.OnPaint%2A> 필요한 기능별 코드와 컨트롤의 이벤트입니다. 재정의할 수도 있습니다는 <xref:System.Windows.Forms.Control.WndProc%2A> 메서드 핸들 windows 메시지를 직접 합니다. 이는 컨트롤을 만드는 가장 강력한 방법이지만 이 기술을 효과적으로 사용하려면 Microsoft Win32® API에 대해 잘 알고 있어야 합니다.  
  
 사용자 지정 컨트롤의 예로 아날로그 시계의 모양과 동작을 복제하는 시계 컨트롤이 있습니다. 사용자 지정 그리기 호출에 대 한 응답에서 이동 하면 시계 바늘 <xref:System.Windows.Forms.Timer.Tick> 내부에서 발생 한 이벤트 <xref:System.Windows.Forms.Timer> 구성 요소입니다. 자세한 내용은 [방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)을 참조하세요.  
  
 **권장 사항**  
  
 다음과 같은 경우 <xref:System.Windows.Forms.Control> 클래스에서 상속합니다.  
  
-   컨트롤의 사용자 지정 그래픽 표현을 제공하려는 경우  
  
-   표준 컨트롤을 통해 사용할 수 없는 사용자 지정 기능을 구현해야 하는 경우  
  
### <a name="activex-controls"></a>ActiveX 컨트롤  
 Windows Forms 인프라는 Windows Forms 컨트롤을 호스팅하도록 최적화되어 있지만 ActiveX 컨트롤을 사용할 수도 있습니다. Visual Studio에서는 이 작업이 지원됩니다. 자세한 내용은 [방법: Windows Forms에 ActiveX 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)를 참조하세요.  
  
### <a name="windowless-controls"></a>창 없는 컨트롤  
 Microsoft Visual Basic® 6.0 및 ActiveX 기술은 *창 없는* 컨트롤을 지원합니다. 창 없는 컨트롤은 Windows Forms에서 지원되지 않습니다.  
  
## <a name="custom-design-experience"></a>사용자 지정 디자인 환경  
 사용자 지정 디자인 타임 환경을 구현해야 할 경우 디자이너를 직접 작성할 수 있습니다. 복합 컨트롤에 대 한 사용자 지정 디자이너에서 파생 된 <xref:System.Windows.Forms.Design.ParentControlDesigner> 또는 <xref:System.Windows.Forms.Design.DocumentDesigner> 클래스입니다. 확장 및 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너 클래스에서 파생 되는 <xref:System.Windows.Forms.Design.ControlDesigner> 클래스입니다.  
  
 사용 된 <xref:System.ComponentModel.DesignerAttribute> 컨트롤 디자이너와 연결할입니다. 자세한 내용은 [디자인 타임 지원 확장](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2) 및 [방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [합성 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [디자인 타임 지원 확장](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)
