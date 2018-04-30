---
title: COM+ 응용 프로그램과 통합 개요
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: e481e48f-7096-40eb-9f20-7f0098412941
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c723bda93feac3eef18f302ab0c8ec7c702eb7a
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="integrating-with-com-applications-overview"></a>COM+ 응용 프로그램과 통합 개요
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 분산 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다. COM+에서 호스트되는 구성 요소 기반 응용 프로그램 논리를 이미 사용 중이면 기존 논리를 다시 작성하지 않고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 기존 논리를 확장할 수 있습니다. 일반 시나리오는 웹 서비스를 통해 기존 COM+ 또는 엔터프라이즈 서비스 비즈니스 논리를 노출하려는 경우입니다.  
  
 COM+ 구성 요소의 인터페이스가 웹 서비스로 노출되는 경우 이러한 서비스의 사양과 계약은 응용 프로그램 초기화 시간에 수행되는 자동 매핑에 의해 결정됩니다. 다음 목록에서는 이 매핑의 개념적 모델을 보여 줍니다.  
  
-   노출된 각 COM 클래스에 대해 하나의 서비스가 정의됩니다.  
  
-   서비스 계약은 선택한 구성 요소의 인터페이스 정의에서 직접 파생되며 구성에서 정의된 메서드가 제외될 수 있습니다.  
  
-   해당 계약의 작업은 구성 요소 인터페이스 정의의 메서드에서 직접 파생됩니다.  
  
-   이러한 작업의 매개 변수는 구성 요소의 메서드 매개 변수에 해당하는 COM 상호 운용성 형식에서 직접 파생됩니다.  
  
 서비스의 기본 주소 및 전송 바인딩은 서비스 구성 파일에서 제공되지만 필요에 따라 다시 구성할 수 있습니다.  
  
> [!NOTE]
>  노출된 웹 서비스의 계약은 COM+ 인터페이스와 구성이 변경되지 않는 한 일정하게 유지됩니다. 여러 인터페이스를 수정하면 사용 가능한 서비스가 자동으로 업데이트되지 않으며 COM+ 서비스 모델 구성 요소 도구(ComSvcConfig.exe)를 다시 실행해야 합니다.  
  
 COM+ 응용 프로그램과 해당 구성 요소의 인증 및 권한 부여 요구 사항은 웹 서비스로 사용할 때 계속 적용됩니다.  
  
 호출자가 웹 서비스 트랜잭션을 시작하면 트랜잭션으로 표시된 구성 요소가 해당 트랜잭션 범위에 참여합니다.  
  
 다음 단계는 구성 요소를 수정하지 않고 COM+ 구성 요소의 인터페이스를 웹 서비스로 노출하는 데 필요합니다.  
  
1.  COM+ 구성 요소의 인터페이스를 웹 서비스로 노출할 수 있는지 여부를 결정합니다.  
  
2.  적절한 호스팅 모드를 선택합니다.  
  
3.  COM+ 서비스 모델 구성 도구(ComSvcConfig.exe)를 사용하여 인터페이스에 대한 웹 서비스를 추가합니다. ComSvcConfig.exe를 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: COM + 서비스 모델 구성 도구를 사용 하 여](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)합니다.  
  
4.  응용 프로그램 구성 파일에서 추가 서비스 설정을 구성합니다. 구성 요소를 구성 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: COM + 서비스 설정 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)합니다.  
  
## <a name="supported-interfaces"></a>지원되는 인터페이스  
 웹 서비스로 노출될 수 있는 인터페이스 형식에는 몇 가지 제한이 있습니다. 다음 인터페이스 형식은 지원되지 않습니다.  
  
-   개체 참조를 매개 변수로 전달하는 인터페이스 - 다음 제한된 개체 참조 방법에 대해서는 제한된 개체 참조 지원 단원에서 설명합니다.  
  
-   [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] COM 상호 운용성 변환과 호환되지 않는 형식을 전달하는 인터페이스  
  
-   COM+에서 호스트될 때 응용 프로그램 풀링을 사용하는 응용 프로그램의 인터페이스  
  
-   응용 프로그램에 개인으로 표시되는 구성 요소의 인터페이스  
  
-   COM+ 인프라 인터페이스  
  
-   시스템 응용 프로그램의 인터페이스  
  
-   전역 어셈블리 캐시에 추가되지 않은 엔터프라이즈 서비스 구성 요소의 인터페이스  
  
### <a name="limited-object-reference-support"></a>제한된 개체 참조 지원  
 배포된 많은 COM+ 구성 요소에서 ADO 레코드 집합 개체의 반환 등 개체를 참조 매개 변수로 사용하므로 COM+ 통합에는 개체 참조 매개 변수에 대한 제한된 지원이 포함됩니다. 지원은 `IPersistStream` COM 인터페이스를 구현하는 개체로 제한됩니다. 여기에는 ADO 레코드 집합 개체가 포함되며 응용 프로그램별 COM 개체에 대해 구현될 수 있습니다.  
  
 ComSvcConfig.exe 도구는에이 지원을 사용 하려면 다음을 제공 합니다.는 **allowreferences** 일반 메서드 서명 매개 변수를 사용 하지 않도록 설정 하 고 도구가 실행 된 개체 참조 매개 변수는 사용 되지 않도록 되 고 확인 하는 스위치 . 또한 <`persistableTypes`> 요소의 자식인 <`comContract`> 구성 요소 내에서 매개 변수로 전달할 개체 형식에 이름을 지정하고 식별해야 합니다.  
  
 이 기능을 사용하는 경우 COM+ 통합 서비스는 `IPersistStream` 인터페이스를 사용하여 개체 인스턴스를 serialize 또는 deserialize합니다. 개체 인스턴스가 `IPersistStream`을 지원하지 않으면 예외가 throw됩니다.  
  
 클라이언트 응용 프로그램 내에서 <xref:System.ServiceModel.ComIntegration.PersistStreamTypeWrapper> 개체의 메서드를 사용하여 개체를 서비스로 전달하고 유사하게 개체를 검색할 수 있습니다.  
  
