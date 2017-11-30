---
title: "COM Interop 예외 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: error-reference
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bc3e01bc8ca463460ede9544d1d5c095c39a59d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="handling-com-interop-exceptions"></a><span data-ttu-id="f0730-102">COM Interop 예외 처리</span><span class="sxs-lookup"><span data-stu-id="f0730-102">Handling COM Interop Exceptions</span></span>
<span data-ttu-id="f0730-103">관리 코드와 비관리 코드를 함께 사용하여 예외를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-103">Managed and unmanaged code can work together to handle exceptions.</span></span> <span data-ttu-id="f0730-104">메서드가 관리 코드에서 예외를 throw하면 공용 언어 런타임이 HRESULT를 COM 개체에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-104">If a method throws an exception in managed code, the common language runtime can pass an HRESULT to a COM object.</span></span> <span data-ttu-id="f0730-105">메서드가 비관리 코드에서 오류 HRESULT를 반환함으로써 실패하면 런타임에서는 관리 코드가 catch할 수 있는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-105">If a method fails in unmanaged code by returning a failure HRESULT, the runtime throws an exception that can be caught by managed code.</span></span>  
  
 <span data-ttu-id="f0730-106">런타임은 자동으로 COM interop에서 더 구체적인 예외로 HRESULT를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-106">The runtime automatically maps the HRESULT from COM interop to more specific exceptions.</span></span> <span data-ttu-id="f0730-107">예를 들어 E_ACCESSDENIED가 <xref:System.UnauthorizedAccessException>이 되고, E_OUTOFMEMORY가 <xref:System.OutOfMemoryException>이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-107">For example, E_ACCESSDENIED becomes <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY becomes <xref:System.OutOfMemoryException>, and so on.</span></span>  
  
 <span data-ttu-id="f0730-108">HRESULT가 사용자 지정 결과이거나 런타임에 인식되지 않으면 런타임에서는 제네릭 <xref:System.Runtime.InteropServices.COMException>을 클라이언트에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-108">If the HRESULT is a custom result or if it is unknown to the runtime, the runtime passes a generic <xref:System.Runtime.InteropServices.COMException> to the client.</span></span> <span data-ttu-id="f0730-109">**ErrorCode** 의 속성은 **COMException** HRESULT 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-109">The **ErrorCode** property of the **COMException** contains the HRESULT value.</span></span>  
  
## <a name="working-with-ierrorinfo"></a><span data-ttu-id="f0730-110">IErrorInfo 작업</span><span class="sxs-lookup"><span data-stu-id="f0730-110">Working with IErrorInfo</span></span>  
 <span data-ttu-id="f0730-111">COM에서 관리 코드로 오류가 전달되면 런타임에서는 예외 개체를 오류 정보로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-111">When an error is passed from COM to managed code, the runtime populates the exception object with error information.</span></span> <span data-ttu-id="f0730-112">IErrorInfo를 지원하고 HRESULTS를 반환하는 COM 개체는 관리 코드 예외에 이 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-112">COM objects that support IErrorInfo and return HRESULTS provide this information to managed code exceptions.</span></span> <span data-ttu-id="f0730-113">예를 들어 런타임에서는 COM 오류에서 예외의 <xref:System.Exception.Message%2A> 속성으로 설명을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-113">For example, the runtime maps the Description from the COM error to the exception's <xref:System.Exception.Message%2A> property.</span></span> <span data-ttu-id="f0730-114">HRESULT가 추가 오류 정보를 제공하지 않으면 런타임에서는 대부분 예외 속성을 기본값으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-114">If the HRESULT provides no additional error information, the runtime fills many of the exception's properties with default values.</span></span>  
  
 <span data-ttu-id="f0730-115">비관리 코드에서 메서드가 실패하면 관리 코드 세그먼트에 예외가 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-115">If a method fails in unmanaged code, an exception can be passed to a managed code segment.</span></span> <span data-ttu-id="f0730-116">항목 [HRESULT 및 예외](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) HRESULT 런타임 예외 개체에 매핑하는 방법을 보여 주는 표가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0730-116">The topic [HRESULTS and Exceptions](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) contains a table showing how HRESULTS map to runtime exception objects.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f0730-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0730-117">See Also</span></span>
[<span data-ttu-id="f0730-118">예외</span><span class="sxs-lookup"><span data-stu-id="f0730-118">Exceptions</span></span>](index.md) 
