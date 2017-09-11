---
title: ".NET Framework로 클라이언트 응용 프로그램 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client application services
- applications [Windows Forms]
- Windows Presentation Foundation, in Visual Studio
- WPF, in Visual Studio
- Windows applications
- rich client applications
- .NET applications, Windows applications
- Visual Basic code, creating applications
- Visual C#, creating applications
- client/server applications, Windows applications
ms.assetid: 2dfb50b7-5af2-4e12-9bbb-c5ade0e39a68
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: aba9547bcd96b9e8038bc973aa9ef971bb82f698
ms.openlocfilehash: 891c783429c069d7c807a9c31aff45d02f518eee
ms.contentlocale: ko-kr
ms.lasthandoff: 09/01/2017

---
# <a name="developing-client-applications-with-the-net-framework"></a><span data-ttu-id="ef0b0-102">.NET Framework로 클라이언트 응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="ef0b0-102">Developing Client Applications with the .NET Framework</span></span>
<span data-ttu-id="ef0b0-103">사용자의 컴퓨터나 장치에서 로컬로 실행되는 .NET Framework를 사용하여 Windows 기반 응용 프로그램을 개발하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-103">There are multiple ways to develop Windows-based applications with the .NET framework that run locally on users' computers or devices.</span></span> <span data-ttu-id="ef0b0-104">이 섹션에는 WPF(Windows Presentation Foundation) 또는 Windows Forms를 사용하여 Windows 기반 응용 프로그램을 만드는 방법을 설명하는 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-104">This section contains topics that describe how to create Windows-based applications by using Windows Presentation Foundation (WPF) or by using Windows Forms.</span></span> <span data-ttu-id="ef0b0-105">그러나 .NET Framework를 사용하여 dnpq 응용 프로그램을 만들고 Windows 스토어 및 Windows Phone 스토어를 통해 사용할 수 있는 컴퓨터 또는 장치용 클라이언트 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-105">However, you can also create web applications using the .NET Framework, and client applications for computers or devices that you make available through the Windows Store or Windows Phone Store.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ef0b0-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="ef0b0-106">In This Section</span></span>  
 [<span data-ttu-id="ef0b0-107">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="ef0b0-107">Windows Presentation Foundation</span></span>](../../docs/framework/wpf/index.md)  
 <span data-ttu-id="ef0b0-108">WPF를 사용한 응용 프로그램 개발 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-108">Provides information about developing applications by using WPF.</span></span>  
  
 [<span data-ttu-id="ef0b0-109">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef0b0-109">Windows Forms</span></span>](../../docs/framework/winforms/index.md)  
 <span data-ttu-id="ef0b0-110">Windows Forms를 사용한 응용 프로그램 개발 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-110">Provides information about developing applications by using Windows Forms.</span></span>  
  
 [<span data-ttu-id="ef0b0-111">일반 클라이언트 기술</span><span class="sxs-lookup"><span data-stu-id="ef0b0-111">Common Client Technologies</span></span>](../../docs/framework/common-client-technologies/index.md)  
 <span data-ttu-id="ef0b0-112">클라이언트 응용 프로그램을 개발할 때 사용할 수 있는 추가 기술에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-112">Provides information about additional technologies that can be used when developing client applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ef0b0-113">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ef0b0-113">Related Sections</span></span>  
 [<span data-ttu-id="ef0b0-114">Windows 스토어 앱</span><span class="sxs-lookup"><span data-stu-id="ef0b0-114">Windows Store apps</span></span>](http://msdn.microsoft.com/windows/apps/)  
 <span data-ttu-id="ef0b0-115">Windows 스토어를 통해 사용자에게 제공할 수 있는 앱을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-115">Describes how to create apps that you can make available to users through the Windows Store</span></span>  
  
 [<span data-ttu-id="ef0b0-116">스토어 앱용 .NET</span><span class="sxs-lookup"><span data-stu-id="ef0b0-116">.NET for Store apps</span></span>](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 <span data-ttu-id="ef0b0-117">Windows 컴퓨터와 장치에 배포할 수 있는 스토어 앱에 대한 .NET Framework 지원을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-117">Describes the .NET Framework support for Store apps, which can be deployed to Windows computers and devices.</span></span>  
  
 <span data-ttu-id="ef0b0-118">[Windows Phone Silverlight용 .NET API](http://msdn.microsoft.com/library/windows/apps/xaml/jj207211\(v=vs.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ef0b0-118">[.NET API for Windows Phone Silverlight](http://msdn.microsoft.com/library/windows/apps/xaml/jj207211\(v=vs.105\).aspx)</span></span>  
 <span data-ttu-id="ef0b0-119">Windows Phone Silverlight로 앱을 빌드하는 데 사용할 수 있는 .NET Framework API를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-119">List the .NET Framework APIs you can use for building apps with Windows Phone Silverlight</span></span>  
  
 [<span data-ttu-id="ef0b0-120">여러 플랫폼을 대상으로 개발</span><span class="sxs-lookup"><span data-stu-id="ef0b0-120">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
 <span data-ttu-id="ef0b0-121">.NET Framework를 사용하여 여러 클라이언트 앱 형식을 대상으로 지정할 수 있는 다양한 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-121">Describes the different methods you can use the .NET Framework to target multiple client app types.</span></span>  
  
 [<span data-ttu-id="ef0b0-122">ASP.NET 웹 사이트 시작</span><span class="sxs-lookup"><span data-stu-id="ef0b0-122">Get Started with ASP.NET Web Sites</span></span>](http://www.asp.net/get-started/websites)  
 <span data-ttu-id="ef0b0-123">ASP.NET을 사용하여 웹앱을 개발할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0b0-123">Describes the ways you can develop web apps using ASP.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef0b0-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef0b0-124">See Also</span></span>  
 <span data-ttu-id="ef0b0-125">[이식 가능한 클래스 라이브러리](../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) </span><span class="sxs-lookup"><span data-stu-id="ef0b0-125">[Portable Class Library](../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) </span></span>  
 <span data-ttu-id="ef0b0-126">[개요](../../docs/framework/get-started/overview.md) </span><span class="sxs-lookup"><span data-stu-id="ef0b0-126">[Overview](../../docs/framework/get-started/overview.md) </span></span>  
 <span data-ttu-id="ef0b0-127">[개발 가이드](../../docs/framework/development-guide.md) </span><span class="sxs-lookup"><span data-stu-id="ef0b0-127">[Development Guide](../../docs/framework/development-guide.md) </span></span>  
 <span data-ttu-id="ef0b0-128">[방법: Windows 데스크톱 응용 프로그램 만들기](http://msdn.microsoft.com/library/47021403-eaca-4c34-946a-a26c42a64148) </span><span class="sxs-lookup"><span data-stu-id="ef0b0-128">[How to: Create a Windows Desktop Application](http://msdn.microsoft.com/library/47021403-eaca-4c34-946a-a26c42a64148) </span></span>  
 [<span data-ttu-id="ef0b0-129">Windows 서비스 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ef0b0-129">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)