> [!NOTE]
>  serialization 방법의 사용자 지정 및 플랫폼별 특성 때문에 이 방법은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 간에 사용하기에 가장 적합합니다.  
  
## <a name="selecting-the-hosting-mode"></a>호스팅 모드 선택  
 COM+는 다음 호스팅 모드 중 하나로 웹 서비스를 노출합니다.  
  
-   COM+ 호스팅  
  
     웹 서비스는 응용 프로그램의 전용 COM+ 서버 프로세스(Dllhost.exe) 내에 호스트됩니다. 이 모드에서는 응용 프로그램을 명시적으로 시작해야 웹 서비스 요청을 받을 수 있습니다. COM+ 옵션 "NT 서비스로 실행" 또는 "유휴 상태일 때도 실행"을 사용하여 응용 프로그램과 해당 서비스에 대해 일정 시간 동안 유휴 상태이면 종료를 방지할 수 있습니다. 이 모드에서는 웹 서비스와 DCOM이 모두 서버 응용 프로그램에 액세스할 수 있습니다.  
  
-   웹 호스팅  
  
     웹 서비스는 웹 서버 작업자 프로세스 내에 호스트됩니다. 이 모드에서는 초기 요청을 받을 때 COM+가 활성 상태가 아니어도 됩니다. 이 요청을 받을 때 응용 프로그램이 활성 상태가 아니면 요청을 처리하기 전에 자동으로 활성화됩니다. 이 모드에서는 웹 서비스와 DCOM이 모두 서버 응용 프로그램에 액세스할 수 있지만 웹 서비스 요청에 대해 프로세스 홉이 발생합니다. 이 경우 일반적으로 클라이언트가 가장을 사용해야 합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 제네릭 <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> 클래스의 속성과 <xref:System.ServiceModel.Security.WindowsClientCredential> 열거형 값으로 액세스되는 <xref:System.ServiceModel.ChannelFactory%601> 클래스의 <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> 속성을 사용하여 이 작업을 수행할 수 있습니다.  
  
-   웹 호스팅 In-Process  
  
     웹 서비스와 COM+ 응용 프로그램 논리는 웹 서버 작업자 프로세스 내에 호스트됩니다. 이 경우 웹 서비스 요청에 대한 프로세스 홉이 발생하지 않고 웹 호스팅 모드가 자동으로 활성화됩니다. DCOM을 통해 서버 응용 프로그램에 액세스할 수 없다는 단점이 있습니다.  
  
### <a name="security-considerations"></a>보안 고려 사항  
 다른 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 마찬가지로 노출된 서비스의 보안 설정은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 채널의 구성 설정을 통해 관리됩니다. 시스템 수준의 DCOM 사용 권한 설정 같은 일반적인 DCOM 보안 설정은 적용되지 않습니다. COM+ 응용 프로그램 역할을 적용하려면 해당 구성 요소에 대해 "구성 요소 수준 액세스 검사" 권한 부여를 사용해야 합니다.  
  
 보안되지 않은 바인딩을 사용하면 통신 중에 조작되거나 정보가 공개될 수 있습니다. 이를 방지하려면 보안 바인딩을 사용하는 것이 좋습니다.  
  
 COM+ 호스팅 및 웹 호스팅 모드의 경우 클라이언트 응용 프로그램에서 서버 프로세스가 클라이언트 사용자를 가장할 수 있도록 허용해야 합니다. 가장 수준을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]으로 설정하여 <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> 클라이언트에서 이 작업을 수행할 수 있습니다.  
  
 IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service)에서 HTTP 전송을 사용하는 경우 Httpcfg.exe 도구를 사용하여 전송 끝점 주소를 예약할 수 있습니다. 다른 구성에서는 필요한 서비스로 작동하는 Rogue 서비스로부터 보호하는 것이 중요합니다. Rogue 서비스가 원하는 끝점에서 시작되지 않도록 하려면 올바른 서비스가 NT 서비스로 실행되도록 구성할 수 있습니다. 이렇게 하면 올바른 서비스가 Rogue 서비스 전에 끝점 주소를 클레임할 수 있습니다.  
  
 웹 호스팅 서비스로 구성 된 COM + 역할 COM + 응용 프로그램을 노출 하는 경우 응용 프로그램의 역할 중 하나에 IIS 프로세스 계정 시작 ""를 추가 해야 합니다. 개체를 사용한 후 완전히 종료할 수 있으려면 일반적으로 이름이 IWAM_machinename인 이 계정을 추가해야 합니다. 계정에 추가 사용 권한을 부여하면 안 됩니다.  
  
 통합 응용 프로그램에서는 COM+ 프로세스 재활용 기능을 사용할 수 없습니다. 프로세스 재활용을 사용하도록 응용 프로그램이 구성되고 구성 요소가 COM+ 호스팅 프로세스로 실행되는 경우 서비스가 시작되지 않습니다. 웹 호스팅 In-Process 모드를 사용하는 서비스는 프로세스 재활용 설정이 적용되지 않으므로 이 요구 사항에 포함되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 응용 프로그램과 통합 개요](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)
