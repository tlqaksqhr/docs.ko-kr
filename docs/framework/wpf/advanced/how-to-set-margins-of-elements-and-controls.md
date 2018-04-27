---
title: '방법: 요소 및 컨트롤의 여백 설정'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f32107074239e9713feaa9e0b9b7e1f89869d111
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-margins-of-elements-and-controls"></a>방법: 요소 및 컨트롤의 여백 설정
이 예제에서는 설정 하는 방법을 설명는 <xref:System.Windows.FrameworkElement.Margin%2A> 여백 코드 숨김에 대 한 기존 속성 값을 변경 하 여 속성입니다. <xref:System.Windows.FrameworkElement.Margin%2A> 속성은 속성의는 <xref:System.Windows.FrameworkElement> 기본 요소를 하며 따라서 다양 한 컨트롤 및 기타 요소에서 상속 됩니다.  
  
 이 예제로 작성 된 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 코드 숨김 파일을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 가리킵니다. 관련 코드는 C#과 Microsoft Visual Basic 버전 모두에 표시 됩니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
