---
title: ".NET Framework 4.5.1의 런타임 변경 내용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "응용 프로그램 호환성"
  - "런타임 변경 내용"
  - ".NET Framework 4.5.1"
ms.assetid: da880ad7-ba0a-4368-b340-705e3533c351
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# .NET Framework 4.5.1의 런타임 변경 내용
드문 경우지만 런타임 변경 내용이 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 또는 4.5 버전을 대상으로 하지만 4.5.1 런타임에 실행되는 기존 앱에 영향을 줄 수 있습니다. 다음 영역에 이러한 변경 내용이 포함되어 있습니다.  
  
-   [코어](#Core)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
 다음 테이블의 범위 열에는 각 변경 내용의 영향력이 지정되어 있습니다.  
  
-   주요함 다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다. 이 범주에 속한 런타임 변경 내용은 없습니다.  
  
-   사소함 소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.  
  
-   특별한 경우 일반적이지 않은 매우 특별한 시나리오의 앱에 영향을 주는 변경 내용입니다.  
  
-   투명 앱 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다. 이 변경 내용으로 인한 앱 수정은 필요하지 않습니다.  
  
<a name="Core"></a>   
## <a name="core-runtime-changes"></a>코어 런타임 변경 내용  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> serialization</TKey, TValue>|A <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 와.NET Framework 4.5에서 serialize 된 개체는 <xref:System.Runtime.Serialization.NetDataContractSerializer> 종류의 내부 변경 내용 때문에.NET Framework 4.5.1 및 4.5.2에서에서 역직렬화 할 수 없습니다.\</TKey, TValue><br /><br /> 이 변경은 않습니다 *하지* 다음과 같은 시나리오에서 적용 합니다.<br /><br /> A <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 개체는.NET Framework 4.5에서 serialize 및 deserialize는 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</TKey, TValue> <xref:System.Runtime.Serialization.NetDataContractSerializer> 에 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 개체를 deserialize 할 수 있습니다.<br /><br /> A <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 개체는.NET Framework의 이후 버전에서 serialize 되 고.NET Framework 4.5에서 deserialize 합니다.\</TKey, TValue> <xref:System.Runtime.Serialization.NetDataContractSerializer> .NET Framework 4.5에는 개체를 deserialize 할 수 있습니다.<br /><br /> 버전 간 직렬화 및 역직렬화는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 후.NET Framework 4.5는.NET Framework의 모든 버전 간에 개체.</TKey, TValue> 이 변경 내용은.NET Framework 4.5를 사용 하 여 serialize 된 개체에 적용 됩니다. *만*합니다.|두 가지 해결 방법을 serialize 하는 데 필요한 경우에 사용할 수 있는 한 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> .NET Framework 4.5에서 개체를.NET Framework의 이후 버전에서 deserialize:\</TKey, TValue><br /><br /> 와 같은 경우 대체 serializer를 사용 하는 <xref:System.Runtime.Serialization.DataContractSerializer> 또는 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>합니다.<br /><br /> 로 업그레이드는 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], deserialization을 지 원하는 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> .NET Framework 4.5를 사용 하 여 serialize 하는 개체입니다.\</TKey, TValue>|사소함|  
|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> 클래스|<xref:System.Diagnostics.Tracing.EventListener> 포함 된 null 있는 문자열을 자릅니다. null 문자를 지원 하지 않는 <xref:System.Diagnostics.Tracing.EventSource> 클래스입니다.|변경 내용을 사용 하는 앱에만 영향을 줍니다 <xref:System.Diagnostics.Tracing.EventListener> 읽을 <xref:System.Diagnostics.Tracing.EventSource> 프로세스에서 데이터를 null 문자 구분 기호로 사용 합니다.|Microsoft Edge|  
|<xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 클래스|이제 런타임에서 다음을 지정 하는 계약 적용: 클래스에서 파생 <xref:System.Diagnostics.Tracing.EventSource> ETW를 정의 하는 이벤트 메서드는 기본 클래스를 호출 해야 <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=fullName> 메서드는 이벤트 id 다음에 ETW 이벤트 메서드가 전달 된 동일한 인수입니다.|<xref:System.IndexOutOfRangeException> 경우 예외가 throw 됩니다는 <xref:System.Diagnostics.Tracing.EventListener> 읽고 <xref:System.Diagnostics.Tracing.EventSource> 이 계약을 위반 하는 이벤트 소스에 대 한 프로세스의 데이터입니다.<br /><br /> 참조 [완화: EventSource.WriteEvent 메서드 호출](../../../docs/framework/migration-guide/mitigation-eventsource-writeevent-method-calls.md)|사소함|  
|응용 프로그램 도메인 간의 개체 역직렬화|경우에 따라, 응용 프로그램 기반이 다른 둘 이상의 앱 도메인이 앱에서 사용되는 경우 앱 도메인 간에 논리 호출 컨텍스트의 개체를 deserialize하려고 하면 예외가 throw됩니다.|이 문제는 매우 특정한 시나리오에서 발생합니다. 자세한 내용 및 해결 방법에 대 한 참조 [해결 방법: Deserialization의 개체 응용 프로그램 도메인 간](../../../docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)합니다.|Microsoft Edge|  
|<xref:System.IO.Stream.Dispose%2A?displayProperty=fullName> 메서드|[!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] 응용 프로그램의 경우 [!INCLUDE[wrt](../../../includes/wrt-md.md)] 스트림 어댑터는 더 이상 호출의 <xref:System.IO.Stream.FlushAsync%2A> 메서드에서 <xref:System.IO.Stream.Dispose%2A> 메서드.|이 변경 내용은 영향을 주지 않습니다. 개발자는 다음과 같은 코드를 작성하여 이전 동작을 복원할 수 있습니다.<br /><br /> `using (System.IO.Stream stream = GetWindowsRuntimeStream() As Stream)  {     // do something     await stream.FlushAsync();   }`|투명|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf-runtime-changes"></a>WCF(Windows Communication Foundation) 런타임 변경 내용  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|[minFreeMemoryPercentageToActiveService](http://msdn.microsoft.com/library/ms731336.aspx) 구성 설정|이 설정은 WCF 서비스 활성화를 위해 서버에서 사용할 수 있는 최소 메모리를 지정합니다. 차단 하도록 설계 된 <xref:System.OutOfMemoryException> 예외입니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 이 설정의 효력이 없으며, [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]에서 해당 설정이 적용됩니다.|웹 서버의 사용 가능한 메모리가 구성 설정에서 정의된 백분율보다 적은 경우 예외가 발생합니다. 성공적으로 시작되었지만 제한된 메모리 환경에서 실행되는 일부 WCF 서비스의 경우 실패할 수 있습니다.<br /><br /> 참조 [완화: minFreeMemoryPercentageToActiveService 구성 설정](../../../docs/framework/migration-guide/mitigation-minfreememorypercentagetoactiveservice-configuration-setting.md)합니다.|사소함|  
  
## <a name="see-also"></a>참고 항목  
 [변경 내용 대상 변경](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-5-1.md)   
 [4.5의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.2의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)