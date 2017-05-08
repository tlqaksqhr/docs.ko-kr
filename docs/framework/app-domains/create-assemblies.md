---
title: "어셈블리 만들기 | Microsoft Docs"
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
  - "어셈블리[.NET Framework], 만들기"
  - "어셈블리[.NET Framework], 다중 파일"
  - "다중 파일 어셈블리"
  - "단일 파일 어셈블리"
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 어셈블리 만들기
[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]와 같은 IDE나 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서 제공하는 컴파일러 및 도구를 사용하여 단일 파일 또는 다중 파일 어셈블리를 만들 수 있습니다.  가장 단순한 어셈블리인 단일 파일 어셈블리는 그 이름이 단순하며 단일 응용 프로그램 도메인에 로드됩니다.  이 어셈블리는 응용 프로그램 디렉터리 외부의 다른 어셈블리에서 참조할 수 없으며 버전 검사도 실행되지 않습니다.  이 어셈블리로 구성된 응용 프로그램을 제거하려면 어셈블리가 들어 있는 디렉터리를 삭제하면 됩니다.  대부분의 개발자는 이 기능을 사용한 어셈블리만으로 응용 프로그램을 배포할 수 있습니다.  
  
 여러 개의 코드 모듈과 리소스 파일을 사용하여 다중 파일 어셈블리를 만들 수 있습니다.  또한, 여러 응용 프로그램에서 공유할 수 있는 어셈블리도 만들 수 있습니다.  공유 어셈블리는 강력한 이름을 사용해야 하며 전역 어셈블리 캐시에서 배포될 수 있습니다.  
  
 코드 모듈과 리소스를 어셈블리로 그룹화하는 경우, 다음과 같은 요소에 따라 여러 가지 옵션이 있습니다.  
  
-   버전 관리  
  
     버전 정보가 동일한 모듈로 그룹화합니다.  
  
-   배포  
  
     사용자 배포 모델을 지원하는 코드 모듈 및 리소스로 그룹화합니다.  
  
-   다시 사용  
  
     특정 용도를 위해 논리적으로 함께 사용할 수 있는 모듈로 그룹화합니다.  예를 들어, 프로그램 관리에 가끔씩 사용되는 형식과 클래스로 구성된 어셈블리는 동일 어셈블리에 저장될 수 있습니다.  또한, 여러 개의 응용 프로그램에서 공유하려는 형식도 어셈블리로 그룹화되어야 하며, 이 때 어셈블리는 강력한 이름으로 서명되어야 합니다.  
  
-   보안  
  
     동일 보안 권한을 필요로 하는 형식이 포함된 모듈로 그룹화합니다.  
  
-   범위 지정  
  
     표시 형식을 동일 어셈블리로 제한해야 하는 형식이 포함된 모듈로 그룹화합니다.  
  
 관리되지 않는 COM 응용 프로그램에서 공용 언어 런타임 어셈블리을 사용하기 위해서는 특수한 사항을 고려해야 합니다.  비관리 코드 작업에 대한 자세한 내용은 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)을 참조하십시오.  
  
## 참고 항목  
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [어셈블리 버전 관리](../../../docs/framework/app-domains/assembly-versioning.md)   
 [방법: 단일 파일 어셈블리 만들기](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)   
 [방법: 다중 파일 어셈블리 빌드](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [다중 파일 어셈블리](../../../docs/framework/app-domains/multifile-assemblies.md)