---
title: "DLL 함수가 포함된 클래스 만들기 | Microsoft Docs"
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
  - "COM interop, DLL 함수"
  - "COM interop, 플랫폼 호출"
  - "DLL 함수"
  - "비관리 코드와의 상호 운용, DLL 함수"
  - "비관리 코드와의 상호 운용, 플랫폼 호출"
  - "플랫폼 호출, 기능에 대한 클래스 만들기"
  - "관리되지 않는 함수"
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# DLL 함수가 포함된 클래스 만들기
자주 사용되는 DLL 함수를 관리되는 클래스에 래핑하면 플랫폼 기능을 효율적으로 캡슐화할 수 있습니다.  모든 DLL 함수를 래핑할 필요는 없지만, DLL 함수 정의 작업은 번거롭고 오류도 쉽게 발생할 수 있기 때문에 클래스 래퍼를 사용하면 여러 가지 면에서 유용합니다.  Visual Basic 또는 C\#에서 프로그래밍하는 경우에는 DLL 함수를 클래스 또는 Visual Basic 모듈 안에 선언해야 합니다.  
  
 클래스 내에서 호출하려는 각 DLL 함수에 대한 정적 메서드를 정의해야 합니다.  이 정의에는 문자 집합 또는 메서드 인수를 전달할 때의 호출 규칙과 같은 추가 정보가 포함될 수 있는데, 이 정보를 생략하면 기본 설정이 사용됩니다.  선언 옵션 목록 및 해당 옵션의 기본 설정에 대한 자세한 내용은 [관리 코드에서 프로토타입 만들기](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)를 참조하십시오.  
  
 함수를 래핑하면 다른 정적 함수에 대해 메서드를 호출할 때와 마찬가지로, 래핑된 함수에 대해 메서드를 호출할 수 있습니다.  플랫폼 호출은 내보낸 내부 함수를 자동으로 처리합니다.  
  
 플랫폼 호출에 사용할 관리되는 클래스를 디자인할 때에는 클래스와 DLL 함수의 관계를 고려해야 합니다.  예를 들어, 다음을 수행할 수 있습니다.  
  
-   기존 클래스 안에 DLL 함수를 선언합니다.  
  
-   함수를 서로 분리하고 찾기 쉽도록 각 DLL 함수에 대해 클래스를 만듭니다.  
  
-   서로 관련된 DLL 함수 집합에 대해 하나의 클래스를 만들어 논리 그룹을 형성하고 오버헤드를 줄입니다.  
  
 클래스와 해당 메서드의 이름은 원하는 대로 지정할 수 있습니다.  플랫폼 호출에서 사용되는 .NET 기반 선언의 생성 방법을 보여 주는 예제는 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)을 참조하십시오.  
  
## 참고 항목  
 [관리되지 않는 DLL 함수 사용](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)   
 [DLL 함수 식별](../../../docs/framework/interop/identifying-functions-in-dlls.md)   
 [관리 코드에서 프로토타입 만들기](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [DLL 함수 호출](../../../docs/framework/interop/calling-a-dll-function.md)