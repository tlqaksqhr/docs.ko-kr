---
title: "방법: DEVPATH를 사용하여 어셈블리 찾기 | Microsoft Docs"
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
  - ".NET Framework 응용 프로그램 구성, 어셈블리"
  - "app.config 파일, 어셈블리 위치"
  - "응용 프로그램 구성 파일, 어셈블리의 위치 지정"
  - "어셈블리[.NET Framework], 위치"
  - "DEVPATH"
  - "어셈블리 찾기"
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# 방법: DEVPATH를 사용하여 어셈블리 찾기
개발자는 작성 중인 공유 어셈블리가 여러 응용 프로그램에서 제대로 동작하는지를 확인해야 할 경우가 있습니다.  개발자는 개발 주기 동안 어셈블리를 전역 어셈블리 캐시에 지속적으로 저장하는 대신, 어셈블리의 빌드 출력 디렉터리를 가리키는 DEVPATH 환경 변수를 만들 수 있습니다.  
  
 예를 들어, 사용자가 MySharedAssembly라는 공유 어셈블리를 작성하고 있으며 출력 디렉터리가 C:\\MySharedAssembly\\Debug라고 가정합시다.  사용자는 C:\\MySharedAssembly\\Debug를 DEVPATH 변수에 저장할 수 있습니다.  그런 다음 [\<developmentMode\>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) 요소를 머신 구성 파일에서 지정해야 합니다.  이 요소는 DEVPATH를 사용하여 어셈블리를 찾도록 공용 언어 런타임에 지시합니다.  
  
 공유 어셈블리는 런타임에 검색 가능해야 합니다.  어셈블리 참조를 해결하기 위한 개인 디렉토리를 지정하기 위해 구성 파일에서 [\<codeBase\> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)[\<probing\> 요소](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)을 사용합니다. 이것은 [어셈블리 위치 지정](../../../docs/framework/configure-apps/specify-assembly-location.md)에 나와 있습니다.  또는 응용 프로그램 디렉터리의 하위 디렉터리에 어셈블리를 넣을 수 있습니다.  자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)을 참조하십시오.  
  
> [!NOTE]
>  이는 개발에 사용할 수 있는 고급 기능입니다.  
  
 다음 예제에서는 DEVPATH 환경 변수에 지정된 디렉터리에서 어셈블리를 찾도록 런타임을 지정하는 방법을 보여 줍니다.  
  
## 예제  
  
```  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 이 설정의 기본값은 false입니다.  
  
> [!NOTE]
>  이 설정은 개발 과정에서만 사용해야 합니다.  런타임에는 DEVPATH에 있는 강력한 이름의 어셈블리의 버전은 확인하지 않고  처음 발견한 어셈블리를 사용합니다.  
  
## 참고 항목  
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/ko-kr/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)