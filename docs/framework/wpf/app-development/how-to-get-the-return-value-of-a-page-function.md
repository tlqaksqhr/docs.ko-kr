---
title: "방법: Page 함수의 반환 값 가져오기 | Microsoft Docs"
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
  - "함수, 반환 값 가져오기"
  - "가져오기, 페이지 함수의 반환 값"
  - "페이지 함수, 반환 값 가져오기"
  - "페이지 함수의 반환 값"
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: Page 함수의 반환 값 가져오기
이 예제에서는 페이지 함수에서 반환되는 결과를 가져오는 방법을 보여 줍니다.  
  
## 예제  
 페이지 함수에서 반환되는 결과를 가져오려면 호출 중인 페이지 함수의 <xref:System.Windows.Navigation.PageFunction%601.Return>을 처리해야 합니다.  
  
 [!code-xml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## 참고 항목  
 <xref:System.Windows.Navigation.PageFunction%601>