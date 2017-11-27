---
title: "비관리 코드와의 상호 운용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2db5b8c2425637e24086f54e8ef69b0e5aac3633
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="interoperating-with-unmanaged-code"></a>비관리 코드와의 상호 운용
.NET Framework를 기반으로 COM 구성 요소, COM+ 서비스, 외부 형식 라이브러리 및 여러 가지 운영 체제 서비스와 상호 작용할 수 있습니다. 관리 개체 모델과 관리되지 않는 개체 모델 간에는 데이터 형식, 메서드 시그니처 및 오류 처리 메커니즘이 달라집니다. .NET Framework 구성 요소와 비관리 코드 간에 상호 운용을 간소화하고 마이그레이션 경로를 줄이기 위해 공용 언어 런타임은 클라이언트 및 서버에서 둘 다 이러한 개체 모델의 차이점을 숨깁니다.  
  
 런타임 제어를 기반으로 실행되는 코드를 관리 코드라고 합니다. 이와 달리 런타임 외부에서 실행되는 코드를 비관리 코드라고 합니다. 비관리 코드로는 COM 구성 요소, ActiveX 인터페이스, Win32 API 함수 등이 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [비관리 코드와의 상호 운용 방법 항목](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 비관리 코드와의 상호 운영에 대한 개념 설명서에 나오는 모든 방법 항목에 대한 링크를 제공합니다.  
  
 [.NET Framework에 COM 구성 요소 노출](../../../docs/framework/interop/exposing-com-components.md)  
 .NET Framework 응용 프로그램에서 COM 구성 요소를 사용하는 방법을 설명합니다.  
  
 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 COM 응용 프로그램에서 .NET Framework 구성 요소를 사용하는 방법을 설명합니다.  
  
 [관리되지 않는 DLL 함수 사용](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 플랫폼 호출을 사용하여 관리되지 않는 DLL 함수를 호출하는 방법을 설명합니다.  
  
 [상호 운용을 위한 디자인 고려 사항](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 통합된 COM 구성 요소를 작성하기 위한 팁을 제공합니다.  
  
 [interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)  
 COM interop 및 플랫폼 호출에 대한 마샬링을 설명합니다.  
  
 [방법: HRESULT 및 예외 매핑](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 실행과 HRESULT 간 매핑을 설명합니다.  
  
 [제네릭 형식을 통한 상호 운용](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 COM interop에서 사용될 경우 제네릭 형식의 동작을 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [고급 COM 상호 운용성](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 COM 구성 요소를 .NET Framework 응용 프로그램으로 통합하는 방법에 대한 추가정보 링크를 제공합니다.
