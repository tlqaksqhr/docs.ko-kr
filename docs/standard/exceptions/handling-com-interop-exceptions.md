---
title: COM Interop 예외 처리
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9f4429d50f6b7646cb75fad44957a98812282928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571266"
---
# <a name="handling-com-interop-exceptions"></a>COM Interop 예외 처리
관리 코드와 비관리 코드를 함께 사용하여 예외를 처리합니다. 메서드가 관리 코드에서 예외를 throw하면 공용 언어 런타임이 HRESULT를 COM 개체에 전달할 수 있습니다. 메서드가 비관리 코드에서 오류 HRESULT를 반환함으로써 실패하면 런타임에서는 관리 코드가 catch할 수 있는 예외를 throw합니다.  
  
 런타임은 자동으로 COM interop에서 더 구체적인 예외로 HRESULT를 매핑합니다. 예를 들어 E_ACCESSDENIED가 <xref:System.UnauthorizedAccessException>이 되고, E_OUTOFMEMORY가 <xref:System.OutOfMemoryException>이 됩니다.  
  
 HRESULT가 사용자 지정 결과이거나 런타임에 인식되지 않으면 런타임에서는 제네릭 <xref:System.Runtime.InteropServices.COMException>을 클라이언트에 전달합니다. **COMException**의 **ErrorCode** 속성에는 HRESULT 값이 포함됩니다.  
  
## <a name="working-with-ierrorinfo"></a>IErrorInfo 작업  
 COM에서 관리 코드로 오류가 전달되면 런타임에서는 예외 개체를 오류 정보로 채웁니다. IErrorInfo를 지원하고 HRESULTS를 반환하는 COM 개체는 관리 코드 예외에 이 정보를 제공합니다. 예를 들어 런타임에서는 COM 오류에서 예외의 <xref:System.Exception.Message%2A> 속성으로 설명을 매핑합니다. HRESULT가 추가 오류 정보를 제공하지 않으면 런타임에서는 대부분 예외 속성을 기본값으로 채웁니다.  
  
 비관리 코드에서 메서드가 실패하면 관리 코드 세그먼트에 예외가 전달될 수 있습니다. [HRESULT 및 예외](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) 항목에는 HRESULT가 런타임 예외 개체에 매핑되는 방식을 보여주는 표가 있습니다.  

## <a name="see-also"></a>참고 항목
[예외](index.md) 
