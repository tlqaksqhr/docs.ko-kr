---
title: "방법: 바인딩된 대상 속성에서 바인딩 개체 가져오기 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), 바인딩된 대상 속성에서 바인딩 개체 가져오기"
  - "속성, 바인딩 개체 가져오기"
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 바인딩된 대상 속성에서 바인딩 개체 가져오기
이 예제에서는 데이터 바인딩된 대상 속성에서 바인딩 개체를 가져오는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Data.Binding> 개체를 가져오기 위해 다음을 수행할 수 있습니다.  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  대상 개체의 속성 둘 이상이 데이터 바인딩을 사용하고 있을 수 있으므로 원하는 바인딩에 대해 [종속성 속성](GTMT)을 지정해야 합니다.  
  
 또는 <xref:System.Windows.Data.BindingExpression>을 가져온 다음 <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> 속성의 값을 가져올 수 있습니다.  
  
 전체 예제를 보려면 [Binding Validation 샘플](http://go.microsoft.com/fwlink/?LinkID=159972)을 참조하십시오.  
  
> [!NOTE]
>  바인딩이 <xref:System.Windows.Data.MultiBinding>인 경우 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>을 사용합니다.  <xref:System.Windows.Data.PriorityBinding>인 경우에는 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>을 사용합니다.  대상 속성이 <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding> 또는 <xref:System.Windows.Data.PriorityBinding> 중 어느 것을 사용하여 바인딩되었는지 확실하지 않은 경우 <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>를 사용할 수 있습니다.  
  
## 참고 항목  
 [코드에서 바인딩 만들기](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)