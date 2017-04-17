---
title: "방법: 텍스트 장식 만들기 | Microsoft Docs"
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
  - "기본 형식"
  - "글꼴, 기준"
  - "글꼴, 윗줄"
  - "글꼴, 취소선"
  - "글꼴, 밑줄"
  - "윗줄 형식"
  - "취소선 형식"
  - "텍스트, 장식"
  - "입력 체계, 텍스트 장식"
  - "밑줄 형식"
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 텍스트 장식 만들기
<xref:System.Windows.TextDecoration> 개체는 텍스트에 추가할 수 있는 시각적 장식입니다.  네 개의 텍스트 장식으로 밑줄, 기준선, 취소선 및 윗줄이 있습니다.  다음 예제에서는 텍스트를 기준으로 텍스트 장식의 위치를 보여 줍니다.  
  
 ![텍스트 장식 위치의 다이어그램](../../../../docs/framework/wpf/advanced/media/textdecoration01.png "TextDecoration01")  
텍스트 장식 종류의 예  
  
 텍스트 장식을 텍스트에 추가하려면 <xref:System.Windows.TextDecoration> 개체를 만들고 해당 속성을 수정합니다.  <xref:System.Windows.TextDecoration.Location%2A> 속성을 사용하여 텍스트 장식이 나타날 위치\(예: 밑줄\)를 지정합니다.  <xref:System.Windows.TextDecoration.Pen%2A> 속성을 사용하여 텍스트 장식의 모양\(예: 단색 채우기 또는 그라데이션 색\)을 지정합니다.  <xref:System.Windows.TextDecoration.Pen%2A> 속성에 대해 값을 지정하지 않는 경우 장식의 기본값은 텍스트와 같은 색으로 지정됩니다.  <xref:System.Windows.TextDecoration> 개체를 정의한 경우 원하는 텍스트 개체의 <xref:System.Windows.TextDecorations> 컬렉션에 해당 개체를 추가합니다.  
  
 다음 예제에서는 선형 그라데이션 브러시 및 파선 펜으로 스타일이 지정된 텍스트 장식을 보여 줍니다.  
  
 ![선형 그라데이션 밑줄로 텍스트 장식](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")  
선형 그라데이션 브러시 및 파선 펜으로 스타일이 지정된 밑줄의 예  
  
 <xref:System.Windows.Documents.Hyperlink> 개체는 유동 콘텐츠 내에 하이퍼링크를 호스팅할 수 있도록 하는 인라인 수준의 유동 콘텐츠 요소입니다.  기본적으로 <xref:System.Windows.Documents.Hyperlink>는 <xref:System.Windows.TextDecoration> 개체를 사용하여 밑줄을 표시합니다.  특히 <xref:System.Windows.Documents.Hyperlink> 개체가 많은 경우 <xref:System.Windows.TextDecoration> 개체를 인스턴스화할 때 성능이 저하될 수 있습니다.  <xref:System.Windows.Documents.Hyperlink> 요소를 광범위하게 사용하는 경우 <xref:System.Windows.ContentElement.MouseEnter> 이벤트와 같은 이벤트가 트리거될 때만 밑줄이 표시되도록 할 수 있습니다.  
  
 다음 예제에서 "My MSN" 링크의 밑줄은 동적입니다. 즉, <xref:System.Windows.ContentElement.MouseEnter> 이벤트가 트리거될 때만 나타납니다.  
  
 ![TextDecoration을 표시하는 하이퍼링크](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
TextDecorations로 정의된 하이퍼링크  
  
 자세한 내용은 [하이퍼링크에 밑줄이 그어지는지 여부 지정](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)을 참조하십시오.  
  
## 예제  
 다음 코드 예제에서 밑줄 텍스트 장식은 기본 글꼴 값을 사용합니다.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 다음 코드 예제에서는 단색 브러시를 펜으로 사용하여 밑줄 텍스트 장식을 만듭니다.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 다음 코드 예제에서는 선형 그라데이션 브러시를 파선 펜으로 사용하여 밑줄 텍스트 장식을 만듭니다.  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## 참고 항목  
 <xref:System.Windows.TextDecoration>   
 <xref:System.Windows.Documents.Hyperlink>   
 [하이퍼링크에 밑줄이 그어지는지 여부 지정](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)