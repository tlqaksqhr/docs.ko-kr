---
title: "방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# 방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기
이 항목에서는 신뢰할 수 있는 세션에 SSL\(Secure Sockets Layer\) 전송 보안을 사용하는 방법을 보여 줍니다.  HTTPS를 통해 신뢰할 수 있는 세션을 사용하려면 신뢰할 수 있는 세션 및 HTTPS 전송을 사용하는 사용자 지정 바인딩을 만들어야 합니다.  코드를 사용하여 명령적으로 또는 구성 파일에서 선언적으로 신뢰할 수 있는 세션을 사용할 수 있습니다.  이 절차에서는 클라이언트와 서비스 구성 파일을 사용하여 신뢰할 수 있는 세션 및 [\<httpsTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) 요소를 사용할 수 있습니다.  
  
 이 절차의 핵심 내용은 "reliableSessionOverHttps"라는 사용자 지정 바인딩 구성을 참조하는 `endpoint` 구성 요소에 `bindingConfiguration` 특성이 포함되어 있다는 것입니다.  그러면 [\<binding\>](../../../../docs/framework/misc/binding.md) 구성 요소에서 이 이름을 참조하여 신뢰할 수 있는 세션을 지정할 수 있으며, `reliableSession` 및 `httpsTransport` 요소를 포함하여 HTTPS 전송이 사용됩니다.  
  
 이 예제의 소스 복사에 대해서는 [HPPTS 기반의 사용자 지정 바인딩 신뢰할 수 있는 세션](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md)를 참조하세요.  
  
### CustomBinding으로 서비스를 구성하여 HTTPS로 신뢰할 수 있는 세션을 사용하려면  
  
1.  서비스 유형에 대한 서비스 계약을 정의합니다.  
  
     [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]  
  
2.  서비스 클래스에 서비스 계약을 구현합니다.  주소 또는 바인딩 정보는 서비스 구현 내에 지정되지 않습니다.  또한 구성 파일에서 해당 정보를 검색하기 위해 코드를 쓰지 않아도 됩니다.  
  
     [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]  
  
3.  Web.config 파일을 만들어 신뢰할 수 있는 세션 및 HTTPS 전송을 사용하는 "reliableSessionOverHttps"라는 사용자 지정 바인딩과 함께 `CalculatorService`에 대한 끝점을 구성합니다.  
  
     <!-- TODO: review snippet reference [!code[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]  -->  
  
4.  다음 줄을 포함하는 Service.svc 파일을 만듭니다.  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  IIS\(인터넷 정보 서비스\) 가상 디렉터리에 Service.svc 파일을 저장합니다.  
  
### CustomBinding으로 클라이언트를 구성하여 HTTPS로 신뢰할 수 있는 세션을 사용하려면  
  
1.  명령줄에서 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 서비스 메타데이터에서 코드를 생성합니다.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  생성된 클라이언트에는 클라이언트 구현에서 충족해야 하는 서비스 계약을 정의하는 `ICalculator` 인터페이스가 포함되어 있습니다.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]  
  
3.  또한 생성된 클라이언트 응용 프로그램에는 `ClientCalculator`의 구현이 포함되어 있습니다.  주소 및 바인딩 정보는 서비스 구현 내에 지정되지 않습니다.  또한 구성 파일에서 해당 정보를 검색하기 위해 코드를 쓰지 않아도 됩니다.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]  
  
4.  신뢰할 수 있는 세션 및 HTTPS 전송을 사용하는 "reliableSessionOverHttps"라는 사용자 지정 바인딩을 구성합니다.  
  
     <!-- TODO: review snippet reference [!code[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]  -->  
  
5.  응용 프로그램에서 `ClientCalculator`의 인스턴스를 만든 다음 서비스 작업을 호출합니다.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]  
  
6.  클라이언트를 컴파일하고 실행합니다.  
  
## 예제  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## .NET Framework 보안  
 이 샘플에 사용된 인증서는 Makecert.exe를 사용하여 만든 테스트 인증서이므로 브라우저에서 https:\/\/localhost\/servicemodelsamples\/service.svc와 같은 HTTPS 주소에 액세스할 때 보안 경고가 나타납니다.  
  
## 참고 항목  
 [신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)