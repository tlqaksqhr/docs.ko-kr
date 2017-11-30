---
title: "방법: 바인딩된 대상 속성에서 바인딩 개체 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 498849cc0205775f88c21d90d12b45c6b71a5dec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>방법: 바인딩된 대상 속성에서 바인딩 개체 가져오기
이 예제에서는 데이터 바인딩된 대상 속성에서 바인딩 개체를 가져오는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 가져오기 위해 다음을 수행할 수 있습니다는 <xref:System.Windows.Data.Binding> 개체:  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  대상 개체의 둘 이상의 속성이 데이터 바인딩을 사용하고 있을 수 있으므로 원하는 바인딩에 대한 종속성 속성을 지정해야 합니다.  
  
 가져올 수 있습니다는 <xref:System.Windows.Data.BindingExpression> 의 값을 가져온 후는 <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> 속성입니다.  
  
 전체 예제는 [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972)(바인딩 유효성 검사 샘플)을 참조하세요.  
  
> [!NOTE]
>  바인딩이 하는 경우는 <xref:System.Windows.Data.MultiBinding>를 사용 하 여 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>합니다. 이 경우는 <xref:System.Windows.Data.PriorityBinding>를 사용 하 여 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>합니다. 사용 하 여 대상 속성은 바인딩되어 있는지 여부는 확실 한 경우는 <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding>, 또는 <xref:System.Windows.Data.PriorityBinding>를 사용할 수 있습니다 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드에서 바인딩 만들기](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
