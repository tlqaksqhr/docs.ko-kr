---
title: "방법: 두 컨트롤의 속성 바인딩 | Microsoft Docs"
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
  - "두 컨트롤의 속성 바인딩"
  - "컨트롤, 바인딩 속성"
  - "데이터 바인딩(data binding), 두 컨트롤의 속성 바인딩"
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 두 컨트롤의 속성 바인딩
이 예제에서는 <xref:System.Windows.Data.Binding.ElementName%2A> 속성을 사용하여 한 인스턴스화된 컨트롤의 속성을 다른 인스턴스화된 컨트롤의 속성에 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Panel.Background%2A> 속성을 <xref:System.Windows.Controls.ComboBox>의 <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 바인딩하는 방법을 보여 줍니다.  
  
 [!code-xml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 이 예제가 렌더링되면 다음과 유사합니다.  
  
 ![녹색 배경의 캔버스](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.png "DataBindingBindingDPsSample")  
  
 **참고** [바인딩 대상](GTMT) 속성\(이 예제에서는 <xref:System.Windows.Controls.Panel.Background%2A> 속성\)은 [종속성 속성](GTMT)이어야 합니다.  자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [바인딩 소스 지정](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)