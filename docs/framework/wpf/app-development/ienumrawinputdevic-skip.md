---
title: IEnumRAWINPUTDEVIC:Skip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e232d2525f9dfa339516f766d417ea9c3ee976c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicskip"></a>IEnumRAWINPUTDEVIC:Skip
열거자를 다음 건너뛰려면 지시 `celt` 열거형의 요소를 다음에 호출할 수 있도록 [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) 이러한 요소를 반환 하지 것입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
  
 [in] 건너뛸 요소 수입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 HRESULT: 제공된 요소 수가 `celt`이면 S_OK이고, 그러지 않으면 S_FALSE입니다.
