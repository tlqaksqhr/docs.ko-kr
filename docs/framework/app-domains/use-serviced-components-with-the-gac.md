---
title: "전역 어셈블리 캐시에서 서비스되는 구성 요소 사용 | Microsoft Docs"
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
  - "어셈블리[.NET Framework], 전역 어셈블리 캐시"
  - "GAC(전역 어셈블리 캐시), 서비스 구성 요소"
  - "전역 어셈블리 캐시, 서비스 구성 요소"
  - "서비스 구성 요소, 전역 어셈블리 캐시"
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 전역 어셈블리 캐시에서 서비스되는 구성 요소 사용
서비스되는 구성 요소\(관리 코드 COM\+ 구성 요소\)는 전역 어셈블리 캐시에 저장되어야 합니다.  일부 시나리오에서는 공용 언어 런타임과 COM\+ 서비스가 전역 어셈블리 캐시에 없는 서비스되는 구성 요소를 처리할 수 있지만 다른 시나리오에서는 처리할 수 없습니다.  다음 시나리오는 이러한 예에 대해 설명합니다.  
  
-   COM\+ 서버 응용 프로그램에 있는 서비스되는 구성 요소의 경우, 이 구성 요소가 포함된 어셈블리는 전역 어셈블리 캐시에 존재해야 합니다. 왜냐하면, Dllhost.exe는 서비스되는 구성 요소가 포함된 디렉터리와 동일한 디렉터리에서 실행할 수 없기 때문입니다.  
  
-   COM\+ 라이브러리 응용 프로그램에 있는 서비스되는 구성 요소의 경우, 런타임과 COM\+ 서비스에서 현재 디렉터리를 검색하여 구성 요소가 포함된 어셈블리의 참조를 확인할 수 있습니다.  이 경우 어셈블리가 전역 어셈블리 캐시에 존재할 필요가 없습니다.  
  
-   ASP.NET 응용 프로그램에 있는 서비스되는 구성 요소의 경우는 상황이 다릅니다.  서비스되는 구성 요소가 포함된 어셈블리를 응용 프로그램 기본 디렉터리의 bin 디렉터리에 저장하고 요청 시 등록하는 기능을 사용하는 경우, ASP.NET에서는 런타임의 섀도 기능을 사용하므로 해당 어셈블리가 다운로드 캐시로 섀도 복사됩니다.  
  
## 참고 항목  
 [How to: Create a Serviced Component](http://msdn.microsoft.com/ko-kr/7ec0b488-e5fc-46f2-a48d-1278ea4e301d)   
 [어셈블리 및 전역 어셈블리 캐시 사용](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe\(전역 어셈블리 캐시 도구\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)   
 [Assembly Cache Viewer \(Shfusion.dll\)](http://msdn.microsoft.com/ko-kr/0d9464cf-ddba-4ca9-bbec-f678fb58f380)