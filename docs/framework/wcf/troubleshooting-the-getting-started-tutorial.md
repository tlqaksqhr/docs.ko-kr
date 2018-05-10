---
title: 초보자를 위한 자습서 문제 해결
ms.date: 03/30/2017
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
ms.openlocfilehash: 12812bd1ef88eab14a8defed0b71657b0d33c618
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>초보자를 위한 자습서 문제 해결
이 항목에서는 초보자를 위한 자습서를 수행할 때 발생하는 가장 일반적인 문제 및 해결 방법을 보여 줍니다.  
  
1.  [하드 드라이브에서 프로젝트 파일을 찾을 수 없는 경우](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [서비스 응용 프로그램을 실행 하는: HTTP URL을 등록 하지 못했습니다 http://+:8000/ServiceModelSamples/Service/합니다. 사용자의 프로세스에 이 네임스페이스에 액세스할 수 있는 권한이 없습니다.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [Svcutil.exe 도구를 사용 하려고: 'svcutil'는 내부 또는 외부 명령, 실행할 수 있는 프로그램 또는 배치 파일으로 인식 되지 않습니다.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [Svcutil.exe에서 생성 한 App.config 파일을 찾을 수 없습니다.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [클라이언트 응용 프로그램의 컴파일: 'CalculatorClient'에 대 한 정의 포함 하지 않는 '&lt;메서드 이름&gt;'및 확장 메서드'&lt;메서드 이름&gt;' 'CalculatorClient' 형식의 첫 번째 인수를 수락 합니다. 찾을 수 없습니다 (사용 하는 누락 된 지시문 또는 어셈블리 참조가?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [클라이언트 응용 프로그램의 컴파일: 형식 또는 네임 스페이스 이름 'CalculatorClient'를 찾을 수 없습니다 (사용 하는 누락 된 지시문 또는 어셈블리 참조가?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [클라이언트를 실행: 처리 되지 않은 예외: System.ServiceModel.EndpointNotFoundException:에 연결 하지 못했습니다 http://localhost:8000/ServiceModelSamples/Service/CalculatorService합니다. TCP 오류 코드 10061: 대상 컴퓨터 거부 했으므로 없습니다 연결을 설정할 수 없습니다.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## <a name="i-am-unable-to-find-the-project-files-on-my-hard-drive"></a>하드 드라이브에서 프로젝트 파일을 찾을 수 없습니다.  
 C:\users에서 프로젝트 파일을 저장 하는 visual Studio\\< 사용자 name\Documents\\< Visual Studio 버전\>에 \Projects [!INCLUDE[wv](../../../includes/wv-md.md)] 및 [!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)], 및 c:\Documents and Settings\\< 사용자 이름 \>\My documents\\< Visual Studio 버전\>이전 버전의 Windows에서 \Projects 합니다.  
  
<a name="BKMK_q2"></a>   
## <a name="attempting-to-run-the-service-application-http-could-not-register-url-http8000servicemodelsamplesservice-your-process-does-not-have-access-rights-to-this-namespace"></a>서비스 응용 프로그램을 실행 하는: HTTP URL을 등록 하지 못했습니다 http://+:8000/ServiceModelSamples/Service/합니다. 사용자의 프로세스에 이 네임스페이스에 액세스할 수 있는 권한이 없습니다.  
 WCF 서비스를 호스팅하는 프로세스를 관리자 권한으로 실행 되어야 합니다. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 내에서 서비스를 실행 중인 경우에는 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]을 관리자로 실행해야 합니다. 이렇게 하려면 **시작**를 마우스 오른쪽 단추로 클릭 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 선택 **관리자 권한으로 실행**합니다. 명령줄 프롬프트에서 서비스를 실행 중인 경우에는 동일한 방식으로 명령줄 프롬프트를 관리자로 시작해야 합니다. 클릭 **시작**를 마우스 오른쪽 단추로 클릭 **명령 프롬프트** 선택 **관리자 권한으로 실행**합니다.  
  
<a name="BKMK_q3"></a>   
## <a name="attempting-to-use-the-svcutilexe-tool-svcutil-is-not-recognized-as-an-internal-or-external-command-operable-program-or-batch-file"></a>Svcutil.exe 도구를 사용하려고 할 때 다음 오류가 발생합니다. 'svcutil'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는 배치 파일이 아닙니다.  
 Svcutil.exe는 시스템 경로에 있어야 합니다. 가장 간단한 해결책은 명령 프롬프트를 사용하는 것입니다. 클릭 **시작**선택, **모든 프로그램**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **Visual Studio Tools**, 및 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] **명령 프롬프트**합니다. 이 명령 프롬프트는 시스템 경로를 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]와 함께 제공되는 모든 도구에 대한 올바른 위치로 설정합니다.  
  
