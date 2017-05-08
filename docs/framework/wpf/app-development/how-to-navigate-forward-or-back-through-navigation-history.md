---
title: "방법: 탐색 기록을 앞으로 또는 뒤로 탐색 | Microsoft Docs"
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
  - "기록, 탐색, 앞으로 탐색"
  - "탐색, 탐색 기록을 통해(앞으로)"
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 탐색 기록을 앞으로 또는 뒤로 탐색
탐색 기록에서 항목을 앞으로 또는 뒤로 이동 하는 예제입니다.  
  
## 예제  
 콘텐츠를 다음 호스트에서 실행 되는 코드 탐색 기록, 한 번에 하나의 항목을 통해 앞으로 또는 뒤로 이동할 수 있습니다.  
  
-   <xref:System.Windows.Navigation.NavigationWindow>사용 하 여<xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame>사용 하 여<xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 앞으로 항목을 이동할 수 있습니다 전에 먼저 항목이 있는 전방 탐색 기록에서 검사 하 여 체크를  **CanGoForward** 속성입니다.  앞으로 한 항목 이동 하려면 호출을  **GoForward** 메서드.  다음 예제에서 이 과정을 보여 줍니다.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 탐색할 수 있습니다 전에 항목, 가지 항목이 후방 탐색 기록에 검사 하 여 먼저 체크 해야의  **CanGoBack** 속성입니다.  뒤로 이동 하려면 호출을  **GoBack** 방법입니다.  다음 예제에서 이 과정을 보여 줍니다.  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**,  **GoForward**,  **CanGoBack**, 및  **GoBack** 에 의해 구현 된 <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, 및 <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  사용자가 호출 하는 경우  **GoForward**, 및 전방 탐색 기록에 항목이 없습니다. 또는 사용자가 호출 하는 경우  **GoBack**, 및 후방 탐색 기록에 항목이 없습니다.는 <xref:System.InvalidOperationException> throw 됩니다.