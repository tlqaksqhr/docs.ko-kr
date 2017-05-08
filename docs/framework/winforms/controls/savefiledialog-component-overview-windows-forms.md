---
title: "SaveFileDialog 구성 요소 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SaveFileDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "파일 저장 대화 상자, 표시"
  - "SaveFileDialog 구성 요소, SaveFileDialog 정보"
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# SaveFileDialog 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.SaveFileDialog> 구성 요소는 미리 구성된 대화 상자입니다.  이 대화 상자는 Windows에서 볼 수 있는 표준 **파일 저장** 대화 상자와 같으며  <xref:System.Windows.Forms.CommonDialog> 클래스에서 상속합니다.  
  
## SaveFileDialog 구성 요소 사용  
 고유한 대화 상자를 구성하는 대신 이 컨트롤을 사용하면 파일을 저장할 수 있는 대화 상자를 쉽게 만들 수 있으며  표준 Windows 대화 상자를 통해 기본 기능에 접근하기 쉬운 응용 프로그램을 만들 수 있습니다.  그러나 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소를 사용하려면 고유한 파일 저장 논리를 작성해야 합니다.  
  
 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 런타임에 대화 상자를 표시할 수 있으며  <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> 메서드를 사용하여 파일을 읽기\/쓰기 모드로 열 수 있습니다.  
  
 <xref:System.Windows.Forms.SaveFileDialog> 구성 요소가 폼에 추가되면 Windows Forms 디자이너의 아래쪽에 있는 트레이에 나타납니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.SaveFileDialog>   
 [SaveFileDialog 구성 요소](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)