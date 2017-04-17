---
title: "방법: 하이퍼링크에 밑줄이 그어지는지 여부 지정 | Microsoft Docs"
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
  - "클래스, TextDecoration"
  - "Hyperlink 컨트롤 형식"
  - "TextDecoration 클래스"
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 하이퍼링크에 밑줄이 그어지는지 여부 지정
<xref:System.Windows.Documents.Hyperlink> 개체는 유동 콘텐츠 내에 하이퍼링크를 호스팅할 수 있도록 하는 인라인 수준의 유동 콘텐츠 요소입니다.  기본적으로 <xref:System.Windows.Documents.Hyperlink>는 <xref:System.Windows.TextDecoration> 개체를 사용하여 밑줄을 표시합니다.  특히 <xref:System.Windows.Documents.Hyperlink> 개체가 많은 경우 <xref:System.Windows.TextDecoration> 개체를 인스턴스화할 때 성능이 저하될 수 있습니다.  <xref:System.Windows.Documents.Hyperlink> 요소를 광범위하게 사용하는 경우 <xref:System.Windows.ContentElement.MouseEnter> 이벤트와 같은 이벤트가 트리거될 때만 밑줄이 표시되도록 할 수 있습니다.  
  
 다음 예제에서 "My MSN" 링크의 밑줄은 동적입니다. 즉, <xref:System.Windows.ContentElement.MouseEnter> 이벤트가 트리거될 때만 나타납니다.  
  
 ![TextDecoration을 표시하는 하이퍼링크](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
TextDecorations로 정의된 하이퍼링크  
  
## 예제  
 다음 태그 샘플에서는 밑줄을 사용하거나 사용하지 않고 정의된 <xref:System.Windows.Documents.Hyperlink>를 보여 줍니다.  
  
 [!code-xml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 다음 코드 샘플에서는 <xref:System.Windows.ContentElement.MouseEnter> 이벤트가 발생할 때 <xref:System.Windows.Documents.Hyperlink>에 밑줄을 그리고 <xref:System.Windows.ContentElement.MouseLeave> 이벤트가 발생할 때 밑줄을 지우는 방법을 보여 줍니다.  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## 참고 항목  
 <xref:System.Windows.TextDecoration>   
 <xref:System.Windows.Documents.Hyperlink>   
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [텍스트 장식 만들기](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)