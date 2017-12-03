---
title: "WCF 성능 카운터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f3f9834e99fb7fa98e2f986a1ce5460aa387143f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-performance-counters"></a>WCF 성능 카운터
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에는 응용 프로그램의 성능을 측정하는 데 도움이 되는 다양한 성능 카운터가 있습니다.  
  
## <a name="enabling-performance-counters"></a>성능 카운터 사용  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스의 app.config 구성 파일을 통해 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스에 대한 성능 카운터를 다음과 같이 활성화할 수 있습니다.  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 특정 유형의 성능 카운터를 활성화하도록 `performanceCounters` 특성을 설정할 수 있습니다. 유효한 값은 다음과 같습니다.  
  
-   All: 모든 범주 카운터(ServiceModelService, ServiceModelEndpoint, ServiceModelOperation)가 활성화됩니다.  
  
-   ServiceOnly: ServiceModelService 범주 카운터만 활성화됩니다. 기본값입니다.  
  
-   Off: ServiceModel* 성능 카운터가 비활성화됩니다.  
  
 모든 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 응용 프로그램에 대해 성능 카운터를 활성화하려면 Machine.config 파일에 구성 설정을 입력할 수 있습니다.  참조 하십시오는 **성능 카운터에 대 한 메모리 크기 늘리기** 컴퓨터에 성능 카운터에 대 한 충분 한 메모리를 구성 하는 방법에 대 한 자세한 내용은 아래 섹션.  
  
 사용자 지정 작업 호출자와 같은 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 확장성 지점을 사용하는 경우에는 성능 카운터도 내보내야 합니다. 이는 확장성 지점을 구현하는 경우 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서 더 이상 기본 경로에서 표준 성능 카운터 데이터를 내보낼 수 없기 때문입니다. 수동 성능 카운터 지원을 구현하지 않으면 예상하는 성능 카운터 데이터가 표시되지 않을 수 있습니다.  
  
 코드를 사용하여 다음과 같이 성능 카운터를 활성화할 수도 있습니다.  
  
