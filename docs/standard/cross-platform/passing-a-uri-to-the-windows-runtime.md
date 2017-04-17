---
title: "Windows 런타임에 URI 전달 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Windows 런타임, .NET Framework 지원"
  - "Windows 런타임, URI 전달"
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Windows 런타임에 URI 전달
Windows 런타임 메서드는 절대 URI만 허용합니다. 상대 URI를 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 메서드에 전달하면 <xref:System.ArgumentException> 예외가 throw됩니다. .NET Framework 코드에서 [!INCLUDE[wrt](../../../includes/wrt-md.md)]을 사용하는 경우 [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) 클래스가 Intellisense에 <xref:System.Uri?displayProperty=fullName>로 표시되기 때문입니다.<xref:System.Uri?displayProperty=fullName> 클래스는 상대 URI를 허용하지만 [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) 클래스는 그렇지 않습니다. 이는 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 구성 요소에 노출하는 메서드의 경우에도 마찬가지입니다. 구성 요소가 URI를 사용하는 메서드를 노출하면 코드의 서명에 <xref:System.Uri?displayProperty=fullName>가 포함됩니다. 그러나 구성 요소의 사용자에 대해서는 서명에 [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376)를 포함합니다. 구성 요소에 전달된 URI는 절대 URI여야 합니다.  
  
 이 항목은 절대 URI를 검색하는 방법과 앱 패키지의 리소스를 참조하는 경우 절대 URI를 만드는 방법을 보여 줍니다.  
  
## 절대 URI 검색 및 사용  
 <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=fullName> 속성을 사용하여 [!INCLUDE[wrt](../../../includes/wrt-md.md)]에 전달하기 전에 URI가 절대 URI인지 확인합니다. 이 속성을 사용하는 것이 <xref:System.ArgumentException> 예외를 catch하고 처리하는 것보다 효율적입니다.  
  
## 앱 패키지의 리소스에 절대 URI 사용  
 앱 패키지에 포함된 리소스에 URI를 지정하려면 `ms-appx` 또는 `ms-appx-web` 체계를 사용하여 절대 URI를 생성할 수 있습니다.  
  
 다음 예제에서는 XAML과 코드를 모두 사용하여 [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) 컨트롤용 [Source](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) 속성과 [Image](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) 컨트롤용 [Source](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) 속성을 Pages라는 이름의 폴더에 포함된 리소스로 설정하는 방법을 보여 줍니다.  
  
 [!code-xml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 이러한 스키마에 대한 자세한 내용은 Windows 개발자 센터의 [URI 체계](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx)를 참조하세요.  
  
## 참고 항목  
 [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)