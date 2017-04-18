---
title: "방법: 시스템 글꼴 열거 | Microsoft Docs"
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
  - "열거, 시스템 글꼴"
  - "글꼴, 열거"
  - "시스템 글꼴, 열거"
  - "입력 체계, 시스템 글꼴 열거"
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 시스템 글꼴 열거
## 예제  
 다음 예제에서는 시스템 글꼴 컬렉션에 글꼴을 열거하는 방법을 보여 줍니다.  <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> 내에 있는 각 <xref:System.Windows.Media.FontFamily>의 글꼴 패밀리 이름은 항목으로 콤보 상자에 추가됩니다.  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 같은 글꼴 패밀리의 여러 버전이 같은 디렉터리에 있는 경우 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 글꼴 열거는 글꼴의 최신 버전을 반환합니다.  버전 정보로 문제가 해결되지 않는 경우에는 최신 타임스탬프가 있는 글꼴이 반환됩니다.  타임스탬프 정보도 같은 경우 사전순으로 먼저 정렬되는 글꼴 파일이 반환됩니다.