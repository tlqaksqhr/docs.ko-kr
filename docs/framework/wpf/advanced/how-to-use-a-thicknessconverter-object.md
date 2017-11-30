---
title: "방법: ThicknessConverter 개체 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ce70dcd749f31d77061b4669d83d2e0b83726c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-thicknessconverter-object"></a>방법: ThicknessConverter 개체 사용
## <a name="example"></a>예제  
 인스턴스를 만드는 방법을 보여 주는이 예제 <xref:System.Windows.ThicknessConverter> 테두리의 두께 변경 하는 데 사용 합니다.  
  
 이 예제에서는 라는 사용자 지정 메서드를 정의 `changeThickness`;이 메서드는 먼저의 내용을 변환는 <xref:System.Windows.Controls.ListBoxItem>별도 정의 된 대로 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일의 인스턴스로 <xref:System.Windows.Thickness>, 나중에 콘텐츠를 변환 하 고는 <xref:System.String>합니다. 이 메서드는 전달는 <xref:System.Windows.Controls.ListBoxItem> 에 <xref:System.Windows.ThicknessConverter> 을 변환 하는 개체는 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.ListBoxItem> 인스턴스에 <xref:System.Windows.Thickness>합니다. 이 값은 다음의 값으로 다시 전달 되는 <xref:System.Windows.Controls.Border.BorderThickness%2A> 의 속성은 <xref:System.Windows.Controls.Border>합니다.  
  
 이 예제에서는 실행되지 않습니다.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Thickness>  
 <xref:System.Windows.ThicknessConverter>  
 <xref:System.Windows.Controls.Border>  
 [방법: Margin 속성 변경](http://msdn.microsoft.com/en-us/8a313efd-5f99-4097-b4c1-8fa49d8379a2)  
 [방법: ListBoxItem을 새 데이터 형식으로 변환 합니다.](http://msdn.microsoft.com/en-us/7a080b88-184e-4b27-bb61-d42bafba9727)  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)
