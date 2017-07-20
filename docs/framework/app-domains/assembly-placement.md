---
title: "어셈블리 배치 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5152d639c34a128c1c0625d9ae2ba12bc4fa7f9d
ms.contentlocale: ko-kr
ms.lasthandoff: 06/02/2017

---
# <a name="assembly-placement"></a>어셈블리 배치
대부분의 .NET Framework 응용 프로그램의 경우 해당 응용 프로그램을 구성하는 어셈블리는 응용 프로그램 디렉터리, 응용 프로그램 디렉터리의 하위 디렉터리 또는 전역 어셈블리 캐시(어셈블리가 공유된 경우)에서 찾을 수 있습니다. 구성 파일에 있는 [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하면 공용 언어 런타임에서 어셈블리를 검색하는 위치를 재정의할 수 있습니다. 어셈블리에 강력한 이름이 없는 경우, [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 지정한 위치는 응용 프로그램 디렉터리와 그 하위 디렉터리로 제한됩니다. 반면, 강력한 이름의 어셈블리인 경우에는 [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 컴퓨터 또는 네트워크상의 모든 위치를 지정할 수 있습니다.  
  
 비관리 코드나 COM interop 응용 프로그램에 대해 어셈블리의 위치를 검색할 때도 이와 비슷한 규칙이 적용됩니다. 여러 응용 프로그램에서 해당 어셈블리를 공유해야 하는 경우에는 어셈블리는 전역 어셈블리 캐시에 설치해야 합니다. 비관리 코드에 사용되는 어셈블리는 형식 라이브러리로 내보낸 후 등록해야 합니다. COM interop에 사용되는 어셈블리는 카달로그에 등록해야 하는데, 경우에 따라서는 어셈블리가 자동으로 등록됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [앱 구성](../../../docs/framework/configure-apps/index.md)   
 [고급 COM 상호 운용성](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [공용 언어 런타임의 어셈블리](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
