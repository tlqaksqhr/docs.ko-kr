---
title: "DLL 함수 호출 | Microsoft Docs"
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
  - "COM interop, 플랫폼 호출"
  - "DLL 함수"
  - "비관리 코드와의 상호 운용, 플랫폼 호출"
  - "플랫폼 호출, 관리되지 않는 함수 호출"
  - "관리되지 않는 함수"
  - "관리되지 않는 함수, 호출"
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# DLL 함수 호출
관리되지 않는 DLL 함수를 호출하는 작업은 다른 관리 코드를 호출하는 것과 거의 비슷하지만 DLL 함수에 대한 혼란을 일으키는 몇 가지 차이점이 있습니다.  이 단원에서는 예외적인 호출 관련 항목에 대해 설명합니다.  
  
 플랫폼 호출로부터 반환되는 구조체는 관리 코드 및 비관리 코드에서 동일하게 표현되는 데이터 형식이어야 합니다.  이러한 형식은 변환할 필요가 없으므로 *blittable 형식*이라고 합니다\([Blittable 형식 및 비 Blittable 형식](../../../docs/framework/interop/blittable-and-non-blittable-types.md) 참조\).  비 blittable 구조체를 반환 형식으로 갖고 있는 함수를 호출할 경우 비 blittable 형식과 동일한 크기의 blittable 도우미 형식을 정의하고 함수 반환 후 데이터를 변환할 수 있습니다.  
  
## 단원 내용  
 [구조체 전달](../../../docs/framework/interop/passing-structures.md)  
 미리 정의된 레이아웃과 함께 데이터 구조체를 전달하는 작업에 대해 설명합니다.  
  
 [콜백 함수](../../../docs/framework/interop/callback-functions.md)  
 콜백 함수에 대한 기본 정보를 제공합니다.  
  
 [방법: 콜백 함수 구현](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 관리 코드에서 콜백 함수를 구현하는 방법에 대해 설명합니다.  
  
## 관련 단원  
 [관리되지 않는 DLL 함수 사용](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 관리되지 않는 DLL 함수를 플랫폼 호출을 통해 호출하는 방법에 대해 설명합니다.  
  
 [플랫폼 호출을 사용하여 데이터 마샬링](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 메서드 매개 변수를 선언하고 관리되지 않는 라이브러리에서 내보낸 함수에 인수를 전달하는 방법에 대해 설명합니다.