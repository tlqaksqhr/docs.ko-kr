---
title: ".NET Framework 구성 요소를 COM에 노출 | Microsoft Docs"
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
  - "COM interop, COM 구성 요소 게시"
  - ".NET Framework 구성 요소를 COM에 노출"
  - "비관리 코드와의 상호 운용, .NET Framework 구성 요소 게시"
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# .NET Framework 구성 요소를 COM에 노출
개발자는 .NET 형식을 작성하고 작성한 형식을 비관리 코드에서 사용합니다.  이 단원에서는 COM 클라이언트와 상호 운용되는 관리 코드를 작성하는 방법에 대해 설명합니다.  
  
-   [상호 운용할 .NET 형식의 정규화](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)  
  
     COM에 노출하려는 관리되는 모든 형식, 메서드, 속성, 필드 및 이벤트는 공용이어야 합니다.  형식에는 COM을 통해 호출될 수 있는 유일한 생성자인 공용 기본 생성자가 있어야 합니다.  
  
-   [interop 특성 적용](../../../docs/framework/interop/applying-interop-attributes.md)  
  
     관리 코드에 사용자 지정 특성을 사용함으로써 구성 요소의 상호 운용성을 향상시킬 수 있습니다.  
  
-   [COM에서 사용할 어셈블리의 패키징](../../../docs/framework/interop/packaging-an-assembly-for-com.md)  
  
     경우에 따라, COM 개발자는 어셈블리를 참조하고 배포하는 작업의 단계에 대한 요약을 필요로할 수 있습니다.  
  
 이 단원에서는 관리되는 형식을 COM 클라이언트에서 사용하는 데 필요한 작업에 대해서도 설명합니다.  
  
#### 관리되는 형식을 COM에서 사용하려면  
  
1.  [COM에 어셈블리 등록](../../../docs/framework/interop/registering-assemblies-with-com.md)  
  
     어셈블리 및 형식 라이브러리의 형식은 디자인 타임에 등록되어야 합니다.  설치 관리자에서 어셈블리를 등록하지 않는 경우, COM 개발자는 Regasm.exe를 사용할 수 있습니다.  
  
2.  [COM에서 .NET 형식 참조](../../../docs/framework/interop/how-to-reference-net-types-from-com.md)  
  
     COM 개발자는 현재 사용하는 도구 및 기술을 사용하여 어셈블리의 형식을 참조할 수 있습니다.  
  
3.  [.NET 개체 호출](http://msdn.microsoft.com/ko-kr/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
  
     COM 개발자는 관리되지 않는 형식에 대해 메서드를 호출하는 것과 마찬가지로 .NET 개체에 대해 메서드를 호출할 수 있습니다.  예를 들어, COM **CoCreateInstance** API는 .NET 개체를 활성화합니다.  
  
4.  [COM에서 액세스할 수 있도록 응용 프로그램 배포](http://msdn.microsoft.com/ko-kr/fb63564c-c1b9-4655-a094-a235625882ce)  
  
     강력한 이름의 어셈블리에는 게시자의 서명이 필요하며, 이 어셈블리는 전역 어셈블리 캐시에 설치할 수 있습니다.  강력한 이름의 어셈블리가 아닌 어셈블리는 클라이언트의 응용 프로그램 디렉터리에 설치해야 합니다.  
  
## 참고 항목  
 [비관리 코드와의 상호 운용](../../../docs/framework/interop/index.md)   
 [COM Interop 샘플: COM 클라이언트 및 .NET 서버](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)