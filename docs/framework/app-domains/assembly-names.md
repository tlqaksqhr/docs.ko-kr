---
title: "어셈블리 이름 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "어셈블리[.NET Framework], 이름"
  - "이름[.NET Framework], 어셈블리"
ms.assetid: 8f8c2c90-f15d-400e-87e7-a757e4f04d0e
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# 어셈블리 이름
어셈블리 이름은 메타데이터에 저장되며 응용 프로그램별로 어셈블리의 범위와 용도에 큰 영향을 줍니다.  강력한 이름의 어셈블리에는 어셈블리 이름, 문화권, 공개 키 및 버전 번호가 포함된 정규화된 이름이 있습니다.  이를 흔히 표시 이름이라고 하여, 로드된 어셈블리의 경우 <xref:System.Reflection.Assembly.FullName%2A> 속성을 사용하여 얻을 수 있습니다.  
  
 런타임에서는 이 정보를 통해 어셈블리를 찾고 이름이 같은 다른 어셈블리와 구별합니다.  예를 들어, `myTypes`라는 강력한 이름의 어셈블리에 다음과 같은 정규화된 이름이 있을 수 있습니다.  
  
```  
myTypes, Version=1.0.1234.0, Culture=en-US, PublicKeyToken=b77a5c561934e089c, ProcessorArchitecture=msil  
```  
  
> [!NOTE]
>  .NET Framework 버전 2.0에서는 어셈블리 ID에 프로세서 아키텍처가 추가되었으므로 프로세서별 어셈블리 버전을 만들 수 있습니다.  32비트 및 64비트 프로세서별 버전과 같이 ID의 프로세서 아키텍처만 다른 여러 어셈블리 버전을 만들 수 있습니다.  프로세서 아키텍처에는 강력한 이름을 사용하지 않아도 됩니다.  자세한 내용은 <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=fullName>을 참조하십시오.  
  
 이 예제에서 정규화된 이름은 `myTypes` 어셈블리에 공개 키 토큰이 포함된 강력한 이름. 미국 영어에 대한 문화권 값 및 버전 번호 1.0.1234.0이 있다는 것을 나타냅니다.  프로세서 아키텍처는 "msil"로서, 해당 어셈블리가 운영 체제 및 프로세서에 따라 32비트 코드나 64비트 코드로 JIT\(Just\-In\-Time\) 컴파일됨을 나타냅니다.  
  
 어셈블리의 형식을 요청하는 코드의 경우에는 정규화된 어셈블리 이름을 사용해야 합니다.  이를 정규화된 바인딩이라고 합니다.  .NET Framework에서 어셈블리를 참조하는 경우에는 어셈블리 이름만 지정하는 부분 바인딩은 사용할 수 없습니다.  
  
 .NET Framework을 구성하는 어셈블리에 대한 모든 어셈블리 참조에도 해당 어셈블리의 정규화된 이름이 포함되어 있어야 합니다.  예를 들어, 버전 1.0에 대한 System.Data .NET Framework 어셈블리를 참조하려면 다음을 포함시켜야 합니다.  
  
```  
  
System.data, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
  
```  
  
 이 버전은 .NET Framework 1.0과 함께 제공된 모든 .NET Framework 어셈블리의 버전 번호에 해당합니다.  .NET Framework 어셈블리의 경우 문화권 값은 항상 neutral이며 공개 키는 이 예제에 표시된 것과 같습니다.  
  
 예를 들어, 구성 파일에 어셈블리 참조를 추가하여 추적 수신기를 설정하려면 시스템 .NET Framework 어셈블리의 정규화된 이름을 포함시켜야 합니다.  
  
```  
<add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
```  
  
> [!NOTE]
>  런타임에서는 어셈블리에 바인딩할 때 어셈블리 이름의 대\/소문자를 구분하지 않지만, 해당 대\/소문자가 그대로 유지됩니다.  그러나 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]의 일부 도구에서는 어셈블리 이름의 대\/소문자를 구분합니다.  어셈블리 이름은 대\/소문자가 구분하여 관리하는 것이 좋습니다.  
  
## 응용 프로그램 구성 요소 이름 지정  
 어셈블리 ID를 결정하는 경우 런타임에서는 파일 이름을 고려하지 않습니다.  어셈블리 이름, 버전, 문화권 및 강력한 이름으로 구성된 어셈블리 ID는 런타임에서 명확해야 합니다.  
  
 예를 들어 myAssembly.dll 이라는 어셈블리를 참조하는 myAssembly.exe라는 어셈블리가 있는 경우, myAssembly.exe를 실행하면 바인딩이 올바로 수행됩니다.  하지만 다른 응용 프로그램에서 메서드 <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=fullName>를 사용하여 myAssembly.exe를 실행하는 경우 myAssembly.exe에서 "myAssembly"에 바인딩을 요청하면 런타임에서는 "myAssembly"가 이미 로드된 것으로 결정합니다. 이 경우 myAssembly.dll은 로드되지 않을 것입니다.  myAssembly.exe에는 요청된 형식이 들어있지 않으므로 <xref:System.TypeLoadException>이 발생합니다.  
  
 이 문제를 방지하려면 응용 프로그램을 구성하는 어셈블리의 이름을 서로 다르게 지정하거나 이름이 동일한 어셈블리를 다른 디렉터리에 저장합니다.  
  
> [!NOTE]
>  전역 어셈블리 캐시에 강력한 이름의 어셈블리를 배치하는 경우 어셈블리의 파일 이름은 어셈블리 이름\(.exe 또는 .dll과 같은 확장명은 제외\)과 일치해야 합니다.  예를 들어, 어셈블리 파일 이름이 myAssembly.dll인 경우 어셈블리 이름은 myAssembly가 되어야 합니다.  루트 응용 프로그램 디렉터리에만 배포된 개인 어셈블리의 이름은 파일 이름과 달라도 됩니다.  
  
## 참고 항목  
 [방법: 어셈블리의 정규화된 이름 식별](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)   
 [어셈블리 만들기](../../../docs/framework/app-domains/create-assemblies.md)   
 [강력한 이름의 어셈블리](../../../docs/framework/app-domains/strong-named-assemblies.md)   
 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)