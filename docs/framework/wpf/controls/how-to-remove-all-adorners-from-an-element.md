---
title: "방법: 요소에서 모든 표시기 제거 | Microsoft Docs"
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
  - "표시기(adorner), 제거"
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 요소에서 모든 표시기 제거
이 예제에서는 지정한 <xref:System.Windows.UIElement>에서 모든 표시기를 프로그래밍 방식으로 제거하는 방법을 보여 줍니다.  
  
## 예제  
 이 자세한 코드 예제에서는 <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>에서 반환된 표시기 배열에서 모든 표시기를 제거합니다.  이 예제는 *myTextBox*라는 <xref:System.Windows.UIElement>에서 표시기를 검색합니다.  <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> 호출에 지정된 요소에 표시기가 없는 경우에는 `null`이 반환됩니다.  이 코드는 null 배열을 명시적으로 검사하며 null 배열이 비교적 많이 나타나는 응용 프로그램에 적합합니다.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## 예제  
 이 요약 코드 예제는 위의 자세한 예제와 기능적으로 동일합니다.  이 코드에서는 null 배열을 명시적으로 검사하지 않으므로 <xref:System.NullReferenceException> 예외가 발생할 수 있습니다.  이 코드는 null 배열이 많지 않은 응용 프로그램에 적합합니다.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## 참고 항목  
 [표시기 개요](../../../../docs/framework/wpf/controls/adorners-overview.md)