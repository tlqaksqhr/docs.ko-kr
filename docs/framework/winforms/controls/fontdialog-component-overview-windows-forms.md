---
title: "FontDialog 구성 요소 개요(Windows Forms) | Microsoft Docs"
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
  - "FontDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "글꼴 대화 상자"
  - "글꼴 대화 상자, Windows Forms"
  - "FontDialog 구성 요소[Windows Forms], FontDialog 구성 요소 정보"
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# FontDialog 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.FontDialog> 구성 요소는 미리 구성된 대화 상자로서 현재 시스템에 설치된 글꼴을 나타내는 데 사용하는 표준 Windows **글꼴** 대화 상자입니다.  Windows 기반 응용 프로그램에서 고유한 대화 상자를 구성하는 대신 이 구성 요소를 사용하면 글꼴을 선택할 수 있는 대화 상자를 쉽게 만들 수 있습니다.  
  
 대화 상자에는 기본적으로 글꼴, 글꼴 스타일 및 크기를 설정하는 목록 상자, 취소선 및 밑줄 등의 효과를 선택하는 확인란, 스크립트를 설정하는 드롭다운 목록, 글꼴 미리보기 등이 표시됩니다.  스크립트는 히브리어나 일본어와 같은 특정 글꼴에서 사용할 수 있는 다른 문자 스크립트를 말합니다. 글꼴 대화 상자를 표시하려면 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 호출합니다.  
  
## 키 속성  
 이 구성 요소에는 모양을 구성하는 속성이 많습니다.  대화 상자의 선택 항목을 설정하는 속성은 <xref:System.Windows.Forms.FontDialog.Font%2A> 및 <xref:System.Windows.Forms.FontDialog.Color%2A>입니다.  <xref:System.Windows.Forms.FontDialog.Font%2A> 속성은  `Arial, 10pt, style=Italic, Strikeout`과 같이 글꼴, 스타일, 크기, 스크립트 및 효과를 설정합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.FontDialog>   
 [FontDialog 구성 요소](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)