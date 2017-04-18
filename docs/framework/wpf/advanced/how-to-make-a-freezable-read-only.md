---
title: "방법: Freezable을 읽기 전용으로 설정 | Microsoft Docs"
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
  - "Freezable 개체, 읽기 전용으로 만들기"
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: Freezable을 읽기 전용으로 설정
이 예제에서는 해당 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 호출하여 <xref:System.Windows.Freezable>을 읽기 전용으로 설정하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Freezable> 개체에 대해 다음 조건 중 하나라도 `true`이면 개체를 고정할 수 없습니다.  
  
-   애니메이션이 적용되거나 데이터가 바인딩된 속성이 있습니다.  
  
-   동적 리소스로 설정된 속성이 있습니다.  동적 리소스에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
-   고정할 수 없는 <xref:System.Windows.Freezable> 하위 개체가 포함되어 있습니다.  
  
 <xref:System.Windows.Freezable>에 대해 이러한 조건이 모두 `false`이고 개체를 수정할 계획이 없는 경우에는 개체를 고정하여 성능을 향상시키는 것이 좋습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Freezable> 개체 형식의 <xref:System.Windows.Media.SolidColorBrush>를 고정합니다.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <xref:System.Windows.Freezable> 개체에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.CanFreeze%2A>   
 <xref:System.Windows.Freezable.Freeze%2A>   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)