---
title: "사용자 지정 컨트롤의 종류 | Microsoft Docs"
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
  - "복합 컨트롤"
  - "컨트롤[Windows Forms], 복합"
  - "컨트롤[Windows Forms], 확장"
  - "컨트롤[Windows Forms], 형식"
  - "컨트롤[Windows Forms], 사용자 정의 컨트롤"
  - "사용자 지정 컨트롤[Windows Forms]"
  - "확장된 컨트롤"
  - "사용자 정의 컨트롤[Windows Forms]"
ms.assetid: 3cea09e5-4344-4ccb-9858-b66ccac210ff
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 사용자 지정 컨트롤의 종류
.NET Framework를 사용하여 새 컨트롤을 개발하고 구현할 수 있습니다.  상속을 통해 기존 컨트롤뿐만 아니라 친숙한 사용자 정의 컨트롤의 기능도 확장할 수 있습니다.  자체적으로 그리기를 수행하는 사용자 지정 컨트롤을 작성할 수도 있습니다.  
  
 경우에 따라 어떤 종류의 컨트롤을 작성할지 혼동될 수 있습니다.  이 항목에서는 상속할 수 있는 다양한 종류의 컨트롤 간의 중요한 차이점을 보여 주고 프로젝트에 사용할 특정 종류의 컨트롤을 선택하는 방법에 대한 정보를 제공합니다.  
  
> [!NOTE]
>  Web Forms에서 사용할 컨트롤을 작성하는 방법에 대한 자세한 내용은 [Developing Custom ASP.NET Server Controls](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md)을 참조하십시오.  
  
## 기본 컨트롤 클래스  
 <xref:System.Windows.Forms.Control> 클래스는 Windows Forms 컨트롤의 기본 클래스이며  Windows Forms 응용 프로그램의 시각적 표시에 필요한 인프라를 제공합니다.  
  
 <xref:System.Windows.Forms.Control> 클래스는 다음 작업을 수행하여 Windows Forms 응용 프로그램에 시각적 표시를 제공합니다.  
  
-   창 핸들 노출  
  
-   메시지 라우팅 관리  
  
-   마우스 및 키보드 이벤트를 비롯한 다른 많은 사용자 인터페이스 이벤트 제공  
  
-   고급 레이아웃 기능 제공  
  
-   <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A> 및 <xref:System.Windows.Forms.Control.Width%2A>와 같은 많은 시각적 표시 관련 속성 포함  
  
-   Windows Forms 컨트롤이 Microsoft® ActiveX® 컨트롤의 역할을 하는 데 필요한 보안 및 스레딩 지원 제공  
  
 인프라 대부분을 기본 클래스에서 제공하기 때문에 사용자 자신의 Windows Forms 컨트롤을 상대적으로 쉽게 개발할 수 있습니다.  
  
## 컨트롤 종류  
 Windows Forms에서는 사용자 정의 *합성*, *확장* 및 *사용자 지정* 컨트롤을 사용할 수 있습니다.  다음 단원에서는 각 종류의 컨트롤에 대해 설명하고 프로젝트에 사용할 컨트롤 선택을 위한 권장 사항을 제공합니다.  
  
### 복합 컨트롤  
 복합 컨트롤은 공용 컨테이너에 캡슐화된 Windows Forms 컨트롤의 컬렉션입니다.  이 컨트롤을 *사용자 정의 컨트롤*이라고도 합니다.  포함된 컨트롤은 *구성 요소 컨트롤*이라고 합니다.  
  
 복합 컨트롤은 포함된 각 Windows Forms 컨트롤과 연결된 모든 고유 기능을 보유하므로 컨트롤의 속성을 선택적으로 노출하고 바인딩할 수 있습니다.  복합 컨트롤은 별도의 개발 과정이 필요 없는 다양한 기본 키보드 처리 기능도 제공합니다.  
  
 예를 들어, 복합 컨트롤을 작성하여 데이터베이스의 고객 주소 데이터를 표시할 수 있습니다.  이 컨트롤은 <xref:System.Windows.Forms.DataGridView> 컨트롤\(데이터베이스 필드 표시\), <xref:System.Windows.Forms.BindingSource> 컨트롤\(데이터 소스에 대한 바인딩 처리\) 및 <xref:System.Windows.Forms.BindingNavigator> 컨트롤\(레코드 내 이동\)을 포함할 수 있습니다.  데이터 바인딩 속성을 선택적으로 노출할 수 있으며 전체 컨트롤을 패키지하여 여러 응용 프로그램에서 다시 사용할 수 있습니다.  이러한 종류의 복합 컨트롤의 예는 [방법: Windows Forms 컨트롤에서 특성 적용](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)을 참조하십시오.  
  
 복합 컨트롤을 작성하려면 <xref:System.Windows.Forms.UserControl> 클래스에서 파생합니다.  기본 클래스 <xref:System.Windows.Forms.UserControl>에서는 자식 컨트롤에 대한 키보드 라우팅을 제공하고 자식 컨트롤이 그룹으로 동작할 수 있도록 합니다.  자세한 내용은 [합성 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)을 참조하십시오.  
  
 **권장 사항**  
  
 다음과 같은 경우에는 <xref:System.Windows.Forms.UserControl> 클래스에서 상속됩니다.  
  
-   여러 Windows Forms 컨트롤의 기능을 다시 사용할 수 있는 하나의 단위로 결합하려는 경우  
  
