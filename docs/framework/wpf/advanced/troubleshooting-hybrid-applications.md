---
title: "혼합 응용 프로그램 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "혼합 응용 프로그램[WPF 상호 운용성]"
  - "상호 운용성[WPF], Windows Forms"
  - "메시지 루프[WPF]"
  - "컨트롤 겹침"
  - "Windows Forms[WPF], 상호 운용성"
  - "Windows Forms, WPF 상호 운용"
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# 혼합 응용 프로그램 문제 해결
<a name="introduction"></a> 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 기술을 모두 사용하는 혼합 응용 프로그램을 작성할 때 발생할 수 있는 몇 가지 일반적인 문제를 설명합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="overlapping_controls"></a>   
## 컨트롤 겹침  
 컨트롤이 예상대로 겹치지 않을 수 있습니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]는 각 컨트롤에 별개의 HWND를 사용하고  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 페이지의 모든 콘텐츠에 하나의 HWND를 사용합니다.  이 구현 차이로 인해 예기치 않은 겹침 동작이 발생합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 호스팅되는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 위에 표시됩니다.  
  
 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스팅되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 Z 순서로 표시됩니다.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 겹칠 수 있지만 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠는 결합되거나 상호 작용하지 않습니다.  
  
<a name="child_property"></a>   
## 자식 속성  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 및 <xref:System.Windows.Forms.Integration.ElementHost> 클래스는 하나의 자식 컨트롤 또는 요소만 호스팅할 수 있습니다.  둘 이상의 컨트롤이나 요소를 호스팅하려면 컨테이너를 자식 콘텐츠로 사용해야 합니다.  예를 들어 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 단추 및 확인란 컨트롤을 <xref:System.Windows.Forms.Panel?displayProperty=fullName> 컨트롤에 추가한 다음 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 속성에 패널을 할당할 수 있습니다.  그러나 단추 및 확인란 컨트롤을 별개로 동일한 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 추가할 수 없습니다.  
  
<a name="scaling"></a>   
## 배율 조정  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에는 서로 다른 배율 조정 모델이 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 배율 조정 변환 중 일부는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 의미가 있지만 일부는 의미가 없습니다.  예를 들어 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 배율을 0으로 조정하는 것은 작동하지만 동일한 컨트롤의 배율을 다시 0이 아닌 값으로 조정하면 컨트롤의 크기가 0으로 남아 있습니다.  자세한 내용은 [WindowsFormsHost 요소에 대한 레이아웃 고려 사항](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)을 참조하십시오.  
  
<a name="adapter"></a>   
## 어댑터  
 숨겨진 컨테이너가 포함되어 있기 때문에  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 및 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용할 때 혼동이 생길 수 있습니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 및 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 둘 다 *어댑터*라는 숨겨진 컨테이너가 있으며 이 어댑터는 콘텐츠를 호스팅하는 데 사용됩니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 경우 어댑터는 <xref:System.Windows.Forms.ContainerControl?displayProperty=fullName> 클래스에서 파생됩니다.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 경우 어댑터는 <xref:System.Windows.Controls.DockPanel> 요소에서 파생됩니다.  다른 상호 운용성 항목의 어댑터에 대한 참조에서 이 컨테이너가 설명됩니다.  
  
<a name="nesting"></a>   
## 중첩  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 안에 중첩하는 것은 지원되지 않습니다.  <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 안에 중첩하는 것도 지원되지 않습니다.  
  
<a name="focus"></a>   
## 포커스  
 포커스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]에서 다르게 작동하는데 이는 혼합 응용 프로그램에서 포커스 문제가 발생할 수 있다는 것을 의미합니다.  예를 들어 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 안에 포커스가 있는 상태에서 페이지를 최소화했다가 복원하거나 모달 대화 상자를 표시할 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 안의 포커스가 손실될 수 있습니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에 계속해서 포커스가 있지만 그 안의 컨트롤이 손실될 수 있습니다.  
  
 데이터 유효성 검사도 포커스의 영향을 받습니다.  유효성 검사는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서 작동하지만 Tab 키를 눌러 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 밖으로 이동하거나 두 개의 다른 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 사이에 이동할 경우에는 작동하지 않습니다.  
  
