---
title: HelpProvider 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 5ad74b862c09734f3490210cb6898945a3c787fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="helpprovider-component-overview-windows-forms"></a>HelpProvider 구성 요소 개요(Windows Forms)
Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) Windows 응용 프로그램에 HTML 도움말 1.x 도움말 파일 (HTML Help Workshop으로 생성 된.chm 파일 또는.htm 파일)을 연결할 구성 요소를 사용 합니다. 다양 한 방법에에서 대 한 도움말을 제공할 수 있습니다.  
  
-   Windows Forms에서 컨트롤에 대 한 상황에 맞는 도움말을 제공 합니다.  
  
-   특정 대화 상자 또는 대화 상자에 특정 컨트롤에 상황에 맞는 도움말을 제공 합니다.  
  
-   도움말 파일을 목차, 색인 또는 검색 기능의 기본 페이지 등의 특정 영역을 엽니다.  
  
## <a name="using-the-help-provider"></a>도움말 공급자를 사용 하 여  
 추가 <xref:System.Windows.Forms.HelpProvider> Windows Form에 구성 요소는 폼의 도움말 속성을 노출 하는 다른 컨트롤에 허용 된 <xref:System.Windows.Forms.HelpProvider> 구성 요소입니다. 그러면 Windows Form의 컨트롤에 대 한 도움말을 제공할 수 있습니다. 도움말 파일을 연결할 수 있습니다는 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용 하는 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 속성입니다. 호출 하 여 제공 된 도움말의 형식을 지정 <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> 의 값을 제공 하는 <xref:System.Windows.Forms.HelpNavigator> 지정된 된 컨트롤에 대 한 열거형입니다. 호출 하 여 도움말에 대 한 키워드 또는 항목을 제공 된 <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> 메서드.  
  
 필요에 따라 다른 컨트롤과 특정 도움말 문자열을 연결 하려면 사용 된 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 메서드. 이 메서드를 사용 하 여 컨트롤에 연결 하는 문자열은 컨트롤에 포커스가 있을 때 F1 키를 누를 때 팝업 창에 표시 됩니다.  
  
 경우 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 사용 해야 설정 되지 않았습니다 <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> 도움말 텍스트만 제공 합니다. 모두 설정 하면 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 도움말 문자열에 따라 도움말 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 우선 적용 됩니다.  
  
> [!NOTE]
>  상대 경로 사용 하 여 문제가 발생할 수 있습니다 때 도움말 파일의 경로를 지정 하는 경우에는 <xref:System.Windows.Forms.Help.ShowHelp%2A> 메서드 또는 <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> 의 속성은 <xref:System.Windows.Forms.HelpProvider> 제어 합니다. 이와 같이 절대 파일 경로 사용 하 여 도움말 파일을 지정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 응용 프로그램의 도움말 시스템](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
