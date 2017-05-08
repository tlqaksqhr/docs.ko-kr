---
title: "방법: 열거형 바인딩 | Microsoft Docs"
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
  - "데이터 바인딩, 열거형"
  - "데이터 바인딩, 열거형"
  - "열거형"
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 열거형 바인딩
이 예제에서는 열거형의 GetValues 메서드에 바인딩하여 열거형에 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서 <xref:System.Windows.Controls.ListBox>는 데이터 바인딩을 통해 <xref:System.Windows.HorizontalAlignment> 열거형 값의 목록을 표시합니다.  <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button>은 <xref:System.Windows.Controls.ListBox>의 값을 선택하여 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성 값을 변경할 수 있도록 바인딩되어 있습니다.  
  
 [!code-xml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## 참고 항목  
 [메서드 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)