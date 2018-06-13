---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: a4ae5153525d5468955a09d19e534c00114c6530
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485120"
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>구문  
  
```  
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## <a name="methods"></a>메서드  
 PrivacyNoticeBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 PrivacyNoticeBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="privacynoticeversion"></a>PrivacyNoticeVersion  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 개인 정보 알림 버전입니다.  
  
### <a name="url"></a>URL  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 개인 정보 알림이 있는 URL입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
