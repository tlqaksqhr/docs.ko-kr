---
title: "어셈블리 및 전역 어셈블리 캐시 사용 | Microsoft Docs"
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
  - "액세스 제어 목록[.NET Framework]"
  - "ACL[.NET Framework]"
  - "어셈블리[.NET Framework], 전역 어셈블리 캐시"
  - "GAC(전역 어셈블리 캐시), 장점"
  - "전역 어셈블리 캐시, 장점"
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 어셈블리 및 전역 어셈블리 캐시 사용
여러 응용 프로그램에서 어셈블리를 공유하려는 경우, 이 어셈블리를 전역 어셈블리 캐시에 설치하면 됩니다.  공용 언어 런타임이 설치된 각 컴퓨터에는 이 컴퓨터 수준의 코드 캐시가 존재하게 됩니다.  전역 어셈블리 캐시에는 컴퓨터의 여러 응용 프로그램에서 공유되도록 특별히 지정된 어셈블리가 저장됩니다.  어셈블리의 강력한 이름은 전역 어셈블리 캐시에 설치되어 있어야 합니다.  
  
> [!NOTE]
>  전역 어셈블리 캐시에 저장된 어셈블리의 어셈블리 이름과 파일 이름은 같아야 합니다. 하지만 파일 확장명은 같지 않아도 됩니다.  예를 들어, 어셈블리 이름이 myAssembly인 어셈블리의 파일 이름은 myAssembly.exe 또는 myAssembly.dll이 되어야 합니다.  
  
 꼭 필요한 경우에만 어셈블리를 전역 어셈블리 캐시에 설치하여 공유해야 합니다.  어셈블리 공유가 명시적으로 필요하지 않은 경우, 어셈블리 종속성을 전용으로 유지하고 응용 프로그램 디렉터리에서 어셈블리를 찾는 것이 일반적인 지침입니다.  또한, 어셈블리를 COM interop나 비관리 코드에서 사용하기 위해 이 어셈블리를 전역 어셈블리 캐시에 설치할 필요가 없습니다.  
  
 어셈블리를 전역 어셈블리 캐시에 설치해야 하는 이유는 다음과 같습니다.  
  
-   위치 공유  
  
     응용 프로그램에서 사용되는 어셈블리를 전역 어셈블리 캐시에 저장할 수 있습니다.  예를 들어, 전역 어셈블리 캐시에 저장된 어셈블리를 모든 응용 프로그램에서 사용해야 하는 경우, Machine.config 파일에 버전 정책 문을 추가할 수 있습니다. 이 파일은 참조를 어셈블리로 리디렉션합니다.  
  
-   파일 보안  
  
     관리자는 systemroot 디렉터리를 보호하기 위해 ACL\(액세스 제어 목록\)을 사용하여 쓰기 및 실행 권한을 제어합니다.  전역 어셈블리 캐시는 systemroot 디렉터리에 설치되므로, 이 캐시는 systemroot 디렉터리의 ACL을 상속합니다.  관리자 권한을 보유한 사용자만이 전역 어셈블리 캐시에서 파일을 삭제하도록 허용하는 것이 좋습니다.  
  
-   Side\-by\-side 버전 관리  
  
     전역 어셈블리 캐시에서는 이름은 동일하지만 버전 정보가 다른 여러 개의 어셈블리 복사본을 관리할 수 있습니다.  
  
-   추가 검색 위치  
  
     공용 언어 런타임은 구성 파일에서 코드베이스 정보를 검색하거나 사용하기 전에, 요청된 어셈블리와 일치하는 어셈블리가 전역 어셈블리 캐시에 있는지를 검사합니다.  
  
 전역 어셈블리 캐시에 어셈블리를 명시적으로 설치하지 않으려는 경우를 생각해 보겠습니다.  응용 프로그램을 구성하는 어셈블리 중 하나를 전역 어셈블리 캐시에 저장하는 경우, 응용 프로그램 디렉터리를 복사하여 응용 프로그램을 복제하거나 설치하는 데 XCOPY를 사용할 필요가 없습니다.  이 경우 어셈블리를 전역 어셈블리 캐시로 옮겨야 합니다.  
  
## 단원 내용  
 [방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 어셈블리를 전역 어셈블리 캐시에 설치하는 네 가지 방법을 설명합니다.  
  
 [방법: 전역 어셈블리 캐시의 내용 보기](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)  
 [Gacutil.exe\(전역 어셈블리 캐시 도구\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 사용하여 전역 어셈블리 캐시의 내용을 보는 방법을 설명합니다.  
  
 [방법: 전역 어셈블리 캐시에서 어셈블리 제거](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 [Gacutil.exe\(전역 어셈블리 캐시 도구\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 사용하여 전역 어셈블리 캐시에서 어셈블리를 제거하는 방법을 설명합니다.  
  
 [전역 어셈블리 캐시에서 서비스되는 구성 요소 사용](../../../docs/framework/app-domains/use-serviced-components-with-the-gac.md)  
 서비스 구성 요소\(관리되는 COM\+ 구성 요소\)가 전역 어셈블리 캐시에 저장되어야 하는 이유를 설명합니다.  
  
## 관련 단원  
 [어셈블리 만들기](../../../docs/framework/app-domains/create-assemblies.md)  
 어셈블리를 만드는 방법을 간략하게 설명합니다.  
  
 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)  
 전역 어셈블리 캐시를 설명합니다.  
  
 [방법: 어셈블리 내용 보기](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 [Ildasm.exe\(IL 디스어셈블러\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 어셈블리에 있는 MSIL\(Microsoft Intermediate Language\) 정보를 보는 방법을 설명합니다.  
  
 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 공용 언어 런타임에서 응용 프로그램을 구성하는 어셈블리를 찾아 로드하는 방법을 설명합니다.  
  
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 관리되는 응용 프로그램의 빌딩 블록인 어셈블리를 설명합니다.