---
title: "Windows Forms의 추가 보안 고려 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "API 호출, Windows Forms 보안 설정"
  - "API, 호출"
  - "클립보드, 액세스 보안"
  - "보안[Windows Forms]"
  - "보안[Windows Forms], API 호출"
  - "Windows API, 호출"
  - "Windows API, 호출 보안"
  - "Windows API, Windows Forms 보안 설정"
  - "Windows Forms, Windows API에 대한 호출 보안"
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Windows Forms의 추가 보안 고려 사항
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 보안 설정으로 인해 부분 신뢰 환경에서는 로컬 컴퓨터에서와는 다르게 응용 프로그램이 실행될 수 있습니다.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 파일 시스템, 네트워크 및 관리되지 않는 API와 같은 중요한 로컬 리소스에 대한 액세스가 제한됩니다.  보안 설정은 보안 시스템에서는 확인할 수 없는 Microsoft Win32 API나 기타 API 호출 기능에 영향을 줍니다.  또한 파일과 데이터 액세스 및 인쇄를 비롯한 응용 프로그램의 다른 측면에도 영향을 줍니다.  부분 신뢰 환경에서의 파일 및 데이터 액세스에 대한 자세한 내용은 [Windows Forms의 파일 및 데이터 액세스 추가 보안](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)을 참조하십시오.  부분 신뢰 환경에서의 인쇄에 대한 자세한 내용은 [Windows Forms의 인쇄 추가 보안](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)을 참조하십시오.  
  
 다음 단원에서는 부분 신뢰 환경에서 실행되는 응용 프로그램에서의 클립보드 사용, 창 조작 수행 및 Win32 API 호출 방법에 대해 설명합니다.  
  
## 클립보드 액세스  
 <xref:System.Security.Permissions.UIPermission> 클래스가 클립보드에 대한 액세스를 제어하고 관련된 <xref:System.Security.Permissions.UIPermissionClipboard> 열거형 값이 액세스 수준을 나타냅니다.  다음 표에서는 가능한 권한 수준을 보여 줍니다.  
  
