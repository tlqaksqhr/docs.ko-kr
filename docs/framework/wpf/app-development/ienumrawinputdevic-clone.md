---
title: "IEnumRAWINPUTDEVIC:Clone | Microsoft Docs"
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
  - "Clone 메서드"
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# IEnumRAWINPUTDEVIC:Clone
현재 열거자와 같은 상태의 다른 원시 입력 장치 열거자를 만들어 같은 목록에서 반복되게 만듭니다.  
  
## 구문  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### 매개 변수  
 `ppenum`  
  
 \[out\] [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) 인터페이스 포인터를 받는 출력 변수의 주소입니다.  메서드가 성공하지 못하는 경우 이 출력 변수의 값이 정의되지 않습니다.  
  
## 속성 값\/반환 값  
 HRESULT: 이 메서드는 표준 반환 값 E\_INVALIDARG, E\_OUTOFMEMORY 및 E\_UNEXPECTED를 지원합니다.  
  
## 설명  
 이 메서드를 사용하면 열거 시퀀스의 한 지점을 기록하여 나중에 해당 지점으로 돌아갈 수 있습니다.  호출자는 첫 번째 열거자와 별도로 이 새 열거자를 해제해야 합니다.