---
title: "완화: 제품 버전 관리 | Microsoft 문서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a6bf9656dee0e6074a8341997abb0e73dc3666f5
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-product-versioning"></a>완화: 제품 버전 관리
[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 및 이상에서, 제품 버전 관리가 .NET Framework(.NET Framework 4, 4.5, 4.5.1 및 4.5.2)의 이전 릴리스에서 변경되었습니다.  
  
## <a name="product-versioning-changes"></a>제품 버전 관리 변경 내용  
 자세한 변경 내용은 다음과 같습니다.  
  
-   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`키에서 `Version` 항목의 값은 .NET Framework 4.6 및 해당 포인트 릴리스에 대해 `4.6.`*xxxxx*로, .NET Framework 4.7에 대해 `4.7.`*xxxxx*로 변경되었습니다. .NET Framework 4.5, 4.5.1 및 4.5.2에서는 `4.5.`*xxxxx* 형식이었습니다.  
  
-   .NET Framework 파일에 대한 파일 및 제품 버전 관리는 이전 버전 관리 체계의 `4.0.30319.x`에서 .NET Framework 4.6 및 해당 포인트 릴리스에 대해 `4.6.X.0`로, .NET Framework 4.7 및 해당 포인트에 대해 `4.7.X.0`로 변경되었습니다. 파일을 마우스 오른쪽 단추로 클릭한 후 파일의 **속성**을 보면 이러한 새 값을 확인할 수 있습니다.  
  
-   관리되는 어셈블리에 대한 <xref:System.Reflection.AssemblyFileVersionAttribute> 및 <xref:System.Reflection.AssemblyInformationalVersionAttribute> 특성은 .NET Framework 4.6 및 해당 포인트 릴리스에 대해 `4.6.X.0`, .NET Framework 4.7에 대해 `4.7.X.0` 형식의 <xref:System.Version> 값을 갖습니다.  
  
-   [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2 및 4.7에서 <xref:System.Environment.Version%2A?displayProperty=fullName> 속성은 고정된 버전 문자열 `4.0.30319.42000`을 반환합니다. .NET Framework 4, 4.5, 4.5.1 및 4.5.2에서는 버전 문자열을 `4.0.30319.xxxxx` 형식(예: "4.0.30319.18010")으로 반환합니다. <xref:System.Environment.Version%2A?displayProperty=fullName> 속성에 새 종속성을 수행하는 응용 프로그램 코드는 권장하지 않습니다.  
  
### <a name="handling-the-product-versioning-changes"></a>제품 버전 관리 변경 내용 처리  
 일반적으로 응용 프로그램은 .NET Framework 및 설치 디렉터리 검색의 런타임 버전과 같은 항목 검색을 위한 권장 기술에 의존해야 합니다.  
  
-   .NET Framework의 런타임 버전을 검색하려면 [방법: 설치된 .NET Framework 버전 확인](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)을 참조합니다.  
  
-   .NET Framework의 설치 경로를 확인하려면`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` 키의 `InstallPath` 항목 값을 사용합니다.  
  
    > [!IMPORTANT]
    >  하위 키 이름은 `.NET Framework Setup`이 아니라 `NET Framework Setup`입니다.  
  
-   .NET Framework 공용 언어 런타임으로 디렉토리 경로를 확인하려면 <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=fullName> 메서드를 호출합니다.  
  
-   CLR 버전을 얻으려면 <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=fullName> 메서드를 호출합니다.   .NET Framework 4 및 해당 포인트 릴리스(.NET Framework 4.5, 4.5.1, 4.5.2, [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2 및 4.7)에 대해 `v4.0.30319` 문자열을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [런타임 변경 내용](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
 
