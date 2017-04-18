---
title: "방법: 단순 바인딩 만들기 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), 단순 바인딩 만들기"
  - "단순 바인딩, 만들기"
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 단순 바인딩 만들기
이 예제에서는 단순 <xref:System.Windows.Data.Binding>을 만드는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에는 `PersonName`이라는 문자열 속성과 함께 `Person` 개체가 있습니다.  `Person` 개체는 `SDKSample`이라는 네임스페이스에 정의되어 있습니다.  
  
 다음 예제에서는 `Joe`의 `PersonName` 속성 값을 사용하여 `Person` 개체를 인스턴스화합니다.  이 작업은 `Resources` 섹션에서 수행되고 `x:Key`를 할당합니다.  
  
 [!code-xml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
[!code-xml[SimpleBinding#EndWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#endwindow)]  
  
 `PersonName` 속성을 바인딩하려면 다음을 수행합니다.  
  
 [!code-xml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 따라서 <xref:System.Windows.Controls.TextBlock>은 "Joe" 값과 함께 나타납니다.  
  
## 참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)