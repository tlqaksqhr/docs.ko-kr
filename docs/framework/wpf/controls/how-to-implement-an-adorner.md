---
title: "방법: 표시기 구현 | Microsoft Docs"
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
  - "표시기(adorner), 구현"
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 표시기 구현
다음 예제에서는 최소한의 표시기\(adorner\) 구현을 보여 줍니다.  
  
## 구현자 참고 사항  
 표시기에는 어떠한 고유 렌더링 동작도 포함되지 않으므로 표시기 구현자가 표시기를 렌더링해야 합니다.  일반적으로 렌더링 동작을 구현할 때는 <xref:System.Windows.UIElement.OnRender%2A> 메서드를 재정의하고 필요에 따라 하나 이상의 <xref:System.Windows.Media.DrawingContext> 개체를 사용하여 표시기의 시각적 요소를 렌더링합니다\(이 예제 참조\).  
  
## 예제  
  
### 설명  
 사용자 지정 표시기는 추상 <xref:System.Windows.Documents.Adorner> 클래스에서 상속되는 클래스를 구현하여 생성됩니다.  이 예제에서 보여 주는 표시기는 <xref:System.Windows.UIElement.OnRender%2A> 메서드를 재정의하여 원으로 <xref:System.Windows.UIElement>의 모퉁이에 간단하게 표시합니다.  
  
### 코드  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## 참고 항목  
 [표시기 개요](../../../../docs/framework/wpf/controls/adorners-overview.md)