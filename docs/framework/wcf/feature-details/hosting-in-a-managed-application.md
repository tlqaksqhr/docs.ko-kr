---
title: "관리되는 응용 프로그램에서의 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 30d531d436937bf5183ac0c28d59425ea71762e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="hosting-in-a-managed-application"></a>관리되는 응용 프로그램에서의 호스팅
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램에서 호스팅할 수 있습니다. 자체 호스팅 서비스는 배포하는 데 최소한의 인프라를 필요로 하기 때문에 가장 유연한 호스팅 옵션입니다. 그러나 관리되는 응용 프로그램이 IIS(인터넷 정보 서비스) 및 Windows 서비스와 같은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 다른 호스팅 옵션에 대한 고급 호스팅 및 관리 기능을 제공하지 않기 때문에 가장 약한 호스팅 옵션이기도 합니다.  
  
 자체 호스팅 서비스를 만들려면 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만들고 열어, 여기서 서비스의 메시지 수신 대기를 시작합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][하는 방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)합니다.  
  
 계약을 정의 계약을 구현 및 관리 되는 응용 프로그램 내에 서비스를 호스트 하는 방법에는 전체 예제에 대 한 참조는 [초보자를 위한 자습서](../../../../docs/framework/wcf/getting-started-tutorial.md) 및 [자체 호스트](../../../../docs/framework/wcf/samples/self-host.md)합니다.  
  
 다음 단원에서는 이 호스팅 옵션을 사용하는 일반적인 시나리오에 대해 설명합니다.  
  
## <a name="console-applications"></a>콘솔 응용 프로그램  
 자체 호스팅을 사용하는 일반적인 시나리오는 콘솔 응용 프로그램 내에서 실행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다. 일반적으로 콘솔 응용 프로그램 내에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스팅하면 서비스의 개발 단계에서 유용합니다. 이 경우 쉽게 디버깅을 수행할 수 있으며, 응용 프로그램 내에서 발생하는 상황을 확인하기 위한 추적 정보를 손쉽게 얻을 수 있으며, 새 위치에 서비스를 복사하여 이동하기 용이합니다.  
  
## <a name="rich-client-applications"></a>리치 클라이언트 응용 프로그램  
 자체 호스팅을 사용하는 다른 일반적인 시나리오는 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] 또는 Windows Forms(WinForms)에 기반한 응용 프로그램과 같은 리치 클라이언트 응용 프로그램입니다. 이 호스팅 옵션을 사용하면 리치 클라이언트 응용 프로그램(예: [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 및 WinForms 응용 프로그램)에서 외부와 쉽게 통신할 수 있습니다. 예를 들면 사용자 인터페이스에 대해 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 를 사용하고 또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스팅하여 다른 클라이언트에서 해당 서비스에 연결하여 정보를 공유할 수 있도록 하는 피어 투 피어 공동 작업 클라이언트가 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스 호스팅](../../../../docs/framework/wcf/hosting-services.md)  
 [초보자를 위한 자습서](../../../../docs/framework/wcf/getting-started-tutorial.md)
