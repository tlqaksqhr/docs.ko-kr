---
title: "시작(WPF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- getting started [WPF]
- introduction [WPF]
- WPF [WPF], getting started
ms.assetid: 04f91da8-708c-46c7-8172-f1695ec847cd
caps.latest.revision: "60"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a8f1181b9ba418e55c2558e3aeb679623eb350b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="getting-started-wpf"></a><span data-ttu-id="55e4b-102">시작(WPF)</span><span class="sxs-lookup"><span data-stu-id="55e4b-102">Getting Started (WPF)</span></span>
<span data-ttu-id="55e4b-103">WPF(Windows Presentation Foundation)는 데스크톱 클라이언트 응용 프로그램을 만드는 UI 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="55e4b-103">Windows Presentation Foundation (WPF) is a UI framework that creates desktop client applications.</span></span> <span data-ttu-id="55e4b-104">WPF 개발 플랫폼은 응용 프로그램 모델, 리소스, 컨트롤, 그래픽, 레이아웃, 데이터 바인딩, 문서 및 보안을 포함하여 다양한 응용 프로그램 개발 기능 집합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="55e4b-104">The WPF development platform supports a broad set of application development features, including an application model, resources, controls, graphics, layout, data binding, documents, and security.</span></span> <span data-ttu-id="55e4b-105">.NET Framework의 하위 집합이므로 이전에 ASP.NET 또는 Windows Forms를 사용하여 .NET Framework로 응용 프로그램을 빌드한 경우 프로그래밍 환경이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="55e4b-105">It is a subset of the .NET Framework, so if you have previously built applications with the .NET Framework using ASP.NET or Windows Forms, the programming experience should be familiar.</span></span> <span data-ttu-id="55e4b-106">WPF는 XAML(Extensible Application Markup Language)을 사용하여 응용 프로그램 프로그래밍을 위한 선언적 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55e4b-106">WPF uses the Extensible Application Markup Language (XAML) to provide a declarative model for application programming.</span></span> <span data-ttu-id="55e4b-107">이 섹션의 항목에서는 WPF를 소개하고 WPF를 시작하는 데 유용한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55e4b-107">This section has topics that introduce and help you get started with WPF.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="55e4b-108">시작 지점</span><span class="sxs-lookup"><span data-stu-id="55e4b-108">Where Should I Start?</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55e4b-109">바로 시작</span><span class="sxs-lookup"><span data-stu-id="55e4b-109">I want to jump right in…</span></span>|[<span data-ttu-id="55e4b-110">연습: 내 첫 WPF 데스크톱 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="55e4b-110">Walkthrough: My first WPF desktop application</span></span>](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|  
|<span data-ttu-id="55e4b-111">응용 프로그램 UI를 디자인하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="55e4b-111">How do I design the application UI?</span></span>|[<span data-ttu-id="55e4b-112">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="55e4b-112">Designing XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)|  
|<span data-ttu-id="55e4b-113">.NET을 처음 사용하세요?</span><span class="sxs-lookup"><span data-stu-id="55e4b-113">New to .NET?</span></span>|<span data-ttu-id="55e4b-114">[.NET Framework의 개요](https://msdn.microsoft.com/library/zw4w595w\(v=vs.140\).aspx)</span><span class="sxs-lookup"><span data-stu-id="55e4b-114">[Overview of the .NET Framework](https://msdn.microsoft.com/library/zw4w595w\(v=vs.140\).aspx)</span></span><br /><br /> [<span data-ttu-id="55e4b-115">.NET Framework 응용 프로그램 주요 사항</span><span class="sxs-lookup"><span data-stu-id="55e4b-115">.NET Framework Application Essentials</span></span>](../../../../docs/standard/application-essentials.md)<br /><br /> <span data-ttu-id="55e4b-116">[Visual C# 및 Visual Basic 시작](https://msdn.microsoft.com/library/dd492171\(v=vs.140\).aspx)</span><span class="sxs-lookup"><span data-stu-id="55e4b-116">[Getting Started with Visual C# and Visual Basic](https://msdn.microsoft.com/library/dd492171\(v=vs.140\).aspx)</span></span>|  
|<span data-ttu-id="55e4b-117">WPF에 대한 자세한 설명...</span><span class="sxs-lookup"><span data-stu-id="55e4b-117">Tell me more about WPF…</span></span>|[<span data-ttu-id="55e4b-118">Visual Studio 2015에서의 WPF 소개</span><span class="sxs-lookup"><span data-stu-id="55e4b-118">Introduction to WPF in Visual Studio 2015</span></span>](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)<br /><br /> [<span data-ttu-id="55e4b-119">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="55e4b-119">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)<br /><br /> [<span data-ttu-id="55e4b-120">컨트롤</span><span class="sxs-lookup"><span data-stu-id="55e4b-120">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)<br /><br /> [<span data-ttu-id="55e4b-121">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="55e4b-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)|  
|<span data-ttu-id="55e4b-122">Windows Forms 개발자인가요?</span><span class="sxs-lookup"><span data-stu-id="55e4b-122">Are you a Windows Forms developer?</span></span>|[<span data-ttu-id="55e4b-123">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="55e4b-123">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)<br /><br /> [<span data-ttu-id="55e4b-124">WPF 및 Windows Forms 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="55e4b-124">WPF and Windows Forms Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-windows-forms-interoperation.md)|  
  
## <a name="see-also"></a><span data-ttu-id="55e4b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55e4b-125">See Also</span></span>  
 [<span data-ttu-id="55e4b-126">클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="55e4b-126">Class Library</span></span>](../../../../docs/framework/wpf/class-library-wpf.md)  
 [<span data-ttu-id="55e4b-127">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="55e4b-127">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
 [<span data-ttu-id="55e4b-128">.NET Framework 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="55e4b-128">.NET Framework Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=187437)
