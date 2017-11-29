---
title: GetRawInputDevices
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e936b4ef2cab65e72ca9edbc3b95281815938983
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getrawinputdevices"></a><span data-ttu-id="58fcc-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="58fcc-102">GetRawInputDevices</span></span>
<span data-ttu-id="58fcc-103">PresentationHost.exe가 호스트 응용 프로그램과 관련된 원시 입력 장치(휴먼 인터페이스 장치)를 검색할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="58fcc-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58fcc-104">구문</span><span class="sxs-lookup"><span data-stu-id="58fcc-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58fcc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58fcc-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="58fcc-106">[out] 에 대 한 포인터는 [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) 원시 입력된 장치를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="58fcc-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="58fcc-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="58fcc-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="58fcc-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="58fcc-108">HRESULT:</span></span>  
  
 <span data-ttu-id="58fcc-109">S_OK- [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) 만 사용해 PresentationHost.exe S_OK가 반환 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="58fcc-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="58fcc-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="58fcc-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58fcc-111">설명</span><span class="sxs-lookup"><span data-stu-id="58fcc-111">Remarks</span></span>  
 <span data-ttu-id="58fcc-112">원시 입력 장치는 키보드, 마우스 및 리모콘과 같은 덜 일반적인 장치를 포함하는 입력 장치 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="58fcc-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="58fcc-113">원시 입력 장치 목록이 검색된 후 PresentationHost.exe는 WM_INPUT 알림 메시지를 받을 장치를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="58fcc-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58fcc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58fcc-114">See Also</span></span>  
 [<span data-ttu-id="58fcc-115">http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp</span><span class="sxs-lookup"><span data-stu-id="58fcc-115">http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)  
 [<span data-ttu-id="58fcc-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="58fcc-116">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
