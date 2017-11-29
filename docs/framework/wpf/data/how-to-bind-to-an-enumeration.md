---
title: "방법: 열거형 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31fb9adbda47514e5405d465c0b5e2493b966d8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-an-enumeration"></a>방법: 열거형 바인딩
이 예제에서는 열거형의 GetValues 메서드에 바인딩하여 열거형에 바인딩하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Controls.ListBox> 의 목록을 표시 <xref:System.Windows.HorizontalAlignment> 데이터 바인딩을 통해 열거형 값입니다. <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.Button> 변경할 수 있도록 바인딩된는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 의 속성 값은 <xref:System.Windows.Controls.Button> 에 값을 선택 하 여는 <xref:System.Windows.Controls.ListBox>합니다.  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a>참고 항목  
 [메서드 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
