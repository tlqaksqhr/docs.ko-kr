---
title: "방법: 코드에서 바인딩 만들기 | Microsoft Docs"
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
  - "데이터 바인딩, 만들기"
  - "데이터 바인딩(data binding), 만들기"
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# 방법: 코드에서 바인딩 만들기
이 예제에서는 코드로 <xref:System.Windows.Data.Binding>을 만들고 설정하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.FrameworkElement> 클래스와 <xref:System.Windows.FrameworkContentElement> 클래스는 둘 다 `SetBinding` 메서드를 노출합니다.  이러한 클래스 중 하나를 상속하는 요소를 바인딩하는 경우에는 <xref:System.Windows.FrameworkElement.SetBinding%2A> 메서드를 직접 호출할 수 있습니다.  
  
 다음 예제에서는 `MyDataProperty` 속성을 포함하는 `MyData` 클래스를 만듭니다.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 다음 예제에서는 바인딩 개체를 만들어 바인딩의 소스를 설정하는 방법을 보여 줍니다.  이 예제에서는<xref:System.Windows.FrameworkElement.SetBinding%2A>을 사용하여 <xref:System.Windows.Controls.TextBlock> 컨트롤인 `myText`의 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성을 `MyDataProperty`에 바인딩합니다.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 샘플의 전체 코드를 보려면 [Code\-only Binding Sample](http://msdn.microsoft.com/ko-kr/764aaf0b-2216-4941-9548-9c98da18d1a6)을 참조하십시오.  
  
 <xref:System.Windows.FrameworkElement.SetBinding%2A>을 호출하는 대신 <xref:System.Windows.Data.BindingOperations> 클래스의 <xref:System.Windows.Data.BindingOperations.SetBinding%2A> 정적 메서드를 사용할 수 있습니다.  다음 예제에서는 <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=fullName> 대신 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=fullName>을 호출하여 `myText`를 `myDataProperty`에 바인딩합니다.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## 참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)