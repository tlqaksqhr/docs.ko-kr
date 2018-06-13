---
title: WCF 보안의 암호화 유연성
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 40f4f8523d5286911216180846e94ec18e40da1c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33810215"
---
# <a name="cryptographic-agility-in-wcf-security"></a>WCF 보안의 암호화 유연성
이 샘플에서는 Windows Communication Foundation (WCF) 클라이언트와 서비스에서 암호화 agile 구현을 제공 하는 표준/사용자 지정 알고리즘에서 지정 하는 방법을 보여 줍니다. 이 샘플은 다음 프로젝트로 구성되어 있습니다.  
  
 서비스  
 이것은 구현 하는 자체 호스팅된 WCF 서비스는 `ICalculator` 인터페이스를 사용 하 여 끝점 보호 하는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 보안 세션 및 신뢰할 수 있는 세션을 사용 하지 않도록 설정 합니다. 이 서비스는 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.  
  
 클라이언트  
 인증을 거친 후 서비스에 액세스 하는 WCFclient입니다. 이 클라이언트는 `ICalculator` 인터페이스에 의해 노출되고 서비스에 의해 구현된 작업을 호출합니다. 또한 클라이언트는 동일한 사용자 지정 `SecurityAlgorithmSuite` 클래스를 정의하여 메시지 보안에 사용할 암호화 알고리즘을 지정합니다.  
  
### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 CryptoAgility.sln 솔루션을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  열기 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] \WCF\Basic\Security\CryptoAgility\Service\bin 디렉터리로 이동 하 고 service.exe를 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 관리자 권한으로 service.exe 파일을 실행 하 고 **관리자 권한으로 실행**합니다.  
  
4.  \WCF\Basic\Security\CryptoAgility\Client\bin 디렉터리로 이동하고 client.exe 파일을 정상적으로 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a>참고 항목  
 [보안](../../../../docs/framework/wcf/feature-details/security.md)
