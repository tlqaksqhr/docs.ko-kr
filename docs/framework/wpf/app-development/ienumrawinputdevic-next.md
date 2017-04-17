---
title: "IEnumRAWINPUTDEVIC:Next | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Next 메서드"
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# IEnumRAWINPUTDEVIC:Next
열거자 목록의 다음 `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) 구조체를 열거하고 `pceltFetched`의 실제 열거된 요소 수와 함께 `rgelt`에 반환합니다.  
  
## 구문  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### 매개 변수  
 `celt`  
  
 \[in\] `rgelt`에 반환된 [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) 구조체 수입니다.  
  
 `rgelt`  
  
 \[out\] 열거된 RAWINPUTDEVICE 구조체를 수신할 celt 크기\(또는 더 큰\)의 배열입니다.  
  
 `pceltFetched`  
  
 \[out\] `rgelt`에 실제로 제공된 요소 수에 대한 포인터입니다.  `rgelt`가 1이면 호출자가 `NULL`을 전달할 수 있습니다.  
  
## 속성 값\/반환 값  
 HRESULT: 제공된 요소 수가 `celt`이면 S\_OK이고, 그러지 않으면 S\_FALSE입니다.