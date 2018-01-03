---
title: ".NET 네이티브 리플렉션 API 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0429c049-22a3-4ba1-9cc8-f6ee91e31d9c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae0037377e9cf092888febb4d74f353ddd8234cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="net-native-reflection-api-reference"></a>.NET 네이티브 리플렉션 API 참조
[!INCLUDE[net_native](../../../includes/net-native-md.md)] 에는 새 예외 형식인 [System.Runtime.CompilerServices.MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), [System.Reflection.MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)및 [System.Reflection.MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)이 포함됩니다. 세 가지 예외 형식 모두에 대해 다음 사항을 확인하세요.  
  
 이러한 형식은 내부용으로만 사용됩니다.  
 이러한 세 가지 예외 형식은 [!INCLUDE[net_native](../../../includes/net-native-md.md)] 도구 체인에만 사용됩니다. [!INCLUDE[net_native](../../../includes/net-native-md.md)] 도구 체인이 프로그램을 계속 실행할 수 없게 하는 데이터 누락을 감지하면 예외가 throw됩니다.  
  
 이러한 예외를 코드에서 처리하지 마세요.  
 이러한 예외는 응용 프로그램에 필요한 메타데이터가 없거나( [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) 및 [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 예외), 응용 프로그램에 필요한 구현 코드가 누락되었음( [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) 예외)을 나타냅니다. 런타임 지시문(.rd.xml) 파일을 수정하여 필요한 메타데이터 또는 구현 코드를 런타임에 사용 가능하게 하는 방식으로 이러한 예외 조건을 수정합니다. 자세한 내용은 [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)을 참조하십시오. [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) 및 [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) 예외를 제거하는 런타임 지시문 파일에 대한 적절한 항목을 제공하는 두 개의 문제 해결사를 사용할 수 있습니다.  
  
-   형식의 경우 [MissingMetadataException 문제 해결사](http://dotnet.github.io/native/troubleshooter/type.html) 입니다.  
  
-   메서드의 경우 [MissingMetadataException 문제 해결사](http://dotnet.github.io/native/troubleshooter/method.html) 입니다.  
  
> [!NOTE]
>  이 참조는 [!INCLUDE[net_native](../../../includes/net-native-md.md)]에 고유한 세 가지 예외 형식을 설명합니다. .NET Framework 핵심 리플렉션 API에 대한 참조 설명서는 [System.Reflection 네임스페이스](http://msdn.microsoft.com/library/gg145033.aspx)를 참조하세요. .NET Framework 핵심 interop API에 대한 참조 설명서는 <xref:System.Runtime.InteropServices>를 참조하세요.  
  
## <a name="systemreflection-namespace"></a>System.Reflection 네임스페이스  
 <xref:System.Reflection> 네임스페이스에는 .NET Framework의 리플렉션에 사용되는 핵심 형식이 포함되어 있습니다. [!INCLUDE[net_native](../../../includes/net-native-md.md)]의 경우에는 두 가지 새 예외 형식도 포함됩니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|[MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)|리플렉션을 사용하여 존재하지 않는 메타데이터를 검색하면 throw되는 예외입니다.|  
|[MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)|형식 또는 형식 멤버의 메타데이터를 사용할 수는 있지만 해당 구현이 제거된 경우 throw되는 예외입니다.|  
  
 이 네임스페이스의 다른 형식에 대한 설명서는 .NET Framework 설명서 집합에서 <xref:System.Reflection> 를 참조하세요.  
  
## <a name="systemruntimecompilerservices-namespace"></a>System.Runtime.CompilerServices 네임스페이스  
 <xref:System.Runtime.CompilerServices> 네임스페이스는 언어 컴파일러에서 사용자용으로 디자인된 형식을 포함합니다. [!INCLUDE[net_native](../../../includes/net-native-md.md)]의 경우에는 새 예외 형식도 포함됩니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|[MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)|수동 마샬링 메서드를 호출했는데 정적 분석 또는 런타임 지시문 파일에서 형식의 메타데이터를 찾을 수 없을 때 throw되는 예외입니다.|  
  
 이 네임스페이스의 다른 형식에 대한 설명서는 .NET Framework 설명서 집합에서 <xref:System.Runtime.CompilerServices> 를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [MissingInteropDataException 클래스](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)  
 [MissingMetadataException 클래스](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)  
 [MissingRuntimeArtifactException 클래스](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)  
 [시작](../../../docs/framework/net-native/getting-started-with-net-native.md)
