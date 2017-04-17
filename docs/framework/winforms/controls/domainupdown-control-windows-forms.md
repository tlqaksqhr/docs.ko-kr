---
title: "DomainUpDown 컨트롤(Windows Forms) | Microsoft Docs"
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
  - "DomainUpDown 컨트롤[Windows Forms]"
  - "spin button 컨트롤"
  - "spin button 컨트롤, up-down 컨트롤"
  - "up-down 컨트롤"
  - "up-down 컨트롤, 스핀 단추 컨트롤"
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# DomainUpDown 컨트롤(Windows Forms)
Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 목록의 위나 아래로 이동하기 위한 한 쌍의 단추와 텍스트 상자의 조합처럼 보입니다.  이 컨트롤은 선택 목록에 있는 텍스트 문자열을 표시하고 설정합니다.  사용자는 목록 사이를 이동하는 위로 이동 및 아래로 이동 단추를 클릭하거나, 위쪽 및 아래쪽 화살표 키를 누르거나, 목록에 있는 항목과 일치하는 문자열을 입력함으로써 문자열을 선택할 수 있습니다.  이 컨트롤은 사전순으로 정렬된 이름 목록에서 항목을 선택하는 용도로 사용할 수 있습니다.  이 때 목록을 정렬하려면 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 속성을 `true`로 설정해야 합니다. 이 컨트롤은 목록 상자나 콤보 상자와 기능이 매우 비슷하지만 공간을 매우 적게 차지합니다.  
  
 이 컨트롤의 주요 속성은 <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 및 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>입니다.  <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성에는 컨트롤에 텍스트 값을 표시하는 개체 목록이 있습니다.  <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>를 `false`로 설정하면 컨트롤에서 입력하는 텍스트를 자동으로 완성하여 목록에 있는 값과 일치시킵니다.  <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>을 `true`로 설정하면 마지막 항목에서 아래로 스크롤할 경우 목록의 첫 항목으로 이동하고 반대의 경우 마지막 항목으로 이동합니다.  이 컨트롤의 주요 메서드는 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 및 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>입니다.  
  
 이 컨트롤은 텍스트 문자열만 표시합니다.  컨트롤에 숫자 값을 표시하려면 <xref:System.Windows.Forms.NumericUpDown> 컨트롤을 사용합니다.  자세한 내용은 [NumericUpDown 컨트롤](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)을 참조하십시오.  
  
## 단원 내용  
 [DomainUpDown 컨트롤 개요](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 사용자가 텍스트 문자열 목록에서 찾아보거나 선택할 수 있는 <xref:System.Windows.Forms.DomainUpDown> 컨트롤의 일반적인 개념을 소개합니다.  
  
 [방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <xref:System.Windows.Forms.DomainUpDown> 컨트롤에서 표시할 텍스트 문자열을 지정하는 방법을 설명합니다.  
  
 [방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 코드로 <xref:System.Windows.Forms.DomainUpDown> 컨트롤에서 항목을 삭제하는 방법을 설명합니다.  
  
## 참조  
 <xref:System.Windows.Forms.DomainUpDown>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크가 포함되어 있습니다.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.  
  
## 관련 단원  
 [Windows Forms에서 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Windows Forms 컨트롤의 전체 목록을 제공하고 컨트롤 사용 정보에 대한 링크를 포함합니다.