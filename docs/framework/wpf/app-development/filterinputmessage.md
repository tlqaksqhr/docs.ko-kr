---
title: FilterInputMessage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b3a0e58c7485d46f004db7ea52215be60340b68
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="filterinputmessage"></a><span data-ttu-id="3adcd-102">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="3adcd-102">FilterInputMessage</span></span>
<span data-ttu-id="3adcd-103">E_NOTIMPL이 반환되지 않는 한 메시지를 받을 때마다 PresentationHost.exe에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-103">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3adcd-104">구문</span><span class="sxs-lookup"><span data-stu-id="3adcd-104">Syntax</span></span>  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3adcd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3adcd-105">Parameters</span></span>  
 `pMsg`  
  
 <span data-ttu-id="3adcd-106">[in] 원시 입력을 가져오는 창으로 전송되는 WM_INPUT 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-106">[in] The WM_INPUT message sent to the window that is getting raw input.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3adcd-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="3adcd-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="3adcd-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="3adcd-108">HRESULT:</span></span>  
  
 <span data-ttu-id="3adcd-109">S_OK - 필터가 메시지를 처리하지 않았으며 추가 처리가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-109">S_OK - The filter did not process the message and further processing may occur.</span></span>  
  
 <span data-ttu-id="3adcd-110">S_FALSE - 필터가 이 메시지를 처리했으며 추가 처리가 발생하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-110">S_FALSE - The filter processed this message and no further processing should occur.</span></span>  
  
 <span data-ttu-id="3adcd-111">이 값이 반환 하는 경우 E_NOTIMPL – [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) 다시 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-111">E_NOTIMPL – If this value is returned, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) is not called again.</span></span> <span data-ttu-id="3adcd-112">이 값은 사용자 지정 진행률 및 오류 사용자 인터페이스를 PresentationHost.exe에 제공하는 것에만 관심이 있고 PresentationHost.exe에서 원시 입력 메시지를 전달받지 않으려는 호스트 응용 프로그램에서 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-112">This might be returned from a host application that is only interested in providing custom progress and error user interfaces to PresentationHost.exe is not interested in being forwarded raw input messages from PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3adcd-113">설명</span><span class="sxs-lookup"><span data-stu-id="3adcd-113">Remarks</span></span>  
 <span data-ttu-id="3adcd-114">PresentationHost.exe는 키보드, 마우스 및 리모컨을 비롯한 다양한 원시 입력 장치의 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-114">PresentationHost.exe is the target of various raw input devices, including keyboard, mice, and remote controls.</span></span> <span data-ttu-id="3adcd-115">호스트 응용 프로그램의 동작이 그러지 않은 경우 PresentationHost.exe에서 사용되는 입력에 따라 달라지는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-115">Sometimes, behavior in the host application is dependent on input that would otherwise be consumed by PresentationHost.exe.</span></span> <span data-ttu-id="3adcd-116">예를 들어 호스트 응용 프로그램은 특정 입력 메시지를 수신하여 특정 사용자 인터페이스 요소를 표시할지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-116">For example, a host application may depend on receiving certain input messages to determine whether or not to display specific user interface elements.</span></span>  
  
 <span data-ttu-id="3adcd-117">호스트 응용 프로그램이 이러한 동작을 제공 하기 위해 필요한 입력된 메시지를 받을 수 있도록 PresentationHost.exe 적절 한 원시 입력된 메시지를 전달 하는 호스팅된 응용 프로그램 호출 하 여 [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-117">To allow the host application to receive the necessary input messages to provide these behaviors, PresentationHost.exe forwards appropriate raw input messages to the hosted application by calling [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span></span>  
  
 <span data-ttu-id="3adcd-118">호스팅된 응용 프로그램에서 반환 된 원시 입력된 장치 (휴먼 인터페이스 장치)의 집합을 등록 하 여 원시 입력된 메시지를 받는 [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3adcd-118">The hosted application receives raw input messages by registering with the set of raw input devices (Human Interface Devices) returned by [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3adcd-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3adcd-119">See Also</span></span>  
 [<span data-ttu-id="3adcd-120">WM_INPUT 알림</span><span class="sxs-lookup"><span data-stu-id="3adcd-120">WM_INPUT Notification</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
