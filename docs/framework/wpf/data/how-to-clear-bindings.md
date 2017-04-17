---
title: "방법: 바인딩 지우기 | Microsoft Docs"
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
  - "바인딩, 지우기"
  - "바인딩 지우기"
  - "데이터 바인딩(data binding), 바인딩 지우기"
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 바인딩 지우기
이 예제에서는 개체에서 바인딩을 지우는 방법을 보여 줍니다.  
  
## 예제  
 개체의 개별 속성에서 바인딩을 지우려면 다음 예제와 같이 <xref:System.Windows.Data.BindingOperations.ClearBinding%2A>을 호출합니다.  다음 예제에서는 <xref:System.Windows.Controls.TextBlock> 개체인 *mytext*의 <xref:System.Windows.Controls.TextBlock.TextProperty>에서 바인딩을 제거합니다.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 바인딩을 지우면 [종속성 속성](GTMT) 값이 바인딩이 없었을 때의 값으로 변경되도록 바인딩이 제거됩니다.  이 값은 기본값, 상속된 값 또는 데이터 템플릿 바인딩의 값이 될 수 있습니다.  
  
 개체의 모든 가능한 속성에서 바인딩을 지우려면 <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>를 사용합니다.  
  
## 참고 항목  
 <xref:System.Windows.Data.BindingOperations>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)