---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ffca9a587bdb32afc252f9719eb35e3139dd3f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a>System.ServiceModel.Channels.PeerNodeAuthenticationFailure
잠재적인 환경이 있는 보안 핸드셰이크가 성공하지 못했습니다.  
  
## <a name="description"></a>설명  
 이 추적은 보안 환경 연결을 설정하는 동안 발생합니다. 이는 자격 증명이 충분하지 않거나 올바르지 않기 때문일 수 있습니다.  
  
 PeerChannel은 강력한 ID인 X.509 인증서에 대한 단일 토큰 형식을 인식합니다. 이는 구현 가능한 인증 및 권한 부여의 형식을 기반으로 강력한 ID 모델을 제공합니다. PeerChannel은 암호를 사용하여 간단한 응용 프로그램에 대한 지원도 제공합니다. 암호는 세션 입장을 허용하는 용도로만 사용할 수 있으며, 메시지 인증에는 사용할 수 없습니다. 이는 피어 그룹이 공유하는 대칭 토큰을 소스 인증에 사용하기에는 어렵고 적절하지 않기 때문입니다.  
  
## <a name="troubleshooting"></a>문제 해결  
 모든 환경에 적합한 보안 자격 증명이 있는지 확인하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [피어 채널 보안](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
