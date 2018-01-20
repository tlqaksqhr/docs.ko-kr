---
title: "방법: DEVPATH를 사용하여 어셈블리 찾기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0944f2798c45a039149baaa6e46ce2b56eb5c5df
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>방법: DEVPATH를 사용하여 어셈블리 찾기
개발자가 작성 하는 공유 어셈블리를 여러 응용 프로그램으로 제대로 작동 하는지 확인 수도 있습니다. 지속적으로 개발 주기 동안 어셈블리를 전역 어셈블리 캐시에 저장, 대신 개발자 어셈블리에 대 한 빌드 출력 디렉터리를 가리키는 DEVPATH 환경 변수를 만들 수 있습니다.  
  
 예를 들어 가정 MySharedAssembly를 호출 하는 공유 어셈블리를 작성 하는 출력 디렉터리는 C:\MySharedAssembly\Debug 합니다. C:\MySharedAssembly\Debug DEVPATH 변수에 넣을 수 있습니다. 그런 다음 지정 해야는 [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) 컴퓨터 구성 파일의 요소입니다. 이 요소에는 공용 언어 런타임 어셈블리를 찾는 DEVPATH를 사용 하도록 지시 합니다.  
  
 공유 어셈블리는 런타임에 검색 가능 해야 합니다.  어셈블리 참조 사용을 확인 하기 위한 전용 디렉터리를 지정 하는 [ \<s e > 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) 또는 [ \<조사 > 요소](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) 에 설명 된 대로 구성 파일에 [어셈블리의 위치 지정](../../../docs/framework/configure-apps/specify-assembly-location.md)합니다.  또한 응용 프로그램 디렉터리의 하위 디렉터리에 어셈블리를 넣을 수 있습니다. 자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하세요.  
  
> [!NOTE]
>  이것이 개발만을 위한 고급 기능입니다.  
  
 다음 예제에서는 런타임에서 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 이 설정의 기본값은 false입니다.  
  
> [!NOTE]
>  개발 시에만이 설정을 사용 합니다. 런타임에서 DEVPATH에서 발견 된 강력한 이름의 어셈블리에 있는 버전을 확인 하지 않습니다. 단순히 처음 발견 한 어셈블리를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 앱 구성](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
