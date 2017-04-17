---
title: "비관리 코드와의 상호 운용 | Microsoft Docs"
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
  - ".NET Framework, 비관리 코드와의 상호 운용"
  - "구성 요소[.NET Framework], 비관리 코드와의 상호 운용"
  - "비관리 코드와의 상호 운용"
  - "비관리 코드와의 상호 운용, 상호 운용성 정보"
  - "관리 코드, 비관리 코드와의 상호 운용"
  - "비관리 코드"
  - "비관리 코드, 상호 운용"
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 비관리 코드와의 상호 운용
.NET Framework에서는 COM 구성 요소, COM\+ 서비스, 외부 형식 라이브러리 및 여러 가지 운영 체제 서비스와의 상호 운용을 지원합니다.  관리되는 개체 모델 및 관리되지 않는 개체 모델의 데이터 형식, 메서드 시그니처 및 오류 처리 메커니즘은 서로 다릅니다.  공용 언어 런타임에서는 .NET Framework 구성 요소와 비관리 코드 간의 상호 운용을 단순화하고 마이그레이션 경로를 쉽게하기 위해, 클라이언트와 서버 모두에서 이러한 개체 모델 간의 차이를 숨깁니다.  
  
 런타임의 제어를 받아 실행되는 코드를 관리 코드라고 하며  런타임 밖에서 실행되는 코드를 비관리 코드라고 합니다.  비관리 코드로는 COM 구성 요소, ActiveX 인터페이스 및 Win32 API 함수가 있습니다.  
  
## 단원 내용  
 [Interoperating with Unmanaged Code How\-to Topics](http://msdn.microsoft.com/ko-kr/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 개념 설명서에 있는 방법 항목 중 비관리 코드를 사용한 상호 운용에 관련된 모든 항목에 대한 링크를 제공합니다.  
  
 [.NET Framework에 COM 구성 요소 노출](../../../docs/framework/interop/exposing-com-components.md)  
 .NET Framework 응용 프로그램에서 COM 구성 요소를 사용하는 방법에 대해 설명합니다.  
  
 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 COM 응용 프로그램에서 .NET Framework 구성 요소를 사용하는 방법에 대해 설명합니다.  
  
 [관리되지 않는 DLL 함수 사용](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 관리되지 않는 DLL 함수를 플랫폼 호출을 통해 호출하는 방법에 대해 설명합니다.  
  
 [상호 운용을 위한 디자인 고려 사항](http://msdn.microsoft.com/ko-kr/b59637f6-fe35-40d6-ae72-901e7a707689)  
 통합 COM 구성 요소를 작성하기 위한 몇 가지 정보를 제공합니다.  
  
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)  
 COM interop와 플랫폼 호출에 대한 마샬링에 대해 설명합니다.  
  
 [방법: HRESULT 및 예외 매핑](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 예외와 HRESULT 간의 매핑에 대해 설명합니다.  
  
 [Interoperating Using Generic Types](http://msdn.microsoft.com/ko-kr/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 COM interop에서 사용될 때 제네릭 형식의 동작에 대해 설명합니다.  
  
## 관련 단원  
 [Advanced COM Interoperability](http://msdn.microsoft.com/ko-kr/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 COM 구성 요소를 .NET Framework 응용 프로그램에 통합하는 작업에 대한 자세한 정보로 연결되는 링크를 제공합니다.