|UIPermissionClipboard 값|설명|  
|-----------------------------|--------|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|클립보드 사용에 제한을 받지 않습니다.|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|약간의 제한을 받으면서 클립보드를 사용할 수 있습니다.  복사 또는 잘라내기 명령 작업과 같이 클립보드에 데이터를 넣는 기능은 제한을 받지 않습니다.  텍스트 상자와 같이 붙여넣기를 허용하는 내장 컨트롤은 클립보드 데이터를 받아들일 수 있지만 사용자 정의 컨트롤은 프로그래밍 방식으로 클립보드에서 데이터를 읽을 수 없습니다.|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|클립보드를 사용할 수 없습니다.|  
  
 기본적으로 로컬 인트라넷 영역에는 <xref:System.Security.Permissions.UIPermissionClipboard> 액세스가 부여되고 인터넷 영역에는 <xref:System.Security.Permissions.UIPermissionClipboard> 액세스가 부여됩니다.  이것은 응용 프로그램에서 클립보드에 데이터를 복사할 수는 있지만 프로그래밍 방식으로 클립보드에 데이터를 붙여넣거나 클립보드에서 데이터를 읽을 수는 없다는 것을 의미합니다.  이러한 제한으로 인해 신뢰 수준이 완전 신뢰가 아닌 프로그램은 다른 응용 프로그램이 클립보드에 복사한 내용을 읽을 수 없습니다.  응용 프로그램에 클립보드에 대한 모든 액세스가 필요하지만 해당 권한이 없을 경우에는 응용 프로그램의 권한을 높여야 합니다.  권한 높이기에 대한 자세한 내용은 [일반 보안 정책 관리](http://msdn.microsoft.com/ko-kr/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)를 참조하십시오.  
  
## 창 조작  
 <xref:System.Security.Permissions.UIPermission> 클래스는 창 조작 및 기타 UI 관련 작업을 수행할 수 있는 권한도 제어하며 관련된 <xref:System.Security.Permissions.UIPermissionWindow> 열거형 값은 액세스 수준을 나타냅니다.  다음 표에서는 가능한 권한 수준을 보여 줍니다.  
  
 기본적으로 로컬 인트라넷 영역에는 <xref:System.Security.Permissions.UIPermissionWindow> 액세스가 부여되고 인터넷 영역에는 <xref:System.Security.Permissions.UIPermissionWindow> 액세스가 부여됩니다.  이것은 인터넷 영역에서는 응용 프로그램이 대부분의 창 작업 및 UI 작업을 수행할 수 있지만 창의 모양이 수정된다는 것을 의미합니다.  수정된 창에는 풍선 알림\(처음 실행한 경우\)과 수정된 제목 표시줄 텍스트가 표시되며, 제목 표시줄에 닫기 단추가 없습니다.  풍선 알림과 제목 표시줄은 응용 프로그램이 부분 신뢰 환경에서 실행되고 있음을 응용 프로그램 사용자에게 알려 줍니다.  
  
|UIPermissionWindow 값|설명|  
|--------------------------|--------|  
|<xref:System.Security.Permissions.UIPermissionWindow>|사용자는 모든 창과 사용자 입력 이벤트를 제한 없이 사용할 수 있습니다.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|사용자가 안전한 최상위 창과 안전한 하위 창만 그리기 작업에 사용할 수 있고, 이러한 최상위 창 및 하위 창 내의 사용자 인터페이스에 대한 사용자 입력 이벤트만 사용할 수 있습니다.  이러한 안전한 창에는 명확하게 레이블이 지정되며 최소 및 최대 크기 제한이 있습니다.  이러한 제한은 시스템 로그온 화면이나 시스템 바탕 화면을 모방하는 등의 악의적인 스푸핑 공격을 방지하며 프로그래밍 방식으로 부모 창과 포커스 관련 API에 액세스하거나 <xref:System.Windows.Forms.ToolTip> 컨트롤을 사용하는 것을 제한합니다.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|사용자가 안전한 하위 창만 그리기 작업에 사용할 수 있고, 해당 하위 창 내의 사용자 인터페이스에 대한 사용자 입력 이벤트만 사용할 수 있습니다.  예를 들어, 브라우저 내에 표시되는 컨트롤은 안전한 하위 창입니다.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|사용자가 창이나 사용자 인터페이스 이벤트를 사용할 수 없습니다.  사용자 인터페이스를 사용할 수 없습니다.|  
  
 <xref:System.Security.Permissions.UIPermissionWindow> 열거형이 나타내는 각 권한 수준은 각 상위 권한 수준보다 더 적은 수의 작업을 허용합니다.  다음 표에서는 <xref:System.Security.Permissions.UIPermissionWindow> 및 <xref:System.Security.Permissions.UIPermissionWindow> 값이 제한하는 작업을 보여 줍니다.  각 멤버에 필요한 정확한 권한은 .NET Framework 클래스 라이브러리 설명서에서 해당 멤버에 대한 참조 항목을 참조하십시오.  
  
 <xref:System.Security.Permissions.UIPermissionWindow> 권한은 다음 표에 나열된 작업을 제한합니다.  
  
|구성 요소|제한된 작업|  
|-----------|------------|  
|<xref:System.Windows.Forms.Application>|-   <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A> 속성 설정|  
|<xref:System.Windows.Forms.Control>|-   <xref:System.Windows.Forms.Control.Parent%2A> 속성 가져오기<br />-   `Region` 속성 설정<br />-   <xref:System.Windows.Forms.Control.FindForm%2A>, <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> 및 <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A> 또는 <xref:System.Windows.Forms.Control.SetTopLevel%2A> 메서드 호출<br />-   반환된 컨트롤이 호출 컨트롤의 자식이 아닐 경우, <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> 메서드 호출<br />-   컨테이너 컨트롤 내에서 컨트롤 포커스 수정|  
|<xref:System.Windows.Forms.Cursor>|-   <xref:System.Windows.Forms.Cursor.Clip%2A> 속성 설정<br />-   <xref:System.Windows.Forms.Control.Hide%2A> 메서드 호출|  
|<xref:System.Windows.Forms.DataGrid>|-   <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A> 메서드 호출|  
|<xref:System.Windows.Forms.Form>|-   <xref:System.Windows.Forms.Form.ActiveForm%2A> 또는 <xref:System.Windows.Forms.Form.MdiParent%2A> 속성 가져오기<br />-   <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A> 또는<xref:System.Windows.Forms.Form.TopMost%2A> 속성 설정<br />-   <xref:System.Windows.Forms.Form.Opacity%2A> 속성을 50% 이하로 설정<br />-   프로그래밍 방식으로 <xref:System.Windows.Forms.Form.WindowState%2A> 속성을 <xref:System.Windows.Forms.FormWindowState>로 설정<br />-   <xref:System.Windows.Forms.Form.Activate%2A> 메서드 호출<br />-   <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle> 및 <xref:System.Windows.Forms.FormBorderStyle> <xref:System.Windows.Forms.FormBorderStyle> 열거형 값 사용|  
|<xref:System.Windows.Forms.NotifyIcon>|-   <xref:System.Windows.Forms.NotifyIcon> 구성 요소 사용은 완전히 제한됩니다.|  
  
 <xref:System.Security.Permissions.UIPermissionWindow> 값은 <xref:System.Security.Permissions.UIPermissionWindow> 값이 제한하는 작업뿐 아니라 다음 표에 나열된 작업도 제한합니다.  
  
|구성 요소|제한된 작업|  
|-----------|------------|  
|<xref:System.Windows.Forms.CommonDialog>|-   <xref:System.Windows.Forms.CommonDialog> 클래스에서 파생된 대화 상자 표시|  
|<xref:System.Windows.Forms.Control>|-   <xref:System.Windows.Forms.Control.CreateGraphics%2A> 메서드 호출<br />-   <xref:System.Windows.Forms.Control.Cursor%2A> 속성 설정|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   <xref:System.Windows.Forms.Cursor.Current%2A> 속성 설정|  
|<xref:System.Windows.Forms.MessageBox>|-   <xref:System.Windows.Forms.Form.Show%2A> 메서드 호출|  
  
### 타사 컨트롤 호스팅  
 다른 종류의 창 조작은 폼에서 타사 컨트롤을 호스팅하는 경우에 발생할 수 있습니다.  타사 컨트롤은 사용자가 직접 개발하여 컴파일하지 않은 사용자 지정 <xref:System.Windows.Forms.UserControl>입니다.  호스팅 시나리오를 악용하기는 어렵지만 타사 컨트롤이 렌더링 화면을 확장하여 폼의 전체 영역을 가리는 것은 논리적으로 가능합니다.  그런 다음 이 컨트롤은 중요한 대화 상자를 모방하여 사용자 이름\/암호 조합이나 은행 계좌 번호 등의 정보를 사용자에게 요청할 수 있습니다.  
  
 이러한 잠재적인 위험을 방지하려면 신뢰할 수 있는 공급업체의 타사 컨트롤만 사용해야 합니다.  확인할 수 없는 소스에서 다운로드한 타사 컨트롤을 사용할 경우에는 소스 코드에서 악용 가능성을 확인하는 것이 좋습니다.  소스에 악의적인 내용이 없는지 확인한 후 어셈블리를 컴파일하여 소스와 어셈블리가 일치하는지 확인해야 합니다.  
  
## Win32 API 호출  
 응용 프로그램을 디자인할 때 Win32 API 함수의 호출이 필요한 경우 비관리 코드에 액세스하게 됩니다.  이 경우 Win32 API 호출이나 값을 사용할 때는 코드가 창이나 운영 체제에 대해 수행하는 작업을 확인할 수 없습니다.  <xref:System.Security.Permissions.SecurityPermission> 클래스와 <xref:System.Security.Permissions.SecurityPermissionFlag> 열거형의 <xref:System.Security.Permissions.SecurityPermissionFlag> 값이 비관리 코드에 대한 액세스를 제어합니다.  응용 프로그램은 <xref:System.Security.Permissions.SecurityPermissionFlag> 권한이 부여된 경우에만 비관리 코드에 액세스할 수 있습니다.  기본적으로 로컬에서 실행되고 있는 응용 프로그램만 비관리 코드에 액세스할 수 있습니다.  
  
 Windows Forms의 몇몇 멤버는 비관리 코드에 대한 액세스를 제공하며 이러한 액세스에는 <xref:System.Security.Permissions.SecurityPermissionFlag> 권한이 필요합니다.  다음 표에서는 이 권한을 필요로 하는 <xref:System.Windows.Forms> 네임스페이스의 멤버를 보여 줍니다.  멤버에 필요한 권한에 대한 자세한 내용은 .NET Framework 클래스 라이브러리 설명서를 참조하십시오.  
  
|구성 요소|멤버|  
|-----------|--------|  
|<xref:System.Windows.Forms.Application>|-   <xref:System.Windows.Forms.Application.AddMessageFilter%2A> 메서드<br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A> 속성<br />-   `Exit` 메서드<br />-   <xref:System.Windows.Forms.Application.ExitThread%2A> 메서드<br />-   <xref:System.Windows.Forms.Application.ThreadException> 이벤트|  
|<xref:System.Windows.Forms.CommonDialog>|-   <xref:System.Windows.Forms.CommonDialog.HookProc%2A> 메서드<br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A> 메서드<br />-   <xref:System.Windows.Forms.CommonDialog.Reset%2A> 메서드<br />-   <xref:System.Windows.Forms.CommonDialog.RunDialog%2A> 메서드|  
|<xref:System.Windows.Forms.Control>|-   <xref:System.Windows.Forms.Control.CreateParams%2A> 메서드<br />-   <xref:System.Windows.Forms.Control.DefWndProc%2A> 메서드<br />-   <xref:System.Windows.Forms.Control.DestroyHandle%2A> 메서드<br />-   <xref:System.Windows.Forms.Control.WndProc%2A> 메서드|  
|<xref:System.Windows.Forms.Help>|-   <xref:System.Windows.Forms.Help.ShowHelp%2A> 메서드<br />-   <xref:System.Windows.Forms.Help.ShowHelpIndex%2A> 메서드|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow> 클래스|  
|<xref:System.Windows.Forms.Screen>|-   <xref:System.Windows.Forms.Screen.FromHandle%2A> 메서드|  
|<xref:System.Windows.Forms.SendKeys>|-   <xref:System.Windows.Forms.SendKeys.Send%2A> 메서드<br />-   <xref:System.Windows.Forms.SendKeys.SendWait%2A> 메서드|  
  
 응용 프로그램에 비관리 코드를 호출할 수 있는 권한이 없을 경우에는 응용 프로그램에서 <xref:System.Security.Permissions.SecurityPermissionFlag> 권한을 요청하거나 해당 기능을 구현할 수 있는 다른 방법을 고려해야 합니다. 대부분의 경우 Windows Forms은 Win32 API 함수를 관리되는 방식으로 호출할 수 있는 대안을 제공합니다.  이러한 대안이 없는 상황에서 비관리 코드에 액세스해야 할 경우에는 응용 프로그램의 권한을 높여야 합니다.  
  
 비관리 코드를 호출할 수 있는 권한을 부여하면 응용 프로그램이 거의 모든 작업을 수행할 수 있습니다.  따라서 비관리 코드를 호출할 수 있는 권한은 신뢰할 수 있는 소스의 응용 프로그램에만 부여해야 합니다.  또는 응용 프로그램에 따라 비관리 코드를 호출하는 기능을 옵션으로 지정하거나 완전 신뢰 환경에서만 이 기능을 사용하도록 할 수 있습니다.  위험한 권한에 대한 자세한 내용은 [위험한 권한 및 정책 관리](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)를 참조하십시오.  권한 높이기에 대한 자세한 내용은 [NIB: General Security Policy Administration](http://msdn.microsoft.com/ko-kr/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)를 참조하십시오.  
  
## 참고 항목  
 [Windows Forms의 파일 및 데이터 액세스 추가 보안](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)   
 [Windows Forms의 인쇄 추가 보안](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)   
 [Windows Forms의 보안 개요](../../../docs/framework/winforms/security-in-windows-forms-overview.md)   
 [Windows Forms 보안](../../../docs/framework/winforms/windows-forms-security.md)   
 [ClickOnce 응용 프로그램 보안](../Topic/Securing%20ClickOnce%20Applications.md)