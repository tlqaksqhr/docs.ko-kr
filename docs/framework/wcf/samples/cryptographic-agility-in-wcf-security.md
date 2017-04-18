---
title: "WCF 보안의 암호화 유연성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# WCF 보안의 암호화 유연성
이 샘플에서는 표준\/사용자 지정 알고리즘을 통해 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트 및 서비스에서 암호화 agile 구현을 제공하도록 지정하는 방법을 보여 줍니다.  이 샘플은 다음 프로젝트로 구성되어 있습니다.  
  
 서비스  
 `ICalculator` 인터페이스를 구현하고 보안 세션 및 신뢰할 수 있는 세션을 사용하지 않도록 설정된 <xref:System.ServiceModel.WsHttpBinding>을 사용하여 끝점을 보안하는 자체 호스팅 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.  이 서비스는 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.  
  
 클라이언트  
 인증에 성공한 후 서비스에 액세스하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트입니다.  이 클라이언트는 `ICalculator` 인터페이스에 의해 노출되고 서비스에 의해 구현된 작업을 호출합니다.  또한 클라이언트는 동일한 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.  
  
### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 CryptoAgility.sln 솔루션을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 열고 \\WCF\\Basic\\Security\\CryptoAgility\\Service\\bin 디렉터리로 이동한 다음 service.exe를 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 선택하여 service.exe 파일을 관리자 권한으로 실행합니다.  
  
4.  \\WCF\\Basic\\Security\\CryptoAgility\\Client\\bin 디렉터리로 이동하고 client.exe 파일을 정상적으로 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.  계속하기 전에 다음\(기본\) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [.NET Framework 4용 WCF\(Windows Communication Foundation\) 및 Windows WF\(Workflow Foundation\) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780)\(영문\)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.  이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## 참고 항목  
 [보안](../../../../docs/framework/wcf/feature-details/security.md)