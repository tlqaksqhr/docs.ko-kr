---
title: "방법: 바인딩된 항목 목록을 기반으로 값 산출 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), MultiBinding"
  - "MultiBinding"
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 바인딩된 항목 목록을 기반으로 값 산출
<xref:System.Windows.Data.MultiBinding>을 사용하여 [바인딩 대상](GTMT)을 속성을 소스 속성 목록에 바인딩한 다음 제공된 입력을 사용하여 값을 산출하는 논리를 적용할 수 있습니다.  이 예제에서는 <xref:System.Windows.Data.MultiBinding>을 사용하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서 `NameListData`는 두 개의 속성, `firstName`과 `lastName`을 포함하는 개체인 `PersonName` 개체의 컬렉션을 참조합니다.  다음 예제에서는 개인의 성과 이름을 표시할 때 성을 먼저 표시하는 <xref:System.Windows.Controls.TextBlock>을 만듭니다.  
  
 [!code-xml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 성이 먼저 오는 형식을 만드는 방법을 이해하려면 `NameConverter`의 구현을 살펴보십시오.  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter`는 <xref:System.Windows.Data.IMultiValueConverter> 인터페이스를 구현합니다.  `NameConverter`는 개별 바인딩의 값을 사용하여 해당 값을 값 개체 배열에 저장합니다.  <xref:System.Windows.Data.Binding> 요소가 <xref:System.Windows.Data.MultiBinding> 요소 아래에 표시되는 순서는 해당 값이 배열에 저장되는 순서입니다.  <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> 특성의 값은 <xref:System.Windows.Data.MultiBinding.Converter%2A> 메서드의 매개 변수 인수에 의해 참조됩니다. 이 메서드는 매개 변수로 전환하여 이름의 서식을 지정하는 방식을 결정합니다.  
  
## 참고 항목  
 [바인딩된 데이터 변환](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)