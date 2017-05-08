---
title: "초보자를 위한 자습서 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 초보자를 위한 자습서 문제 해결
이 항목에서는 초보자를 위한 자습서를 수행할 때 발생하는 가장 일반적인 문제 및 해결 방법을 보여 줍니다.  
  
1.  [하드 드라이브에서 프로젝트 파일을 찾을 수 없습니다.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [서비스 응용 프로그램을 실행하려고 할 때 다음 오류가 발생합니다. HTTP가 URL http://+:8000/ServiceModelSamples/Service/을(를) 등록할 수 없습니다.사용자의 프로세스에 이 네임스페이스에 액세스할 수 있는 권한이 없습니다.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [Svcutil.exe 도구를 사용하려고 할 때 다음 오류가 발생합니다. 'svcutil'은(는) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는 배치 파일이 아닙니다.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [Svcutil.exe에서 생성한 App.config 파일을 찾을 수 없습니다.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [클라이언트 응용 프로그램을 컴파일하는 동안 다음과 같은 구문 오류가 발생합니다. 'CalculatorClient'에 '&lt;method name&gt;'에 대한 정의가 없고 'CalculatorClient' 형식의 첫 번째 인수를 허용하는 확장 메서드 '&lt;method name&gt;'이(가) 없습니다. using 지시문 또는 어셈블리 참조가 있는지 확인하십시오.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [클라이언트 응용 프로그램을 컴파일하는 동안 다음 오류가 발생합니다. 'CalculatorClient' 형식 또는 네임스페이스 이름을 찾을 수 없습니다. using 지시문 또는 어셈블리 참조가 있는지 확인하십시오.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [클라이언트를 실행할 때 다음 오류가 발생합니다. 처리되지 않은 예외: System.ServiceModel.EndpointNotFoundException: http://localhost:8000/ServiceModelSamples/Service/CalculatorService에 연결할 수 없습니다.TCP 오류 코드 10061: 대상 컴퓨터에서 연결을 거부했으므로 연결하지 못했습니다.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## 하드 드라이브에서 프로젝트 파일을 찾을 수 없습니다.  
 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]는 프로젝트 파일을 [!INCLUDE[wv](../../../includes/wv-md.md)]에서 c:\\users\\\<사용자 이름\\Documents\\\<Visual Studio 버전\>\\Projects에 저장하고, [!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)]는 이전 버전 Windows에서 c:\\Documents and Settings\\\<사용자 이름\>\\My Documents\\\<Visual Studio 버전\>\\Projects에 저장합니다.  
  
<a name="BKMK_q2"></a>   
## 서비스 응용 프로그램을 실행하려고 할 때 다음 오류가 발생합니다. HTTP가 URL http:\/\/\+:8000\/ServiceModelSamples\/Service\/을\(를\) 등록할 수 없습니다.사용자의 프로세스에 이 네임스페이스에 액세스할 수 있는 권한이 없습니다.  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 호스팅하는 프로세스는 관리자 권한으로 실행해야 합니다.[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 내에서 서비스를 실행 중인 경우에는 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]을 관리자로 실행해야 합니다.이렇게 하려면 **시작**을 클릭하고 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]을 마우스 오른쪽 단추로 클릭한 다음 **관리자 권한으로 실행**을 클릭합니다.명령줄 프롬프트에서 서비스를 실행 중인 경우에는 동일한 방식으로 명령줄 프롬프트를 관리자로 시작해야 합니다.**시작**을 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 다음 **관리자 권한으로 실행**을 클릭합니다.  
  
<a name="BKMK_q3"></a>   
## Svcutil.exe 도구를 사용하려고 할 때 다음 오류가 발생합니다. 'svcutil'은\(는\) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는 배치 파일이 아닙니다.  
 Svcutil.exe는 시스템 경로에 있어야 합니다.가장 간단한 해결책은 명령 프롬프트를 사용하는 것입니다.**시작**을 클릭하고 **모든 프로그램**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **Visual Studio 도구**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **명령 프롬프트**를 차례로 선택합니다.이 명령 프롬프트는 시스템 경로를 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]의 일부로 제공되는 모든 도구의 올바른 위치로 설정합니다.  
  
<a name="BKMK_q4"></a>   
## Svcutil.exe에서 생성한 App.config 파일을 찾을 수 없습니다.  
 **기존 항목 추가** 대화 상자는 기본적으로 .cs, .resx, .settings, .xsd, .wsdl과 같은 확장명의 파일만 표시합니다.**기존 항목 추가** 대화 상자의 오른쪽 아래 모퉁이에 있는 드롭다운 목록 상자에서 **모든 파일 \(\*.\*\)**을 선택하여 모든 파일 형식을 볼 수 있도록 지정할 수 있습니다.  
  
<a name="BKMK_q5"></a>   
## 클라이언트 응용 프로그램을 컴파일하는 동안 다음과 같은 구문 오류가 발생합니다. 'CalculatorClient'에 '\<method name\>'에 대한 정의가 없고 'CalculatorClient' 형식의 첫 번째 인수를 허용하는 확장 메서드 '\<method name\>'이\(가\) 없습니다. using 지시문 또는 어셈블리 참조가 있는지 확인하십시오.  
 `ServiceOperationAttribute`로 표시된 메서드만 외부에 노출됩니다.`ICalculator` 인터페이스에 있는 메서드 중 하나에서 `ServiceOperationAttribute` 특성을 생략한 경우 특성이 없는 작업을 호출하는 클라이언트 응용 프로그램을 컴파일하는 동안 이 오류 메시지가 나타납니다.  
  
<a name="BKMK_q6"></a>   
## 클라이언트 응용 프로그램을 컴파일하는 동안 다음 오류가 발생합니다. 'CalculatorClient' 형식 또는 네임스페이스 이름을 찾을 수 없습니다. using 지시문 또는 어셈블리 참조가 있는지 확인하십시오.  
 클라이언트 프로젝트에 Proxy.cs 또는 Proxy.vb 파일을 추가하면 이 오류가 발생합니다.  
  
<a name="BKMK_q7"></a>   
## 클라이언트를 실행할 때 다음 오류가 발생합니다. 처리되지 않은 예외: System.ServiceModel.EndpointNotFoundException: http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService에 연결할 수 없습니다.TCP 오류 코드 10061: 대상 컴퓨터에서 연결을 거부했으므로 연결하지 못했습니다.  
 서비스를 실행하지 않고 클라이언트 응용 프로그램을 실행하면 이 오류가 발생합니다.  
  
<a name="BKMK_q8"></a>   
## 다음 오류가 발생합니다. 처리되지 않은 예외: System.ServiceModel.Security.SecurityNegotiationException: 'http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService' 대상에 대한 'http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService'과\(와\)의 SOAP 보안 협상을 실행하지 못했습니다.  
 이 오류는 도메인에 참가한 컴퓨터가 네트워크에 연결할 수 없는 경우 발생합니다.컴퓨터를 네트워크에 연결하거나 클라이언트와 서비스 모두에 대해 보안을 해제하십시오.서비스의 경우에는 WSHttpBinding을 만드는 코드를 다음과 같이 수정합니다.  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
  
```  
  
 클라이언트의 경우에는 **\<binding\>** 요소 아래의 **\<security\>** 요소를 다음과 같이 변경합니다.  
  
```  
<security mode="Node" />  
```  
  
## 참고 항목  
 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md)   
 [WCF 문제 해결 퀵 스타트](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)   
 [설치 문제 해결](../../../docs/framework/wcf/troubleshooting-setup-issues.md)