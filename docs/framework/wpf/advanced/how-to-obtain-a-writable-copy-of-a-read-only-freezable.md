---
title: "방법: 읽기 전용 Freezable의 쓰기 가능한 복사본 가져오기 | Microsoft Docs"
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
  - "Freezable 개체 복제"
  - "Freezable 개체, 수정 가능한 복제본"
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 읽기 전용 Freezable의 쓰기 가능한 복사본 가져오기
이 예제에서는 <xref:System.Windows.Freezable.Clone%2A> 메서드를 사용하여 읽기 전용 <xref:System.Windows.Freezable>의 쓰기 가능한 복사본을 만드는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Freezable> 개체가 읽기 전용\("고정"\)으로 표시된 뒤에는 이를 수정할 수 있습니다.  하지만 <xref:System.Windows.Freezable.Clone%2A> 메서드를 사용하여 고정된 개체의 수정 가능한 복제본을 만들 수 있습니다.  
  
## 예제  
 다음 예제에서는 고정된 <xref:System.Windows.Media.SolidColorBrush> 개체의 수정 가능한 복제본을 만듭니다.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <xref:System.Windows.Freezable> 개체에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)