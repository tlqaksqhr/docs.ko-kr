---
title: "방법: 게시자 정책 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "GAC(전역 어셈블리 캐시), 게시자 정책 어셈블리"
  - "전역 어셈블리 캐시, 게시자 정책 어셈블리"
  - "게시자 정책 어셈블리"
  - "게시자 정책 파일"
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# 방법: 게시자 정책 만들기
어셈블리 공급업체는 응용 프로그램에서 새 버전의 어셈블리를 사용해야 한다고 규정할 수 있습니다. 이를 위해 공급업체는 업그레이드된 어셈블리를 게시자 정책 파일과 함께 제공합니다.  게시자 정책 파일은 어셈블리 리디렉션 및 코드 베이스 설정을 지정하며 응용 프로그램 구성 파일과 같은 형식을 사용합니다.  게시자 정책 파일은 어셈블리로 컴파일되며 전역 어셈블리 캐시에 추가됩니다.  
  
 게시자 정책을 만들 때는 다음 세 단계를 거칩니다.  
  
1.  게시자 정책 파일을 만듭니다.  
  
2.  게시자 정책 어셈블리를 만듭니다.  
  
3.  게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가합니다.  
  
 게시자 정책에 대한 스키마는 [어셈블리 버전 리디렉션](../../../docs/framework/configure-apps/redirect-assembly-versions.md)에서 설명합니다.  다음 예제에서는 `myAssembly` 버전을 다른 버전으로 리디렉션하는 게시자 정책 파일을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 코드 베이스를 지정하는 방법에 대해서는 [어셈블리 위치 지정](../../../docs/framework/configure-apps/specify-assembly-location.md)을 참조하십시오.  
  
## 게시자 정책 어셈블리 만들기  
 [어셈블리 링커\(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 게시자 정책 어셈블리를 만듭니다.  
  
#### 게시자 정책 어셈블리를 만들려면  
  
1.  명령 프롬프트에서 다음 명령을 입력합니다.  
  
     **al \/link:** *publisherPolicyFile* **\/out:** *publisherPolicyAssemblyFile* **\/keyfile:** *keyPairFile* **\/platform:** *processorArchitecture*  
  
     이 명령에서  
  
    -   *publisherPolicyFile* 인수는 게시자 정책 파일 이름입니다.  
  
    -   *publisherPolicyAssemblyFile* 인수는 이 명령으로 생성된 게시자 정책 어셈블리의 이름입니다.  어셈블리 파일 이름은 다음 형식이어야 합니다.  
  
         **policy.** *majorNumber* **.** *minorNumber* **.** *mainAssemblyName* **.dll**  
  
    -   *keyPairFile* 인수는 키 쌍이 포함된 파일 이름입니다.  어셈블리와 게시자 정책 어셈블리에 같은 키 쌍으로 서명해야 합니다.  
  
    -   *processorArchitecture* 인수는 프로세서별 어셈블리의 대상이 되는 플랫폼을 식별합니다.  
  
        > [!NOTE]
        >  특정 프로세서 아키텍처를 대상으로 하는 기능은 .NET Framework 버전 2.0의 새로운 기능입니다.  
  
     다음 명령은 `pub.config` 게시자 정책 파일에서 `policy.1.0.myAssembly`라는 게시자 정책 어셈블리를 만들고, `sgKey.snk` 파일의 키 쌍을 사용하여 어셈블리에 강력한 이름을 지정하며, 어셈블리가 x86 프로세서 아키텍처를 대상으로 하도록 지정합니다.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     게시자 정책 어셈블리는 해당 어셈블리가 적용되는 어셈블리의 프로세서 아키텍처와 일치해야 합니다.  따라서 어셈블리의 <xref:System.Reflection.ProcessorArchitecture> 값이 <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A>이면 해당 어셈블리의 게시자 정책 어셈블리는 `/platform:anycpu`을 사용하여 만들어야 합니다.  각 프로세서별 어셈블리에 대해 별도의 게시자 정책 어셈블리를 제공해야 합니다.  
  
     따라서 어셈블리에 대한 프로세서 아키텍처를 변경하려면 버전 번호의 주 버전 또는 부 버전 구성 요소를 변경해야 올바른 프로세서 아키텍처가 포함된 새 게시자 정책 어셈블리를 제공할 수 있습니다.  이전 게시자 정책 어셈블리는 어셈블리에 다른 프로세서 아키텍처가 있으면 해당 어셈블리를 서비스할 수 없습니다.  
  
     또한 버전 2.0 링커는 항상 프로세서 아키텍처를 지정하므로 이전 버전의 .NET Framework를 사용하여 컴파일된 어셈블리의 게시자 정책 어셈블리를 만드는 데 사용할 수 없습니다.  
  
## 전역 어셈블리 캐시에 게시자 정책 어셈블리 추가  
 [전역 어셈블리 캐시 도구\(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 사용하면 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가할 수 있습니다.  
  
#### 게시자 정책 어셈블리를 전역 어셈블리 캐시에 추가하려면  
  
1.  명령 프롬프트에서 다음 명령을 입력합니다.  
  
     **gacutil \/i**  *publisherPolicyAssemblyFile*  
  
     다음 명령은 `policy.1.0.myAssembly.dll`을 전역 어셈블리 캐시에 추가합니다.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  게시자 정책 어셈블리는 원래 게시자 정책 파일이 해당 어셈블리와 동일한 디렉터리에 있어야만 전역 어셈블리 캐시에 추가할 수 있습니다.  
  
## 참고 항목  
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [응용 프로그램 구성](../../../docs/framework/configure-apps/index.md)   
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/ko-kr/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)   
 [런타임 설정 스키마](../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)   
 [어셈블리 버전 리디렉션](../../../docs/framework/configure-apps/redirect-assembly-versions.md)