---
title: "방법: INotifyPropertyChanged 인터페이스 구현 | Microsoft Docs"
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
  - "INotifyPropertyChanged 인터페이스, 구현"
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: INotifyPropertyChanged 인터페이스 구현
다음 코드 예제에서는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하는 방법을 보여 줍니다.  이 인터페이스는 Windows Forms 데이터 바인딩에 사용되는 비즈니스 개체에 대해 구현합니다.  이 인터페이스를 구현하면 비즈니스 개체에 대한 속성 변경 사항이 바인딩된 컨트롤에 통보됩니다.  
  
## 예제  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## 참고 항목  
 [방법: PropertyNameChanged 패턴 적용](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)   
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [방법: BindingSource와 INotifyPropertyChanged 인터페이스를 사용하여 변경 내용 알림 발생](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)   
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)