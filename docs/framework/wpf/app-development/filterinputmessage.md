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
ms.workload: dotnet
ms.openlocfilehash: 7e76f9863b68d5c7c34bca8adc872210527d6c17
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="filterinputmessage"></a>FilterInputMessage
E_NOTIMPL이 반환되지 않는 한 메시지를 받을 때마다 PresentationHost.exe에서 호출됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pMsg`  
  
 [in] 원시 입력을 가져오는 창으로 전송되는 WM_INPUT 메시지입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 HRESULT:  
  
 S_OK - 필터가 메시지를 처리하지 않았으며 추가 처리가 발생할 수 있습니다.  
  
 S_FALSE - 필터가 이 메시지를 처리했으며 추가 처리가 발생하면 안 됩니다.  
  
 이 값이 반환 하는 경우 E_NOTIMPL – [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) 다시 호출 되지 않습니다. 이 값은 사용자 지정 진행률 및 오류 사용자 인터페이스를 PresentationHost.exe에 제공하는 것에만 관심이 있고 PresentationHost.exe에서 원시 입력 메시지를 전달받지 않으려는 호스트 응용 프로그램에서 반환될 수 있습니다.  
  
## <a name="remarks"></a>설명  
 PresentationHost.exe는 키보드, 마우스 및 리모컨을 비롯한 다양한 원시 입력 장치의 대상입니다. 호스트 응용 프로그램의 동작이 그러지 않은 경우 PresentationHost.exe에서 사용되는 입력에 따라 달라지는 경우도 있습니다. 예를 들어 호스트 응용 프로그램은 특정 입력 메시지를 수신하여 특정 사용자 인터페이스 요소를 표시할지 여부를 확인할 수 있습니다.  
  
 호스트 응용 프로그램이 이러한 동작을 제공 하기 위해 필요한 입력된 메시지를 받을 수 있도록 PresentationHost.exe 적절 한 원시 입력된 메시지를 전달 하는 호스팅된 응용 프로그램 호출 하 여 [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)합니다.  
  
 호스팅된 응용 프로그램에서 반환 된 원시 입력된 장치 (휴먼 인터페이스 장치)의 집합을 등록 하 여 원시 입력된 메시지를 받는 [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WM_INPUT 알림](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