<a name="property_mapping"></a>   
## 속성 매핑  
 일부 속성 매핑에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 기술 간의 상이한 구현을 연결하기 위해 광범위한 해석이 필요합니다.  속성 매핑을 사용하면 글꼴, 색 및 기타 속성의 변경 내용에 대해 코드에서 대응할 수 있습니다.  일반적으로 속성 매핑은 *Property*Changed 이벤트 또는 On*Property*Changed 호출을 수신 대기하고 자식 컨트롤 또는 해당 어댑터에서 적절한 속성을 설정하여 작동합니다.  자세한 내용은 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)을 참조하십시오.  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## 호스팅된 콘텐츠의 레이아웃 관련 속성  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=fullName> 또는 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=fullName> 속성이 할당된 경우 호스팅된 콘텐츠의 여러 레이아웃 관련 속성이 자동으로 설정됩니다.  이러한 콘텐츠 속성을 변경하면 예기치 않은 레이아웃 동작이 발생할 수 있습니다.  
  
 호스팅된 콘텐츠는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 및 <xref:System.Windows.Forms.Integration.ElementHost> 부모를 채우기 위해 도킹됩니다.  이 채우기 동작을 사용하도록 설정하기 위해 자식 속성을 설정할 때 여러 속성이 설정됩니다.  다음 표에서는 <xref:System.Windows.Forms.Integration.ElementHost> 및 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스에 의해 설정되는 콘텐츠 속성을 보여 줍니다.  
  
|호스트 클래스|콘텐츠 속성|  
|-------------|------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 호스팅된 콘텐츠에서 이러한 속성을 직접 설정하지 마십시오.  자세한 내용은 [WindowsFormsHost 요소에 대한 레이아웃 고려 사항](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)을 참조하십시오.  
  
<a name="navigation_applications"></a>   
## 탐색 응용 프로그램  
 탐색 응용 프로그램은 사용자 상태를 유지 관리하지 못할 수 있습니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 탐색 응용 프로그램에서 사용될 경우 해당 컨트롤을 다시 만듭니다.  사용자가 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 호스팅하는 페이지 밖으로 이동했다가 돌아올 경우 자식 컨트롤을 다시 만드는 작업이 발생합니다.  사용자가 입력한 모든 콘텐츠는 손실됩니다.  
  
<a name="message_loop_interoperation"></a>   
## 메시지 루프 상호 운용성  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 메시지 루프를 사용할 경우 메시지가 예상대로 처리되지 않을 수 있습니다.  <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 생성자에 의해 호출됩니다.  이 메서드는 메시지 필터를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 루프에 추가합니다.  <xref:System.Windows.Forms.Control?displayProperty=fullName>이 메시지의 대상이었고 메시지를 변환\/디스패치할 경우 이 필터는 <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=fullName> 메서드를 호출합니다.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>을 사용하여 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 메시지 루프에 <xref:System.Windows.Window>를 표시할 경우 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 메서드를 호출하지 않으면 아무 것도 입력할 수 없습니다.  <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 메서드는 <xref:System.Windows.Window>를 사용하며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 루프에 키 관련 메시지를 다시 라우팅하는 <xref:System.Windows.Forms.IMessageFilter?displayProperty=fullName>를 추가합니다.  자세한 내용은 [Windows Forms 및 WPF 상호 운용성 입력 아키텍처](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md)를 참조하십시오.  
  
<a name="opacity_and_layering"></a>   
## 불투명도 및 계층화  
 <xref:System.Windows.Interop.HwndHost> 클래스는 계층화를 지원하지 않습니다.  이는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서 <xref:System.Windows.UIElement.Opacity%2A> 속성을 설정할 경우 효과가 없으며 `true`로 설정된 <xref:System.Windows.Window.AllowsTransparency%2A>가 있는 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창과의 혼합이 발생하지 않는다는 것을 의미합니다.  
  
<a name="dispose"></a>   
## 삭제  
 클래스를 올바르게 삭제하지 않을 경우 리소스가 누수될 수 있습니다.  혼합 응용 프로그램에서 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 및 <xref:System.Windows.Forms.Integration.ElementHost> 클래스가 삭제되었는지 확인합니다. 이러한 클래스가 삭제되지 않은 경우 리소스가 누수될 수 있습니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]는 모달이 아닌 해당 <xref:System.Windows.Forms.Form> 부모가 닫힐 때 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 삭제합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 응용 프로그램이 종료할 때 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 삭제합니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 메시지 루프의 <xref:System.Windows.Window>에서 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 표시할 수 있습니다.  이 경우 응용 프로그램이 종료 중이라는 알림을 코드에서 받지 못할 수도 있습니다.  
  
