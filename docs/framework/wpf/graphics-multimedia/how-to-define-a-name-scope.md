---
title: "방법: 이름 범위 정의 | Microsoft Docs"
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
  - "애니메이션, 스토리보드, 프로시저 코드"
  - "이름 범위, 정의"
  - "스토리보드, 프로시저 코드에서 애니메이션 적용"
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 이름 범위 정의
코드에서 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 애니메이션 효과를 주려면 <xref:System.Windows.NameScope>를 만들고 대상 개체의 이름을 해당 이름 범위를 소유하는 요소에 등록해야 합니다.  다음 예제에서는 `myMainPanel`에 대한 <xref:System.Windows.NameScope>를 만듭니다.  그런 다음 `button1` 및 `button2`라는 단추 두 개를 패널에 추가하고 이름을 등록한 후  다양한 애니메이션과 <xref:System.Windows.Media.Animation.Storyboard>를 만듭니다.  애니메이션을 시작하는 데에는 Storyboard의 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드가 사용됩니다.  
  
 `button1`, `button2` 및 `myMainPanel` 모두 동일한 이름 범위를 공유하기 때문에 그 중 하나를 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드와 함께 사용하여 애니메이션을 시작할 수 있습니다.  
  
## 예제  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## 참고 항목  
 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)