### 확장 컨트롤  
 기존의 모든 Windows Forms 컨트롤에서 상속된 컨트롤을 만들 수 있습니다.  이렇게 하면 Windows Forms 컨트롤의 모든 고유 기능을 유지하면서 사용자 지정 속성, 메서드 또는 기타 기능을 추가하여 해당 기능을 확장할 수 있습니다.  이 옵션을 사용하면 기본 컨트롤의 그리기 논리를 재정의한 다음 모양을 변경하여 해당 사용자 인터페이스를 확장할 수 있습니다.  
  
 예를 들어, 사용자가 클릭한 횟수를 추적하고 <xref:System.Windows.Forms.Button> 컨트롤에서 파생된 컨트롤을 만들 수 있습니다.  
  
 일부 컨트롤의 경우 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하여 컨트롤의 그래픽 사용자 인터페이스에 사용자 지정 모양을 추가할 수도 있습니다.  클릭 횟수를 추적하는 확장 단추의 경우 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하여 <xref:System.Windows.Forms.Control.OnPaint%2A>의 기본 구현을 호출한 다음 <xref:System.Windows.Forms.Button> 컨트롤 클라이언트 영역의 한쪽 모퉁이에 클릭 횟수를 그릴 수 있습니다.  
  
 **권장 사항**  
  
 다음과 같은 경우에는 Windows Forms 컨트롤에서 상속합니다.  
  
-   대부분의 필요한 기능이 기존 Windows Forms 컨트롤에 있는 경우  
  
-   사용자 지정 그래픽 사용자 인터페이스가 필요하지 않거나 기존 컨트롤에 대한 새 그래픽 사용자 인터페이스를 디자인하려는 경우  
  
### 사용자 지정 컨트롤  
 컨트롤을 만드는 또 다른 방법은 <xref:System.Windows.Forms.Control>에서 상속하여 처음부터 컨트롤을 만드는 것입니다.  <xref:System.Windows.Forms.Control> 클래스는 마우스 및 키보드 처리 이벤트를 포함하여 컨트롤에 필요한 모든 기본 기능을 제공하지만 컨트롤별 기능이나 그래픽 인터페이스는 제공하지 않습니다.  
  
 <xref:System.Windows.Forms.Control> 클래스에서 상속하여 컨트롤을 만드는 작업은 <xref:System.Windows.Forms.UserControl>이나 기존 Windows Forms 컨트롤에서 상속하는 것보다 어렵습니다.  많은 구현을 사용자가 수행해야 하므로 사용자 지정 컨트롤은 복합 컨트롤이나 확장 컨트롤보다 융통성이 보다 높으며 사용자가 필요에 맞게 컨트롤을 설정할 수 있습니다.  
  
 사용자 지정 컨트롤을 구현하려면 필요한 모든 기능별 코드뿐만 아니라 컨트롤의 <xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트에 대한 코드도 작성해야 합니다.  <xref:System.Windows.Forms.Control.WndProc%2A> 메서드를 재정의하고 Windows 메시지를 직접 처리할 수도 있습니다.  이는 컨트롤을 만드는 가장 강력한 방법이지만 이 기술을 효과적으로 사용하려면 Microsoft Win32® API를 잘 알고 있어야 합니다.  
  
 사용자 지정 컨트롤의 예로 아날로그 시계의 모양과 동작을 복제하는 시계 컨트롤을 들 수 있습니다.  내부 <xref:System.Windows.Forms.Timer> 구성 요소의 <xref:System.Windows.Forms.Timer.Tick> 이벤트에 대한 응답으로 시계 바늘을 이동시키기 위해 사용자 지정 그리기가 호출됩니다.  자세한 내용은 [방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)을 참조하십시오.  
  
 **권장 사항**  
  
 다음과 같은 경우에는 <xref:System.Windows.Forms.Control> 클래스에서 상속됩니다.  
  
-   컨트롤의 사용자 지정 그래픽 표현을 제공하려는 경우  
  
-   표준 컨트롤을 통해 구현할 수 없는 사용자 지정 기능을 구현할 필요가 있는 경우  
  
### ActiveX 컨트롤  
 Windows Forms 인프라는 Windows Forms 컨트롤을 호스팅하기에 최적화되어 있지만 ActiveX 컨트롤을 사용할 수도 있습니다.  Visual Studio에서는 이 작업을 지원합니다.  자세한 내용은 [방법: Windows Forms에 ActiveX 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)를 참조하십시오.  
  
### 창 없는 컨트롤  
 Microsoft Visual Basic® 6.0 및 ActiveX 기술을 통해 *창 없는* 컨트롤을 사용할 수 있습니다.  Windows Forms에서는 창 없는 컨트롤을 사용할 수 없습니다.  
  
## 사용자 지정 디자인 환경  
 사용자 지정 디자인 타임 환경을 구현해야 하는 경우 사용자 디자이너를 작성할 수 있습니다.  복합 컨트롤의 경우 <xref:System.Windows.Forms.Design.ParentControlDesigner> 또는 <xref:System.Windows.Forms.Design.DocumentDesigner> 클래스에서 사용자 지정 디자이너 클래스를 파생합니다.  확장 컨트롤과 사용자 지정 컨트롤의 경우 <xref:System.Windows.Forms.Design.ControlDesigner> 클래스에서 사용자 지정 디자이너 클래스를 파생합니다.  
  
 <xref:System.ComponentModel.DesignerAttribute>를 사용하여 사용자 정의 컨트롤을 디자이너에 연결합니다.  자세한 내용은 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md) 및 [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md)를 참조하십시오.  
  
## 참고 항목  
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)   
 [합성 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [How to: Create a Windows Forms Control That Takes Advantage of Design\-Time Features](../Topic/How%20to:%20Create%20a%20Windows%20Forms%20Control%20That%20Takes%20Advantage%20of%20Design-Time%20Features.md)