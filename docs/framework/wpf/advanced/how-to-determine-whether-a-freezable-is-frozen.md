---
title: "방법: Freezable의 고정 여부 확인 | Microsoft Docs"
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
  - "Freezable 개체, 고정 여부 결정"
  - "IsFrozen 속성"
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: Freezable의 고정 여부 확인
이 예제에서는 <xref:System.Windows.Freezable> 개체의 고정 여부를 확인하는 방법을 보여 줍니다.  고정된 <xref:System.Windows.Freezable> 개체를 수정하려고 하면 <xref:System.InvalidOperationException>이 throws됩니다.  이 예외가 throw되지 않도록 하려면 <xref:System.Windows.Freezable> 개체의 <xref:System.Windows.Freezable.IsFrozen%2A> 속성을 사용하여 고정 여부를 확인합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush>를 고정한 다음 <xref:System.Windows.Freezable.IsFrozen%2A> 속성으로 테스트하여 고정 여부를 확인합니다.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <xref:System.Windows.Freezable> 개체에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.IsFrozen%2A>   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)