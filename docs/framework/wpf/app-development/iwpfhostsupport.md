---
title: IWpfHostSupport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a516d5917c2106bc83842befac9b506312fcce1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="15782-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="15782-102">IWpfHostSupport</span></span>
<span data-ttu-id="15782-103">응용 프로그램을 호스팅할 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] PresentationHost.exe 통해 콘텐츠를 호스트와 PresentationHost.exe 간의 통합 지점을 제공 하기 위해이 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15782-104">설명</span><span class="sxs-lookup"><span data-stu-id="15782-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="15782-105">웹 브라우저 같은 응용 프로그램에서 호스팅할 수 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] 콘텐츠를 포함 하 여 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 느슨한 XAML 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-105"> applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="15782-106">호스트에 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] 콘텐츠, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 응용 프로그램의 인스턴스를 만들는 [WebBrowser 컨트롤](http://go.microsoft.com/fwlink/?LinkId=97911)합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](http://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="15782-107">호스팅할 수 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] PresentationHost.exe 호스팅된 제공 하는의 인스턴스를 만들고 [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] 에 표시 하기 위해 호스트에 콘텐츠는 [WebBrowser 컨트롤](http://go.microsoft.com/fwlink/?LinkId=97911)합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](http://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="15782-108">통합 사용 하 여 `IWpfHostSupport` PresentationHost.exe를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
-   <span data-ttu-id="15782-109">검색 하 고 호스트 응용 프로그램은에 관심 있는 원시 입력된 장치 (휴먼 인터페이스 장치)에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
-   <span data-ttu-id="15782-110">호스트 응용 프로그램으로 원시 입력된 장치를 등록된 하 고 적절 한 메시지 전달에서 입력된 메시지를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
-   <span data-ttu-id="15782-111">사용자 지정 진행률과 오류 사용자 인터페이스에 대 한 호스트 응용 프로그램을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15782-112">이 API는 로컬 클라이언트 컴퓨터에서만 사용할 수 있도록 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="15782-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="15782-113">멤버</span><span class="sxs-lookup"><span data-stu-id="15782-113">Members</span></span>  
  
|<span data-ttu-id="15782-114">멤버</span><span class="sxs-lookup"><span data-stu-id="15782-114">Member</span></span>|<span data-ttu-id="15782-115">설명</span><span class="sxs-lookup"><span data-stu-id="15782-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15782-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="15782-116">GetRawInputDevices</span></span>](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|<span data-ttu-id="15782-117">PresentationHost.exe가 호스트 응용 프로그램과 관련된 원시 입력 장치(휴먼 인터페이스 장치)를 검색할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="15782-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="15782-118">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|<span data-ttu-id="15782-119">E_NOTIMPL이 반환되지 않는 한 메시지를 받을 때마다 PresentationHost.exe에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="15782-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="15782-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="15782-120">GetCustomUI</span></span>](../../../../docs/framework/wpf/app-development/getcustomui.md)|<span data-ttu-id="15782-121">기본적으로 PresentationHost.exe 자체 배포 진행률 및 배포 오류 사용자 인터페이스 제공 WPF 콘텐츠를 배포할 때 표시 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="15782-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
