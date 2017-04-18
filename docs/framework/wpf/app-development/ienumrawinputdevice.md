---
title: "IEnumRAWINPUTDEVICE | Microsoft Docs"
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
  - "IEnumRAWINPUTDEVICE 인터페이스"
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# IEnumRAWINPUTDEVICE
이 인터페이스는 원시 입력 장치를 열거하며 PresentationHost.exe에서만 사용됩니다.  
  
> [!NOTE]
>  이 API는 로컬 클라이언트 컴퓨터에서만 사용할 수 있도록 지원됩니다.  
  
## 멤버  
  
|멤버|설명|  
|--------|--------|  
|[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|열거자 목록에서 다음 `celt` 요소\(즉, RAWINPUTDEVICE 구조체\)를 열거하고 `pceltFetched`의 실제 열거된 요소 수와 함께 `rgelt`에 반환합니다.|  
|[IEnumRAWINPUTDEVIC:Skip](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|다음에 [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)을 호출할 때 이러한 요소가 반환되지 않도록 열거형의 다음 `celt` 요소를 건너뛰도록 열거자에 지시합니다.|  
|[IEnumRAWINPUTDEVIC:Reset](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|열거형 시퀀스를 시작 부분으로 다시 설정합니다.|  
|[IEnumRAWINPUTDEVIC:Clone](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|현재 열거자와 동일한 상태인 다른 원시 입력 장치 열거자를 만들어 동일한 목록을 반복합니다.|  
  
## 참고 항목  
 [원시 입력 정보](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)