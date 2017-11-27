---
title: "방법: 코드에서 바인딩 만들기"
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
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6279de3b892d64bc48b4f67c9f08bd89dd1b7d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-binding-in-code"></a>방법: 코드에서 바인딩 만들기
만들고 설정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Data.Binding> 코드에서입니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.FrameworkElement> 클래스 및 <xref:System.Windows.FrameworkContentElement> 둘 다 노출 하는 클래스는 `SetBinding` 메서드. 이러한 클래스 중 하나를 상속 하는 요소에 바인딩하는 경우 호출할 수 있습니다는 <xref:System.Windows.FrameworkElement.SetBinding%2A> 메서드를 직접 합니다.  
  
 다음 예제에서는 명명 된 인스턴스인지 클래스 `MyData`, 라는 속성이 포함 된 `MyDataProperty`합니다.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 다음 예제에서는 바인딩의 원본을 설정 하려면 바인딩 개체를 만드는 방법을 보여 줍니다.  이 예에서는 사용 <xref:System.Windows.FrameworkElement.SetBinding%2A> 바인딩할는 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성 `myText`, 변수인는 <xref:System.Windows.Controls.TextBlock> 컨트롤과 `MyDataProperty`합니다.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 전체 코드 샘플을 보려면 [코드 전용 Binding 샘플](http://msdn.microsoft.com/en-us/764aaf0b-2216-4941-9548-9c98da18d1a6)합니다.  
  
 호출 하는 대신 <xref:System.Windows.FrameworkElement.SetBinding%2A>를 사용할 수 있습니다는 <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 의 정적 메서드는 <xref:System.Windows.Data.BindingOperations> 클래스입니다. 다음 예제에서는 호출 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> 대신 <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> 바인딩할 `myText` 를 `myDataProperty`합니다.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
