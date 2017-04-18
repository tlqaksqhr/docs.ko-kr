---
title: "전역 어셈블리 캐시 | Microsoft Docs"
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
  - "캐시[.NET Framework], 전역 어셈블리 캐시"
  - "GAC(전역 어셈블리 캐시)"
  - "전역 어셈블리 캐시"
  - "전역 어셈블리 캐시, 정보"
ms.assetid: cf5eacd0-d3ec-4879-b6da-5fd5e4372202
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 전역 어셈블리 캐시
공용 언어 런타임이 설치된 컴퓨터에는 전역 어셈블리 캐시라고 하는 컴퓨터 전체에서 사용되는 코드 캐시가 있습니다.  전역 어셈블리 캐시에는 컴퓨터의 여러 응용 프로그램에서 공유되도록 특별히 지정된 어셈블리가 저장됩니다.  
  
 꼭 필요한 경우, 어셈블리를 전역 어셈블리 캐시에 설치하여 어셈블리를 공유할 수 있습니다.  어셈블리 공유가 명시적으로 필요하지 않은 경우, 어셈블리 종속성을 전용으로 유지하고 응용 프로그램 디렉터리에서 어셈블리를 찾는 것이 일반적인 지침입니다.  또한, 어셈블리를 COM interop나 비관리 코드에서 사용하기 위해 이 어셈블리를 전역 어셈블리 캐시에 설치할 필요가 없습니다.  
  
> [!NOTE]
>  전역 어셈블리 캐시에 어셈블리를 명시적으로 설치하지 않고 싶을 경우도 있습니다.  응용 프로그램을 구성하는 어셈블리 중 하나를 전역 어셈블리 캐시에 저장하는 경우, 응용 프로그램 디렉터리를 복사하여 응용 프로그램을 복제하거나 설치하는 데 **xcopy** 명령을 사용할 필요가 없습니다.  결국에는 전역 어셈블리 캐시에 있는 해당 어셈블리를 다른 곳으로 옮겨야 합니다.  
  
 어셈블리를 전역 어셈블리 캐시에 배포하는 방법에는 두 가지가 있습니다.  
  
-   전역 어셈블리 캐시와 사용하도록 디자인된 설치 관리자를 사용합니다.  이것은 전역 어셈블리 캐시에 어셈블리를 설치할 때의 기본 옵션입니다.  
  
-   [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서 제공하는 [전역 어셈블리 캐시 도구\(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)라는 개발자 도구를 사용합니다.  
  
    > [!NOTE]
    >  배포 시나리오에서는 전역 어셈블리 캐시에 어셈블리를 설치할 때 Windows Installer 을 사용해야 합니다.  전역 어셈블리 캐시 도구를 사용했을 때는 Windows Installer를 사용했을 때 제공되는 어셈블리 참조 수 계산이나 기타 기능이 제공되지 않기 때문에, 이들 방법은 개발 시나리오에서만 사용해야 합니다.  
  
 .NET Framework 4 부터는, 전역 어셈블리 캐시를 위한 기본 위치는 **%windir%\\Microsoft.NET\\assembly** 입니다.  .NET Framework 이전 버전에서의 기본 위치는 **%windir%\\assembly** 입니다.  
  
 관리자는 systemroot 디렉터리를 보호하기 위해 ACL\(액세스 제어 목록\)을 사용하여 쓰기 및 실행 권한을 제어합니다.  전역 어셈블리 캐시는 systemroot 디렉터리의 하위 디렉터리에 설치되므로, 이 캐시는 systemroot 디렉터리의 ACL을 상속합니다.  관리자 권한을 보유한 사용자만이 전역 어셈블리 캐시에서 파일을 삭제하도록 허용하는 것이 좋습니다.  
  
 전역 어셈블리 캐시에 배포된 어셈블리에는 강력한 이름을 지정해야 합니다.  전역 어셈블리 캐시에 어셈블리를 추가하면 어셈블리를 구성하는 모든 파일에 대해 무결성 검사가 수행됩니다.  무결성 검사는 배포된 어셈블리가 훼손되었는지 여부\(예: 파일의 변경 내용이 매니페스트에 나타나지 않는 경우\)를 확인하기 위한 절차입니다.  
  
## 참고 항목  
 [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)   
 [어셈블리 및 전역 어셈블리 캐시 사용](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [강력한 이름의 어셈블리](../../../docs/framework/app-domains/strong-named-assemblies.md)