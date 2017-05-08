---
title: "&lt;runtime&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<runtime> 요소"
  - "컨테이너 태그, <runtime> 요소"
  - "runtime 요소"
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
caps.latest.revision: 70
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 62
---
# &lt;runtime&gt; 요소
어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.  
  
## 구문  
  
```  
<runtime>  
</runtime>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<alwaysFlowImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)|가장이 수행된 방법에 관계없이 Windows ID가 항상 비동기 지점 간에 전달되도록 지정합니다.|  
|[\<appDomainManagerAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)|프로세스의 기본 응용 프로그램 도메인에 대한 응용 프로그램 도메인 관리자를 제공하는 어셈블리를 지정합니다.|  
|[\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)|기본 응용 프로그램 도메인의 응용 프로그램 도메인 관리자 역할을 하는 형식을 지정합니다.|  
|[\<appDomainResourceMonitoring\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)|프로세스의 수명 동안 프로세스의 모든 응용 프로그램 도메인에 대한 통계를 수집하도록 런타임에 지시합니다.|  
|[\<assemblyBinding\>](../../../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md)|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
|[\<bypassTrustedAppStrongNames\>](../../../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)|신뢰할 수 있는 어셈블리에 대한 강력한 이름 확인을 건너뛸지 여부를 지정합니다.|  
|[\<CompatSortNLSVersion\>](../../../../../docs/framework/configure-apps/file-schema/runtime/compatsortnlsversion-element.md)|문자열 비교를 수행할 때 런타임에서 레거시 정렬 동작을 사용하도록 지정합니다.|  
|[\<developmentMode\>](../../../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md)|런타임에서, DEVPATH 환경 변수에 지정된 디렉터리에서 어셈블리를 찾는지 여부를 지정합니다.|  
|[\<disableCachingBindingFailures\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecachingbindingfailures-element.md)|.NET Framework 버전 2.0의 기본 동작인 바인딩 실패 캐싱 기능을 사용하지 않을지 여부를 지정합니다.|  
|[\<disableCommitThreadStack\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablecommitthreadstack-element.md)|스레드를 시작할 때 전체 스레드 스택을 커밋할지 여부를 지정합니다.|  
|[\<disableFusionUpdatesFromADManager\>](../../../../../docs/framework/configure-apps/file-schema/runtime/disablefusionupdatesfromadmanager-element.md)|런타임 호스트에서 응용 프로그램 도메인에 대한 구성 설정을 재정의할 수 있도록 허용하는 기본 동작을 해제할지 여부를 지정합니다.|  
|[\<enforceFIPSPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/enforcefipspolicy-element.md)|암호화 알고리즘이 FIPS\(Federal Information Processing Standard\)를 준수해야 하는 컴퓨터 구성 요구 사항에 대해 이를 적용할지 여부를 지정합니다.|  
|[\<etwEnable\>](../../../../../docs/framework/configure-apps/file-schema/runtime/etwenable-element.md)|공용 언어 런타임 이벤트에 대한 이벤트 추적을 위해 Windows\(ETW\)를 사용할지 여부를 지정합니다.|  
|[\<forcePerformanceCounterUniqueSharedMemoryReads\>](../../../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md)|특정 범주의 공유 메모리 또는 전역 메모리에서 성능 카운터 데이터를 로드할 것인지 결정하는 데 PerfCounter.dll이 .NET Framework 버전 1.1 응용 프로그램의 CategoryOptions 레지스트리 설정을 사용할지 여부를 지정합니다.|  
|[\<gcAllowVeryLargeObjects\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md)|64 비트 플랫폼에서, 전체 크기가 2기가바이트 \(GB\) 보다 큰 배열을 지원합니다.|  
|[\<gcConcurrent\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)|공용 언어 런타임에서 가비지 수집을 동시에 실행하는지 여부를 지정합니다.|  
|[\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)|가비지 수집이 여러 CPU 그룹을 지원하는지 여부를 지정합니다.|  
|[\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)|공용 언어 런타임에서 서버 가비지 수집을 실행하는지 여부를 지정합니다.|  
|[\<generatePublisherEvidence\>](../../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)|런타임에서 CAS\(코드 액세스 보안\) 게시자 정책을 사용하는지 여부를 지정합니다.|  
|[\<legacyCorruptedStateExceptionsPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)|런타임에서 관리 코드를 사용하여 액세스 위반과 기타 손상된 상태 예외를 catch할 수 있는지 여부를 지정합니다.|  
|[\<legacyImpersonationPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)|현재 스레드의 실행 컨텍스트에 대한 흐름 설정에 관계없이 Windows ID가 비동기 지점 간에 전달되지 않도록 지정합니다.|  
|[\<loadFromRemoteSources\>](../../../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md)|원격 소스의 어셈블리가 완전 신뢰로 로드되는지 여부를 지정합니다.|  
|[\<NetFx40\_LegacySecurityPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)|런타임에서 레거시 CAS\(코드 액세스 보안\) 정책을 사용하는지 여부를 지정합니다.|  
|[\<NetFx40\_PInvokeStackResilience\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx40-pinvokestackresilience-element.md)|프로그램 관리 및 비관리 코드 사이의 느린 전환 비용으로 런타임에 잘못된 플랫폼 호출 선언을 자동으로 해결할지 여부를 지정합니다.|  
|[\<NetFx45\_CultureAwareComparerGetHashCode\_LongStrings\>](../../../../../docs/framework/configure-apps/file-schema/runtime/netfx45-cultureawarecomparergethashcode-longstrings-element.md)|런타임이 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName> 방법을 위한 해시 코드를 계산하기 위해 고정된 크기의 메모리를 사용할 지 여부를 지정합니다.|  
|[\<PreferComInsteadOfRemoting\>](../../../../../docs/framework/configure-apps/file-schema/runtime/prefercominsteadofmanagedremoting-element.md)|런타임이 응용 프로그램 도메인 경계에서 원격 서비스 대신 COM interop를 사용하도록 지정합니다.|  
|[\<relativeBindForResources\>](../../../../../docs/framework/configure-apps/file-schema/runtime/relativebindforresources-element.md)|위성 어셈블리의 프로브를 최적화합니다.|  
|[\<shadowCopyVerifyByTimeStamp\>](../../../../../docs/framework/configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)|섀도 복사가 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]에 도입된 기본 시작 동작을 사용하거나 .NET Framework의 이전 버전의 시작 동작으로 되돌릴지 여부를 지정합니다.|  
|[\<supportPortability\>](../../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md)|응용 프로그램 이식성을 위해 어셈블리를 같은 것으로 간주하는 기본 동작을 비활성화하여 응용 프로그램이 .NET Framework의 두 가지 다른 구현에 있는 같은 어셈블리를 참조할 수 있도록 지정합니다.|  
|[\<system.runtime.caching\>](../../../../../docs/framework/configure-apps/file-schema/runtime/system-runtime-caching-element-cache-settings.md)|기본 메모리 내 개체 캐시에 대한 구성 정보를 제공합니다.|  
|[\<Thread\_UseAllCpuGroups\>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md)|런타임이 모든 CPU 그룹에서 관리되는 스레드를 분포하는지 여부를 지정합니다.|  
|[\<ThrowUnobservedTaskExceptions\>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)|작업이 처리 되지 않은 예외에서 실행 중인 프로세스를 종료 해야 하는지 여부를 지정 합니다.|  
|[\<TimeSpan\_LegacyFormatMode\>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)|런타임이 <xref:System.TimeSpan> 값의 레거시 서식 지정을 사용할지 여부를 지정합니다.|  
|[\<UseRandomizedStringHashAlgorithm\>](../../../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md)|런타임이 응용 프로그램 도메인별로 문자열에 대한 해시 코드를 계산할지 여부를 지정합니다.|  
|[\<UseSmallInternalThreadStacks\>](../../../../../docs/framework/configure-apps/file-schema/runtime/usesmallinternalthreadstacks-element.md)|런타임이 내부적으로 사용하는 특정 스레드를 만들 때 기본 스택 크기 대신 명시적 스택 크기를 사용할 것을 요청합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## 설명  
 .NET Framework 버전 2.0에서는 가장된 ID가 응용 프로그램 도메인 내의 비동기 지점 간에 전달되며,  machine.config 파일이나 응용 프로그램 구성 파일에서 런타임 요소를 올바르게 구성하면 이러한 비동기 지점 간의 가장 전달을 사용하거나 사용하지 않도록 설정할 수 있습니다.  ASP.NET의 경우, \<Windows Folder\>\\Microsoft.NET\\Framework\\vx.x.xxxx 디렉터리에 있는 aspnet.config 파일에서 가장 전달을 구성할 수 있습니다.  
  
 기본적으로 ASP.NET에서는 aspnet.config 파일에서 다음 구성 설정을 사용하여 가장 전달을 사용하지 않도록 설정합니다.  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 ASP.NET에서 가장 전달을 허용하려면 다음 구성 설정을 명시적으로 사용해야 합니다.  
  
```  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
 자세한 내용은 [\<legacyImpersonationPolicy\> 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) 및 [\<alwaysFlowImpersonationPolicy\> 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 어셈블리 버전을 다른 버전으로 리디렉션하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
             <bindingRedirect oldVersion="1.0.0.0"  
                              newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [어셈블리 버전 리디렉션](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/ko-kr/ba2c6c67-5778-497c-9fac-5f793b5500c7)