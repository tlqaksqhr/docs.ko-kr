---
title: "설치 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# 설치 문제 해결
이 항목에서는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 설치 문제를 해결하는 방법을 설명합니다.  
  
## 일부 Windows Communication Foundation 레지스트리 키를 .NET Framework 3.0에서 MSI 복구 작업을 수행하여 복구할 수 없음  
 다음과 같은 레지스트리 키를 삭제한 경우 이 문제가 발생합니다.  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ServiceModelService 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ServiceModelOperation 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ServiceModelEndpoint 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SMSvcHost 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSDTC Bridge 3.0.0.0  
  
 이러한 키는 **제어판**의 **프로그램 추가\/제거** 애플릿에서 실행된 .NET Framework 3.0 설치 관리자를 사용하여 복구를 실행해도 다시 만들 수 없습니다.해당 키를 다시 만들려면 .NET Framework 3.0을 제거하고 다시 설치해야 합니다.  
  
## .NET Framework 3.0 패키지 설치 시 WMI 서비스 손상으로 인해 Windows Communication Foundation WMI 공급자가 설치되지 않음  
 WMI 서비스 손상으로 인해 Windows Communication Foundation WMI 공급자가 설치되지 않을 수 있습니다.설치 시 Windows Communication Foundation 설치 관리자가 mofcomp.exe 구성 요소를 사용하여 WCF .mof 파일을 등록할 수 없습니다.다음과 같은 증상이 있습니다.  
  
1.  .NET Framework 3.0 설치를 완료했지만 WCF WMI 공급자가 등록되지 않습니다.  
  
2.  오류 이벤트가 WCF의 WMI 공급자 등록이나 mofcomp.exe 실행에 관련된 문제를 참조하는 응용 프로그램 이벤트 로그에 표시됩니다.  
  
3.  사용자의 %temp% 디렉터리에 있는 이름이 dd\_wcf\_retCA\*인 설치 로그 파일에 WCF WMI 공급자 등록 실패에 대한 참조가 있습니다.  
  
4.  다음과 같은 예외가 이벤트 로그나 설치 추적 로그 파일에 표시됩니다.  
  
     ServiceModelReg \[11:09:59:046\]: System.ApplicationException: "E:\\WINDOWS\\Microsoft.NET\\Framework\\v3.0\\Windows Communication Foundation\\ServiceModel.mof"을\(를\) 통해 E:\\WINDOWS\\system32\\wbem\\mofcomp.exe을\(를\) 실행하는 동안 예기치 않은 3 결과가 나타났습니다.  
  
     또는  
  
     ServiceModelReg \[07:19:33:843\]: System.TypeInitializationException: 'System.Management.ManagementPath'의 형식 이니셜라이저에서 예외를 throw했습니다.\-\-\-\> System.Runtime.InteropServices.COMException \(0x80040154\): 80040154 오류로 인해 CLSID가 {CF4CC405\-E2C5\-4DDD\-B3CE\-5E7582D8C9FA}인 구성 요소의 COM 클래스 팩터리를 검색하지 못했습니다.  
  
     또는  
  
     ServiceModelReg \[07:19:32:750\]: System.IO.FileNotFoundException: 파일이나 어셈블리 'C:\\WINDOWS\\system32\\wbem\\mofcomp.exe' 또는 여기에 종속되어 있는 파일이나 어셈블리 중 하나를 로드할 수 없습니다.지정한 파일을 찾을 수 없습니다.  
  
     파일 이름: 'C:\\WINDOWS\\system32\\wbem\\mofcomp.exe  
  
 위에 설명한 문제를 해결하려면 다음 단계를 수행해야 합니다.  
  
1.  [WMI Diagnosis Utility, 버전 2.0](http://go.microsoft.com/fwlink/?LinkId=94685)을 실행하여 WMI 서비스를 복구합니다.이 도구 사용에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 [WMI Diagnosis Utility](http://go.microsoft.com/fwlink/?LinkId=94686) 항목을 참조하십시오.  
  
 **제어판**의 **프로그램 추가\/제거** 애플릿을 사용하여 .NET Framework 3.0 설치를 복구하거나 .NET Framework 3.0을 제거하고 다시 설치합니다.  
  
## .NET Framework 3.5 설치 후 .NET Framework 3.0을 복구하면 machine.config에서 .NET Framework 3.5에 의해 추가된 구성 요소가 제거됨  
 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 설치한 후 .NET Framework 3.0을 복구하면 machine.config에서 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]에 의해 추가된 구성 요소가 제거됩니다.그러나 web.config는 그대로 유지됩니다.이 문제를 해결하는 방법은 ARP를 통해 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 설치한 후 복구하거나 [워크플로 서비스 등록 도구\(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)를 `/c` 스위치와 함께 사용하는 것입니다.  
  
 [워크플로 서비스 등록 도구\(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)는 %windir%\\Microsoft.NET\\framework\\v3.5\\ 또는 %windir%\\Microsoft.NET\\framework64\\v3.5\\에 있습니다.  
  
## .NET Framework 3.5 설치 후 WCF\/WF Webhost에 대해 IIS를 올바로 구성  
 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 설치하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 관련 추가 IIS 구성 설정을 구성하지 못한 경우 설치 로그에 오류가 계속 기록됩니다.필요한 구성 설정이 없기 때문에 WorkflowServices 응용 프로그램을 실행할 수 없습니다.예를 들어 xoml 또는 규칙 서비스를 로드하지 못할 수 있습니다.  
  
 이 문제를 해결하려면 `/c` 스위치가 있는 [워크플로 서비스 등록 도구\(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)를 사용하여 컴퓨터의 IIS 스크립트 맵을 적절히 구성합니다.[워크플로 서비스 등록 도구\(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)는 %windir%\\Microsoft.NET\\framework\\v3.5\\ 또는 %windir%\\Microsoft.NET\\framework64\\v3.5\\에 있습니다.  
  
## ‘System.ServiceModel, Version 3.0.0.0, Culture\=neutral, PublicKeyToken\=b77a5c561934e089’ 어셈블리에서 ‘System.ServiceModel.Activation.HttpModule’ 형식을 로드할 수 없습니다.  
 이 오류는 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]을 설치한 다음 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)] HTTP 활성화를 사용하도록 설정한 경우에 발생합니다.이 문제를 해결하려면 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] 명령 프롬프트에서 다음 명령줄을 실행합니다.  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## 참고 항목  
 [설치 지침](../../../docs/framework/wcf/samples/set-up-instructions.md)