```  
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a>성능 데이터 보기  
 성능 카운터에서 캡처한 데이터를 보려면 Windows와 함께 제공된 성능 모니터(Perfmon.exe)를 사용할 수 있습니다. 로 이동 하 여이 도구를 시작할 수 **시작**를 클릭 하 고 **실행** 유형과 `perfmon.exe` 대화 상자에서 합니다.  
  
> [!NOTE]
>  끝점 디스패처가 마지막 메시지를 처리하기 이전에 성능 카운터 인스턴스가 해제될 수 있습니다. 그러면 일부 메시지에 대한 성능 데이터가 캡처되지 않습니다.  
  
## <a name="increasing-memory-size-for-performance-counters"></a>성능 카운터에 대한 메모리 크기 늘리기  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 성능 카운터 범주에 대해 별도의 공유 메모리를 사용합니다.  
  
 기본적으로 별도의 공유 메모리는 전역 성능 카운터 메모리 크기의 1/4로 설정됩니다. 기본 전역 성능 카운터 메모리는 524,288바이트입니다. 따라서 세 개의 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 성능 카운터 범주의 기본 크기는 각각 약 128KB입니다. 컴퓨터에 있는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 응용 프로그램의 런타임 특성에 따라 성능 카운터 메모리가 부족할 수 있습니다. 이 때 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]는 응용 프로그램 이벤트 로그에 오류를 기록합니다. 오류 내용에는 성능 카운터가 로드되지 않았다는 설명이 표시되며, "System.InvalidOperationException: 사용자 지정 카운터 파일 뷰 메모리가 부족합니다."라는 예외가 항목에 포함됩니다. 오류 수준에서 추적 기능을 사용하도록 설정하면 이 오류도 추적됩니다. 성능 카운터 메모리가 부족한 상태에서 성능 카운터를 활성화한 상태로 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 응용 프로그램을 계속 실행하면 성능이 저하될 수 있습니다. 컴퓨터 관리자는 언제든지 최대 성능 카운터 수를 지원하는 데 충분한 메모리를 할당하도록 컴퓨터를 구성해야 합니다.  
  
 레지스트리에서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 범주에 대한 성능 카운터 메모리 양을 변경할 수 있습니다. 그렇게 하려면 다음 세 위치에 `FileMappingSize`라는 새로운 DWORD 값을 추가하여 원하는 값(바이트)으로 설정해야 합니다. 컴퓨터를 다시 부팅하여 변경 내용을 적용합니다.  
  
-   HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance  
  
-   HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance  
  
-   HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance  
  
 많은 수의 개체(예: ServiceHost)를 삭제할 때 가비지가 수집되기를 대기 중인 경우 `PrivateBytes` 성능 카운터는 매우 높은 수를 등록합니다. 이 문제를 해결하려면 응용 프로그램 관련 카운터를 추가하거나 `performanceCounters` 특성을 사용하여 서비스 수준 카운터만 활성화할 수 있습니다.  
  
## <a name="types-of-performance-counters"></a>성능 카운터 형식  
 성능 카운터의 범위는 서비스, 끝점 및 작업의 세 가지 수준입니다.  
  
 WMI를 사용하여 성능 카운터 인스턴스의 이름을 검색할 수 있습니다. 예를 들면 다음과 같습니다.  
  
-   WMI를 통해 서비스 카운터 인스턴스 이름을 가져올 수 [서비스](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) 인스턴스의 "CounterInstanceName" 속성입니다.  
  
-   WMI를 통해 끝점 카운터 인스턴스 이름을 가져올 수 [끝점](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) 인스턴스의 "CounterInstanceName" 속성입니다.  
  
-   WMI를 통해 작업 카운터 인스턴스 이름을 가져올 수 [끝점](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) 인스턴스의 "GetOperationCounterInstanceName" 메서드.  
  
 WMI에 대 한 자세한 내용은 참조 하십시오. [진단에 대 한 Windows Management Instrumentation를 사용 하 여](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)합니다.  
  
### <a name="service-performance-counters"></a>서비스 성능 카운터  
 서비스 성능 카운터는 서비스 동작을 전반적으로 측정하며 전체 서비스 성능을 진단하는 데 사용할 수 있습니다. 이러한 카운터는 성능 모니터에서 볼 때 `ServiceModelService 4.0.0.0` 성능 개체 아래에 있습니다. 인스턴스 이름은 다음 패턴으로 지정됩니다.  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
 서비스 범위 내의 카운터가 끝점 컬렉션 내의 카운터로부터 집계됩니다.  
  
 새 InstanceContext가 만들어지면 서비스 인스턴스 만들기에 대한 성능 카운터가 증가합니다. 기존 서비스에서 활성화 상태가 아닌 메시지를 받거나, 한 세션에서 인스턴스에 연결하고 세션을 끝낸 다음 다른 세션에서 다시 연결하는 경우에도 새 InstanceContext가 만들어집니다.  
  
### <a name="endpoint-performance-counters"></a>끝점 성능 카운터  
 끝점 성능 카운터를 사용하면 끝점이 메시지를 수신하는 방식을 나타내는 데이터를 조사할 수 있습니다. 이러한 카운터는 성능 모니터를 사용하여 볼 때 `ServiceModelEndpoint 4.0.0.0` 성능 개체 아래에 있습니다. 인스턴스 이름은 다음 패턴으로 지정됩니다.  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 데이터는 개별 작업을 위해 수집된 데이터와 비슷하지만 끝점에서만 집계됩니다.  
  
 끝점 범위 내의 카운터가 작업 컬렉션 내의 카운터로부터 집계됩니다.  
  
> [!NOTE]
>  두 끝점의 계약 이름과 주소가 동일한 경우 두 끝점은 동일한 카운터 인스턴스에 매핑됩니다.  
  
### <a name="operation-performance-counters"></a>작업 성능 카운터  
 작업 성능 카운터는 성능 모니터에서 볼 때 `ServiceModelOperation 4.0.0.0` 성능 개체 아래에 있습니다. 각 작업에는 개별 인스턴스가 있습니다. 즉, 지정된 계약에 10개의 작업이 있는 경우 10개의 작업 카운터 인스턴스가 해당 계약에 연결되어 있습니다. 개체 인스턴스 이름은 다음 패턴으로 지정됩니다.  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 이 카운터를 사용하면 호출이 사용되는 방법과 작업 진행 상태를 측정할 수 있습니다.  
  
 카운터가 여러 범위에 표시될 때 상위 범위에서 수집된 데이터가 하위 범위의 데이터와 결합됩니다. 예를 들어, 끝점의 `Calls`는 끝점에 있는 모든 작업 호출의 합계를 나타내고 서비스의 `Calls`는 서비스에 있는 모든 끝점에 대한 모든 호출 합계를 나타냅니다.  
  
> [!NOTE]
>  계약에 중복 작업 이름이 있는 경우 두 작업에 대해 카운터 인스턴스를 하나만 가져옵니다.  
  
## <a name="programming-the-wcf-performance-counters"></a>WCF 성능 카운터 프로그래밍  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 성능 카운터를 프로그래밍 방식으로 액세스할 수 있도록 SDK 설치 폴더에 여러 파일이 설치됩니다. 설치되는 파일은 다음과 같습니다.  
  
-   _ServiceModelEndpointPerfCounters.vrg  
  
-   _ServiceModelOperationPerfCounters.vrg  
  
-   _ServiceModelServicePerfCounters.vrg  
  
-   _SMSvcHostPerfCounters.vrg  
  
-   _TransactionBridgePerfCounters.vrg  
  
 카운터를 프로그래밍 방식으로 액세스 하는 방법에 대 한 자세한 내용은 참조 하십시오. [성능 카운터 프로그래밍 아키텍처](http://go.microsoft.com/fwlink/?LinkId=95179)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
