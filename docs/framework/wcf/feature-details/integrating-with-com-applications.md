---
title: "COM 응용 프로그램과 통합"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 130a7cda170721f34a5b44f3361bd591d6375267
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-with-com-applications"></a>COM 응용 프로그램과 통합
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 직접 기존 코드에 통합할 수 있습니다. 서비스 모니커는 Office VBA, Visual Basic 6.0 또는 Visual C++ 6.0과 같은 다양한 범위의 COM 기반 개발 환경에서 사용할 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [COM 응용 프로그램과 통합 개요](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 통합 프로세스의 주요 부분에 대한 개요를 제공합니다.  
  
 [방법: 서비스 모니커 등록 및 구성](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 COM 응용 프로그램 내에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모니커를 사용하려면 필요한 특성을 사용하는 형식을 COM에 등록하고 필요한 바인딩 구성을 사용하여 COM 응용 프로그램과 모니커를 구성합니다.  
  
 [방법: 등록 없이 Windows Communication Foundation 서비스 모니커 사용](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 WSDL(웹 서비스 기술 언어) 문서의 형태로 또는 WS-MetadataExchange 끝점에서 계약 정의를 가져오는 방법에 대해 설명합니다.  
  
 [방법: WSDL 계약을 통해 서비스 모니커 사용](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 샘플을 호출하는 방법에 대해 설명합니다.  
  
 [방법: 메타데이터 교환 계약을 통해 서비스 모니커 사용](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Mex 끝점을 지정하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모니커를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 샘플을 호출하는 방법에 대해 설명합니다.  
  
 [방법: 채널 보안 자격 증명 지정](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모니커는 채널 자격 증명을 지정하는 다양한 대체 방법을 허용하는 `IChannelCredentials` 인터페이스를 지원합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>참고 항목  
 [COM+ 응용 프로그램과 통합](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