<a name="BKMK_q4"></a>   
## <a name="unable-to-find-the-appconfig-file-generated-by-svcutilexe"></a>Svcutil.exe에서 생성한 App.config 파일을 찾을 수 없습니다.  
 **기존 항목 추가** 대화 기본적으로 같은 확장명의 파일만 표시:.cs,.resx,.settings,.xsd,.wsdl 합니다. 모든 파일 형식을 선택 하 여 볼를 지정할 수 있습니다 **모든 파일 (\*.\*)**  의 오른쪽 아래에 있는 목록 상자 드롭다운에는 **기존 항목 추가** 대화 상자.  
  
<a name="BKMK_q5"></a>   
## <a name="compiling-the-client-application-calculatorclient-does-not-contain-a-definition-for-method-name-and-no-extension-method-method-name-accepting-a-first-argument-of-type-calculatorclient-could-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>클라이언트 응용 프로그램의 컴파일: 'CalculatorClient'에 대 한 정의 포함 하지 않는 '\<메서드 이름 >' 확장 메서드 '\<메서드 이름 >' 수락 'CalculatorClient' 형식의 첫 번째 인수를 찾을 수 없습니다 (이십니까 using 지시문 또는 어셈블리 참조가?)  
 `ServiceOperationAttribute`로 표시된 메서드만 외부에 노출됩니다. `ServiceOperationAttribute` 인터페이스에 있는 메서드 중 하나에서 `ICalculator`특성을 생략한 경우 특성이 없는 작업을 호출하는 클라이언트 응용 프로그램을 컴파일하는 동안 이 오류 메시지가 나타납니다.  
  
<a name="BKMK_q6"></a>   
## <a name="compiling-the-client-application-the-type-or-namespace-name-calculatorclient-could-not-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>클라이언트 응용 프로그램을 컴파일하는 동안 다음 오류가 발생합니다. 'CalculatorClient' 형식 또는 네임스페이스 이름을 찾을 수 없습니다. using 지시문 또는 어셈블리 참조가 있는지 확인하십시오.  
 클라이언트 프로젝트에 Proxy.cs 또는 Proxy.vb 파일을 추가하면 이 오류가 발생합니다.  
  
<a name="BKMK_q7"></a>   
## <a name="running-the-client-unhandled-exception-systemservicemodelendpointnotfoundexception-could-not-connect-to-httplocalhost8000servicemodelsamplesservicecalculatorservice-tcp-error-code-10061-no-connection-could-be-made-because-the-target-machine-actively-refused-it"></a>클라이언트를 실행: 처리 되지 않은 예외: System.ServiceModel.EndpointNotFoundException:에 연결 하지 못했습니다 http://localhost:8000/ServiceModelSamples/Service/CalculatorService합니다. TCP 오류 코드 10061: 대상 컴퓨터에서 연결을 거부했으므로 연결하지 못했습니다.  
 서비스를 실행하지 않고 클라이언트 응용 프로그램을 실행하면 이 오류가 발생합니다.  
  
<a name="BKMK_q8"></a>   
## <a name="unhandled-exception-systemservicemodelsecuritysecuritynegotiationexception-soap-security-negotiation-with-httplocalhost8000servicemodelsamplesservicecalculatorservice-for-target-httplocalhost8000servicemodelsamplesservicecalculatorservice-failed"></a>처리 되지 않은 예외: System.ServiceModel.Security.SecurityNegotiationException:와 SOAP 보안 협상 'http://localhost:8000/ServiceModelSamples/Service/CalculatorService'대상'에 대 한http://localhost:8000/ServiceModelSamples/Service/CalculatorService' 하지 못했습니다.  
 이 오류는 도메인에 참가한 컴퓨터가 네트워크에 연결할 수 없는 경우 발생합니다. 컴퓨터를 네트워크에 연결하거나 클라이언트와 서비스 모두에 대해 보안을 해제하십시오. 서비스의 경우에는 WSHttpBinding을 만드는 코드를 다음과 같이 수정합니다.  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```  
  
 클라이언트에 대 한 변경의  **\<보안 >** 요소 아래에서  **\<바인딩 >** 요소는 다음과:  
  
```xml  
<security mode="Node" />  
```  
  
## <a name="see-also"></a>참고 항목  
 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [WCF 문제 해결 퀵 스타트](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 [설치 문제 해결](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
