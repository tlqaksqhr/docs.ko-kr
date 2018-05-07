---
title: Windows 런타임에 URI 전달
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7a31a1246fe311c36e7457327c79aeeef30e7813
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Windows 런타임에 URI 전달
Windows 런타임 메서드는 절대 URI만 허용합니다. 상대 URI를 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 메서드에 전달하면 <xref:System.ArgumentException> 예외가 throw됩니다. 이유는 다음과 같습니다: 사용 하는 경우는 [!INCLUDE[wrt](../../../includes/wrt-md.md)] .NET Framework 코드에서는 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 로 표시 된 클래스 <xref:System.Uri?displayProperty=nameWithType> Intellisense에 있습니다. <xref:System.Uri?displayProperty=nameWithType> 클래스에는 상대 Uri를 허용 하지만 <xref:Windows.Foundation.Uri?displayProperty=nameWithType> 클래스는 그렇지 않습니다. 이는 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 구성 요소에 노출하는 메서드의 경우에도 마찬가지입니다. 구성 요소가 URI를 사용하는 메서드를 노출하면 코드의 서명에 <xref:System.Uri?displayProperty=nameWithType>가 포함됩니다. 그러나 구성 요소의 사용자에 게는 시그니처에 <xref:Windows.Foundation.Uri?displayProperty=nameWithType>합니다. 구성 요소에 전달된 URI는 절대 URI여야 합니다.  
  
 이 항목은 절대 URI를 검색하는 방법과 앱 패키지의 리소스를 참조하는 경우 절대 URI를 만드는 방법을 보여 줍니다.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>절대 URI 검색 및 사용  
 <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> 속성을 사용하여 [!INCLUDE[wrt](../../../includes/wrt-md.md)]에 전달하기 전에 URI가 절대 URI인지 확인합니다. 이 속성을 사용하는 것이 <xref:System.ArgumentException> 예외를 catch하고 처리하는 것보다 효율적입니다.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>앱 패키지의 리소스에 절대 URI 사용  
 앱 패키지에 포함된 리소스에 URI를 지정하려면 `ms-appx` 또는 `ms-appx-web` 체계를 사용하여 절대 URI를 생성할 수 있습니다.  
  
 설정 하는 방법을 보여 주는 다음 예제는 [소스](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) 속성에 대 한는 [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) 제어 및 [소스](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) 속성에 대 한 프로그램 [이미지](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) 컨트롤 XAML 및 코드를 모두 사용 하 여 페이지 라는 폴더에 포함 된 리소스입니다.  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 이러한 스키마에 대 한 자세한 내용은 참조 [URI 체계](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) Windows 개발자 센터에서.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
