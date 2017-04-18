---
title: "Interop 응용 프로그램 배포 | Microsoft Docs"
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
  - "COM interop, 응용 프로그램 배포"
  - "COM interop, COM 구성 요소 게시"
  - "응용 프로그램 배포[.NET Framework], interop"
  - ".NET Framework에 COM 구성 요소 게시"
  - "비관리 코드와의 상호 운용, 응용 프로그램 배포"
  - "비관리 코드와의 상호 운용, COM 구성 요소 게시"
  - "전용 어셈블리"
  - "공유 어셈블리"
  - "서명된 어셈블리"
  - "강력한 이름의 어셈블리, interop 응용 프로그램"
  - "서명되지 않은 어셈블리"
ms.assetid: ea8a403e-ae03-4faa-9d9b-02179ec72992
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Interop 응용 프로그램 배포
Interop 응용 프로그램에는 일반적으로 .NET 클라이언트 어셈블리, COM 형식 라이브러리를 나타내는 하나 이상의 interop 어셈블리, 하나 이상의 등록된 COM 구성 요소 등이 포함됩니다.  Visual Studio 및 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]에서는 [형식 라이브러리를 어셈블리로 가져오기](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)에 설명된 대로 형식 라이브러리를 가져와 interop 어셈블리로 변환하는 도구를 제공합니다.  Interop 응용 프로그램은 두 가지 방법으로 배포할 수 있습니다.  
  
-   포함된 interop 형식 사용. [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 및 이후 버전에서는 interop 어셈블리의 형식 정보를 실행 파일에 포함하도록 컴파일러에 지시할 수 있습니다.  컴파일러는 응용 프로그램에서 사용하는 형식 정보만 포함합니다.  응용 프로그램과 함께 interop 어셈블리를 배포할 필요가 없습니다.  이것이 권장되는 방법입니다.  
  
-   interop 어셈블리 배포. interop 어셈블리에 대한 표준 참조를 만들 수 있습니다.  이 경우 interop 어셈블리가 응용 프로그램과 함께 배포되어야 합니다.  이 방법을 채택하고 전용 COM 구성 요소를 사용하지 않는 경우 관리 코드에 통합할 COM 구성 요소의 작성자가 게시한 PIA\(주 interop 어셈블리\)를 항상 참조합니다.  주 interop 어셈블리의 생성과 사용에 대한 자세한 내용은 [주 Interop 어셈블리](http://msdn.microsoft.com/ko-kr/b977a8be-59a0-40a0-a806-b11ffba5c080)를 참조하십시오.  
  
 포함된 interop 형식을 사용하면 간단하고 쉽게 배포할 수 있습니다.  이 경우 특별히 수행할 작업은 없습니다.  이 문서의 나머지 부분에서는 interop 어셈블리를 응용 프로그램과 함께 배포하는 시나리오에 대해 설명합니다.  
  
## Interop 어셈블리 배포  
 어셈블리에는 강력한 이름을 지정할 수 있는데  강력한 이름의 어셈블리에는 고유하게 식별되는 게시자의 공개 키가 포함됩니다.  게시자는 **\/keyfile** 옵션을 사용하여 [형식 라이브러리 가져오기\(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)로 생성된 어셈블리에 서명할 수 있습니다.  서명된 어셈블리는 전역 어셈블리 캐시에 설치될 수 있지만  서명되지 않은 어셈블리는 사용자의 컴퓨터에 전용 어셈블리로 설치되어야 합니다.  
  
### 전용 어셈블리  
 전용으로 사용될 어셈블리를 설치하려면 응용 프로그램 실행 파일 및 가져온 COM 형식이 포함된 interop 어셈블리를 동일한 디렉터리 구조에 설치해야 합니다.  다음 예제에서는 서로 다른 응용 프로그램 디렉터리에 위치하는Client1.exe와 Client2.exe에서 전용으로 사용될 서명되지 않은 interop 어셈블리를 보여 줍니다.  이 예제에서 LOANLib.dll이라는 interop 어셈블리는 두 번 설치됩니다.  
  
 ![디렉터리 구조 및 Windows 레지스트리](../../../docs/framework/interop/media/comdeployprivate.gif "comdeployprivate")  
전용 배포 시 디렉터리 구조 및 레지스트리 항목  
  
 응용 프로그램과 관련된 모든 COM 구성 요소는 Windows 레지스트리에 설치되어야 합니다.  예제의 Client1.exe와 Client2.exe는 서로 다른 컴퓨터에 설치되어 있기 때문에 COM 구성 요소를 두 컴퓨터에 모두 등록해야 합니다.  
  
### 공유 어셈블리  
 여러 응용 프로그램에서 공유하는 어셈블리는 전역 어셈블리 캐시라고 하는 중앙 리포지토리에 설치되어야 합니다.  이렇게 하면, .NET 클라이언트에서는 서명되고 전역 어셈블리 캐시에 설치된 interop 어셈블리의 동일한 복사본에 액세스할 수 있습니다.  주 interop 어셈블리의 생성과 사용에 대한 자세한 내용은 [주 Interop 어셈블리](http://msdn.microsoft.com/ko-kr/b977a8be-59a0-40a0-a806-b11ffba5c080)를 참조하십시오.  
  
## 참고 항목  
 [.NET Framework에 COM 구성 요소 노출](../../../docs/framework/interop/exposing-com-components.md)   
 [형식 라이브러리를 어셈블리로 가져오기](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/ko-kr/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Interop 프로젝트 컴파일](../../../docs/framework/interop/compiling-an-interop-project.md)