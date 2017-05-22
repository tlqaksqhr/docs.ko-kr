---
title: ".NET Framework 4.5.1의 런타임 변경 내용 | Microsoft 문서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- runtime changes
- .NET Framework 4.5.1
ms.assetid: da880ad7-ba0a-4368-b340-705e3533c351
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4e4903c2f25354005f95b3ed8f9728cfe8a0a92e
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="runtime-changes-in-the-net-framework-451"></a>.NET Framework 4.5.1의 런타임 변경 내용
드문 경우지만 런타임 변경 내용이 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 또는 4.5 버전을 대상으로 하지만 4.5.1 런타임에 실행되는 기존 앱에 영향을 줄 수 있습니다. 다음 영역에 이러한 변경 내용이 포함되어 있습니다.  
  
-   [핵심](#Core)  
  
-   [WCF(Windows Communication Foundation)](#WCF)  
  
 다음 테이블의 범위 열에는 각 변경 내용의 영향력이 지정되어 있습니다.  
  
-   주요함 다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다. 이 범주에 속한 런타임 변경 내용은 없습니다.  
  
-   사소함 소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.  
  
-   특별한 경우 일반적이지 않은 매우 특별한 시나리오의 앱에 영향을 주는 변경 내용입니다.  
  
-   투명 앱 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다. 이 변경 내용으로 인한 앱 수정은 필요하지 않습니다.  
  
<a name="Core"></a>   
## <a name="core-runtime-changes"></a>코어 런타임 변경 내용  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> serialization|<xref:System.Runtime.Serialization.NetDataContractSerializer>를 사용하여 .NET Framework 4.5에서 serialization된 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 개체는 형식에서의 내부적 변경으로 인해 .NET Framework 4.5.1 및 4.5.2에서 deserialization할 수 없습니다.<br /><br /> 이러한 변경 내용은 다음의 시나리오에서는 적용되지 *않습니다*.<br /><br /> <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 개체가 .NET Framework 4.5에서 serialization되고 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 deserialization되었습니다. [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]의 <xref:System.Runtime.Serialization.NetDataContractSerializer>은 개체를 deserialization할 수 있습니다.<br /><br /> <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 개체가 .NET Framework의 최근 버전에서 serialization되고 .NET Framework 4.5에서 deserialization되었습니다. .NET Framework 4.5의 <xref:System.Runtime.Serialization.NetDataContractSerializer>은 개체를 deserialization할 수 있습니다.<br /><br /> .NET Framework 4.5 이후의 .NET Framework 버전 간 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 개체의 버전 간 serialization 및 deserialization. 이 변경 내용은 .NET Framework 4.5*만*을 사용하여 직렬화된 개체에 적용됩니다.|.NET Framework 4.5에서 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 개체를 serialization하고 .NET Framework의 이후 버전에서 deserialization해야 하는 경우 두 가지 해결 방법이 있습니다.<br /><br /> <xref:System.Runtime.Serialization.DataContractSerializer> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>와 같은 대체 serializer를 사용합니다.<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]로 업그레이드하세요. 이것은 NET Framework 4.5를 사용하여 serialization된 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 개체의 deserialization을 지원합니다.|부|  
|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> 클래스|<xref:System.Diagnostics.Tracing.EventListener>는 포함된 null이 있는 문자열을 자릅니다. Null 문자는 <xref:System.Diagnostics.Tracing.EventSource> 클래스에서 지원되지 않습니다.|이 변경 내용은 <xref:System.Diagnostics.Tracing.EventListener>를 사용하여 프로세스의 <xref:System.Diagnostics.Tracing.EventSource> 데이터를 읽고 null 문자를 구분 기호로 사용하는 앱에만 영향을 줍니다.|가장자리|  
|<xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 클래스|이제 런타임에서는 다음을 지정하는 계약이 적용됩니다. ETW 이벤트 메서드를 정의하는 <xref:System.Diagnostics.Tracing.EventSource>에서 파생된 클래스는 이벤트 ID 다음에 ETW 이벤트 메서드가 전달된 동일한 인수를 사용하여 기본 클래스 <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=fullName> 메서드를 호출해야 합니다.|<xref:System.IndexOutOfRangeException>가 이 계약을 위반하는 이벤트 소스에 대해 프로세스의 <xref:System.Diagnostics.Tracing.EventListener> 데이터를 읽는 경우 <xref:System.Diagnostics.Tracing.EventSource> 예외가 throw됩니다.<br /><br /> [완화: EventSource.WriteEvent 메서드 호출](../../../docs/framework/migration-guide/mitigation-eventsource-writeevent-method-calls.md)을 참조하십시오.|사소함|  
|응용 프로그램 도메인 간의 개체 역직렬화|경우에 따라, 응용 프로그램 기반이 다른 둘 이상의 앱 도메인이 앱에서 사용되는 경우 앱 도메인 간에 논리 호출 컨텍스트의 개체를 deserialize하려고 하면 예외가 throw됩니다.|이 문제는 매우 특정한 시나리오에서 발생합니다. 자세한 내용 및 완화에 대해서는 [완화: 응용 프로그램 도메인 간 개체의 역직렬화](../../../docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)를 참조하십시오.|Microsoft Edge|  
|<xref:System.IO.Stream.Dispose%2A?displayProperty=fullName> 메서드|[!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] 앱에서, [!INCLUDE[wrt](../../../includes/wrt-md.md)] 스트림 어댑터는 더 이상 <xref:System.IO.Stream.FlushAsync%2A> 메서드에서 <xref:System.IO.Stream.Dispose%2A> 메서드를 호출하지 않습니다.|이 변경 내용은 영향을 주지 않습니다. 개발자는 다음과 같은 코드를 작성하여 이전 동작을 복원할 수 있습니다.<br /><br /> `using (System.IO.Stream stream = GetWindowsRuntimeStream() As Stream)  {     // do something     await stream.FlushAsync();   }`|투명|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf-runtime-changes"></a>WCF(Windows Communication Foundation) 런타임 변경 내용  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|[minFreeMemoryPercentageToActiveService](http://msdn.microsoft.com/library/ms731336.aspx) 구성 설정|이 설정은 WCF 서비스 활성화를 위해 서버에서 사용할 수 있는 최소 메모리를 지정합니다. 또한 이 설정은 <xref:System.OutOfMemoryException> 예외가 발생되지 않도록 설계되었습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 이 설정의 효력이 없으며, [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]에서 해당 설정이 적용됩니다.|웹 서버의 사용 가능한 메모리가 구성 설정에서 정의된 백분율보다 적은 경우 예외가 발생합니다. 성공적으로 시작되었지만 제한된 메모리 환경에서 실행되는 일부 WCF 서비스의 경우 실패할 수 있습니다.<br /><br /> [완화: minFreeMemoryPercentageToActiveService 구성 설정](../../../docs/framework/migration-guide/mitigation-minfreememorypercentagetoactiveservice-configuration-setting.md)을 참조하십시오.|사소함|  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)   
 [4.5의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.2의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
