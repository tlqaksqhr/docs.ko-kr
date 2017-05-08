---
title: "방법: 전역 어셈블리 캐시의 내용 보기 | Microsoft Docs"
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
  - "GAC(전역 어셈블리 캐시), 내용 보기"
  - "Gacutil.exe"
  - "전역 어셈블리 캐시 도구"
  - "전역 어셈블리 캐시, 내용 보기"
  - "전역 어셈블리 캐시의 어셈블리 목록"
  - "강력한 이름의 어셈블리, 전역 어셈블리 캐시"
  - "전역 어셈블리 캐시의 어셈블리 보기"
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 전역 어셈블리 캐시의 내용 보기
[전역 어셈블리 캐시 도구\(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 사용하면 전역 어셈블리캐시의 콘텐츠를 볼 수 있습니다.  
  
### 전역 어셈블리 캐시에서 어셈블리 목록을 보려면  
  
1.  [Visual Studio 명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)에 다음 명령을 입력합니다.  
  
     **gacutil \-l**   
     또는               
     **gacutil \/l**  
  
 이전 버전의 .NET Framework에서는 [Shfusion.dll](http://msdn.microsoft.com/ko-kr/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows 셸 확장을 통해 파일 탐색기에서 전역 어셈블리 캐시를 볼 수 있었습니다.  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 Shfusion.dll이 사용되지 않습니다.  
  
## 참고 항목  
 [어셈블리 및 전역 어셈블리 캐시 사용](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe\(전역 어셈블리 캐시 도구\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)