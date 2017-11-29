---
title: "방법: 바인딩 지우기"
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
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f8e009d00960f40abcd3c3913a15fa51f1be4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-clear-bindings"></a>방법: 바인딩 지우기
이 예에서는 개체에서 바인딩을 지우는 방법을 보여줍니다.  
  
## <a name="example"></a>예제  
 개체에서 개별 속성에서 바인딩을 지우려면 호출 <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> 다음 예제와 같이 합니다. 다음 예제에서 바인딩을 제거는 <xref:System.Windows.Controls.TextBlock.TextProperty> 의 *mytext*, <xref:System.Windows.Controls.TextBlock> 개체입니다.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 바인딩을 지우면 바인딩이 제거되므로, 종속성 속성의 값이 바인딩이 없는 값으로 변경됩니다. 이 값은 기본값, 상속된 값 또는 데이터 템플릿 바인딩의 값이 될 수 있습니다.  
  
 개체의 모든 가능한 속성에서 바인딩을 지우려면를 사용 하 여 <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.BindingOperations>  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
