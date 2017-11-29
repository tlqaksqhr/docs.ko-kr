---
title: "방법: 주 응용 프로그램 창 가져오기 및 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d6bca158172fd3fc31526287c6d4a9928a8ea0c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-get-and-set-the-main-application-window"></a>방법: 주 응용 프로그램 창 가져오기 및 설정
이 예제에는 주 응용 프로그램 창 가져오기 및 설정 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 첫 번째 <xref:System.Windows.Window> 내에서 인스턴스화됩니다는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램 자동으로 설정 되어 <xref:System.Windows.Application> 주 응용 프로그램 창으로 합니다. 첫 번째 <xref:System.Windows.Window> 되도록 인스턴스화된는 가능성이 가장 높은 수의 시작으로 지정 된 창 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (참조 <xref:System.Windows.Application.StartupUri%2A>).  
  
 첫 번째 <xref:System.Windows.Window> 도 코드를 사용 하 여 인스턴스화할 수 없습니다. 한 가지 예는 다음과 같은 응용 프로그램 시작 하는 동안 창을 엽니다.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 경우에 따라 첫 번째 인스턴스화된 <xref:System.Windows.Window> 는 실제로 기본 응용 프로그램 창 예: 시작 화면. 이 경우 다음과 같은 태그를 사용 하 여 기본 응용 프로그램 시간을 지정할 수 있습니다.  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 주 창에서 주 창 자동 또는 수동으로 지정 하는지 여부를 얻을 수 있습니다 <xref:System.Windows.Application.MainWindow%2A> 다음 코드는 다음과 같이 사용 하 여:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
