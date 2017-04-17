---
title: "방법: 팝업 도움말 표시 | Microsoft Docs"
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
  - "F1 도움말, 대화 상자"
  - "폼, 도움말 표시"
  - "도움말, 대화 상자에 추가"
  - "도움말, 팝업 도움말"
  - "HelpProvider 구성 요소[Windows Forms]"
  - "모달 대화 상자, 팝업 도움말"
  - "팝업 도움말"
  - "Windows Forms, 도움말 표시"
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 팝업 도움말 표시
Windows Forms에 도움말을 표시하는 한 가지 방법은 <xref:System.Windows.Forms.Form.HelpButton%2A> 속성을 통해 액세스할 수 있는 제목 표시줄의 오른쪽에 있는 **도움말** 단추를 사용하는 것입니다.  이 도움말 표시 유형은 대화 상자에서 사용하기에 적합합니다.  모달 대화 상자를 먼저 닫아야 다른 창으로 포커스를 이동할 수 있으므로 모달 형식으로 표시되는 대화 상자\(<xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드 사용\)에서 외부 도움말 시스템을 가져오려면 문제가 발생합니다.  또한 **도움말** 단추를 사용하려면 **최소화** 단추 또는 **최대화** 단추가 제목 표시줄에 표시되지 않아야 합니다.  이는 표준 대화 상자 규칙이지만, 폼에는 일반적으로 **최소화** 및 **최대화** 단추가 있습니다.  
  
 또한 팝업 도움말을 구현한 경우에도 <xref:System.Windows.Forms.HelpProvider> 구성 요소를 사용하여 컨트롤을 도움말 시스템의 파일에 연결할 수 있습니다.  자세한 내용은 [Windows 응용 프로그램에서 도움말 제공](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)을 참조하세요.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### 팝업 도움말을 표시하려면  
  
1.  도구 상자의 [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) 구성 요소를 폼으로 끕니다.  
  
     Windows Forms 디자이너 아래쪽의 트레이에 배치됩니다.  
  
2.  속성 창에서 <xref:System.Windows.Forms.Form.HelpButton%2A> 속성을 `true`로 설정합니다.  그러면 폼의 제목 표시줄 오른쪽에 물음표가 있는 단추가 표시됩니다.  
  
3.  <xref:System.Windows.Forms.Form.HelpButton%2A>이 표시되려면 폼의 <xref:System.Windows.Forms.Form.MinimizeBox%2A> 및 <xref:System.Windows.Forms.Form.MaximizeBox%2A> 속성을 `false`로 설정하고 <xref:System.Windows.Forms.Form.ControlBox%2A> 속성을 `true`로 설정하고 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle> 또는 <xref:System.Windows.Forms.FormBorderStyle> 값 중 하나로 설정해야 합니다.  
  
4.  폼에서 도움말을 표시할 컨트롤을 선택하고 속성 창에서 도움말 문자열을 설정합니다.  이는 [도구 설명](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)과 비슷하게 창에 표시되는 텍스트 문자열입니다.  
  
5.  **F5** 키를 누릅니다.  
  
6.  제목 표시줄에서 **도움말** 단추를 누르고 도움말 문자열을 설정한 컨트롤을 클릭합니다.  
  
## 참고 항목  
 [ToolTip을 사용한 컨트롤 도움말](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)   
 [Windows Forms에 사용자 도움말 통합](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)