<a name="enabling_visual_styles"></a>   
## 비주얼 스타일 사용  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에서 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 비주얼 스타일을 사용하도록 설정할 수 없습니다.  <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> 메서드는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램에 대한 템플릿에서 호출됩니다.  이 메서드를 사용 하는 경우 기본적으로 호출 되지 않습니다 있지만 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 프로젝트를 만들려면 드리겠습니다 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visual 6.0 comctl32.dll 버전을 사용할 수 있는 경우 컨트롤에 대 한 스타일. 호출 해야는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 메서드 핸들 스레드를 만들기 전에.  자세한 내용은 [방법: 혼합 응용 프로그램에서 비주얼 스타일 사용](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)을 참조하십시오.  
  
<a name="licensed_controls"></a>   
## 라이선스가 있는 컨트롤  
 메시지 상자에서 라이선스 정보를 사용자에게 표시하는 라이선스가 있는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 혼합 응용 프로그램에서 예기치 않은 동작을 가져올 수 있습니다.  라이선스가 있는 일부 컨트롤은 핸들 만들기에 응답하여 대화 상자를 표시합니다.  예를 들어 라이선스가 있는 컨트롤은 라이선스가 필요하다거나 컨트롤의 무료 사용 횟수가 세 번 남았다는 것을 사용자에게 알릴 수 있습니다.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 <xref:System.Windows.Interop.HwndHost> 클래스에서 파생되고 자식 컨트롤의 핸들은 <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> 메서드 안에서 만들어집니다.  <xref:System.Windows.Interop.HwndHost> 클래스는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> 메서드에서 메시지가 처리되도록 허용하지 않지만 대화 상자를 표시하면 메시지가 보내집니다.  이 라이선스 시나리오를 가능하게 하려면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 자식으로 할당하기 전에 컨트롤에서 <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=fullName> 메서드를 호출합니다.  
  
<a name="wpf_designer"></a>   
## WPF Designer  
 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]를 사용하여 WPF 콘텐츠를 디자인할 수 있습니다.  다음 단원에서는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]를 사용하여 혼합 응용 프로그램을 만들 때 발생할 수 있는 몇 가지 일반적인 문제를 보여 줍니다.  
  
### BackColorTransparent가 디자인 타임에 무시됩니다.  
 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 속성이 디자인 타임에 예상대로 작동하지 않을 수 있습니다.  
  
 WPF 컨트롤이 표시되는 부모에 있지 않으면 WPF 런타임에 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 값이 무시됩니다.  <xref:System.Windows.Forms.Integration.ElementHost> 개체가 별도의 <xref:System.AppDomain>에 만들어지므로 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>가 무시될 수 있습니다.  그러나 응용 프로그램을 실행하면 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>가 올바르게 작동합니다.  
  
### obj 폴더를 삭제하면 디자인 타임 오류 목록이 나타납니다.  
 obj 폴더를 삭제하면 디자인 타임 오류 목록이 나타납니다.  
  
 <xref:System.Windows.Forms.Integration.ElementHost>를 사용하여 디자인하는 경우 프로젝트의 obj 폴더 아래 있는 Debug 또는 Release 폴더에 생성된 파일이 Windows Forms 디자이너에 사용됩니다.  이러한 파일을 삭제하면 디자인 타임 오류 목록이 나타납니다.  이 문제를 해결하려면 프로젝트를 다시 빌드해야 합니다.  자세한 내용은 [Windows Forms 디자이너의 디자인 타임 오류](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)를 참조하십시오.  
  
<a name="elementhost_and_ime"></a>   
## ElementHost 및 IME  
 <xref:System.Windows.Forms.Integration.ElementHost>에 호스팅된 WPF 컨트롤은 현재 <xref:System.Windows.Forms.Control.ImeMode%2A> 속성을 지원하지 않습니다.  <xref:System.Windows.Forms.Control.ImeMode%2A>에 대한 변경 사항은 호스팅된 컨트롤에서 무시됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer의 상호 운용성](http://msdn.microsoft.com/ko-kr/2cb7c1ca-2a75-463b-8801-fba81e2b7042)   
 [Windows Forms 및 WPF 상호 운용성 입력 아키텍처](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md)   
 [방법: 혼합 응용 프로그램에서 비주얼 스타일 사용](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)   
 [WindowsFormsHost 요소에 대한 레이아웃 고려 사항](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)   
 [Windows Forms 및 WPF 속성 매핑](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [Windows Forms 디자이너의 디자인 타임 오류](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)   
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)