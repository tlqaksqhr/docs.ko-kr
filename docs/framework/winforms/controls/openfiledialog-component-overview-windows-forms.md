---
title: "OpenFileDialog 구성 요소 개요(Windows Forms) | Microsoft Docs"
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
  - "OpenFileDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "파일 열기 대화 상자, Windows Forms에 표시"
  - "OpenFileDialog 구성 요소, OpenFileDialog 정보"
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# OpenFileDialog 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.OpenFileDialog> 구성 요소는 미리 구성된 대화 상자입니다.  이 구성 요소는 Windows 운영 체제에서 볼 수 있는 **파일 열기** 대화 상자와 같으며  <xref:System.Windows.Forms.CommonDialog> 클래스에서 상속합니다.  
  
## OpenFileDialog 구성 요소 사용  
 Windows 기반 응용 프로그램에서 고유한 대화 상자를 구성하는 대신 이 구성 요소를 파일 선택을 위한 간단한 솔루션으로 사용하면  표준 Windows 대화 상자를 사용하여 사용자가 기본 기능을 쉽게 이해할 수 있는 응용 프로그램을 만들 수 있습니다.  그러나 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소를 사용하려면 고유한 파일 열기 논리를 작성해야 합니다.  
  
 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 런타임에 대화 상자를 표시합니다.  <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> 속성을 사용하면 여러 파일을 선택하여 열 수 있도록 설정할 수 있습니다.  또한 <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> 속성을 사용하면 대화 상자에 읽기 전용 확인란을 표시할지 여부를 결정할 수 있습니다.  <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> 속성은 읽기 전용 확인란이 선택되었는지 여부를 나타냅니다.  마지막으로 <xref:System.Windows.Forms.FileDialog.Filter%2A> 속성은 현재 파일 이름을 필터링할 문자열을 설정하여 대화 상자의 "파일 형식" 상자에 표시할 파일 형식을 결정합니다.  
  
 <xref:System.Windows.Forms.OpenFileDialog> 구성 요소가 폼에 추가되면 Windows Forms 디자이너의 아래쪽에 있는 트레이에 나타납니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.OpenFileDialog>   
 [OpenFileDialog 구성 요소](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)