---
title: "방법: 응용 프로그램 간에 끌어서 놓기 작업 수행 | Microsoft Docs"
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
  - "끌어서 놓기, 응용 프로그램 간"
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 응용 프로그램 간에 끌어서 놓기 작업 수행
응용 프로그램 간 끌어서 놓기 작업 수행은 두 응용 프로그램이 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> 및 <xref:System.Windows.Forms.DragEventArgs.Effect%2A> 속성 간에 설정된 “계약"에 따른 행동을 포함하는 경우 응용 프로그램 내에서 이 작업을 사용하도록 설정하는 방법과 다르지 않습니다.  
  
 다음 절차에서는 생성한 Windows 기반 응용 프로그램 및 응용 프로그램 간 끌어서 놓기 작업을 수행하는 Windows 운영 체제에 포함된 워드 패드 워드 프로세서를 사용합니다.  워드 패드는 끌어서 놓기 작업을 성공적으로 완료하도록 효과를 수행하기 위한 코트를 작성하는 Windows 기반 응용 프로그램인 텍스트 끌어서 놓기 효과를 허용하는 특정 설정이 있습니다.  
  
### 응용 프로그램 간에 끌어서 놓기 프로시저를 수행하려면  
  
1.  새 Windows Forms 응용 프로그램을 만듭니다.  
  
2.  폼에 <xref:System.Windows.Forms.TextBox> 컨트롤을 추가합니다.  
  
3.  놓은 데이터를 받으려면 <xref:System.Windows.Forms.TextBox> 컨트롤을 구성합니다.  
  
     자세한 내용은 [연습: Windows Forms에서 끌어서 놓기 작업 수행](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)을 참조하세요.  
  
4.  Windows 기반 응용 프로그램을 실행하고 응용 프로그램이 실행되는 동안 워드패드를 실행합니다.  
  
     워드패드는 끌어서 놓기 작업을 허용하는 Windows에 설치된 텍스트 편집기입니다.  **시작** 단추를 누르고 **실행**은 선택한 다음 **실행** 대화 상자의 텍스트 상자에 `워드 패드`를 입력하고 **확인**을 클릭하여 액세스할 수 있습니다.  
  
5.  워드 패드를 열면 텍스트 문자열을 입력합니다.  
  
6.  마우스를 사용하여 텍스트를 선택한 다음 Windows 기반 응용 프로그램에 <xref:System.Windows.Forms.TextBox> 컨트롤 위로 선택한 텍스트를 끕니다.  
  
     <xref:System.Windows.Forms.TextBox> 컨트롤\(결과적으로 <xref:System.Windows.Forms.Control.DragEnter> 이벤트 발생\), 커서 변경 사항 위로 마우스를 이동한 경우 참조하여 <xref:System.Windows.Forms.TextBox> 컨트롤에서 선택한 텍스트를 놓을 수 있습니다.  
  
     또한 워드 패드에 끌어서 놓는 텍스트 스트링을 허용하기 위한 <xref:System.Windows.Forms.TextBox> 컨트롤을 구성할 수 있습니다.  자세한 내용은 [연습: Windows Forms에서 끌어서 놓기 작업 수행](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)을 참조하세요.  
  
## 참고 항목  
 [방법: 클립보드에 데이터 추가](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)   
 [방법: 클립보드에서 데이터 검색](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)   
 [끌어서 놓기 작업 및 클립보드 지원](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)