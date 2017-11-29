---
title: "방법: FontSizeConverter 클래스 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcf2d7348ca5b6b9d3b2edc44f92afbd46d32594
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-the-fontsizeconverter-class"></a>방법: FontSizeConverter 클래스 사용
## <a name="example"></a>예제  
 인스턴스를 만드는 방법을 보여 주는이 예제 <xref:System.Windows.FontSizeConverter> 글꼴 크기를 변경 하는 데 사용 합니다.  
  
 이 예제에서는 라는 사용자 지정 메서드를 정의 `changeSize` 의 콘텐츠를 변환 하는 <xref:System.Windows.Controls.ListBoxItem>별도 정의 된 대로 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일의 인스턴스로 <xref:System.Double>, 고 나중에 다시는 <xref:System.String>합니다. 이 메서드는 전달는 <xref:System.Windows.Controls.ListBoxItem> 에 <xref:System.Windows.FontSizeConverter> 을 변환 하는 개체는 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.ListBoxItem> 인스턴스에 <xref:System.Double>합니다. 이 값은 다음의 값으로 다시 전달 되는 <xref:System.Windows.Controls.TextBlock.FontSize%2A> 의 속성은 <xref:System.Windows.Controls.TextBlock> 요소입니다.  
  
 이 예에서는 또한 호출 하는 두 번째 사용자 지정 메서드를 정의 `changeFamily`합니다. 이 메서드는 변환의 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.ListBoxItem> 에 <xref:System.String>, 다음에 해당 값을 전달는 <xref:System.Windows.Controls.TextBlock.FontFamily%2A> 속성의는 <xref:System.Windows.Controls.TextBlock> 요소입니다.  
  
 이 예제에서는 실행되지 않습니다.  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.FontSizeConverter>
