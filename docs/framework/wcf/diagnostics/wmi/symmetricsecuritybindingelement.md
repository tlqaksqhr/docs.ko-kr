---
title: SymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7960ae9972490f2363b0f6f9942e947677c7d299
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="symmetricsecuritybindingelement"></a>SymmetricSecurityBindingElement
SymmetricSecurityBindingElement  
  
## <a name="syntax"></a>구문  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>메서드  
 SymmetricSecurityBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 SymmetricSecurityBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 바인딩의 메시지 암호화 및 서명 순서입니다.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 바인딩에 서명 확인이 필요한지 여부입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
