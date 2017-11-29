---
title: "방법: Freezable을 읽기 전용으로 설정"
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
helpviewer_keywords: Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c407a2fcccfbda29ba23f63ba6ae71302c734d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-a-freezable-read-only"></a>방법: Freezable을 읽기 전용으로 설정
확인 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Freezable> 호출 하 여 읽기 전용 해당 <xref:System.Windows.Freezable.Freeze%2A> 메서드.  
  
 고정할 수 없습니다는 <xref:System.Windows.Freezable> 다음 조건 중 하나라도 않은 경우 개체 `true` 개체에 대 한 합니다.  
  
-   애니메이션이 적용 또는 데이터 바인딩된 속성입니다.  
  
-   동적 리소스에서 설정 하는 속성이 있습니다. 동적 리소스에 대 한 자세한 내용은 참조는 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.  
  
-   포함 된 <xref:System.Windows.Freezable> 고정할 수 없는 하위 개체입니다.  
  
 이러한 조건이 `false` 에 대 한 프로그램 <xref:System.Windows.Freezable> 개체 하지 않으려는 수정 성능을 향상 시키는 것을 고려 하십시오.  
  
## <a name="example"></a>예제  
 다음 예제에서는 고정 한 <xref:System.Windows.Media.SolidColorBrush>의 형식인 <xref:System.Windows.Freezable> 개체입니다.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체 참조는 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
