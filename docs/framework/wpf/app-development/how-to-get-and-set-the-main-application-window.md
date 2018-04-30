---
title: '방법: 주 응용 프로그램 창 가져오기 및 설정'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9bdc96c509f88650edd93ba4a7f595e2b161db39
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="2b8c0-102">방법: 주 응용 프로그램 창 가져오기 및 설정</span><span class="sxs-lookup"><span data-stu-id="2b8c0-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="2b8c0-103">이 예제에는 주 응용 프로그램 창 가져오기 및 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c0-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b8c0-104">예제</span><span class="sxs-lookup"><span data-stu-id="2b8c0-104">Example</span></span>  
 <span data-ttu-id="2b8c0-105">첫 번째 <xref:System.Windows.Window> 내는 WPF Windows Presentation Foundation ()에서 응용 프로그램은 자동으로 설정 인스턴스화된 <xref:System.Windows.Application> 주 응용 프로그램 창으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c0-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="2b8c0-106">첫 번째 <xref:System.Windows.Window> 되도록 인스턴스화된는 가능성이 가장 높은 수의 시작으로 지정 된 창 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (참조 <xref:System.Windows.Application.StartupUri%2A>).</span><span class="sxs-lookup"><span data-stu-id="2b8c0-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="2b8c0-107">첫 번째 <xref:System.Windows.Window> 도 코드를 사용 하 여 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c0-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="2b8c0-108">한 가지 예는 다음과 같은 응용 프로그램 시작 하는 동안 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c0-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="2b8c0-109">경우에 따라 첫 번째 인스턴스화된 <xref:System.Windows.Window> 는 실제로 기본 응용 프로그램 창 예: 시작 화면.</span><span class="sxs-lookup"><span data-stu-id="2b8c0-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="2b8c0-110">이 경우 다음과 같은 태그를 사용 하 여 기본 응용 프로그램 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b8c0-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="2b8c0-111">주 창에서 주 창 자동 또는 수동으로 지정 하는지 여부를 얻을 수 있습니다 <xref:System.Windows.Application.MainWindow%2A> 다음 코드는 다음과 같이 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="2b8c0-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
