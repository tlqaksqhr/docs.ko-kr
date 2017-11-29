---
title: "방법: COM에서 .NET 형식 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f58225e41d7e09471685395dd6e2194ee5de123c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reference-net-types-from-com"></a>방법: COM에서 .NET 형식 참조
클라이언트 및 서버 코드의 관점에서 COM과 .NET Framework의 차이점은 크게 눈에 띄지 않습니다. Microsoft Visual Basic 클라이언트는 개체 메서드와 구문, 속성 및 필드를 정확히 다른 COM 개체인 것처럼 노출하는 개체 브라우저에서 .NET 개체를 볼 수 있습니다.  
  
 동일한 도구를 사용하여 메타데이터를 COM 형식 라이브러리로 내보내지만 C++ 클라이언트의 경우 형식 라이브러리를 가져오는 프로세스가 약간 더 복잡합니다. 관리되지 않는 C++ 클라이언트에서 .NET 개체 멤버를 참조하려면 **#import** 지시문을 사용하여 TLB 파일(Tlbexp.exe로 생성됨)을 참조합니다. C++에서 형식 라이브러리를 참조할 경우 **raw_interfaces_only** 옵션을 지정하거나 기본 클래스 라이브러리 Mscorlib.tlb의 정의를 가져와야 합니다.  
  
### <a name="to-import-a-library"></a>라이브러리를 가져오려면  
  
-   **#import** 지시문에서 **raw_interfaces_only** 옵션을 지정합니다. 예:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     또는  
  
-   Mscorlib.tlb에 대한 #import 지시문을 포함합니다. 예:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework 구성 요소를 COM에 노출](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [COM에 어셈블리 등록](../../../docs/framework/interop/registering-assemblies-with-com.md)  
 [.NET 개체를 호출합니다.](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33)  
 [COM 액세스를 위해 응용 프로그램 배포](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce)
