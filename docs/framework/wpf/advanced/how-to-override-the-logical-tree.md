---
title: "방법: 논리 트리 재정의 | Microsoft Docs"
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
  - "논리 트리(logical tree), 재정의"
  - "논리 트리 재정의"
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 논리 트리 재정의
일반적으로는 필요하지 않지만 숙련된 컨트롤 작성자의 경우에는 필요에 따라 [논리 트리](GTMT)를 재정의할 수 있습니다.  
  
## 예제  
 이 예제에서는 <xref:System.Windows.Controls.StackPanel>을 서브클래싱하여 패널이 자식 요소를 하나만 포함하고 렌더링하는 동작을 적용하기 위해 논리 트리를 재정의하는 방법을 설명합니다.  이 동작은 일반적으로 권장되지는 않지만 요소의 일반적인 논리 트리를 재정의하는 시나리오를 보여 주기 위해 이 예제에 사용되었습니다.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 논리 트리에 대한 자세한 내용은 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)를 참조하십시오.