---
title: "방법: 속성 변경 알림 구현 | Microsoft Docs"
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
  - "변경 알림"
  - "데이터 바인딩(data binding), 속성 변경 알림"
  - "변경 알림"
  - "속성, 변경 알림"
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 속성 변경 알림 구현
사용자가 폼을 편집할 때 미리 보기 창이 자동으로 업데이트되도록 하는 등 [바인딩 대상](GTMT) 속성에 [바인딩 소스](GTMT)의 동적 변경 내용이 자동으로 반영되도록 <xref:System.Windows.Data.BindingMode> 또는 <xref:System.Windows.Data.BindingMode> 바인딩을 지원하려면 사용자 클래스에서 적절한 속성 변경 알림을 제공해야 합니다.  이 예제에서는 <xref:System.ComponentModel.INotifyPropertyChanged>를 구현하는 클래스를 만드는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.ComponentModel.INotifyPropertyChanged>를 구현하려면 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 선언하고 `OnPropertyChanged` 메서드를 만들어야 합니다.  그런 다음 변경 알림을 제공할 각 속성에 대해 해당 속성이 업데이트될 때마다 `OnPropertyChanged`를 호출합니다.  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 `Person` 클래스를 사용하여 <xref:System.Windows.Data.BindingMode> 바인딩을 지원하는 방법에 대한 예제를 보려면 [TextBox 텍스트의 소스를 업데이트하는 시점 제어](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)를 참조하십시오.  
  
## 참고 항목  
 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)