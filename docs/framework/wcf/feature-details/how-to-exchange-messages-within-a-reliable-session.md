---
title: "방법: 신뢰할 수 있는 세션 내에서 메시지 교환 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# 방법: 신뢰할 수 있는 세션 내에서 메시지 교환
이 항목에서는 기본적이지는 않지만 신뢰할 수 있는 세션을 지원하는 시스템 제공 바인딩 중 하나를 사용하여 이러한 세션을 사용하도록 설정하는 데 필요한 단계에 대해 간략하게 설명합니다.신뢰할 수 있는 세션은 코드를 사용하여 명령적으로 사용되거나 구성 파일에서 선언적으로 사용될 수 있습니다.이 절차에서는 클라이언트 및 서비스 구성 파일을 사용하여 신뢰할 수 있는 세션을 사용하도록 설정하고 메시지를 보낸 순서대로 동일하게 메시지를 받도록 규정할 수 있습니다.  
  
 이 절차의 핵심 내용은 끝점 구성 요소에 "Binding1"이라는 바인딩 구성을 참조하는 `bindingConfiguration` 특성이 포함되어 있다는 것입니다. [\<binding\>](../../../../docs/framework/misc/binding.md) 구성 요소는 [reliableSession](http://msdn.microsoft.com/ko-kr/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) 요소의 `enabled` 특성을 `true`로 설정하여 신뢰할 수 있는 세션을 사용하도록 이 이름을 참조할 수 있습니다.`ordered` 특성을 `true`로 설정하여 신뢰할 수 있는 세션에 대해 순서가 지정된 배달 보증을 지정합니다.  
  
 이 예제의 소스 복사에 대해서는 [WS 신뢰할 수 있는 세션](../../../../docs/framework/wcf/samples/ws-reliable-session.md)을 참조하십시오.  
  
### 신뢰할 수 있는 세션을 사용하도록 WSHttpBinding으로 서비스를 구성하려면  
  
1.  서비스 유형에 대한 서비스 계약을 정의합니다.  
  
     [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]  
  
2.  서비스 클래스에 서비스 계약을 구현합니다.주소 또는 바인딩 정보는 서비스 구현 내에 지정되지 않습니다.또한 구성 파일에서 해당 정보를 검색하기 위해 코드를 쓰지 않아도 됩니다.  
  
     [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]  
  
3.  Web.config 파일을 만들어 신뢰할 수 있는 세션이 활성화되어 있고 필요한 메시지 배달 순서가 지정된 상태에서 <xref:System.ServiceModel.WSHttpBinding>을 사용하는 `CalculatorService`의 끝점을 구성합니다.  
  
     <!-- TODO: review snippet reference [!code[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]  -->  
  
4.  다음 줄을 포함하는 Service.svc 파일을 만듭니다.  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  IIS\(인터넷 정보 서비스\) 가상 디렉터리에 Service.svc 파일을 저장합니다.  
  
### 신뢰할 수 있는 세션을 사용하도록 WSHttpBinding으로 클라이언트를 구성하려면  
  
1.  명령줄에서 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스 메타데이터에서 코드를 생성합니다.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  생성된 클라이언트에는 클라이언트 구현에서 충족해야 하는 서비스 계약을 정의하는 `ICalculator` 인터페이스가 포함되어 있습니다.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]  
  
3.  또한 생성된 클라이언트 응용 프로그램에는 `ClientCalculator`의 구현이 포함되어 있습니다.주소 및 바인딩 정보는 서비스 구현 내에 지정되지 않습니다.또한 구성 파일에서 해당 정보를 검색하기 위해 코드를 쓰지 않아도 됩니다.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]  
  
4.  또한 Svcutil.exe는 <xref:System.ServiceModel.WSHttpBinding> 클래스를 사용하는 클라이언트의 구성도 생성합니다.이 파일은 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]를 사용하는 경우 이름을 App.config로 지정해야 합니다.  
  
     <!-- TODO: review snippet reference [!code[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]  -->  
  
5.  응용 프로그램에서 `ClientCalculator`의 인스턴스를 만든 다음 서비스 작업을 호출합니다.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]  
  
6.  클라이언트를 컴파일하고 실행합니다.  
  
## 예제  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
 기본적으로 여러 시스템 제공 바인딩은 신뢰할 수 있는 세션을 지원합니다.이러한 세션은 다음과 같습니다.  
  
-   <xref:System.ServiceModel.WSDualHttpBinding>  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>  
  
 신뢰할 수 있는 세션을 지원하는 사용자 지정 바인딩을 만드는 방법에 대한 예제는 [방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)를 참조하십시오.  
  
## 참고 항목  
 [신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)